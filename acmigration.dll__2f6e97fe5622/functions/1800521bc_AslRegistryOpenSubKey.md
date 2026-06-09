# AslRegistryOpenSubKey

- ea: `0x1800521bc`
- end: `0x18005225c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005a904`

## callees

- `0x1800521bc`
- `0x1800543c0`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18005224d`
- `ntdll!ZwOpenKey` at `0x18005224d`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800521ed`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800521ed`

## string_xrefs

- `0x1800521f9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18005220a`: `AslRegistryOpenSubKey`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // eax
  NTSTATUS v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
  v6 = inited;
  if ( inited >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = a2;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return ZwOpenKey(KeyHandle, 0x20019u, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenSubKey", 958, "AslRegistryOpenSubKey passed bad Path [%x]", inited);
    return v6;
  }
}

```

## disassembly

```asm
0x1800521bc  push    rbp
0x1800521be  push    rbx
0x1800521bf  push    rsi
0x1800521c0  push    rdi
0x1800521c1  mov     rbp, rsp
0x1800521c4  sub     rsp, 78h
0x1800521c8  xorps   xmm0, xmm0
0x1800521cb  xor     eax, eax
0x1800521cd  mov     [rcx], rax
0x1800521d0  mov     rsi, rdx
0x1800521d3  mov     rdi, rcx
0x1800521d6  mov     rdx, r8; SourceString
0x1800521d9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800521dd  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800521e1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800521e5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800521e9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800521ed  call    cs:__imp_RtlInitUnicodeStringEx
0x1800521f3  mov     ebx, eax
0x1800521f5  test    eax, eax
0x1800521f7  jns     short loc_18005221F
0x1800521f9  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x180052200  mov     [rsp+78h+var_58], eax
0x180052204  mov     r8d, 3BEh
0x18005220a  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x180052211  mov     ecx, 1
0x180052216  call    AslLogCallPrintf
0x18005221b  mov     eax, ebx
0x18005221d  jmp     short loc_180052253
0x18005221f  lea     rax, [rbp+DestinationString]
0x180052223  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005222a  xorps   xmm0, xmm0
0x18005222d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180052231  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180052235  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x180052239  mov     edx, 20019h; DesiredAccess
0x18005223e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180052245  mov     rcx, rdi; KeyHandle
0x180052248  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005224d  call    cs:__imp_ZwOpenKey
0x180052253  add     rsp, 78h
0x180052257  pop     rdi
0x180052258  pop     rsi
0x180052259  pop     rbx
0x18005225a  pop     rbp
0x18005225b  retn
```
