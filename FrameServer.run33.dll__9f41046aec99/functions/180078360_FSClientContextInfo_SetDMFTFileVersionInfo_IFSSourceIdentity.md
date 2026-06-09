# FSClientContextInfo::SetDMFTFileVersionInfo(IFSSourceIdentity *)

- ea: `0x180078360`
- end: `0x180078919`
- name: `?SetDMFTFileVersionInfo@FSClientContextInfo@@UEAAJPEAUIFSSourceIdentity@@@Z`
- size: `1465`
- prototype: `int(FSClientContextInfo *__hidden this, struct IFSSourceIdentity *)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800041f0`
- `0x18000478c`
- `0x180009608`
- `0x180017ab8`
- `0x180017f60`
- `0x180018998`
- `0x18004d714`
- `0x18004d748`
- `0x18007503c`
- `0x1800763f0`
- `0x180076584`
- `0x180078360`
- `0x180078e18`
- `0x1800e26e8`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078867`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180078867`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078393`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180078393`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800784ce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800784ce`

## pseudocode

```c
__int64 __fastcall FSClientContextInfo::SetDMFTFileVersionInfo(FSClientContextInfo *this, struct IFSSourceIdentity *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  FSClientContextInfo *v3; // r14
  int v4; // edi
  FSSourceIdentityTrace *v6; // rax
  const char *String; // rax
  unsigned int v8; // esi
  int v9; // eax
  __int64 v10; // rdx
  unsigned __int8 *v11; // r13
  int v12; // eax
  const struct std::nothrow_t *v13; // rdx
  __int64 v14; // rdx
  size_t v15; // rdi
  void *v16; // rax
  void *v17; // rsi
  __int64 v18; // rax
  int v19; // esi
  int v20; // r14d
  int v21; // r15d
  int v22; // r12d
  __int64 v23; // rax
  int v24; // eax
  char v25; // di
  __int64 v26; // rax
  __int64 v27; // rdx
  int v29; // edi
  __int64 v30; // [rsp+30h] [rbp-100h]
  __int64 v31; // [rsp+38h] [rbp-F8h]
  int v32; // [rsp+40h] [rbp-F0h]
  __int64 v33; // [rsp+40h] [rbp-F0h]
  __int64 v34; // [rsp+48h] [rbp-E8h]
  __int64 v35; // [rsp+50h] [rbp-E0h]
  __int64 v36; // [rsp+58h] [rbp-D8h]
  __int64 v37; // [rsp+60h] [rbp-D0h]
  int v38; // [rsp+68h] [rbp-C8h]
  __int64 v39; // [rsp+68h] [rbp-C8h]
  int v40; // [rsp+70h] [rbp-C0h]
  __int64 v41; // [rsp+70h] [rbp-C0h]
  int v42; // [rsp+78h] [rbp-B8h]
  __int64 v43; // [rsp+78h] [rbp-B8h]
  int v44; // [rsp+80h] [rbp-B0h]
  __int64 v45; // [rsp+80h] [rbp-B0h]
  int v46; // [rsp+88h] [rbp-A8h]
  __int64 v47; // [rsp+88h] [rbp-A8h]
  int v48; // [rsp+90h] [rbp-A0h]
  __int64 v49; // [rsp+90h] [rbp-A0h]
  int v50; // [rsp+98h] [rbp-98h]
  __int64 v51; // [rsp+98h] [rbp-98h]
  int v52; // [rsp+A0h] [rbp-90h]
  __int64 v53; // [rsp+A0h] [rbp-90h]
  void *v54; // [rsp+B8h] [rbp-78h] BYREF
  size_t v55; // [rsp+C0h] [rbp-70h] BYREF
  STRSAFE_LPWSTR v56; // [rsp+C8h] [rbp-68h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+D0h] [rbp-60h]
  struct _RTL_CRITICAL_SECTION *v58; // [rsp+D8h] [rbp-58h]
  char *v59; // [rsp+E0h] [rbp-50h]
  void **v60; // [rsp+E8h] [rbp-48h] BYREF
  _BYTE v61[96]; // [rsp+F0h] [rbp-40h] BYREF
  FSClientContextInfo *v62; // [rsp+160h] [rbp+30h] BYREF
  unsigned int v63; // [rsp+168h] [rbp+38h] BYREF
  unsigned int v64; // [rsp+170h] [rbp+40h] BYREF
  int v65; // [rsp+178h] [rbp+48h] BYREF

  v62 = this;
  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v3 = this;
  v4 = 0;
  v58 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v64 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v63 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v6 = FSSourceIdentityTrace::FSSourceIdentityTrace((FSSourceIdentityTrace *)&v60, a2);
    String = FSString::GetString((FSSourceIdentityTrace *)((char *)v6 + 8));
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      26,
      (unsigned int)&WPP_9bb944463e3039875071016bf2e24787_Traceguids,
      (_DWORD)v3,
      (__int64)String);
    v4 = 1;
    v64 = 1;
  }
  if ( (v4 & 1) != 0 )
  {
    v64 = v4 & 0xFFFFFFFE;
    v60 = &FSSourceIdentityControlTrace::`vftable';
    FSString::~FSString((FSString *)v61);
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_9bb944463e3039875071016bf2e24787_Traceguids,
        v3,
        -2147024809);
    goto LABEL_45;
  }
  v9 = (*(__int64 (__fastcall **)(struct IFSSourceIdentity *, _QWORD, _QWORD, unsigned int *))(*(_QWORD *)a2 + 328LL))(
         a2,
         0,
         0,
         &v63);
  v8 = v9;
  if ( v9 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_45;
    v10 = 28;
LABEL_44:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v3, v9);
    goto LABEL_45;
  }
  if ( v63 )
  {
    wil::make_unique_nothrow<__MIDL___MIDL_itf_fsclienttypes_0000_0000_0028 [0]>(&v54, v63);
    v11 = (unsigned __int8 *)v54;
    if ( !v54 )
    {
      v9 = -2147024882;
      v8 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_45;
      v10 = 29;
      goto LABEL_44;
    }
    v12 = (*(__int64 (__fastcall **)(struct IFSSourceIdentity *, void *, _QWORD, unsigned int *))(*(_QWORD *)a2 + 328LL))(
            a2,
            v54,
            v63,
            &v63);
    v8 = v12;
    if ( v12 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 30;
LABEL_19:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v3, v12);
        goto LABEL_20;
      }
      goto LABEL_20;
    }
    v15 = 63LL * v63 + 1;
    v16 = CoTaskMemAlloc(2 * v15);
    v17 = v16;
    if ( !v16 )
    {
      v12 = -2147024882;
      v8 = -2147024882;
      if ( g_wppLevels )
      {
        v14 = 31;
        goto LABEL_19;
      }
LABEL_20:
      operator delete(v11, v13);
      goto LABEL_45;
    }
    memset_0(v16, 0, 2 * v15);
    v59 = (char *)v3 + 232;
    v18 = tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
            (char *)v3 + 232,
            &v65);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (void **)(*(_QWORD *)v18 + 288LL),
      v17);
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v65);
    pszDest = *(STRSAFE_LPWSTR *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                                               (char *)v3 + 232,
                                               &v65)
                                + 288LL);
    v56 = pszDest;
    tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v65);
    v19 = v11[11];
    v20 = v11[10];
    v21 = v11[9];
    v22 = v11[8];
    v52 = *((unsigned __int16 *)v11 + 11);
    v50 = *((unsigned __int16 *)v11 + 10);
    v48 = *((unsigned __int16 *)v11 + 9);
    v46 = *((unsigned __int16 *)v11 + 8);
    v44 = v11[15];
    v42 = v11[14];
    v40 = v11[13];
    v55 = v15;
    v38 = v11[12];
    v32 = *((unsigned __int16 *)v11 + 3);
    v11 = (unsigned __int8 *)v54;
    v12 = StringCchPrintfExW(
            pszDest,
            v15,
            &v56,
            &v55,
            0,
            L"{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X},%d.%d.%d.%d",
            *(_DWORD *)v54,
            *((unsigned __int16 *)v54 + 2),
            v32,
            v22,
            v21,
            v20,
            v19,
            v38,
            v40,
            v42,
            v44,
            v46,
            v48,
            v50,
            v52);
    v2 = v58;
    v8 = v12;
    if ( v12 < 0 )
    {
      v3 = v62;
      if ( !g_wppLevels )
        goto LABEL_20;
      v14 = 32;
      goto LABEL_19;
    }
    v23 = 1;
    v65 = 1;
    if ( v63 > 1 )
    {
      while ( 1 )
      {
        LODWORD(v53) = *(unsigned __int16 *)&v11[112 * v23 + 22];
        LODWORD(v51) = *(unsigned __int16 *)&v11[112 * v23 + 20];
        LODWORD(v49) = *(unsigned __int16 *)&v11[112 * v23 + 18];
        LODWORD(v47) = *(unsigned __int16 *)&v11[112 * v23 + 16];
        LODWORD(v45) = v11[112 * v23 + 15];
        LODWORD(v43) = v11[112 * v23 + 14];
        LODWORD(v41) = v11[112 * v23 + 13];
        LODWORD(v39) = v11[112 * v23 + 12];
        LODWORD(v37) = v11[112 * v23 + 11];
        LODWORD(v36) = v11[112 * v23 + 10];
        LODWORD(v35) = v11[112 * v23 + 9];
        LODWORD(v34) = v11[112 * v23 + 8];
        LODWORD(v33) = *(unsigned __int16 *)&v11[112 * v23 + 6];
        v11 = (unsigned __int8 *)v54;
        LODWORD(v31) = *((unsigned __int16 *)v54 + 56 * v23 + 2);
        LODWORD(v30) = *((_DWORD *)v54 + 28 * v23);
        v24 = StringCchPrintfExW(
                v56,
                v55,
                &v56,
                &v55,
                0,
                L";{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X},%d.%d.%d.%d",
                v30,
                v31,
                v33,
                v34,
                v35,
                v36,
                v37,
                v39,
                v41,
                v43,
                v45,
                v47,
                v49,
                v51,
                v53);
        v2 = v58;
        v8 = v24;
        if ( v24 < 0 )
          break;
        v23 = (unsigned int)(v65 + 1);
        v65 = v23;
        if ( (unsigned int)v23 >= v63 )
          goto LABEL_27;
      }
      v3 = v62;
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v62, v24);
      if ( !v11 )
      {
LABEL_45:
        v29 = *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                                       (char *)v3 + 232,
                                       &v62)
                        + 272LL) >> 31;
        tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v62);
        if ( (unsigned __int8)v29 != 1 )
        {
          *(_DWORD *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
                                   (char *)v3 + 232,
                                   &v62)
                    + 272LL) = v8;
          tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v62);
        }
        if ( byte_18010EC4D )
        {
          v27 = 35;
          goto LABEL_40;
        }
        goto LABEL_41;
      }
      goto LABEL_20;
    }
LABEL_27:
    v25 = v64;
    if ( (unsigned __int8)byte_18010EC4D < 8u )
    {
      v3 = v62;
    }
    else
    {
      v25 = v64 | 2;
      v26 = tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(
              v59,
              &v64);
      v3 = v62;
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        34,
        (unsigned int)&WPP_9bb944463e3039875071016bf2e24787_Traceguids,
        (_DWORD)v62,
        *(_QWORD *)(*(_QWORD *)v26 + 288LL));
    }
    if ( (v25 & 2) != 0 )
      tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(&v64);
    if ( v11 )
      operator delete(v11, v13);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v27 = 36;
LABEL_40:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v27, &WPP_9bb944463e3039875071016bf2e24787_Traceguids, v3, v8);
  }
LABEL_41:
  LeaveCriticalSection(v2);
  return v8;
}

```

## disassembly

```asm
0x180078360  mov     [rsp-8+arg_0], rcx
0x180078365  push    rbp
0x180078366  push    rbx
0x180078367  push    rsi
0x180078368  push    rdi
0x180078369  push    r12
0x18007836b  push    r13
0x18007836d  push    r14
0x18007836f  push    r15
0x180078371  lea     rbp, [rsp+18h]
0x180078376  sub     rsp, 118h
0x18007837d  lea     rbx, [rcx+10h]
0x180078381  mov     r14, rcx
0x180078384  xor     edi, edi
0x180078386  mov     [rbp+20h+var_78], rbx
0x18007838a  mov     rcx, rbx; lpCriticalSection
0x18007838d  mov     [rbp+20h+arg_10], edi
0x180078390  mov     r15, rdx
0x180078393  call    cs:__imp_EnterCriticalSection
0x180078399  mov     [rbp+20h+arg_8], edi
0x18007839c  cmp     cs:byte_18010EC4D, 8
0x1800783a3  jb      short loc_1800783E7
0x1800783a5  mov     rdx, r15; struct IFSSourceIdentity *
0x1800783a8  lea     rcx, [rbp+20h+var_68]; this
0x1800783ac  call    ??0FSSourceIdentityTrace@@QEAA@PEAUIFSSourceIdentity@@@Z; FSSourceIdentityTrace::FSSourceIdentityTrace(IFSSourceIdentity *)
0x1800783b1  lea     rcx, [rax+8]; this
0x1800783b5  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x1800783ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1800783c1  lea     edx, [rdi+1Ah]
0x1800783c4  mov     r9, r14
0x1800783c7  mov     qword ptr [rsp+150h+dwFlags], rax
0x1800783cc  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x1800783d3  mov     rcx, [rcx+0D8h]
0x1800783da  call    WPP_SF_qs
0x1800783df  mov     edi, 1
0x1800783e4  mov     [rbp+20h+arg_10], edi
0x1800783e7  test    dil, 1
0x1800783eb  jz      short loc_180078407
0x1800783ed  and     edi, 0FFFFFFFEh
0x1800783f0  lea     rax, ??_7FSSourceIdentityControlTrace@@6B@; const FSSourceIdentityControlTrace::`vftable'
0x1800783f7  mov     [rbp+20h+arg_10], edi
0x1800783fa  lea     rcx, [rbp+20h+var_60]; this
0x1800783fe  mov     [rbp+20h+var_68], rax
0x180078402  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180078407  test    r15, r15
0x18007840a  jnz     short loc_18007842B
0x18007840c  mov     esi, 80070057h
0x180078411  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078418  jb      loc_1800788B6
0x18007841e  lea     edx, [r15+1Bh]
0x180078422  mov     [rsp+150h+dwFlags], esi
0x180078426  jmp     loc_18007889C
0x18007842b  mov     rax, [r15]
0x18007842e  lea     r9, [rbp+20h+arg_8]
0x180078432  xor     r8d, r8d
0x180078435  xor     edx, edx
0x180078437  mov     rcx, r15
0x18007843a  mov     rax, [rax+148h]
0x180078441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078446  mov     esi, eax
0x180078448  test    eax, eax
0x18007844a  jns     short loc_180078463
0x18007844c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078453  jb      loc_1800788B6
0x180078459  mov     edx, 1Ch
0x18007845e  jmp     loc_180078898
0x180078463  mov     eax, [rbp+20h+arg_8]
0x180078466  test    eax, eax
0x180078468  jz      loc_180078835
0x18007846e  mov     edx, eax
0x180078470  lea     rcx, [rbp+20h+var_98]
0x180078474  call    ??$make_unique_nothrow@$$BY0A@U__MIDL___MIDL_itf_fsclienttypes_0000_0000_0028@@@wil@@YA?AV?$unique_ptr@$$BY0A@U__MIDL___MIDL_itf_fsclienttypes_0000_0000_0028@@U?$default_delete@$$BY0A@U__MIDL___MIDL_itf_fsclienttypes_0000_0000_0028@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<__MIDL___MIDL_itf_fsclienttypes_0000_0000_0028 [0]>(unsigned __int64)
0x180078479  mov     r13, [rbp+20h+var_98]
0x18007847d  test    r13, r13
0x180078480  jz      loc_180078883
0x180078486  mov     rax, [r15]
0x180078489  lea     r9, [rbp+20h+arg_8]
0x18007848d  mov     r8d, [rbp+20h+arg_8]
0x180078491  mov     rdx, r13
0x180078494  mov     rcx, r15
0x180078497  mov     rax, [rax+148h]
0x18007849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800784a3  mov     esi, eax
0x1800784a5  test    eax, eax
0x1800784a7  jns     short loc_1800784B9
0x1800784a9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800784b0  jb      short loc_18007850F
0x1800784b2  mov     edx, 1Eh
0x1800784b7  jmp     short loc_1800784F1
0x1800784b9  mov     eax, [rbp+20h+arg_8]
0x1800784bc  imul    rdi, rax, 3Fh ; '?'
0x1800784c0  inc     rdi
0x1800784c3  mov     [rbp+20h+cchDest], rdi
0x1800784c7  lea     r15, [rdi+rdi]
0x1800784cb  mov     rcx, r15; cb
0x1800784ce  call    cs:__imp_CoTaskMemAlloc
0x1800784d4  mov     rsi, rax
0x1800784d7  test    rax, rax
0x1800784da  jnz     short loc_18007851C
0x1800784dc  mov     eax, 8007000Eh
0x1800784e1  mov     esi, eax
0x1800784e3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800784ea  jb      short loc_18007850F
0x1800784ec  mov     edx, 1Fh
0x1800784f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800784f8  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x1800784ff  mov     r9, r14
0x180078502  mov     [rsp+150h+dwFlags], eax
0x180078506  mov     rcx, [rcx+10h]
0x18007850a  call    WPP_SF_qD
0x18007850f  mov     rcx, r13; void *
0x180078512  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180078517  jmp     loc_1800788B6
0x18007851c  mov     r8, r15; Size
0x18007851f  xor     edx, edx; Val
0x180078521  mov     rcx, rsi; void *
0x180078524  call    memset_0
0x180078529  lea     rbx, [r14+0E8h]
0x180078530  mov     rcx, rbx
0x180078533  mov     [rbp+20h+var_70], rbx
0x180078537  lea     rdx, [rbp+20h+arg_18]
0x18007853b  call    ??C?$tip_test@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(void)
0x180078540  mov     rdx, rsi
0x180078543  mov     rcx, [rax]
0x180078546  add     rcx, 120h
0x18007854d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180078552  lea     rcx, [rbp+20h+arg_18]
0x180078556  call    ??1?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(void)
0x18007855b  lea     rdx, [rbp+20h+arg_18]
0x18007855f  mov     rcx, rbx
0x180078562  call    ??C?$tip_test@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(void)
0x180078567  mov     rcx, [rax]
0x18007856a  mov     rax, [rcx+120h]
0x180078571  lea     rcx, [rbp+20h+arg_18]
0x180078575  mov     [rbp+20h+pszDest], rax
0x180078579  mov     [rbp+20h+var_88], rax
0x18007857d  call    ??1?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(void)
0x180078582  movzx   eax, word ptr [r13+16h]
0x180078587  movzx   ecx, word ptr [r13+14h]
0x18007858c  movzx   edx, word ptr [r13+12h]
0x180078591  movzx   r8d, word ptr [r13+10h]
0x180078596  movzx   r9d, byte ptr [r13+0Fh]
0x18007859b  movzx   r10d, byte ptr [r13+0Eh]
0x1800785a0  movzx   r11d, byte ptr [r13+0Dh]
0x1800785a5  movzx   esi, byte ptr [r13+0Bh]
0x1800785aa  movzx   r14d, byte ptr [r13+0Ah]
0x1800785af  movzx   r15d, byte ptr [r13+9]
0x1800785b4  movzx   r12d, byte ptr [r13+8]
0x1800785b9  mov     [rsp+150h+var_B0], eax
0x1800785c0  mov     dword ptr [rsp+150h+var_B8], ecx
0x1800785c7  mov     rcx, [rbp+20h+pszDest]; pszDest
0x1800785cb  mov     dword ptr [rsp+150h+var_C0], edx
0x1800785d2  mov     rdx, [rbp+20h+cchDest]; cchDest
0x1800785d6  mov     dword ptr [rsp+150h+var_C8], r8d
0x1800785de  lea     r8, [rbp+20h+var_88]; unsigned __int16 **
0x1800785e2  mov     dword ptr [rsp+150h+var_D0], r9d
0x1800785ea  lea     r9, [rbp+20h+var_90]; unsigned __int64 *
0x1800785ee  mov     dword ptr [rsp+150h+var_D8], r10d
0x1800785f3  mov     dword ptr [rsp+150h+var_E0], r11d
0x1800785f8  mov     [rbp+20h+var_90], rdi
0x1800785fc  movzx   edi, byte ptr [r13+0Ch]
0x180078601  movzx   r13d, word ptr [r13+6]
0x180078606  mov     dword ptr [rsp+150h+var_E8], edi
0x18007860a  mov     dword ptr [rsp+150h+var_F0], esi
0x18007860e  mov     dword ptr [rsp+150h+var_F8], r14d
0x180078613  mov     dword ptr [rsp+150h+var_100], r15d
0x180078618  mov     dword ptr [rsp+150h+var_108], r12d
0x18007861d  mov     dword ptr [rsp+150h+var_110], r13d
0x180078622  mov     r13, [rbp+20h+var_98]
0x180078626  movzx   eax, word ptr [r13+4]
0x18007862b  mov     dword ptr [rsp+150h+var_118], eax
0x18007862f  mov     eax, [r13+0]
0x180078633  mov     dword ptr [rsp+150h+var_120], eax
0x180078637  lea     rax, a08lx04x04x02x0; "{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%"...
0x18007863e  mov     [rsp+150h+var_128], rax; unsigned __int16 *
0x180078643  mov     qword ptr [rsp+150h+dwFlags], 0; dwFlags
0x18007864c  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180078651  mov     rbx, [rbp+20h+var_78]
0x180078655  mov     esi, eax
0x180078657  test    eax, eax
0x180078659  jns     short loc_180078676
0x18007865b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180078662  mov     r14, [rbp+20h+arg_0]
0x180078666  jb      loc_18007850F
0x18007866c  mov     edx, 20h ; ' '
0x180078671  jmp     loc_1800784F1
0x180078676  cmp     [rbp+20h+arg_8], 1
0x18007867a  mov     eax, 1
0x18007867f  mov     [rbp+20h+arg_18], eax
0x180078682  jbe     loc_180078780
0x180078688  imul    rbx, rax, 70h ; 'p'
0x18007868c  movzx   eax, word ptr [rbx+r13+16h]
0x180078692  movzx   ecx, word ptr [rbx+r13+14h]
0x180078698  movzx   edx, word ptr [rbx+r13+12h]
0x18007869e  movzx   r8d, word ptr [rbx+r13+10h]
0x1800786a4  movzx   r9d, byte ptr [rbx+r13+0Fh]
0x1800786aa  movzx   r10d, byte ptr [rbx+r13+0Eh]
0x1800786b0  movzx   r11d, byte ptr [rbx+r13+0Dh]
0x1800786b6  movzx   edi, byte ptr [rbx+r13+0Ch]
0x1800786bc  movzx   esi, byte ptr [rbx+r13+0Bh]
0x1800786c2  movzx   r14d, byte ptr [rbx+r13+0Ah]
0x1800786c8  movzx   r15d, byte ptr [rbx+r13+9]
0x1800786ce  movzx   r12d, byte ptr [rbx+r13+8]
0x1800786d4  movzx   r13d, word ptr [rbx+r13+6]
0x1800786da  mov     [rsp+150h+var_B0], eax
0x1800786e1  mov     dword ptr [rsp+150h+var_B8], ecx
0x1800786e8  mov     rcx, [rbp+20h+var_88]; pszDest
0x1800786ec  mov     dword ptr [rsp+150h+var_C0], edx
0x1800786f3  mov     rdx, [rbp+20h+var_90]; cchDest
0x1800786f7  mov     dword ptr [rsp+150h+var_C8], r8d
0x1800786ff  lea     r8, [rbp+20h+var_88]; unsigned __int16 **
0x180078703  mov     dword ptr [rsp+150h+var_D0], r9d
0x18007870b  lea     r9, [rbp+20h+var_90]; unsigned __int64 *
0x18007870f  mov     dword ptr [rsp+150h+var_D8], r10d
0x180078714  mov     dword ptr [rsp+150h+var_E0], r11d
0x180078719  mov     dword ptr [rsp+150h+var_E8], edi
0x18007871d  mov     dword ptr [rsp+150h+var_F0], esi
0x180078721  mov     dword ptr [rsp+150h+var_F8], r14d
0x180078726  mov     dword ptr [rsp+150h+var_100], r15d
0x18007872b  mov     dword ptr [rsp+150h+var_108], r12d
0x180078730  mov     dword ptr [rsp+150h+var_110], r13d
0x180078735  mov     r13, [rbp+20h+var_98]
0x180078739  movzx   eax, word ptr [rbx+r13+4]
0x18007873f  mov     dword ptr [rsp+150h+var_118], eax
0x180078743  mov     eax, [rbx+r13]
0x180078747  mov     dword ptr [rsp+150h+var_120], eax
0x18007874b  lea     rax, a08lx04x04x02x0_2; ";{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X"...
0x180078752  mov     [rsp+150h+var_128], rax; unsigned __int16 *
0x180078757  mov     qword ptr [rsp+150h+dwFlags], 0; dwFlags
0x180078760  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180078765  mov     rbx, [rbp+20h+var_78]
0x180078769  mov     esi, eax
0x18007876b  test    eax, eax
0x18007876d  js      short loc_1800787D7
0x18007876f  mov     eax, [rbp+20h+arg_18]
0x180078772  inc     eax
0x180078774  mov     [rbp+20h+arg_18], eax
0x180078777  cmp     eax, [rbp+20h+arg_8]
0x18007877a  jb      loc_180078688
0x180078780  cmp     cs:byte_18010EC4D, 8
0x180078787  mov     edi, [rbp+20h+arg_10]
0x18007878a  jb      loc_180078815
0x180078790  mov     rcx, [rbp+20h+var_70]
0x180078794  lea     rdx, [rbp+20h+arg_10]
0x180078798  or      edi, 2
0x18007879b  call    ??C?$tip_test@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::operator->(void)
0x1800787a0  mov     r14, [rbp+20h+arg_0]
0x1800787a4  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x1800787ab  mov     edx, 22h ; '"'
0x1800787b0  mov     r9, r14
0x1800787b3  mov     rcx, [rax]
0x1800787b6  mov     rax, [rcx+120h]
0x1800787bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787c4  mov     qword ptr [rsp+150h+dwFlags], rax
0x1800787c9  mov     rcx, [rcx+0D8h]
0x1800787d0  call    WPP_SF_qS
0x1800787d5  jmp     short loc_180078819
0x1800787d7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800787de  mov     r14, [rbp+20h+arg_0]
0x1800787e2  jb      short loc_180078807
0x1800787e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800787eb  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x1800787f2  mov     edx, 21h ; '!'
0x1800787f7  mov     [rsp+150h+dwFlags], eax
0x1800787fb  mov     r9, r14
0x1800787fe  mov     rcx, [rcx+10h]
0x180078802  call    WPP_SF_qD
0x180078807  test    r13, r13
0x18007880a  jz      loc_1800788B6
0x180078810  jmp     loc_18007850F
0x180078815  mov     r14, [rbp+20h+arg_0]
0x180078819  test    dil, 2
0x18007881d  jz      short loc_180078828
0x18007881f  lea     rcx, [rbp+20h+arg_10]
0x180078823  call    ??1?$test_data_control@V?$merged_data@U_tip_FSClientContextManagedCameraTip@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>::~test_data_control<tip2::details::merged_data<_tip_FSClientContextManagedCameraTip,_tip_FSClientContextManagedCameraTip>>(void)
0x180078828  test    r13, r13
0x18007882b  jz      short loc_180078835
0x18007882d  mov     rcx, r13; void *
0x180078830  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180078835  cmp     cs:byte_18010EC4D, 8
0x18007883c  jb      short loc_180078864
0x18007883e  mov     edx, 24h ; '$'
0x180078843  mov     rcx, cs:WPP_GLOBAL_Control
0x18007884a  lea     r8, WPP_9bb944463e3039875071016bf2e24787_Traceguids
0x180078851  mov     r9, r14
0x180078854  mov     [rsp+150h+dwFlags], esi
0x180078858  mov     rcx, [rcx+0D8h]
0x18007885f  call    WPP_SF_qD
0x180078864  mov     rcx, rbx; lpCriticalSection
0x180078867  call    cs:__imp_LeaveCriticalSection
0x18007886d  mov     eax, esi
0x18007886f  add     rsp, 118h
0x180078876  pop     r15
0x180078878  pop     r14
0x18007887a  pop     r13
0x18007887c  pop     r12
0x18007887e  pop     rdi
0x18007887f  pop     rsi
0x180078880  pop     rbx
0x180078881  pop     rbp
  ... truncated ...
```
