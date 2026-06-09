# MdmSettings::GetProtectionSessionLastSent(unsigned __int64 *)

- ea: `0x180012f70`
- end: `0x1800130ac`
- name: `?GetProtectionSessionLastSent@MdmSettings@@SAJPEA_K@Z`
- size: `316`
- prototype: `__int64 __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c6e8`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x1800065c0`
- `0x180012d8c`
- `0x180012f70`
- `0x18001d21c`

## string_xrefs

- `0x180012fe8`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmsettings.cpp`
- `0x18001301a`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszKey, &cchKey))`

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
0x180012f70  mov     [rsp+arg_8], rbx
0x180012f75  push    rdi
0x180012f76  sub     rsp, 260h
0x180012f7d  mov     rax, cs:__security_cookie
0x180012f84  xor     rax, rsp
0x180012f87  mov     [rsp+268h+var_18], rax
0x180012f8f  mov     rdi, rcx
0x180012f92  xor     edx, edx; Val
0x180012f94  lea     rcx, [rsp+268h+SubKey]; void *
0x180012f99  mov     r8d, 208h; Size
0x180012f9f  call    memset_0
0x180012fa4  mov     [rsp+268h+var_238], 104h
0x180012fac  mov     qword ptr [rsp+268h+var_230], 0
0x180012fb5  mov     [rsp+268h+var_234], 8
0x180012fbd  test    rdi, rdi
0x180012fc0  jnz     short loc_180012FFC
0x180012fc2  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180012fc9  mov     ebx, 80070057h
0x180012fce  jz      loc_180013088
0x180012fd4  lea     rax, aCprPullvalue; "CPR(pullValue)"
0x180012fdb  mov     [rsp+268h+var_240], rax
0x180012fe0  mov     [rsp+268h+var_248], 76h ; 'v'
0x180012fe8  lea     r9, aOnecoreuapShel_2; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x180012fef  mov     r8d, ebx
0x180012ff2  call    McTemplateU0dsqs_EventWriteTransfer
0x180012ff7  jmp     loc_180013088
0x180012ffc  lea     rdx, [rsp+268h+var_238]; unsigned int *
0x180013001  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x180013006  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x18001300b  mov     ebx, eax
0x18001300d  test    eax, eax
0x18001300f  jns     short loc_180013030
0x180013011  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x180013018  jz      short loc_180013088
0x18001301a  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180013021  mov     [rsp+268h+var_240], rax
0x180013026  mov     [rsp+268h+var_248], 78h ; 'x'
0x18001302e  jmp     short loc_180012FE8
0x180013030  lea     r9, [rsp+268h+var_234]; unsigned int *
0x180013035  lea     r8, [rsp+268h+var_230]; unsigned __int8 *
0x18001303a  lea     rcx, [rsp+268h+SubKey]; lpSubKey
0x18001303f  call    ?GetByteValue@MdmRegistry@@SAJPEBG0QEAEAEAK@Z; MdmRegistry::GetByteValue(ushort const *,ushort const *,uchar * const,ulong &)
0x180013044  mov     ebx, eax
0x180013046  cmp     eax, 80070490h
0x18001304b  jz      short loc_180013081
0x18001304d  cmp     eax, 80070002h
0x180013052  jz      short loc_180013081
0x180013054  test    eax, eax
0x180013056  jns     short loc_18001307A
0x180013058  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001305f  jz      short loc_180013088
0x180013061  lea     rax, aChrHr; "CHR(hr)"
0x180013068  mov     [rsp+268h+var_240], rax
0x18001306d  mov     [rsp+268h+var_248], 88h
0x180013075  jmp     loc_180012FE8
0x18001307a  mov     rax, qword ptr [rsp+268h+var_230]
0x18001307f  jmp     short loc_180013085
0x180013081  xor     eax, eax
0x180013083  xor     ebx, ebx
0x180013085  mov     [rdi], rax
0x180013088  mov     eax, ebx
0x18001308a  mov     rcx, [rsp+268h+var_18]
0x180013092  xor     rcx, rsp; StackCookie
0x180013095  call    __security_check_cookie
0x18001309a  mov     rbx, [rsp+268h+arg_8]
0x1800130a2  add     rsp, 260h
0x1800130a9  pop     rdi
0x1800130aa  retn
```
