# FSSourceInfo::ConfigureProfile_MEPProfileExDisabled(IMFAttributes *,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *)

- ea: `0x180082790`
- end: `0x180082e30`
- name: `?ConfigureProfile_MEPProfileExDisabled@FSSourceInfo@@IEAAJPEAUIMFAttributes@@PEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@@Z`
- size: `1696`
- prototype: `__int64 __fastcall(FSSourceInfo *__hidden this, struct IMFAttributes *, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800826f0`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x1800096f4`
- `0x18000a648`
- `0x180017ab8`
- `0x18001807c`
- `0x18003b884`
- `0x18006b99c`
- `0x180082790`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x18008292a`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082bf0`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082ceb`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x18008292a`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082bf0`
- `MFSENSORGROUP!MFCreateSensorProfileWithFlags` at `0x180082ceb`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180082ac6`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180082ac6`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082992`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082c59`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082992`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180082c59`

## pseudocode

```c
__int64 __fastcall FSSourceInfo::ConfigureProfile_MEPProfileExDisabled(
        FSSourceInfo *this,
        struct IMFAttributes *a2,
        struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *a3)
{
  int v6; // ebx
  int ShareMode; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, GUID *, GUID *, __int64 *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdi
  int (__fastcall *v14)(__int64, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  _BOOL8 v18; // rdi
  HRESULT (__stdcall *GetAllocatedString)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rbx
  int (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rcx
  int (__fastcall ***v21)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v22)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v23; // rdi
  int (__fastcall *v24)(__int64, GUID *, GUID *, __int64 *); // rbx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, GUID *, GUID *, __int64 *); // rbx
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rbx
  int v29; // eax
  __int64 v30; // rdx
  __int64 (__fastcall ***v31)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v32)(_QWORD, GUID *, char *); // rdi
  __int64 (__fastcall ***v33)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v34)(_QWORD, GUID *, char *); // rdi
  __int64 v36; // [rsp+30h] [rbp-40h] BYREF
  int (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-38h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, char *); // [rsp+40h] [rbp-30h] BYREF
  __int64 v39; // [rsp+48h] [rbp-28h] BYREF
  __int64 (__fastcall ***v40)(_QWORD, GUID *, char *); // [rsp+50h] [rbp-20h] BYREF
  __int64 v41; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v42[2]; // [rsp+60h] [rbp-10h] BYREF
  int v43; // [rsp+B8h] [rbp+48h] BYREF

  v38 = 0;
  v40 = 0;
  v42[0] = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13));
    ShareMode = FSSourceInfo::GetShareMode(this);
    WPP_SF_qDD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      184,
      &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
      this,
      ShareMode,
      v6);
  }
  if ( !(unsigned int)FSSourceInfo::GetShareMode(this)
    && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 24LL))(*((_QWORD *)this + 13)) != 4 )
  {
    v8 = *((_QWORD *)this + 12);
    v36 = 0;
    v37 = 0;
    v39 = 0;
    v43 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v8 + 224LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    v10 = v9(v8, &GUID_00000000_0000_0000_0000_000000000000, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v36);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_9:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v39);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v37);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
        goto LABEL_62;
      }
      v12 = 186;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this, v10);
      goto LABEL_9;
    }
    v13 = v36;
    v14 = *(int (__fastcall **)(__int64, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v36 + 80LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v40);
    if ( v14(
           v13,
           a3,
           &GUID_22f765d1_8dab_4107_846d_56baf72215e7,
           (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v40) >= 0 )
    {
      v41 = 0;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v41);
      v15 = MFCloneSensorProfile(v40, &v41);
      v11 = v15;
      if ( v15 < 0 )
      {
        if ( g_wppLevels )
        {
          v16 = 189;
LABEL_19:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v16,
            &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
            this,
            v15);
        }
LABEL_20:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v41);
        goto LABEL_9;
      }
      wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v40, &v41);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 190, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v41);
    }
    else
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v40);
      v10 = MFCreateSensorProfileWithFlags(a3, 0x20000000, &v40);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_9;
        v12 = 187;
        goto LABEL_8;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 188, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 96LL))(*((_QWORD *)this + 21));
    v18 = v17 == 0;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        191,
        &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids,
        this,
        v17 == 0);
    if ( !a2 )
      goto LABEL_33;
    GetAllocatedString = a2->lpVtbl->GetAllocatedString;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      v42,
      0);
    if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, _QWORD *, int *))GetAllocatedString)(
           a2,
           &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
           v42,
           &v43) < 0 )
      goto LABEL_33;
    v20 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
    v37 = 0;
    if ( v20 )
      ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v20)[2])(v20);
    if ( (int)MFCreateSensorGroupWithOptions(v42[0], v18, &v37) < 0
      || (v21 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37,
          v22 = **v37,
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v39),
          v22(v21, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, &v39) < 0)
      || (v23 = v39,
          v24 = *(int (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v39 + 24LL),
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36),
          v24(v23, &GUID_00000000_0000_0000_0000_000000000000, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v36) < 0) )
    {
LABEL_33:
      v25 = *((_QWORD *)this + 12);
      v26 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, __int64 *))(*(_QWORD *)v25 + 224LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
      v10 = v26(v25, &GUID_00000000_0000_0000_0000_000000000000, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v36);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_9;
        v12 = 192;
        goto LABEL_8;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 193, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
    }
    v27 = v36;
    v28 = *(int (__fastcall **)(__int64, struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *, GUID *, __int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(*(_QWORD *)v36 + 80LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v38);
    if ( v28(
           v27,
           a3,
           &GUID_22f765d1_8dab_4107_846d_56baf72215e7,
           (__int64 (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v38) < 0 )
    {
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v38);
      v10 = MFCreateSensorProfileWithFlags(a3, 0x20000000, &v38);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_9;
        v12 = 194;
        goto LABEL_8;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 195, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
      goto LABEL_50;
    }
    v41 = 0;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v41);
    v15 = MFCloneSensorProfile(v38, &v41);
    v11 = v15;
    if ( v15 >= 0 )
    {
      wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v38, &v41);
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 197, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v41);
LABEL_50:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v39);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
      goto LABEL_55;
    }
    if ( g_wppLevels )
    {
      v16 = 196;
      goto LABEL_19;
    }
    goto LABEL_20;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v38);
  v29 = MFCreateSensorProfileWithFlags(a3, 0x40000000, &v38);
  v11 = v29;
  if ( v29 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_62;
    v30 = 185;
    goto LABEL_61;
  }
  wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(&v40, &v38);
LABEL_55:
  v31 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v38;
  v32 = **v38;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 248);
  v29 = v32(v31, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, (char *)this + 248);
  v11 = v29;
  if ( v29 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_62;
    v30 = 198;
    goto LABEL_61;
  }
  v33 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v40;
  v34 = **v40;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)this + 256);
  v29 = v34(v33, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, (char *)this + 256);
  v11 = v29;
  if ( v29 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_62;
    v30 = 199;
LABEL_61:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v30, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this, v29);
LABEL_62:
    if ( byte_18010EC4D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 200, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this, v11);
    goto LABEL_66;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 201, &WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids, this, v29);
LABEL_66:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v42);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v40);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v38);
  return v11;
}

```

## disassembly

```asm
0x180082790  mov     [rsp-28h+arg_0], rbx
0x180082795  mov     [rsp-28h+arg_8], rsi
0x18008279a  push    rbp
0x18008279b  push    rdi
0x18008279c  push    r13
0x18008279e  push    r14
0x1800827a0  push    r15
0x1800827a2  mov     rbp, rsp
0x1800827a5  sub     rsp, 70h
0x1800827a9  mov     rsi, r8
0x1800827ac  mov     [rbp+var_30], 0
0x1800827b4  mov     r15, rdx
0x1800827b7  mov     [rbp+var_20], 0
0x1800827bf  mov     r14, rcx
0x1800827c2  mov     [rbp+var_10], 0
0x1800827ca  cmp     cs:byte_18010EC4D, 8
0x1800827d1  lea     r13, WPP_5cdde1c29a30365888bdf7d14a1c0af1_Traceguids
0x1800827d8  jb      short loc_18008281A
0x1800827da  mov     rcx, [rcx+68h]
0x1800827de  mov     rax, [rcx]
0x1800827e1  mov     rax, [rax+18h]
0x1800827e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800827ea  mov     rcx, r14
0x1800827ed  mov     ebx, eax
0x1800827ef  call    ?GetShareMode@FSSourceInfo@@QEBA?AW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@XZ; FSSourceInfo::GetShareMode(void)
0x1800827f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800827fb  mov     edx, 0B8h
0x180082800  mov     [rsp+70h+var_48], ebx
0x180082804  mov     r9, r14
0x180082807  mov     r8, r13
0x18008280a  mov     dword ptr [rsp+70h+var_50], eax
0x18008280e  mov     rcx, [rcx+0D8h]
0x180082815  call    WPP_SF_qDD
0x18008281a  mov     rcx, r14
0x18008281d  call    ?GetShareMode@FSSourceInfo@@QEBA?AW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@XZ; FSSourceInfo::GetShareMode(void)
0x180082822  test    eax, eax
0x180082824  jnz     loc_180082CD6
0x18008282a  mov     rcx, [r14+68h]
0x18008282e  mov     rax, [rcx]
0x180082831  mov     rax, [rax+18h]
0x180082835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008283a  cmp     eax, 4
0x18008283d  jz      loc_180082CD6
0x180082843  mov     rdi, [r14+60h]
0x180082847  lea     rcx, [rbp+var_40]
0x18008284b  mov     [rbp+var_40], 0
0x180082853  mov     [rbp+var_38], 0
0x18008285b  mov     [rbp+var_28], 0
0x180082863  mov     [rbp+arg_18], 0
0x18008286a  mov     rax, [rdi]
0x18008286d  mov     rbx, [rax+0E0h]
0x180082874  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082879  lea     r9, [rbp+var_40]
0x18008287d  mov     rcx, rdi
0x180082880  lea     r8, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180082887  mov     rax, rbx
0x18008288a  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180082891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082896  mov     ebx, eax
0x180082898  test    eax, eax
0x18008289a  jns     short loc_1800828E4
0x18008289c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800828a3  jb      short loc_1800828C4
0x1800828a5  mov     edx, 0BAh
0x1800828aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800828b1  mov     r9, r14
0x1800828b4  mov     r8, r13
0x1800828b7  mov     dword ptr [rsp+70h+var_50], eax
0x1800828bb  mov     rcx, [rcx+10h]
0x1800828bf  call    WPP_SF_qD
0x1800828c4  lea     rcx, [rbp+var_28]; void *
0x1800828c8  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800828cd  lea     rcx, [rbp+var_38]; void *
0x1800828d1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800828d6  lea     rcx, [rbp+var_40]; void *
0x1800828da  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800828df  jmp     loc_180082DBB
0x1800828e4  mov     rdi, [rbp+var_40]
0x1800828e8  lea     rcx, [rbp+var_20]
0x1800828ec  mov     rax, [rdi]
0x1800828ef  mov     rbx, [rax+50h]
0x1800828f3  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800828f8  lea     r9, [rbp+var_20]
0x1800828fc  mov     rdx, rsi
0x1800828ff  lea     r8, _GUID_22f765d1_8dab_4107_846d_56baf72215e7
0x180082906  mov     rcx, rdi
0x180082909  mov     rax, rbx
0x18008290c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082911  test    eax, eax
0x180082913  jns     short loc_180082979
0x180082915  lea     rcx, [rbp+var_20]
0x180082919  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008291e  lea     r8, [rbp+var_20]
0x180082922  mov     edx, 20000000h
0x180082927  mov     rcx, rsi
0x18008292a  call    cs:__imp_MFCreateSensorProfileWithFlags
0x180082930  mov     ebx, eax
0x180082932  test    eax, eax
0x180082934  jns     short loc_180082949
0x180082936  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008293d  jb      short loc_1800828C4
0x18008293f  mov     edx, 0BBh
0x180082944  jmp     loc_1800828AA
0x180082949  cmp     cs:byte_18010EC4D, 8
0x180082950  jb      loc_180082A11
0x180082956  mov     rcx, cs:WPP_GLOBAL_Control
0x18008295d  mov     edx, 0BCh
0x180082962  mov     r9, r14
0x180082965  mov     r8, r13
0x180082968  mov     rcx, [rcx+0D8h]
0x18008296f  call    WPP_SF_q
0x180082974  jmp     loc_180082A11
0x180082979  lea     rcx, [rbp+var_18]
0x18008297d  mov     [rbp+var_18], 0
0x180082985  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18008298a  mov     rcx, [rbp+var_20]
0x18008298e  lea     rdx, [rbp+var_18]
0x180082992  call    cs:__imp_MFCloneSensorProfile
0x180082998  mov     ebx, eax
0x18008299a  test    eax, eax
0x18008299c  jns     short loc_1800829D4
0x18008299e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800829a5  jb      short loc_1800829C6
0x1800829a7  mov     edx, 0BDh
0x1800829ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800829b3  mov     r9, r14
0x1800829b6  mov     r8, r13
0x1800829b9  mov     dword ptr [rsp+70h+var_50], eax
0x1800829bd  mov     rcx, [rcx+10h]
0x1800829c1  call    WPP_SF_qD
0x1800829c6  lea     rcx, [rbp+var_18]; void *
0x1800829ca  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800829cf  jmp     loc_1800828C4
0x1800829d4  lea     rdx, [rbp+var_18]
0x1800829d8  lea     rcx, [rbp+var_20]
0x1800829dc  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x1800829e1  cmp     cs:byte_18010EC4D, 8
0x1800829e8  jb      short loc_180082A08
0x1800829ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800829f1  mov     edx, 0BEh
0x1800829f6  mov     r9, r14
0x1800829f9  mov     r8, r13
0x1800829fc  mov     rcx, [rcx+0D8h]
0x180082a03  call    WPP_SF_q
0x180082a08  lea     rcx, [rbp+var_18]; void *
0x180082a0c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180082a11  lea     rcx, [rbp+var_40]
0x180082a15  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082a1a  mov     rcx, [r14+0A8h]
0x180082a21  mov     rax, [rcx]
0x180082a24  mov     rax, [rax+60h]
0x180082a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a2d  xor     edi, edi
0x180082a2f  test    eax, eax
0x180082a31  setz    dil
0x180082a35  cmp     cs:byte_18010EC4D, 8
0x180082a3c  jb      short loc_180082A61
0x180082a3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180082a45  mov     edx, 0BFh
0x180082a4a  mov     r9, r14
0x180082a4d  mov     [rsp+70h+var_50], rdi
0x180082a52  mov     r8, r13
0x180082a55  mov     rcx, [rcx+0D8h]
0x180082a5c  call    WPP_SF_qq
0x180082a61  test    r15, r15
0x180082a64  jz      loc_180082B32
0x180082a6a  mov     rax, [r15]
0x180082a6d  lea     rcx, [rbp+var_10]
0x180082a71  xor     edx, edx
0x180082a73  mov     rbx, [rax+68h]
0x180082a77  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180082a7c  lea     r9, [rbp+arg_18]
0x180082a80  mov     rcx, r15
0x180082a83  lea     r8, [rbp+var_10]
0x180082a87  mov     rax, rbx
0x180082a8a  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x180082a91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082a96  test    eax, eax
0x180082a98  js      loc_180082B32
0x180082a9e  mov     rcx, [rbp+var_38]
0x180082aa2  mov     [rbp+var_38], 0
0x180082aaa  test    rcx, rcx
0x180082aad  jz      short loc_180082ABB
0x180082aaf  mov     rax, [rcx]
0x180082ab2  mov     rax, [rax+10h]
0x180082ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082abb  mov     rcx, [rbp+var_10]
0x180082abf  lea     r8, [rbp+var_38]
0x180082ac3  mov     rdx, rdi
0x180082ac6  call    cs:__imp_MFCreateSensorGroupWithOptions
0x180082acc  test    eax, eax
0x180082ace  js      short loc_180082B32
0x180082ad0  mov     rdi, [rbp+var_38]
0x180082ad4  lea     rcx, [rbp+var_28]
0x180082ad8  mov     rax, [rdi]
0x180082adb  mov     rbx, [rax]
0x180082ade  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082ae3  lea     r8, [rbp+var_28]
0x180082ae7  mov     rcx, rdi
0x180082aea  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x180082af1  mov     rax, rbx
0x180082af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082af9  test    eax, eax
0x180082afb  js      short loc_180082B32
0x180082afd  mov     rdi, [rbp+var_28]
0x180082b01  lea     rcx, [rbp+var_40]
0x180082b05  mov     rax, [rdi]
0x180082b08  mov     rbx, [rax+18h]
0x180082b0c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082b11  lea     r9, [rbp+var_40]
0x180082b15  mov     rcx, rdi
0x180082b18  lea     r8, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180082b1f  mov     rax, rbx
0x180082b22  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180082b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b2e  test    eax, eax
0x180082b30  jns     short loc_180082BAA
0x180082b32  mov     rdi, [r14+60h]
0x180082b36  lea     rcx, [rbp+var_40]
0x180082b3a  mov     rax, [rdi]
0x180082b3d  mov     rbx, [rax+0E0h]
0x180082b44  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082b49  lea     r9, [rbp+var_40]
0x180082b4d  mov     rcx, rdi
0x180082b50  lea     r8, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180082b57  mov     rax, rbx
0x180082b5a  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180082b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b66  mov     ebx, eax
0x180082b68  test    eax, eax
0x180082b6a  jns     short loc_180082B83
0x180082b6c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082b73  jb      loc_1800828C4
0x180082b79  mov     edx, 0C0h
0x180082b7e  jmp     loc_1800828AA
0x180082b83  cmp     cs:byte_18010EC4D, 8
0x180082b8a  jb      short loc_180082BAA
0x180082b8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180082b93  mov     edx, 0C1h
0x180082b98  mov     r9, r14
0x180082b9b  mov     r8, r13
0x180082b9e  mov     rcx, [rcx+0D8h]
0x180082ba5  call    WPP_SF_q
0x180082baa  mov     rdi, [rbp+var_40]
0x180082bae  lea     rcx, [rbp+var_30]
0x180082bb2  mov     rax, [rdi]
0x180082bb5  mov     rbx, [rax+50h]
0x180082bb9  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082bbe  lea     r9, [rbp+var_30]
0x180082bc2  mov     rdx, rsi
0x180082bc5  lea     r8, _GUID_22f765d1_8dab_4107_846d_56baf72215e7
0x180082bcc  mov     rcx, rdi
0x180082bcf  mov     rax, rbx
0x180082bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082bd7  test    eax, eax
0x180082bd9  jns     short loc_180082C40
0x180082bdb  lea     rcx, [rbp+var_30]
0x180082bdf  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082be4  lea     r8, [rbp+var_30]
0x180082be8  mov     edx, 20000000h
0x180082bed  mov     rcx, rsi
0x180082bf0  call    cs:__imp_MFCreateSensorProfileWithFlags
0x180082bf6  mov     ebx, eax
0x180082bf8  test    eax, eax
0x180082bfa  jns     short loc_180082C13
0x180082bfc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082c03  jb      loc_1800828C4
0x180082c09  mov     edx, 0C2h
0x180082c0e  jmp     loc_1800828AA
0x180082c13  cmp     cs:byte_18010EC4D, 8
0x180082c1a  jb      loc_180082CB9
0x180082c20  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c27  mov     edx, 0C3h
0x180082c2c  mov     r9, r14
0x180082c2f  mov     r8, r13
0x180082c32  mov     rcx, [rcx+0D8h]
0x180082c39  call    WPP_SF_q
0x180082c3e  jmp     short loc_180082CB9
0x180082c40  lea     rcx, [rbp+var_18]
0x180082c44  mov     [rbp+var_18], 0
0x180082c4c  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180082c51  mov     rcx, [rbp+var_30]
0x180082c55  lea     rdx, [rbp+var_18]
0x180082c59  call    cs:__imp_MFCloneSensorProfile
0x180082c5f  mov     ebx, eax
0x180082c61  test    eax, eax
0x180082c63  jns     short loc_180082C7C
0x180082c65  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180082c6c  jb      loc_1800829C6
0x180082c72  mov     edx, 0C4h
0x180082c77  jmp     loc_1800829AC
0x180082c7c  lea     rdx, [rbp+var_18]
0x180082c80  lea     rcx, [rbp+var_30]
0x180082c84  call    ??4?$com_ptr_t@UIFSControl@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IFSControl,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IFSControl,wil::err_returncode_policy> const &)
0x180082c89  cmp     cs:byte_18010EC4D, 8
0x180082c90  jb      short loc_180082CB0
0x180082c92  mov     rcx, cs:WPP_GLOBAL_Control
0x180082c99  mov     edx, 0C5h
0x180082c9e  mov     r9, r14
0x180082ca1  mov     r8, r13
  ... truncated ...
```
