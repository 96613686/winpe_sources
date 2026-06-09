# AslRegistryOpenKey

- ea: `0x140012f44`
- end: `0x140012fd6`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle, const WCHAR *, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001582c`
- `0x140016744`

## callees

- `0x140012f44`
- `0x1400151b0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x140012f61`
- `ntdll!RtlInitUnicodeStringEx` at `0x140012f61`
- `ntdll!ZwOpenKey` at `0x140012fc3`
- `ntdll!ZwOpenKey` at `0x140012fc3`

## string_xrefs

- `0x140012f6f`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x140012f80`: `AslRegistryOpenKey`

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
0x140012f44  push    rbp
0x140012f46  push    rbx
0x140012f47  push    rsi
0x140012f48  push    rdi
0x140012f49  mov     rbp, rsp
0x140012f4c  sub     rsp, 78h
0x140012f50  mov     rdi, rcx
0x140012f53  xorps   xmm0, xmm0
0x140012f56  lea     rcx, [rbp+DestinationString]; DestinationString
0x140012f5a  mov     esi, r8d
0x140012f5d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140012f61  call    cs:__imp_RtlInitUnicodeStringEx
0x140012f67  xor     ecx, ecx
0x140012f69  mov     ebx, eax
0x140012f6b  test    eax, eax
0x140012f6d  jns     short loc_140012F93
0x140012f6f  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x140012f76  mov     [rsp+78h+var_58], eax
0x140012f7a  mov     r8d, 388h
0x140012f80  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x140012f87  mov     ecx, 1
0x140012f8c  call    AslLogCallPrintf
0x140012f91  jmp     short loc_140012FCB
0x140012f93  mov     [rdi], rcx
0x140012f96  lea     rax, [rbp+DestinationString]
0x140012f9a  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x140012f9e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140012fa2  xorps   xmm0, xmm0
0x140012fa5  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140012fa9  mov     rcx, rdi; KeyHandle
0x140012fac  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012fb4  mov     edx, esi; DesiredAccess
0x140012fb6  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140012fbe  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012fc3  call    cs:__imp_ZwOpenKey
0x140012fc9  mov     ebx, eax
0x140012fcb  mov     eax, ebx
0x140012fcd  add     rsp, 78h
0x140012fd1  pop     rdi
0x140012fd2  pop     rsi
0x140012fd3  pop     rbx
0x140012fd4  pop     rbp
0x140012fd5  retn
```
