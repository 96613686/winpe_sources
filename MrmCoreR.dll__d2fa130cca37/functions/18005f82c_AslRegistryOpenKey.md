# AslRegistryOpenKey

- ea: `0x18005f82c`
- end: `0x18005f8be`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e0e8`
- `0x1800602e0`

## callees

- `0x18005f82c`
- `0x180083870`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18005f887`
- `ntdll!ZwOpenKey` at `0x18005f887`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005f849`
- `ntdll!RtlInitUnicodeStringEx` at `0x18005f849`

## string_xrefs

- `0x18005f89a`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18005f8ab`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  v6 = inited;
  if ( inited < 0 )
  {
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  }
  else
  {
    *KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
  }
  return v6;
}

```

## disassembly

```asm
0x18005f82c  push    rbp
0x18005f82e  push    rbx
0x18005f82f  push    rsi
0x18005f830  push    rdi
0x18005f831  mov     rbp, rsp
0x18005f834  sub     rsp, 78h
0x18005f838  mov     rdi, rcx
0x18005f83b  xorps   xmm0, xmm0
0x18005f83e  lea     rcx, [rbp+DestinationString]; DestinationString
0x18005f842  mov     esi, r8d
0x18005f845  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18005f849  call    cs:__imp_RtlInitUnicodeStringEx
0x18005f84f  xor     ecx, ecx
0x18005f851  mov     ebx, eax
0x18005f853  test    eax, eax
0x18005f855  js      short loc_18005F89A
0x18005f857  mov     [rdi], rcx
0x18005f85a  lea     rax, [rbp+DestinationString]
0x18005f85e  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18005f862  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18005f866  xorps   xmm0, xmm0
0x18005f869  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18005f86d  mov     rcx, rdi; KeyHandle
0x18005f870  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18005f878  mov     edx, esi; DesiredAccess
0x18005f87a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18005f882  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18005f887  call    cs:__imp_ZwOpenKey
0x18005f88d  mov     ebx, eax
0x18005f88f  mov     eax, ebx
0x18005f891  add     rsp, 78h
0x18005f895  pop     rdi
0x18005f896  pop     rsi
0x18005f897  pop     rbx
0x18005f898  pop     rbp
0x18005f899  retn
0x18005f89a  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18005f8a1  mov     [rsp+78h+var_58], eax
0x18005f8a5  mov     r8d, 388h
0x18005f8ab  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18005f8b2  mov     ecx, 1
0x18005f8b7  call    AslLogCallPrintf
0x18005f8bc  jmp     short loc_18005F88F
```
