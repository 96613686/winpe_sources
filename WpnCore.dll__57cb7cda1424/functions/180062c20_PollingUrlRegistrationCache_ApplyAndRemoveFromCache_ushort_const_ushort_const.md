# PollingUrlRegistrationCache::ApplyAndRemoveFromCache(ushort const *,ushort const *)

- ea: `0x180062c20`
- end: `0x180063338`
- name: `?ApplyAndRemoveFromCache@PollingUrlRegistrationCache@@QEAAJPEBG0@Z`
- size: `1816`
- prototype: `__int64 __fastcall(PollingUrlRegistrationCache *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004ae04`

## callees

- `0x180004e38`
- `0x18002ee38`
- `0x18002f224`
- `0x180062c20`
- `0x1800a1308`
- `0x1800af0a4`
- `0x1800df41c`
- `0x1800f581c`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062c83`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180062c83`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800632c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180062cb6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800632c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062c66`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180062c66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800632a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800632a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800632b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800632b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006326b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063290`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063258`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006326b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180063290`

## string_xrefs

- `0x180062cdb`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062d66`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062de5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062e48`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062ee5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062f5b`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180062fb1`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180063018`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x18006307f`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x1800630e6`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x180063150`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`
- `0x1800631ea`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\pollingurlregistrationcache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall PollingUrlRegistrationCache::ApplyAndRemoveFromCache(
        RTL_SRWLOCK *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  RTL_SRWLOCK *v6; // rdi
  void **p_Ptr; // rbx
  void **i; // rsi
  int v9; // eax
  void ***v10; // rcx
  void **v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // ebx
  __int64 (__fastcall *v14)(__int64, _QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64 *); // rbx
  int v20; // eax
  __int64 v21; // rcx
  int v22; // eax
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)); // rbx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  int v32; // eax
  void *v33; // rcx
  void *v34; // rcx
  unsigned int j; // edi
  void *v36; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v38; // rcx
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64); // rcx
  __int64 v40; // rcx
  int v42; // [rsp+20h] [rbp-39h]
  __int64 v43; // [rsp+50h] [rbp-9h] BYREF
  __int64 v44; // [rsp+58h] [rbp-1h] BYREF
  __int64 (__fastcall ***v45)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp+7h] BYREF
  __int64 v46; // [rsp+68h] [rbp+Fh] BYREF
  int v47; // [rsp+70h] [rbp+17h]
  __int64 v48; // [rsp+80h] [rbp+27h]
  int v49; // [rsp+88h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v51; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v52; // [rsp+D8h] [rbp+7Fh] BYREF

  v44 = 0;
  v45 = 0;
  v43 = 0;
  v46 = 0;
  v47 = 0;
  v6 = this + 3;
  AcquireSRWLockExclusive(this + 3);
  p_Ptr = &this[1].Ptr;
  for ( i = (void **)*p_Ptr; ; i = (void **)*i )
  {
    if ( i == p_Ptr )
    {
      v13 = 0;
      ReleaseSRWLockExclusive(v6);
      goto LABEL_75;
    }
    v9 = _o__wcsicmp(i[2], a3);
    v10 = (void ***)*i;
    if ( !v9 )
      break;
  }
  if ( v10[1] != i || (v11 = (void **)i[1], *v11 != i) )
    __fastfail(3u);
  *v11 = v10;
  v10[1] = v11;
  ReleaseSRWLockExclusive(v6);
  Microsoft::WRL::Details::Make<PlatformFactory,>(&v52);
  v12 = v52;
  if ( !v52 )
  {
    v13 = -2147467261;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
      (const char *)0x80004003LL,
      v42);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids, 2147500035LL);
    goto LABEL_62;
  }
  v51 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v52 + 24LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
  v15 = v14(v12, 0, &GUID_df8e9480_ca73_448e_b8f0_da000f581428, &v51);
  v13 = v15;
  if ( v15 >= 0 )
  {
    v18 = v51;
    v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 24LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v44);
    v20 = v19(v18, &v44);
    v13 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE4,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
        (const char *)(unsigned int)v20,
        v42);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_61;
      v17 = 16;
      goto LABEL_15;
    }
    if ( *((_DWORD *)i + 10) )
    {
      v22 = WpnCalculateNextDueTime(i[11], *((unsigned int *)i + 24), &v46);
      v13 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xED,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
          (const char *)(unsigned int)v22,
          v42);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_61;
        v17 = 17;
        goto LABEL_15;
      }
      v48 = v46;
      v49 = v47;
      v42 = (_DWORD)i + 48;
      v23 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v44 + 160LL))(
              v44,
              a2,
              a3,
              1);
      v13 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xF8,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
          (const char *)(unsigned int)v23,
          v42);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_61;
        v17 = 18;
        goto LABEL_15;
      }
      if ( *((_DWORD *)i + 6) )
      {
        v24 = v51;
        v25 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(*(_QWORD *)v51 + 48LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v45);
        v26 = v25(v24, &v45);
        v13 = v26;
        if ( v26 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xFD,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
            (const char *)(unsigned int)v26,
            v42);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_61;
          v17 = 19;
          goto LABEL_15;
        }
        v27 = Microsoft::WRL::ComPtr<IWpnSettingsEndpoint>::As<IWpnSettingsEndpoint2>(&v45, (__int64)&v43);
        v13 = v27;
        if ( v27 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
            (const char *)(unsigned int)v27,
            v42);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_61;
          v17 = 20;
          goto LABEL_15;
        }
        v28 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, _QWORD))(*(_QWORD *)v43 + 32LL))(
                v43,
                a3,
                L"s:cycle:medium",
                *((unsigned int *)i + 7));
        v13 = v28;
        if ( v28 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x103,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
            (const char *)(unsigned int)v28,
            v42);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_61;
          v17 = 21;
          goto LABEL_15;
        }
        v29 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, _QWORD))(*(_QWORD *)v43 + 32LL))(
                v43,
                a3,
                L"s:cycle:wide",
                *((unsigned int *)i + 8));
        v13 = v29;
        if ( v29 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x106,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
            (const char *)(unsigned int)v29,
            v42);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_61;
          v17 = 22;
          goto LABEL_15;
        }
        v30 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const wchar_t *, _QWORD))(*(_QWORD *)v43 + 32LL))(
                v43,
                a3,
                L"s:cycle:large",
                *((unsigned int *)i + 9));
        v13 = v30;
        if ( v30 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
            (const char *)(unsigned int)v30,
            v42);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
            goto LABEL_61;
          v17 = 23;
          goto LABEL_15;
        }
      }
    }
    if ( !i[13] )
      goto LABEL_59;
    LODWORD(v46) = 0;
    v31 = WpnCalculateNextDueTime(i[11], *((unsigned int *)i + 24), &v46);
    v13 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
        (const char *)(unsigned int)v31,
        v42);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_61;
      v17 = 24;
      goto LABEL_15;
    }
    v48 = v46;
    v49 = v47;
    v32 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64))(*(_QWORD *)v44 + 160LL))(
            v44,
            a2,
            a3,
            2);
    v13 = v32;
    if ( v32 >= 0 )
    {
LABEL_59:
      if ( (byte_18015DE45 & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v21, WPNEND_CACHED_POLLING_URL_APPLIED, a3);
      goto LABEL_61;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
      (const char *)(unsigned int)v32,
      (_DWORD)i + 104);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_61;
    v17 = 25;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\pollingurlregistrationcache.cpp",
      (const char *)(unsigned int)v15,
      v42);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
      goto LABEL_61;
    v17 = 15;
  }
LABEL_15:
  WPP_SF_d(v16[2], v17, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids, v13);
LABEL_61:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v51);
LABEL_62:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v52);
  if ( i )
  {
    v33 = i[2];
    if ( v33 )
    {
      CoTaskMemFree(v33);
      i[2] = 0;
    }
    v34 = i[13];
    if ( v34 )
    {
      CoTaskMemFree(v34);
      i[13] = 0;
    }
    for ( j = 0; j < *((_DWORD *)i + 10); ++j )
    {
      if ( j >= 5 )
        break;
      v36 = i[j + 6];
      if ( v36 )
      {
        CoTaskMemFree(v36);
        i[j + 6] = 0;
      }
    }
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, i);
  }
LABEL_75:
  v38 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  }
  v39 = v45;
  if ( v45 )
  {
    v45 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v39)[2])(v39);
  }
  v40 = v44;
  if ( v44 )
  {
    v44 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  return v13;
}

```

## disassembly

```asm
0x180062c20  mov     [rsp-8+arg_8], rbx
0x180062c25  mov     [rsp-8+arg_10], rsi
0x180062c2a  push    rbp
0x180062c2b  push    rdi
0x180062c2c  push    r12
0x180062c2e  push    r14
0x180062c30  push    r15
0x180062c32  lea     rbp, [rsp-37h]
0x180062c37  sub     rsp, 90h
0x180062c3e  mov     r14, r8
0x180062c41  mov     r15, rdx
0x180062c44  mov     rbx, rcx
0x180062c47  xor     r12d, r12d
0x180062c4a  mov     [rbp+57h+var_58], r12
0x180062c4e  mov     [rbp+57h+var_50], r12
0x180062c52  mov     [rbp+57h+var_60], r12
0x180062c56  xor     eax, eax
0x180062c58  mov     [rbp+57h+var_48], rax
0x180062c5c  mov     [rbp+57h+var_40], eax
0x180062c5f  lea     rdi, [rcx+18h]
0x180062c63  mov     rcx, rdi; SRWLock
0x180062c66  call    cs:__imp_AcquireSRWLockExclusive
0x180062c6c  add     rbx, 8
0x180062c70  mov     rsi, [rbx]
0x180062c73  cmp     rsi, rbx
0x180062c76  jz      loc_1800632BF
0x180062c7c  mov     rdx, r14
0x180062c7f  mov     rcx, [rsi+10h]
0x180062c83  call    cs:__imp__o__wcsicmp
0x180062c89  mov     rcx, [rsi]
0x180062c8c  test    eax, eax
0x180062c8e  jz      short loc_180062C95
0x180062c90  mov     rsi, rcx
0x180062c93  jmp     short loc_180062C73
0x180062c95  cmp     [rcx+8], rsi
0x180062c99  jnz     loc_1800632B8
0x180062c9f  mov     rax, [rsi+8]
0x180062ca3  cmp     [rax], rsi
0x180062ca6  jnz     loc_1800632B8
0x180062cac  mov     [rax], rcx
0x180062caf  mov     [rcx+8], rax
0x180062cb3  mov     rcx, rdi; SRWLock
0x180062cb6  call    cs:__imp_ReleaseSRWLockExclusive
0x180062cbc  lea     rcx, [rbp+57h+arg_18]
0x180062cc0  call    ??$Make@VPlatformFactory@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VPlatformFactory@@@12@XZ; Microsoft::WRL::Details::Make<PlatformFactory,>(void)
0x180062cc5  nop
0x180062cc6  mov     rbx, [rbp+57h+arg_18]
0x180062cca  test    rbx, rbx
0x180062ccd  jnz     short loc_180062D2D
0x180062ccf  mov     ebx, 80004003h
0x180062cd4  mov     rcx, [rbp+5Fh]; this
0x180062cd8  mov     r9d, ebx; char *
0x180062cdb  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062ce2  mov     edx, 0DDh; void *
0x180062ce7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062cec  lea     rax, WPP_GLOBAL_Control
0x180062cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180062cfa  cmp     rcx, rax
0x180062cfd  jz      loc_180063241
0x180062d03  test    byte ptr [rcx+1Ch], 80h
0x180062d07  jz      loc_180063241
0x180062d0d  mov     edx, 0Eh
0x180062d12  mov     r9d, 80004003h
0x180062d18  lea     r8, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids
0x180062d1f  mov     rcx, [rcx+10h]
0x180062d23  call    WPP_SF_d
0x180062d28  jmp     loc_180063241
0x180062d2d  mov     [rbp+57h+arg_0], r12
0x180062d31  mov     rax, [rbx]
0x180062d34  mov     rdi, [rax+18h]
0x180062d38  lea     rcx, [rbp+57h+arg_0]
0x180062d3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180062d41  lea     r9, [rbp+57h+arg_0]
0x180062d45  lea     r8, _GUID_df8e9480_ca73_448e_b8f0_da000f581428
0x180062d4c  xor     edx, edx
0x180062d4e  mov     rcx, rbx
0x180062d51  mov     rax, rdi
0x180062d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d59  mov     ebx, eax
0x180062d5b  test    eax, eax
0x180062d5d  jns     short loc_180062DB5
0x180062d5f  mov     rcx, [rbp+5Fh]; this
0x180062d63  mov     r9d, eax; char *
0x180062d66  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062d6d  mov     edx, 0E1h; void *
0x180062d72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062d77  lea     rax, WPP_GLOBAL_Control
0x180062d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180062d85  cmp     rcx, rax
0x180062d88  jz      loc_180063237
0x180062d8e  test    byte ptr [rcx+1Ch], 80h
0x180062d92  jz      loc_180063237
0x180062d98  mov     edx, 0Fh
0x180062d9d  mov     r9d, ebx
0x180062da0  lea     r8, WPP_3092d8a00e6a3aa07144cb8230583aa5_Traceguids
0x180062da7  mov     rcx, [rcx+10h]
0x180062dab  call    WPP_SF_d
0x180062db0  jmp     loc_180063237
0x180062db5  mov     rdi, [rbp+57h+arg_0]
0x180062db9  mov     rax, [rdi]
0x180062dbc  mov     rbx, [rax+18h]
0x180062dc0  lea     rcx, [rbp+57h+var_58]
0x180062dc4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180062dc9  lea     rdx, [rbp+57h+var_58]
0x180062dcd  mov     rcx, rdi
0x180062dd0  mov     rax, rbx
0x180062dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062dd8  mov     ebx, eax
0x180062dda  test    eax, eax
0x180062ddc  jns     short loc_180062E21
0x180062dde  mov     rcx, [rbp+5Fh]; this
0x180062de2  mov     r9d, eax; char *
0x180062de5  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062dec  mov     edx, 0E4h; void *
0x180062df1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062df6  lea     rax, WPP_GLOBAL_Control
0x180062dfd  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e04  cmp     rcx, rax
0x180062e07  jz      loc_180063237
0x180062e0d  test    byte ptr [rcx+1Ch], 80h
0x180062e11  jz      loc_180063237
0x180062e17  mov     edx, 10h
0x180062e1c  jmp     loc_180062D9D
0x180062e21  cmp     [rsi+28h], r12d
0x180062e25  jbe     loc_180063122
0x180062e2b  lea     r8, [rbp+57h+var_48]
0x180062e2f  mov     edx, [rsi+60h]
0x180062e32  mov     rcx, [rsi+58h]
0x180062e36  call    ?WpnCalculateNextDueTime@@YAJU_FILETIME@@W4__MIDL___MIDL_itf_wpnplatform_0000_0007_0003@@PEAU_WPN_FILE_TIME@@@Z; WpnCalculateNextDueTime(_FILETIME,__MIDL___MIDL_itf_wpnplatform_0000_0007_0003,_WPN_FILE_TIME *)
0x180062e3b  mov     ebx, eax
0x180062e3d  test    eax, eax
0x180062e3f  jns     short loc_180062E84
0x180062e41  mov     rcx, [rbp+5Fh]; this
0x180062e45  mov     r9d, eax; char *
0x180062e48  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062e4f  mov     edx, 0EDh; void *
0x180062e54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062e59  lea     rax, WPP_GLOBAL_Control
0x180062e60  mov     rcx, cs:WPP_GLOBAL_Control
0x180062e67  cmp     rcx, rax
0x180062e6a  jz      loc_180063237
0x180062e70  test    byte ptr [rcx+1Ch], 80h
0x180062e74  jz      loc_180063237
0x180062e7a  mov     edx, 11h
0x180062e7f  jmp     loc_180062D9D
0x180062e84  mov     rcx, [rbp+57h+var_58]
0x180062e88  movsd   xmm0, [rbp+57h+var_48]
0x180062e8d  movsd   [rbp+57h+var_30], xmm0
0x180062e92  mov     eax, [rbp+57h+var_40]
0x180062e95  mov     [rbp+57h+var_28], eax
0x180062e98  mov     rax, [rcx]
0x180062e9b  lea     r8, [rsi+30h]
0x180062e9f  mov     [rsp+0B0h+var_70], r12d
0x180062ea4  lea     rdx, [rbp+57h+var_30]
0x180062ea8  mov     [rsp+0B0h+var_78], rdx
0x180062ead  mov     edx, [rsi+60h]
0x180062eb0  mov     [rsp+0B0h+var_80], edx
0x180062eb4  mov     edx, [rsi+28h]
0x180062eb7  mov     [rsp+0B0h+var_88], edx
0x180062ebb  mov     qword ptr [rsp+0B0h+var_90], r8; int
0x180062ec0  mov     r9d, 1
0x180062ec6  mov     r8, r14
0x180062ec9  mov     rdx, r15
0x180062ecc  mov     rax, [rax+0A0h]
0x180062ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062ed8  mov     ebx, eax
0x180062eda  test    eax, eax
0x180062edc  jns     short loc_180062F21
0x180062ede  mov     rcx, [rbp+5Fh]; this
0x180062ee2  mov     r9d, eax; char *
0x180062ee5  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062eec  mov     edx, 0F8h; void *
0x180062ef1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062ef6  lea     rax, WPP_GLOBAL_Control
0x180062efd  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f04  cmp     rcx, rax
0x180062f07  jz      loc_180063237
0x180062f0d  test    byte ptr [rcx+1Ch], 80h
0x180062f11  jz      loc_180063237
0x180062f17  mov     edx, 12h
0x180062f1c  jmp     loc_180062D9D
0x180062f21  cmp     [rsi+18h], r12d
0x180062f25  jz      loc_180063122
0x180062f2b  mov     rdi, [rbp+57h+arg_0]
0x180062f2f  mov     rax, [rdi]
0x180062f32  mov     rbx, [rax+30h]
0x180062f36  lea     rcx, [rbp+57h+var_50]
0x180062f3a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180062f3f  lea     rdx, [rbp+57h+var_50]
0x180062f43  mov     rcx, rdi
0x180062f46  mov     rax, rbx
0x180062f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062f4e  mov     ebx, eax
0x180062f50  test    eax, eax
0x180062f52  jns     short loc_180062F97
0x180062f54  mov     rcx, [rbp+5Fh]; this
0x180062f58  mov     r9d, eax; char *
0x180062f5b  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062f62  mov     edx, 0FDh; void *
0x180062f67  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062f6c  lea     rax, WPP_GLOBAL_Control
0x180062f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f7a  cmp     rcx, rax
0x180062f7d  jz      loc_180063237
0x180062f83  test    byte ptr [rcx+1Ch], 80h
0x180062f87  jz      loc_180063237
0x180062f8d  mov     edx, 13h
0x180062f92  jmp     loc_180062D9D
0x180062f97  lea     rdx, [rbp+57h+var_60]
0x180062f9b  lea     rcx, [rbp+57h+var_50]
0x180062f9f  call    ??$As@UIWpnSettingsEndpoint2@@@?$ComPtr@UIWpnSettingsEndpoint@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWpnSettingsEndpoint2@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IWpnSettingsEndpoint>::As<IWpnSettingsEndpoint2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWpnSettingsEndpoint2>>)
0x180062fa4  mov     ebx, eax
0x180062fa6  test    eax, eax
0x180062fa8  jns     short loc_180062FED
0x180062faa  mov     rcx, [rbp+5Fh]; this
0x180062fae  mov     r9d, eax; char *
0x180062fb1  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180062fb8  mov     edx, 100h; void *
0x180062fbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180062fc2  lea     rax, WPP_GLOBAL_Control
0x180062fc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180062fd0  cmp     rcx, rax
0x180062fd3  jz      loc_180063237
0x180062fd9  test    byte ptr [rcx+1Ch], 80h
0x180062fdd  jz      loc_180063237
0x180062fe3  mov     edx, 14h
0x180062fe8  jmp     loc_180062D9D
0x180062fed  mov     rcx, [rbp+57h+var_60]
0x180062ff1  mov     rax, [rcx]
0x180062ff4  mov     r9d, [rsi+1Ch]
0x180062ff8  lea     r8, aSCycleMedium; "s:cycle:medium"
0x180062fff  mov     rdx, r14
0x180063002  mov     rax, [rax+20h]
0x180063006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006300b  mov     ebx, eax
0x18006300d  test    eax, eax
0x18006300f  jns     short loc_180063054
0x180063011  mov     rcx, [rbp+5Fh]; this
0x180063015  mov     r9d, eax; char *
0x180063018  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006301f  mov     edx, 103h; void *
0x180063024  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063029  lea     rax, WPP_GLOBAL_Control
0x180063030  mov     rcx, cs:WPP_GLOBAL_Control
0x180063037  cmp     rcx, rax
0x18006303a  jz      loc_180063237
0x180063040  test    byte ptr [rcx+1Ch], 80h
0x180063044  jz      loc_180063237
0x18006304a  mov     edx, 15h
0x18006304f  jmp     loc_180062D9D
0x180063054  mov     rcx, [rbp+57h+var_60]
0x180063058  mov     rax, [rcx]
0x18006305b  mov     r9d, [rsi+20h]
0x18006305f  lea     r8, aSCycleWide; "s:cycle:wide"
0x180063066  mov     rdx, r14
0x180063069  mov     rax, [rax+20h]
0x18006306d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063072  mov     ebx, eax
0x180063074  test    eax, eax
0x180063076  jns     short loc_1800630BB
0x180063078  mov     rcx, [rbp+5Fh]; this
0x18006307c  mov     r9d, eax; char *
0x18006307f  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180063086  mov     edx, 106h; void *
0x18006308b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180063090  lea     rax, WPP_GLOBAL_Control
0x180063097  mov     rcx, cs:WPP_GLOBAL_Control
0x18006309e  cmp     rcx, rax
0x1800630a1  jz      loc_180063237
0x1800630a7  test    byte ptr [rcx+1Ch], 80h
0x1800630ab  jz      loc_180063237
0x1800630b1  mov     edx, 16h
0x1800630b6  jmp     loc_180062D9D
0x1800630bb  mov     rcx, [rbp+57h+var_60]
0x1800630bf  mov     rax, [rcx]
0x1800630c2  mov     r9d, [rsi+24h]
0x1800630c6  lea     r8, aSCycleLarge; "s:cycle:large"
0x1800630cd  mov     rdx, r14
0x1800630d0  mov     rax, [rax+20h]
0x1800630d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800630d9  mov     ebx, eax
0x1800630db  test    eax, eax
0x1800630dd  jns     short loc_180063122
0x1800630df  mov     rcx, [rbp+5Fh]; this
0x1800630e3  mov     r9d, eax; char *
0x1800630e6  lea     r8, aOnecoreuapBase_150; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800630ed  mov     edx, 109h; void *
0x1800630f2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800630f7  lea     rax, WPP_GLOBAL_Control
0x1800630fe  mov     rcx, cs:WPP_GLOBAL_Control
0x180063105  cmp     rcx, rax
0x180063108  jz      loc_180063237
0x18006310e  test    byte ptr [rcx+1Ch], 80h
0x180063112  jz      loc_180063237
0x180063118  mov     edx, 17h
0x18006311d  jmp     loc_180062D9D
0x180063122  lea     rdi, [rsi+68h]
0x180063126  cmp     [rdi], r12
0x180063129  jz      loc_18006321E
0x18006312f  mov     dword ptr [rbp+57h+var_48], r12d
  ... truncated ...
```
