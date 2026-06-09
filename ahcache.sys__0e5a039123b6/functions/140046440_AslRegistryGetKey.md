# AslRegistryGetKey

- ea: `0x140046440`
- end: `0x140046659`
- name: `AslRegistryGetKey`
- size: `537`
- prototype: `__int64 __fastcall(void **, const WCHAR *, ACCESS_MASK, int)`
- caller_count: `8`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1400046e8`
- `0x140024700`
- `0x14002e270`
- `0x140033320`
- `0x140041638`
- `0x14004506c`
- `0x140046180`
- `0x14004634c`

## callees

- `0x14000436d`
- `0x14000440f`
- `0x1400044b1`
- `0x140004553`
- `0x14003e364`
- `0x140046440`
- `0x140051fcc`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046513`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046526`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046513`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140046526`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400464f1`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400464f1`

## string_xrefs

- `0x140046491`: `\Registry\Machine`
- `0x140046617`: `AslRegistryBuildMachinePath`
- `0x140046636`: `AslRegistryBuildMachinePath failed %x for %ws`
- `0x140046643`: `AslRegistryGetKey`
- `0x1400465ef`: `AslRegistryBuildUserPath failed %x for %ws`
- `0x1400465c4`: `NtOpenKey failed %x for %ws`

## pseudocode

```c
__int64 __fastcall AslRegistryGetKey(void **a1, const WCHAR *a2, ACCESS_MASK a3, int a4)
{
  __int64 v7; // rax
  NTSTATUS v8; // eax
  unsigned int v9; // edi
  int v11; // eax
  __int64 v12; // [rsp+28h] [rbp-21h]
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-1h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+Fh] BYREF
  void *KeyHandle; // [rsp+A8h] [rbp+5Fh] BYREF

  *a1 = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  Destination = 0;
  if ( a4 )
  {
    DestinationString = 0;
    RtlInitUnicodeString_0(&DestinationString, L"\\Registry\\Machine");
    v7 = -1;
    Destination.Length = 0;
    do
      ++v7;
    while ( a2[v7] );
    Destination.MaximumLength = DestinationString.Length + 2 * (v7 + 1);
    Destination.Buffer = (wchar_t *)ExAllocatePool2_0(256, Destination.MaximumLength, 1953517633);
    if ( !Destination.Buffer )
    {
      AslLogCallPrintf(
        1,
        "AslRegistryBuildMachinePath",
        1582,
        "Failed to allocate %d bytes for user key buffer",
        Destination.MaximumLength);
      v9 = -1073741801;
      LODWORD(v12) = -1073741801;
      AslLogCallPrintf(
        1,
        "AslRegistryGetKey",
        1718,
        "AslRegistryBuildMachinePath failed %x for %ws",
        v12,
        a2,
        *(_QWORD *)&Destination.Length);
      goto LABEL_11;
    }
    RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    if ( a2 && *a2 != 92 )
      RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeToString(&Destination, a2);
  }
  else
  {
    v11 = AslRegistryBuildUserPath(&Destination, a2);
    v9 = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(
        1,
        "AslRegistryGetKey",
        1725,
        "AslRegistryBuildUserPath failed %x for %ws",
        v11,
        a2,
        *(_QWORD *)&Destination.Length);
      goto LABEL_11;
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = ZwOpenKey_0(&KeyHandle, a3, &ObjectAttributes);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -1073741772 )
      AslLogCallPrintf(
        1,
        "AslRegistryGetKey",
        1761,
        "NtOpenKey failed %x for %ws",
        v8,
        a2,
        *(_QWORD *)&Destination.Length);
  }
  else
  {
    v9 = 0;
    *a1 = KeyHandle;
    KeyHandle = 0;
  }
LABEL_11:
  if ( Destination.Buffer )
    ExFreePoolWithTag_0(Destination.Buffer, 0x74705041u);
  return v9;
}

```

## disassembly

```asm
0x140046440  mov     rax, rsp
0x140046443  push    rbp
0x140046444  push    rdi
0x140046445  lea     rbp, [rax-57h]
0x140046449  sub     rsp, 88h
0x140046450  mov     [rax+10h], rbx
0x140046454  xorps   xmm0, xmm0
0x140046457  mov     [rax+18h], rsi
0x14004645b  mov     rbx, rdx
0x14004645e  mov     [rax+20h], r14
0x140046462  mov     rsi, rcx
0x140046465  mov     [rax-18h], r15
0x140046469  mov     r14d, r8d
0x14004646c  xor     r15d, r15d
0x14004646f  xor     eax, eax
0x140046471  mov     [rcx], r15
0x140046474  mov     [rbp+4Fh+KeyHandle], r15
0x140046478  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x14004647c  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x140046480  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x140046484  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x140046488  test    r9d, r9d
0x14004648b  jz      loc_1400465D7
0x140046491  lea     rdx, aRegistryMachin_8; "\\Registry\\Machine"
0x140046498  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x14004649c  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1400464a0  call    RtlInitUnicodeString_0
0x1400464a5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400464ac  mov     [rbp+4Fh+Destination.Length], r15w
0x1400464b1  inc     rax
0x1400464b4  cmp     [rbx+rax*2], r15w
0x1400464b9  jnz     short loc_1400464B1
0x1400464bb  inc     ax
0x1400464be  mov     ecx, 100h
0x1400464c3  add     ax, ax
0x1400464c6  mov     r8d, 74705041h
0x1400464cc  add     ax, [rbp+4Fh+DestinationString.Length]
0x1400464d0  movzx   edx, ax
0x1400464d3  mov     [rbp+4Fh+Destination.MaximumLength], dx
0x1400464d7  call    ExAllocatePool2_0
0x1400464dc  mov     [rbp+4Fh+Destination.Buffer], rax
0x1400464e0  test    rax, rax
0x1400464e3  jz      loc_140046602
0x1400464e9  lea     rdx, [rbp+4Fh+DestinationString]; Source
0x1400464ed  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400464f1  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400464f8  nop     dword ptr [rax+rax+00h]
0x1400464fd  test    rbx, rbx
0x140046500  jz      short loc_14004651F
0x140046502  cmp     word ptr [rbx], 5Ch ; '\'
0x140046506  jz      short loc_14004651F
0x140046508  lea     rdx, asc_14000AF88; "\\"
0x14004650f  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140046513  call    cs:__imp_RtlAppendUnicodeToString
0x14004651a  nop     dword ptr [rax+rax+00h]
0x14004651f  mov     rdx, rbx; Source
0x140046522  lea     rcx, [rbp+4Fh+Destination]; Destination
0x140046526  call    cs:__imp_RtlAppendUnicodeToString
0x14004652d  nop     dword ptr [rax+rax+00h]
0x140046532  lea     rax, [rbp+4Fh+Destination]
0x140046536  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x14004653d  xorps   xmm0, xmm0
0x140046540  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x140046544  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x140046548  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x14004654c  mov     edx, r14d; DesiredAccess
0x14004654f  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x140046556  lea     rcx, [rbp+4Fh+KeyHandle]; KeyHandle
0x14004655a  movdqu  xmmword ptr [rbp+2Fh], xmm0
0x14004655f  call    ZwOpenKey_0
0x140046564  mov     edi, eax
0x140046566  test    eax, eax
0x140046568  js      short loc_1400465B8
0x14004656a  mov     rax, [rbp+4Fh+KeyHandle]
0x14004656e  mov     edi, r15d
0x140046571  mov     [rsi], rax
0x140046574  mov     [rbp+4Fh+KeyHandle], r15
0x140046578  mov     rcx, [rbp+4Fh+Destination.Buffer]; P
0x14004657c  mov     r15, [rsp+80h]
0x140046584  mov     r14, [rsp+90h+arg_18]
0x14004658c  mov     rsi, [rsp+90h+arg_10]
0x140046594  mov     rbx, [rsp+90h+arg_8]
0x14004659c  test    rcx, rcx
0x14004659f  jz      short loc_1400465AB
0x1400465a1  mov     edx, 74705041h; Tag
0x1400465a6  call    ExFreePoolWithTag_0
0x1400465ab  mov     eax, edi
0x1400465ad  add     rsp, 88h
0x1400465b4  pop     rdi
0x1400465b5  pop     rbp
0x1400465b6  retn
0x1400465b8  cmp     eax, 0C0000034h
0x1400465bd  jz      short loc_140046578
0x1400465bf  mov     [rsp+28h], rbx
0x1400465c4  lea     r9, aNtopenkeyFaile; "NtOpenKey failed %x for %ws"
0x1400465cb  mov     dword ptr [rsp+90h+var_70], eax
0x1400465cf  mov     r8d, 6E1h
0x1400465d5  jmp     short loc_140046643
0x1400465d7  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400465db  call    AslRegistryBuildUserPath
0x1400465e0  mov     edi, eax
0x1400465e2  test    eax, eax
0x1400465e4  jns     loc_140046532
0x1400465ea  mov     [rsp+28h], rbx
0x1400465ef  lea     r9, aAslregistrybui_2; "AslRegistryBuildUserPath failed %x for "...
0x1400465f6  mov     dword ptr [rsp+90h+var_70], eax
0x1400465fa  mov     r8d, 6BDh
0x140046600  jmp     short loc_140046643
0x140046602  movzx   eax, [rbp+4Fh+Destination.MaximumLength]
0x140046606  lea     r9, aFailedToAlloca_24; "Failed to allocate %d bytes for user ke"...
0x14004660d  mov     r8d, 62Eh
0x140046613  mov     dword ptr [rsp+90h+var_70], eax
0x140046617  lea     rdx, aAslregistrybui_1; "AslRegistryBuildMachinePath"
0x14004661e  mov     ecx, 1
0x140046623  call    AslLogCallPrintf
0x140046628  mov     edi, 0C0000017h
0x14004662d  mov     [rsp+28h], rbx
0x140046632  mov     dword ptr [rsp+90h+var_70], edi
0x140046636  lea     r9, aAslregistrybui; "AslRegistryBuildMachinePath failed %x f"...
0x14004663d  mov     r8d, 6B6h
0x140046643  lea     rdx, aAslregistryget_0; "AslRegistryGetKey"
0x14004664a  mov     ecx, 1
0x14004664f  call    AslLogCallPrintf
0x140046654  jmp     loc_140046578
```
