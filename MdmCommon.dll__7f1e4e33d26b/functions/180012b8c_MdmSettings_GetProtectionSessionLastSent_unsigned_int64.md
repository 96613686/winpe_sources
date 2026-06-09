# MdmSettings::GetProtectionSessionLastSent(unsigned __int64 *)

- ea: `0x180012b8c`
- end: `0x180012cc7`
- name: `?GetProtectionSessionLastSent@MdmSettings@@SAJPEA_K@Z`
- size: `315`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c38c`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180006548`
- `0x1800129b0`
- `0x180012b8c`
- `0x18001cbb8`

## string_xrefs

- `0x180012c04`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x180012c36`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`

## pseudocode

```c
__int64 __fastcall MdmSettings::GetProtectionSessionLastSent(unsigned __int64 *a1)
{
  int v2; // edx
  int v3; // ecx
  unsigned int MdmCommonSettingValuesPersistedLocation; // ebx
  const unsigned __int16 *v5; // rdx
  int v6; // ecx
  int ByteValue; // eax
  int v8; // edx
  int v9; // ecx
  unsigned __int64 v10; // rax
  __int64 v12; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int8 v13[8]; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v12 = 0x800000104LL;
  *(_QWORD *)v13 = 0;
  if ( !a1 )
  {
    MdmCommonSettingValuesPersistedLocation = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v3,
        v2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        118,
        "CPR(pullValue)",
        v12);
    return MdmCommonSettingValuesPersistedLocation;
  }
  MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(SubKey, (unsigned int *)&v12);
  if ( (MdmCommonSettingValuesPersistedLocation & 0x80000000) != 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v6,
        (_DWORD)v5,
        MdmCommonSettingValuesPersistedLocation,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
        120,
        "CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))",
        v12);
    return MdmCommonSettingValuesPersistedLocation;
  }
  ByteValue = MdmRegistry::GetByteValue(SubKey, v5, v13, (unsigned int *)&v12 + 1);
  MdmCommonSettingValuesPersistedLocation = ByteValue;
  if ( ByteValue == -2147023728 || ByteValue == -2147024894 )
  {
    v10 = 0;
    MdmCommonSettingValuesPersistedLocation = 0;
    goto LABEL_15;
  }
  if ( ByteValue >= 0 )
  {
    v10 = *(_QWORD *)v13;
LABEL_15:
    *a1 = v10;
    return MdmCommonSettingValuesPersistedLocation;
  }
  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      ByteValue,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmsettings.cpp",
      136,
      "CHR(hr)",
      v12);
  return MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180012b8c  mov     [rsp+arg_8], rbx
0x180012b91  push    rdi
0x180012b92  sub     rsp, 260h
0x180012b99  mov     rax, cs:__security_cookie
0x180012ba0  xor     rax, rsp
0x180012ba3  mov     [rsp+268h+var_18], rax
0x180012bab  mov     rdi, rcx
0x180012bae  xor     edx, edx; Val
0x180012bb0  lea     rcx, [rsp+268h+SubKey]; void *
0x180012bb5  mov     r8d, 208h; Size
0x180012bbb  call    memset_0
0x180012bc0  mov     [rsp+268h+var_238], 104h
0x180012bc8  mov     qword ptr [rsp+268h+var_230], 0
0x180012bd1  mov     [rsp+268h+var_234], 8
0x180012bd9  test    rdi, rdi
0x180012bdc  jnz     short loc_180012C18
0x180012bde  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012be5  mov     ebx, 80070057h
0x180012bea  jz      loc_180012CA4
0x180012bf0  lea     rax, aCprPullvalue; "CPR(pullValue)"
0x180012bf7  mov     [rsp+268h+var_240], rax
0x180012bfc  mov     [rsp+268h+var_248], 76h ; 'v'
0x180012c04  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012c0b  mov     r8d, ebx
0x180012c0e  call    McTemplateU0dsqs_EventWriteTransfer
0x180012c13  jmp     loc_180012CA4
0x180012c18  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180012c1d  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x180012c22  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180012c27  mov     ebx, eax
0x180012c29  test    eax, eax
0x180012c2b  jns     short loc_180012C4C
0x180012c2d  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012c34  jz      short loc_180012CA4
0x180012c36  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180012c3d  mov     [rsp+268h+var_240], rax
0x180012c42  mov     [rsp+268h+var_248], 78h ; 'x'
0x180012c4a  jmp     short loc_180012C04
0x180012c4c  lea     r9, [rsp+268h+var_234]; unsigned int *
0x180012c51  lea     r8, [rsp+268h+var_230]; unsigned __int8 *
0x180012c56  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x180012c5b  call    ?GetByteValue@MdmRegistry@@SAJPEBG0QEAEAEAK@Z; MdmRegistry::GetByteValue(ushort const *,ushort const *,uchar * const,ulong &)
0x180012c60  mov     ebx, eax
0x180012c62  cmp     eax, 80070490h
0x180012c67  jz      short loc_180012C9D
0x180012c69  cmp     eax, 80070002h
0x180012c6e  jz      short loc_180012C9D
0x180012c70  test    eax, eax
0x180012c72  jns     short loc_180012C96
0x180012c74  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012c7b  jz      short loc_180012CA4
0x180012c7d  lea     rax, aChrHr; "CHR(hr)"
0x180012c84  mov     [rsp+268h+var_240], rax
0x180012c89  mov     [rsp+268h+var_248], 88h
0x180012c91  jmp     loc_180012C04
0x180012c96  mov     rax, qword ptr [rsp+268h+var_230]
0x180012c9b  jmp     short loc_180012CA1
0x180012c9d  xor     eax, eax
0x180012c9f  xor     ebx, ebx
0x180012ca1  mov     [rdi], rax
0x180012ca4  mov     eax, ebx
0x180012ca6  mov     rcx, [rsp+268h+var_18]
0x180012cae  xor     rcx, rsp; StackCookie
0x180012cb1  call    __security_check_cookie
0x180012cb6  mov     rbx, [rsp+268h+arg_8]
0x180012cbe  add     rsp, 260h
0x180012cc5  pop     rdi
0x180012cc6  retn
```
