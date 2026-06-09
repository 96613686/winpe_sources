# AslRegistryOpenKey

- ea: `0x18004ca60`
- end: `0x18004caf2`
- name: `AslRegistryOpenKey`
- size: `146`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800463f0`
- `0x180049234`

## callees

- `0x18004c020`
- `0x18004ca60`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18004cadf`
- `ntdll!ZwOpenKey` at `0x18004cadf`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004ca7d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004ca7d`

## string_xrefs

- `0x18004ca8b`: `AslRegistryOpenKey passed bad Path [%x]`
- `0x18004ca9c`: `AslRegistryOpenKey`

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
0x18004ca60  push    rbp
0x18004ca62  push    rbx
0x18004ca63  push    rsi
0x18004ca64  push    rdi
0x18004ca65  mov     rbp, rsp
0x18004ca68  sub     rsp, 78h
0x18004ca6c  mov     rdi, rcx
0x18004ca6f  xorps   xmm0, xmm0
0x18004ca72  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004ca76  mov     esi, r8d
0x18004ca79  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004ca7d  call    cs:__imp_RtlInitUnicodeStringEx
0x18004ca83  xor     ecx, ecx
0x18004ca85  mov     ebx, eax
0x18004ca87  test    eax, eax
0x18004ca89  jns     short loc_18004CAAF
0x18004ca8b  lea     r9, aAslregistryope; "AslRegistryOpenKey passed bad Path [%x]"
0x18004ca92  mov     [rsp+78h+var_58], eax
0x18004ca96  mov     r8d, 388h
0x18004ca9c  lea     rdx, aAslregistryope_1; "AslRegistryOpenKey"
0x18004caa3  mov     ecx, 1
0x18004caa8  call    AslLogCallPrintf
0x18004caad  jmp     short loc_18004CAE7
0x18004caaf  mov     [rdi], rcx
0x18004cab2  lea     rax, [rbp+DestinationString]
0x18004cab6  mov     [rbp+ObjectAttributes.RootDirectory], rcx
0x18004caba  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004cabe  xorps   xmm0, xmm0
0x18004cac1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004cac5  mov     rcx, rdi; KeyHandle
0x18004cac8  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004cad0  mov     edx, esi; DesiredAccess
0x18004cad2  mov     qword ptr [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004cada  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004cadf  call    cs:__imp_ZwOpenKey
0x18004cae5  mov     ebx, eax
0x18004cae7  mov     eax, ebx
0x18004cae9  add     rsp, 78h
0x18004caed  pop     rdi
0x18004caee  pop     rsi
0x18004caef  pop     rbx
0x18004caf0  pop     rbp
0x18004caf1  retn
```
