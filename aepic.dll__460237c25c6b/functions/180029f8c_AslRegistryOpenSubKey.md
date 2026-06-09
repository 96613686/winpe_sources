# AslRegistryOpenSubKey

- ea: `0x180029f8c`
- end: `0x18002a02c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180035868`

## callees

- `0x1800295dc`
- `0x180029f8c`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18002a01d`
- `ntdll!ZwOpenKey` at `0x18002a01d`
- `ntdll!RtlInitUnicodeStringEx` at `0x180029fbd`
- `ntdll!RtlInitUnicodeStringEx` at `0x180029fbd`

## string_xrefs

- `0x180029fc9`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x180029fda`: `AslRegistryOpenSubKey`

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
0x180029f8c  push    rbp
0x180029f8e  push    rbx
0x180029f8f  push    rsi
0x180029f90  push    rdi
0x180029f91  mov     rbp, rsp
0x180029f94  sub     rsp, 78h
0x180029f98  xorps   xmm0, xmm0
0x180029f9b  xor     eax, eax
0x180029f9d  mov     [rcx], rax
0x180029fa0  mov     rsi, rdx
0x180029fa3  mov     rdi, rcx
0x180029fa6  mov     rdx, r8; SourceString
0x180029fa9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180029fad  lea     rcx, [rbp+DestinationString]; DestinationString
0x180029fb1  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180029fb5  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180029fb9  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x180029fbd  call    cs:__imp_RtlInitUnicodeStringEx
0x180029fc3  mov     ebx, eax
0x180029fc5  test    eax, eax
0x180029fc7  jns     short loc_180029FEF
0x180029fc9  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x180029fd0  mov     [rsp+78h+var_58], eax
0x180029fd4  mov     r8d, 3BEh
0x180029fda  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x180029fe1  mov     ecx, 1
0x180029fe6  call    AslLogCallPrintf
0x180029feb  mov     eax, ebx
0x180029fed  jmp     short loc_18002A023
0x180029fef  lea     rax, [rbp+DestinationString]
0x180029ff3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180029ffa  xorps   xmm0, xmm0
0x180029ffd  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002a001  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002a005  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18002a009  mov     edx, 20019h; DesiredAccess
0x18002a00e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18002a015  mov     rcx, rdi; KeyHandle
0x18002a018  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002a01d  call    cs:__imp_ZwOpenKey
0x18002a023  add     rsp, 78h
0x18002a027  pop     rdi
0x18002a028  pop     rsi
0x18002a029  pop     rbx
0x18002a02a  pop     rbp
0x18002a02b  retn
```
