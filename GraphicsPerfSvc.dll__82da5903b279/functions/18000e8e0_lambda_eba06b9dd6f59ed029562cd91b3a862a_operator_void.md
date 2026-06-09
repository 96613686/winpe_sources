# _lambda_eba06b9dd6f59ed029562cd91b3a862a_::operator()(void)

- ea: `0x18000e8e0`
- end: `0x18000e9e8`
- name: `??R_lambda_eba06b9dd6f59ed029562cd91b3a862a_@@QEBA@XZ`
- size: `264`
- prototype: `__int64 __fastcall(std::thread ***)`
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e010`

## callees

- `0x18000768c`
- `0x18000e1bc`
- `0x18000e418`
- `0x18000e5bc`
- `0x18000e700`
- `0x18000e8e0`
- `0x180010070`
- `0x180010f3c`
- `0x180011130`
- `0x1800112d4`
- `0x1800113dc`
- `0x1800115fc`
- `0x180026074`
- `0x180031010`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18000e9b3`
- `api-ms-win-shcore-thread-l1-1-0!GetProcessReference` at `0x18000e9b3`

## string_xrefs

- `0x18000e996`: `onecoreuap\windows\directx\dxg\gpm\service\service.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_eba06b9dd6f59ed029562cd91b3a862a_::operator()(std::thread ***a1)
{
  __int64 future; // rax
  __int64 *v3; // rcx
  __int64 v4; // rbx
  int v5; // ebx
  int v7[4]; // [rsp+20h] [rbp-20h] BYREF
  _BYTE v8[16]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+8h]
  __int64 v10; // [rsp+58h] [rbp+18h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  future = std::promise<void>::get_future(a1, v8);
  v11 = 30;
  if ( !(unsigned __int8)std::_State_manager<int>::valid(future) )
    std::_Throw_future_error2(4);
  v4 = *v3;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, *v3 + 32);
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4) )
  {
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v7);
    v5 = 2;
  }
  else if ( std::condition_variable::wait_for<__int64,std::ratio<1,1>,std::_Associated_state<int>::_Test_ready>(
              v4 + 112,
              (__int64)v7,
              (__int64)&v11,
              v4) )
  {
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v7);
    v5 = 0;
  }
  else
  {
    std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v7);
    v5 = 1;
  }
  std::_State_manager<int>::~_State_manager<int>(v8);
  if ( v5 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\windows\\directx\\dxg\\gpm\\service\\service.cpp",
      (const char *)0x8000FFFFLL,
      v7[0]);
  v10 = 0;
  GetProcessReference(&v10);
  ServiceEtwThreadProc();
  std::thread::detach(**a1);
  dxg::svc::Host::ShutdownService();
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
}

```

## disassembly

```asm
0x18000e8e0  mov     [rsp-8+arg_0], rbx
0x18000e8e5  mov     [rsp-8+arg_18], rdi
0x18000e8ea  push    rbp
0x18000e8eb  mov     rbp, rsp
0x18000e8ee  sub     rsp, 40h
0x18000e8f2  mov     rdi, rcx
0x18000e8f5  lea     rdx, [rbp+var_10]
0x18000e8f9  call    ?get_future@?$promise@X@std@@QEAA?AV?$future@X@2@XZ; std::promise<void>::get_future(void)
0x18000e8fe  mov     rcx, rax
0x18000e901  mov     [rbp+arg_10], 1Eh
0x18000e909  call    ?valid@?$_State_manager@H@std@@QEBA_NXZ; std::_State_manager<int>::valid(void)
0x18000e90e  test    al, al
0x18000e910  jnz     short loc_18000E91D
0x18000e912  mov     ecx, 4
0x18000e917  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x18000e91d  mov     rbx, [rcx]
0x18000e920  lea     rdx, [rbx+20h]
0x18000e924  lea     rcx, [rbp+var_20]
0x18000e928  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000e92d  mov     rax, [rbx]
0x18000e930  mov     rcx, rbx
0x18000e933  mov     rax, [rax+18h]
0x18000e937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e93c  test    al, al
0x18000e93e  jz      short loc_18000E950
0x18000e940  lea     rcx, [rbp+var_20]
0x18000e944  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000e949  mov     ebx, 2
0x18000e94e  jmp     short loc_18000E97F
0x18000e950  lea     rcx, [rbx+70h]
0x18000e954  mov     r9, rbx
0x18000e957  lea     r8, [rbp+arg_10]
0x18000e95b  lea     rdx, [rbp+var_20]
0x18000e95f  call    ??$wait_for@_JU?$ratio@$00$00@std@@U_Test_ready@?$_Associated_state@H@2@@condition_variable@std@@QEAA_NAEAV?$unique_lock@Vmutex@std@@@1@AEBV?$duration@_JU?$ratio@$00$00@std@@@chrono@1@U_Test_ready@?$_Associated_state@H@1@@Z; std::condition_variable::wait_for<__int64,std::ratio<1,1>,std::_Associated_state<int>::_Test_ready>(std::unique_lock<std::mutex> &,std::chrono::duration<__int64,std::ratio<1,1>> const &,std::_Associated_state<int>::_Test_ready)
0x18000e964  lea     rcx, [rbp+var_20]
0x18000e968  test    al, al
0x18000e96a  jz      short loc_18000E975
0x18000e96c  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000e971  xor     ebx, ebx
0x18000e973  jmp     short loc_18000E97F
0x18000e975  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x18000e97a  mov     ebx, 1
0x18000e97f  lea     rcx, [rbp+var_10]
0x18000e983  call    ??1?$_State_manager@H@std@@QEAA@XZ; std::_State_manager<int>::~_State_manager<int>(void)
0x18000e988  mov     rcx, [rbp+8]; this
0x18000e98c  test    ebx, ebx
0x18000e98e  jz      short loc_18000E9A7
0x18000e990  mov     r9d, 8000FFFFh; char *
0x18000e996  lea     r8, aOnecoreuapWind; "onecoreuap\\windows\\directx\\dxg\\gpm"...
0x18000e99d  mov     edx, 7Eh ; '~'; void *
0x18000e9a2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e9a7  mov     [rbp+arg_8], 0
0x18000e9af  lea     rcx, [rbp+arg_8]
0x18000e9b3  call    cs:__imp_GetProcessReference
0x18000e9b9  call    ?ServiceEtwThreadProc@@YAXXZ; ServiceEtwThreadProc(void)
0x18000e9be  mov     rcx, [rdi]
0x18000e9c1  mov     rcx, [rcx]; this
0x18000e9c4  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x18000e9c9  call    ?ShutdownService@Host@svc@dxg@@SAXXZ; dxg::svc::Host::ShutdownService(void)
0x18000e9ce  nop
0x18000e9cf  lea     rcx, [rbp+arg_8]
0x18000e9d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e9d8  mov     rbx, [rsp+40h+arg_0]
0x18000e9dd  mov     rdi, [rsp+40h+arg_18]
0x18000e9e2  add     rsp, 40h
0x18000e9e6  pop     rbp
0x18000e9e7  retn
```
