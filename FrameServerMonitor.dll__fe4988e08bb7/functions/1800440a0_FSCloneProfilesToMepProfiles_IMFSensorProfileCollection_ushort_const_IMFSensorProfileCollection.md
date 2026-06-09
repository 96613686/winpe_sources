# FSCloneProfilesToMepProfiles(IMFSensorProfileCollection *,ushort const *,IMFSensorProfileCollection * *)

- ea: `0x1800440a0`
- end: `0x1800446f9`
- name: `?FSCloneProfilesToMepProfiles@@YAJPEAUIMFSensorProfileCollection@@PEBGPEAPEAU1@@Z`
- size: `1625`
- prototype: `__int64 __fastcall(struct IMFSensorProfileCollection *, const unsigned __int16 *, struct IMFSensorProfileCollection **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029540`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180005f98`
- `0x1800060e8`
- `0x1800060f8`
- `0x180006a98`
- `0x18000d3b0`
- `0x18000d3d8`
- `0x18000d418`
- `0x180011438`
- `0x18002fa3c`
- `0x18002fd04`
- `0x1800440a0`
- `0x180044700`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180044198`
- `MFSENSORGROUP!MFCreateSensorProfileCollection` at `0x180044198`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180044396`
- `MFSENSORGROUP!MFCloneSensorProfile` at `0x180044396`

## pseudocode

```c
__int64 __fastcall FSCloneProfilesToMepProfiles(
        struct IMFSensorProfileCollection *a1,
        const unsigned __int16 *a2,
        struct IMFSensorProfileCollection **a3)
{
  unsigned int v3; // r12d
  struct IMFSensorProfileCollection *v4; // rdi
  int v6; // r15d
  struct IMFSensorProfileCollection *v7; // rcx
  int v8; // esi
  __int64 v9; // rdx
  unsigned int v10; // eax
  __int64 (__fastcall **v11)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rax
  __int64 v12; // rdx
  __int64 (__fastcall **v13)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rax
  __int64 v14; // rdi
  void (__fastcall *v15)(__int64, _QWORD); // rbx
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int i; // r13d
  __int64 v19; // rax
  __int64 v20; // rcx
  unsigned int v21; // ebx
  const struct std::nothrow_t *v22; // rdx
  const wchar_t *v23; // rbx
  GuidTrace *v24; // rax
  unsigned int String; // eax
  int v26; // edx
  int v27; // r8d
  unsigned int v28; // r14d
  unsigned int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // rbx
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  struct IMFSensorProfileCollection *v35; // rax
  __int64 v37; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v38; // [rsp+38h] [rbp-C8h] BYREF
  struct IMFSensorProfileCollection *v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v41; // [rsp+4Ch] [rbp-B4h]
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v43; // [rsp+58h] [rbp-A8h]
  __int64 v44; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+68h] [rbp-98h] BYREF
  struct IMFSensorProfileCollection *v46; // [rsp+70h] [rbp-90h]
  struct IMFSensorProfileCollection **v47; // [rsp+78h] [rbp-88h]
  struct _GUID v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  _BYTE v50[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v51[528]; // [rsp+C0h] [rbp-40h] BYREF

  v3 = 0;
  v46 = a1;
  v4 = a1;
  v47 = a3;
  v43 = 0;
  v39 = 0;
  v6 = 0;
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 27), 10, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids);
    v7 = v39;
  }
  if ( !v4 )
  {
    v8 = -2147024809;
    if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      goto LABEL_67;
    v9 = 11;
    goto LABEL_6;
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 12;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v8);
      goto LABEL_67;
    }
    goto LABEL_67;
  }
  *a3 = 0;
  v39 = 0;
  if ( v7 )
    (*(void (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = MFCreateSensorProfileCollection(&v39);
  if ( v8 < 0 )
  {
    if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
    {
      v9 = 13;
      goto LABEL_6;
    }
LABEL_67:
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() )
    {
      v34 = 23;
LABEL_72:
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v34,
        &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids,
        (unsigned int)v8);
      goto LABEL_73;
    }
    goto LABEL_73;
  }
  v10 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v4 + 24LL))(v4);
  v43 = v10;
  if ( v10 )
  {
    for ( i = 0; i < v10; ++i )
    {
      v37 = 0;
      v49 = 0;
      v19 = *(_QWORD *)v4;
      v38 = 0;
      v48 = 0;
      v8 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *, _QWORD, __int64 *))(v19 + 32))(v4, i, &v38);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v33 = 17;
        goto LABEL_65;
      }
      v20 = v37;
      v37 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v8 = MFCloneSensorProfile(v38, &v37);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v33 = 18;
        goto LABEL_65;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v37 + 48LL))(v37, L"PHSEQ");
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v33 = 19;
        goto LABEL_65;
      }
      v8 = (*(__int64 (__fastcall **)(struct IMFSensorProfileCollection *, __int64))(*(_QWORD *)v39 + 40LL))(v39, v37);
      if ( v8 < 0 )
      {
        if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          goto LABEL_66;
        v33 = 20;
LABEL_65:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v8);
        goto LABEL_66;
      }
      if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 0x10u )
      {
        v45 = 0;
        if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
               v37,
               &GUID_b35b06ef_9123_4604_a586_9750cdd2c67d,
               &v45) >= 0 )
        {
          v40 = 0;
          memset_0(v51, 0, 0x208u);
          v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v45 + 88LL))(v45);
          v41 = v21;
          (*(void (__fastcall **)(__int64, _BYTE *, __int64, int *))(*(_QWORD *)v45 + 168LL))(v45, v51, 260, &v40);
          if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
          {
            v23 = L"<empty>";
            if ( v40 )
              v23 = (const wchar_t *)v51;
            v6 |= 1u;
            v24 = GuidTrace::GuidTrace((GuidTrace *)v50, &v48);
            String = (unsigned int)GuidTrace::GetString(v24);
            WPP_SF_sdS(*((_QWORD *)WPP_GLOBAL_Control + 27), v26, v27, String, v49, (__int64)v23);
            v21 = v41;
          }
          if ( (v6 & 1) != 0 )
          {
            v6 &= ~1u;
            FSString::~FSString((FSString *)v50, v22);
          }
          v28 = 0;
          if ( v21 )
          {
            do
            {
              v44 = 0;
              if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 96LL))(v45, v28, &v44) >= 0 )
              {
                v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 88LL))(v44);
                if ( v29 )
                {
                  v30 = v29;
                  do
                  {
                    v42 = 0;
                    if ( (*(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v44 + 96LL))(v44, v3, &v42) >= 0
                      && _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
                    {
                      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 56LL))(v42);
                      v32 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 40LL))(v44);
                      WPP_SF_DS(
                        *((_QWORD *)WPP_GLOBAL_Control + 27),
                        22,
                        (unsigned int)&WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids,
                        v32,
                        v31);
                    }
                    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v42);
                    ++v3;
                  }
                  while ( v3 < v30 );
                  v21 = v41;
                }
                v3 = 0;
              }
              wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v44);
              ++v28;
            }
            while ( v28 < v21 );
            v4 = v46;
          }
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v45);
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v37);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v38);
      v10 = v43;
    }
    v35 = v39;
    v39 = 0;
    *v47 = v35;
  }
  else
  {
    v11 = *(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, __int64 *))v4;
    v37 = 0;
    v38 = 0;
    v8 = (*v11)(v4, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v38);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
      {
LABEL_66:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v37);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v38);
        goto LABEL_67;
      }
      v12 = 14;
LABEL_19:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, 0, v8);
      goto LABEL_66;
    }
    v13 = *(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, __int64 *))v39;
    v37 = 0;
    v8 = (*v13)(v39, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v37);
    if ( v8 < 0 )
    {
      if ( !_MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
        goto LABEL_66;
      v12 = 15;
      goto LABEL_19;
    }
    v14 = v37;
    v15 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v37 + 160LL);
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 152LL))(v38);
    v15(v14, v16);
    if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
    {
      v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v38 + 152LL))(v38);
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 27), 16, &WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids, v17);
    }
    *a3 = v39;
    v39 = 0;
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v37);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v38);
  }
  if ( _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel() >= 8u )
  {
    v34 = 24;
    goto LABEL_72;
  }
LABEL_73:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v39);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800440a0  mov     [rsp-8+arg_8], rbx
0x1800440a5  push    rbp
0x1800440a6  push    rsi
0x1800440a7  push    rdi
0x1800440a8  push    r12
0x1800440aa  push    r13
0x1800440ac  push    r14
0x1800440ae  push    r15
0x1800440b0  lea     rbp, [rsp-1E0h]
0x1800440b8  sub     rsp, 2E0h
0x1800440bf  mov     rax, cs:__security_cookie
0x1800440c6  xor     rax, rsp
0x1800440c9  mov     [rbp+210h+var_40], rax
0x1800440d0  xor     r12d, r12d
0x1800440d3  mov     [rsp+310h+var_2A0], rcx
0x1800440d8  mov     rdi, rcx
0x1800440db  mov     [rsp+310h+var_298], r8
0x1800440e0  mov     ecx, r12d
0x1800440e3  mov     [rsp+310h+var_2B8], r12d
0x1800440e8  mov     [rsp+310h+var_2D0], rcx
0x1800440ed  mov     r14, r8
0x1800440f0  mov     r15d, r12d
0x1800440f3  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800440f8  cmp     al, 8
0x1800440fa  jb      short loc_180044120
0x1800440fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180044103  lea     edx, [r12+0Ah]
0x180044108  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x18004410f  mov     rcx, [rcx+0D8h]
0x180044116  call    WPP_SF_
0x18004411b  mov     rcx, [rsp+310h+var_2D0]
0x180044120  test    rdi, rdi
0x180044123  jnz     short loc_18004415D
0x180044125  mov     esi, 80070057h
0x18004412a  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004412f  cmp     al, 1
0x180044131  jb      loc_180044676
0x180044137  lea     edx, [rdi+0Bh]
0x18004413a  mov     rcx, cs:WPP_GLOBAL_Control
0x180044141  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180044148  xor     r9d, r9d
0x18004414b  mov     dword ptr [rsp+310h+var_2F0], esi
0x18004414f  mov     rcx, [rcx+10h]
0x180044153  call    WPP_SF_qD
0x180044158  jmp     loc_180044676
0x18004415d  test    r14, r14
0x180044160  jnz     short loc_18004417A
0x180044162  mov     esi, 80004003h
0x180044167  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004416c  cmp     al, 1
0x18004416e  jb      loc_180044676
0x180044174  lea     edx, [r14+0Ch]
0x180044178  jmp     short loc_18004413A
0x18004417a  mov     [r14], r12
0x18004417d  mov     [rsp+310h+var_2D0], r12
0x180044182  test    rcx, rcx
0x180044185  jz      short loc_180044193
0x180044187  mov     rax, [rcx]
0x18004418a  mov     rax, [rax+10h]
0x18004418e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044193  lea     rcx, [rsp+310h+var_2D0]
0x180044198  call    cs:__imp_MFCreateSensorProfileCollection
0x18004419e  mov     esi, eax
0x1800441a0  test    eax, eax
0x1800441a2  jns     short loc_1800441B8
0x1800441a4  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x1800441a9  cmp     al, 1
0x1800441ab  jb      loc_180044676
0x1800441b1  mov     edx, 0Dh
0x1800441b6  jmp     short loc_18004413A
0x1800441b8  mov     rax, [rdi]
0x1800441bb  mov     rcx, rdi
0x1800441be  mov     rax, [rax+18h]
0x1800441c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441c7  mov     [rsp+310h+var_2B8], eax
0x1800441cb  test    eax, eax
0x1800441cd  jnz     loc_18004432D
0x1800441d3  mov     rax, [rdi]
0x1800441d6  lea     r8, [rsp+310h+var_2D8]
0x1800441db  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x1800441e2  mov     [rsp+310h+var_2E0], r12
0x1800441e7  mov     rcx, rdi
0x1800441ea  mov     [rsp+310h+var_2D8], r12
0x1800441ef  mov     rax, [rax]
0x1800441f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441f7  mov     esi, eax
0x1800441f9  test    eax, eax
0x1800441fb  jns     short loc_180044242
0x1800441fd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180044202  cmp     al, 1
0x180044204  jb      short loc_180044229
0x180044206  mov     edx, 0Eh
0x18004420b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044212  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x180044219  xor     r9d, r9d
0x18004421c  mov     dword ptr [rsp+310h+var_2F0], esi
0x180044220  mov     rcx, [rcx+10h]
0x180044224  call    WPP_SF_qD
0x180044229  lea     rcx, [rsp+310h+var_2E0]
0x18004422e  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180044233  lea     rcx, [rsp+310h+var_2D8]
0x180044238  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004423d  jmp     loc_180044676
0x180044242  mov     rcx, [rsp+310h+var_2E0]
0x180044247  mov     rbx, [rsp+310h+var_2D0]
0x18004424c  mov     rax, [rbx]
0x18004424f  mov     [rsp+310h+var_2E0], r12
0x180044254  mov     rdi, [rax]
0x180044257  test    rcx, rcx
0x18004425a  jz      short loc_180044268
0x18004425c  mov     r8, [rcx]
0x18004425f  mov     rax, [r8+10h]
0x180044263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044268  lea     r8, [rsp+310h+var_2E0]
0x18004426d  mov     rcx, rbx
0x180044270  lea     rdx, _GUID_9a9daaaa_9774_4732_848e_8739655f2ba3
0x180044277  mov     rax, rdi
0x18004427a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004427f  mov     esi, eax
0x180044281  test    eax, eax
0x180044283  jns     short loc_180044298
0x180044285  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18004428a  cmp     al, 1
0x18004428c  jb      short loc_180044229
0x18004428e  mov     edx, 0Fh
0x180044293  jmp     loc_18004420B
0x180044298  mov     rdi, [rsp+310h+var_2E0]
0x18004429d  mov     rcx, [rsp+310h+var_2D8]
0x1800442a2  mov     rax, [rdi]
0x1800442a5  mov     rdx, [rcx]
0x1800442a8  mov     rbx, [rax+0A0h]
0x1800442af  mov     rax, [rdx+98h]
0x1800442b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442bb  mov     edx, eax
0x1800442bd  mov     rcx, rdi
0x1800442c0  mov     rax, rbx
0x1800442c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442c8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800442cd  cmp     al, 8
0x1800442cf  jb      short loc_180044307
0x1800442d1  mov     rcx, [rsp+310h+var_2D8]
0x1800442d6  mov     rax, [rcx]
0x1800442d9  mov     rax, [rax+98h]
0x1800442e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800442ec  lea     r8, WPP_fa9e39f405903c8ceb5d154a80b23f72_Traceguids
0x1800442f3  mov     edx, 10h
0x1800442f8  mov     r9d, eax
0x1800442fb  mov     rcx, [rcx+0D8h]
0x180044302  call    WPP_SF_d
0x180044307  mov     rax, [rsp+310h+var_2D0]
0x18004430c  lea     rcx, [rsp+310h+var_2E0]
0x180044311  mov     [r14], rax
0x180044314  mov     [rsp+310h+var_2D0], r12
0x180044319  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18004431e  lea     rcx, [rsp+310h+var_2D8]
0x180044323  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180044328  jmp     loc_180044698
0x18004432d  mov     r13d, r12d
0x180044330  cmp     r13d, eax
0x180044333  jnb     loc_180044686
0x180044339  xor     eax, eax
0x18004433b  mov     [rsp+310h+var_2E0], r12
0x180044340  mov     [rbp+210h+var_280], rax
0x180044344  lea     r8, [rsp+310h+var_2D8]
0x180044349  mov     rax, [rdi]
0x18004434c  xorps   xmm0, xmm0
0x18004434f  mov     edx, r13d
0x180044352  mov     [rsp+310h+var_2D8], r12
0x180044357  mov     rcx, rdi
0x18004435a  movups  xmmword ptr [rbp+210h+var_290.Data1], xmm0
0x18004435e  mov     rax, [rax+20h]
0x180044362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044367  mov     esi, eax
0x180044369  test    eax, eax
0x18004436b  js      loc_180044636
0x180044371  mov     rcx, [rsp+310h+var_2E0]
0x180044376  mov     [rsp+310h+var_2E0], r12
0x18004437b  test    rcx, rcx
0x18004437e  jz      short loc_18004438C
0x180044380  mov     rax, [rcx]
0x180044383  mov     rax, [rax+10h]
0x180044387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004438c  mov     rcx, [rsp+310h+var_2D8]
0x180044391  lea     rdx, [rsp+310h+var_2E0]
0x180044396  call    cs:__imp_MFCloneSensorProfile
0x18004439c  mov     esi, eax
0x18004439e  test    eax, eax
0x1800443a0  js      loc_180044626
0x1800443a6  mov     rcx, [rsp+310h+var_2E0]
0x1800443ab  lea     rdx, aPhseq; "PHSEQ"
0x1800443b2  mov     rax, [rcx]
0x1800443b5  mov     rax, [rax+30h]
0x1800443b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443be  mov     esi, eax
0x1800443c0  test    eax, eax
0x1800443c2  js      loc_180044616
0x1800443c8  mov     rcx, [rsp+310h+var_2D0]
0x1800443cd  mov     rdx, [rsp+310h+var_2E0]
0x1800443d2  mov     rax, [rcx]
0x1800443d5  mov     rax, [rax+28h]
0x1800443d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443de  mov     esi, eax
0x1800443e0  test    eax, eax
0x1800443e2  js      loc_180044606
0x1800443e8  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x1800443ed  cmp     al, 10h
0x1800443ef  jb      loc_1800445E6
0x1800443f5  mov     rcx, [rsp+310h+var_2E0]
0x1800443fa  lea     r8, [rsp+310h+var_2A8]
0x1800443ff  mov     [rsp+310h+var_2A8], r12
0x180044404  lea     rdx, _GUID_b35b06ef_9123_4604_a586_9750cdd2c67d
0x18004440b  mov     rax, [rcx]
0x18004440e  mov     rax, [rax]
0x180044411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044416  test    eax, eax
0x180044418  js      loc_1800445DC
0x18004441e  xor     edx, edx; Val
0x180044420  mov     [rsp+310h+var_2C8], r12d
0x180044425  mov     r8d, 208h; Size
0x18004442b  lea     rcx, [rbp+210h+var_250]; void *
0x18004442f  call    memset_0
0x180044434  mov     rcx, [rsp+310h+var_2A8]
0x180044439  mov     rax, [rcx]
0x18004443c  mov     rax, [rax+58h]
0x180044440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044445  mov     rcx, [rsp+310h+var_2A8]
0x18004444a  lea     r9, [rsp+310h+var_2C8]
0x18004444f  mov     ebx, eax
0x180044451  mov     [rsp+310h+var_2C4], eax
0x180044455  mov     r8d, 104h
0x18004445b  mov     rdx, [rcx]
0x18004445e  mov     rax, [rdx+0A8h]
0x180044465  lea     rdx, [rbp+210h+var_250]
0x180044469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004446e  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180044473  cmp     al, 8
0x180044475  jb      short loc_1800444CA
0x180044477  cmp     [rsp+310h+var_2C8], r12d
0x18004447c  lea     rax, [rbp+210h+var_250]
0x180044480  lea     rbx, aEmpty; "<empty>"
0x180044487  cmovnz  rbx, rax
0x18004448b  lea     rdx, [rbp+210h+var_290]; struct _GUID *
0x18004448f  lea     rcx, [rbp+210h+var_278]; this
0x180044493  or      r15d, 1
0x180044497  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18004449c  mov     rcx, rax; this
0x18004449f  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800444a4  mov     ecx, dword ptr [rbp+210h+var_280]
0x1800444a7  mov     r9, rax
0x1800444aa  mov     [rsp+310h+var_2E8], rbx
0x1800444af  mov     dword ptr [rsp+310h+var_2F0], ecx
0x1800444b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800444ba  mov     rcx, [rcx+0D8h]
0x1800444c1  call    WPP_SF_sdS
0x1800444c6  mov     ebx, [rsp+310h+var_2C4]
0x1800444ca  test    r15b, 1
0x1800444ce  jz      short loc_1800444DD
0x1800444d0  and     r15d, 0FFFFFFFEh
0x1800444d4  lea     rcx, [rbp+210h+var_278]; this
0x1800444d8  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800444dd  mov     r14d, r12d
0x1800444e0  test    ebx, ebx
0x1800444e2  jz      loc_1800445DC
0x1800444e8  mov     rcx, [rsp+310h+var_2A8]
0x1800444ed  lea     r8, [rsp+310h+var_2B0]
0x1800444f2  mov     [rsp+310h+var_2B0], r12
0x1800444f7  mov     edx, r14d
0x1800444fa  mov     rax, [rcx]
0x1800444fd  mov     rax, [rax+60h]
0x180044501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044506  test    eax, eax
0x180044508  js      loc_1800445C1
0x18004450e  mov     rcx, [rsp+310h+var_2B0]
0x180044513  mov     rax, [rcx]
0x180044516  mov     rax, [rax+58h]
0x18004451a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004451f  test    eax, eax
0x180044521  jz      loc_1800445BE
0x180044527  mov     edi, eax
0x180044529  mov     rcx, [rsp+310h+var_2B0]
0x18004452e  lea     r8, [rsp+310h+var_2C0]
0x180044533  mov     [rsp+310h+var_2C0], 0
0x18004453c  mov     rdx, [rcx]
0x18004453f  mov     rax, [rdx+60h]
0x180044543  mov     edx, r12d
0x180044546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004454b  test    eax, eax
0x18004454d  js      short loc_1800445A4
0x18004454f  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_CORE_MFTS@@SAEXZ; _MFControlLevel_CTRLGUID_MF_CORE_MFTS::GetLevel(void)
0x180044554  cmp     al, 8
0x180044556  jb      short loc_1800445A4
0x180044558  mov     rcx, [rsp+310h+var_2C0]
0x18004455d  mov     rax, [rcx]
0x180044560  mov     rax, [rax+38h]
0x180044564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044569  mov     rcx, [rsp+310h+var_2B0]
0x18004456e  mov     rbx, rax
0x180044571  mov     rdx, [rcx]
0x180044574  mov     rax, [rdx+28h]
  ... truncated ...
```
