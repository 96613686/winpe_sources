# TimeUpdate::NlmThread(std::promise<long> &)

- ea: `0x1800081ac`
- end: `0x180008380`
- name: `?NlmThread@TimeUpdate@@AEAAXAEAV?$promise@J@std@@@Z`
- size: `468`
- prototype: `void __fastcall(HANDLE *this, __int64 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004c30`

## callees

- `0x180004e9c`
- `0x180005658`
- `0x1800057b4`
- `0x180005820`
- `0x180005f40`
- `0x180007e24`
- `0x180007e44`
- `0x1800081ac`
- `0x180009bb8`
- `0x180009d88`
- `0x18000a4cc`
- `0x18000a6d0`
- `0x18000a92c`
- `0x18000ab38`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800082a2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800082a2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800081c5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800081c5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008361`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180008361`

## pseudocode

```c
void __fastcall TimeUpdate::NlmThread(HANDLE *this, __int64 *a2)
{
  HRESULT v4; // eax
  __int64 v5; // r8
  int v6; // edi
  const char *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rbx
  const char *v10; // rdx
  struct IConnectionPoint *v11; // rbx
  DWORD v12; // eax
  DWORD v13; // eax
  void *v14; // rdx
  unsigned int v15; // r8d
  const char *v16; // r9
  struct IConnectionPoint *v17; // rdi
  unsigned int v18[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v20; // [rsp+58h] [rbp+28h] BYREF
  struct IConnectionPoint *v21; // [rsp+60h] [rbp+30h] BYREF
  SC_HANDLE v22; // [rsp+68h] [rbp+38h] BYREF

  v4 = CoInitializeEx(0, 0);
  v6 = v4;
  if ( v4 < 0 )
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x37C, v5, (const char *)(unsigned int)v4);
  if ( !(unsigned __int8)std::_State_manager<long>::valid(a2) || !(unsigned __int8)std::_State_manager<long>::valid(v8) )
    std::_Throw_future_error2(4, v7);
  v9 = *a2;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v18, v9 + 32);
  if ( *(_BYTE *)(v9 + 193) )
    std::_Throw_future_error2(3, v10);
  *(_DWORD *)(v9 + 12) = v6;
  (*(void (__fastcall **)(__int64, unsigned int *, _QWORD))(*(_QWORD *)v9 + 40LL))(v9, v18, 0);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>((__int64)v18);
  if ( v6 >= 0 )
  {
    v22 = 0;
    v11 = 0;
    v21 = 0;
    v20 = 0;
    while ( 1 )
    {
      if ( v11 || (TimeUpdate::SubscribeForNlmNotifications((TimeUpdate *)this, &v21, &v20), (v11 = v21) != 0) )
        v12 = TimeUpdate::SubscribeForNlmService(this, &v22);
      else
        v12 = 5000;
      v13 = WaitForSingleObjectEx(this[73], v12, v12 == -1);
      if ( !v13 )
        break;
      if ( v13 == -1 )
      {
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x3A8, v15, v16);
        break;
      }
      if ( v13 == 192 )
      {
        if ( (unsigned int)std::_Atomic_storage<unsigned long,4>::load(this + 72) != 4 )
        {
          if ( v11 )
          {
            v17 = v11;
            ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v11->lpVtbl->Unadvise)(v11, v20);
            v11 = 0;
            v21 = 0;
            ((void (__fastcall *)(struct IConnectionPoint *))v17->lpVtbl->Release)(v17);
            v20 = 0;
          }
          TimeUpdate::ConnectivityChanged((struct _RTL_CRITICAL_SECTION *)this, NLM_CONNECTIVITY_DISCONNECTED, 0);
        }
      }
      else
      {
        wil::details::in1diag3::Log_Win32(retaddr, v14, v15, (const char *)v13, v18[0]);
      }
    }
    if ( v11 )
      ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v11->lpVtbl->Unadvise)(v11, v20);
    wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>((__int64 *)&v21);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v22);
    CoUninitialize();
  }
}

```

## disassembly

```asm
0x1800081ac  mov     [rsp-18h+arg_0], rbx
0x1800081b1  push    rbp
0x1800081b2  push    rsi
0x1800081b3  push    rdi
0x1800081b4  mov     rbp, rsp
0x1800081b7  sub     rsp, 30h
0x1800081bb  mov     rbx, rdx
0x1800081be  mov     rsi, rcx
0x1800081c1  xor     edx, edx; dwCoInit
0x1800081c3  xor     ecx, ecx; pvReserved
0x1800081c5  call    cs:__imp_CoInitializeEx
0x1800081cb  mov     edi, eax
0x1800081cd  mov     rcx, [rbp+18h]; this
0x1800081d1  test    eax, eax
0x1800081d3  jns     short loc_1800081E2
0x1800081d5  mov     r9d, eax; char *
0x1800081d8  mov     edx, 37Ch; void *
0x1800081dd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800081e2  mov     rcx, rbx
0x1800081e5  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x1800081ea  test    al, al
0x1800081ec  jz      loc_180008375
0x1800081f2  call    ?valid@?$_State_manager@J@std@@QEBA_NXZ; std::_State_manager<long>::valid(void)
0x1800081f7  test    al, al
0x1800081f9  jz      loc_180008375
0x1800081ff  mov     rbx, [rbx]
0x180008202  lea     rdx, [rbx+20h]
0x180008206  lea     rcx, [rbp+var_10]
0x18000820a  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x18000820f  cmp     byte ptr [rbx+0C1h], 0
0x180008216  jz      short loc_180008223
0x180008218  mov     ecx, 3
0x18000821d  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180008223  mov     [rbx+0Ch], edi
0x180008226  mov     rax, [rbx]
0x180008229  xor     r8d, r8d
0x18000822c  lea     rdx, [rbp+var_10]
0x180008230  mov     rcx, rbx
0x180008233  mov     rax, [rax+28h]
0x180008237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823c  lea     rcx, [rbp+var_10]
0x180008240  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180008245  test    edi, edi
0x180008247  js      loc_180008368
0x18000824d  mov     [rbp+arg_18], 0
0x180008255  xor     ebx, ebx
0x180008257  mov     [rbp+arg_10], rbx
0x18000825b  mov     [rbp+arg_8], ebx
0x18000825e  test    rbx, rbx
0x180008261  jnz     short loc_18000827C
0x180008263  lea     r8, [rbp+arg_8]; unsigned int *
0x180008267  lea     rdx, [rbp+arg_10]; struct IConnectionPoint **
0x18000826b  mov     rcx, rsi; this
0x18000826e  call    ?SubscribeForNlmNotifications@TimeUpdate@@AEAAJPEAPEAUIConnectionPoint@@AEAK@Z; TimeUpdate::SubscribeForNlmNotifications(IConnectionPoint * *,ulong &)
0x180008273  mov     rbx, [rbp+arg_10]
0x180008277  test    rbx, rbx
0x18000827a  jz      short loc_18000828A
0x18000827c  lea     rdx, [rbp+arg_18]
0x180008280  mov     rcx, rsi
0x180008283  call    ?SubscribeForNlmService@TimeUpdate@@AEAAKAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; TimeUpdate::SubscribeForNlmService(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &)
0x180008288  jmp     short loc_18000828F
0x18000828a  mov     eax, 1388h
0x18000828f  xor     r8d, r8d
0x180008292  cmp     eax, 0FFFFFFFFh
0x180008295  setz    r8b; bAlertable
0x180008299  mov     edx, eax; dwMilliseconds
0x18000829b  mov     rcx, [rsi+248h]; hHandle
0x1800082a2  call    cs:__imp_WaitForSingleObjectEx
0x1800082a8  test    eax, eax
0x1800082aa  jz      loc_180008338
0x1800082b0  cmp     eax, 0FFFFFFFFh
0x1800082b3  jz      short loc_18000832A
0x1800082b5  cmp     eax, 0C0h
0x1800082ba  jz      short loc_1800082CA
0x1800082bc  mov     rcx, [rbp+18h]; this
0x1800082c0  mov     r9d, eax; char *
0x1800082c3  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x1800082c8  jmp     short loc_18000825E
0x1800082ca  lea     rcx, [rsi+240h]
0x1800082d1  call    ?load@?$_Atomic_storage@K$03@std@@QEBAKW4memory_order@2@@Z; std::_Atomic_storage<ulong,4>::load(std::memory_order)
0x1800082d6  cmp     eax, 4
0x1800082d9  jz      short loc_18000825E
0x1800082db  test    rbx, rbx
0x1800082de  jz      short loc_180008318
0x1800082e0  mov     rdi, rbx
0x1800082e3  mov     rax, [rbx]
0x1800082e6  mov     edx, [rbp+arg_8]
0x1800082e9  mov     rcx, rbx
0x1800082ec  mov     rax, [rax+30h]
0x1800082f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f5  nop
0x1800082f6  xor     ebx, ebx
0x1800082f8  mov     [rbp+arg_10], rbx
0x1800082fc  test    rdi, rdi
0x1800082ff  jz      short loc_180008311
0x180008301  mov     rax, [rdi]
0x180008304  mov     rcx, rdi
0x180008307  mov     rax, [rax+10h]
0x18000830b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008310  nop
0x180008311  mov     [rbp+arg_8], 0
0x180008318  xor     r8d, r8d; bool
0x18000831b  xor     edx, edx; enum NLM_CONNECTIVITY
0x18000831d  mov     rcx, rsi; this
0x180008320  call    ?ConnectivityChanged@TimeUpdate@@AEAAXW4NLM_CONNECTIVITY@@_N@Z; TimeUpdate::ConnectivityChanged(NLM_CONNECTIVITY,bool)
0x180008325  jmp     loc_18000825E
0x18000832a  mov     rcx, [rbp+18h]; this
0x18000832e  mov     edx, 3A8h; void *
0x180008333  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x180008338  test    rbx, rbx
0x18000833b  jz      short loc_18000834F
0x18000833d  mov     rax, [rbx]
0x180008340  mov     edx, [rbp+arg_8]
0x180008343  mov     rcx, rbx
0x180008346  mov     rax, [rax+30h]
0x18000834a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000834f  lea     rcx, [rbp+arg_10]
0x180008353  call    ??1?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(void)
0x180008358  lea     rcx, [rbp+arg_18]
0x18000835c  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x180008361  call    cs:__imp_CoUninitialize
0x180008367  nop
0x180008368  mov     rbx, [rsp+30h+arg_0]
0x18000836d  add     rsp, 30h
0x180008371  pop     rdi
0x180008372  pop     rsi
0x180008373  pop     rbp
0x180008374  retn
0x180008375  mov     ecx, 4
0x18000837a  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
