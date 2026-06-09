# HNS::Service::Util::details::ServiceMonitor::~ServiceMonitor(void)

- ea: `0x18023f610`
- end: `0x18023f76f`
- name: `??1ServiceMonitor@details@Util@Service@HNS@@QEAA@XZ`
- size: `351`
- prototype: `void __fastcall(HNS::Service::Util::details::ServiceMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18023f82c`

## callees

- `0x180064018`
- `0x18006c530`
- `0x18023f478`
- `0x18023f610`

## import_xrefs

- `msvcp_win!_Thrd_join` at `0x18023f662`
- `msvcp_win!_Thrd_join` at `0x18023f662`
- `msvcp_win!_Thrd_id` at `0x18023f63a`
- `msvcp_win!_Thrd_id` at `0x18023f63a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f64a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f671`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f64a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18023f671`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18023f708`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18023f708`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f626`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18023f626`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18023f6ba`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18023f6ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18023f69c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18023f69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023f689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18023f689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6c9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18023f6ef`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023f694`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023f718`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023f694`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18023f718`

## pseudocode

```c
void __fastcall HNS::Service::Util::details::ServiceMonitor::~ServiceMonitor(
        HNS::Service::Util::details::ServiceMonitor *this)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  SC_HANDLE v4; // rsi
  DWORD LastError; // ebx
  void *v6; // rcx
  unsigned int v7; // r8d
  const char *v8; // r9
  void *v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  void *v12; // rcx
  unsigned int v13; // r8d
  const char *v14; // r9
  SC_HANDLE v15; // rcx
  _Thrd_t v16; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !SetEvent(*((HANDLE *)this + 9)) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v2, v3);
  if ( *((_DWORD *)this + 6) )
  {
    if ( *((_DWORD *)this + 6) == _Thrd_id() )
    {
      std::_Throw_Cpp_error(5);
      __debugbreak();
    }
    v16 = (_Thrd_t)*((_OWORD *)this + 1);
    if ( _Thrd_join(&v16, 0) )
    {
      std::_Throw_Cpp_error(2);
      __debugbreak();
    }
    *((_OWORD *)this + 1) = 0;
  }
  v4 = (SC_HANDLE)*((_QWORD *)this + 1);
  if ( v4 )
  {
    LastError = GetLastError();
    CloseServiceHandle(v4);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 1) = 0;
  std::vector<std::unique_ptr<std::function<void (enum HNS::Service::Util::ServiceState)>>>::~vector<std::unique_ptr<std::function<void (enum HNS::Service::Util::ServiceState)>>>((char *)this + 144);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 && !CloseHandle(v6) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
  v9 = (void *)*((_QWORD *)this + 9);
  if ( v9 && !CloseHandle(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
  v12 = (void *)*((_QWORD *)this + 8);
  if ( v12 && !CloseHandle(v12) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v13, v14);
  std::wstring::~wstring((char *)this + 32);
  if ( *((_DWORD *)this + 6) )
  {
    _o_terminate();
    __debugbreak();
  }
  v15 = (SC_HANDLE)*((_QWORD *)this + 1);
  if ( v15 )
    CloseServiceHandle(v15);
}

```

## disassembly

```asm
0x18023f610  mov     [rsp+arg_0], rbx
0x18023f615  mov     [rsp+arg_8], rsi
0x18023f61a  push    rdi
0x18023f61b  sub     rsp, 30h
0x18023f61f  mov     rdi, rcx
0x18023f622  mov     rcx, [rcx+48h]; hEvent
0x18023f626  call    cs:__imp_SetEvent
0x18023f62c  test    eax, eax
0x18023f62e  jz      loc_18023F73F
0x18023f634  cmp     dword ptr [rdi+18h], 0
0x18023f638  jz      short loc_18023F680
0x18023f63a  call    cs:__imp__Thrd_id
0x18023f640  cmp     [rdi+18h], eax
0x18023f643  jnz     short loc_18023F651
0x18023f645  mov     ecx, 5
0x18023f64a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18023f650  int     3; Trap to Debugger
0x18023f651  movups  xmm0, xmmword ptr [rdi+10h]
0x18023f655  movdqu  xmmword ptr [rsp+38h+var_18._Hnd], xmm0
0x18023f65b  xor     edx, edx; int *
0x18023f65d  lea     rcx, [rsp+38h+var_18]; _Thrd_t
0x18023f662  call    cs:__imp__Thrd_join
0x18023f668  test    eax, eax
0x18023f66a  jz      short loc_18023F678
0x18023f66c  mov     ecx, 2
0x18023f671  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18023f677  int     3; Trap to Debugger
0x18023f678  xorps   xmm0, xmm0
0x18023f67b  movdqu  xmmword ptr [rdi+10h], xmm0
0x18023f680  mov     rsi, [rdi+8]
0x18023f684  test    rsi, rsi
0x18023f687  jz      short loc_18023F6A2
0x18023f689  call    cs:__imp_GetLastError
0x18023f68f  mov     ebx, eax
0x18023f691  mov     rcx, rsi; hSCObject
0x18023f694  call    cs:__imp_CloseServiceHandle
0x18023f69a  mov     ecx, ebx; dwErrCode
0x18023f69c  call    cs:__imp_SetLastError
0x18023f6a2  mov     qword ptr [rdi+8], 0
0x18023f6aa  lea     rcx, [rdi+90h]
0x18023f6b1  call    ??1?$vector@V?$unique_ptr@V?$function@$$A6AXW4ServiceState@Util@Service@HNS@@@Z@std@@U?$default_delete@V?$function@$$A6AXW4ServiceState@Util@Service@HNS@@@Z@std@@@2@@std@@V?$allocator@V?$unique_ptr@V?$function@$$A6AXW4ServiceState@Util@Service@HNS@@@Z@std@@U?$default_delete@V?$function@$$A6AXW4ServiceState@Util@Service@HNS@@@Z@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<std::function<void (HNS::Service::Util::ServiceState)>>>::~vector<std::unique_ptr<std::function<void (HNS::Service::Util::ServiceState)>>>(void)
0x18023f6b6  lea     rcx, [rdi+58h]; lpCriticalSection
0x18023f6ba  call    cs:__imp_DeleteCriticalSection
0x18023f6c0  mov     rcx, [rdi+50h]; hObject
0x18023f6c4  test    rcx, rcx
0x18023f6c7  jz      short loc_18023F6D3
0x18023f6c9  call    cs:__imp_CloseHandle
0x18023f6cf  test    eax, eax
0x18023f6d1  jz      short loc_18023F74F
0x18023f6d3  mov     rcx, [rdi+48h]; hObject
0x18023f6d7  test    rcx, rcx
0x18023f6da  jz      short loc_18023F6E6
0x18023f6dc  call    cs:__imp_CloseHandle
0x18023f6e2  test    eax, eax
0x18023f6e4  jz      short loc_18023F75F
0x18023f6e6  mov     rcx, [rdi+40h]; hObject
0x18023f6ea  test    rcx, rcx
0x18023f6ed  jz      short loc_18023F6F9
0x18023f6ef  call    cs:__imp_CloseHandle
0x18023f6f5  test    eax, eax
0x18023f6f7  jz      short loc_18023F72F
0x18023f6f9  lea     rcx, [rdi+20h]; void *
0x18023f6fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18023f702  cmp     dword ptr [rdi+18h], 0
0x18023f706  jz      short loc_18023F70F
0x18023f708  call    cs:__imp__o_terminate
0x18023f70e  int     3; Trap to Debugger
0x18023f70f  mov     rcx, [rdi+8]; hSCObject
0x18023f713  test    rcx, rcx
0x18023f716  jz      short loc_18023F71F
0x18023f718  call    cs:__imp_CloseServiceHandle
0x18023f71e  nop
0x18023f71f  mov     rbx, [rsp+38h+arg_0]
0x18023f724  mov     rsi, [rsp+38h+arg_8]
0x18023f729  add     rsp, 30h
0x18023f72d  pop     rdi
0x18023f72e  retn
0x18023f72f  mov     rcx, [rsp+38h]; this
0x18023f734  mov     edx, 0A0Bh; void *
0x18023f739  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18023f73f  mov     rcx, [rsp+38h]; this
0x18023f744  mov     edx, 0A01h; void *
0x18023f749  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18023f74f  mov     rcx, [rsp+38h]; this
0x18023f754  mov     edx, 0A0Bh; void *
0x18023f759  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18023f75f  mov     rcx, [rsp+38h]; this
0x18023f764  mov     edx, 0A0Bh; void *
0x18023f769  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
