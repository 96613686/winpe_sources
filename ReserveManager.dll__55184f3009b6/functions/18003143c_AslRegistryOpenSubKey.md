# AslRegistryOpenSubKey

- ea: `0x18003143c`
- end: `0x1800314dc`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e694`

## callees

- `0x18003143c`
- `0x180031a3c`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x1800314cd`
- `ntdll!ZwOpenKey` at `0x1800314cd`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003146d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003146d`

## string_xrefs

- `0x18003148a`: `AslRegistryOpenSubKey`
- `0x180031479`: `AslRegistryOpenSubKey passed bad Path [%x]`

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
0x18003143c  push    rbp
0x18003143e  push    rbx
0x18003143f  push    rsi
0x180031440  push    rdi
0x180031441  mov     rbp, rsp
0x180031444  sub     rsp, 78h
0x180031448  xorps   xmm0, xmm0
0x18003144b  xor     eax, eax
0x18003144d  mov     [rcx], rax
0x180031450  mov     rsi, rdx
0x180031453  mov     rdi, rcx
0x180031456  mov     rdx, r8; SourceString
0x180031459  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003145d  lea     rcx, [rbp+DestinationString]; DestinationString
0x180031461  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180031465  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180031469  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18003146d  call    cs:__imp_RtlInitUnicodeStringEx
0x180031473  mov     ebx, eax
0x180031475  test    eax, eax
0x180031477  jns     short loc_18003149F
0x180031479  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x180031480  mov     [rsp+78h+var_58], eax
0x180031484  mov     r8d, 3BEh
0x18003148a  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x180031491  mov     ecx, 1
0x180031496  call    AslLogCallPrintf
0x18003149b  mov     eax, ebx
0x18003149d  jmp     short loc_1800314D3
0x18003149f  lea     rax, [rbp+DestinationString]
0x1800314a3  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800314aa  xorps   xmm0, xmm0
0x1800314ad  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800314b1  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800314b5  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x1800314b9  mov     edx, 20019h; DesiredAccess
0x1800314be  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x1800314c5  mov     rcx, rdi; KeyHandle
0x1800314c8  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800314cd  call    cs:__imp_ZwOpenKey
0x1800314d3  add     rsp, 78h
0x1800314d7  pop     rdi
0x1800314d8  pop     rsi
0x1800314d9  pop     rbx
0x1800314da  pop     rbp
0x1800314db  retn
```
