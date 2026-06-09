# AslRegistryOpenKey

- ea: `0x1800313a4`
- end: `0x180031436`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002e694`
- `0x18002f0f4`

## callees

- `0x1800313a4`
- `0x180031a3c`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x180031423`
- `ntdll!ZwOpenKey` at `0x180031423`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800313c1`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800313c1`

## string_xrefs

- `0x1800313e0`: `AslRegistryOpenKey`
- `0x1800313cf`: `AslRegistryOpenKey passed bad Path [%x]`

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
0x1800313a4  push    rbp
0x1800313a6  push    rbx
0x1800313a7  push    rsi
0x1800313a8  push    rdi
0x1800313a9  mov     rbp, rsp
0x1800313ac  sub     rsp, 78h
0x1800313b0  mov     rdi, rcx
0x1800313b3  xorps   xmm0, xmm0
0x1800313b6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800313ba  mov     esi, r8d
0x1800313bd  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800313c1  call    cs:__imp_RtlInitUnicodeStringEx
0x1800313c7  xor     ecx, ecx
0x1800313c9  mov     ebx, eax
0x1800313cb  test    eax, eax
0x1800313cd  jns     short loc_1800313F3
0x1800313cf  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x1800313d6  mov     [rsp+78h+var_58], eax
0x1800313da  mov     r8d, 388h
0x1800313e0  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x1800313e7  mov     ecx, 1
0x1800313ec  call    AslLogCallPrintf
0x1800313f1  jmp     short loc_18003142B
0x1800313f3  mov     [rdi], rcx
0x1800313f6  lea     rax, [rbp+DestinationString]
0x1800313fa  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x1800313fe  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180031402  xorps   xmm0, xmm0
0x180031405  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180031409  mov     rcx, rdi; KeyHandle
0x18003140c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x180031414  mov     edx, esi; DesiredAccess
0x180031416  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003141e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180031423  call    cs:__imp_ZwOpenKey
0x180031429  mov     ebx, eax
0x18003142b  mov     eax, ebx
0x18003142d  add     rsp, 78h
0x180031431  pop     rdi
0x180031432  pop     rsi
0x180031433  pop     rbx
0x180031434  pop     rbp
0x180031435  retn
```
