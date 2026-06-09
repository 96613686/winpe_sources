# AslRegistryOpenKey

- ea: `0x18001590c`
- end: `0x18001599e`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012d8c`
- `0x1800137e0`

## callees

- `0x180015220`
- `0x18001590c`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180015929`
- `ntdll!RtlInitUnicodeStringEx` at `0x180015929`
- `ntdll!ZwOpenKey` at `0x18001598b`
- `ntdll!ZwOpenKey` at `0x18001598b`

## string_xrefs

- `0x180015948`: `AslRegistryOpenKey`
- `0x180015937`: `AslRegistryOpenKey passed bad Path [%x]`

## pseudocode

```c
__int64 __fastcall AslRegistryOpenKey(PHANDLE KeyHandle, const WCHAR *a2, ACCESS_MASK a3)
{
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  DestinationString = 0;
  inited = RtlInitUnicodeStringEx(&DestinationString, a2);
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
    AslLogCallPrintf(1, "AslRegistryOpenKey", 904, "AslRegistryOpenKey passed bad Path [%x]");
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001590c  push    rbp
0x18001590e  push    rbx
0x18001590f  push    rsi
0x180015910  push    rdi
0x180015911  mov     rbp, rsp
0x180015914  sub     rsp, 78h
0x180015918  mov     rdi, rcx
0x18001591b  xorps   xmm0, xmm0
0x18001591e  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015922  mov     esi, r8d
0x180015925  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015929  call    cs:__imp_RtlInitUnicodeStringEx
0x18001592f  xor     ecx, ecx
0x180015931  mov     ebx, eax
0x180015933  test    eax, eax
0x180015935  jns     short loc_18001595B
0x180015937  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18001593e  mov     [rsp+78h+var_58], eax
0x180015942  mov     r8d, 388h
0x180015948  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18001594f  mov     ecx, 1
0x180015954  call    AslLogCallPrintf
0x180015959  jmp     short loc_180015993
0x18001595b  mov     [rdi], rcx
0x18001595e  lea     rax, [rbp+DestinationString]
0x180015962  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180015966  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001596a  xorps   xmm0, xmm0
0x18001596d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180015971  mov     rcx, rdi; KeyHandle
0x180015974  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18001597c  mov     edx, esi; DesiredAccess
0x18001597e  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180015986  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18001598b  call    cs:__imp_ZwOpenKey
0x180015991  mov     ebx, eax
0x180015993  mov     eax, ebx
0x180015995  add     rsp, 78h
0x180015999  pop     rdi
0x18001599a  pop     rsi
0x18001599b  pop     rbx
0x18001599c  pop     rbp
0x18001599d  retn
```
