# AslRegistryOpenSubKey

- ea: `0x18003d5c8`
- end: `0x18003d668`
- name: `AslRegistryOpenSubKey`
- size: `160`
- prototype: `NTSTATUS __fastcall(PHANDLE KeyHandle, void *, const WCHAR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180030054`
- `0x18003f210`

## callees

- `0x18000f114`
- `0x18003d5c8`

## import_xrefs

- `ntdll!ZwOpenKey` at `0x18003d659`
- `ntdll!ZwOpenKey` at `0x18003d659`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003d5f9`
- `ntdll!RtlInitUnicodeStringEx` at `0x18003d5f9`

## string_xrefs

- `0x18003d605`: `AslRegistryOpenSubKey passed bad Path [%x]`
- `0x18003d616`: `AslRegistryOpenSubKey`

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
0x18003d5c8  push    rbp
0x18003d5ca  push    rbx
0x18003d5cb  push    rsi
0x18003d5cc  push    rdi
0x18003d5cd  mov     rbp, rsp
0x18003d5d0  sub     rsp, 78h
0x18003d5d4  xorps   xmm0, xmm0
0x18003d5d7  xor     eax, eax
0x18003d5d9  mov     [rcx], rax
0x18003d5dc  mov     rsi, rdx
0x18003d5df  mov     rdi, rcx
0x18003d5e2  mov     rdx, r8; SourceString
0x18003d5e5  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18003d5e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003d5ed  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003d5f1  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18003d5f5  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18003d5f9  call    cs:__imp_RtlInitUnicodeStringEx
0x18003d5ff  mov     ebx, eax
0x18003d601  test    eax, eax
0x18003d603  jns     short loc_18003D62B
0x18003d605  lea     r9, aAslregistryope_2; "AslRegistryOpenSubKey passed bad Path ["...
0x18003d60c  mov     [rsp+78h+var_58], eax
0x18003d610  mov     r8d, 3BEh
0x18003d616  lea     rdx, aAslregistryope_0; "AslRegistryOpenSubKey"
0x18003d61d  mov     ecx, 1
0x18003d622  call    AslLogCallPrintf
0x18003d627  mov     eax, ebx
0x18003d629  jmp     short loc_18003D65F
0x18003d62b  lea     rax, [rbp+DestinationString]
0x18003d62f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18003d636  xorps   xmm0, xmm0
0x18003d639  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18003d63d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18003d641  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x18003d645  mov     edx, 20019h; DesiredAccess
0x18003d64a  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18003d651  mov     rcx, rdi; KeyHandle
0x18003d654  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18003d659  call    cs:__imp_ZwOpenKey
0x18003d65f  add     rsp, 78h
0x18003d663  pop     rdi
0x18003d664  pop     rsi
0x18003d665  pop     rbx
0x18003d666  pop     rbp
0x18003d667  retn
```
