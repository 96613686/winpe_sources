# TimeUpdate::SubscribeForNlmNotifications(IConnectionPoint * *,ulong &)

- ea: `0x180009bb8`
- end: `0x180009d81`
- name: `?SubscribeForNlmNotifications@TimeUpdate@@AEAAJPEAPEAUIConnectionPoint@@AEAK@Z`
- size: `457`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, struct IConnectionPoint **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800081ac`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180005658`
- `0x180005f40`
- `0x180009194`
- `0x180009bb8`
- `0x18000a4cc`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009c19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009c19`

## string_xrefs

- `0x180009c51`: `onecore\base\time\autotime\timeservice\timeupdate.cpp`

## pseudocode

```c
__int64 __fastcall TimeUpdate::SubscribeForNlmNotifications(
        struct _RTL_CRITICAL_SECTION *this,
        struct IConnectionPoint **a2,
        unsigned int *a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // r8
  struct IConnectionPoint *v11; // rax
  LPVOID ppv; // [rsp+30h] [rbp-10h] BYREF
  __int64 v14; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  NLM_CONNECTIVITY v16; // [rsp+70h] [rbp+30h] BYREF
  struct IConnectionPoint *v17; // [rsp+78h] [rbp+38h] BYREF

  ppv = 0;
  v14 = 0;
  v17 = 0;
  v16 = NLM_CONNECTIVITY_DISCONNECTED;
  *a3 = 0;
  v6 = CoCreateInstance(
         &GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b,
         0,
         0x17u,
         &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b,
         &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 984;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (int)"onecore\\base\\time\\autotime\\timeservice\\timeupdate.cpp",
      (const char *)(unsigned int)v6);
    goto LABEL_16;
  }
  v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(
         ppv,
         &GUID_b196b284_bab4_101a_b69c_00aa00341d07,
         &v14);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 987;
    goto LABEL_5;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, GUID *, struct IConnectionPoint **))(*(_QWORD *)v14 + 32LL))(
         v14,
         &GUID_dcb00001_570f_4a9b_8d69_199fdba5723b,
         &v17);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 990;
    goto LABEL_5;
  }
  v6 = ((__int64 (__fastcall *)(struct IConnectionPoint *, struct _RTL_CRITICAL_SECTION *, unsigned int *))v17->lpVtbl->Advise)(
         v17,
         this,
         a3);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 992;
    goto LABEL_5;
  }
  v9 = (*(__int64 (__fastcall **)(LPVOID, NLM_CONNECTIVITY *))(*(_QWORD *)ppv + 104LL))(ppv, &v16);
  v7 = v9;
  if ( v9 >= 0 )
  {
    v11 = v17;
    v17 = 0;
    *a2 = v11;
    if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 512) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_18001C010,
        (__int64)&byte_1800165F7,
        0,
        0);
    TimeUpdate::ConnectivityChanged(this, v16, 1);
    v7 = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x3E2, v10, (const char *)(unsigned int)v9);
    ((void (__fastcall *)(struct IConnectionPoint *, _QWORD))v17->lpVtbl->Unadvise)(v17, *a3);
    *a3 = 0;
  }
LABEL_16:
  wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>((__int64 *)&v17);
  wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(&v14);
  wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>((__int64 *)&ppv);
  return v7;
}

```

## disassembly

```asm
0x180009bb8  mov     [rsp-18h+arg_0], rbx
0x180009bbd  mov     [rsp-18h+arg_8], rsi
0x180009bc2  push    rbp
0x180009bc3  push    rdi
0x180009bc4  push    r14
0x180009bc6  mov     rbp, rsp
0x180009bc9  sub     rsp, 40h
0x180009bcd  mov     rdi, r8
0x180009bd0  mov     r14, rdx
0x180009bd3  mov     rsi, rcx
0x180009bd6  mov     [rbp+var_10], 0
0x180009bde  mov     [rbp+var_8], 0
0x180009be6  mov     [rbp+arg_18], 0
0x180009bee  mov     [rbp+arg_10], 0
0x180009bf5  mov     dword ptr [r8], 0
0x180009bfc  lea     rax, [rbp+var_10]
0x180009c00  mov     [rsp+40h+ppv], rax; int
0x180009c05  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x180009c0c  xor     edx, edx; pUnkOuter
0x180009c0e  lea     r8d, [rdx+17h]; dwClsContext
0x180009c12  lea     rcx, _GUID_dcb00c01_570f_4a9b_8d69_199fdba5723b; rclsid
0x180009c19  call    cs:__imp_CoCreateInstance
0x180009c1f  mov     ebx, eax
0x180009c21  test    eax, eax
0x180009c23  jns     short loc_180009C2C
0x180009c25  mov     edx, 3D8h
0x180009c2a  jmp     short loc_180009C51
0x180009c2c  mov     rcx, [rbp+var_10]
0x180009c30  mov     rax, [rcx]
0x180009c33  lea     r8, [rbp+var_8]
0x180009c37  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x180009c3e  mov     rax, [rax]
0x180009c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c46  mov     ebx, eax
0x180009c48  test    eax, eax
0x180009c4a  jns     short loc_180009C69
0x180009c4c  mov     edx, 3DBh; void *
0x180009c51  lea     r8, aOnecoreBaseTim_3; "onecore\\base\\time\\autotime\\timeserv"...
0x180009c58  mov     r9d, eax; char *
0x180009c5b  mov     rcx, [rbp+18h]; this
0x180009c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c64  jmp     loc_180009D51
0x180009c69  mov     rcx, [rbp+var_8]
0x180009c6d  mov     rax, [rcx]
0x180009c70  lea     r8, [rbp+arg_18]
0x180009c74  lea     rdx, _GUID_dcb00001_570f_4a9b_8d69_199fdba5723b
0x180009c7b  mov     rax, [rax+20h]
0x180009c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c84  mov     ebx, eax
0x180009c86  test    eax, eax
0x180009c88  jns     short loc_180009C91
0x180009c8a  mov     edx, 3DEh
0x180009c8f  jmp     short loc_180009C51
0x180009c91  mov     rcx, [rbp+arg_18]
0x180009c95  mov     rax, [rcx]
0x180009c98  mov     r8, rdi
0x180009c9b  mov     rdx, rsi
0x180009c9e  mov     rax, [rax+28h]
0x180009ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca7  mov     ebx, eax
0x180009ca9  test    eax, eax
0x180009cab  jns     short loc_180009CB4
0x180009cad  mov     edx, 3E0h
0x180009cb2  jmp     short loc_180009C51
0x180009cb4  mov     rcx, [rbp+var_10]
0x180009cb8  mov     rax, [rcx]
0x180009cbb  lea     rdx, [rbp+arg_10]
0x180009cbf  mov     rax, [rax+68h]
0x180009cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cc8  mov     ebx, eax
0x180009cca  test    eax, eax
0x180009ccc  jns     short loc_180009CF9
0x180009cce  mov     rcx, [rbp+18h]; this
0x180009cd2  mov     r9d, eax; char *
0x180009cd5  mov     edx, 3E2h; void *
0x180009cda  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180009cdf  mov     rcx, [rbp+arg_18]
0x180009ce3  mov     rdx, [rcx]
0x180009ce6  mov     rax, [rdx+30h]
0x180009cea  mov     edx, [rdi]
0x180009cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cf1  mov     dword ptr [rdi], 0
0x180009cf7  jmp     short loc_180009D51
0x180009cf9  mov     rax, [rbp+arg_18]
0x180009cfd  mov     [rbp+arg_18], 0
0x180009d05  mov     [r14], rax
0x180009d08  mov     eax, cs:dword_18001C010
0x180009d0e  cmp     eax, 4
0x180009d11  jbe     short loc_180009D41
0x180009d13  mov     edx, 200h
0x180009d18  lea     rcx, dword_18001C010
0x180009d1f  call    _tlgKeywordOn
0x180009d24  test    al, al
0x180009d26  jz      short loc_180009D41
0x180009d28  xor     r9d, r9d
0x180009d2b  xor     r8d, r8d
0x180009d2e  lea     rdx, byte_1800165F7
0x180009d35  lea     rcx, dword_18001C010
0x180009d3c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180009d41  mov     r8b, 1; bool
0x180009d44  mov     edx, [rbp+arg_10]; enum NLM_CONNECTIVITY
0x180009d47  mov     rcx, rsi; this
0x180009d4a  call    ?ConnectivityChanged@TimeUpdate@@AEAAXW4NLM_CONNECTIVITY@@_N@Z; TimeUpdate::ConnectivityChanged(NLM_CONNECTIVITY,bool)
0x180009d4f  xor     ebx, ebx
0x180009d51  lea     rcx, [rbp+arg_18]
0x180009d55  call    ??1?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(void)
0x180009d5a  lea     rcx, [rbp+var_8]
0x180009d5e  call    ??1?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(void)
0x180009d63  lea     rcx, [rbp+var_10]
0x180009d67  call    ??1?$com_ptr_t@UINetworkListManager@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INetworkListManager,wil::err_exception_policy>::~com_ptr_t<INetworkListManager,wil::err_exception_policy>(void)
0x180009d6c  mov     eax, ebx
0x180009d6e  mov     rbx, [rsp+40h+arg_0]
0x180009d73  mov     rsi, [rsp+40h+arg_8]
0x180009d78  add     rsp, 40h
0x180009d7c  pop     r14
0x180009d7e  pop     rdi
0x180009d7f  pop     rbp
0x180009d80  retn
```
