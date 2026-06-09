# FSMConfigurationsManager::CleanupWSEOptInState(unsigned __int64)

- ea: `0x180027d90`
- end: `0x1800285b7`
- name: `?CleanupWSEOptInState@FSMConfigurationsManager@@UEAAJ_K@Z`
- size: `2087`
- prototype: `__int64 __fastcall(FSMConfigurationsManager *this, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x18000d154`
- `0x18000d4f8`
- `0x18000d538`
- `0x18000e66c`
- `0x180017b70`
- `0x180027d90`
- `0x1800291f0`
- `0x180029290`
- `0x18003a2d8`
- `0x180040004`
- `0x1800403e4`
- `0x180040ef8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027dc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002858f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002858f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002844f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002844f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800284e6`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800281bb`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x1800281bb`

## string_xrefs

- `0x180028260`: `<empty_config>`

## pseudocode

```c
__int64 __fastcall FSMConfigurationsManager::CleanupWSEOptInState(FSMConfigurationsManager *this, __int64 a2)
{
  int v4; // esi
  int v5; // eax
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 **i; // rbx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(FSMConfigurationsManager *, _QWORD *, __int64 **); // rbx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  int v18; // ebx
  unsigned __int64 v19; // r13
  __int64 v20; // r15
  __int64 v21; // rax
  int v22; // eax
  unsigned int v23; // r12d
  int v24; // edx
  int v25; // r8d
  __int64 v26; // rsi
  __int64 (__fastcall *v27)(__int64, _QWORD, __int64 **); // rbx
  int v28; // eax
  __int64 v29; // rbx
  __int64 v30; // rdx
  char v31; // al
  __int64 v32; // rcx
  const wchar_t *v33; // rax
  unsigned int v34; // r12d
  unsigned int v35; // r15d
  __int64 v36; // rsi
  __int64 (__fastcall *v37)(__int64, _QWORD, __int64 **); // rbx
  int v38; // eax
  int v39; // esi
  __int64 v40; // rax
  char v41; // bl
  int v42; // eax
  int v43; // r8d
  const wchar_t *v44; // rax
  void *v45; // rcx
  __int64 v46; // rdx
  void *v47; // rcx
  __int64 *v49; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v50; // [rsp+48h] [rbp-91h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-89h] BYREF
  unsigned int v52; // [rsp+58h] [rbp-81h]
  unsigned int v53; // [rsp+5Ch] [rbp-7Dh] BYREF
  __int64 v54; // [rsp+60h] [rbp-79h] BYREF
  __int64 *v55; // [rsp+68h] [rbp-71h] BYREF
  __int64 v56; // [rsp+70h] [rbp-69h] BYREF
  int v57; // [rsp+78h] [rbp-61h]
  unsigned __int64 v58; // [rsp+80h] [rbp-59h]
  __int64 *v59; // [rsp+88h] [rbp-51h] BYREF
  unsigned int v60; // [rsp+90h] [rbp-49h]
  _QWORD v61[2]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v62; // [rsp+A8h] [rbp-31h]
  _QWORD v63[3]; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v64; // [rsp+C8h] [rbp-11h] BYREF
  unsigned __int64 v65; // [rsp+D8h] [rbp-1h]

  v52 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  v62 = 0;
  v61[0] = v61;
  v4 = 0;
  v63[2] = 0;
  v61[1] = v61;
  v63[0] = v63;
  v63[1] = v63;
  v55 = 0;
  v5 = FSGetMEPOptInSupport();
  *((_DWORD *)this + 13) = v5;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qDq(*((_QWORD *)WPP_GLOBAL_Control + 27), 15, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v5, a2);
  if ( !*((_DWORD *)this + 13) || (a2 & 0x303) == 0x100 && *((_QWORD *)this + 7) )
    goto LABEL_101;
  v7 = FSEnumDeviceInterfaces(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v6, v61);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_48;
    v9 = 16;
    goto LABEL_9;
  }
  v7 = FSEnumDeviceInterfaces(&GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196, v8, v63);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_48;
    v9 = 17;
    goto LABEL_9;
  }
  for ( i = (__int64 **)v63[0]; i != v63; i = (__int64 **)*i )
  {
    v50 = 0;
    v11 = (const unsigned __int16 *)i[2];
    v53 = 0;
    if ( FSGetAliasDeviceName2(1, v11, &GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196, 0, 0, &v50) >= 0
      && v50 > 1
      && FSGetAliasDeviceName2(
           1,
           (const unsigned __int16 *)i[2],
           &GUID_e5323777_f976_4f5b_9b55_b94699c46e44,
           0,
           0,
           &v53) < 0
      && !(unsigned __int8)utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
                             v61,
                             i + 2) )
    {
      v4 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids,
          this,
          -2147024882);
      goto LABEL_48;
    }
  }
  if ( !v62 )
  {
LABEL_101:
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      v30 = 29;
LABEL_103:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v30, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v4);
    }
    goto LABEL_104;
  }
  v12 = (__int64)v55;
  v13 = *(_QWORD *)this;
  v55 = 0;
  v14 = *(__int64 (__fastcall **)(FSMConfigurationsManager *, _QWORD *, __int64 **))(v13 + 48);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v7 = v14(this, v61, &v55);
  v4 = v7;
  if ( v7 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_48;
    v9 = 19;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v7);
    goto LABEL_48;
  }
  v15 = (*(__int64 (__fastcall **)(__int64 *))(*v55 + 24))(v55);
  v16 = v15;
  v60 = v15;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 20, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v15);
  v17 = 0;
  v53 = 0;
  if ( !v16 )
  {
LABEL_47:
    GetSystemTimePreciseAsFileTime((char *)this + 56);
    if ( v4 < 0 )
      goto LABEL_48;
    goto LABEL_101;
  }
  while ( 1 )
  {
    v54 = 0;
    v18 = -1;
    v19 = 0;
    v57 = -1;
    v20 = 0;
    v58 = 0;
    v21 = *v55;
    v59 = 0;
    v22 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v21 + 32))(v55, v17, &v54);
    v4 = v22;
    if ( v22 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v22);
      goto LABEL_100;
    }
    v23 = 0;
    LODWORD(pv) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v54 + 24LL))(v54);
    if ( (_DWORD)pv )
    {
      do
      {
        v26 = v54;
        v49 = 0;
        v65 = 0;
        v64 = 0;
        v50 = 0;
        v27 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v54 + 32LL);
        wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v49);
        v28 = v27(v26, v23, &v49);
        v4 = v28;
        if ( v28 < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids,
              this,
              v28);
          goto LABEL_90;
        }
        if ( (*(int (__fastcall **)(__int64 *, __int64 *, __int128 *, __int64, unsigned int *))(*v49 + 120))(
               v49,
               FSM_WSEOPTIN_CONFIGURATION_INFO,
               &v64,
               24,
               &v50) >= 0
          && v50 == 24
          && v65 > v19 )
        {
          v19 = v65;
          v29 = v20;
          v20 = (__int64)v49;
          v57 = v23;
          v58 = v65;
          v59 = v49;
          if ( v49 )
            (*(void (__fastcall **)(__int64 *))(*v49 + 8))(v49);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v49);
        ++v23;
      }
      while ( v23 < (unsigned int)pv );
      v18 = v57;
    }
    if ( v18 != -1 )
      break;
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 23, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this);
LABEL_46:
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v59);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v54);
    v17 = v53 + 1;
    v53 = v17;
    if ( (unsigned int)v17 >= v60 )
      goto LABEL_47;
  }
  v31 = byte_18005E5A5;
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
  {
    v32 = 0;
    v49 = 0;
    if ( v20 )
    {
      (*(void (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v20 + 272LL))(v20, &v49);
      v31 = byte_18005E5A5;
      v32 = (__int64)v49;
    }
    if ( (unsigned __int8)v31 >= 8u )
    {
      if ( v20 )
      {
        if ( v32 )
        {
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 56LL))(v32) )
            v33 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64 *))(*v49 + 56))(v49);
          else
            v33 = (const wchar_t *)L"<nullptr>";
        }
        else
        {
          v33 = L"<empty_key>";
        }
      }
      else
      {
        v33 = L"<empty_config>";
      }
      WPP_SF_qdiS(*((_QWORD *)WPP_GLOBAL_Control + 27), v24, v25, (_DWORD)this, v18, v19, (__int64)v33);
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v49);
  }
  v34 = (unsigned int)pv;
  v35 = 0;
  if ( !(_DWORD)pv )
    goto LABEL_46;
  while ( 1 )
  {
    v49 = 0;
    pv = 0;
    v50 = 0;
    if ( v35 == v18 )
      goto LABEL_86;
    v36 = v54;
    v37 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v54 + 32LL);
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v49);
    v38 = v37(v36, v35, &v49);
    v39 = v52;
    if ( v38 < 0
      || (v39 = v52 | 1,
          v52 |= 1u,
          v40 = *v49,
          *(_QWORD *)&v64 = &pv,
          *((_QWORD *)&v64 + 1) = 0,
          LOBYTE(v65) = 1,
          (*(int (__fastcall **)(__int64 *, __int64 *, char *, unsigned int *))(v40 + 128))(
            v49,
            FSM_WSEOPTIN_CONFIGURATION_INFO,
            (char *)&v64 + 8,
            &v50) < 0)
      || (v41 = 1, v50 < 0x18) )
    {
      v41 = 0;
    }
    if ( (v39 & 1) != 0 )
    {
      v52 = v39 & 0xFFFFFFFE;
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&v64);
    }
    if ( v41 )
    {
      *((_QWORD *)pv + 1) |= 2uLL;
      v42 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, LPVOID, _QWORD))(*v49 + 208))(
              v49,
              FSM_WSEOPTIN_CONFIGURATION_INFO,
              pv,
              v50);
      v4 = v42;
      if ( v42 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_94;
        v46 = 25;
        goto LABEL_93;
      }
    }
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      v56 = 0;
      (*(void (__fastcall **)(__int64 *, __int64 *))(*v49 + 272))(v49, &v56);
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        if ( v56 )
        {
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 56LL))(v56) )
            v44 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v56 + 56LL))(v56);
          else
            v44 = (const wchar_t *)L"<nullptr>";
        }
        else
        {
          v44 = L"<empty_key>";
        }
        WPP_SF_qdS(*((_QWORD *)WPP_GLOBAL_Control + 27), 26, v43, (_DWORD)this, v35, (__int64)v44);
      }
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v56);
    }
    v42 = FSMSavePublicDeviceConfiguration(v49);
    v4 = v42;
    if ( v42 < 0 )
      break;
    v45 = pv;
    pv = 0;
    if ( v45 )
      CoTaskMemFree(v45);
    v18 = v57;
LABEL_86:
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v49);
    if ( ++v35 >= v34 )
      goto LABEL_46;
  }
  if ( g_wppLevels )
  {
    v46 = 27;
LABEL_93:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v46, &WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids, this, v42);
  }
LABEL_94:
  v47 = pv;
  pv = 0;
  if ( v47 )
    CoTaskMemFree(v47);
LABEL_90:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v49);
LABEL_100:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v59);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v54);
LABEL_48:
  if ( byte_18005E5A5 )
  {
    v30 = 28;
    goto LABEL_103;
  }
LABEL_104:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v55);
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v63);
  utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::clear(v61);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027d90  push    rbp
0x180027d92  push    rbx
0x180027d93  push    rsi
0x180027d94  push    rdi
0x180027d95  push    r12
0x180027d97  push    r13
0x180027d99  push    r14
0x180027d9b  push    r15
0x180027d9d  lea     rbp, [rsp-1Fh]
0x180027da2  sub     rsp, 0F8h
0x180027da9  mov     rax, cs:__security_cookie
0x180027db0  xor     rax, rsp
0x180027db3  mov     [rbp+57h+var_50], rax
0x180027db7  mov     r14, rcx
0x180027dba  xor     r13d, r13d
0x180027dbd  add     rcx, 8; lpCriticalSection
0x180027dc1  mov     [rsp+130h+var_D8], r13d
0x180027dc6  mov     rbx, rdx
0x180027dc9  call    cs:__imp_EnterCriticalSection
0x180027dcf  lea     rax, [rbp+57h+var_98]
0x180027dd3  mov     [rbp+57h+var_88], r13
0x180027dd7  mov     [rbp+57h+var_98], rax
0x180027ddb  mov     esi, r13d
0x180027dde  lea     rax, [rbp+57h+var_98]
0x180027de2  mov     [rbp+57h+var_70], r13
0x180027de6  mov     [rbp+57h+var_90], rax
0x180027dea  lea     rax, [rbp+57h+var_80]
0x180027dee  mov     [rbp+57h+var_80], rax
0x180027df2  lea     rax, [rbp+57h+var_80]
0x180027df6  mov     [rbp+57h+var_78], rax
0x180027dfa  mov     [rbp+57h+var_C8], r13
0x180027dfe  call    ?FSGetMEPOptInSupport@@YAJXZ; FSGetMEPOptInSupport(void)
0x180027e03  mov     [r14+34h], eax
0x180027e07  cmp     cs:byte_18005E5A5, 8
0x180027e0e  jb      short loc_180027E3A
0x180027e10  mov     rcx, cs:WPP_GLOBAL_Control
0x180027e17  lea     edx, [r13+0Fh]
0x180027e1b  mov     [rsp+130h+var_108], rbx
0x180027e20  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180027e27  mov     r9, r14
0x180027e2a  mov     [rsp+130h+var_110], eax
0x180027e2e  mov     rcx, [rcx+0D8h]
0x180027e35  call    WPP_SF_qDq
0x180027e3a  cmp     [r14+34h], r13d
0x180027e3e  jz      loc_180028541
0x180027e44  and     ebx, 303h
0x180027e4a  cmp     rbx, 100h
0x180027e51  jnz     short loc_180027E5D
0x180027e53  cmp     [r14+38h], r13
0x180027e57  jnz     loc_180028541
0x180027e5d  lea     r8, [rbp+57h+var_98]
0x180027e61  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x180027e68  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180027e6d  mov     esi, eax
0x180027e6f  test    eax, eax
0x180027e71  jns     short loc_180027E8E
0x180027e73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027e7a  jb      loc_1800281C9
0x180027e80  mov     edx, 10h
0x180027e85  mov     [rsp+130h+var_110], eax
0x180027e89  jmp     loc_180027F5D
0x180027e8e  lea     r8, [rbp+57h+var_80]
0x180027e92  lea     rcx, _GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196
0x180027e99  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180027e9e  mov     esi, eax
0x180027ea0  test    eax, eax
0x180027ea2  jns     short loc_180027EB8
0x180027ea4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027eab  jb      loc_1800281C9
0x180027eb1  mov     edx, 11h
0x180027eb6  jmp     short loc_180027E85
0x180027eb8  mov     rbx, [rbp+57h+var_80]
0x180027ebc  lea     rax, [rbp+57h+var_80]
0x180027ec0  cmp     rbx, rax
0x180027ec3  jz      loc_180027F7C
0x180027ec9  lea     rax, [rsp+130h+var_E8]
0x180027ece  mov     [rsp+130h+var_E8], r13d
0x180027ed3  mov     [rsp+130h+var_108], rax; unsigned int *
0x180027ed8  lea     r15, [rbx+10h]
0x180027edc  mov     rdx, [r15]; unsigned __int16 *
0x180027edf  lea     r8, _GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196; struct _GUID *
0x180027ee6  xor     r9d, r9d; unsigned __int16 *
0x180027ee9  mov     [rsp+130h+var_110], r13d; unsigned int
0x180027eee  mov     cl, 1; bool
0x180027ef0  mov     [rbp+57h+var_D4], r13d
0x180027ef4  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x180027ef9  test    eax, eax
0x180027efb  js      short loc_180027F3A
0x180027efd  cmp     [rsp+130h+var_E8], 1
0x180027f02  jbe     short loc_180027F3A
0x180027f04  mov     rdx, [r15]; unsigned __int16 *
0x180027f07  lea     rax, [rbp+57h+var_D4]
0x180027f0b  mov     [rsp+130h+var_108], rax; unsigned int *
0x180027f10  lea     r8, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44; struct _GUID *
0x180027f17  xor     r9d, r9d; unsigned __int16 *
0x180027f1a  mov     [rsp+130h+var_110], r13d; unsigned int
0x180027f1f  mov     cl, 1; bool
0x180027f21  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x180027f26  test    eax, eax
0x180027f28  jns     short loc_180027F3A
0x180027f2a  mov     rdx, r15
0x180027f2d  lea     rcx, [rbp+57h+var_98]
0x180027f31  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180027f36  test    al, al
0x180027f38  jz      short loc_180027F42
0x180027f3a  mov     rbx, [rbx]
0x180027f3d  jmp     loc_180027EBC
0x180027f42  mov     esi, 8007000Eh
0x180027f47  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027f4e  jb      loc_1800281C9
0x180027f54  mov     edx, 12h
0x180027f59  mov     [rsp+130h+var_110], esi
0x180027f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180027f64  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180027f6b  mov     r9, r14
0x180027f6e  mov     rcx, [rcx+10h]
0x180027f72  call    WPP_SF_qD
0x180027f77  jmp     loc_1800281C9
0x180027f7c  cmp     [rbp+57h+var_88], r13
0x180027f80  jz      loc_180028541
0x180027f86  mov     rcx, [rbp+57h+var_C8]
0x180027f8a  mov     rax, [r14]
0x180027f8d  mov     [rbp+57h+var_C8], r13
0x180027f91  mov     rbx, [rax+30h]
0x180027f95  test    rcx, rcx
0x180027f98  jz      short loc_180027FA6
0x180027f9a  mov     rdx, [rcx]
0x180027f9d  mov     rax, [rdx+10h]
0x180027fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fa6  lea     r8, [rbp+57h+var_C8]
0x180027faa  mov     rcx, r14
0x180027fad  lea     rdx, [rbp+57h+var_98]
0x180027fb1  mov     rax, rbx
0x180027fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fb9  mov     esi, eax
0x180027fbb  test    eax, eax
0x180027fbd  jns     short loc_180027FD6
0x180027fbf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180027fc6  jb      loc_1800281C9
0x180027fcc  mov     edx, 13h
0x180027fd1  jmp     loc_180027E85
0x180027fd6  mov     rcx, [rbp+57h+var_C8]
0x180027fda  mov     rax, [rcx]
0x180027fdd  mov     rax, [rax+18h]
0x180027fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fe6  mov     ebx, eax
0x180027fe8  mov     [rbp+57h+var_A0], eax
0x180027feb  cmp     cs:byte_18005E5A5, 8
0x180027ff2  jb      short loc_18002801A
0x180027ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180027ffb  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x180028002  mov     edx, 14h
0x180028007  mov     [rsp+130h+var_110], eax
0x18002800b  mov     r9, r14
0x18002800e  mov     rcx, [rcx+0D8h]
0x180028015  call    WPP_SF_qD
0x18002801a  mov     edx, r13d
0x18002801d  mov     [rbp+57h+var_D4], edx
0x180028020  test    ebx, ebx
0x180028022  jz      loc_1800281B7
0x180028028  mov     rcx, [rbp+57h+var_C8]
0x18002802c  lea     r8, [rbp+57h+var_D0]
0x180028030  mov     [rbp+57h+var_D0], r13
0x180028034  or      ebx, 0FFFFFFFFh
0x180028037  xor     r13d, r13d
0x18002803a  mov     [rbp+57h+var_B8], ebx
0x18002803d  xor     r15d, r15d
0x180028040  mov     [rbp+57h+var_B0], r13
0x180028044  mov     rax, [rcx]
0x180028047  mov     [rbp+57h+var_A8], r15
0x18002804b  mov     rax, [rax+20h]
0x18002804f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028054  mov     esi, eax
0x180028056  test    eax, eax
0x180028058  js      loc_1800284FE
0x18002805e  mov     rcx, [rbp+57h+var_D0]
0x180028062  mov     rax, [rcx]
0x180028065  mov     rax, [rax+18h]
0x180028069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002806e  xor     r12d, r12d
0x180028071  mov     dword ptr [rsp+130h+pv], eax
0x180028075  test    eax, eax
0x180028077  jz      loc_180028161
0x18002807d  mov     rsi, [rbp+57h+var_D0]
0x180028081  lea     rcx, [rsp+130h+var_F0]
0x180028086  xor     eax, eax
0x180028088  mov     [rsp+130h+var_F0], 0
0x180028091  xorps   xmm0, xmm0
0x180028094  mov     [rbp+57h+var_58], rax
0x180028098  movups  [rbp+57h+var_68], xmm0
0x18002809c  mov     [rsp+130h+var_E8], eax
0x1800280a0  mov     rax, [rsi]
0x1800280a3  mov     rbx, [rax+20h]
0x1800280a7  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x1800280ac  lea     r8, [rsp+130h+var_F0]
0x1800280b1  mov     edx, r12d
0x1800280b4  mov     rcx, rsi
0x1800280b7  mov     rax, rbx
0x1800280ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280bf  mov     esi, eax
0x1800280c1  test    eax, eax
0x1800280c3  js      loc_180028473
0x1800280c9  mov     rcx, [rsp+130h+var_F0]
0x1800280ce  lea     rdx, [rsp+130h+var_E8]
0x1800280d3  mov     qword ptr [rsp+130h+var_110], rdx
0x1800280d8  lea     r8, [rbp+57h+var_68]
0x1800280dc  mov     r9d, 18h
0x1800280e2  lea     rdx, FSM_WSEOPTIN_CONFIGURATION_INFO
0x1800280e9  mov     rax, [rcx]
0x1800280ec  mov     rax, [rax+78h]
0x1800280f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280f5  test    eax, eax
0x1800280f7  js      short loc_180028146
0x1800280f9  cmp     [rsp+130h+var_E8], 18h
0x1800280fe  jnz     short loc_180028146
0x180028100  cmp     [rbp+57h+var_58], r13
0x180028104  jbe     short loc_180028146
0x180028106  mov     r13, [rbp+57h+var_58]
0x18002810a  mov     rbx, r15
0x18002810d  mov     r15, [rsp+130h+var_F0]
0x180028112  mov     [rbp+57h+var_B8], r12d
0x180028116  mov     [rbp+57h+var_B0], r13
0x18002811a  mov     [rbp+57h+var_A8], r15
0x18002811e  test    r15, r15
0x180028121  jz      short loc_180028132
0x180028123  mov     rax, [r15]
0x180028126  mov     rcx, r15
0x180028129  mov     rax, [rax+8]
0x18002812d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028132  test    rbx, rbx
0x180028135  jz      short loc_180028146
0x180028137  mov     rax, [rbx]
0x18002813a  mov     rcx, rbx
0x18002813d  mov     rax, [rax+10h]
0x180028141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028146  lea     rcx, [rsp+130h+var_F0]
0x18002814b  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180028150  inc     r12d
0x180028153  cmp     r12d, dword ptr [rsp+130h+pv]
0x180028158  jb      loc_18002807D
0x18002815e  mov     ebx, [rbp+57h+var_B8]
0x180028161  cmp     ebx, 0FFFFFFFFh
0x180028164  jnz     short loc_1800281E0
0x180028166  cmp     cs:byte_18005E5A5, 8
0x18002816d  jb      short loc_180028191
0x18002816f  mov     rcx, cs:WPP_GLOBAL_Control
0x180028176  lea     r8, WPP_a34380bbb6b43d25e2b3a85add1dbda1_Traceguids
0x18002817d  mov     edx, 17h
0x180028182  mov     r9, r14
0x180028185  mov     rcx, [rcx+0D8h]
0x18002818c  call    WPP_SF_q
0x180028191  xor     r13d, r13d
0x180028194  lea     rcx, [rbp+57h+var_A8]
0x180028198  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x18002819d  lea     rcx, [rbp+57h+var_D0]
0x1800281a1  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800281a6  mov     edx, [rbp+57h+var_D4]
0x1800281a9  inc     edx
0x1800281ab  mov     [rbp+57h+var_D4], edx
0x1800281ae  cmp     edx, [rbp+57h+var_A0]
0x1800281b1  jb      loc_180028028
0x1800281b7  lea     rcx, [r14+38h]
0x1800281bb  call    cs:__imp_GetSystemTimePreciseAsFileTime
0x1800281c1  test    esi, esi
0x1800281c3  jns     loc_180028541
0x1800281c9  cmp     cs:byte_18005E5A5, 1
0x1800281d0  jb      loc_180028570
0x1800281d6  mov     edx, 1Ch
0x1800281db  jmp     loc_18002854F
0x1800281e0  mov     al, cs:byte_18005E5A5
0x1800281e6  cmp     al, 10h
0x1800281e8  jb      loc_180028295
0x1800281ee  xor     ecx, ecx
0x1800281f0  mov     [rsp+130h+var_F0], rcx
0x1800281f5  test    r15, r15
0x1800281f8  jz      short loc_18002821C
0x1800281fa  mov     rax, [r15]
0x1800281fd  lea     rdx, [rsp+130h+var_F0]
0x180028202  mov     rcx, r15
0x180028205  mov     rax, [rax+110h]
0x18002820c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028211  mov     al, cs:byte_18005E5A5
0x180028217  mov     rcx, [rsp+130h+var_F0]
0x18002821c  cmp     al, 8
0x18002821e  jb      short loc_18002828B
0x180028220  test    r15, r15
0x180028223  jz      short loc_180028260
0x180028225  test    rcx, rcx
0x180028228  jz      short loc_180028257
0x18002822a  mov     rax, [rcx]
0x18002822d  mov     rax, [rax+38h]
0x180028231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028236  test    rax, rax
0x180028239  jz      short loc_18002824E
0x18002823b  mov     rcx, [rsp+130h+var_F0]
0x180028240  mov     rax, [rcx]
0x180028243  mov     rax, [rax+38h]
0x180028247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002824c  jmp     short loc_180028267
0x18002824e  lea     rax, aNullptr; "<nullptr>"
  ... truncated ...
```
