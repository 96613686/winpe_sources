# AslRegistryOpenKey

- ea: `0x180029ef4`
- end: `0x180029f86`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e270`
- `0x180035868`

## callees

- `0x1800295dc`
- `0x180029ef4`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x180029f73`
- `ntdll!ZwOpenKey` at `0x180029f73`
- `ntdll!RtlInitUnicodeStringEx` at `0x180029f11`
- `ntdll!RtlInitUnicodeStringEx` at `0x180029f11`

## string_xrefs

- `0x180029f1f`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x180029f30`: `AslRegistryOpenKey`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // eax
  unsigned int v6; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
  v6 = inited;
  if ( inited >= 0 )
  {
    *KeyHandle = 0;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    return (unsigned int)ZwOpenKey(KeyHandle, a3, &ObjectAttributes);
  }
  else
  {
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]", inited);
  }
  return v6;
}

```

## disassembly

```asm
0x180029ef4  push    rbp
0x180029ef6  push    rbx
0x180029ef7  push    rsi
0x180029ef8  push    rdi
0x180029ef9  mov     rbp, rsp
0x180029efc  sub     rsp, 78h
0x180029f00  mov     rdi, rcx
0x180029f03  xorps   xmm0, xmm0
0x180029f06  lea     rcx, [rbp+DestinationString]; DestinationString
0x180029f0a  mov     esi, r8d
0x180029f0d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180029f11  call    cs:__imp_RtlInitUnicodeStringEx
0x180029f17  xor     ecx, ecx
0x180029f19  mov     ebx, eax
0x180029f1b  test    eax, eax
0x180029f1d  jns     short loc_180029F43
0x180029f1f  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x180029f26  mov     [rsp+78h+var_58], eax
0x180029f2a  mov     r8d, 388h
0x180029f30  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x180029f37  mov     ecx, 1
0x180029f3c  call    AslLogCallPrintf
0x180029f41  jmp     short loc_180029F7B
0x180029f43  mov     [rdi], rcx
0x180029f46  lea     rax, [rbp+DestinationString]
0x180029f4a  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180029f4e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180029f52  xorps   xmm0, xmm0
0x180029f55  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180029f59  mov     rcx, rdi; KeyHandle
0x180029f5c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180029f64  mov     edx, esi; DesiredAccess
0x180029f66  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180029f6e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180029f73  call    cs:__imp_ZwOpenKey
0x180029f79  mov     ebx, eax
0x180029f7b  mov     eax, ebx
0x180029f7d  add     rsp, 78h
0x180029f81  pop     rdi
0x180029f82  pop     rsi
0x180029f83  pop     rbx
0x180029f84  pop     rbp
0x180029f85  retn
```
