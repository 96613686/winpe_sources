# LoadSensorGroupBySymbolicLink(ushort const *,unsigned __int64,IMFSensorGroup * *)

- ea: `0x180012284`
- end: `0x180012914`
- name: `?LoadSensorGroupBySymbolicLink@@YAJPEBG_KPEAPEAUIMFSensorGroup@@@Z`
- size: `1680`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, unsigned __int64, struct IMFSensorGroup **)`
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180010adc`
- `0x180066ae0`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000c348`
- `0x18000f5a0`
- `0x18000fde4`
- `0x1800114c0`
- `0x180012284`
- `0x180012d34`
- `0x1800133fc`
- `0x18001b39c`
- `0x18001c854`
- `0x18001c96c`
- `0x180025d70`
- `0x180028d34`
- `0x180028eb4`
- `0x18002ae3c`
- `0x18002af88`
- `0x18002b3dc`
- `0x18002c008`
- `0x18002d02c`
- `0x1800356d8`
- `0x18003c55c`
- `0x180044f30`
- `0x180051a1c`
- `0x18006dff0`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125eb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800125fa`

## pseudocode

```c
__int64 __fastcall LoadSensorGroupBySymbolicLink(LPCWSTR pszDeviceInterface, char a2, struct IMFSensorGroup **a3)
{
  char v4; // di
  char v6; // r15
  const char *v7; // r9
  int v8; // esi
  __int64 v9; // rdx
  struct IMFSensorGroupId *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  struct IMFSensorGroupId *v14; // rbx
  __int64 (__fastcall **v15)(struct IMFSensorGroupId *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v16)(struct IMFSensorGroupId *, GUID *, __int64 *); // rsi
  BYTE *v17; // rbx
  FSString *v18; // rax
  const char *String; // rax
  __int64 v20; // r15
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, unsigned int *); // rdi
  int v23; // eax
  __int64 v24; // rdx
  int v25; // eax
  int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // edi
  __int64 v29; // rdx
  void **unique; // rax
  PBYTE v31; // rbx
  struct IMFSensorGroup *v32; // rcx
  __int64 v33; // rdx
  unsigned int v35[2]; // [rsp+30h] [rbp-39h] BYREF
  PBYTE PropertyBuffer; // [rsp+38h] [rbp-31h] BYREF
  __int64 v37; // [rsp+40h] [rbp-29h] BYREF
  struct IMFSensorGroup *v38; // [rsp+48h] [rbp-21h] BYREF
  struct IMFSensorGroupId *v39; // [rsp+50h] [rbp-19h] BYREF
  struct IFSConfiguration *v40; // [rsp+58h] [rbp-11h] BYREF
  __int64 v41; // [rsp+60h] [rbp-9h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-1h] BYREF
  __int64 v43; // [rsp+78h] [rbp+Fh]

  v35[0] = 0;
  v4 = a2;
  v39 = 0;
  v37 = 0;
  v6 = 0;
  v38 = 0;
  v40 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    LODWORD(v7) = (_DWORD)pszDeviceInterface;
    if ( !pszDeviceInterface )
      v7 = L"<nullptr>";
    WPP_SF_Si(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      193,
      (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
      (_DWORD)v7,
      a2);
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    if ( g_wppLevels )
    {
      v9 = 194;
LABEL_78:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v8);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  *a3 = 0;
  if ( !pszDeviceInterface )
  {
    v8 = -2147024809;
    if ( g_wppLevels )
    {
      v9 = 195;
      goto LABEL_78;
    }
LABEL_79:
    if ( !byte_18008D62D )
      goto LABEL_89;
    v33 = 211;
    goto LABEL_88;
  }
  v10 = v39;
  v39 = 0;
  if ( v10 )
    (*(void (__fastcall **)(struct IMFSensorGroupId *))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = SensorGroupId::CreateSensorGroupId(&v39);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v12 = 196;
LABEL_16:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v11);
    goto LABEL_79;
  }
  v13 = v37;
  v14 = v39;
  v15 = *(__int64 (__fastcall ***)(struct IMFSensorGroupId *, GUID *, __int64 *))v39;
  v37 = 0;
  v16 = *v15;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  v11 = v16(v14, &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7, &v37);
  v8 = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_79;
    v12 = 197;
    goto LABEL_16;
  }
  if ( !IsSensorGroupName(pszDeviceInterface)
    && !SGUtils_IsCurrentProcessWinBioSrvc()
    && !SGUtils_IsCurrentProcessBioEnrollment() )
  {
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v40);
    if ( (int)FSLoadAllAppsDeviceConfiguration(pszDeviceInterface, &v40) >= 0 && (v4 & 4) == 0 )
    {
      v17 = (BYTE *)MFGetAttributeUINT64(v40, MF_FRAMESERVER_MANAGED_CAMERA_MODE);
      PropertyBuffer = v17;
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v18 = ManagedModeTrace::ManagedModeTrace(
                (ManagedModeTrace *)pvar,
                (const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *)&PropertyBuffer);
        String = FSString::GetString(v18);
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 27), 198, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, String);
        v17 = PropertyBuffer;
        v6 = 1;
      }
      if ( (v6 & 1) != 0 )
        FSString::~FSString((FSString *)pvar);
      if ( v17 )
      {
        *(_QWORD *)v35 = 0;
        if ( ((unsigned __int8)v17 & 1) != 0 || (v20 = 0, ((unsigned __int8)v17 & 4) != 0) )
          v20 = 1;
        v21 = v37;
        v22 = *(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 96LL);
        wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(v35);
        v23 = v22(v21, v35);
        v8 = v23;
        if ( v23 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_39:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v35);
            goto LABEL_79;
          }
          v24 = 199;
LABEL_38:
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v24, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v23);
          goto LABEL_39;
        }
        v23 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, BYTE *))(**(_QWORD **)v35 + 176LL))(
                *(_QWORD *)v35,
                MF_FRAMESERVER_MANAGED_CAMERA_MODE,
                v17);
        v8 = v23;
        if ( v23 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_39;
          v24 = 200;
          goto LABEL_38;
        }
        if ( v20 )
        {
          v43 = 0;
          *(_OWORD *)pvar = 0;
          if ( (*(int (__fastcall **)(struct IFSConfiguration *, __int64 *, PROPVARIANT *))(*(_QWORD *)v40 + 24LL))(
                 v40,
                 MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
                 pvar) >= 0 )
          {
            v25 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, PROPVARIANT *))(**(_QWORD **)v35 + 144LL))(
                    *(_QWORD *)v35,
                    MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA,
                    pvar);
            v8 = v25;
            if ( v25 < 0 )
            {
              if ( g_wppLevels )
                WPP_SF_qD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  201,
                  &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
                  0,
                  v25);
              PropVariantClear(pvar);
              goto LABEL_39;
            }
          }
          PropVariantClear(pvar);
        }
        v4 = 2 * v20;
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v35);
      }
    }
  }
  if ( (v4 & 1) != 0 )
  {
    LODWORD(v43) = 22;
    v35[0] = 0;
    *(_OWORD *)pvar = SensorGroupFMTGUID;
    PropertyBuffer = 0;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        202,
        (unsigned int)&WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        0,
        (__int64)pszDeviceInterface);
    v26 = FSGetDeviceInterfaceProperty(pszDeviceInterface, (DEVPROPKEY *)pvar, 0, 0, v35);
    v8 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_62:
        wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&PropertyBuffer);
        goto LABEL_79;
      }
      v27 = 203;
LABEL_57:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v27, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v26);
      goto LABEL_62;
    }
    v28 = v35[0];
    if ( !v35[0] )
    {
      v8 = -1072875854;
      if ( !g_wppLevels )
        goto LABEL_62;
      v29 = 204;
LABEL_61:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v8);
      goto LABEL_62;
    }
    unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v41, v35[0]);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(
      (void **)&PropertyBuffer,
      unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v41);
    v31 = PropertyBuffer;
    if ( !PropertyBuffer )
    {
      v8 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_62;
      v29 = 205;
      goto LABEL_61;
    }
    v26 = FSGetDeviceInterfaceProperty(pszDeviceInterface, (DEVPROPKEY *)pvar, PropertyBuffer, v28, v35);
    v8 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_62;
      v27 = 206;
      goto LABEL_57;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, PBYTE, _QWORD))(*(_QWORD *)v37 + 248LL))(v37, v31, v35[0]);
    v8 = v26;
    if ( v26 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_62;
      v27 = 207;
      goto LABEL_57;
    }
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&PropertyBuffer);
  }
  else
  {
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        208,
        &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
        pszDeviceInterface);
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCWSTR))(*(_QWORD *)v37 + 208LL))(v37, 0, pszDeviceInterface);
    v8 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_79;
      v12 = 209;
      goto LABEL_16;
    }
  }
  v32 = v38;
  v38 = 0;
  if ( v32 )
    (*(void (__fastcall **)(struct IMFSensorGroup *))(*(_QWORD *)v32 + 16LL))(v32);
  v8 = SensorGroup::LoadSensorGroup(v39, &v38);
  if ( v8 < 0 )
  {
    if ( g_wppLevels )
    {
      v9 = 210;
      goto LABEL_78;
    }
    goto LABEL_79;
  }
  *a3 = v38;
  v38 = 0;
  if ( (unsigned __int8)byte_18008D62D < 8u )
    goto LABEL_89;
  v33 = 212;
LABEL_88:
  WPP_SF_d(
    *((_QWORD *)WPP_GLOBAL_Control + 27),
    v33,
    &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids,
    (unsigned int)v8);
LABEL_89:
  if ( v40 )
    (*(void (__fastcall **)(struct IFSConfiguration *))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v38 )
    (*(void (__fastcall **)(struct IMFSensorGroup *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v39 )
    (*(void (__fastcall **)(struct IMFSensorGroupId *))(*(_QWORD *)v39 + 16LL))(v39);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180012284  mov     [rsp-8+arg_8], rbx
0x180012289  push    rbp
0x18001228a  push    rsi
0x18001228b  push    rdi
0x18001228c  push    r12
0x18001228e  push    r13
0x180012290  push    r14
0x180012292  push    r15
0x180012294  lea     rbp, [rsp-27h]
0x180012299  sub     rsp, 90h
0x1800122a0  mov     rax, cs:__security_cookie
0x1800122a7  xor     rax, rsp
0x1800122aa  mov     [rbp+57h+var_40], rax
0x1800122ae  xor     r13d, r13d
0x1800122b1  mov     r12, r8
0x1800122b4  mov     [rbp+57h+var_90], r13d
0x1800122b8  mov     rdi, rdx
0x1800122bb  mov     [rbp+57h+var_70], r13
0x1800122bf  mov     r14, rcx
0x1800122c2  mov     [rbp+57h+var_80], r13
0x1800122c6  mov     r15d, r13d
0x1800122c9  mov     [rbp+57h+var_78], r13
0x1800122cd  mov     [rbp+57h+var_68], r13
0x1800122d1  cmp     cs:byte_18008D62D, 8
0x1800122d8  jb      short loc_18001230F
0x1800122da  mov     r9, rcx
0x1800122dd  mov     [rsp+0C0h+var_A0], rdi
0x1800122e2  test    rcx, rcx
0x1800122e5  lea     rax, aNullptr; "<nullptr>"
0x1800122ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122f3  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x1800122fa  cmovz   r9, rax
0x1800122fe  mov     edx, 0C1h
0x180012303  mov     rcx, [rcx+0D8h]
0x18001230a  call    WPP_SF_Si
0x18001230f  test    r12, r12
0x180012312  jnz     short loc_180012330
0x180012314  mov     esi, 80004003h
0x180012319  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012320  jb      loc_1800127EC
0x180012326  mov     edx, 0C2h
0x18001232b  jmp     loc_1800127CE
0x180012330  mov     [r12], r13
0x180012334  test    r14, r14
0x180012337  jnz     short loc_180012355
0x180012339  mov     esi, 80070057h
0x18001233e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012345  jb      loc_1800127EC
0x18001234b  mov     edx, 0C3h
0x180012350  jmp     loc_1800127CE
0x180012355  mov     rcx, [rbp+57h+var_70]
0x180012359  mov     [rbp+57h+var_70], r13
0x18001235d  test    rcx, rcx
0x180012360  jz      short loc_18001236E
0x180012362  mov     rax, [rcx]
0x180012365  mov     rax, [rax+10h]
0x180012369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001236e  lea     rcx, [rbp+57h+var_70]; struct IMFSensorGroupId **
0x180012372  call    ?CreateSensorGroupId@SensorGroupId@@SAJPEAPEAUIMFSensorGroupId@@@Z; SensorGroupId::CreateSensorGroupId(IMFSensorGroupId * *)
0x180012377  mov     esi, eax
0x180012379  test    eax, eax
0x18001237b  jns     short loc_180012398
0x18001237d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012384  jb      loc_1800127EC
0x18001238a  mov     edx, 0C4h
0x18001238f  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180012393  jmp     loc_1800127D2
0x180012398  mov     rcx, [rbp+57h+var_80]
0x18001239c  mov     rbx, [rbp+57h+var_70]
0x1800123a0  mov     rax, [rbx]
0x1800123a3  mov     [rbp+57h+var_80], r13
0x1800123a7  mov     rsi, [rax]
0x1800123aa  test    rcx, rcx
0x1800123ad  jz      short loc_1800123BB
0x1800123af  mov     rdx, [rcx]
0x1800123b2  mov     rax, [rdx+10h]
0x1800123b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123bb  lea     r8, [rbp+57h+var_80]
0x1800123bf  mov     rcx, rbx
0x1800123c2  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x1800123c9  mov     rax, rsi
0x1800123cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123d1  mov     esi, eax
0x1800123d3  test    eax, eax
0x1800123d5  jns     short loc_1800123EB
0x1800123d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800123de  jb      loc_1800127EC
0x1800123e4  mov     edx, 0C5h
0x1800123e9  jmp     short loc_18001238F
0x1800123eb  mov     rcx, r14; pszDeviceInterface
0x1800123ee  call    ?IsSensorGroupName@@YA_NPEBG@Z; IsSensorGroupName(ushort const *)
0x1800123f3  test    al, al
0x1800123f5  jnz     loc_18001260D
0x1800123fb  call    ?SGUtils_IsCurrentProcessWinBioSrvc@@YA_NXZ; SGUtils_IsCurrentProcessWinBioSrvc(void)
0x180012400  test    al, al
0x180012402  jnz     loc_18001260D
0x180012408  call    ?SGUtils_IsCurrentProcessBioEnrollment@@YA_NXZ; SGUtils_IsCurrentProcessBioEnrollment(void)
0x18001240d  test    al, al
0x18001240f  jnz     loc_18001260D
0x180012415  lea     rcx, [rbp+57h+var_68]
0x180012419  call    ?reset@?$com_ptr_t@UIRelativePanelDirectionTracker@System@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(void)
0x18001241e  lea     rdx, [rbp+57h+var_68]; struct IFSConfiguration **
0x180012422  mov     rcx, r14; pszDeviceInterface
0x180012425  call    FSLoadAllAppsDeviceConfiguration
0x18001242a  test    eax, eax
0x18001242c  js      loc_18001260D
0x180012432  test    dil, 4
0x180012436  jnz     loc_18001260D
0x18001243c  mov     rcx, [rbp+57h+var_68]
0x180012440  lea     rdx, MF_FRAMESERVER_MANAGED_CAMERA_MODE
0x180012447  call    MFGetAttributeUINT64
0x18001244c  mov     rbx, rax
0x18001244f  mov     [rbp+57h+PropertyBuffer], rax
0x180012453  cmp     cs:byte_18008D62D, 8
0x18001245a  jb      short loc_18001249D
0x18001245c  lea     rdx, [rbp+57h+PropertyBuffer]; union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *
0x180012460  lea     rcx, [rbp+57h+pvar]; this
0x180012464  call    ??0ManagedModeTrace@@QEAA@AEBT__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010@@@Z; ManagedModeTrace::ManagedModeTrace(__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 const &)
0x180012469  mov     rcx, rax; this
0x18001246c  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180012471  mov     rcx, cs:WPP_GLOBAL_Control
0x180012478  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18001247f  mov     edx, 0C6h
0x180012484  mov     r9, rax
0x180012487  mov     rcx, [rcx+0D8h]
0x18001248e  call    WPP_SF_s
0x180012493  mov     rbx, [rbp+57h+PropertyBuffer]
0x180012497  mov     r15d, 1
0x18001249d  test    r15b, 1
0x1800124a1  jz      short loc_1800124AC
0x1800124a3  lea     rcx, [rbp+57h+pvar]; this
0x1800124a7  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800124ac  test    rbx, rbx
0x1800124af  jz      loc_18001260D
0x1800124b5  mov     qword ptr [rbp+57h+var_90], r13
0x1800124b9  test    bl, 1
0x1800124bc  jnz     short loc_1800124C6
0x1800124be  mov     r15, r13
0x1800124c1  test    bl, 4
0x1800124c4  jz      short loc_1800124CC
0x1800124c6  mov     r15d, 1
0x1800124cc  mov     rsi, [rbp+57h+var_80]
0x1800124d0  lea     rcx, [rbp+57h+var_90]
0x1800124d4  mov     rax, [rsi]
0x1800124d7  mov     rdi, [rax+60h]
0x1800124db  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x1800124e0  lea     rdx, [rbp+57h+var_90]
0x1800124e4  mov     rcx, rsi
0x1800124e7  mov     rax, rdi
0x1800124ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124ef  mov     esi, eax
0x1800124f1  test    eax, eax
0x1800124f3  jns     short loc_18001252F
0x1800124f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800124fc  jb      short loc_180012521
0x1800124fe  mov     edx, 0C7h
0x180012503  mov     rcx, cs:WPP_GLOBAL_Control
0x18001250a  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180012511  xor     r9d, r9d
0x180012514  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180012518  mov     rcx, [rcx+10h]
0x18001251c  call    WPP_SF_qD
0x180012521  lea     rcx, [rbp+57h+var_90]
0x180012525  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001252a  jmp     loc_1800127EC
0x18001252f  mov     rcx, qword ptr [rbp+57h+var_90]
0x180012533  lea     rdx, MF_FRAMESERVER_MANAGED_CAMERA_MODE
0x18001253a  mov     r8, rbx
0x18001253d  mov     rax, [rcx]
0x180012540  mov     rax, [rax+0B0h]
0x180012547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001254c  mov     esi, eax
0x18001254e  test    eax, eax
0x180012550  jns     short loc_180012562
0x180012552  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012559  jb      short loc_180012521
0x18001255b  mov     edx, 0C8h
0x180012560  jmp     short loc_180012503
0x180012562  test    r15, r15
0x180012565  jz      loc_180012600
0x18001256b  mov     rcx, [rbp+57h+var_68]
0x18001256f  lea     r8, [rbp+57h+pvar]
0x180012573  xor     eax, eax
0x180012575  lea     rdx, MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA
0x18001257c  mov     [rbp+57h+var_48], rax
0x180012580  xorps   xmm0, xmm0
0x180012583  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180012587  mov     rax, [rcx]
0x18001258a  mov     rax, [rax+18h]
0x18001258e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012593  test    eax, eax
0x180012595  js      short loc_1800125F6
0x180012597  mov     rcx, qword ptr [rbp+57h+var_90]
0x18001259b  lea     r8, [rbp+57h+pvar]
0x18001259f  lea     rdx, MF_FRAMESERVER_MANAGED_CAMERA_SELECTED_MEDIA
0x1800125a6  mov     rax, [rcx]
0x1800125a9  mov     rax, [rax+90h]
0x1800125b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125b5  mov     esi, eax
0x1800125b7  test    eax, eax
0x1800125b9  jns     short loc_1800125F6
0x1800125bb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800125c2  jb      short loc_1800125E7
0x1800125c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800125cb  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x1800125d2  mov     edx, 0C9h
0x1800125d7  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1800125db  xor     r9d, r9d
0x1800125de  mov     rcx, [rcx+10h]
0x1800125e2  call    WPP_SF_qD
0x1800125e7  lea     rcx, [rbp+57h+pvar]; pvar
0x1800125eb  call    cs:__imp_PropVariantClear
0x1800125f1  jmp     loc_180012521
0x1800125f6  lea     rcx, [rbp+57h+pvar]; pvar
0x1800125fa  call    cs:__imp_PropVariantClear
0x180012600  lea     rcx, [rbp+57h+var_90]
0x180012604  lea     rdi, [r15+r15]
0x180012608  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001260d  test    dil, 1
0x180012611  jz      loc_180012800
0x180012617  movups  xmm0, cs:SensorGroupFMTGUID
0x18001261e  mov     dword ptr [rbp+57h+var_48], 16h
0x180012625  mov     [rbp+57h+var_90], r13d
0x180012629  movdqu  xmmword ptr [rbp+57h+pvar], xmm0
0x18001262e  mov     [rbp+57h+PropertyBuffer], r13
0x180012632  cmp     cs:byte_18008D62D, 8
0x180012639  jb      short loc_180012662
0x18001263b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012642  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x180012649  mov     edx, 0CAh
0x18001264e  mov     [rsp+0C0h+var_A0], r14
0x180012653  xor     r9d, r9d
0x180012656  mov     rcx, [rcx+0D8h]
0x18001265d  call    WPP_SF_dS
0x180012662  lea     rax, [rbp+57h+var_90]
0x180012666  xor     r9d, r9d; unsigned int
0x180012669  xor     r8d, r8d; PropertyBuffer
0x18001266c  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x180012671  lea     rdx, [rbp+57h+pvar]; PropertyKey
0x180012675  mov     rcx, r14; pszDeviceInterface
0x180012678  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18001267d  mov     esi, eax
0x18001267f  test    eax, eax
0x180012681  jns     short loc_180012697
0x180012683  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001268a  jb      short loc_1800126CF
0x18001268c  mov     edx, 0CBh
0x180012691  mov     dword ptr [rsp+0C0h+var_A0], eax
0x180012695  jmp     short loc_1800126B5
0x180012697  mov     edi, [rbp+57h+var_90]
0x18001269a  test    edi, edi
0x18001269c  jnz     short loc_1800126DD
0x18001269e  mov     esi, 0C00D36B2h
0x1800126a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800126aa  jb      short loc_1800126CF
0x1800126ac  mov     edx, 0CCh
0x1800126b1  mov     dword ptr [rsp+0C0h+var_A0], esi
0x1800126b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800126bc  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x1800126c3  xor     r9d, r9d
0x1800126c6  mov     rcx, [rcx+10h]
0x1800126ca  call    WPP_SF_qD
0x1800126cf  lea     rcx, [rbp+57h+PropertyBuffer]
0x1800126d3  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800126d8  jmp     loc_1800127EC
0x1800126dd  mov     rdx, rdi
0x1800126e0  lea     rcx, [rbp+57h+var_60]
0x1800126e4  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x1800126e9  mov     rdx, rax
0x1800126ec  lea     rcx, [rbp+57h+PropertyBuffer]
0x1800126f0  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x1800126f5  lea     rcx, [rbp+57h+var_60]
0x1800126f9  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x1800126fe  mov     rbx, [rbp+57h+PropertyBuffer]
0x180012702  test    rbx, rbx
0x180012705  jnz     short loc_18001271C
0x180012707  mov     esi, 8007000Eh
0x18001270c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012713  jb      short loc_1800126CF
0x180012715  mov     edx, 0CDh
0x18001271a  jmp     short loc_1800126B1
0x18001271c  lea     rax, [rbp+57h+var_90]
0x180012720  mov     r9d, edi; unsigned int
0x180012723  mov     r8, rbx; PropertyBuffer
0x180012726  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x18001272b  lea     rdx, [rbp+57h+pvar]; PropertyKey
0x18001272f  mov     rcx, r14; pszDeviceInterface
0x180012732  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180012737  mov     esi, eax
0x180012739  test    eax, eax
0x18001273b  jns     short loc_180012750
0x18001273d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012744  jb      short loc_1800126CF
0x180012746  mov     edx, 0CEh
0x18001274b  jmp     loc_180012691
0x180012750  mov     rcx, [rbp+57h+var_80]
0x180012754  mov     rdx, rbx
0x180012757  mov     r8d, [rbp+57h+var_90]
0x18001275b  mov     rax, [rcx]
0x18001275e  mov     rax, [rax+0F8h]
  ... truncated ...
```
