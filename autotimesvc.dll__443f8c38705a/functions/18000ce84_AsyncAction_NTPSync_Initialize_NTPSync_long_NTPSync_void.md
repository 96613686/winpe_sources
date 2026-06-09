# AsyncAction<NTPSync>::Initialize(NTPSync *,long (NTPSync::*)(void))

- ea: `0x18000ce84`
- end: `0x18000cf0a`
- name: `?Initialize@?$AsyncAction@VNTPSync@@@@QEAAJPEAVNTPSync@@P82@EAAJXZ@Z`
- size: `134`
- prototype: `__int64 __fastcall(_QWORD *pv, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000d178`

## callees

- `0x180009174`
- `0x180009194`
- `0x18000bb08`
- `0x18000ce84`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000ced0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18000ced0`

## string_xrefs

- `0x18000ce94`: `onecore\base\time\autotime\timeservice\ntpsynchelper.h`
- `0x18000ceec`: `onecore\base\time\autotime\timeservice\ntpsynchelper.h`

## pseudocode

```c
__int64 __fastcall AsyncAction<NTPSync>::Initialize(_QWORD *pv, __int64 a2)
{
  _QWORD *v3; // rbx
  PTP_WORK ThreadpoolWork; // rax
  const char *v5; // r9
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 )
  {
    *pv = a2;
    pv[1] = NTPSync::SyncTimeOverNetworkAsync;
    v3 = pv + 3;
    ThreadpoolWork = CreateThreadpoolWork(AsyncAction<NTPSync>::Callback, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      v3,
      ThreadpoolWork);
    if ( *v3 )
      return 0;
    else
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x47,
               (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\ntpsynchelper.h",
               v5);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\time\\autotime\\timeservice\\ntpsynchelper.h",
      (const char *)0x80070057LL,
      v6);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18000ce84  push    rbx; int
0x18000ce86  sub     rsp, 20h
0x18000ce8a  test    rdx, rdx
0x18000ce8d  jnz     short loc_18000CEB1
0x18000ce8f  mov     rcx, [rsp+28h]; this
0x18000ce94  lea     r8, aOnecoreBaseTim_0; "onecore\\base\\time\\autotime\\timeserv"...
0x18000ce9b  mov     ebx, 80070057h
0x18000cea0  mov     edx, 3Fh ; '?'; void *
0x18000cea5  mov     r9d, ebx; char *
0x18000cea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cead  mov     eax, ebx
0x18000ceaf  jmp     short loc_18000CF04
0x18000ceb1  mov     [rcx], rdx
0x18000ceb4  lea     rax, ?SyncTimeOverNetworkAsync@NTPSync@@AEAAJXZ; NTPSync::SyncTimeOverNetworkAsync(void)
0x18000cebb  mov     [rcx+8], rax
0x18000cebf  lea     rbx, [rcx+18h]
0x18000cec3  mov     rdx, rcx; pv
0x18000cec6  xor     r8d, r8d; pcbe
0x18000cec9  lea     rcx, ?Callback@?$AsyncAction@VNTPSync@@@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000ced0  call    cs:__imp_CreateThreadpoolWork
0x18000ced6  mov     rdx, rax
0x18000ced9  mov     rcx, rbx
0x18000cedc  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18000cee1  cmp     qword ptr [rbx], 0
0x18000cee5  jnz     short loc_18000CF02
0x18000cee7  mov     rcx, [rsp+28h]; this
0x18000ceec  lea     r8, aOnecoreBaseTim_0; "onecore\\base\\time\\autotime\\timeserv"...
0x18000cef3  mov     edx, 47h ; 'G'; void *
0x18000cef8  add     rsp, 20h
0x18000cefc  pop     rbx
0x18000cefd  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cf02  xor     eax, eax
0x18000cf04  add     rsp, 20h
0x18000cf08  pop     rbx
0x18000cf09  retn
```
