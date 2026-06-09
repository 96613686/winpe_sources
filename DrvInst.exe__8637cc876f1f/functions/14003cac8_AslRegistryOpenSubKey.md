# AslRegistryOpenSubKey

- ea: `0x14003cac8`
- end: `0x14003cb68`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14003fba0`

## callees

- `0x14003bf18`
- `0x14003cac8`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14003caf9`
- `ntdll!RtlInitUnicodeStringEx` at `0x14003caf9`
- `ntdll!ZwOpenKey` at `0x14003cb59`
- `ntdll!ZwOpenKey` at `0x14003cb59`

## string_xrefs

- `0x14003cb16`: `AslRegistryOpenSubKey`
- `0x14003cb05`: `AslRegistryOpenSubKey passed bad Path [%x]`

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
0x14003cac8  push    rbp
0x14003caca  push    rbx
0x14003cacb  push    rsi
0x14003cacc  push    rdi
0x14003cacd  mov     rbp, rsp
0x14003cad0  sub     rsp, 78h
0x14003cad4  xorps   xmm0, xmm0
0x14003cad7  xor     eax, eax
0x14003cad9  mov     [rcx], rax
0x14003cadc  mov     rsi, rdx
0x14003cadf  mov     rdi, rcx
0x14003cae2  mov     rdx, r8; SourceString
0x14003cae5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14003cae9  lea     rcx, [rbp+DestinationString]; DestinationString
0x14003caed  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14003caf1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14003caf5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14003caf9  call    cs:__imp_RtlInitUnicodeStringEx
0x14003caff  mov     ebx, eax
0x14003cb01  test    eax, eax
0x14003cb03  jns     short loc_14003CB2B
0x14003cb05  lea     r9, aAslregistryope_0; "AslRegistryOpenSubKey passed bad Path ["...
0x14003cb0c  mov     [rsp+78h+var_58], eax
0x14003cb10  mov     r8d, 3BEh
0x14003cb16  lea     rdx, aAslregistryope; "AslRegistryOpenSubKey"
0x14003cb1d  mov     ecx, 1
0x14003cb22  call    AslLogCallPrintf
0x14003cb27  mov     eax, ebx
0x14003cb29  jmp     short loc_14003CB5F
0x14003cb2b  lea     rax, [rbp+DestinationString]
0x14003cb2f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14003cb36  xorps   xmm0, xmm0
0x14003cb39  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14003cb3d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14003cb41  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14003cb45  mov     edx, 20019h; DesiredAccess
0x14003cb4a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14003cb51  mov     rcx, rdi; KeyHandle
0x14003cb54  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14003cb59  call    cs:__imp_ZwOpenKey
0x14003cb5f  add     rsp, 78h
0x14003cb63  pop     rdi
0x14003cb64  pop     rsi
0x14003cb65  pop     rbx
0x14003cb66  pop     rbp
0x14003cb67  retn
```
