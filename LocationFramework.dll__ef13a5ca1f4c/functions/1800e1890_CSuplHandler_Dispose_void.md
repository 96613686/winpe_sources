# CSuplHandler::Dispose(void)

- ea: `0x1800e1890`
- end: `0x1800e1ac8`
- name: `?Dispose@CSuplHandler@@UEAAJXZ`
- size: `568`
- prototype: `__int64 __fastcall(CSuplHandler *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c974`
- `0x180012310`
- `0x18003b92c`
- `0x18005df20`
- `0x180085578`
- `0x18009c58c`
- `0x1800a98c0`
- `0x1800e1890`
- `0x1800e4a9c`
- `0x1800e4ee8`
- `0x1800e4f14`
- `0x1800e4fdc`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800e1a15`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800e1a15`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800e1a0c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800e1a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1a63`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e1a63`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSuplHandler::Dispose(CSuplHandler *this)
{
  struct _TP_WAIT *v3; // rbx
  _QWORD *v4; // rsi
  __int64 v5; // rcx
  int v6; // eax
  int v7; // eax
  void *v8; // rdx
  unsigned int v9; // r8d
  const char *v10; // r9
  void *v11; // rcx
  __int64 v12; // [rsp+20h] [rbp-28h] BYREF
  int v13; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  v12 = 0;
  wil::EnterCriticalSection(&v12, (char *)this + 8);
  if ( *((_DWORD *)this + 14) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    return 2147500036LL;
  }
  else
  {
    *((_DWORD *)this + 14) = 1;
    v3 = (struct _TP_WAIT *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    v4 = (_QWORD *)((char *)this + 696);
    v5 = *((_QWORD *)this + 87);
    if ( v5 )
    {
      v13 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v5 + 128LL))(v5, &v13);
      if ( v6 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x6A0,
          (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
          (const char *)(unsigned int)v6,
          v12);
      if ( v13 == 1 )
      {
        v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 144LL))(*v4);
        if ( v7 < 0 )
          wil::details::in1diag3::_FailFast_Hr(
            retaddr,
            (void *)0x6A4,
            (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\gnssadapter\\suplhandler.cpp",
            (const char *)(unsigned int)v7,
            v12);
        if ( !(unsigned __int8)wil::slim_event_t<0>::wait((char *)this + 736) )
          wil::details::in1diag3::_FailFast_Unexpected(retaddr, v8, v9, v10);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 56LL))(*v4, *((_QWORD *)this + 88));
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 72LL))(*v4, *((_QWORD *)this + 89));
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 88LL))(*v4, *((_QWORD *)this + 90));
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v4 + 120LL))(*v4, *((_QWORD *)this + 91));
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 696);
      *((_QWORD *)this + 88) = 0;
      *((_QWORD *)this + 89) = 0;
      *((_QWORD *)this + 90) = 0;
      *((_QWORD *)this + 91) = 0;
    }
    if ( v3 )
    {
      WaitForThreadpoolWaitCallbacks(v3, 1);
      CloseThreadpoolWait(v3);
    }
    ResettableTimer::SetWindowLength((CSuplHandler *)((char *)this + 744), 0x1388u);
    ResettableTimer::Dispose((CSuplHandler *)((char *)this + 744));
    wil::EnterCriticalSection(&v13, (char *)this + 8);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(
      &v12,
      &v13);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v13);
    v11 = (void *)*((_QWORD *)this + 8);
    if ( v11 )
    {
      CloseHandle(v11);
      *((_QWORD *)this + 8) = 0;
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(&v12);
    return 0;
  }
}

```

## disassembly

```asm
0x1800e1890  push    rbp
0x1800e1892  push    rbx
0x1800e1893  push    rsi
0x1800e1894  push    rdi
0x1800e1895  push    r14
0x1800e1897  push    r15
0x1800e1899  mov     rbp, rsp
0x1800e189c  sub     rsp, 48h
0x1800e18a0  mov     rax, cs:__security_cookie
0x1800e18a7  xor     rax, rsp
0x1800e18aa  mov     [rbp+var_18], rax
0x1800e18ae  mov     rdi, rcx
0x1800e18b1  mov     [rbp+var_28], 0
0x1800e18b9  lea     rdx, [rcx+8]
0x1800e18bd  lea     rcx, [rbp+var_28]
0x1800e18c1  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800e18c6  nop
0x1800e18c7  cmp     dword ptr [rdi+38h], 0
0x1800e18cb  jz      short loc_1800E18E0
0x1800e18cd  lea     rcx, [rbp+var_28]
0x1800e18d1  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800e18d6  mov     eax, 80004004h
0x1800e18db  jmp     loc_1800E1A7C
0x1800e18e0  mov     dword ptr [rdi+38h], 1
0x1800e18e7  mov     rbx, [rdi+48h]
0x1800e18eb  mov     qword ptr [rdi+48h], 0
0x1800e18f3  xor     edx, edx
0x1800e18f5  lea     rcx, [rbp+var_28]
0x1800e18f9  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::reset(_RTL_CRITICAL_SECTION *)
0x1800e18fe  lea     rsi, [rdi+2B8h]
0x1800e1905  mov     rcx, [rsi]
0x1800e1908  test    rcx, rcx
0x1800e190b  jz      loc_1800E19FF
0x1800e1911  mov     [rbp+var_20], 0
0x1800e1918  mov     rax, [rcx]
0x1800e191b  lea     rdx, [rbp+var_20]
0x1800e191f  mov     rax, [rax+80h]
0x1800e1926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e192b  mov     rcx, [rbp+30h]; this
0x1800e192f  test    eax, eax
0x1800e1931  js      loc_1800E1A9E
0x1800e1937  cmp     [rbp+var_20], 1
0x1800e193b  jnz     short loc_1800E1973
0x1800e193d  mov     rcx, [rsi]
0x1800e1940  mov     rax, [rcx]
0x1800e1943  mov     rax, [rax+90h]
0x1800e194a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e194f  mov     rcx, [rbp+30h]; this
0x1800e1953  test    eax, eax
0x1800e1955  js      loc_1800E1AB3
0x1800e195b  mov     r15, [rbp+30h]
0x1800e195f  lea     rcx, [rdi+2E0h]
0x1800e1966  call    ?wait@?$slim_event_t@$0A@@wil@@QEAA_NK@Z; wil::slim_event_t<0>::wait(ulong)
0x1800e196b  test    al, al
0x1800e196d  jz      loc_1800E1A95
0x1800e1973  mov     rcx, [rsi]
0x1800e1976  mov     rax, [rcx]
0x1800e1979  mov     rdx, [rdi+2C0h]
0x1800e1980  mov     rax, [rax+38h]
0x1800e1984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1989  mov     rcx, [rsi]
0x1800e198c  mov     rax, [rcx]
0x1800e198f  mov     rdx, [rdi+2C8h]
0x1800e1996  mov     rax, [rax+48h]
0x1800e199a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e199f  mov     rcx, [rsi]
0x1800e19a2  mov     rax, [rcx]
0x1800e19a5  mov     rdx, [rdi+2D0h]
0x1800e19ac  mov     rax, [rax+58h]
0x1800e19b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e19b5  mov     rcx, [rsi]
0x1800e19b8  mov     rax, [rcx]
0x1800e19bb  mov     rdx, [rdi+2D8h]
0x1800e19c2  mov     rax, [rax+78h]
0x1800e19c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e19cb  mov     rcx, rsi
0x1800e19ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800e19d3  mov     qword ptr [rdi+2C0h], 0
0x1800e19de  mov     qword ptr [rdi+2C8h], 0
0x1800e19e9  mov     qword ptr [rdi+2D0h], 0
0x1800e19f4  mov     qword ptr [rdi+2D8h], 0
0x1800e19ff  test    rbx, rbx
0x1800e1a02  jz      short loc_1800E1A1B
0x1800e1a04  mov     edx, 1; fCancelPendingCallbacks
0x1800e1a09  mov     rcx, rbx; pwa
0x1800e1a0c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800e1a12  mov     rcx, rbx; pwa
0x1800e1a15  call    cs:__imp_CloseThreadpoolWait
0x1800e1a1b  lea     rbx, [rdi+2E8h]
0x1800e1a22  mov     edx, 1388h; unsigned int
0x1800e1a27  mov     rcx, rbx; this
0x1800e1a2a  call    ?SetWindowLength@ResettableTimer@@QEAAJK@Z; ResettableTimer::SetWindowLength(ulong)
0x1800e1a2f  mov     rcx, rbx; this
0x1800e1a32  call    ?Dispose@ResettableTimer@@QEAAXXZ; ResettableTimer::Dispose(void)
0x1800e1a37  lea     rdx, [rdi+8]
0x1800e1a3b  lea     rcx, [rbp+var_20]
0x1800e1a3f  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800e1a44  lea     rdx, [rbp+var_20]
0x1800e1a48  lea     rcx, [rbp+var_28]
0x1800e1a4c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>> &&)
0x1800e1a51  lea     rcx, [rbp+var_20]
0x1800e1a55  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800e1a5a  mov     rcx, [rdi+40h]; hObject
0x1800e1a5e  test    rcx, rcx
0x1800e1a61  jz      short loc_1800E1A71
0x1800e1a63  call    cs:__imp_CloseHandle
0x1800e1a69  mov     qword ptr [rdi+40h], 0
0x1800e1a71  lea     rcx, [rbp+var_28]
0x1800e1a75  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>(void)
0x1800e1a7a  xor     eax, eax
0x1800e1a7c  mov     rcx, [rbp+var_18]
0x1800e1a80  xor     rcx, rsp; StackCookie
0x1800e1a83  call    __security_check_cookie
0x1800e1a88  add     rsp, 48h
0x1800e1a8c  pop     r15
0x1800e1a8e  pop     r14
0x1800e1a90  pop     rdi
0x1800e1a91  pop     rsi
0x1800e1a92  pop     rbx
0x1800e1a93  pop     rbp
0x1800e1a94  retn
0x1800e1a95  mov     rcx, r15; this
0x1800e1a98  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800e1a9e  mov     r9d, eax; char *
0x1800e1aa1  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800e1aa8  mov     edx, 6A0h; void *
0x1800e1aad  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x1800e1ab3  mov     r9d, eax; char *
0x1800e1ab6  lea     r8, aOnecoreuapDriv_19; "onecoreuap\\drivers\\mobilepc\\location"...
0x1800e1abd  mov     edx, 6A4h; void *
0x1800e1ac2  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
