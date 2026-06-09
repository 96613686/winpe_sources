# InProcProxyEventListener::OnWinEvent(uint,HWND__ *,int,int)

- ea: `0x180035500`
- end: `0x180035982`
- name: `?OnWinEvent@InProcProxyEventListener@@UEAAXIPEAUHWND__@@HH@Z`
- size: `1154`
- prototype: `void(InProcProxyEventListener *__hidden this, unsigned int, HWND, int, int)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180034360`
- `0x180035500`
- `0x180035988`
- `0x1800359a8`
- `0x180035ac4`
- `0x180041fe4`
- `0x1801296a4`
- `0x1801be44c`
- `0x1801e8320`
- `0x1801e8380`
- `0x1801e8a1c`
- `0x1801e8a84`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180035667`
- `msvcp_win!_Mtx_unlock` at `0x180035667`
- `msvcp_win!_Mtx_lock` at `0x1800355f3`
- `msvcp_win!_Mtx_lock` at `0x1800355f3`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180035940`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180035951`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180035940`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180035951`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003590b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003590b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035584`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180035584`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800358f8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800358f8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800358c9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowThreadProcessId` at `0x1800358c9`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowTextW` at `0x1800357e8`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetWindowTextW` at `0x1800357e8`

## string_xrefs

- `0x1800358f1`: `user32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall InProcProxyEventListener::OnWinEvent(
        InProcProxyEventListener *this,
        unsigned int a2,
        HWND a3,
        unsigned int a4,
        unsigned int a5)
{
  DWORD v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rbx
  __int64 *v13; // rbx
  __int64 v14; // rcx
  int v15; // eax
  std::_Ref_count_base **v16; // rax
  std::_Ref_count_base *v17; // rcx
  __int64 i; // rax
  int v19; // edx
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  DWORD dwProcessId[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v24; // [rsp+30h] [rbp-D0h]
  DWORD *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base **v29; // [rsp+70h] [rbp-90h]
  WCHAR String[264]; // [rsp+80h] [rbp-80h] BYREF

  dwProcessId[0] = 0;
  if ( dword_1803A34B0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 88LL) )
  {
    Init_thread_header(&dword_1803A34B0);
    if ( dword_1803A34B0 == -1 )
    {
      LibraryW = LoadLibraryW(L"user32.dll");
      if ( LibraryW )
        ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0xA98);
      else
        ProcAddress = 0;
      qword_1803A34B8 = (__int64 (__fastcall *)(_QWORD))ProcAddress;
      Init_thread_footer(&dword_1803A34B0);
    }
  }
  if ( qword_1803A34B8 )
  {
    v9 = qword_1803A34B8(a3);
    dwProcessId[0] = v9;
  }
  else
  {
    GetWindowThreadProcessId(a3, dwProcessId);
    v9 = dwProcessId[0];
  }
  if ( GetCurrentProcessId() == v9 )
  {
    if ( a2 == 32779 )
    {
      if ( a4 != -8 )
        return;
LABEL_9:
      v10 = *((_QWORD *)this + 1);
      v25 = (DWORD *)a2;
      *(_QWORD *)&v26 = a3;
      *((_QWORD *)&v26 + 1) = __PAIR64__(a5, a4);
      v27 = v10;
      if ( _Mtx_lock((_Mtx_t)v10) )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      if ( *(_DWORD *)(v10 + 76) == 0x7FFFFFFF )
      {
        *(_DWORD *)(v10 + 76) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      else
      {
        std::vector<WinEvent>::_Emplace_one_at_back<WinEvent const &>(v10 + 80, &v25);
        if ( (_DWORD)v25 == 32773 )
        {
          *(_QWORD *)(v10 + 104) = 0xAAAAAAAAAAAAAAABuLL
                                 * ((__int64)(*(_QWORD *)(v10 + 88) - *(_QWORD *)(v10 + 80)) >> 3)
                                 - 1;
          *(_BYTE *)(v10 + 112) = 1;
          *(_DWORD *)(v10 + 113) = *(_DWORD *)((char *)&v24 + 9);
          *(_WORD *)(v10 + 117) = *(_WORD *)((char *)&v24 + 13);
          *(_BYTE *)(v10 + 119) = HIBYTE(v24);
        }
        _Mtx_unlock((_Mtx_t)v10);
        v11 = *((_QWORD *)this + 2);
        if ( v11 )
          _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
        *(_QWORD *)&v24 = *((_QWORD *)this + 1);
        v12 = (volatile signed __int32 *)*((_QWORD *)this + 2);
        *((_QWORD *)&v24 + 1) = v12;
        if ( !*((_BYTE *)this + 32) )
        {
          anonymous_namespace_::DispatchWinEventsToCorrectThread();
LABEL_39:
          if ( v12 && _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
          return;
        }
        v13 = (__int64 *)((char *)this + 24);
        v14 = *((_QWORD *)this + 3);
        if ( !v14
          || (LODWORD(v25) = 0,
              v26 = 0,
              v15 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14),
              v15 >= 0) )
        {
          v27 = 50000;
          *(_OWORD *)v28 = v24;
          v24 = 0;
          v29 = v28;
          v16 = (std::_Ref_count_base **)operator new(0x20u);
          v29 = v16;
          *((_DWORD *)v16 + 2) = 1;
          v16[2] = 0;
          v16[3] = 0;
          v16[2] = v28[0];
          v16[3] = v28[1];
          *(_OWORD *)v28 = 0;
          _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
          *v16 = (std::_Ref_count_base *)off_1802E1988;
          *(_QWORD *)dwProcessId = v16;
          v17 = v28[1];
          if ( v28[1] )
            std::_Ref_count_base::_Decref(v28[1]);
          v25 = dwProcessId;
          *(_QWORD *)&v26 = &v27;
          v29 = (std::_Ref_count_base **)&qword_1803A16C8;
          _InterlockedIncrement64(&qword_1803A16C8);
          if ( winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> )
          {
            winrt::impl::consume_Windows_System_Threading_IThreadPoolTimerStatics<winrt::Windows::System::Threading::IThreadPoolTimerStatics>::CreateTimer(
              &winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>,
              &v23,
              dwProcessId,
              &v27);
            _InterlockedDecrement64(&qword_1803A16C8);
          }
          else
          {
            _InterlockedDecrement64(&qword_1803A16C8);
            winrt::impl::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::call<_lambda_b19cf72fe9674443383aa89d5c22450b_ &>(
              v17,
              &v23,
              &v25);
          }
          if ( v13 == &v23 )
          {
            if ( v23 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
          }
          else
          {
            if ( *v13 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref((char *)this + 24);
            *v13 = v23;
          }
          if ( *(_QWORD *)dwProcessId )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(dwProcessId);
          v12 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
          goto LABEL_39;
        }
      }
      winrt::throw_hresult((unsigned int)v15, &v25);
    }
    if ( a2 != 32773 )
      goto LABEL_9;
    memset_0(String, 0, 0x208u);
    if ( GetWindowTextW(a3, String, 260) <= 0 )
      goto LABEL_9;
    for ( i = 0; i != 24; i += 2 )
    {
      v19 = String[i] - aRemoteappMarke[i];
      if ( v19 )
        break;
      v19 = String[i + 1] - aRemoteappMarke[i + 1];
      if ( v19 )
        break;
    }
    if ( v19 )
      goto LABEL_9;
  }
}

```

## disassembly

```asm
0x180035500  push    rbp
0x180035502  push    rbx
0x180035503  push    rsi
0x180035504  push    rdi
0x180035505  push    r12
0x180035507  push    r14
0x180035509  push    r15
0x18003550b  lea     rbp, [rsp-1A0h]
0x180035513  sub     rsp, 2A0h
0x18003551a  mov     rax, cs:__security_cookie
0x180035521  xor     rax, rsp
0x180035524  mov     [rbp+1D0h+var_40], rax
0x18003552b  mov     r15d, r9d
0x18003552e  mov     rsi, r8
0x180035531  mov     edi, edx
0x180035533  mov     r14, rcx
0x180035536  xor     r12d, r12d
0x180035539  mov     [rsp+2D0h+dwProcessId], r12d
0x18003553e  mov     r8d, cs:_tls_index
0x180035545  mov     rax, gs:58h
0x18003554e  mov     ecx, 58h ; 'X'
0x180035553  mov     rax, [rax+r8*8]
0x180035557  mov     ecx, [rcx+rax]
0x18003555a  cmp     cs:dword_1803A34B0, ecx
0x180035560  jg      loc_1800358D8
0x180035566  mov     rax, cs:qword_1803A34B8
0x18003556d  mov     rcx, rsi; hWnd
0x180035570  test    rax, rax
0x180035573  jz      loc_1800358C4
0x180035579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003557e  mov     ebx, eax
0x180035580  mov     [rsp+2D0h+dwProcessId], eax
0x180035584  call    cs:__imp_GetCurrentProcessId
0x18003558a  cmp     eax, ebx
0x18003558c  jnz     short loc_18003559C
0x18003558e  cmp     edi, 800Bh
0x180035594  jnz     short loc_1800355BD
0x180035596  cmp     r15d, 0FFFFFFF8h
0x18003559a  jz      short loc_1800355C9
0x18003559c  mov     rcx, [rbp+1D0h+var_40]
0x1800355a3  xor     rcx, rsp; StackCookie
0x1800355a6  call    __security_check_cookie
0x1800355ab  add     rsp, 2A0h
0x1800355b2  pop     r15
0x1800355b4  pop     r14
0x1800355b6  pop     r12
0x1800355b8  pop     rdi
0x1800355b9  pop     rsi
0x1800355ba  pop     rbx
0x1800355bb  pop     rbp
0x1800355bc  retn
0x1800355bd  cmp     edi, 8005h
0x1800355c3  jz      loc_1800357CA
0x1800355c9  mov     rbx, [r14+8]
0x1800355cd  mov     dword ptr [rsp+2D0h+var_290], edi
0x1800355d1  xor     eax, eax
0x1800355d3  mov     dword ptr [rsp+2D0h+var_290+4], eax
0x1800355d7  mov     qword ptr [rsp+2D0h+var_288], rsi
0x1800355dc  mov     dword ptr [rsp+2D0h+var_288+8], r15d
0x1800355e1  mov     eax, [rbp+1D0h+arg_20]
0x1800355e7  mov     dword ptr [rsp+2D0h+var_288+0Ch], eax
0x1800355eb  mov     [rsp+2D0h+var_278], rbx
0x1800355f0  mov     rcx, rbx; _Mtx_t
0x1800355f3  call    cs:__imp__Mtx_lock
0x1800355f9  test    eax, eax
0x1800355fb  jnz     loc_18003593B
0x180035601  mov     eax, [rbx+4Ch]
0x180035604  cmp     eax, 7FFFFFFFh
0x180035609  jz      loc_180035947
0x18003560f  lea     rdx, [rsp+2D0h+var_290]
0x180035614  lea     rcx, [rbx+50h]
0x180035618  call    ??$_Emplace_one_at_back@AEBUWinEvent@@@?$vector@UWinEvent@@V?$allocator@UWinEvent@@@std@@@std@@AEAAAEAUWinEvent@@AEBU2@@Z; std::vector<WinEvent>::_Emplace_one_at_back<WinEvent const &>(WinEvent const &)
0x18003561d  cmp     dword ptr [rsp+2D0h+var_290], 8005h
0x180035625  jnz     short loc_180035664
0x180035627  mov     rax, [rbx+58h]
0x18003562b  sub     rax, [rbx+50h]
0x18003562f  sar     rax, 3
0x180035633  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18003563d  imul    rax, rcx
0x180035641  dec     rax
0x180035644  mov     [rbx+68h], rax
0x180035648  mov     byte ptr [rbx+70h], 1
0x18003564c  mov     eax, dword ptr [rsp+2D0h+var_2A0+9]
0x180035650  mov     [rbx+71h], eax
0x180035653  movzx   eax, word ptr [rsp+2D0h+var_2A0+0Dh]
0x180035658  mov     [rbx+75h], ax
0x18003565c  movzx   eax, byte ptr [rsp+2D0h+var_2A0+0Fh]
0x180035661  mov     [rbx+77h], al
0x180035664  mov     rcx, rbx; _Mtx_t
0x180035667  call    cs:__imp__Mtx_unlock
0x18003566d  mov     rax, [r14+10h]
0x180035671  test    rax, rax
0x180035674  jz      short loc_18003567A
0x180035676  lock inc dword ptr [rax+8]
0x18003567a  mov     rcx, [r14+8]
0x18003567e  mov     qword ptr [rsp+2D0h+var_2A0], rcx
0x180035683  mov     rbx, [r14+10h]
0x180035687  mov     [rsp+38h], rbx
0x18003568c  cmp     byte ptr [r14+20h], 0
0x180035691  jz      loc_180035845
0x180035697  lea     rbx, [r14+18h]
0x18003569b  mov     rcx, [rbx]
0x18003569e  test    rcx, rcx
0x1800356a1  jz      short loc_1800356C5
0x1800356a3  mov     dword ptr [rsp+2D0h+var_290], r12d
0x1800356a8  xorps   xmm0, xmm0
0x1800356ab  movdqu  [rsp+2D0h+var_288], xmm0
0x1800356b1  mov     rax, [rcx]
0x1800356b4  mov     rax, [rax+40h]
0x1800356b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356bd  test    eax, eax
0x1800356bf  js      loc_180035958
0x1800356c5  mov     [rsp+2D0h+var_278], 0C350h
0x1800356ce  movaps  xmm0, [rsp+2D0h+var_2A0]
0x1800356d3  movdqa  xmmword ptr [rsp+2D0h+var_270], xmm0
0x1800356d9  xorps   xmm1, xmm1
0x1800356dc  movdqa  [rsp+2D0h+var_2A0], xmm1
0x1800356e2  lea     rax, [rsp+2D0h+var_270]
0x1800356e7  mov     [rsp+2D0h+var_260], rax
0x1800356ec  mov     ecx, 20h ; ' '; Size
0x1800356f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800356f6  mov     [rsp+2D0h+var_260], rax
0x1800356fb  mov     dword ptr [rax+8], 1
0x180035702  mov     [rax+10h], r12
0x180035706  mov     [rax+18h], r12
0x18003570a  mov     rcx, [rsp+2D0h+var_270]
0x18003570f  mov     [rax+10h], rcx
0x180035713  mov     rcx, [rsp+2D0h+var_270+8]
0x180035718  mov     [rax+18h], rcx
0x18003571c  xorps   xmm0, xmm0
0x18003571f  movdqa  xmmword ptr [rsp+2D0h+var_270], xmm0
0x180035725  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18003572c  lea     rcx, off_1802E1988
0x180035733  mov     [rax], rcx
0x180035736  mov     qword ptr [rsp+2D0h+dwProcessId], rax
0x18003573b  mov     rcx, [rsp+2D0h+var_270+8]; this
0x180035740  test    rcx, rcx
0x180035743  jz      short loc_18003574B
0x180035745  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003574a  nop
0x18003574b  lea     rax, [rsp+2D0h+dwProcessId]
0x180035750  mov     [rsp+2D0h+var_290], rax
0x180035755  lea     rax, [rsp+2D0h+var_278]
0x18003575a  mov     qword ptr [rsp+2D0h+var_288], rax
0x18003575f  lea     rax, qword_1803A16C8
0x180035766  mov     [rsp+2D0h+var_260], rax
0x18003576b  lock inc cs:qword_1803A16C8
0x180035773  cmp     cs:??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A, 0; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x18003577b  jz      loc_180035965
0x180035781  lea     r9, [rsp+2D0h+var_278]
0x180035786  lea     r8, [rsp+2D0h+dwProcessId]
0x18003578b  lea     rdx, [rsp+2D0h+var_2A8]
0x180035790  lea     rcx, ??$factory_cache_entry_v@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@12@A; factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>::winrt::factory_cache_entry<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::System::Threading::ThreadPoolTimer,winrt::Windows::System::Threading::IThreadPoolTimerStatics>
0x180035797  call    ?CreateTimer@?$consume_Windows_System_Threading_IThreadPoolTimerStatics@UIThreadPoolTimerStatics@Threading@System@Windows@winrt@@@impl@winrt@@QEBA@AEBUTimerElapsedHandler@Threading@System@Windows@3@AEBV?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@chrono@std@@@Z; winrt::impl::consume_Windows_System_Threading_IThreadPoolTimerStatics<winrt::Windows::System::Threading::IThreadPoolTimerStatics>::CreateTimer(winrt::Windows::System::Threading::TimerElapsedHandler const &,std::chrono::duration<__int64,std::ratio<1,10000000>> const &)
0x18003579c  nop
0x18003579d  lock dec cs:qword_1803A16C8
0x1800357a5  lea     rax, [rsp+2D0h+var_2A8]
0x1800357aa  cmp     rbx, rax
0x1800357ad  jz      loc_18003584C
0x1800357b3  cmp     qword ptr [rbx], 0
0x1800357b7  jnz     loc_180035913
0x1800357bd  mov     rax, [rsp+2D0h+var_2A8]
0x1800357c2  mov     [rbx], rax
0x1800357c5  jmp     loc_18003585F
0x1800357ca  xor     edx, edx; Val
0x1800357cc  mov     r8d, 208h; Size
0x1800357d2  lea     rcx, [rbp+1D0h+String]; void *
0x1800357d6  call    memset_0
0x1800357db  mov     r8d, 104h; nMaxCount
0x1800357e1  lea     rdx, [rbp+1D0h+String]; lpString
0x1800357e5  mov     rcx, rsi; hWnd
0x1800357e8  call    cs:__imp_GetWindowTextW
0x1800357ee  test    eax, eax
0x1800357f0  jle     loc_1800355C9
0x1800357f6  lea     r8, [rbp+1D0h+String]
0x1800357fa  lea     r9, aRemoteappMarke; "RemoteApp Marker Window"
0x180035801  mov     rax, r12
0x180035804  nop     dword ptr [rax+00h]
0x180035808  nop     dword ptr [rax+rax+00000000h]
0x180035810  movzx   edx, word ptr [r8+rax*2]
0x180035815  movzx   ecx, word ptr [r9+rax*2]
0x18003581a  sub     edx, ecx
0x18003581c  jnz     short loc_180035838
0x18003581e  movzx   edx, word ptr [r8+rax*2+2]
0x180035824  movzx   ecx, word ptr [r9+rax*2+2]
0x18003582a  sub     edx, ecx
0x18003582c  jnz     short loc_180035838
0x18003582e  add     rax, 2
0x180035832  cmp     rax, 18h
0x180035836  jnz     short loc_180035810
0x180035838  test    edx, edx
0x18003583a  jnz     loc_1800355C9
0x180035840  jmp     loc_18003559C
0x180035845  call    _anonymous_namespace___DispatchWinEventsToCorrectThread
0x18003584a  jmp     short loc_180035876
0x18003584c  cmp     [rsp+2D0h+var_2A8], 0
0x180035852  jz      short loc_18003585F
0x180035854  lea     rcx, [rsp+2D0h+var_2A8]
0x180035859  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003585e  nop
0x18003585f  cmp     qword ptr [rsp+2D0h+dwProcessId], 0
0x180035865  jz      short loc_180035871
0x180035867  lea     rcx, [rsp+2D0h+dwProcessId]
0x18003586c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180035871  mov     rbx, qword ptr [rsp+2D0h+var_2A0+8]
0x180035876  test    rbx, rbx
0x180035879  jz      loc_18003559C
0x18003587f  mov     edi, 0FFFFFFFFh
0x180035884  mov     eax, edi
0x180035886  lock xadd [rbx+8], eax
0x18003588b  cmp     eax, 1
0x18003588e  jnz     loc_18003559C
0x180035894  mov     rax, [rbx]
0x180035897  mov     rcx, rbx
0x18003589a  mov     rax, [rax]
0x18003589d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358a2  lock xadd [rbx+0Ch], edi
0x1800358a7  cmp     edi, 1
0x1800358aa  jnz     loc_18003559C
0x1800358b0  mov     rax, [rbx]
0x1800358b3  mov     rcx, rbx
0x1800358b6  mov     rax, [rax+8]
0x1800358ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800358bf  jmp     loc_18003559C
0x1800358c4  lea     rdx, [rsp+2D0h+dwProcessId]; lpdwProcessId
0x1800358c9  call    cs:__imp_GetWindowThreadProcessId
0x1800358cf  mov     ebx, [rsp+2D0h+dwProcessId]
0x1800358d3  jmp     loc_180035584
0x1800358d8  lea     rcx, dword_1803A34B0
0x1800358df  call    _Init_thread_header
0x1800358e4  cmp     cs:dword_1803A34B0, 0FFFFFFFFh
0x1800358eb  jnz     loc_180035566
0x1800358f1  lea     rcx, LibFileName; "user32.dll"
0x1800358f8  call    cs:__imp_LoadLibraryW
0x1800358fe  test    rax, rax
0x180035901  jz      short loc_180035920
0x180035903  mov     edx, 0A98h; lpProcName
0x180035908  mov     rcx, rax; hModule
0x18003590b  call    cs:__imp_GetProcAddress
0x180035911  jmp     short loc_180035923
0x180035913  mov     rcx, rbx
0x180035916  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18003591b  jmp     loc_1800357BD
0x180035920  mov     rax, r12
0x180035923  mov     cs:qword_1803A34B8, rax
0x18003592a  lea     rcx, dword_1803A34B0
0x180035931  call    _Init_thread_footer
0x180035936  jmp     loc_180035566
0x18003593b  mov     ecx, 5
0x180035940  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180035946  int     3; Trap to Debugger
0x180035947  dec     eax
0x180035949  mov     [rbx+4Ch], eax
0x18003594c  mov     ecx, 6
0x180035951  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180035957  nop
0x180035958  lea     rdx, [rsp+2D0h+var_290]
0x18003595d  mov     ecx, eax
0x18003595f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180035965  lock dec cs:qword_1803A16C8
0x18003596d  lea     r8, [rsp+2D0h+var_290]
0x180035972  lea     rdx, [rsp+2D0h+var_2A8]
0x180035977  call    ??$call@AEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@?$factory_cache_entry@UThreadPoolTimer@Threading@System@Windows@winrt@@UIThreadPoolTimerStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_b19cf72fe9674443383aa89d5c22450b_@@@Z
0x18003597c  jmp     loc_1800357A5
```
