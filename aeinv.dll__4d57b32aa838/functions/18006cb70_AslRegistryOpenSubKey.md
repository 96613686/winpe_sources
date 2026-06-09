# AslRegistryOpenSubKey

- ea: `0x18006cb70`
- end: `0x18006cc10`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180069a0c`
- `0x18006ff68`

## callees

- `0x1800197d4`
- `0x18006cb70`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x18006cba1`
- `ntdll!RtlInitUnicodeStringEx` at `0x18006cba1`
- `ntdll!ZwOpenKey` at `0x18006cc01`
- `ntdll!ZwOpenKey` at `0x18006cc01`

## string_xrefs

- `0x18006cbad`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18006cbbe`: `AslRegistryOpenSubKey`

## pseudocode

```c
NTSTATUS __fastcall AslRegistryOpenSubKey(PHANDLE KeyHandle, void *a2, const WCHAR *a3)
{
  NTSTATUS inited; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  *KeyHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  inited = RtlInitUnicodeStringEx(&DestinationString, a3);
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
    AslLogCallPrintf(
      1,
      (unsigned int)"AslRegistryOpenSubKey",
      958,
      (unsigned int)"AslRegistryOpenSubKey passed bad Path [%x]");
    return inited;
  }
}

```

## disassembly

```asm
0x18006cb70  push    rbp
0x18006cb72  push    rbx
0x18006cb73  push    rsi
0x18006cb74  push    rdi
0x18006cb75  mov     rbp, rsp
0x18006cb78  sub     rsp, 78h
0x18006cb7c  xorps   xmm0, xmm0
0x18006cb7f  xor     eax, eax
0x18006cb81  mov     [rcx], rax
0x18006cb84  mov     rsi, rdx
0x18006cb87  mov     rdi, rcx
0x18006cb8a  mov     rdx, r8; SourceString
0x18006cb8d  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006cb91  lea     rcx, [rbp+DestinationString]; DestinationString
0x18006cb95  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18006cb99  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18006cb9d  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18006cba1  call    cs:__imp_RtlInitUnicodeStringEx
0x18006cba7  mov     ebx, eax
0x18006cba9  test    eax, eax
0x18006cbab  jns     short loc_18006CBD3
0x18006cbad  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18006cbb4  mov     [rsp+78h+var_58], eax
0x18006cbb8  mov     r8d, 3BEh
0x18006cbbe  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18006cbc5  mov     ecx, 1
0x18006cbca  call    AslLogCallPrintf
0x18006cbcf  mov     eax, ebx
0x18006cbd1  jmp     short loc_18006CC07
0x18006cbd3  lea     rax, [rbp+DestinationString]
0x18006cbd7  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18006cbde  xorps   xmm0, xmm0
0x18006cbe1  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006cbe5  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18006cbe9  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18006cbed  mov     edx, 20019h; DesiredAccess
0x18006cbf2  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18006cbf9  mov     rcx, rdi; KeyHandle
0x18006cbfc  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18006cc01  call    cs:__imp_ZwOpenKey
0x18006cc07  add     rsp, 78h
0x18006cc0b  pop     rdi
0x18006cc0c  pop     rsi
0x18006cc0d  pop     rbx
0x18006cc0e  pop     rbp
0x18006cc0f  retn
```
