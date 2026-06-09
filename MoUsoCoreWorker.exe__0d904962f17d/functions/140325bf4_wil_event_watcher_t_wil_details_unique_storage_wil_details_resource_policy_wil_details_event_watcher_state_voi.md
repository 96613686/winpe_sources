# wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(void *,wistd::function<void (void)> &&)

- ea: `0x140325bf4`
- end: `0x140325e4e`
- name: `?create_take_hevent_ownership@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@AEAAJPEAX$$QEAV?$function@$$A6AXXZ@wistd@@@Z`
- size: `602`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140317d5c`

## callees

- `0x14003fd58`
- `0x140040184`
- `0x14004045c`
- `0x1400407f8`
- `0x140325bf4`
- `0x140326898`
- `0x1403790cc`
- `0x14037911c`
- `0x140380b50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140325d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140325da9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140325d2c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140325da9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140325cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140325d8c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140325cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140325d8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325cc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325dcf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325cc6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325d72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140325dcf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140325ce8`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x140325ce8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140325d24`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140325d24`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140325d1b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140325d1b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140325d0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140325dc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140325d0d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x140325dc0`

## string_xrefs

- `0x140325cac`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140325d43`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140325df7`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140325e0e`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140325e25`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140325e3c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::create_take_hevent_ownership(
        wil::details::event_watcher_state **a1,
        void *a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rbx
  _QWORD *v7; // rax
  void *v8; // rsi
  void *v9; // rdi
  const char *v10; // r9
  PTP_WAIT ThreadpoolWait; // rbp
  const char *v13; // r9
  struct _TP_WAIT *v14; // r14
  DWORD LastError; // edi
  unsigned int v16; // edi
  const char *v17; // r9
  wil::details::event_watcher_state *v18; // rbp
  DWORD v19; // edi
  const char *v20; // r9
  int v21; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v5 = a2;
  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF5E,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v21 = (int)a2;
  v7 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( v7 )
  {
    if ( *(_QWORD *)(a3 + 112) )
    {
      v7[14] = v7 + 1;
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 112) + 16LL))(*(_QWORD *)(a3 + 112));
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a3 + 112) + 24LL))(*(_QWORD *)(a3 + 112));
      *(_QWORD *)(a3 + 112) = 0;
    }
    else
    {
      v7[14] = 0;
    }
    *((_QWORD *)v8 + 15) = v5;
    v5 = 0;
    *((_QWORD *)v8 + 16) = 0;
    v9 = 0;
  }
  else
  {
    v8 = 0;
    v9 = v5;
  }
  if ( v8 )
  {
    ThreadpoolWait = CreateThreadpoolWait(
                       wil::event_watcher_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>,wil::err_exception_policy>::wait_callback,
                       v8,
                       0);
    v14 = (struct _TP_WAIT *)*((_QWORD *)v8 + 16);
    if ( v14 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v14, 0, 0);
      WaitForThreadpoolWaitCallbacks(v14, 1);
      CloseThreadpoolWait(v14);
      SetLastError(LastError);
    }
    *((_QWORD *)v8 + 16) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      v18 = *a1;
      if ( *a1 )
      {
        v19 = GetLastError();
        wil::details::event_watcher_state::~event_watcher_state(v18);
        operator delete(v18);
        SetLastError(v19);
      }
      *a1 = (wil::details::event_watcher_state *)v8;
      SetThreadpoolWait(*((PTP_WAIT *)v8 + 16), *((HANDLE *)v8 + 15), 0);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v20);
      return 0;
    }
    else
    {
      v16 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0xF65,
              (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
              v13);
      wil::details::event_watcher_state::~event_watcher_state((wil::details::event_watcher_state *)v8);
      operator delete(v8);
      if ( v5 && !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v17);
      return v16;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF62,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v21);
    if ( v9 )
    {
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0x9D1,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
          v10);
    }
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140325bf4  mov     [rsp+arg_8], rbx
0x140325bf9  mov     [rsp+arg_18], rbp
0x140325bfe  push    rsi
0x140325bff  push    rdi
0x140325c00  push    r13
0x140325c02  push    r14
0x140325c04  push    r15
0x140325c06  sub     rsp, 30h
0x140325c0a  mov     rdi, r8
0x140325c0d  mov     rbx, rdx
0x140325c10  mov     r15, rcx
0x140325c13  test    rdx, rdx
0x140325c16  jz      loc_140325E09
0x140325c1c  mov     qword ptr [rsp+58h+var_38], rdx; int
0x140325c21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140325c28  mov     r13d, 88h
0x140325c2e  mov     ecx, r13d; unsigned __int64
0x140325c31  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140325c36  mov     rsi, rax
0x140325c39  mov     [rsp+58h+var_30], rax
0x140325c3e  test    rax, rax
0x140325c41  jz      short loc_140325C95
0x140325c43  cmp     qword ptr [rdi+70h], 0
0x140325c48  jnz     short loc_140325C54
0x140325c4a  mov     qword ptr [rax+70h], 0
0x140325c52  jmp     short loc_140325C84
0x140325c54  lea     rdx, [rax+8]
0x140325c58  mov     [rax+70h], rdx
0x140325c5c  mov     rcx, [rdi+70h]
0x140325c60  mov     rax, [rcx]
0x140325c63  mov     rax, [rax+10h]
0x140325c67  call    _guard_dispatch_icall
0x140325c6c  mov     rcx, [rdi+70h]
0x140325c70  mov     rax, [rcx]
0x140325c73  mov     rax, [rax+18h]
0x140325c77  call    _guard_dispatch_icall
0x140325c7c  mov     qword ptr [rdi+70h], 0
0x140325c84  mov     [rsi+78h], rbx
0x140325c88  xor     ebx, ebx
0x140325c8a  mov     [rsi+80h], rbx
0x140325c91  xor     edi, edi
0x140325c93  jmp     short loc_140325C9A
0x140325c95  xor     esi, esi
0x140325c97  mov     rdi, rbx
0x140325c9a  test    rsi, rsi
0x140325c9d  jnz     short loc_140325CDB
0x140325c9f  mov     rcx, [rsp+58h]; this
0x140325ca4  mov     esi, 8007000Eh
0x140325ca9  mov     r9d, esi; char *
0x140325cac  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325cb3  mov     edx, 0F62h; void *
0x140325cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140325cbd  nop
0x140325cbe  test    rdi, rdi
0x140325cc1  jz      short loc_140325CD4
0x140325cc3  mov     rcx, rbx; hObject
0x140325cc6  call    cs:__imp_CloseHandle
0x140325ccc  test    eax, eax
0x140325cce  jz      loc_140325E20
0x140325cd4  mov     eax, esi
0x140325cd6  jmp     loc_140325DDB
0x140325cdb  xor     r8d, r8d; pcbe
0x140325cde  mov     rdx, rsi; pv
0x140325ce1  lea     rcx, ?wait_callback@?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@K@Z; pfnwa
0x140325ce8  call    cs:__imp_CreateThreadpoolWait
0x140325cee  mov     rbp, rax
0x140325cf1  mov     r14, [rsi+80h]
0x140325cf8  test    r14, r14
0x140325cfb  jz      short loc_140325D32
0x140325cfd  call    cs:__imp_GetLastError
0x140325d03  mov     edi, eax
0x140325d05  xor     r8d, r8d; pftTimeout
0x140325d08  xor     edx, edx; h
0x140325d0a  mov     rcx, r14; pwa
0x140325d0d  call    cs:__imp_SetThreadpoolWait
0x140325d13  mov     edx, 1; fCancelPendingCallbacks
0x140325d18  mov     rcx, r14; pwa
0x140325d1b  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x140325d21  mov     rcx, r14; pwa
0x140325d24  call    cs:__imp_CloseThreadpoolWait
0x140325d2a  mov     ecx, edi; dwErrCode
0x140325d2c  call    cs:__imp_SetLastError
0x140325d32  mov     [rsi+80h], rbp
0x140325d39  test    rbp, rbp
0x140325d3c  jnz     short loc_140325D84
0x140325d3e  mov     rcx, [rsp+58h]; this
0x140325d43  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325d4a  mov     edx, 0F65h; void *
0x140325d4f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140325d54  mov     edi, eax
0x140325d56  mov     rcx, rsi; this
0x140325d59  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x140325d5e  mov     rdx, r13
0x140325d61  mov     rcx, rsi; Block
0x140325d64  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140325d69  nop
0x140325d6a  test    rbx, rbx
0x140325d6d  jz      short loc_140325D80
0x140325d6f  mov     rcx, rbx; hObject
0x140325d72  call    cs:__imp_CloseHandle
0x140325d78  test    eax, eax
0x140325d7a  jz      loc_140325E37
0x140325d80  mov     eax, edi
0x140325d82  jmp     short loc_140325DDB
0x140325d84  mov     rbp, [r15]
0x140325d87  test    rbp, rbp
0x140325d8a  jz      short loc_140325DAF
0x140325d8c  call    cs:__imp_GetLastError
0x140325d92  mov     edi, eax
0x140325d94  mov     rcx, rbp; this
0x140325d97  call    ??1event_watcher_state@details@wil@@QEAA@XZ; wil::details::event_watcher_state::~event_watcher_state(void)
0x140325d9c  mov     rdx, r13
0x140325d9f  mov     rcx, rbp; Block
0x140325da2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140325da7  mov     ecx, edi; dwErrCode
0x140325da9  call    cs:__imp_SetLastError
0x140325daf  mov     [r15], rsi
0x140325db2  xor     r8d, r8d; pftTimeout
0x140325db5  mov     rdx, [rsi+78h]; h
0x140325db9  mov     rcx, [rsi+80h]; pwa
0x140325dc0  call    cs:__imp_SetThreadpoolWait
0x140325dc6  nop
0x140325dc7  test    rbx, rbx
0x140325dca  jz      short loc_140325DD9
0x140325dcc  mov     rcx, rbx; hObject
0x140325dcf  call    cs:__imp_CloseHandle
0x140325dd5  test    eax, eax
0x140325dd7  jz      short loc_140325DF2
0x140325dd9  xor     eax, eax
0x140325ddb  mov     rbx, [rsp+58h+arg_8]
0x140325de0  mov     rbp, [rsp+58h+arg_18]
0x140325de5  add     rsp, 30h
0x140325de9  pop     r15
0x140325deb  pop     r14
0x140325ded  pop     r13
0x140325def  pop     rdi
0x140325df0  pop     rsi
0x140325df1  retn
0x140325df2  mov     rcx, [rsp+58h]; this
0x140325df7  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325dfe  mov     edx, 9D1h; void *
0x140325e03  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140325e09  mov     rcx, [rsp+58h]; this
0x140325e0e  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325e15  mov     edx, 0F5Eh; void *
0x140325e1a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140325e20  mov     rcx, [rsp+58h]; this
0x140325e25  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325e2c  mov     edx, 9D1h; void *
0x140325e31  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x140325e37  mov     rcx, [rsp+58h]; this
0x140325e3c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140325e43  mov     edx, 9D1h; void *
0x140325e48  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
