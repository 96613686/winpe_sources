# FSSourceInfo::ConfigureProfile_MEPProfileExEnabled(IMFAttributes *,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *)

- ea: `0x180082e38`
- end: `0x180083396`
- name: `?ConfigureProfile_MEPProfileExEnabled@FSSourceInfo@@IEAAJPEAUIMFAttributes@@PEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@@Z`
- size: `1374`
- prototype: `__int64 __fastcall(FSSourceInfo *__hidden this, struct IMFAttributes *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800826f0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x180018998`
- `0x18003b884`
- `0x18004d714`
- `0x18004d748`
- `0x18006b99c`
- `0x180082e38`
- `0x180084914`
- `0x1800e2d5c`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082f57`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180083086`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082f57`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180083086`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082fab`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x1800830f1`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082fab`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x1800830f1`

## pseudocode

```c
__int64 __fastcall FSSourceInfo::ConfigureProfile_MEPProfileExEnabled(
        FSSourceInfo *this,
        struct IMFAttributes *a2,
        struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *a3)
{
  char v6; // r15
  int v7; // ebx
  int ShareMode; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, GUID *, GUID *, struct IMFSensorProfileCollectionInternal **); // rbx
  int SensorProfile; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  struct IMFSensorProfileCollectionInternal *v14; // rdi
  int (__fastcall *v15)(struct IMFSensorProfileCollectionInternal *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, struct IMFSensorProfile **); // rbx
  __int64 v16; // rdx
  struct IMFSensorProfileCollectionInternal *v17; // rdi
  int (__fastcall *v18)(struct IMFSensorProfileCollectionInternal *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, struct IMFSensorProfile **); // rbx
  int v19; // eax
  struct IMFSensorProfile *v20; // rsi
  __int64 (__fastcall *v21)(struct IMFSensorProfile *, GUID *, char *); // rdi
  struct IMFSensorProfile *v22; // rsi
  __int64 (__fastcall *v23)(struct IMFSensorProfile *, GUID *, char *); // rdi
  int v24; // eax
  __int64 v25; // rdx
  FSString *v26; // rax
  const char *String; // rax
  FSString *v28; // rax
  const char *v29; // rax
  FSString *v30; // rax
  const char *v31; // rax
  struct IMFSensorProfileCollectionInternal *v33; // [rsp+30h] [rbp-30h] BYREF
  __int64 v34; // [rsp+38h] [rbp-28h] BYREF
  _BYTE v35[32]; // [rsp+40h] [rbp-20h] BYREF
  struct IMFSensorProfile *v36; // [rsp+A0h] [rbp+40h] BYREF
  struct IMFSensorProfile *v37; // [rsp+B8h] [rbp+58h] BYREF

  v36 = 0;
  v33 = 0;
  v6 = 0;
  v37 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13));
    ShareMode = FSSourceInfo::GetShareMode(this);
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      166,
      &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      this,
      ShareMode,
      v7);
  }
  v9 = *((_QWORD *)this + 12);
  v10 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, struct IMFSensorProfileCollectionInternal **))(*(_QWORD *)v9 + 224LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v33);
  SensorProfile = v10(v9, &GUID_00000000_0000_0000_0000_000000000000, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v33);
  v12 = SensorProfile;
  if ( SensorProfile < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_41;
    v13 = 167;
    goto LABEL_6;
  }
  v14 = v33;
  v15 = *(int (__fastcall **)(struct IMFSensorProfileCollectionInternal *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, struct IMFSensorProfile **))(*(_QWORD *)v33 + 80LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v37);
  if ( v15(v14, a3, &GUID_22f765d1_8dab_4107_846d_56baf72215e7, &v37) >= 0 )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    SensorProfile = MFCloneSensorProfile(v37, &v36);
    v12 = SensorProfile;
    if ( SensorProfile < 0 )
    {
      if ( g_wppLevels )
      {
        v13 = 170;
        goto LABEL_6;
      }
LABEL_41:
      if ( byte_18010EC4D )
      {
        v25 = 182;
LABEL_57:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v25,
          &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
          this,
          v12);
        goto LABEL_58;
      }
      goto LABEL_58;
    }
    wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v37, &v36);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 171, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v33);
    SensorProfile = FSSourceInfo::InternalGetSensorProfile(this, a2, &v33);
    v12 = SensorProfile;
    if ( SensorProfile < 0 )
    {
      if ( g_wppLevels )
      {
        v13 = 172;
        goto LABEL_6;
      }
      goto LABEL_41;
    }
    v17 = v33;
    v18 = *(int (__fastcall **)(struct IMFSensorProfileCollectionInternal *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, struct IMFSensorProfile **))(*(_QWORD *)v33 + 80LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    if ( v18(v17, a3, &GUID_22f765d1_8dab_4107_846d_56baf72215e7, &v36) >= 0 )
    {
      v34 = 0;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v34);
      v19 = MFCloneSensorProfile(v36, &v34);
      v12 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            175,
            &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
            this,
            v19);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
        goto LABEL_41;
      }
      wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v36, &v34);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 176, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v34);
    }
    else
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
      SensorProfile = MFCreateSensorProfileWithFlags(a3, 0x20000000, &v36);
      v12 = SensorProfile;
      if ( SensorProfile < 0 )
      {
        if ( g_wppLevels )
        {
          v13 = 173;
          goto LABEL_6;
        }
        goto LABEL_41;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v16 = 174;
        goto LABEL_27;
      }
    }
  }
  else
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    SensorProfile = MFCreateSensorProfileWithFlags(a3, 0x40000000, &v36);
    v12 = SensorProfile;
    if ( SensorProfile < 0 )
    {
      if ( g_wppLevels )
      {
        v13 = 168;
LABEL_6:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
          this,
          SensorProfile);
        goto LABEL_41;
      }
      goto LABEL_41;
    }
    wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v37, &v36);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v16 = 169;
LABEL_27:
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), v16, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
    }
  }
  v20 = v36;
  v21 = **(__int64 (__fastcall ***)(struct IMFSensorProfile *, GUID *, char *))v36;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 248);
  SensorProfile = v21(v20, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, (char *)this + 248);
  v12 = SensorProfile;
  if ( SensorProfile < 0 )
  {
    if ( g_wppLevels )
    {
      v13 = 177;
      goto LABEL_6;
    }
    goto LABEL_41;
  }
  v22 = v37;
  v23 = **(__int64 (__fastcall ***)(struct IMFSensorProfile *, GUID *, char *))v37;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 256);
  v24 = v23(v22, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, (char *)this + 256);
  v12 = v24;
  if ( v24 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this, v24);
    goto LABEL_41;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v26 = CameraProfileTracer::CameraProfileTracer((CameraProfileTracer *)v35, v36);
    String = FSString::GetString(v26);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      179,
      (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      (_DWORD)this,
      (__int64)String);
    v6 = 1;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    FSString::~FSString((FSString *)v35);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v6 |= 2u;
    v28 = CameraProfileTracer::CameraProfileTracer((CameraProfileTracer *)v35, v37);
    v29 = FSString::GetString(v28);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      180,
      (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      (_DWORD)this,
      (__int64)v29);
  }
  if ( (v6 & 2) != 0 )
  {
    v6 &= ~2u;
    FSString::~FSString((FSString *)v35);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v6 |= 4u;
    v30 = CameraProfileTracer::CameraProfileTracer((CameraProfileTracer *)v35, *((struct IMFSensorProfile **)this + 33));
    v31 = FSString::GetString(v30);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      181,
      (unsigned int)&WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      (_DWORD)this,
      (__int64)v31);
  }
  if ( (v6 & 4) != 0 )
    FSString::~FSString((FSString *)v35);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v25 = 183;
    goto LABEL_57;
  }
LABEL_58:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v37);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v33);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
  return v12;
}

```

## disassembly

```asm
0x180082e38  mov     [rsp-38h+arg_8], rbx
0x180082e3d  push    rbp
0x180082e3e  push    rsi
0x180082e3f  push    rdi
0x180082e40  push    r12
0x180082e42  push    r13
0x180082e44  push    r14
0x180082e46  push    r15
0x180082e48  mov     rbp, rsp
0x180082e4b  sub     rsp, 60h
0x180082e4f  xor     eax, eax
0x180082e51  mov     rsi, r8
0x180082e54  mov     dword ptr [rbp+arg_0], eax
0x180082e57  mov     r12, rdx
0x180082e5a  mov     [rbp+arg_0], rax
0x180082e5e  mov     r14, rcx
0x180082e61  mov     [rbp+var_30], rax
0x180082e65  mov     r15d, eax
0x180082e68  mov     [rbp+arg_18], rax
0x180082e6c  cmp     cs:byte_18010EC4D, 8
0x180082e73  lea     r13, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x180082e7a  jb      short loc_180082EBC
0x180082e7c  mov     rcx, [rcx+68h]
0x180082e80  mov     rax, [rcx]
0x180082e83  mov     rax, [rax+18h]
0x180082e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082e8c  mov     rcx, r14
0x180082e8f  mov     ebx, eax
0x180082e91  call    ?GetShareMode@FSSourceInfo@@QEBA?AW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@XZ; FSSourceInfo::GetShareMode(void)
0x180082e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180082e9d  mov     edx, 0A6h
0x180082ea2  mov     [rsp+60h+var_38], ebx
0x180082ea6  mov     r9, r14
0x180082ea9  mov     r8, r13
0x180082eac  mov     dword ptr [rsp+60h+var_40], eax
0x180082eb0  mov     rcx, [rcx+0D8h]
0x180082eb7  call    WPP_SF_qDD
0x180082ebc  mov     rdi, [r14+60h]
0x180082ec0  lea     rcx, [rbp+var_30]
0x180082ec4  mov     rax, [rdi]
0x180082ec7  mov     rbx, [rax+0E0h]
0x180082ece  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082ed3  lea     r9, [rbp+var_30]
0x180082ed7  mov     rcx, rdi
0x180082eda  lea     r8, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180082ee1  mov     rax, rbx
0x180082ee4  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180082eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ef0  mov     ebx, eax
0x180082ef2  test    eax, eax
0x180082ef4  jns     short loc_180082F11
0x180082ef6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082efd  jb      loc_180083216
0x180082f03  mov     edx, 0A7h
0x180082f08  mov     dword ptr [rsp+60h+var_40], eax
0x180082f0c  jmp     loc_180083200
0x180082f11  mov     rdi, [rbp+var_30]
0x180082f15  lea     rcx, [rbp+arg_18]
0x180082f19  mov     rax, [rdi]
0x180082f1c  mov     rbx, [rax+50h]
0x180082f20  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082f25  lea     r9, [rbp+arg_18]
0x180082f29  mov     rdx, rsi
0x180082f2c  lea     r8, _GUID_22f765d1_8dab_4107_846d_56baf72215e7
0x180082f33  mov     rcx, rdi
0x180082f36  mov     rax, rbx
0x180082f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082f3e  lea     rcx, [rbp+arg_0]
0x180082f42  test    eax, eax
0x180082f44  jns     short loc_180082F9E
0x180082f46  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082f4b  lea     r8, [rbp+arg_0]
0x180082f4f  mov     edx, 40000000h
0x180082f54  mov     rcx, rsi
0x180082f57  call    cs:__imp_MFCreateSensorProfileWithFlags
0x180082f5d  mov     ebx, eax
0x180082f5f  test    eax, eax
0x180082f61  jns     short loc_180082F77
0x180082f63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082f6a  jb      loc_180083216
0x180082f70  mov     edx, 0A8h
0x180082f75  jmp     short loc_180082F08
0x180082f77  lea     rdx, [rbp+arg_0]
0x180082f7b  lea     rcx, [rbp+arg_18]
0x180082f7f  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x180082f84  mov     r12b, 8
0x180082f87  cmp     cs:byte_18010EC4D, r12b
0x180082f8e  jb      loc_180083173
0x180082f94  mov     edx, 0A9h
0x180082f99  jmp     loc_1800830BE
0x180082f9e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082fa3  mov     rcx, [rbp+arg_18]
0x180082fa7  lea     rdx, [rbp+arg_0]
0x180082fab  call    cs:__imp_MFCloneSensorProfile
0x180082fb1  mov     ebx, eax
0x180082fb3  test    eax, eax
0x180082fb5  jns     short loc_180082FCE
0x180082fb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082fbe  jb      loc_180083216
0x180082fc4  mov     edx, 0AAh
0x180082fc9  jmp     loc_180082F08
0x180082fce  lea     rdx, [rbp+arg_0]
0x180082fd2  lea     rcx, [rbp+arg_18]
0x180082fd6  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x180082fdb  cmp     cs:byte_18010EC4D, 8
0x180082fe2  jb      short loc_180083002
0x180082fe4  mov     rcx, cs:WPP_GLOBAL_Control
0x180082feb  mov     edx, 0ABh
0x180082ff0  mov     r9, r14
0x180082ff3  mov     r8, r13
0x180082ff6  mov     rcx, [rcx+0D8h]
0x180082ffd  call    WPP_SF_q
0x180083002  lea     rcx, [rbp+arg_0]
0x180083006  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008300b  lea     rcx, [rbp+var_30]
0x18008300f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180083014  lea     r8, [rbp+var_30]; struct IMFSensorProfileCollectionInternal **
0x180083018  mov     rdx, r12; struct IMFAttributes *
0x18008301b  mov     rcx, r14; this
0x18008301e  call    ?InternalGetSensorProfile@FSSourceInfo@@IEAAJPEAUIMFAttributes@@PEAPEAUIMFSensorProfileCollectionInternal@@@Z; FSSourceInfo::InternalGetSensorProfile(IMFAttributes *,IMFSensorProfileCollectionInternal * *)
0x180083023  mov     ebx, eax
0x180083025  test    eax, eax
0x180083027  jns     short loc_180083040
0x180083029  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083030  jb      loc_180083216
0x180083036  mov     edx, 0ACh
0x18008303b  jmp     loc_180082F08
0x180083040  mov     rdi, [rbp+var_30]
0x180083044  lea     rcx, [rbp+arg_0]
0x180083048  mov     rax, [rdi]
0x18008304b  mov     rbx, [rax+50h]
0x18008304f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180083054  lea     r9, [rbp+arg_0]
0x180083058  mov     rdx, rsi
0x18008305b  lea     r8, _GUID_22f765d1_8dab_4107_846d_56baf72215e7
0x180083062  mov     rcx, rdi
0x180083065  mov     rax, rbx
0x180083068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008306d  test    eax, eax
0x18008306f  jns     short loc_1800830DC
0x180083071  lea     rcx, [rbp+arg_0]
0x180083075  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008307a  lea     r8, [rbp+arg_0]
0x18008307e  mov     edx, 20000000h
0x180083083  mov     rcx, rsi
0x180083086  call    cs:__imp_MFCreateSensorProfileWithFlags
0x18008308c  mov     ebx, eax
0x18008308e  test    eax, eax
0x180083090  jns     short loc_1800830A9
0x180083092  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083099  jb      loc_180083216
0x18008309f  mov     edx, 0ADh
0x1800830a4  jmp     loc_180082F08
0x1800830a9  mov     r12b, 8
0x1800830ac  cmp     cs:byte_18010EC4D, r12b
0x1800830b3  jb      loc_180083173
0x1800830b9  mov     edx, 0AEh
0x1800830be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800830c5  mov     r9, r14
0x1800830c8  mov     r8, r13
0x1800830cb  mov     rcx, [rcx+0D8h]
0x1800830d2  call    WPP_SF_q
0x1800830d7  jmp     loc_180083173
0x1800830dc  lea     rcx, [rbp+var_28]
0x1800830e0  mov     [rbp+var_28], r15
0x1800830e4  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800830e9  mov     rcx, [rbp+arg_0]
0x1800830ed  lea     rdx, [rbp+var_28]
0x1800830f1  call    cs:__imp_MFCloneSensorProfile
0x1800830f7  mov     ebx, eax
0x1800830f9  test    eax, eax
0x1800830fb  jns     short loc_180083133
0x1800830fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180083104  jb      short loc_180083125
0x180083106  mov     rcx, cs:WPP_GLOBAL_Control
0x18008310d  mov     edx, 0AFh
0x180083112  mov     r9, r14
0x180083115  mov     dword ptr [rsp+60h+var_40], eax
0x180083119  mov     r8, r13
0x18008311c  mov     rcx, [rcx+10h]
0x180083120  call    WPP_SF_qD
0x180083125  lea     rcx, [rbp+var_28]; void *
0x180083129  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18008312e  jmp     loc_180083216
0x180083133  lea     rdx, [rbp+var_28]
0x180083137  lea     rcx, [rbp+arg_0]
0x18008313b  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x180083140  mov     r12b, 8
0x180083143  cmp     cs:byte_18010EC4D, r12b
0x18008314a  jb      short loc_18008316A
0x18008314c  mov     rcx, cs:WPP_GLOBAL_Control
0x180083153  mov     edx, 0B0h
0x180083158  mov     r9, r14
0x18008315b  mov     r8, r13
0x18008315e  mov     rcx, [rcx+0D8h]
0x180083165  call    WPP_SF_q
0x18008316a  lea     rcx, [rbp+var_28]; void *
0x18008316e  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180083173  mov     rsi, [rbp+arg_0]
0x180083177  lea     rbx, [r14+0F8h]
0x18008317e  mov     rcx, rbx
0x180083181  mov     rax, [rsi]
0x180083184  mov     rdi, [rax]
0x180083187  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008318c  mov     r8, rbx
0x18008318f  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x180083196  mov     rcx, rsi
0x180083199  mov     rax, rdi
0x18008319c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800831a1  mov     ebx, eax
0x1800831a3  test    eax, eax
0x1800831a5  jns     short loc_1800831BA
0x1800831a7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800831ae  jb      short loc_180083216
0x1800831b0  mov     edx, 0B1h
0x1800831b5  jmp     loc_180082F08
0x1800831ba  mov     rsi, [rbp+arg_18]
0x1800831be  lea     rbx, [r14+100h]
0x1800831c5  mov     rcx, rbx
0x1800831c8  mov     rax, [rsi]
0x1800831cb  mov     rdi, [rax]
0x1800831ce  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800831d3  mov     r8, rbx
0x1800831d6  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x1800831dd  mov     rcx, rsi
0x1800831e0  mov     rax, rdi
0x1800831e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800831e8  mov     ebx, eax
0x1800831ea  test    eax, eax
0x1800831ec  jns     short loc_18008322D
0x1800831ee  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800831f5  jb      short loc_180083216
0x1800831f7  mov     edx, 0B2h
0x1800831fc  mov     dword ptr [rsp+60h+var_40], eax
0x180083200  mov     rcx, cs:WPP_GLOBAL_Control
0x180083207  mov     r9, r14
0x18008320a  mov     r8, r13
0x18008320d  mov     rcx, [rcx+10h]
0x180083211  call    WPP_SF_qD
0x180083216  cmp     cs:byte_18010EC4D, 1
0x18008321d  jb      loc_180083361
0x180083223  mov     edx, 0B6h
0x180083228  jmp     loc_180083344
0x18008322d  cmp     cs:byte_18010EC4D, r12b
0x180083234  jb      short loc_180083274
0x180083236  mov     rdx, [rbp+arg_0]; struct IMFSensorProfile *
0x18008323a  lea     rcx, [rbp+var_20]; this
0x18008323e  call    ??0CameraProfileTracer@@QEAA@PEAUIMFSensorProfile@@@Z; CameraProfileTracer::CameraProfileTracer(IMFSensorProfile *)
0x180083243  mov     rcx, rax; this
0x180083246  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18008324b  mov     rcx, cs:WPP_GLOBAL_Control
0x180083252  mov     edx, 0B3h
0x180083257  mov     r9, r14
0x18008325a  mov     [rsp+60h+var_40], rax
0x18008325f  mov     r8, r13
0x180083262  mov     rcx, [rcx+0D8h]
0x180083269  call    WPP_SF_qs
0x18008326e  mov     r15d, 1
0x180083274  test    r15b, 1
0x180083278  jz      short loc_180083287
0x18008327a  and     r15d, 0FFFFFFFEh
0x18008327e  lea     rcx, [rbp+var_20]; this
0x180083282  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180083287  cmp     cs:byte_18010EC4D, r12b
0x18008328e  jb      short loc_1800832CC
0x180083290  mov     rdx, [rbp+arg_18]; struct IMFSensorProfile *
0x180083294  lea     rcx, [rbp+var_20]; this
0x180083298  or      r15d, 2
0x18008329c  call    ??0CameraProfileTracer@@QEAA@PEAUIMFSensorProfile@@@Z; CameraProfileTracer::CameraProfileTracer(IMFSensorProfile *)
0x1800832a1  mov     rcx, rax; this
0x1800832a4  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800832a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800832b0  mov     edx, 0B4h
0x1800832b5  mov     r9, r14
0x1800832b8  mov     [rsp+60h+var_40], rax
0x1800832bd  mov     r8, r13
0x1800832c0  mov     rcx, [rcx+0D8h]
0x1800832c7  call    WPP_SF_qs
0x1800832cc  test    r15b, 2
0x1800832d0  jz      short loc_1800832DF
0x1800832d2  and     r15d, 0FFFFFFFDh
0x1800832d6  lea     rcx, [rbp+var_20]; this
0x1800832da  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800832df  cmp     cs:byte_18010EC4D, r12b
0x1800832e6  jb      short loc_180083327
0x1800832e8  mov     rdx, [r14+108h]; struct IMFSensorProfile *
0x1800832ef  lea     rcx, [rbp+var_20]; this
0x1800832f3  or      r15d, 4
0x1800832f7  call    ??0CameraProfileTracer@@QEAA@PEAUIMFSensorProfile@@@Z; CameraProfileTracer::CameraProfileTracer(IMFSensorProfile *)
0x1800832fc  mov     rcx, rax; this
0x1800832ff  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180083304  mov     rcx, cs:WPP_GLOBAL_Control
0x18008330b  mov     edx, 0B5h
0x180083310  mov     r9, r14
0x180083313  mov     [rsp+60h+var_40], rax
0x180083318  mov     r8, r13
0x18008331b  mov     rcx, [rcx+0D8h]
0x180083322  call    WPP_SF_qs
0x180083327  test    r15b, 4
0x18008332b  jz      short loc_180083336
  ... truncated ...
```
