# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x18001b870`
- end: `0x18001b93a`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001a538`
- `0x18001ad40`
- `0x18001b750`

## callees

- `0x180007630`
- `0x180017bfc`
- `0x18001b870`
- `0x18001b940`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001b920`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x18001b920`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001b8c7`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18001b8c7`

## string_xrefs

- `0x18001b8d6`: `onecore\internal\com\inc\comservicehelper.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::Uninitialize(Windows::Internal::ServiceModuleBase *this)
{
  __int64 v2; // rcx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v2 = *((_QWORD *)this + 3);
  if ( v2 )
  {
    v5 = 5;
    (*(void (__fastcall **)(__int64, __int64 (__fastcall *)(struct tagComCallData *), Windows::Internal::ServiceModuleBase *, GUID *))(*(_QWORD *)v2 + 24LL))(
      v2,
      Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk,
      this,
      &IID_IContextCallback);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 24);
  }
  if ( *((_BYTE *)this + 21) )
  {
    v3 = CoRegisterServerShutdownDelay(0, 0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xA1,
        (unsigned int)"onecore\\internal\\com\\inc\\comservicehelper.h",
        (const char *)(unsigned int)v3,
        v5);
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
0x18001b870  mov     [rsp+arg_0], rbx
0x18001b875  push    rdi
0x18001b876  sub     rsp, 40h
0x18001b87a  mov     rbx, rcx
0x18001b87d  mov     rcx, [rcx+18h]
0x18001b881  test    rcx, rcx
0x18001b884  jz      short loc_18001B8BD
0x18001b886  mov     rax, [rcx]
0x18001b889  lea     r9, IID_IContextCallback
0x18001b890  mov     [rsp+48h+var_20], 0
0x18001b899  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x18001b8a0  mov     r8, rbx
0x18001b8a3  mov     [rsp+48h+var_28], 5; int
0x18001b8ab  mov     rax, [rax+18h]
0x18001b8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8b4  lea     rcx, [rbx+18h]
0x18001b8b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001b8bd  cmp     byte ptr [rbx+15h], 0
0x18001b8c1  jz      short loc_18001B8EE
0x18001b8c3  xor     edx, edx
0x18001b8c5  xor     ecx, ecx
0x18001b8c7  call    cs:__imp_CoRegisterServerShutdownDelay
0x18001b8cd  test    eax, eax
0x18001b8cf  jns     short loc_18001B8EA
0x18001b8d1  mov     rcx, [rsp+48h]; this
0x18001b8d6  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x18001b8dd  mov     r9d, eax; char *
0x18001b8e0  mov     edx, 0A1h; void *
0x18001b8e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001b8ea  mov     byte ptr [rbx+15h], 0
0x18001b8ee  cmp     byte ptr [rbx+14h], 0
0x18001b8f2  jz      short loc_18001B907
0x18001b8f4  mov     rax, [rbx]
0x18001b8f7  mov     rcx, rbx
0x18001b8fa  mov     rax, [rax+18h]
0x18001b8fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b903  mov     byte ptr [rbx+14h], 0
0x18001b907  cmp     dword ptr [rbx+10h], 0
0x18001b90b  jl      short loc_18001B92D
0x18001b90d  lea     rcx, [rbx+8]
0x18001b911  cmp     qword ptr [rcx], 0
0x18001b915  jz      short loc_18001B920
0x18001b917  xor     edx, edx
0x18001b919  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x18001b91e  jmp     short loc_18001B926
0x18001b920  call    cs:__imp_RoUninitialize
0x18001b926  mov     dword ptr [rbx+10h], 80004005h
0x18001b92d  mov     rbx, [rsp+48h+arg_0]
0x18001b932  xor     eax, eax
0x18001b934  add     rsp, 40h
0x18001b938  pop     rdi
0x18001b939  retn
```
