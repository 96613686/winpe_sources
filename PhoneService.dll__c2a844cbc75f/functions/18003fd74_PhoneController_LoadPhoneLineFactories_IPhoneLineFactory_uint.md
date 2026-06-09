# PhoneController::_LoadPhoneLineFactories(IPhoneLineFactory * *,uint)

- ea: `0x18003fd74`
- end: `0x180040498`
- name: `?_LoadPhoneLineFactories@PhoneController@@IEAAJPEAPEAUIPhoneLineFactory@@I@Z`
- size: `1828`
- prototype: `__int64 __fastcall(PhoneController *__hidden this, struct IPhoneLineFactory **, unsigned int)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180034e08`

## callees

- `0x18000151c`
- `0x180005660`
- `0x180005c54`
- `0x180006e94`
- `0x18000e1a4`
- `0x18000f9f4`
- `0x18002c574`
- `0x18002c580`
- `0x18003b4f8`
- `0x18003fd74`
- `0x18004b39c`
- `0x18004b834`
- `0x180053d50`
- `0x18007f9ec`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180040259`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180040259`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040283`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180040283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fda4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fdc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fda4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fdc5`

## string_xrefs

- `0x180040033`: `onecoreuap\internal\net\inc\phone\ConfigValue.h`
- `0x18003fdb9`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18003ffb0`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180040008`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004020c`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004033f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800403c2`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180040454`: `PhoneLineFactories load complete`
- `0x18004040f`: `onecoreuap\net\phone\phoneservice\service\lib\phonelinefactoryhost.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_LoadPhoneLineFactories(
        PhoneController *this,
        struct IPhoneLineFactory **a2,
        unsigned int a3)
{
  __int64 v6; // rcx
  __int64 ***v7; // r14
  BackTraceCollection *v8; // rcx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rsi
  struct IPhoneLineFactory *v12; // rdi
  __int64 ****v13; // rax
  __int64 ****v14; // rbx
  __int64 ***v15; // rax
  int v16; // ebx
  __int64 **k; // rbx
  __int64 v18; // rsi
  _QWORD *v19; // rax
  BackTraceCollection *v20; // rcx
  _QWORD *v21; // rdi
  struct ATL::CAtlModule *v22; // rcx
  __int64 v23; // rcx
  void (__fastcall ***v24)(_QWORD, GUID *, LPVOID *); // rcx
  LPVOID v25; // r8
  int v26; // eax
  BackTraceCollection *v27; // rcx
  unsigned int v28; // esi
  __int64 v29; // rcx
  int v30; // esi
  unsigned int v31; // ebx
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v35; // rdi
  __int64 v36; // rbx
  int v37; // eax
  __int64 v38; // r9
  int v39; // eax
  __int64 v40; // rdx
  __int64 v41; // r9
  __int64 v42; // rdx
  BackTraceCollection *v43; // rcx
  __int64 v44; // r9
  BackTraceCollection *v45; // rcx
  _QWORD *i; // rbx
  void *v47; // rcx
  _QWORD *j; // rdi
  _QWORD *v49; // rsi
  const OLECHAR *v50; // rcx
  HRESULT v51; // eax
  BackTraceCollection *v52; // rcx
  HRESULT v53; // eax
  BackTraceCollection *v54; // rcx
  __int64 ****v55; // rax
  BackTraceCollection *v56; // rcx
  __int64 ****v57; // rbx
  LPVOID v58; // rcx
  __int64 ***v59; // rax
  LPVOID v60; // rcx
  __int64 v61; // r9
  __int64 v62; // rdx
  BackTraceCollection *v63; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-49h] BYREF
  void **v65; // [rsp+38h] [rbp-41h] BYREF
  _QWORD v66[2]; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int64 v67; // [rsp+50h] [rbp-29h]
  __m128i si128; // [rsp+58h] [rbp-21h] BYREF
  __int64 v69; // [rsp+68h] [rbp-11h]
  GUID pclsid; // [rsp+70h] [rbp-9h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 499);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = (__int64 ***)((char *)this + 184);
  utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear((char *)this + 184);
  if ( !a2 )
  {
    v35 = *((_QWORD *)this + 61);
    v65 = &ConfigValueValueList::`vftable';
    v67 = 0;
    v66[0] = v66;
    v66[1] = v66;
    v36 = *(_QWORD *)(v35 + 360);
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v69 = -1;
    LODWORD(ppv) = 0;
    if ( !*(_QWORD *)(v36 + 80) )
    {
      Log_AssertionEvent_3(v8, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1308);
      if ( !*(_QWORD *)(v36 + 80) )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v37 = ConfigValue<ConfigValueValueList>::_Get(v35 + 328, *(_QWORD *)(v36 + 80), &v65, &ppv);
    v31 = v37;
    if ( v37 < 0 )
    {
      v38 = 143;
LABEL_46:
      Log_HREvent_7((unsigned int)v37, 1, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v38);
      v41 = 129;
      v42 = 1;
LABEL_50:
      Log_HREvent_7(v31, v42, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", v41);
      BackTraceCollection::Capture(v43, v31);
      v44 = 515;
      goto LABEL_66;
    }
    v39 = (int)ppv;
    if ( !(_DWORD)ppv )
    {
      v40 = *(_QWORD *)(v35 + 360);
      if ( *(_QWORD *)(v40 + 88) )
      {
        v37 = ConfigValue<ConfigValueValueList>::_Get(v35 + 328, *(_QWORD *)(v40 + 88), &v65, &ppv);
        v31 = v37;
        if ( v37 < 0 )
        {
          v38 = 148;
          goto LABEL_46;
        }
        v39 = (int)ppv;
      }
      if ( !v39 )
      {
        v41 = 135;
        v42 = 0;
        v31 = -2147024894;
        goto LABEL_50;
      }
    }
    if ( !v67
      || v67 < 0x1000000000000000LL
      && (unsigned __int8)utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(&si128) )
    {
      for ( i = (_QWORD *)v66[0]; i != v66; i = (_QWORD *)*i )
      {
        v47 = (void *)i[2];
        ppv = v47;
        if ( v47 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v47 + 8LL))(v47);
        if ( !(unsigned __int8)utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>>::push_back(
                                 &si128,
                                 &ppv) )
        {
          v31 = -2147024882;
          Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1683);
          v45 = (BackTraceCollection *)ppv;
          if ( ppv )
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
          goto LABEL_65;
        }
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      for ( j = (_QWORD *)si128.m128i_i64[0]; ; ++j )
      {
        if ( j == (_QWORD *)si128.m128i_i64[1] )
        {
          utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(&si128);
          v65 = &ConfigValueValueList::`vftable';
          utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(v66);
          goto LABEL_17;
        }
        v49 = (_QWORD *)*j;
        if ( *j )
          (*(void (__fastcall **)(_QWORD))(*v49 + 8LL))(*j);
        v50 = (const OLECHAR *)v49[7];
        ppv = 0;
        pclsid = 0;
        v51 = CLSIDFromString(v50, &pclsid);
        v31 = v51;
        if ( v51 < 0 )
          break;
        v53 = CoCreateInstance(&pclsid, 0, 0x17u, &GUID_d2bce917_37ff_48b7_ae00_4ed7cad38b2c, &ppv);
        v31 = v53;
        if ( v53 < 0 )
        {
          BackTraceCollection::Capture(v54, v53);
          v61 = 524;
          goto LABEL_82;
        }
        v55 = (__int64 ****)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        v57 = v55;
        if ( !v55 )
        {
          v31 = -2147024882;
          BackTraceCollection::Capture(v56, -2147024882);
          v61 = 526;
          v62 = 0;
          goto LABEL_83;
        }
        v58 = ppv;
        v55[2] = (__int64 ***)ppv;
        if ( v58 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v58 + 8LL))(v58);
        v59 = (__int64 ***)*((_QWORD *)this + 24);
        v57[1] = v59;
        *v57 = v7;
        *v59 = (__int64 **)v57;
        v60 = ppv;
        *((_QWORD *)this + 24) = v57;
        ++*((_QWORD *)this + 25);
        if ( v60 )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v60 + 16LL))(v60);
        (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
      }
      BackTraceCollection::Capture(v52, v51);
      v61 = 523;
LABEL_82:
      v62 = 1;
LABEL_83:
      Log_HREvent_7(v31, v62, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v61);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
      goto LABEL_86;
    }
    v31 = -2147024882;
    Log_HREvent_7(2147942414LL, 0, "onecoreuap\\internal\\net\\inc\\phone\\ConfigValue.h", 1679);
LABEL_65:
    BackTraceCollection::Capture(v45, -2147024882);
    v44 = 516;
LABEL_66:
    Log_HREvent_7(v31, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v44);
LABEL_86:
    utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(&si128);
    v65 = &ConfigValueValueList::`vftable';
    utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(v66);
    return v31;
  }
  v11 = 0;
  if ( a3 )
  {
    while ( 1 )
    {
      v12 = a2[v11];
      if ( v12 )
        (*(void (__fastcall **)(struct IPhoneLineFactory *))(*(_QWORD *)v12 + 8LL))(a2[v11]);
      v13 = (__int64 ****)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( v13 )
      {
        v13[2] = (__int64 ***)v12;
        if ( v12 )
          (*(void (__fastcall **)(struct IPhoneLineFactory *))(*(_QWORD *)v12 + 8LL))(v12);
        v15 = (__int64 ***)*((_QWORD *)this + 24);
        v14[1] = v15;
        *v14 = v7;
        *v15 = (__int64 **)v14;
        *((_QWORD *)this + 24) = v14;
        v16 = 1;
        ++*((_QWORD *)this + 25);
      }
      else
      {
        v16 = 0;
      }
      if ( v12 )
        (*(void (__fastcall **)(struct IPhoneLineFactory *))(*(_QWORD *)v12 + 16LL))(v12);
      if ( !v16 )
        break;
      v11 = (unsigned int)(v11 + 1);
      if ( (unsigned int)v11 >= a3 )
        goto LABEL_17;
    }
    v31 = -2147024882;
    BackTraceCollection::Capture(v8, -2147024882);
    v32 = 507;
    v33 = 0;
LABEL_35:
    Log_HREvent_7(2147942414LL, v33, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v32);
    return v31;
  }
LABEL_17:
  for ( k = *v7; k != (__int64 **)v7; k = (__int64 **)*k )
  {
    v18 = *((_QWORD *)this + 26);
    v19 = operator new(0x20u);
    v21 = v19;
    if ( !v19 )
    {
      v31 = -2147024882;
      BackTraceCollection::Capture(v20, -2147024882);
      Log_HREvent_14(2147942414LL, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\phonelinefactoryhost.cpp");
      BackTraceCollection::Capture(v63, -2147024882);
      v32 = 534;
      v33 = 1;
      goto LABEL_35;
    }
    *(_QWORD *)((char *)v19 + 12) = 0;
    *((_DWORD *)v19 + 5) = 0;
    v22 = ATL::_pAtlModule;
    *((_DWORD *)v19 + 2) = 0;
    v19[3] = 0;
    *v19 = &ATL::CComObject<PhoneLineFactoryHost>::`vftable';
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v22 + 8LL))(v22);
    (*(void (__fastcall **)(_QWORD *))(*v21 + 8LL))(v21);
    (*(void (__fastcall **)(_QWORD *))(*v21 + 8LL))(v21);
    (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    if ( v21[3] != v18 )
    {
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
      v23 = v21[3];
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v21[3] = v18;
    }
    v24 = (void (__fastcall ***)(_QWORD, GUID *, LPVOID *))*((_QWORD *)this + 59);
    v25 = 0;
    ppv = 0;
    if ( v24 )
    {
      (**v24)(v24, &GUID_211b5528_0872_4431_85c5_a072e72ee915, &ppv);
      v25 = ppv;
    }
    v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD *, LPVOID))(*k[2] + 24))(k[2], v21, v25);
    v28 = v26;
    if ( v26 < 0 )
    {
      BackTraceCollection::Capture(v27, v26);
      Log_HREvent_7(v28, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 538);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
      return v28;
    }
    v30 = (*(__int64 (__fastcall **)(__int64 *))(*k[2] + 40))(k[2]);
    if ( !v30 )
    {
      Log_AssertionEvent_3(v29, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 544);
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    *((_DWORD *)this + 116) |= v30;
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
  }
  if ( (unsigned int)dword_1800B3200 > 4 )
  {
    LODWORD(ppv) = *((_DWORD *)this + 116);
    *(_QWORD *)&pclsid.Data1 = "PhoneLineFactories load complete";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)v8,
      (unsigned int)byte_1800A8BAD,
      v9,
      v10,
      (__int64)&pclsid,
      (__int64)&ppv);
  }
  return 0;
}

```

## disassembly

```asm
0x18003fd74  push    rbp
0x18003fd76  push    rbx
0x18003fd77  push    rsi
0x18003fd78  push    rdi
0x18003fd79  push    r12
0x18003fd7b  push    r13
0x18003fd7d  push    r14
0x18003fd7f  push    r15
0x18003fd81  lea     rbp, [rsp-1Fh]
0x18003fd86  sub     rsp, 98h
0x18003fd8d  mov     rax, cs:__security_cookie
0x18003fd94  xor     rax, rsp
0x18003fd97  mov     [rbp+57h+var_50], rax
0x18003fd9b  mov     r12d, r8d
0x18003fd9e  mov     r13, rdx
0x18003fda1  mov     r15, rcx
0x18003fda4  call    cs:__imp_GetCurrentThreadId
0x18003fdaa  cmp     [r15+0F0h], eax
0x18003fdb1  jz      short loc_18003FDD9
0x18003fdb3  mov     r8d, 1F3h
0x18003fdb9  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003fdc0  call    Log_AssertionEvent_3
0x18003fdc5  call    cs:__imp_GetCurrentThreadId
0x18003fdcb  cmp     [r15+0F0h], eax
0x18003fdd2  jz      short loc_18003FDD9
0x18003fdd4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003fdd9  lea     r14, [r15+0B8h]
0x18003fde0  mov     rcx, r14
0x18003fde3  call    ?clear@?$list@V?$CComPtr@VRegistryValue@@@ATL@@V?$allocator@V?$CComPtr@VRegistryValue@@@ATL@@@utl@@@utl@@QEAAXXZ; utl::list<ATL::CComPtr<RegistryValue>,utl::allocator<ATL::CComPtr<RegistryValue>>>::clear(void)
0x18003fde8  mov     esi, 1
0x18003fded  test    r13, r13
0x18003fdf0  jz      loc_18004001D
0x18003fdf6  xor     esi, esi
0x18003fdf8  test    r12d, r12d
0x18003fdfb  jz      loc_18003FE91
0x18003fe01  mov     rdi, [r13+rsi*8+0]
0x18003fe06  test    rdi, rdi
0x18003fe09  jz      short loc_18003FE1A
0x18003fe0b  mov     rax, [rdi]
0x18003fe0e  mov     rcx, rdi
0x18003fe11  mov     rax, [rax+8]
0x18003fe15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003fe21  mov     ecx, 18h; unsigned __int64
0x18003fe26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003fe2b  mov     rbx, rax
0x18003fe2e  test    rax, rax
0x18003fe31  jz      short loc_18003FE68
0x18003fe33  mov     [rax+10h], rdi
0x18003fe37  test    rdi, rdi
0x18003fe3a  jz      short loc_18003FE4B
0x18003fe3c  mov     rax, [rdi]
0x18003fe3f  mov     rcx, rdi
0x18003fe42  mov     rax, [rax+8]
0x18003fe46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe4b  mov     rax, [r14+8]
0x18003fe4f  mov     [rbx+8], rax
0x18003fe53  mov     [rbx], r14
0x18003fe56  mov     [rax], rbx
0x18003fe59  mov     [r14+8], rbx
0x18003fe5d  mov     ebx, 1
0x18003fe62  inc     qword ptr [r14+10h]
0x18003fe66  jmp     short loc_18003FE6A
0x18003fe68  xor     ebx, ebx
0x18003fe6a  test    rdi, rdi
0x18003fe6d  jz      short loc_18003FE7E
0x18003fe6f  mov     rax, [rdi]
0x18003fe72  mov     rcx, rdi
0x18003fe75  mov     rax, [rax+10h]
0x18003fe79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe7e  test    ebx, ebx
0x18003fe80  jz      loc_18003FFF4
0x18003fe86  inc     esi
0x18003fe88  cmp     esi, r12d
0x18003fe8b  jb      loc_18003FE01
0x18003fe91  xor     r12d, r12d
0x18003fe94  mov     rbx, [r14]
0x18003fe97  cmp     rbx, r14
0x18003fe9a  jz      loc_180040438
0x18003fea0  mov     rsi, [r15+0D0h]
0x18003fea7  mov     ecx, 20h ; ' '; Size
0x18003feac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003feb1  mov     rdi, rax
0x18003feb4  test    rax, rax
0x18003feb7  jz      loc_1800403FD
0x18003febd  mov     [rax+0Ch], r12
0x18003fec1  mov     [rax+14h], r12d
0x18003fec5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18003fecc  mov     [rax+8], r12d
0x18003fed0  mov     [rax+18h], r12
0x18003fed4  lea     rax, ??_7?$CComObject@VPhoneLineFactoryHost@@@ATL@@6B@; const ATL::CComObject<PhoneLineFactoryHost>::`vftable'
0x18003fedb  mov     [rdi], rax
0x18003fede  mov     rdx, [rcx]
0x18003fee1  mov     rax, [rdx+8]
0x18003fee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003feea  mov     rax, [rdi]
0x18003feed  mov     rcx, rdi
0x18003fef0  mov     rax, [rax+8]
0x18003fef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fef9  mov     rax, [rdi]
0x18003fefc  mov     rcx, rdi
0x18003feff  mov     rax, [rax+8]
0x18003ff03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff08  mov     rax, [rdi]
0x18003ff0b  mov     rcx, rdi
0x18003ff0e  mov     rax, [rax+10h]
0x18003ff12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff17  cmp     [rdi+18h], rsi
0x18003ff1b  jz      short loc_18003FF4A
0x18003ff1d  test    rsi, rsi
0x18003ff20  jz      short loc_18003FF31
0x18003ff22  mov     rax, [rsi]
0x18003ff25  mov     rcx, rsi
0x18003ff28  mov     rax, [rax+8]
0x18003ff2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff31  mov     rcx, [rdi+18h]
0x18003ff35  test    rcx, rcx
0x18003ff38  jz      short loc_18003FF46
0x18003ff3a  mov     rax, [rcx]
0x18003ff3d  mov     rax, [rax+10h]
0x18003ff41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff46  mov     [rdi+18h], rsi
0x18003ff4a  mov     rcx, [r15+1D8h]
0x18003ff51  mov     r8, r12
0x18003ff54  mov     [rbp+57h+var_A0], r12
0x18003ff58  test    rcx, rcx
0x18003ff5b  jz      short loc_18003FF77
0x18003ff5d  mov     rax, [rcx]
0x18003ff60  lea     r8, [rbp+57h+var_A0]
0x18003ff64  lea     rdx, _GUID_211b5528_0872_4431_85c5_a072e72ee915
0x18003ff6b  mov     rax, [rax]
0x18003ff6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff73  mov     r8, [rbp+57h+var_A0]
0x18003ff77  mov     rcx, [rbx+10h]
0x18003ff7b  mov     rdx, rdi
0x18003ff7e  mov     rax, [rcx]
0x18003ff81  mov     rax, [rax+18h]
0x18003ff85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ff8a  mov     esi, eax
0x18003ff8c  test    eax, eax
0x18003ff8e  js      loc_1800403B5
0x18003ff94  mov     rcx, [rbx+10h]
0x18003ff98  mov     rax, [rcx]
0x18003ff9b  mov     rax, [rax+28h]
0x18003ff9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffa4  mov     esi, eax
0x18003ffa6  test    eax, eax
0x18003ffa8  jnz     short loc_18003FFC1
0x18003ffaa  mov     r8d, 220h
0x18003ffb0  lea     rdx, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18003ffb7  call    Log_AssertionEvent_3
0x18003ffbc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003ffc1  or      [r15+1D0h], esi
0x18003ffc8  mov     rcx, [rbp+57h+var_A0]
0x18003ffcc  test    rcx, rcx
0x18003ffcf  jz      short loc_18003FFDD
0x18003ffd1  mov     rax, [rcx]
0x18003ffd4  mov     rax, [rax+10h]
0x18003ffd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffdd  mov     rax, [rdi]
0x18003ffe0  mov     rcx, rdi
0x18003ffe3  mov     rax, [rax+10h]
0x18003ffe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffec  mov     rbx, [rbx]
0x18003ffef  jmp     loc_18003FE97
0x18003fff4  mov     ebx, 8007000Eh
0x18003fff9  mov     edx, ebx; int
0x18003fffb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180040000  mov     r9d, 1FBh
0x180040006  xor     edx, edx
0x180040008  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004000f  mov     ecx, ebx
0x180040011  call    Log_HREvent_7
0x180040016  mov     eax, ebx
0x180040018  jmp     loc_180040478
0x18004001d  mov     rdi, [r15+1E8h]
0x180040024  lea     rax, ??_7ConfigValueValueList@@6B@; const ConfigValueValueList::`vftable'
0x18004002b  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180040033  lea     r13, aOnecoreuapInte_1; "onecoreuap\\internal\\net\\inc\\phone\\"...
0x18004003a  mov     [rbp+57h+var_98], rax
0x18004003e  xor     r12d, r12d
0x180040041  lea     rax, [rbp+57h+var_90]
0x180040045  mov     [rbp+57h+var_80], r12
0x180040049  mov     [rbp+57h+var_90], rax
0x18004004d  lea     rax, [rbp+57h+var_90]
0x180040051  mov     [rbp+57h+var_88], rax
0x180040055  mov     rbx, [rdi+168h]
0x18004005c  movdqu  [rbp+57h+var_78], xmm0
0x180040061  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFFh
0x180040069  mov     dword ptr [rbp+57h+var_A0], r12d
0x18004006d  cmp     [rbx+50h], r12
0x180040071  jnz     short loc_18004008C
0x180040073  mov     r8d, 51Ch
0x180040079  mov     rdx, r13
0x18004007c  call    Log_AssertionEvent_3
0x180040081  cmp     [rbx+50h], r12
0x180040085  jnz     short loc_18004008C
0x180040087  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004008c  mov     rdx, [rbx+50h]
0x180040090  lea     r9, [rbp+57h+var_A0]
0x180040094  lea     r8, [rbp+57h+var_98]
0x180040098  lea     rcx, [rdi+148h]
0x18004009f  call    ?_Get@?$ConfigValue@VConfigValueValueList@@@@IEAAJPEAUHKEY__@@PEAVConfigValueValueList@@PEAH@Z; ConfigValue<ConfigValueValueList>::_Get(HKEY__ *,ConfigValueValueList *,int *)
0x1800400a4  mov     ebx, eax
0x1800400a6  test    eax, eax
0x1800400a8  jns     short loc_1800400B2
0x1800400aa  mov     r9d, 8Fh
0x1800400b0  jmp     short loc_1800400EA
0x1800400b2  mov     eax, dword ptr [rbp+57h+var_A0]
0x1800400b5  test    eax, eax
0x1800400b7  jnz     short loc_180040130
0x1800400b9  mov     rdx, [rdi+168h]
0x1800400c0  cmp     [rdx+58h], r12
0x1800400c4  jz      short loc_180040103
0x1800400c6  mov     rdx, [rdx+58h]
0x1800400ca  lea     r9, [rbp+57h+var_A0]
0x1800400ce  lea     r8, [rbp+57h+var_98]
0x1800400d2  lea     rcx, [rdi+148h]
0x1800400d9  call    ?_Get@?$ConfigValue@VConfigValueValueList@@@@IEAAJPEAUHKEY__@@PEAVConfigValueValueList@@PEAH@Z; ConfigValue<ConfigValueValueList>::_Get(HKEY__ *,ConfigValueValueList *,int *)
0x1800400de  mov     ebx, eax
0x1800400e0  test    eax, eax
0x1800400e2  jns     short loc_180040100
0x1800400e4  mov     r9d, 94h
0x1800400ea  mov     r8, r13
0x1800400ed  mov     edx, esi
0x1800400ef  mov     ecx, eax
0x1800400f1  call    Log_HREvent_7
0x1800400f6  mov     r9d, 81h
0x1800400fc  mov     edx, esi
0x1800400fe  jmp     short loc_180040114
0x180040100  mov     eax, dword ptr [rbp+57h+var_A0]
0x180040103  test    eax, eax
0x180040105  jnz     short loc_180040130
0x180040107  mov     r9d, 87h
0x18004010d  xor     edx, edx
0x18004010f  mov     ebx, 80070002h
0x180040114  mov     r8, r13
0x180040117  mov     ecx, ebx
0x180040119  call    Log_HREvent_7
0x18004011e  mov     edx, ebx; int
0x180040120  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180040125  mov     r9d, 203h
0x18004012b  jmp     loc_18004020C
0x180040130  mov     rdx, [rbp+57h+var_80]
0x180040134  test    rdx, rdx
0x180040137  jz      short loc_18004017E
0x180040139  cmp     rdx, 8
0x18004013d  jbe     short loc_180040150
0x18004013f  mov     rax, 0FFFFFFFFFFFFFFFh
0x180040149  cmp     rdx, rax
0x18004014c  ja      short loc_180040162
0x18004014e  jmp     short loc_180040155
0x180040150  mov     edx, 8
0x180040155  lea     rcx, [rbp+57h+var_78]
0x180040159  call    ?_SetCapacity@?$vector@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceUiSink@@@ATL@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<ATL::CComPtr<IPhoneServiceUiSink>,utl::allocator<ATL::CComPtr<IPhoneServiceUiSink>>>::_SetCapacity(unsigned __int64)
0x18004015e  test    al, al
0x180040160  jnz     short loc_18004017E
0x180040162  mov     ebx, 8007000Eh
0x180040167  mov     r9d, 68Fh
0x18004016d  mov     ecx, ebx
0x18004016f  mov     r8, r13
0x180040172  xor     edx, edx
0x180040174  call    Log_HREvent_7
0x180040179  jmp     loc_1800401FF
0x18004017e  mov     rbx, [rbp+57h+var_90]
0x180040182  lea     rax, [rbp+57h+var_90]
0x180040186  cmp     rbx, rax
0x180040189  jz      loc_180040221
0x18004018f  mov     rcx, [rbx+10h]
0x180040193  mov     [rbp+57h+var_A0], rcx
0x180040197  test    rcx, rcx
0x18004019a  jz      short loc_1800401A8
0x18004019c  mov     rax, [rcx]
0x18004019f  mov     rax, [rax+8]
0x1800401a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401a8  lea     rdx, [rbp+57h+var_A0]
0x1800401ac  lea     rcx, [rbp+57h+var_78]
0x1800401b0  call    ?push_back@?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@QEAA_NAEBV?$CComPtr@VCallInfo@@@ATL@@@Z; utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>>::push_back(ATL::CComPtr<CallInfo> const &)
0x1800401b5  test    al, al
0x1800401b7  jz      short loc_1800401D3
0x1800401b9  mov     rcx, [rbp+57h+var_A0]
0x1800401bd  test    rcx, rcx
0x1800401c0  jz      short loc_1800401CE
0x1800401c2  mov     rax, [rcx]
0x1800401c5  mov     rax, [rax+10h]
0x1800401c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401ce  mov     rbx, [rbx]
0x1800401d1  jmp     short loc_180040182
0x1800401d3  mov     ebx, 8007000Eh
0x1800401d8  mov     r9d, 693h
0x1800401de  mov     ecx, ebx
0x1800401e0  mov     r8, r13
0x1800401e3  xor     edx, edx
0x1800401e5  call    Log_HREvent_7
0x1800401ea  mov     rcx, [rbp+57h+var_A0]
0x1800401ee  test    rcx, rcx
0x1800401f1  jz      short loc_1800401FF
0x1800401f3  mov     rax, [rcx]
0x1800401f6  mov     rax, [rax+10h]
0x1800401fa  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
