# FSMDeviceWatcher::UpdateSGPairCollection(IMFSensorGroupIdManager *,ushort const *,CTUnkArray<IMFSensorGroupIdInternal> &)

- ea: `0x180016120`
- end: `0x1800166fe`
- name: `?UpdateSGPairCollection@FSMDeviceWatcher@@SAJPEAUIMFSensorGroupIdManager@@PEBGAEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@@Z`
- size: `1502`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180012ec4`
- `0x180016d0c`

## callees

- `0x1800019f0`
- `0x180001dc0`
- `0x180002346`
- `0x18000265c`
- `0x180004f78`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a68`
- `0x180006a98`
- `0x18000d418`
- `0x18000f310`
- `0x180016120`
- `0x180017ca0`
- `0x180017d70`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x1800161a9`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x180016209`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x18001627f`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x18001649d`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x180016516`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x1800161a9`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x180016209`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x18001627f`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x18001649d`
- `MFSENSORGROUP!MFGetSensorDeviceRegistryProperty` at `0x180016516`
- `MFSENSORGROUP!MFGetSensorDeviceProperty` at `0x180016316`
- `MFSENSORGROUP!MFGetSensorDeviceProperty` at `0x180016316`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016298`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180016298`

## pseudocode

```c
__int64 __fastcall FSMDeviceWatcher::UpdateSGPairCollection(__int64 a1, __int64 a2, __int64 a3)
{
  HRESULT v6; // ebx
  __int64 v7; // rdx
  unsigned __int8 Level; // al
  char v9; // r14
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, __int64 *); // rbx
  __int64 v12; // rdx
  void *v13; // rax
  void *v14; // rdi
  const struct std::nothrow_t *v15; // rdx
  int v16; // edx
  __int64 v17; // rdx
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v20; // [rsp+50h] [rbp-B0h] BYREF
  int v21; // [rsp+58h] [rbp-A8h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  GUID v23; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v24[264]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(sz, 0, 0x208u);
  memset_0(v24, 0, 0x208u);
  if ( (unsigned int)MFGetSensorDeviceRegistryProperty(a2, L"FSSensorGroupID", 1) == -1072860816 )
  {
    v19 = 0;
    v21 = 0;
    pclsid = GUID_00000000_0000_0000_0000_000000000000;
    v23 = GUID_00000000_0000_0000_0000_000000000000;
    v6 = MFGetSensorDeviceRegistryProperty(a2, L"FSSensorGroupID", 1);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
LABEL_6:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v19);
LABEL_7:
        Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
        goto LABEL_52;
      }
      v7 = 63;
LABEL_5:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, 0, v6);
      goto LABEL_6;
    }
    if ( (int)MFGetSensorDeviceRegistryProperty(a2, L"FSSensorGroupName", 1) < 0 )
    {
      v9 = 0;
      v6 = StringCchPrintfW(v24, 0x104u, L"No %s", L"FSSensorGroupName");
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_6;
        v7 = 64;
        goto LABEL_5;
      }
    }
    else
    {
      v9 = 1;
    }
    v6 = CLSIDFromString(sz, &pclsid);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_6;
      v7 = 65;
      goto LABEL_5;
    }
    MFGetSensorDeviceProperty(a2, 0, &DEVPKEY_Device_ContainerId, &v23, 16, &v21);
    v19 = 0;
    v6 = FSMDeviceWatcher::FindInCollection(a1, a3, &pclsid, &v19);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_6;
      v7 = 66;
      goto LABEL_5;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 64LL))(v19, a2);
    if ( v6 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_6;
      v7 = 67;
      goto LABEL_5;
    }
    if ( v9 )
    {
      v10 = v19;
      v20 = 0;
      v11 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 96LL);
      wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v20);
      v6 = v11(v10, &v20);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        {
LABEL_27:
          wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v20);
          goto LABEL_6;
        }
        v12 = 68;
LABEL_26:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, 0, v6);
        goto LABEL_27;
      }
      v6 = (*(__int64 (__fastcall **)(__int64, const IID *, unsigned __int16 *))(*(_QWORD *)v20 + 200LL))(
             v20,
             &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
             v24);
      if ( v6 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_27;
        v12 = 69;
        goto LABEL_26;
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v20);
    }
    if ( (*(int (__fastcall **)(__int64))(*(_QWORD *)v19 + 184LL))(v19) < 0 )
    {
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
        v16 = 74;
        goto LABEL_49;
      }
    }
    else
    {
      if ( (unsigned int)MFGetSensorDeviceRegistryProperty(a2, L"FSSensorGroupCategoryList", 1) == -1072860816 )
      {
        v13 = operator new[](2u);
        v14 = v13;
        if ( !v13 )
        {
          v6 = -2147024882;
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_6;
          v7 = 70;
          goto LABEL_5;
        }
        memset_0(v13, 0, 2u);
        v6 = MFGetSensorDeviceRegistryProperty(a2, L"FSSensorGroupCategoryList", 1);
        if ( v6 >= 0
          && (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v19 + 168LL))(v19, v14) == -1072873841
          && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
        {
          WPP_SF_DSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v14, a2);
        }
        operator delete(v14, v15);
        if ( v6 < 0 )
        {
          if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            goto LABEL_6;
          v7 = 72;
          goto LABEL_5;
        }
        goto LABEL_50;
      }
      if ( (*(unsigned int (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 168LL))(v19, 0) == -1072873841
        && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
      {
        v16 = 73;
LABEL_49:
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v16,
          (unsigned int)&WPP_e195e873ff74378705b1ac731df50f11_Traceguids,
          -1072873841,
          a2);
      }
    }
LABEL_50:
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v19);
    goto LABEL_51;
  }
  v6 = StringCchPrintfW(sz, 0x104u, L"No %s", L"FSSensorGroupID");
  if ( v6 < 0 )
  {
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_7;
    v17 = 75;
LABEL_57:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_e195e873ff74378705b1ac731df50f11_Traceguids, 0, v6);
    goto LABEL_7;
  }
  v6 = StringCchPrintfW(v24, 0x104u, L"No %s", L"FSSensorGroupName");
  if ( v6 < 0 && _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
  {
    v17 = 76;
    goto LABEL_57;
  }
LABEL_51:
  Level = _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel();
  if ( v6 < 0 )
  {
LABEL_52:
    if ( Level )
      goto LABEL_62;
    return (unsigned int)v6;
  }
  if ( Level >= 8u )
LABEL_62:
    WPP_SF_DSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), a2, (__int64)sz, (__int64)v24);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180016120  push    rbp
0x180016122  push    rbx
0x180016123  push    rsi
0x180016124  push    rdi
0x180016125  push    r12
0x180016127  push    r14
0x180016129  push    r15
0x18001612b  lea     rbp, [rsp-3B0h]
0x180016133  sub     rsp, 4B0h
0x18001613a  mov     rax, cs:__security_cookie
0x180016141  xor     rax, rsp
0x180016144  mov     [rbp+3E0h+var_40], rax
0x18001614b  mov     r12, r8
0x18001614e  mov     dword ptr [rsp+4E0h+Size], 0
0x180016156  mov     rsi, rdx
0x180016159  mov     r15, rcx
0x18001615c  mov     ebx, 208h
0x180016161  lea     rcx, [rbp+3E0h+sz]; void *
0x180016168  mov     r8d, ebx; Size
0x18001616b  xor     edx, edx; Val
0x18001616d  call    memset_0
0x180016172  mov     r8d, ebx; Size
0x180016175  lea     rcx, [rbp+3E0h+var_460]; void *
0x180016179  xor     edx, edx; Val
0x18001617b  call    memset_0
0x180016180  xor     r9d, r9d
0x180016183  lea     rax, [rsp+4E0h+Size]
0x180016188  mov     [rsp+4E0h+var_4B8], rax
0x18001618d  lea     r14, aFssensorgroupi; "FSSensorGroupID"
0x180016194  mov     rdx, r14
0x180016197  mov     dword ptr [rsp+4E0h+var_4C0], 0
0x18001619f  mov     rcx, rsi
0x1800161a2  lea     ebx, [r9+1]
0x1800161a6  mov     r8d, ebx
0x1800161a9  call    cs:__imp_MFGetSensorDeviceRegistryProperty
0x1800161af  cmp     eax, 0C00D7170h
0x1800161b4  jnz     loc_180016612
0x1800161ba  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800161c1  lea     rax, [rsp+4E0h+Size]
0x1800161c6  mov     [rsp+4E0h+var_498], 0
0x1800161cf  mov     [rsp+4E0h+var_4B8], rax
0x1800161d4  lea     r9, [rbp+3E0h+sz]
0x1800161db  mov     edi, 206h
0x1800161e0  mov     [rsp+4E0h+var_488], 0
0x1800161e8  mov     r8d, ebx
0x1800161eb  mov     dword ptr [rsp+4E0h+Size], 0
0x1800161f3  mov     rdx, r14
0x1800161f6  mov     dword ptr [rsp+4E0h+var_4C0], edi
0x1800161fa  mov     rcx, rsi
0x1800161fd  movdqu  xmmword ptr [rsp+4E0h+pclsid.Data1], xmm0
0x180016203  movdqu  [rsp+4E0h+var_470], xmm0
0x180016209  call    cs:__imp_MFGetSensorDeviceRegistryProperty
0x18001620f  mov     ebx, eax
0x180016211  test    eax, eax
0x180016213  jns     short loc_180016255
0x180016215  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001621a  cmp     al, 1
0x18001621c  jb      short loc_180016241
0x18001621e  mov     edx, 3Fh ; '?'
0x180016223  mov     rcx, cs:WPP_GLOBAL_Control
0x18001622a  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x180016231  xor     r9d, r9d
0x180016234  mov     dword ptr [rsp+4E0h+var_4C0], ebx
0x180016238  mov     rcx, [rcx+10h]
0x18001623c  call    WPP_SF_qD
0x180016241  lea     rcx, [rsp+4E0h+var_498]
0x180016246  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18001624b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180016250  jmp     loc_180016600
0x180016255  lea     rax, [rsp+4E0h+Size]
0x18001625a  mov     dword ptr [rsp+4E0h+Size], 0
0x180016262  mov     [rsp+4E0h+var_4B8], rax
0x180016267  lea     r9, [rbp+3E0h+var_460]
0x18001626b  mov     r8d, 1
0x180016271  mov     dword ptr [rsp+4E0h+var_4C0], edi
0x180016275  lea     rdx, aFssensorgroupn; "FSSensorGroupName"
0x18001627c  mov     rcx, rsi
0x18001627f  call    cs:__imp_MFGetSensorDeviceRegistryProperty
0x180016285  test    eax, eax
0x180016287  js      short loc_1800162B7
0x180016289  mov     r14b, 1
0x18001628c  lea     rdx, [rsp+4E0h+pclsid]; pclsid
0x180016291  lea     rcx, [rbp+3E0h+sz]; lpsz
0x180016298  call    cs:__imp_CLSIDFromString
0x18001629e  mov     ebx, eax
0x1800162a0  test    eax, eax
0x1800162a2  jns     short loc_1800162F3
0x1800162a4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800162a9  cmp     al, 1
0x1800162ab  jb      short loc_180016241
0x1800162ad  mov     edx, 41h ; 'A'
0x1800162b2  jmp     loc_180016223
0x1800162b7  lea     r9, aFssensorgroupn; "FSSensorGroupName"
0x1800162be  mov     edx, 104h; unsigned __int64
0x1800162c3  lea     r8, aNoS; "No %s"
0x1800162ca  xor     r14b, r14b
0x1800162cd  lea     rcx, [rbp+3E0h+var_460]; unsigned __int16 *
0x1800162d1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800162d6  mov     ebx, eax
0x1800162d8  test    eax, eax
0x1800162da  jns     short loc_18001628C
0x1800162dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800162e1  cmp     al, 1
0x1800162e3  jb      loc_180016241
0x1800162e9  mov     edx, 40h ; '@'
0x1800162ee  jmp     loc_180016223
0x1800162f3  lea     rax, [rsp+4E0h+var_488]
0x1800162f8  xor     edx, edx
0x1800162fa  mov     [rsp+4E0h+var_4B8], rax
0x1800162ff  lea     r9, [rsp+4E0h+var_470]
0x180016304  lea     r8, DEVPKEY_Device_ContainerId
0x18001630b  mov     dword ptr [rsp+4E0h+var_4C0], 10h
0x180016313  mov     rcx, rsi
0x180016316  call    cs:__imp_MFGetSensorDeviceProperty
0x18001631c  mov     rcx, [rsp+4E0h+var_498]
0x180016321  mov     [rsp+4E0h+var_498], 0
0x18001632a  test    rcx, rcx
0x18001632d  jz      short loc_18001633B
0x18001632f  mov     rax, [rcx]
0x180016332  mov     rax, [rax+10h]
0x180016336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001633b  lea     r9, [rsp+4E0h+var_498]
0x180016340  mov     rdx, r12
0x180016343  lea     r8, [rsp+4E0h+pclsid]
0x180016348  mov     rcx, r15
0x18001634b  call    ?FindInCollection@FSMDeviceWatcher@@SAJPEAUIMFSensorGroupIdManager@@AEAV?$CTUnkArray@UIMFSensorGroupIdInternal@@@@AEBU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0012@@PEAPEAUIMFSensorGroupIdInternal@@@Z; FSMDeviceWatcher::FindInCollection(IMFSensorGroupIdManager *,CTUnkArray<IMFSensorGroupIdInternal> &,__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0012 const &,IMFSensorGroupIdInternal * *)
0x180016350  mov     ebx, eax
0x180016352  test    eax, eax
0x180016354  jns     short loc_18001636D
0x180016356  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001635b  cmp     al, 1
0x18001635d  jb      loc_180016241
0x180016363  mov     edx, 42h ; 'B'
0x180016368  jmp     loc_180016223
0x18001636d  mov     rcx, [rsp+4E0h+var_498]
0x180016372  mov     rdx, rsi
0x180016375  mov     rax, [rcx]
0x180016378  mov     rax, [rax+40h]
0x18001637c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016381  mov     ebx, eax
0x180016383  test    eax, eax
0x180016385  jns     short loc_18001639E
0x180016387  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18001638c  cmp     al, 1
0x18001638e  jb      loc_180016241
0x180016394  mov     edx, 43h ; 'C'
0x180016399  jmp     loc_180016223
0x18001639e  test    r14b, r14b
0x1800163a1  jz      loc_180016456
0x1800163a7  mov     rdi, [rsp+4E0h+var_498]
0x1800163ac  lea     rcx, [rsp+4E0h+var_490]
0x1800163b1  mov     [rsp+4E0h+var_490], 0
0x1800163ba  mov     rax, [rdi]
0x1800163bd  mov     rbx, [rax+60h]
0x1800163c1  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x1800163c6  lea     rdx, [rsp+4E0h+var_490]
0x1800163cb  mov     rcx, rdi
0x1800163ce  mov     rax, rbx
0x1800163d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800163d6  mov     ebx, eax
0x1800163d8  test    eax, eax
0x1800163da  jns     short loc_180016417
0x1800163dc  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800163e1  cmp     al, 1
0x1800163e3  jb      short loc_180016408
0x1800163e5  mov     edx, 44h ; 'D'
0x1800163ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800163f1  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800163f8  xor     r9d, r9d
0x1800163fb  mov     dword ptr [rsp+4E0h+var_4C0], ebx
0x1800163ff  mov     rcx, [rcx+10h]
0x180016403  call    WPP_SF_qD
0x180016408  lea     rcx, [rsp+4E0h+var_490]
0x18001640d  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180016412  jmp     loc_180016241
0x180016417  mov     rcx, [rsp+4E0h+var_490]
0x18001641c  lea     r8, [rbp+3E0h+var_460]
0x180016420  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME
0x180016427  mov     rax, [rcx]
0x18001642a  mov     rax, [rax+0C8h]
0x180016431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016436  mov     ebx, eax
0x180016438  test    eax, eax
0x18001643a  jns     short loc_18001644C
0x18001643c  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016441  cmp     al, 1
0x180016443  jb      short loc_180016408
0x180016445  mov     edx, 45h ; 'E'
0x18001644a  jmp     short loc_1800163EA
0x18001644c  lea     rcx, [rsp+4E0h+var_490]
0x180016451  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180016456  mov     rcx, [rsp+4E0h+var_498]
0x18001645b  mov     rax, [rcx]
0x18001645e  mov     rax, [rax+0B8h]
0x180016465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001646a  test    eax, eax
0x18001646c  js      loc_1800165B6
0x180016472  xor     r9d, r9d
0x180016475  mov     dword ptr [rsp+4E0h+Size], 0
0x18001647d  lea     rax, [rsp+4E0h+Size]
0x180016482  mov     rcx, rsi
0x180016485  mov     [rsp+4E0h+var_4B8], rax
0x18001648a  lea     rdx, aFssensorgroupc; "FSSensorGroupCategoryList"
0x180016491  mov     dword ptr [rsp+4E0h+var_4C0], 0
0x180016499  lea     r8d, [r9+1]
0x18001649d  call    cs:__imp_MFGetSensorDeviceRegistryProperty
0x1800164a3  cmp     eax, 0C00D7170h
0x1800164a8  jnz     loc_180016589
0x1800164ae  mov     eax, dword ptr [rsp+4E0h+Size]
0x1800164b2  add     eax, 2
0x1800164b5  mov     ecx, eax; unsigned __int64
0x1800164b7  mov     dword ptr [rsp+4E0h+Size], eax
0x1800164bb  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800164c0  mov     rdi, rax
0x1800164c3  test    rax, rax
0x1800164c6  jnz     short loc_1800164E2
0x1800164c8  mov     ebx, 8007000Eh
0x1800164cd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800164d2  cmp     al, 1
0x1800164d4  jb      loc_180016241
0x1800164da  lea     edx, [rdi+46h]
0x1800164dd  jmp     loc_180016223
0x1800164e2  mov     r8d, dword ptr [rsp+4E0h+Size]; Size
0x1800164e7  xor     edx, edx; Val
0x1800164e9  mov     rcx, rdi; void *
0x1800164ec  call    memset_0
0x1800164f1  lea     rax, [rsp+4E0h+Size]
0x1800164f6  mov     r9, rdi
0x1800164f9  mov     [rsp+4E0h+var_4B8], rax
0x1800164fe  lea     rdx, aFssensorgroupc; "FSSensorGroupCategoryList"
0x180016505  mov     eax, dword ptr [rsp+4E0h+Size]
0x180016509  mov     r8d, 1
0x18001650f  mov     rcx, rsi
0x180016512  mov     dword ptr [rsp+4E0h+var_4C0], eax
0x180016516  call    cs:__imp_MFGetSensorDeviceRegistryProperty
0x18001651c  mov     ebx, eax
0x18001651e  test    eax, eax
0x180016520  js      short loc_180016566
0x180016522  mov     rcx, [rsp+4E0h+var_498]
0x180016527  mov     rdx, rdi
0x18001652a  mov     rax, [rcx]
0x18001652d  mov     rax, [rax+0A8h]
0x180016534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016539  cmp     eax, 0C00D3E8Fh
0x18001653e  jnz     short loc_180016566
0x180016540  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180016545  cmp     al, 1
0x180016547  jb      short loc_180016566
0x180016549  mov     rcx, cs:WPP_GLOBAL_Control
0x180016550  mov     [rsp+4E0h+var_4B8], rsi; __int64
0x180016555  mov     [rsp+4E0h+var_4C0], rdi; __int64
0x18001655a  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180016561  call    WPP_SF_DSS
0x180016566  mov     rcx, rdi; void *
0x180016569  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001656e  test    ebx, ebx
0x180016570  jns     short loc_1800165E9
0x180016572  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180016577  cmp     al, 1
0x180016579  jb      loc_180016241
0x18001657f  mov     edx, 48h ; 'H'
0x180016584  jmp     loc_180016223
0x180016589  mov     rcx, [rsp+4E0h+var_498]
0x18001658e  xor     edx, edx
0x180016590  mov     rax, [rcx]
0x180016593  mov     rax, [rax+0A8h]
0x18001659a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001659f  cmp     eax, 0C00D3E8Fh
0x1800165a4  jnz     short loc_1800165E9
0x1800165a6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800165ab  cmp     al, 1
0x1800165ad  jb      short loc_1800165E9
0x1800165af  mov     edx, 49h ; 'I'
0x1800165b4  jmp     short loc_1800165C4
0x1800165b6  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800165bb  cmp     al, 1
0x1800165bd  jb      short loc_1800165E9
0x1800165bf  mov     edx, 4Ah ; 'J'
0x1800165c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800165cb  lea     r8, WPP_e195e873ff74378705b1ac731df50f11_Traceguids
0x1800165d2  mov     r9d, 0C00D3E8Fh
0x1800165d8  mov     [rsp+4E0h+var_4C0], rsi
0x1800165dd  mov     rcx, [rcx+0D8h]
0x1800165e4  call    WPP_SF_DS
0x1800165e9  lea     rcx, [rsp+4E0h+var_498]
0x1800165ee  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800165f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800165f8  test    ebx, ebx
0x1800165fa  jns     loc_1800166A2
0x180016600  cmp     al, 1
0x180016602  jb      loc_1800166DB
0x180016608  mov     edx, 4Dh ; 'M'
0x18001660d  jmp     loc_1800166AB
0x180016612  mov     edi, 104h
0x180016617  lea     r8, aNoS; "No %s"
0x18001661e  mov     edx, edi; unsigned __int64
0x180016620  lea     rcx, [rbp+3E0h+sz]; unsigned __int16 *
0x180016627  mov     r9, r14
0x18001662a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001662f  mov     ebx, eax
  ... truncated ...
```
