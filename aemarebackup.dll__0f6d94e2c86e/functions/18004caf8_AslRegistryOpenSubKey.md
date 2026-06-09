# AslRegistryOpenSubKey

- ea: `0x18004caf8`
- end: `0x18004cb98`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `__int64 __fastcall(PHANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800463f0`

## callees

- `0x18004c020`
- `0x18004caf8`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18004cb89`
- `ntdll!ZwOpenKey` at `0x18004cb89`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004cb29`
- `ntdll!RtlInitUnicodeStringEx` at `0x18004cb29`

## string_xrefs

- `0x18004cb35`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18004cb46`: `AslRegistryOpenSubKey`

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
0x18004caf8  push    rbp
0x18004cafa  push    rbx
0x18004cafb  push    rsi
0x18004cafc  push    rdi
0x18004cafd  mov     rbp, rsp
0x18004cb00  sub     rsp, 78h
0x18004cb04  xorps   xmm0, xmm0
0x18004cb07  xor     eax, eax
0x18004cb09  mov     [rcx], rax
0x18004cb0c  mov     rsi, rdx
0x18004cb0f  mov     rdi, rcx
0x18004cb12  mov     rdx, r8; SourceString
0x18004cb15  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004cb19  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004cb1d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004cb21  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004cb25  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18004cb29  call    cs:__imp_RtlInitUnicodeStringEx
0x18004cb2f  mov     ebx, eax
0x18004cb31  test    eax, eax
0x18004cb33  jns     short loc_18004CB5B
0x18004cb35  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18004cb3c  mov     [rsp+78h+var_58], eax
0x18004cb40  mov     r8d, 3BEh
0x18004cb46  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18004cb4d  mov     ecx, 1
0x18004cb52  call    AslLogCallPrintf
0x18004cb57  mov     eax, ebx
0x18004cb59  jmp     short loc_18004CB8F
0x18004cb5b  lea     rax, [rbp+DestinationString]
0x18004cb5f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004cb66  xorps   xmm0, xmm0
0x18004cb69  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004cb6d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004cb71  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18004cb75  mov     edx, 20019h; DesiredAccess
0x18004cb7a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004cb81  mov     rcx, rdi; KeyHandle
0x18004cb84  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004cb89  call    cs:__imp_ZwOpenKey
0x18004cb8f  add     rsp, 78h
0x18004cb93  pop     rdi
0x18004cb94  pop     rsi
0x18004cb95  pop     rbx
0x18004cb96  pop     rbp
0x18004cb97  retn
```
