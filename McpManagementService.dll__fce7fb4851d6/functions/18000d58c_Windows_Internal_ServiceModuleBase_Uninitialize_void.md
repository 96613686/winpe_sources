# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x18000d58c`
- end: `0x18000d64a`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `190`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800050e4`
- `0x1800073d0`
- `0x18000c570`

## callees

- `0x180009fc0`
- `0x18000d58c`
- `0x18000e128`
- `0x18000e73c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000d630`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18000d630`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000d5e3`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000d5e3`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Uninitialize(Windows::Internal::ServiceModuleBase *this)
{
  __int64 v2; // rcx
  int v3; // eax
  void *v4; // rdx
  __int64 v5; // r8
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *, int, _QWORD))(*(_QWORD *)v2 + 24LL))(
      v2,
      Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk,
      this,
      &IID_IContextCallback,
      5,
      0);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)this + 3);
  }
  if ( *((_BYTE *)this + 21) )
  {
    v3 = CoRegisterServerShutdownDelay(0, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(retaddr, v4, v5, (const char *)(unsigned int)v3);
    *((_BYTE *)this + 21) = 0;
  }
  if ( *((_BYTE *)this + 20) )
  {
    (*(void (__fastcall **)(Windows::Internal::ServiceModuleBase *))(*(_QWORD *)this + 24LL))(this);
    *((_BYTE *)this + 20) = 0;
  }
  if ( *((int *)this + 4) >= 0 )
  {
    if ( *((_QWORD *)this + 1) )
      wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(
        (char *)this + 8,
        0);
    else
      RoUninitialize();
    *((_DWORD *)this + 4) = -2147467259;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d58c  mov     [rsp+arg_0], rbx
0x18000d591  push    rdi
0x18000d592  sub     rsp, 40h
0x18000d596  mov     rbx, rcx
0x18000d599  mov     rcx, [rcx+18h]
0x18000d59d  test    rcx, rcx
0x18000d5a0  jz      short loc_18000D5D9
0x18000d5a2  mov     rax, [rcx]
0x18000d5a5  lea     r9, IID_IContextCallback
0x18000d5ac  mov     [rsp+48h+var_20], 0
0x18000d5b5  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x18000d5bc  mov     r8, rbx
0x18000d5bf  mov     [rsp+48h+var_28], 5; int
0x18000d5c7  mov     rax, [rax+18h]
0x18000d5cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5d0  lea     rcx, [rbx+18h]
0x18000d5d4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000d5d9  cmp     byte ptr [rbx+15h], 0
0x18000d5dd  jz      short loc_18000D5FE
0x18000d5df  xor     edx, edx
0x18000d5e1  xor     ecx, ecx
0x18000d5e3  call    cs:__imp_CoRegisterServerShutdownDelay
0x18000d5e9  test    eax, eax
0x18000d5eb  jns     short loc_18000D5FA
0x18000d5ed  mov     rcx, [rsp+48h]; this
0x18000d5f2  mov     r9d, eax; char *
0x18000d5f5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d5fa  mov     byte ptr [rbx+15h], 0
0x18000d5fe  cmp     byte ptr [rbx+14h], 0
0x18000d602  jz      short loc_18000D617
0x18000d604  mov     rax, [rbx]
0x18000d607  mov     rcx, rbx
0x18000d60a  mov     rax, [rax+18h]
0x18000d60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d613  mov     byte ptr [rbx+14h], 0
0x18000d617  cmp     dword ptr [rbx+10h], 0
0x18000d61b  jl      short loc_18000D63D
0x18000d61d  lea     rcx, [rbx+8]
0x18000d621  cmp     qword ptr [rcx], 0
0x18000d625  jz      short loc_18000D630
0x18000d627  xor     edx, edx
0x18000d629  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x18000d62e  jmp     short loc_18000D636
0x18000d630  call    cs:__imp_RoUninitialize
0x18000d636  mov     dword ptr [rbx+10h], 80004005h
0x18000d63d  mov     rbx, [rsp+48h+arg_0]
0x18000d642  xor     eax, eax
0x18000d644  add     rsp, 40h
0x18000d648  pop     rdi
0x18000d649  retn
```
