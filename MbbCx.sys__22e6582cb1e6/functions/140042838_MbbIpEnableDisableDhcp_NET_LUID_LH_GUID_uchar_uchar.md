# MbbIpEnableDisableDhcp(_NET_LUID_LH *,_GUID *,uchar,uchar)

- ea: `0x140042838`
- end: `0x140042998`
- name: `?MbbIpEnableDisableDhcp@@YAJPEAT_NET_LUID_LH@@PEAU_GUID@@EE@Z`
- size: `352`
- prototype: `int(union _NET_LUID_LH *, struct _GUID *, unsigned __int8, unsigned __int8)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140046c6c`

## callees

- `0x140001cf8`
- `0x14004253c`
- `0x140042838`
- `0x140046ac4`

## import_xrefs

- `ntoskrnl!RtlWriteRegistryValue` at `0x1400428f1`
- `ntoskrnl!RtlWriteRegistryValue` at `0x1400428f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042978`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042978`

## pseudocode

```c
__int64 __fastcall MbbIpEnableDisableDhcp(union _NET_LUID_LH *a1, struct _GUID *a2, char a3)
{
  int v5; // edx
  unsigned int v6; // edi
  int v7; // r9d
  int v8; // r8d
  int v9; // r9d
  const char *v10; // rax
  int ValueData; // [rsp+20h] [rbp-38h]
  PCWSTR Path; // [rsp+40h] [rbp-18h] BYREF
  BOOL v14; // [rsp+70h] [rbp+18h] BYREF
  unsigned int v15; // [rsp+78h] [rbp+20h] BYREF

  Path = 0;
  v15 = 0;
  v14 = a3 != 0;
  v6 = MbbIpBuildInterfaceRegistryPath(a2, 0, &v15, (unsigned __int16 **)&Path);
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_12;
    v7 = 92;
    goto LABEL_4;
  }
  v6 = RtlWriteRegistryValue(0, Path, L"EnableDHCP", 4u, &v14, 4u);
  if ( v6 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v7 = 93;
LABEL_4:
      LOBYTE(v5) = 2;
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        2,
        v7,
        (__int64)WPP_f53708f2277a3aabca584f524242a299_Traceguids);
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v10 = "ENABLED";
    if ( !a3 )
      v10 = "DISABLED";
    WPP_RECORDER_SF_iss(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v8,
      v9,
      ValueData,
      a1->Value,
      (__int64)v10,
      (__int64)"DHCPV4");
  }
LABEL_12:
  if ( Path )
    ExFreePoolWithTag((PVOID)Path, 0);
  return v6;
}

```

## disassembly

```asm
0x140042838  mov     r11, rsp
0x14004283b  mov     [r11+8], rsi
0x14004283f  mov     [r11+10h], rdi
0x140042843  mov     [r11+20h], r9b
0x140042847  push    r14
0x140042849  sub     rsp, 50h
0x14004284d  xor     eax, eax
0x14004284f  mov     qword ptr [r11-18h], 0
0x140042857  test    r8b, r8b
0x14004285a  mov     [rsp+58h+arg_18], 0
0x140042862  mov     r10, rdx
0x140042865  lea     r9, [r11-18h]; unsigned __int16 **
0x140042869  setnz   al
0x14004286c  mov     sil, r8b
0x14004286f  mov     r14, rcx
0x140042872  mov     [rsp+58h+arg_10], eax
0x140042876  xor     edx, edx; unsigned __int8
0x140042878  lea     r8, [r11+20h]; unsigned int *
0x14004287c  mov     rcx, r10; Guid
0x14004287f  call    ?MbbIpBuildInterfaceRegistryPath@@YAJPEAU_GUID@@EPEAKPEAPEAG@Z; MbbIpBuildInterfaceRegistryPath(_GUID *,uchar,ulong *,ushort * *)
0x140042884  mov     edi, eax
0x140042886  test    eax, eax
0x140042888  jz      short loc_1400428CE
0x14004288a  lea     rcx, WPP_RECORDER_INITIALIZED
0x140042891  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140042898  jz      loc_140042969
0x14004289e  mov     r9d, 5Ch ; '\'
0x1400428a4  lea     rcx, WPP_f53708f2277a3aabca584f524242a299_Traceguids
0x1400428ab  mov     r8d, 2
0x1400428b1  mov     [rsp+58h+ValueData], rcx
0x1400428b6  mov     dl, r8b
0x1400428b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400428c0  mov     rcx, [rcx+40h]
0x1400428c4  call    WPP_RECORDER_SF_
0x1400428c9  jmp     loc_140042969
0x1400428ce  mov     rdx, [rsp+58h+Path]; Path
0x1400428d3  lea     rax, [rsp+58h+arg_10]
0x1400428d8  mov     r9d, 4; ValueType
0x1400428de  lea     r8, ValueName; "EnableDHCP"
0x1400428e5  mov     [rsp+58h+ValueLength], r9d; ValueLength
0x1400428ea  xor     ecx, ecx; RelativeTo
0x1400428ec  mov     [rsp+58h+ValueData], rax; ValueData
0x1400428f1  call    cs:__imp_RtlWriteRegistryValue
0x1400428f8  nop     dword ptr [rax+rax+00h]
0x1400428fd  mov     edi, eax
0x1400428ff  test    eax, eax
0x140042901  jz      short loc_14004291B
0x140042903  lea     rcx, WPP_RECORDER_INITIALIZED
0x14004290a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140042911  jz      short loc_140042969
0x140042913  mov     r9d, 5Dh ; ']'
0x140042919  jmp     short loc_1400428A4
0x14004291b  lea     rcx, WPP_RECORDER_INITIALIZED
0x140042922  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140042929  jz      short loc_140042969
0x14004292b  test    sil, sil
0x14004292e  lea     rcx, aDisabled; "DISABLED"
0x140042935  lea     rax, aEnabled; "ENABLED"
0x14004293c  cmovz   rax, rcx
0x140042940  lea     rcx, aDhcpv4; "DHCPV4"
0x140042947  mov     [rsp+58h+var_20], rcx
0x14004294c  mov     rcx, cs:WPP_GLOBAL_Control
0x140042953  mov     [rsp+58h+var_28], rax
0x140042958  mov     rax, [r14]
0x14004295b  mov     qword ptr [rsp+58h+ValueLength], rax
0x140042960  mov     rcx, [rcx+40h]
0x140042964  call    WPP_RECORDER_SF_iss
0x140042969  cmp     [rsp+58h+Path], 0
0x14004296f  jz      short loc_140042984
0x140042971  mov     rcx, [rsp+58h+Path]; P
0x140042976  xor     edx, edx; Tag
0x140042978  call    cs:__imp_ExFreePoolWithTag
0x14004297f  nop     dword ptr [rax+rax+00h]
0x140042984  mov     rsi, [rsp+58h+arg_0]
0x140042989  mov     eax, edi
0x14004298b  mov     rdi, [rsp+58h+arg_8]
0x140042990  add     rsp, 50h
0x140042994  pop     r14
0x140042996  retn
```
