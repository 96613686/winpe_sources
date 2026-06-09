# AslRegistryOpenSubKey

- ea: `0x140012fdc`
- end: `0x14001307c`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001582c`

## callees

- `0x140012fdc`
- `0x1400151b0`

## import_xrefs

- `ntdll!RtlInitUnicodeStringEx` at `0x14001300d`
- `ntdll!RtlInitUnicodeStringEx` at `0x14001300d`
- `ntdll!ZwOpenKey` at `0x14001306d`
- `ntdll!ZwOpenKey` at `0x14001306d`

## string_xrefs

- `0x140013019`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x14001302a`: `AslRegistryOpenSubKey`

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
0x140012fdc  push    rbp
0x140012fde  push    rbx
0x140012fdf  push    rsi
0x140012fe0  push    rdi
0x140012fe1  mov     rbp, rsp
0x140012fe4  sub     rsp, 78h
0x140012fe8  xorps   xmm0, xmm0
0x140012feb  xor     eax, eax
0x140012fed  mov     [rcx], rax
0x140012ff0  mov     rsi, rdx
0x140012ff3  mov     rdi, rcx
0x140012ff6  mov     rdx, r8; SourceString
0x140012ff9  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x140012ffd  lea     rcx, [rbp+DestinationString]; DestinationString
0x140013001  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140013005  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x140013009  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14001300d  call    cs:__imp_RtlInitUnicodeStringEx
0x140013013  mov     ebx, eax
0x140013015  test    eax, eax
0x140013017  jns     short loc_14001303F
0x140013019  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x140013020  mov     [rsp+78h+var_58], eax
0x140013024  mov     r8d, 3BEh
0x14001302a  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x140013031  mov     ecx, 1
0x140013036  call    AslLogCallPrintf
0x14001303b  mov     eax, ebx
0x14001303d  jmp     short loc_140013073
0x14001303f  lea     rax, [rbp+DestinationString]
0x140013043  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14001304a  xorps   xmm0, xmm0
0x14001304d  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140013051  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140013055  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x140013059  mov     edx, 20019h; DesiredAccess
0x14001305e  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x140013065  mov     rcx, rdi; KeyHandle
0x140013068  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14001306d  call    cs:__imp_ZwOpenKey
0x140013073  add     rsp, 78h
0x140013077  pop     rdi
0x140013078  pop     rsi
0x140013079  pop     rbx
0x14001307a  pop     rbp
0x14001307b  retn
```
