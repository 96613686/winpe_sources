# Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::Start(void)

- ea: `0x1800cd050`
- end: `0x1800cd14c`
- name: `?Start@AppFootprintTracer@AppFootprint@Inventory@Compat@Windows@@UEAAJXZ`
- size: `252`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AppFootprint::AppFootprintTracer *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800108d4`
- `0x180031898`
- `0x180031b3c`
- `0x1800ccc0c`
- `0x1800cd050`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd0e1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800cd0e1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd076`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd0d5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd076`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800cd0d5`

## string_xrefs

- `0x1800cd10c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800cd123`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x1800cd13a`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AppFootprint::AppFootprintTracer::Start(HANDLE *this)
{
  const char *v2; // r9
  HANDLE v3; // rsi
  __int64 (__fastcall *v4)(HANDLE); // rax
  HANDLE v5; // rcx
  int v6; // ebx
  HANDLE v7; // rcx
  const char *v8; // r9
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::GetImpl'::`2'::impl) )
  {
    if ( !ResetEvent(this[7]) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA06,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
        v2);
    v3 = this[7];
    if ( (int)Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease((__int64)(this + 3), 0) >= 0 )
    {
      v4 = (__int64 (__fastcall *)(HANDLE))this[5];
      if ( v4 )
      {
        v5 = v3;
LABEL_9:
        v6 = v4(v5);
        goto LABEL_11;
      }
    }
  }
  else if ( (int)Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease((__int64)(this + 3), 0) >= 0 )
  {
    v4 = (__int64 (__fastcall *)(HANDLE))this[5];
    if ( v4 )
    {
      v5 = 0;
      goto LABEL_9;
    }
  }
  v6 = -2147467259;
LABEL_11:
  v7 = this[7];
  if ( v6 < 0 )
  {
    if ( !SetEvent(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA01,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
  }
  else if ( !ResetEvent(v7) )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA06,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      v8);
  }
  Windows::Compat::Inventory::Service::Tracer::LogStart((Windows::Compat::Inventory::Service::Tracer *)this, v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800cd050  mov     [rsp+arg_0], rbx
0x1800cd055  mov     [rsp+arg_8], rsi
0x1800cd05a  push    rdi
0x1800cd05b  sub     rsp, 20h
0x1800cd05f  mov     rdi, rcx
0x1800cd062  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone> `wil::Feature<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::GetImpl(void)'::`2'::impl
0x1800cd069  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppFootprint_SignalWhenDone>::__private_IsEnabled(void)
0x1800cd06e  test    al, al
0x1800cd070  jz      short loc_1800CD0A5
0x1800cd072  mov     rcx, [rdi+38h]; hEvent
0x1800cd076  call    cs:__imp_ResetEvent
0x1800cd07c  test    eax, eax
0x1800cd07e  jz      loc_1800CD135
0x1800cd084  mov     rsi, [rdi+38h]
0x1800cd088  lea     rcx, [rdi+18h]
0x1800cd08c  xor     edx, edx
0x1800cd08e  call    ?DllAcquireRelease@AppFootprintModule@AppFootprint@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease(Windows::Compat::Inventory::AppFootprint::AppFootprintModule::Action)
0x1800cd093  test    eax, eax
0x1800cd095  js      short loc_1800CD0C8
0x1800cd097  mov     rax, [rdi+28h]
0x1800cd09b  test    rax, rax
0x1800cd09e  jz      short loc_1800CD0C8
0x1800cd0a0  mov     rcx, rsi
0x1800cd0a3  jmp     short loc_1800CD0BF
0x1800cd0a5  xor     edx, edx
0x1800cd0a7  lea     rcx, [rdi+18h]
0x1800cd0ab  call    ?DllAcquireRelease@AppFootprintModule@AppFootprint@Inventory@Compat@Windows@@AEAAJW4Action@12345@@Z; Windows::Compat::Inventory::AppFootprint::AppFootprintModule::DllAcquireRelease(Windows::Compat::Inventory::AppFootprint::AppFootprintModule::Action)
0x1800cd0b0  test    eax, eax
0x1800cd0b2  js      short loc_1800CD0C8
0x1800cd0b4  mov     rax, [rdi+28h]
0x1800cd0b8  test    rax, rax
0x1800cd0bb  jz      short loc_1800CD0C8
0x1800cd0bd  xor     ecx, ecx
0x1800cd0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd0c4  mov     ebx, eax
0x1800cd0c6  jmp     short loc_1800CD0CD
0x1800cd0c8  mov     ebx, 80004005h
0x1800cd0cd  mov     rcx, [rdi+38h]; hEvent
0x1800cd0d1  test    ebx, ebx
0x1800cd0d3  js      short loc_1800CD0E1
0x1800cd0d5  call    cs:__imp_ResetEvent
0x1800cd0db  test    eax, eax
0x1800cd0dd  jz      short loc_1800CD11E
0x1800cd0df  jmp     short loc_1800CD0EB
0x1800cd0e1  call    cs:__imp_SetEvent
0x1800cd0e7  test    eax, eax
0x1800cd0e9  jz      short loc_1800CD107
0x1800cd0eb  mov     edx, ebx; int
0x1800cd0ed  mov     rcx, rdi; this
0x1800cd0f0  call    ?LogStart@Tracer@Service@Inventory@Compat@Windows@@IEAAJJ@Z; Windows::Compat::Inventory::Service::Tracer::LogStart(long)
0x1800cd0f5  mov     rsi, [rsp+28h+arg_8]
0x1800cd0fa  mov     eax, ebx
0x1800cd0fc  mov     rbx, [rsp+28h+arg_0]
0x1800cd101  add     rsp, 20h
0x1800cd105  pop     rdi
0x1800cd106  retn
0x1800cd107  mov     rcx, [rsp+28h]; this
0x1800cd10c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd113  mov     edx, 0A01h; void *
0x1800cd118  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800cd11e  mov     rcx, [rsp+28h]; this
0x1800cd123  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd12a  mov     edx, 0A06h; void *
0x1800cd12f  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800cd135  mov     rcx, [rsp+28h]; this
0x1800cd13a  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800cd141  mov     edx, 0A06h; void *
0x1800cd146  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
