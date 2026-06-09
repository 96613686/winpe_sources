# AslRegistryOpenKey

- ea: `0x180015c08`
- end: `0x180015c9a`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016e90`
- `0x180017f84`

## callees

- `0x1800152d0`
- `0x180015c08`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x180015c25`
- `ntdll!RtlInitUnicodeStringEx` at `0x180015c25`
- `ntdll!ZwOpenKey` at `0x180015c87`
- `ntdll!ZwOpenKey` at `0x180015c87`

## string_xrefs

- `0x180015c33`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x180015c44`: `AslRegistryOpenKey`

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
0x180015c08  push    rbp
0x180015c0a  push    rbx
0x180015c0b  push    rsi
0x180015c0c  push    rdi
0x180015c0d  mov     rbp, rsp
0x180015c10  sub     rsp, 78h
0x180015c14  mov     rdi, rcx
0x180015c17  xorps   xmm0, xmm0
0x180015c1a  lea     rcx, [rbp+DestinationString]; DestinationString
0x180015c1e  mov     esi, r8d
0x180015c21  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180015c25  call    cs:__imp_RtlInitUnicodeStringEx
0x180015c2b  xor     ecx, ecx
0x180015c2d  mov     ebx, eax
0x180015c2f  test    eax, eax
0x180015c31  jns     short loc_180015C57
0x180015c33  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x180015c3a  mov     [rsp+78h+var_58], eax
0x180015c3e  mov     r8d, 388h
0x180015c44  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x180015c4b  mov     ecx, 1
0x180015c50  call    AslLogCallPrintf
0x180015c55  jmp     short loc_180015C8F
0x180015c57  mov     [rdi], rcx
0x180015c5a  lea     rax, [rbp+DestinationString]
0x180015c5e  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x180015c62  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180015c66  xorps   xmm0, xmm0
0x180015c69  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180015c6d  mov     rcx, rdi; KeyHandle
0x180015c70  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180015c78  mov     edx, esi; DesiredAccess
0x180015c7a  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180015c82  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180015c87  call    cs:__imp_ZwOpenKey
0x180015c8d  mov     ebx, eax
0x180015c8f  mov     eax, ebx
0x180015c91  add     rsp, 78h
0x180015c95  pop     rdi
0x180015c96  pop     rsi
0x180015c97  pop     rbx
0x180015c98  pop     rbp
0x180015c99  retn
```
