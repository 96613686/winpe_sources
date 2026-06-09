# FSSource::ConfigureProfiles(void)

- ea: `0x1800939a8`
- end: `0x1800942b5`
- name: `?ConfigureProfiles@FSSource@@IEAAJXZ`
- size: `2317`
- prototype: `__int64 __fastcall(FSSource *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180098678`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009658`
- `0x1800096f4`
- `0x180009b5c`
- `0x18004d714`
- `0x18004da70`
- `0x180088220`
- `0x1800939a8`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180093dde`
- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180093dde`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180093ac0`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180093cd9`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180093ac0`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x180093cd9`

## pseudocode

```c
__int64 __fastcall FSSource::ConfigureProfiles(FSSource *this)
{
  unsigned int v1; // r12d
  int v3; // r13d
  unsigned __int8 v4; // r15
  _QWORD *v5; // rbx
  int v6; // eax
  int v7; // eax
  int v8; // esi
  __int64 v9; // rax
  __int64 (__fastcall ***v10)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 **); // rbx
  int v12; // eax
  __int64 v13; // rdx
  int (__fastcall ***v14)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64 **); // rbx
  int (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v24; // rbx
  __int64 v25; // rax
  void (__fastcall *v26)(__int64, __int64 *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  __int64 v27; // rax
  __int64 (__fastcall ***v28)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v29)(_QWORD, GUID *, __int64 **); // rbx
  int (__fastcall ***v30)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  __int64 (__fastcall *v33)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)); // rdi
  int v34; // eax
  __int64 v35; // rdx
  int (__fastcall ***v36)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v37)(_QWORD, GUID *, __int64 *); // rbx
  int (__fastcall ***v38)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v39; // rbx
  unsigned int v40; // eax
  int (__fastcall ***v41)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v42)(_QWORD, GUID *, __int64 *); // rbx
  int v43; // eax
  unsigned int v44; // esi
  __int64 v45; // rdi
  int (__fastcall *v46)(__int64, _QWORD, _QWORD); // rbx
  int (__fastcall ***v47)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v48)(_QWORD, GUID *, __int64 **); // rbx
  unsigned int v49; // ebx
  const struct std::nothrow_t *v50; // rdx
  __int64 *v51; // rbx
  GuidTrace *v52; // rax
  const char *String; // rax
  unsigned int v54; // edi
  unsigned int v55; // eax
  unsigned int v56; // r15d
  unsigned int v57; // esi
  __int64 v58; // rbx
  char v59; // al
  int v60; // eax
  __int64 v61; // rdx
  __int64 v63; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v64; // [rsp+40h] [rbp-C0h]
  __int64 *v65; // [rsp+48h] [rbp-B8h] BYREF
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-B0h] BYREF
  __int64 v67; // [rsp+58h] [rbp-A8h] BYREF
  int v68; // [rsp+60h] [rbp-A0h]
  __int64 v69; // [rsp+68h] [rbp-98h] BYREF
  __int64 (__fastcall ***v70)(_QWORD, GUID *, __int64 **); // [rsp+70h] [rbp-90h] BYREF
  int v71; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v72; // [rsp+7Ch] [rbp-84h]
  unsigned int v73; // [rsp+80h] [rbp-80h]
  int (__fastcall ***v74)(_QWORD, GUID *, __int64 **); // [rsp+88h] [rbp-78h] BYREF
  __int64 v75; // [rsp+90h] [rbp-70h] BYREF
  __int64 v76; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v77[32]; // [rsp+A0h] [rbp-60h] BYREF
  struct _GUID v78; // [rsp+C0h] [rbp-40h] BYREF
  char v79[16]; // [rsp+D0h] [rbp-30h]
  __int64 v80[66]; // [rsp+E0h] [rbp-20h] BYREF

  v1 = 0;
  LODWORD(v67) = 0;
  v3 = 0;
  v70 = 0;
  v4 = 0;
  v66 = 0;
  v75 = 0;
  v64 = 0;
  v5 = (_QWORD *)((char *)this + 256);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 24LL))(*v5);
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 552, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v6);
  }
  v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 24LL))(*v5);
  if ( !v7 )
  {
    v70 = 0;
    v27 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 40LL))(*v5);
    if ( (int)MFCreateSensorGroupWithOptions(v27, 0, &v70) >= 0 )
    {
      v28 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
      v65 = 0;
      v29 = **v70;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v65);
      v12 = v29(v28, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, &v65);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v13 = 553;
          goto LABEL_32;
        }
        goto LABEL_33;
      }
      v30 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
      v31 = (__int64)v65;
      v32 = *v65;
      v66 = 0;
      v33 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(v32 + 24);
      if ( v30 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v30)[2])(v30);
      v12 = v33(
              v31,
              &GUID_00000000_0000_0000_0000_000000000000,
              &GUID_c95ea55b_0187_48be_9353_8d2507662351,
              (int (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v66);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_33;
        v13 = 554;
        goto LABEL_32;
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
    }
    v8 = 0;
    v68 = 0;
    goto LABEL_41;
  }
  if ( v7 == 2 )
  {
    v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 33);
    v65 = 0;
    v67 = 0;
    v19 = (**v18)(v18, &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8, &v67);
    v8 = v19;
    if ( v19 >= 0 )
    {
      v21 = v67;
      v22 = *(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v67 + 104LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v65);
      v19 = v22(v21, &v65);
      v68 = v19;
      v8 = v19;
      if ( v19 >= 0 )
      {
        v23 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
        v24 = (__int64)v65;
        v25 = *v65;
        v66 = 0;
        v26 = *(void (__fastcall **)(__int64, __int64 *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(v25 + 136);
        if ( v23 )
          ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
        v26(
          v24,
          MF_DEVICEMFT_SENSORPROFILE_COLLECTION,
          &GUID_c95ea55b_0187_48be_9353_8d2507662351,
          (int (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v66);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v67);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
        goto LABEL_41;
      }
      if ( g_wppLevels )
      {
        v20 = 556;
        goto LABEL_20;
      }
    }
    else if ( g_wppLevels )
    {
      v20 = 555;
LABEL_20:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v19);
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v67);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
    goto LABEL_87;
  }
  v68 = 0;
  v8 = 0;
  if ( v7 == 4 && (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 48LL))(*v5) == 1 )
  {
    v70 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v5 + 56LL))(*v5, 0);
    if ( (int)MFCreateSensorGroupWithOptions(v9, 1, &v70) >= 0 )
    {
      v10 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v70;
      v65 = 0;
      v11 = **v70;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v65);
      v12 = v11(v10, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, &v65);
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v13 = 557;
LABEL_32:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v13,
            &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
            this,
            v12);
          goto LABEL_33;
        }
        goto LABEL_33;
      }
      v14 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
      v15 = (__int64)v65;
      v16 = *v65;
      v66 = 0;
      v17 = *(__int64 (__fastcall **)(__int64, GUID *, GUID *, int (__fastcall ****)(_QWORD, _QWORD, _QWORD)))(v16 + 24);
      if ( v14 )
        ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v14)[2])(v14);
      v12 = v17(
              v15,
              &GUID_00000000_0000_0000_0000_000000000000,
              &GUID_c95ea55b_0187_48be_9353_8d2507662351,
              (int (__fastcall ****)(_QWORD, _QWORD, _QWORD))&v66);
      v68 = v12;
      v8 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v13 = 558;
          goto LABEL_32;
        }
LABEL_33:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
        goto LABEL_87;
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
    }
  }
LABEL_41:
  if ( !v66 )
  {
    v66 = 0;
    v34 = MFCreateSensorProfileCollection(&v66);
    v8 = v34;
    if ( v34 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_87;
      v35 = 559;
      goto LABEL_45;
    }
    v36 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
    v37 = **v66;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
    v34 = v37(v36, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v75);
    v68 = v34;
    v8 = v34;
    if ( v34 < 0 )
    {
      if ( g_wppLevels )
      {
        v35 = 560;
LABEL_45:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids, this, v34);
      }
LABEL_87:
      if ( byte_18010EC4D )
      {
        v60 = v4;
        v61 = 564;
LABEL_91:
        LODWORD(v63) = v8;
        WPP_SF_qDD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          v61,
          &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
          this,
          v63,
          v60);
        goto LABEL_92;
      }
      goto LABEL_92;
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v75 + 160LL))(v75, 0x40000000);
    v64 = 1;
  }
  v38 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
  v39 = *((_QWORD *)this + 74);
  *((_QWORD *)this + 74) = v66;
  if ( v38 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v38)[1])(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u && v66 )
  {
    v40 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 74) + 24LL))(*((_QWORD *)this + 74));
    v73 = v40;
    v76 = 0;
    if ( v40 )
    {
      v44 = v40;
      do
      {
        v45 = *((_QWORD *)this + 74);
        v74 = 0;
        v65 = 0;
        v78 = 0;
        *(_QWORD *)v79 = 0;
        v46 = *(int (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v45 + 32LL);
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v74);
        if ( v46(v45, v1, &v74) >= 0 )
        {
          v47 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v74;
          v48 = **v74;
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v65);
          if ( v48(v47, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, &v65) >= 0
            && (*(int (__fastcall **)(__int64 *, struct _GUID *))(*v65 + 24))(v65, &v78) >= 0 )
          {
            v71 = 0;
            memset_0(v80, 0, 0x208u);
            v49 = (*(__int64 (__fastcall **)(__int64 *))(*v65 + 88))(v65);
            v72 = v49;
            (*(void (__fastcall **)(__int64 *, __int64 *, __int64, int *))(*v65 + 168))(v65, v80, 260, &v71);
            if ( (unsigned __int8)byte_18010EC4D >= 8u )
            {
              v51 = (__int64 *)L"<empty>";
              if ( v71 )
                v51 = v80;
              v3 |= 1u;
              v52 = GuidTrace::GuidTrace((GuidTrace *)v77, &v78);
              String = GuidTrace::GetString(v52);
              WPP_SF_qsdS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)String, v79[0], (__int64)v51);
              v49 = v72;
            }
            if ( (v3 & 1) != 0 )
            {
              v3 &= ~1u;
              FSString::~FSString((FSString *)v77, v50);
            }
            v54 = 0;
            if ( v49 )
            {
              do
              {
                v69 = 0;
                if ( (*(int (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v65 + 96))(v65, v54, &v69) >= 0 )
                {
                  v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 88LL))(v69);
                  v56 = 0;
                  if ( v55 )
                  {
                    v57 = v55;
                    do
                    {
                      v67 = 0;
                      if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v69 + 96LL))(v69, v56, &v67) >= 0
                        && (unsigned __int8)byte_18010EC4D >= 8u )
                      {
                        v58 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 56LL))(v67);
                        v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 40LL))(v69);
                        WPP_SF_qDS(
                          *((_QWORD *)WPP_GLOBAL_Control + 27),
                          563,
                          (unsigned int)&WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
                          (_DWORD)this,
                          v59,
                          v58);
                      }
                      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v67);
                      ++v56;
                    }
                    while ( v56 < v57 );
                    v49 = v72;
                  }
                }
                wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v69);
                ++v54;
              }
              while ( v54 < v49 );
              v44 = v73;
            }
          }
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v65);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v74);
        ++v1;
      }
      while ( v1 < v44 );
      v8 = v68;
    }
    else
    {
      v41 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v66;
      v69 = 0;
      v42 = (int (__fastcall *)(_QWORD, GUID *, __int64 *))**v66;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v69);
      if ( v42(v41, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v69) >= 0 && (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v43 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v69 + 152LL))(v69);
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          561,
          &WPP_adf67030a59d332a335e13d5925f79fa_Traceguids,
          this,
          v43);
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v69);
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v76);
  }
  if ( v8 < 0 )
  {
    v4 = v64;
    goto LABEL_87;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v60 = v64;
    v61 = 565;
    goto LABEL_91;
  }
LABEL_92:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v66);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v70);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800939a8  push    rbp
0x1800939aa  push    rbx
0x1800939ab  push    rsi
0x1800939ac  push    rdi
0x1800939ad  push    r12
0x1800939af  push    r13
0x1800939b1  push    r14
0x1800939b3  push    r15
0x1800939b5  lea     rbp, [rsp-208h]
0x1800939bd  sub     rsp, 308h
0x1800939c4  mov     rax, cs:__security_cookie
0x1800939cb  xor     rax, rsp
0x1800939ce  mov     [rbp+240h+var_50], rax
0x1800939d5  xor     r12d, r12d
0x1800939d8  mov     r14, rcx
0x1800939db  mov     dword ptr [rsp+340h+var_2E8], r12d
0x1800939e0  mov     r13d, r12d
0x1800939e3  mov     [rsp+340h+var_2D0], r12
0x1800939e8  mov     r15b, r12b
0x1800939eb  mov     [rsp+340h+var_2F0], r12
0x1800939f0  mov     [rbp+240h+var_2B0], r12
0x1800939f4  mov     [rsp+340h+var_300], r12b
0x1800939f9  cmp     cs:byte_18010EC4D, 8
0x180093a00  lea     rbx, [rcx+100h]
0x180093a07  jb      short loc_180093A3E
0x180093a09  mov     rcx, [rbx]
0x180093a0c  mov     rax, [rcx]
0x180093a0f  mov     rax, [rax+18h]
0x180093a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a18  mov     rcx, cs:WPP_GLOBAL_Control
0x180093a1f  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180093a26  mov     edx, 228h
0x180093a2b  mov     dword ptr [rsp+340h+var_320], eax
0x180093a2f  mov     r9, r14
0x180093a32  mov     rcx, [rcx+0D8h]
0x180093a39  call    WPP_SF_qD
0x180093a3e  mov     rcx, [rbx]
0x180093a41  mov     rax, [rcx]
0x180093a44  mov     rax, [rax+18h]
0x180093a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a4d  test    eax, eax
0x180093a4f  jz      loc_180093CA5
0x180093a55  cmp     eax, 2
0x180093a58  jz      loc_180093B91
0x180093a5e  mov     [rsp+340h+var_2E0], r12d
0x180093a63  mov     esi, r12d
0x180093a66  cmp     eax, 4
0x180093a69  jnz     loc_180093DC9
0x180093a6f  mov     rcx, [rbx]
0x180093a72  mov     rax, [rcx]
0x180093a75  mov     rax, [rax+30h]
0x180093a79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093a7e  cmp     eax, 1
0x180093a81  jnz     loc_180093DC9
0x180093a87  mov     rcx, [rsp+340h+var_2D0]
0x180093a8c  mov     [rsp+340h+var_2D0], r12
0x180093a91  test    rcx, rcx
0x180093a94  jz      short loc_180093AA2
0x180093a96  mov     rax, [rcx]
0x180093a99  mov     rax, [rax+10h]
0x180093a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093aa2  mov     rcx, [rbx]
0x180093aa5  xor     edx, edx
0x180093aa7  mov     rax, [rcx]
0x180093aaa  mov     rax, [rax+38h]
0x180093aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ab3  lea     r8, [rsp+340h+var_2D0]
0x180093ab8  mov     edx, 1
0x180093abd  mov     rcx, rax
0x180093ac0  call    cs:__imp_MFCreateSensorGroupWithOptions
0x180093ac6  test    eax, eax
0x180093ac8  js      loc_180093DC9
0x180093ace  mov     rdi, [rsp+340h+var_2D0]
0x180093ad3  lea     rcx, [rsp+340h+var_2F8]
0x180093ad8  mov     [rsp+340h+var_2F8], r12
0x180093add  mov     rax, [rdi]
0x180093ae0  mov     rbx, [rax]
0x180093ae3  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180093ae8  lea     r8, [rsp+340h+var_2F8]
0x180093aed  mov     rcx, rdi
0x180093af0  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x180093af7  mov     rax, rbx
0x180093afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093aff  mov     esi, eax
0x180093b01  test    eax, eax
0x180093b03  jns     short loc_180093B1C
0x180093b05  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093b0c  jb      loc_180093D4A
0x180093b12  mov     edx, 22Dh
0x180093b17  jmp     loc_180093D2C
0x180093b1c  mov     rcx, [rsp+340h+var_2F0]
0x180093b21  mov     rbx, [rsp+340h+var_2F8]
0x180093b26  mov     rax, [rbx]
0x180093b29  mov     [rsp+340h+var_2F0], r12
0x180093b2e  mov     rdi, [rax+18h]
0x180093b32  test    rcx, rcx
0x180093b35  jz      short loc_180093B43
0x180093b37  mov     rax, [rcx]
0x180093b3a  mov     rax, [rax+10h]
0x180093b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b43  lea     r9, [rsp+340h+var_2F0]
0x180093b48  mov     rcx, rbx
0x180093b4b  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x180093b52  mov     rax, rdi
0x180093b55  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180093b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093b61  mov     [rsp+340h+var_2E0], eax
0x180093b65  mov     esi, eax
0x180093b67  test    eax, eax
0x180093b69  jns     short loc_180093B82
0x180093b6b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093b72  jb      loc_180093D4A
0x180093b78  mov     edx, 22Eh
0x180093b7d  jmp     loc_180093D2C
0x180093b82  lea     rcx, [rsp+340h+var_2F8]; void *
0x180093b87  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093b8c  jmp     loc_180093DC9
0x180093b91  mov     rcx, [r14+108h]
0x180093b98  lea     r8, [rsp+340h+var_2E8]
0x180093b9d  mov     [rsp+340h+var_2F8], r12
0x180093ba2  lea     rdx, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x180093ba9  mov     [rsp+340h+var_2E8], r12
0x180093bae  mov     rax, [rcx]
0x180093bb1  mov     rax, [rax]
0x180093bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093bb9  mov     esi, eax
0x180093bbb  test    eax, eax
0x180093bbd  jns     short loc_180093C04
0x180093bbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093bc6  jb      short loc_180093BEB
0x180093bc8  mov     edx, 22Bh
0x180093bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180093bd4  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180093bdb  mov     r9, r14
0x180093bde  mov     dword ptr [rsp+340h+var_320], eax
0x180093be2  mov     rcx, [rcx+10h]
0x180093be6  call    WPP_SF_qD
0x180093beb  lea     rcx, [rsp+340h+var_2E8]; void *
0x180093bf0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093bf5  lea     rcx, [rsp+340h+var_2F8]; void *
0x180093bfa  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093bff  jmp     loc_180094227
0x180093c04  mov     rdi, [rsp+340h+var_2E8]
0x180093c09  lea     rcx, [rsp+340h+var_2F8]
0x180093c0e  mov     rax, [rdi]
0x180093c11  mov     rbx, [rax+68h]
0x180093c15  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180093c1a  lea     rdx, [rsp+340h+var_2F8]
0x180093c1f  mov     rcx, rdi
0x180093c22  mov     rax, rbx
0x180093c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c2a  mov     [rsp+340h+var_2E0], eax
0x180093c2e  mov     esi, eax
0x180093c30  test    eax, eax
0x180093c32  jns     short loc_180093C44
0x180093c34  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093c3b  jb      short loc_180093BEB
0x180093c3d  mov     edx, 22Ch
0x180093c42  jmp     short loc_180093BCD
0x180093c44  mov     rcx, [rsp+340h+var_2F0]
0x180093c49  mov     rbx, [rsp+340h+var_2F8]
0x180093c4e  mov     rax, [rbx]
0x180093c51  mov     [rsp+340h+var_2F0], r12
0x180093c56  mov     rdi, [rax+88h]
0x180093c5d  test    rcx, rcx
0x180093c60  jz      short loc_180093C6E
0x180093c62  mov     rdx, [rcx]
0x180093c65  mov     rax, [rdx+10h]
0x180093c69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c6e  lea     r9, [rsp+340h+var_2F0]
0x180093c73  mov     rcx, rbx
0x180093c76  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x180093c7d  mov     rax, rdi
0x180093c80  lea     rdx, MF_DEVICEMFT_SENSORPROFILE_COLLECTION
0x180093c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093c8c  lea     rcx, [rsp+340h+var_2E8]; void *
0x180093c91  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093c96  lea     rcx, [rsp+340h+var_2F8]; void *
0x180093c9b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093ca0  jmp     loc_180093DC9
0x180093ca5  mov     rcx, [rsp+340h+var_2D0]
0x180093caa  mov     [rsp+340h+var_2D0], r12
0x180093caf  test    rcx, rcx
0x180093cb2  jz      short loc_180093CC0
0x180093cb4  mov     rax, [rcx]
0x180093cb7  mov     rax, [rax+10h]
0x180093cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093cc0  mov     rcx, [rbx]
0x180093cc3  mov     rax, [rcx]
0x180093cc6  mov     rax, [rax+28h]
0x180093cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ccf  lea     r8, [rsp+340h+var_2D0]
0x180093cd4  xor     edx, edx
0x180093cd6  mov     rcx, rax
0x180093cd9  call    cs:__imp_MFCreateSensorGroupWithOptions
0x180093cdf  test    eax, eax
0x180093ce1  js      loc_180093DC1
0x180093ce7  mov     rdi, [rsp+340h+var_2D0]
0x180093cec  lea     rcx, [rsp+340h+var_2F8]
0x180093cf1  mov     [rsp+340h+var_2F8], r12
0x180093cf6  mov     rax, [rdi]
0x180093cf9  mov     rbx, [rax]
0x180093cfc  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180093d01  lea     r8, [rsp+340h+var_2F8]
0x180093d06  mov     rcx, rdi
0x180093d09  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x180093d10  mov     rax, rbx
0x180093d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d18  mov     esi, eax
0x180093d1a  test    eax, eax
0x180093d1c  jns     short loc_180093D59
0x180093d1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093d25  jb      short loc_180093D4A
0x180093d27  mov     edx, 229h
0x180093d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180093d33  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180093d3a  mov     r9, r14
0x180093d3d  mov     dword ptr [rsp+340h+var_320], eax
0x180093d41  mov     rcx, [rcx+10h]
0x180093d45  call    WPP_SF_qD
0x180093d4a  lea     rcx, [rsp+340h+var_2F8]; void *
0x180093d4f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093d54  jmp     loc_180094227
0x180093d59  mov     rcx, [rsp+340h+var_2F0]
0x180093d5e  mov     rbx, [rsp+340h+var_2F8]
0x180093d63  mov     rax, [rbx]
0x180093d66  mov     [rsp+340h+var_2F0], r12
0x180093d6b  mov     rdi, [rax+18h]
0x180093d6f  test    rcx, rcx
0x180093d72  jz      short loc_180093D80
0x180093d74  mov     rax, [rcx]
0x180093d77  mov     rax, [rax+10h]
0x180093d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d80  lea     r9, [rsp+340h+var_2F0]
0x180093d85  mov     rcx, rbx
0x180093d88  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x180093d8f  mov     rax, rdi
0x180093d92  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180093d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d9e  mov     esi, eax
0x180093da0  test    eax, eax
0x180093da2  jns     short loc_180093DB7
0x180093da4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093dab  jb      short loc_180093D4A
0x180093dad  mov     edx, 22Ah
0x180093db2  jmp     loc_180093D2C
0x180093db7  lea     rcx, [rsp+340h+var_2F8]; void *
0x180093dbc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180093dc1  mov     esi, r12d
0x180093dc4  mov     [rsp+340h+var_2E0], r12d
0x180093dc9  cmp     [rsp+340h+var_2F0], r12
0x180093dce  jnz     loc_180093E84
0x180093dd4  lea     rcx, [rsp+340h+var_2F0]
0x180093dd9  mov     [rsp+340h+var_2F0], r12
0x180093dde  call    cs:__imp_MFCreateSensorProfileCollection
0x180093de4  mov     esi, eax
0x180093de6  test    eax, eax
0x180093de8  jns     short loc_180093E1F
0x180093dea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093df1  jb      loc_180094227
0x180093df7  mov     edx, 22Fh
0x180093dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180093e03  lea     r8, WPP_adf67030a59d332a335e13d5925f79fa_Traceguids
0x180093e0a  mov     r9, r14
0x180093e0d  mov     dword ptr [rsp+340h+var_320], eax
0x180093e11  mov     rcx, [rcx+10h]
0x180093e15  call    WPP_SF_qD
0x180093e1a  jmp     loc_180094227
0x180093e1f  mov     rdi, [rsp+340h+var_2F0]
0x180093e24  lea     rcx, [rbp+240h+var_2B0]
0x180093e28  mov     rax, [rdi]
0x180093e2b  mov     rbx, [rax]
0x180093e2e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180093e33  lea     r8, [rbp+240h+var_2B0]
0x180093e37  mov     rcx, rdi
0x180093e3a  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180093e41  mov     rax, rbx
0x180093e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e49  mov     [rsp+340h+var_2E0], eax
0x180093e4d  mov     esi, eax
0x180093e4f  test    eax, eax
0x180093e51  jns     short loc_180093E67
0x180093e53  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180093e5a  jb      loc_180094227
0x180093e60  mov     edx, 230h
0x180093e65  jmp     short loc_180093DFC
0x180093e67  mov     rcx, [rbp+240h+var_2B0]
0x180093e6b  mov     edx, 40000000h
0x180093e70  mov     rax, [rcx]
0x180093e73  mov     rax, [rax+0A0h]
0x180093e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e7f  mov     [rsp+340h+var_300], 1
0x180093e84  mov     rcx, [rsp+340h+var_2F0]
0x180093e89  mov     rbx, [r14+250h]
0x180093e90  mov     [r14+250h], rcx
0x180093e97  test    rcx, rcx
0x180093e9a  jz      short loc_180093EA8
0x180093e9c  mov     rax, [rcx]
0x180093e9f  mov     rax, [rax+8]
0x180093ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
