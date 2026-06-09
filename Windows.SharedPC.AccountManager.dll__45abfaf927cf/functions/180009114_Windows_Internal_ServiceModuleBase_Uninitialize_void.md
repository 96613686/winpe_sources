# Windows::Internal::ServiceModuleBase::Uninitialize(void)

- ea: `0x180009114`
- end: `0x1800091de`
- name: `?Uninitialize@ServiceModuleBase@Internal@Windows@@QEAAJXZ`
- size: `202`
- prototype: `__int64 __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000605c`
- `0x1800071d8`
- `0x180008920`

## callees

- `0x180005120`
- `0x180009114`
- `0x180009534`
- `0x180009610`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800091c4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x1800091c4`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000916b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x18000916b`

## string_xrefs

- `0x18000917a`: `onecore\internal\com\inc\comservicehelper.h`

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
0x180009114  mov     [rsp+arg_0], rbx
0x180009119  push    rdi
0x18000911a  sub     rsp, 40h
0x18000911e  mov     rbx, rcx
0x180009121  mov     rcx, [rcx+18h]
0x180009125  test    rcx, rcx
0x180009128  jz      short loc_180009161
0x18000912a  mov     rax, [rcx]
0x18000912d  lea     r9, IID_IContextCallback
0x180009134  mov     [rsp+48h+var_20], 0
0x18000913d  lea     rdx, ?DisconnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z; Windows::Internal::ServiceModuleBase::DisconnectCallbackThunk(tagComCallData *)
0x180009144  mov     r8, rbx
0x180009147  mov     [rsp+48h+var_28], 5; int
0x18000914f  mov     rax, [rax+18h]
0x180009153  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009158  lea     rcx, [rbx+18h]
0x18000915c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180009161  cmp     byte ptr [rbx+15h], 0
0x180009165  jz      short loc_180009192
0x180009167  xor     edx, edx
0x180009169  xor     ecx, ecx
0x18000916b  call    cs:__imp_CoRegisterServerShutdownDelay
0x180009171  test    eax, eax
0x180009173  jns     short loc_18000918E
0x180009175  mov     rcx, [rsp+48h]; this
0x18000917a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\com\\inc\\comservice"...
0x180009181  mov     r9d, eax; char *
0x180009184  mov     edx, 0A1h; void *
0x180009189  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000918e  mov     byte ptr [rbx+15h], 0
0x180009192  cmp     byte ptr [rbx+14h], 0
0x180009196  jz      short loc_1800091AB
0x180009198  mov     rax, [rbx]
0x18000919b  mov     rcx, rbx
0x18000919e  mov     rax, [rax+18h]
0x1800091a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a7  mov     byte ptr [rbx+14h], 0
0x1800091ab  cmp     dword ptr [rbx+10h], 0
0x1800091af  jl      short loc_1800091D1
0x1800091b1  lea     rcx, [rbx+8]
0x1800091b5  cmp     qword ptr [rcx], 0
0x1800091b9  jz      short loc_1800091C4
0x1800091bb  xor     edx, edx
0x1800091bd  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x1800091c2  jmp     short loc_1800091CA
0x1800091c4  call    cs:__imp_RoUninitialize
0x1800091ca  mov     dword ptr [rbx+10h], 80004005h
0x1800091d1  mov     rbx, [rsp+48h+arg_0]
0x1800091d6  xor     eax, eax
0x1800091d8  add     rsp, 40h
0x1800091dc  pop     rdi
0x1800091dd  retn
```
