# FSCloneProfilesToMepProfiles(IMFSensorProfileCollection *,ushort const *,IMFSensorProfileCollection * *)

- ea: `0x180047510`
- end: `0x180047b72`
- name: `?FSCloneProfilesToMepProfiles@@YAJPEAUIMFSensorProfileCollection@@PEBGPEAPEAU1@@Z`
- size: `1634`
- prototype: `__int64 __fastcall(struct IMFSensorProfileCollection *, const unsigned __int16 *, struct IMFSensorProfileCollection **)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a914`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x180009cc0`
- `0x180017bb4`
- `0x180036730`
- `0x180047510`
- `0x180047b78`
- `0x18004d714`
- `0x18004da70`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180047600`
- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180047600`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x1800477fd`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x1800477fd`

## pseudocode

```c
__int64 __fastcall FSCloneProfilesToMepProfiles(
        struct IMFSensorProfileCollection *a1,
        const unsigned __int16 *a2,
        struct IMFSensorProfileCollection **a3)
{
  struct IMFSensorProfileCollection **v4; // r13
  int v5; // r15d
  unsigned int v6; // esi
  __int64 v7; // rdx
  int v8; // eax
  unsigned int v9; // eax
  __int64 (__fastcall **v10)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rax
  __int64 (__fastcall *v11)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rbx
  int v12; // eax
  __int64 v13; // rdx
  struct IMFSensorProfileCollection *v14; // rdi
  __int64 (__fastcall *v15)(struct IMFSensorProfileCollection *, GUID *, _QWORD); // rbx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int i; // r12d
  __int64 v21; // rax
  __int64 (__fastcall *v22)(struct IMFSensorProfileCollection *, _QWORD, __int64 *); // rbx
  int v23; // eax
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rbx
  int v26; // eax
  unsigned int v27; // edi
  unsigned int v28; // ebx
  const struct std::nothrow_t *v29; // rdx
  const wchar_t *v30; // rbx
  GuidTrace *v31; // rax
  unsigned int String; // eax
  int v33; // edx
  int v34; // r8d
  unsigned int v35; // eax
  unsigned int v36; // r12d
  unsigned int v37; // r13d
  __int64 v38; // rbx
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 (__fastcall ***v43)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFSensorProfileCollection *v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  int v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+54h] [rbp-ACh]
  unsigned int v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v51; // [rsp+68h] [rbp-98h]
  __int64 v52; // [rsp+70h] [rbp-90h] BYREF
  struct IMFSensorProfileCollection **v53; // [rsp+78h] [rbp-88h]
  struct _GUID v54; // [rsp+80h] [rbp-80h] BYREF
  __int64 v55; // [rsp+90h] [rbp-70h]
  _BYTE v56[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v57[528]; // [rsp+C0h] [rbp-40h] BYREF

  v53 = a3;
  v51 = 0;
  v4 = a3;
  v45 = 0;
  v5 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids);
  if ( !a1 )
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_62;
    v7 = 11;
    goto LABEL_6;
  }
  if ( !v4 )
  {
    v6 = -2147467261;
    if ( g_wppLevels )
    {
      v7 = 12;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v6);
    }
LABEL_62:
    if ( byte_18010EC4D )
    {
      v41 = 23;
LABEL_67:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), v41, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, v6);
      goto LABEL_68;
    }
    goto LABEL_68;
  }
  *v4 = 0;
  v45 = 0;
  v8 = MFCreateSensorProfileCollection(&v45);
  v6 = v8;
  if ( v8 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v8);
    goto LABEL_62;
  }
  v9 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)a1 + 24LL))(a1);
  v51 = v9;
  if ( v9 )
  {
    for ( i = 0; ; ++i )
    {
      v49 = i;
      if ( i >= v9 )
        break;
      v44 = 0;
      v55 = 0;
      v21 = *(_QWORD *)a1;
      v43 = 0;
      v54 = 0;
      v22 = *(__int64 (__fastcall **)(struct IMFSensorProfileCollection *, _QWORD, __int64 *))(v21 + 32);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v44);
      v23 = v22(a1, i, &v44);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v40 = 17;
        goto LABEL_60;
      }
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v43);
      v23 = MFCloneSensorProfile(v44, &v43);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v40 = 18;
        goto LABEL_60;
      }
      v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), const unsigned __int16 *))(*v43)[6])(
              v43,
              L"PHSEQ");
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v40 = 19;
        goto LABEL_60;
      }
      v23 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *, __int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v45 + 40LL))(
              v45,
              v43);
      v6 = v23;
      if ( v23 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_61;
        v40 = 20;
LABEL_60:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v23);
        goto LABEL_61;
      }
      if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
      {
        v46 = 0;
        v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
        v25 = **v43;
        wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v46);
        v26 = v25(v24, &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d, &v46);
        v27 = 0;
        if ( v26 >= 0 )
        {
          v47 = 0;
          memset_0(v57, 0, 0x208u);
          v28 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 88LL))(v46);
          v48 = v28;
          (*(void (__fastcall **)(__int64, _BYTE *, __int64, int *))(*(_QWORD *)v46 + 168LL))(v46, v57, 260, &v47);
          if ( (unsigned __int8)byte_18010EC4D >= 8u )
          {
            v30 = L"<empty>";
            if ( v47 )
              v30 = (const wchar_t *)v57;
            v5 |= 1u;
            v31 = GuidTrace::GuidTrace((GuidTrace *)v56, &v54);
            String = (unsigned int)GuidTrace::GetString(v31);
            WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 27), v33, v34, String, v55, (__int64)v30);
            v28 = v48;
          }
          if ( (v5 & 1) != 0 )
          {
            v5 &= ~1u;
            FSString::~FSString((FSString *)v56, v29);
          }
          if ( v28 )
          {
            do
            {
              v52 = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 96LL))(v46, v27, &v52) >= 0 )
              {
                v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 88LL))(v52);
                v36 = 0;
                if ( v35 )
                {
                  v37 = v35;
                  do
                  {
                    v50 = 0;
                    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 96LL))(v52, v36, &v50) >= 0
                      && (unsigned __int8)byte_18010EC4D >= 8u )
                    {
                      v38 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v50 + 56LL))(v50);
                      v39 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v52 + 40LL))(v52);
                      WPP_SF_DS(
                        *((_QWORD *)WPP_GLOBAL_Control + 27),
                        22,
                        (unsigned int)&WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids,
                        v39,
                        v38);
                    }
                    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v50);
                    ++v36;
                  }
                  while ( v36 < v37 );
                  v28 = v48;
                }
              }
              wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v52);
              ++v27;
            }
            while ( v27 < v28 );
            v4 = v53;
            i = v49;
          }
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v46);
      }
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v43);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v44);
      v9 = v51;
    }
    *v4 = v45;
    v45 = 0;
  }
  else
  {
    v10 = *(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, __int64 *))a1;
    v44 = 0;
    v43 = 0;
    v11 = *v10;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v44);
    v12 = v11(a1, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v44);
    v6 = v12;
    if ( v12 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_61:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v43);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v44);
        goto LABEL_62;
      }
      v13 = 14;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v12);
      goto LABEL_61;
    }
    v14 = v45;
    v15 = **(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, _QWORD))v45;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v43);
    v12 = v15(v14, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v43);
    v6 = v12;
    if ( v12 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_61;
      v13 = 15;
      goto LABEL_17;
    }
    v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v43;
    v17 = (*v43)[20];
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 152LL))(v44);
    ((void (__fastcall *)(_QWORD, _QWORD))v17)(v16, v18);
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 152LL))(v44);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, v19);
    }
    *v4 = v45;
    v45 = 0;
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v43);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v44);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v41 = 24;
    goto LABEL_67;
  }
LABEL_68:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v45);
  return v6;
}

```

## disassembly

```asm
0x180047510  mov     [rsp-8+arg_8], rbx
0x180047515  push    rbp
0x180047516  push    rsi
0x180047517  push    rdi
0x180047518  push    r12
0x18004751a  push    r13
0x18004751c  push    r14
0x18004751e  push    r15
0x180047520  lea     rbp, [rsp-1E0h]
0x180047528  sub     rsp, 2E0h
0x18004752f  mov     rax, cs:__security_cookie
0x180047536  xor     rax, rsp
0x180047539  mov     [rbp+210h+var_40], rax
0x180047540  xor     edi, edi
0x180047542  mov     [rsp+310h+var_298], r8
0x180047547  mov     r14, rcx
0x18004754a  mov     [rsp+310h+var_2A8], edi
0x18004754e  mov     ecx, edi
0x180047550  mov     r13, r8
0x180047553  mov     [rsp+310h+var_2D0], rcx
0x180047558  mov     r15d, edi
0x18004755b  cmp     cs:byte_18010EC4D, 8
0x180047562  jb      short loc_180047586
0x180047564  mov     rcx, cs:WPP_GLOBAL_Control
0x18004756b  lea     edx, [rdi+0Ah]
0x18004756e  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180047575  mov     rcx, [rcx+0D8h]
0x18004757c  call    WPP_SF_
0x180047581  mov     rcx, [rsp+310h+var_2D0]
0x180047586  test    r14, r14
0x180047589  jnz     short loc_1800475C4
0x18004758b  mov     esi, 80070057h
0x180047590  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180047597  jb      loc_180047AF3
0x18004759d  lea     edx, [r14+0Bh]
0x1800475a1  mov     dword ptr [rsp+310h+var_2F0], esi
0x1800475a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800475ac  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x1800475b3  xor     r9d, r9d
0x1800475b6  mov     rcx, [rcx+10h]
0x1800475ba  call    WPP_SF_qD
0x1800475bf  jmp     loc_180047AF3
0x1800475c4  test    r13, r13
0x1800475c7  jnz     short loc_1800475E1
0x1800475c9  mov     esi, 80004003h
0x1800475ce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800475d5  jb      loc_180047AF3
0x1800475db  lea     edx, [r13+0Ch]
0x1800475df  jmp     short loc_1800475A1
0x1800475e1  mov     [r13+0], rdi
0x1800475e5  mov     [rsp+310h+var_2D0], rdi
0x1800475ea  test    rcx, rcx
0x1800475ed  jz      short loc_1800475FB
0x1800475ef  mov     rax, [rcx]
0x1800475f2  mov     rax, [rax+10h]
0x1800475f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475fb  lea     rcx, [rsp+310h+var_2D0]
0x180047600  call    cs:__imp_MFCreateSensorProfileCollection
0x180047606  mov     esi, eax
0x180047608  test    eax, eax
0x18004760a  jns     short loc_180047624
0x18004760c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180047613  jb      loc_180047AF3
0x180047619  mov     edx, 0Dh
0x18004761e  mov     dword ptr [rsp+310h+var_2F0], eax
0x180047622  jmp     short loc_1800475A5
0x180047624  mov     rax, [r14]
0x180047627  mov     rcx, r14
0x18004762a  mov     rax, [rax+18h]
0x18004762e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047633  mov     [rsp+310h+var_2A8], eax
0x180047637  test    eax, eax
0x180047639  jnz     loc_180047793
0x18004763f  mov     rax, [r14]
0x180047642  lea     rcx, [rsp+310h+var_2D8]
0x180047647  mov     [rsp+310h+var_2D8], rdi
0x18004764c  mov     [rsp+310h+var_2E0], rdi
0x180047651  mov     rbx, [rax]
0x180047654  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180047659  lea     r8, [rsp+310h+var_2D8]
0x18004765e  mov     rcx, r14
0x180047661  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180047668  mov     rax, rbx
0x18004766b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047670  mov     esi, eax
0x180047672  test    eax, eax
0x180047674  jns     short loc_1800476BB
0x180047676  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004767d  jb      short loc_1800476A2
0x18004767f  mov     edx, 0Eh
0x180047684  mov     rcx, cs:WPP_GLOBAL_Control
0x18004768b  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180047692  xor     r9d, r9d
0x180047695  mov     dword ptr [rsp+310h+var_2F0], eax
0x180047699  mov     rcx, [rcx+10h]
0x18004769d  call    WPP_SF_qD
0x1800476a2  lea     rcx, [rsp+310h+var_2E0]; void *
0x1800476a7  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800476ac  lea     rcx, [rsp+310h+var_2D8]; void *
0x1800476b1  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800476b6  jmp     loc_180047AF3
0x1800476bb  mov     rdi, [rsp+310h+var_2D0]
0x1800476c0  lea     rcx, [rsp+310h+var_2E0]
0x1800476c5  mov     rax, [rdi]
0x1800476c8  mov     rbx, [rax]
0x1800476cb  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800476d0  lea     r8, [rsp+310h+var_2E0]
0x1800476d5  mov     rcx, rdi
0x1800476d8  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x1800476df  mov     rax, rbx
0x1800476e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476e7  mov     esi, eax
0x1800476e9  test    eax, eax
0x1800476eb  jns     short loc_1800476FD
0x1800476ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800476f4  jb      short loc_1800476A2
0x1800476f6  mov     edx, 0Fh
0x1800476fb  jmp     short loc_180047684
0x1800476fd  mov     rdi, [rsp+310h+var_2E0]
0x180047702  mov     rcx, [rsp+310h+var_2D8]
0x180047707  mov     rax, [rdi]
0x18004770a  mov     rdx, [rcx]
0x18004770d  mov     rbx, [rax+0A0h]
0x180047714  mov     rax, [rdx+98h]
0x18004771b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047720  mov     edx, eax
0x180047722  mov     rcx, rdi
0x180047725  mov     rax, rbx
0x180047728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004772d  cmp     cs:byte_18010EC4D, 8
0x180047734  jb      short loc_18004776C
0x180047736  mov     rcx, [rsp+310h+var_2D8]
0x18004773b  mov     rax, [rcx]
0x18004773e  mov     rax, [rax+98h]
0x180047745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004774a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047751  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180047758  mov     edx, 10h
0x18004775d  mov     r9d, eax
0x180047760  mov     rcx, [rcx+0D8h]
0x180047767  call    WPP_SF_d
0x18004776c  mov     rax, [rsp+310h+var_2D0]
0x180047771  lea     rcx, [rsp+310h+var_2E0]; void *
0x180047776  mov     [r13+0], rax
0x18004777a  mov     [rsp+310h+var_2D0], r15
0x18004777f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180047784  lea     rcx, [rsp+310h+var_2D8]; void *
0x180047789  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18004778e  jmp     loc_180047B11
0x180047793  mov     r12d, edi
0x180047796  mov     [rsp+310h+var_2B8], r12d
0x18004779b  cmp     r12d, eax
0x18004779e  jnb     loc_180047B03
0x1800477a4  xor     eax, eax
0x1800477a6  mov     [rsp+310h+var_2D8], rdi
0x1800477ab  mov     [rbp+210h+var_280], rax
0x1800477af  lea     rcx, [rsp+310h+var_2D8]
0x1800477b4  mov     rax, [r14]
0x1800477b7  xorps   xmm0, xmm0
0x1800477ba  mov     [rsp+310h+var_2E0], rdi
0x1800477bf  movups  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x1800477c3  mov     rbx, [rax+20h]
0x1800477c7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800477cc  lea     r8, [rsp+310h+var_2D8]
0x1800477d1  mov     edx, r12d
0x1800477d4  mov     rcx, r14
0x1800477d7  mov     rax, rbx
0x1800477da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477df  mov     esi, eax
0x1800477e1  test    eax, eax
0x1800477e3  js      loc_180047AB3
0x1800477e9  lea     rcx, [rsp+310h+var_2E0]
0x1800477ee  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800477f3  mov     rcx, [rsp+310h+var_2D8]
0x1800477f8  lea     rdx, [rsp+310h+var_2E0]
0x1800477fd  call    cs:__imp_MFCloneSensorProfile
0x180047803  mov     esi, eax
0x180047805  test    eax, eax
0x180047807  js      loc_180047AA3
0x18004780d  mov     rcx, [rsp+310h+var_2E0]
0x180047812  lea     rdx, aPhseq; "PHSEQ"
0x180047819  mov     rax, [rcx]
0x18004781c  mov     rax, [rax+30h]
0x180047820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047825  mov     esi, eax
0x180047827  test    eax, eax
0x180047829  js      loc_180047A93
0x18004782f  mov     rcx, [rsp+310h+var_2D0]
0x180047834  mov     rdx, [rsp+310h+var_2E0]
0x180047839  mov     rax, [rcx]
0x18004783c  mov     rax, [rax+28h]
0x180047840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047845  mov     esi, eax
0x180047847  test    eax, eax
0x180047849  js      loc_180047A83
0x18004784f  cmp     cs:byte_18010EC4D, 10h
0x180047856  jb      loc_180047A63
0x18004785c  mov     [rsp+310h+var_2C8], rdi
0x180047861  lea     rcx, [rsp+310h+var_2C8]
0x180047866  mov     rdi, [rsp+310h+var_2E0]
0x18004786b  mov     rax, [rdi]
0x18004786e  mov     rbx, [rax]
0x180047871  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180047876  lea     r8, [rsp+310h+var_2C8]
0x18004787b  mov     rcx, rdi
0x18004787e  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x180047885  mov     rax, rbx
0x180047888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004788d  xor     edi, edi
0x18004788f  test    eax, eax
0x180047891  js      loc_180047A59
0x180047897  xor     edx, edx; Val
0x180047899  mov     [rsp+310h+var_2C0], edi
0x18004789d  mov     r8d, 208h; Size
0x1800478a3  lea     rcx, [rbp+210h+var_250]; void *
0x1800478a7  call    memset_0
0x1800478ac  mov     rcx, [rsp+310h+var_2C8]
0x1800478b1  mov     rax, [rcx]
0x1800478b4  mov     rax, [rax+58h]
0x1800478b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478bd  mov     rcx, [rsp+310h+var_2C8]
0x1800478c2  lea     r9, [rsp+310h+var_2C0]
0x1800478c7  mov     ebx, eax
0x1800478c9  mov     [rsp+310h+var_2BC], eax
0x1800478cd  mov     r8d, 104h
0x1800478d3  mov     rdx, [rcx]
0x1800478d6  mov     rax, [rdx+0A8h]
0x1800478dd  lea     rdx, [rbp+210h+var_250]
0x1800478e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800478e6  cmp     cs:byte_18010EC4D, 8
0x1800478ed  jb      short loc_180047941
0x1800478ef  cmp     [rsp+310h+var_2C0], edi
0x1800478f3  lea     rax, [rbp+210h+var_250]
0x1800478f7  lea     rbx, aEmpty_1; "<empty>"
0x1800478fe  cmovnz  rbx, rax
0x180047902  lea     rdx, [rbp+210h+var_290]; struct _GUID *
0x180047906  lea     rcx, [rbp+210h+var_278]; this
0x18004790a  or      r15d, 1
0x18004790e  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180047913  mov     rcx, rax; this
0x180047916  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18004791b  mov     ecx, dword ptr [rbp+210h+var_280]
0x18004791e  mov     r9, rax
0x180047921  mov     [rsp+310h+var_2E8], rbx
0x180047926  mov     dword ptr [rsp+310h+var_2F0], ecx
0x18004792a  mov     rcx, cs:WPP_GLOBAL_Control
0x180047931  mov     rcx, [rcx+0D8h]
0x180047938  call    WPP_SF_sdS
0x18004793d  mov     ebx, [rsp+310h+var_2BC]
0x180047941  test    r15b, 1
0x180047945  jz      short loc_180047954
0x180047947  and     r15d, 0FFFFFFFEh
0x18004794b  lea     rcx, [rbp+210h+var_278]; this
0x18004794f  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180047954  test    ebx, ebx
0x180047956  jz      loc_180047A59
0x18004795c  mov     rcx, [rsp+310h+var_2C8]
0x180047961  lea     r8, [rsp+310h+var_2A0]
0x180047966  mov     [rsp+310h+var_2A0], 0
0x18004796f  mov     edx, edi
0x180047971  mov     rax, [rcx]
0x180047974  mov     rax, [rax+60h]
0x180047978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004797d  test    eax, eax
0x18004797f  js      loc_180047A39
0x180047985  mov     rcx, [rsp+310h+var_2A0]
0x18004798a  mov     rax, [rcx]
0x18004798d  mov     rax, [rax+58h]
0x180047991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047996  xor     r12d, r12d
0x180047999  test    eax, eax
0x18004799b  jz      loc_180047A39
0x1800479a1  mov     r13d, eax
0x1800479a4  mov     rcx, [rsp+310h+var_2A0]
0x1800479a9  lea     r8, [rsp+310h+var_2B0]
0x1800479ae  mov     [rsp+310h+var_2B0], 0
0x1800479b7  mov     rdx, [rcx]
0x1800479ba  mov     rax, [rdx+60h]
0x1800479be  mov     edx, r12d
0x1800479c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479c6  test    eax, eax
0x1800479c8  js      short loc_180047A1F
0x1800479ca  cmp     cs:byte_18010EC4D, 8
0x1800479d1  jb      short loc_180047A1F
0x1800479d3  mov     rcx, [rsp+310h+var_2B0]
0x1800479d8  mov     rax, [rcx]
0x1800479db  mov     rax, [rax+38h]
0x1800479df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479e4  mov     rcx, [rsp+310h+var_2A0]
0x1800479e9  mov     rbx, rax
0x1800479ec  mov     rdx, [rcx]
0x1800479ef  mov     rax, [rdx+28h]
0x1800479f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800479f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800479ff  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180047a06  mov     edx, 16h
0x180047a0b  mov     [rsp+310h+var_2F0], rbx
0x180047a10  mov     r9d, eax
0x180047a13  mov     rcx, [rcx+0D8h]
0x180047a1a  call    WPP_SF_DS
  ... truncated ...
```
