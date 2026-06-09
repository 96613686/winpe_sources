# AslRegistryOpenSubKey

- ea: `0x18006124c`
- end: `0x1800612ec`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800602e0`

## callees

- `0x18006124c`
- `0x180083870`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1800612dd`
- `ntdll!ZwOpenKey` at `0x1800612dd`
- `ntdll!RtlInitUnicodeStringEx` at `0x18006127d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18006127d`

## string_xrefs

- `0x18006129a`: `AslRegistryOpenSubKey`
- `0x180061289`: `AslRegistryOpenSubKey passed bad Path [%x]`

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
0x18006124c  push    rbp
0x18006124e  push    rbx
0x18006124f  push    rsi
0x180061250  push    rdi
0x180061251  mov     rbp, rsp
0x180061254  sub     rsp, 78h
0x180061258  xorps   xmm0, xmm0
0x18006125b  xor     eax, eax
0x18006125d  mov     [rcx], rax
0x180061260  mov     rsi, rdx
0x180061263  mov     rdi, rcx
0x180061266  mov     rdx, r8; SourceString
0x180061269  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006126d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180061271  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180061275  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180061279  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18006127d  call    cs:__imp_RtlInitUnicodeStringEx
0x180061283  mov     ebx, eax
0x180061285  test    eax, eax
0x180061287  jns     short loc_1800612AF
0x180061289  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x180061290  mov     [rsp+78h+var_58], eax
0x180061294  mov     r8d, 3BEh
0x18006129a  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x1800612a1  mov     ecx, 1
0x1800612a6  call    AslLogCallPrintf
0x1800612ab  mov     eax, ebx
0x1800612ad  jmp     short loc_1800612E3
0x1800612af  lea     rax, [rbp+DestinationString]
0x1800612b3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800612ba  xorps   xmm0, xmm0
0x1800612bd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800612c1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800612c5  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800612c9  mov     edx, 20019h; DesiredAccess
0x1800612ce  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800612d5  mov     rcx, rdi; KeyHandle
0x1800612d8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800612dd  call    cs:__imp_ZwOpenKey
0x1800612e3  add     rsp, 78h
0x1800612e7  pop     rdi
0x1800612e8  pop     rsi
0x1800612e9  pop     rbx
0x1800612ea  pop     rbp
0x1800612eb  retn
```
