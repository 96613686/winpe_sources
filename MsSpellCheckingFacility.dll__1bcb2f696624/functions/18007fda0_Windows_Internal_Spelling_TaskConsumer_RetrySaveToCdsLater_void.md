# Windows::Internal::Spelling::TaskConsumer::RetrySaveToCdsLater(void)

- ea: `0x18007fda0`
- end: `0x18007fe2c`
- name: `?RetrySaveToCdsLater@TaskConsumer@Spelling@Internal@Windows@@AEAAXXZ`
- size: `140`
- prototype: `void __fastcall(Windows::Internal::Spelling::TaskConsumer *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800ba3a7`
- `0x1800bad54`

## callees

- `0x180044c28`
- `0x18007dfbc`
- `0x18007fda0`
- `0x180080154`
- `0x1800829f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fdc6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18007fdc6`

## string_xrefs

- `0x18007fde7`: `onecoreuap\base\win32\winnls\els\advancedservices\spelling\spellcheck\current\roamingdictionarymanager.cpp`

## pseudocode

```c
void __fastcall Windows::Internal::Spelling::TaskConsumer::RetrySaveToCdsLater(
        Windows::Internal::Spelling::TaskConsumer *this,
        struct _TP_TIMER *a2,
        __int64 a3)
{
  Windows::Internal::Spelling **v4; // rdi
  PTP_TIMER ThreadpoolTimer; // rax
  const char *v6; // r9
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    v4 = (Windows::Internal::Spelling **)((char *)this + 128);
    if ( !*((_QWORD *)this + 16) )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(lambda_0038fbb65ac8f140e451efc27a5b7ef1_::_lambda_invoker_cdecl_, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v4,
        ThreadpoolTimer);
      if ( !*v4 )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0x391,
          (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdi"
                        "ctionarymanager.cpp",
          v6);
    }
    if ( ++*((_DWORD *)this + 34) > 5u )
    {
      SpellingTelemetry::CdsUploadRetryFailed();
      *((_DWORD *)this + 34) = 0;
    }
    Windows::Internal::Spelling::SetThreadpoolTimerByMillisecondsDelay(*v4, a2, a3);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\base\\win32\\winnls\\els\\advancedservices\\spelling\\spellcheck\\current\\roamingdictionarymanager.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x18007fda0  mov     [rsp+arg_0], rbx
0x18007fda5  push    rdi
0x18007fda6  sub     rsp, 20h
0x18007fdaa  mov     rbx, rcx
0x18007fdad  lea     rdi, [rcx+80h]
0x18007fdb4  cmp     qword ptr [rdi], 0
0x18007fdb8  jnz     short loc_18007FDF8
0x18007fdba  xor     r8d, r8d; pcbe
0x18007fdbd  xor     edx, edx; pv
0x18007fdbf  lea     rcx, _lambda_0038fbb65ac8f140e451efc27a5b7ef1____lambda_invoker_cdecl_; pfnti
0x18007fdc6  call    cs:__imp_CreateThreadpoolTimer
0x18007fdcc  mov     rdx, rax
0x18007fdcf  mov     rcx, rdi
0x18007fdd2  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18007fdd7  cmp     qword ptr [rdi], 0
0x18007fddb  setz    al
0x18007fdde  mov     rcx, [rsp+28h]; this
0x18007fde3  test    al, al
0x18007fde5  jz      short loc_18007FDF8
0x18007fde7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\win32\\winnls\\els\\a"...
0x18007fdee  mov     edx, 391h; void *
0x18007fdf3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18007fdf8  inc     dword ptr [rbx+88h]
0x18007fdfe  cmp     dword ptr [rbx+88h], 5
0x18007fe05  jbe     short loc_18007FE16
0x18007fe07  call    ?CdsUploadRetryFailed@SpellingTelemetry@@SAXXZ; SpellingTelemetry::CdsUploadRetryFailed(void)
0x18007fe0c  mov     dword ptr [rbx+88h], 0
0x18007fe16  mov     rcx, [rdi]; this
0x18007fe19  call    ?SetThreadpoolTimerByMillisecondsDelay@Spelling@Internal@Windows@@YAXPEAU_TP_TIMER@@_J@Z; Windows::Internal::Spelling::SetThreadpoolTimerByMillisecondsDelay(_TP_TIMER *,__int64)
0x18007fe1e  nop
0x18007fe1f  jmp     short $+2
0x18007fe21  mov     rbx, [rsp+28h+arg_0]
0x18007fe26  add     rsp, 20h
0x18007fe2a  pop     rdi
0x18007fe2b  retn
```
