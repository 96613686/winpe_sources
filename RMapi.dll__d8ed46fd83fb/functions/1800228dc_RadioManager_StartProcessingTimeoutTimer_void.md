# RadioManager::_StartProcessingTimeoutTimer(void)

- ea: `0x1800228dc`
- end: `0x180022994`
- name: `?_StartProcessingTimeoutTimer@RadioManager@@AEAAXXZ`
- size: `184`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001b968`

## callees

- `0x1800042b0`
- `0x18000b744`
- `0x18000d2a0`
- `0x1800228dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002290d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002290d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002297b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002297b`

## string_xrefs

- `0x180022931`: `Failed to Create timer!`

## pseudocode

```c
void __fastcall RadioManager::_StartProcessingTimeoutTimer(struct _TP_TIMER **pv)
{
  struct _TP_TIMER **v1; // rbx
  struct _TP_TIMER *v3; // rcx
  PTP_TIMER ThreadpoolTimer; // rax
  int v5; // r8d
  int v6; // r9d
  int v7; // [rsp+30h] [rbp-28h] BYREF
  const char *v8; // [rsp+38h] [rbp-20h] BYREF
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-18h] BYREF

  v1 = pv + 54;
  v3 = pv[54];
  if ( v3
    || (ThreadpoolTimer = CreateThreadpoolTimer(RadioManager::ProcessingTimeoutCallback, pv, 0),
        wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
          v1,
          ThreadpoolTimer),
        (v3 = *v1) != 0) )
  {
    pftDueTime = (struct _FILETIME)-54000000LL;
    SetThreadpoolTimer(v3, &pftDueTime, 0, 0);
  }
  else if ( (unsigned int)dword_180037050 > 2 )
  {
    v7 = -2147467259;
    v8 = "Failed to Create timer!";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      0,
      (unsigned int)word_18002F09A,
      v5,
      v6,
      (__int64)&v8,
      (__int64)&v7);
  }
}

```

## disassembly

```asm
0x1800228dc  push    rbx
0x1800228de  sub     rsp, 50h
0x1800228e2  mov     rax, cs:__security_cookie
0x1800228e9  xor     rax, rsp
0x1800228ec  mov     [rsp+58h+var_10], rax
0x1800228f1  lea     rbx, [rcx+1B0h]
0x1800228f8  mov     rdx, rcx; pv
0x1800228fb  mov     rcx, [rbx]; pti
0x1800228fe  test    rcx, rcx
0x180022901  jnz     short loc_180022967
0x180022903  xor     r8d, r8d; pcbe
0x180022906  lea     rcx, ?ProcessingTimeoutCallback@RadioManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002290d  call    cs:__imp_CreateThreadpoolTimer
0x180022913  mov     rdx, rax
0x180022916  mov     rcx, rbx
0x180022919  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18002291e  mov     rcx, [rbx]
0x180022921  test    rcx, rcx
0x180022924  jnz     short loc_180022967
0x180022926  mov     eax, cs:dword_180037050
0x18002292c  cmp     eax, 2
0x18002292f  jbe     short loc_180022981
0x180022931  lea     rax, aFailedToCreate; "Failed to Create timer!"
0x180022938  mov     [rsp+58h+var_28], 80004005h
0x180022940  mov     [rsp+58h+var_20], rax
0x180022945  lea     rdx, word_18002F09A
0x18002294c  lea     rax, [rsp+58h+var_28]
0x180022951  mov     [rsp+58h+var_30], rax
0x180022956  lea     rax, [rsp+58h+var_20]
0x18002295b  mov     [rsp+58h+var_38], rax
0x180022960  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180022965  jmp     short loc_180022981
0x180022967  xor     r9d, r9d; msWindowLength
0x18002296a  mov     qword ptr [rsp+58h+pftDueTime.dwLowDateTime], 0FFFFFFFFFCC80680h
0x180022973  xor     r8d, r8d; msPeriod
0x180022976  lea     rdx, [rsp+58h+pftDueTime]; pftDueTime
0x18002297b  call    cs:__imp_SetThreadpoolTimer
0x180022981  mov     rcx, [rsp+58h+var_10]
0x180022986  xor     rcx, rsp; StackCookie
0x180022989  call    __security_check_cookie
0x18002298e  add     rsp, 50h
0x180022992  pop     rbx
0x180022993  retn
```
