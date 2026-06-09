# RadioManager::_LoadRadioManagers(wchar_t const *)

- ea: `0x1800213d4`
- end: `0x18002189e`
- name: `?_LoadRadioManagers@RadioManager@@AEAAXPEB_W@Z`
- size: `1226`
- prototype: `void __fastcall(RadioManager *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020940`

## callees

- `0x180006200`
- `0x18000844c`
- `0x180008ed0`
- `0x18000a6a0`
- `0x18000a798`
- `0x18000a9c0`
- `0x18000b814`
- `0x18000c15c`
- `0x18000c2a4`
- `0x18000d2a0`
- `0x18000df28`
- `0x18000df88`
- `0x180016418`
- `0x18001a138`
- `0x18001a1d8`
- `0x18001a27c`
- `0x18001a31c`
- `0x18001a3c0`
- `0x18001bb84`
- `0x1800213d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021443`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002175b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021443`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021613`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002175b`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180021672`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800217ba`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180021672`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800217ba`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800214f7`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800214f7`

## string_xrefs

- `0x180021850`: `onecore\private\net\inc\wcm\wcm_registry_iterator.h`

## pseudocode

```c
void __fastcall RadioManager::_LoadRadioManagers(RadioManager *this, const wchar_t *a2)
{
  __int64 v2; // rbx
  const OLECHAR *v3; // rcx
  const char *v4; // rdx
  __int64 v5; // rbx
  __int64 v6; // r14
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  wil *v10; // rcx
  RadioManager *v11; // r15
  RadioManager *v12; // rdi
  GUID *v13; // rsi
  GUID *v14; // r15
  __int64 v15; // r14
  char *i; // rbx
  wil *v17; // rcx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24[10]; // [rsp+0h] [rbp-178h] BYREF
  int v25; // [rsp+40h] [rbp-138h] BYREF
  GUID *p_iid; // [rsp+48h] [rbp-130h] BYREF
  GUID *v27; // [rsp+50h] [rbp-128h] BYREF
  const char *v28; // [rsp+58h] [rbp-120h] BYREF
  RadioManager *v29; // [rsp+60h] [rbp-118h]
  _QWORD v30[2]; // [rsp+68h] [rbp-110h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+78h] [rbp-100h] BYREF
  _BYTE v32[32]; // [rsp+90h] [rbp-E8h] BYREF
  GUID iid; // [rsp+B0h] [rbp-C8h] BYREF
  void *Buf2[2]; // [rsp+C0h] [rbp-B8h] BYREF
  void *v35; // [rsp+D0h] [rbp-A8h]
  __int64 v36; // [rsp+D8h] [rbp-A0h] BYREF
  GUID Buf1; // [rsp+E0h] [rbp-98h] BYREF
  RadioManager *v38; // [rsp+F0h] [rbp-88h]
  LPCOLESTR lpsz[2]; // [rsp+100h] [rbp-78h] BYREF
  RadioManager *v40; // [rsp+110h] [rbp-68h]
  unsigned int v41; // [rsp+120h] [rbp-58h]
  const OLECHAR *v42; // [rsp+128h] [rbp-50h] BYREF
  char v43[24]; // [rsp+130h] [rbp-48h] BYREF
  __int64 v44; // [rsp+148h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+0h]

  try
  {
    v12 = this;
    v30[1] = this;
    v11 = this;
    v29 = this;
    *(_OWORD *)Buf2 = 0;
    v35 = 0;
    v36 = 0;
    WcmCommon::Registry::CreateKeyRO(&v36, a2, a2);
    EnterCriticalSection((LPCRITICAL_SECTION)v11 + 6);
    v30[0] = (char *)v11 + 240;
    v2 = v36;
    WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(
      lpsz,
      v36,
      0);
    WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(
      &v42,
      v2,
      1);
    while ( v41 != -1 && (_DWORD)v44 != -1 && lpsz[0] != v42 || v41 != (_DWORD)v44 )
    {
      if ( v41 == -1 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xD7,
          (unsigned int)"onecore\\private\\net\\inc\\wcm\\wcm_registry_iterator.h",
          (const char *)0x103,
          v24[8]);
      v3 = (const OLECHAR *)&qword_18002AF20;
      if ( (unsigned __int64)((v40 - (RadioManager *)lpsz[1]) >> 1) >= 2 )
        v3 = lpsz[1];
      iid = 0;
      if ( IIDFromString(v3, &iid) >= 0 )
      {
        if ( Buf2[1] == v35 )
        {
          std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(Buf2, Buf2[1], &iid);
        }
        else
        {
          *(GUID *)Buf2[1] = iid;
          Buf2[1] = (char *)Buf2[1] + 16;
        }
        Buf1 = iid;
        v5 = *((_QWORD *)v12 + 35);
        v6 = *((_QWORD *)v11 + 36);
        while ( v5 != v6 )
        {
          if ( !memcmp_0(&Buf1, (const void *)(*(_QWORD *)v5 + 8LL), 0x10u) )
            goto LABEL_26;
          v5 += 8;
        }
        if ( (unsigned int)dword_180037050 > 4 )
        {
          v27 = (GUID *)RmGuidToMediaTypeString(&iid);
          p_iid = &iid;
          v28 = "Processing a MediaRadioManager";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(
            v7,
            (unsigned int)&unk_18002FDE0,
            v8,
            v9,
            (__int64)&v28,
            (__int64)&p_iid,
            (__int64)&v27);
        }
        Buf1 = iid;
        v38 = v12;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 448));
        try
        {
          p_iid = (GUID *)((char *)v12 + 448);
          if ( *((_BYTE *)v12 + 712) )
          {
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&p_iid);
          }
          else
          {
            if ( *((_DWORD *)v12 + 110) == 1 )
              std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::_Emplace_back_internal__RadioManager::_LoadRadioManagers_::_23_::_lambda_2___(
                (char *)v12 + 592,
                &Buf1);
            else
              std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::_Emplace_back_internal__RadioManager::_LoadRadioManagers_::_23_::_lambda_2___(
                (char *)v12 + 672,
                &Buf1);
            wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&p_iid);
            _InterlockedIncrement64((volatile signed __int64 *)v12 + 72);
            SubmitThreadpoolWork(*((PTP_WORK *)v12 + 71));
          }
        }
        catch ( ... )
        {
          v4 = (const char *)v24;
          if ( (unsigned int)dword_180037050 > 2 )
          {
            v25 = wil::ResultFromCaughtException(v10);
            v28 = RmGuidToMediaTypeString(&iid);
            v27 = &iid;
            p_iid = (GUID *)"SubmitWork to the TP queue to add a MediaRadioManager failed with an exception";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              v18,
              (unsigned int)word_18002FD82,
              v19,
              v20,
              (__int64)&p_iid,
              (__int64)&v27,
              (__int64)&v28,
              (__int64)&v25);
          }
          v11 = v29;
          v12 = v29;
        }
      }
LABEL_26:
      if ( v41 + 1 < v41 )
      {
        std::out_of_range::out_of_range((std::out_of_range *)pExceptionObject, v4);
        throw (std::out_of_range *)pExceptionObject;
      }
      if ( v41 == -2 )
      {
        std::out_of_range::out_of_range((std::out_of_range *)v32, v4);
        throw (std::out_of_range *)v32;
      }
      ++v41;
      WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(lpsz);
    }
    std::vector<wchar_t>::_Tidy(v43);
    std::vector<wchar_t>::_Tidy(&lpsz[1]);
    v13 = (GUID *)*((_QWORD *)v12 + 35);
    v14 = (GUID *)*((_QWORD *)v12 + 36);
    *(_QWORD *)&iid.Data1 = v14;
    while ( 1 )
    {
      v27 = v13;
      if ( v13 == v14 )
        break;
      v15 = *(_QWORD *)&v13->Data1;
      Buf1 = *(GUID *)(*(_QWORD *)&v13->Data1 + 8LL);
      for ( i = (char *)Buf2[0]; i != Buf2[1]; i += 16 )
      {
        if ( !memcmp_0((const void *)(v15 + 8), i, 0x10u) )
          goto LABEL_41;
      }
      *(_OWORD *)lpsz = *(_OWORD *)(v15 + 8);
      v40 = v12;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)v12 + 448));
      p_iid = (GUID *)((char *)v12 + 448);
      if ( *((_BYTE *)v12 + 712) )
      {
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&p_iid);
      }
      else
      {
        if ( *((_DWORD *)v12 + 110) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::_Emplace_back_internal__RadioManager::_LoadRadioManagers_::_39_::_lambda_4___(
            (char *)v12 + 592,
            lpsz);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::_Emplace_back_internal__RadioManager::_LoadRadioManagers_::_39_::_lambda_4___(
            (char *)v12 + 672,
            lpsz);
        wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&p_iid);
        _InterlockedIncrement64((volatile signed __int64 *)v12 + 72);
        SubmitThreadpoolWork(*((PTP_WORK *)v12 + 71));
      }
LABEL_41:
      v13 = (GUID *)((char *)v13 + 8);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v36);
    v17 = (wil *)Buf2[0];
    if ( Buf2[0] )
      std::_Deallocate<16>(Buf2[0], ((unsigned __int64)v35 - (unsigned __int64)Buf2[0]) & 0xFFFFFFFFFFFFFFF0uLL);
  }
  catch ( ... )
  {
    if ( (unsigned int)dword_180037050 > 2 )
    {
      v25 = wil::ResultFromCaughtException(v17);
      v30[0] = "Exception thrown accessing the RadioManager registry key to find radio managers";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&word_18002FCDE,
        v22,
        v23,
        (__int64)v30,
        (__int64)&v25);
    }
  }
}

```

## disassembly

```asm
0x1800213d4  mov     r11, rsp
0x1800213d7  mov     [r11+18h], rbx
0x1800213db  mov     [r11+20h], rsi
0x1800213df  push    rdi
0x1800213e0  push    r14
0x1800213e2  push    r15
0x1800213e4  sub     rsp, 160h
0x1800213eb  mov     rax, cs:__security_cookie
0x1800213f2  xor     rax, rsp
0x1800213f5  mov     [rsp+178h+var_28], rax
0x1800213fd  mov     rdi, rcx
0x180021400  mov     [rsp+178h+var_108], rcx
0x180021405  mov     r15, rcx
0x180021408  mov     [rsp+178h+var_118], rcx
0x18002140d  xor     eax, eax
0x18002140f  xorps   xmm1, xmm1
0x180021412  movdqu  xmmword ptr [rsp+178h+Buf2], xmm1
0x18002141b  mov     [r11-0A8h], rax
0x180021422  mov     [r11-0A0h], rax
0x180021429  mov     r8, rdx
0x18002142c  lea     rcx, [r11-0A0h]
0x180021433  call    ?CreateKeyRO@Registry@WcmCommon@@YA?AVKey@12@QEAUHKEY__@@QEB_W@Z; WcmCommon::Registry::CreateKeyRO(HKEY__ * const,wchar_t const * const)
0x180021438  nop
0x180021439  lea     rbx, [r15+0F0h]
0x180021440  mov     rcx, rbx; lpCriticalSection
0x180021443  call    cs:__imp_EnterCriticalSection
0x180021449  mov     [rsp+178h+var_110], rbx
0x18002144e  mov     rbx, [rsp+178h+var_A0]
0x180021456  xor     r8d, r8d
0x180021459  mov     rdx, rbx
0x18002145c  lea     rcx, [rsp+178h+lpsz]
0x180021464  call    ??0?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@QEAA@QEAUHKEY__@@W4IteratorCreationFlag@12@@Z; WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(HKEY__ * const,WcmCommon::Registry::IteratorCreationFlag)
0x180021469  nop
0x18002146a  mov     r8d, 1
0x180021470  mov     rdx, rbx
0x180021473  lea     rcx, [rsp+178h+var_50]
0x18002147b  call    ??0?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@QEAA@QEAUHKEY__@@W4IteratorCreationFlag@12@@Z; WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::Iterator<WcmCommon::Registry::Details::KeyIteratorData>(HKEY__ * const,WcmCommon::Registry::IteratorCreationFlag)
0x180021480  nop
0x180021481  or      esi, 0FFFFFFFFh
0x180021484  mov     edx, [rsp+178h+var_58]
0x18002148b  mov     rcx, [rsp+178h+var_30]
0x180021493  cmp     edx, esi
0x180021495  jz      short loc_1800214AD
0x180021497  cmp     ecx, esi
0x180021499  jz      short loc_1800214AD
0x18002149b  mov     rax, [rsp+178h+var_50]
0x1800214a3  cmp     [rsp+178h+lpsz], rax
0x1800214ab  jnz     short loc_1800214B5
0x1800214ad  cmp     edx, ecx
0x1800214af  jz      loc_1800216B9
0x1800214b5  cmp     edx, esi
0x1800214b7  jz      loc_180021842
0x1800214bd  mov     rax, [rsp+178h+var_68]
0x1800214c5  sub     rax, [rsp+178h+lpsz+8]
0x1800214cd  sar     rax, 1
0x1800214d0  lea     rcx, qword_18002AF20
0x1800214d7  cmp     rax, 2
0x1800214db  cmovnb  rcx, [rsp+178h+lpsz+8]; lpsz
0x1800214e4  xorps   xmm0, xmm0
0x1800214e7  movups  xmmword ptr [rsp+178h+iid.Data1], xmm0
0x1800214ef  lea     rdx, [rsp+178h+iid]; lpiid
0x1800214f7  call    cs:__imp_IIDFromString
0x1800214fd  test    eax, eax
0x1800214ff  js      loc_180021686
0x180021505  mov     rdx, [rsp+178h+Buf2+8]
0x18002150d  cmp     rdx, [rsp+178h+var_A8]
0x180021515  jz      short loc_18002152E
0x180021517  movaps  xmm0, xmmword ptr [rsp+178h+iid.Data1]
0x18002151f  movdqu  xmmword ptr [rdx], xmm0
0x180021523  add     [rsp+178h+Buf2+8], 10h
0x18002152c  jmp     short loc_180021543
0x18002152e  lea     r8, [rsp+178h+iid]
0x180021536  lea     rcx, [rsp+178h+Buf2]
0x18002153e  call    ??$_Emplace_reallocate@AEBU_GUID@@@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEAAPEAU_GUID@@QEAU2@AEBU2@@Z; std::vector<_GUID>::_Emplace_reallocate<_GUID const &>(_GUID * const,_GUID const &)
0x180021543  movaps  xmm0, xmmword ptr [rsp+178h+iid.Data1]
0x18002154b  movdqa  [rsp+178h+Buf1], xmm0
0x180021554  mov     rbx, [rdi+118h]
0x18002155b  mov     r14, [r15+120h]
0x180021562  jmp     short loc_18002158A
0x180021564  mov     rdx, [rbx]
0x180021567  add     rdx, 8; Buf2
0x18002156b  mov     r8d, 10h; Size
0x180021571  lea     rcx, [rsp+178h+Buf1]; Buf1
0x180021579  call    memcmp_0
0x18002157e  test    eax, eax
0x180021580  jz      loc_180021686
0x180021586  add     rbx, 8
0x18002158a  cmp     rbx, r14
0x18002158d  jnz     short loc_180021564
0x18002158f  mov     eax, cs:dword_180037050
0x180021595  cmp     eax, 4
0x180021598  jbe     short loc_1800215F0
0x18002159a  lea     rcx, [rsp+178h+iid]; struct _GUID *
0x1800215a2  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x1800215a7  mov     [rsp+178h+var_128], rax
0x1800215ac  lea     rax, [rsp+178h+iid]
0x1800215b4  mov     [rsp+178h+var_130], rax
0x1800215b9  lea     rax, aProcessingAMed; "Processing a MediaRadioManager"
0x1800215c0  mov     [rsp+178h+var_120], rax
0x1800215c5  lea     rax, [rsp+178h+var_128]
0x1800215ca  mov     [rsp+178h+var_148], rax
0x1800215cf  lea     rax, [rsp+178h+var_130]
0x1800215d4  mov     [rsp+178h+var_150], rax
0x1800215d9  lea     rax, [rsp+178h+var_120]
0x1800215de  mov     [rsp+178h+var_158], rax
0x1800215e3  lea     rdx, unk_18002FDE0
0x1800215ea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &)
0x1800215ef  nop
0x1800215f0  movaps  xmm0, xmmword ptr [rsp+178h+iid.Data1]
0x1800215f8  movdqu  [rsp+178h+Buf1], xmm0
0x180021601  mov     [rsp+178h+var_88], rdi
0x180021609  lea     rbx, [rdi+1C0h]
0x180021610  mov     rcx, rbx; lpCriticalSection
0x180021613  call    cs:__imp_EnterCriticalSection
0x180021619  mov     [rsp+178h+var_130], rbx
0x18002161e  lea     rcx, [rdi+250h]
0x180021625  cmp     byte ptr [rcx+78h], 0
0x180021629  jz      short loc_180021637
0x18002162b  lea     rcx, [rsp+178h+var_130]
0x180021630  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180021635  jmp     short loc_180021679
0x180021637  lea     rdx, [rsp+178h+Buf1]
0x18002163f  cmp     dword ptr [rdi+1B8h], 1
0x180021646  jnz     short loc_18002164F
0x180021648  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void_________Emplace_back_internal__RadioManager___LoadRadioManagers____23____lambda_2___
0x18002164d  jmp     short loc_180021659
0x18002164f  add     rcx, 50h ; 'P'
0x180021653  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult__________Emplace_back_internal__RadioManager___LoadRadioManagers____23____lambda_2___
0x180021658  nop
0x180021659  lea     rcx, [rsp+178h+var_130]
0x18002165e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180021663  lock inc qword ptr [rdi+240h]
0x18002166b  mov     rcx, [rdi+238h]; pwk
0x180021672  call    cs:__imp_SubmitThreadpoolWork
0x180021678  nop
0x180021679  jmp     short loc_180021686
0x18002167b  or      esi, 0FFFFFFFFh
0x18002167e  mov     r15, [rsp+178h+var_118]
0x180021683  mov     rdi, r15
0x180021686  mov     eax, [rsp+178h+var_58]
0x18002168d  lea     ecx, [rax+1]
0x180021690  cmp     ecx, eax
0x180021692  jb      loc_180021860
0x180021698  cmp     ecx, esi
0x18002169a  jz      loc_18002187B
0x1800216a0  mov     [rsp+178h+var_58], ecx
0x1800216a7  lea     rcx, [rsp+178h+lpsz]
0x1800216af  call    ?enumerateNext@?$Iterator@UKeyIteratorData@Details@Registry@WcmCommon@@@Registry@WcmCommon@@AEAAXXZ; WcmCommon::Registry::Iterator<WcmCommon::Registry::Details::KeyIteratorData>::enumerateNext(void)
0x1800216b4  jmp     loc_180021484
0x1800216b9  lea     rcx, [rsp+178h+var_48]
0x1800216c1  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800216c6  nop
0x1800216c7  lea     rcx, [rsp+178h+lpsz+8]
0x1800216cf  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x1800216d4  mov     rsi, [rdi+118h]
0x1800216db  mov     r15, [rdi+120h]
0x1800216e2  mov     qword ptr [rsp+178h+iid.Data1], r15
0x1800216ea  mov     [rsp+178h+var_128], rsi
0x1800216ef  cmp     rsi, r15
0x1800216f2  jz      loc_1800217DE
0x1800216f8  mov     r14, [rsi]
0x1800216fb  movups  xmm0, xmmword ptr [r14+8]
0x180021700  movdqu  [rsp+178h+Buf1], xmm0
0x180021709  mov     rbx, [rsp+178h+Buf2]
0x180021711  jmp     short loc_180021731
0x180021713  mov     r8d, 10h; Size
0x180021719  mov     rdx, rbx; Buf2
0x18002171c  lea     rcx, [r14+8]; Buf1
0x180021720  call    memcmp_0
0x180021725  test    eax, eax
0x180021727  jz      loc_1800217C1
0x18002172d  add     rbx, 10h
0x180021731  cmp     rbx, [rsp+178h+Buf2+8]
0x180021739  jnz     short loc_180021713
0x18002173b  movups  xmm0, xmmword ptr [r14+8]
0x180021740  movdqu  xmmword ptr [rsp+178h+lpsz], xmm0
0x180021749  mov     [rsp+178h+var_68], rdi
0x180021751  lea     rbx, [rdi+1C0h]
0x180021758  mov     rcx, rbx; lpCriticalSection
0x18002175b  call    cs:__imp_EnterCriticalSection
0x180021761  mov     [rsp+178h+var_130], rbx
0x180021766  lea     rcx, [rdi+250h]
0x18002176d  cmp     byte ptr [rcx+78h], 0
0x180021771  jz      short loc_18002177F
0x180021773  lea     rcx, [rsp+178h+var_130]
0x180021778  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002177d  jmp     short loc_1800217C1
0x18002177f  lea     rdx, [rsp+178h+lpsz]
0x180021787  cmp     dword ptr [rdi+1B8h], 1
0x18002178e  jnz     short loc_180021797
0x180021790  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void_________Emplace_back_internal__RadioManager___LoadRadioManagers____39____lambda_4___
0x180021795  jmp     short loc_1800217A1
0x180021797  add     rcx, 50h ; 'P'
0x18002179b  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult__________Emplace_back_internal__RadioManager___LoadRadioManagers____39____lambda_4___
0x1800217a0  nop
0x1800217a1  lea     rcx, [rsp+178h+var_130]
0x1800217a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800217ab  lock inc qword ptr [rdi+240h]
0x1800217b3  mov     rcx, [rdi+238h]; pwk
0x1800217ba  call    cs:__imp_SubmitThreadpoolWork
0x1800217c0  nop
0x1800217c1  jmp     short loc_1800217D5
0x1800217c3  mov     rsi, [rsp+178h+var_128]
0x1800217c8  mov     r15, qword ptr [rsp+178h+iid.Data1]
0x1800217d0  mov     rdi, [rsp+178h+var_108]
0x1800217d5  add     rsi, 8
0x1800217d9  jmp     loc_1800216EA
0x1800217de  lea     rcx, [rsp+178h+var_110]
0x1800217e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x1800217e8  nop
0x1800217e9  lea     rcx, [rsp+178h+var_A0]
0x1800217f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800217f6  nop
0x1800217f7  mov     rcx, [rsp+178h+Buf2]
0x1800217ff  test    rcx, rcx
0x180021802  jz      short loc_180021819
0x180021804  mov     rdx, [rsp+178h+var_A8]
0x18002180c  sub     rdx, rcx
0x18002180f  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180021813  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180021818  nop
0x180021819  mov     rcx, [rsp+178h+var_28]
0x180021821  xor     rcx, rsp; StackCookie
0x180021824  call    __security_check_cookie
0x180021829  lea     r11, [rsp+178h+var_18]
0x180021831  mov     rbx, [r11+30h]
0x180021835  mov     rsi, [r11+38h]
0x180021839  mov     rsp, r11
0x18002183c  pop     r15
0x18002183e  pop     r14
0x180021840  pop     rdi
0x180021841  retn
0x180021842  mov     rcx, [rsp+178h]; this
0x18002184a  mov     r9d, 103h; char *
0x180021850  lea     r8, aOnecorePrivate; "onecore\\private\\net\\inc\\wcm\\wcm_re"...
0x180021857  lea     edx, [r9-2Ch]; void *
0x18002185b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180021860  lea     rcx, [rsp+178h+pExceptionObject]; this
0x180021865  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x18002186a  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180021871  lea     rcx, [rsp+178h+pExceptionObject]; pExceptionObject
0x180021876  call    _CxxThrowException_0
0x18002187b  lea     rcx, [rsp+178h+var_E8]; this
0x180021883  call    ??0out_of_range@std@@QEAA@PEBD@Z; std::out_of_range::out_of_range(char const *)
0x180021888  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x18002188f  lea     rcx, [rsp+178h+var_E8]; pExceptionObject
0x180021897  call    _CxxThrowException_0
```
