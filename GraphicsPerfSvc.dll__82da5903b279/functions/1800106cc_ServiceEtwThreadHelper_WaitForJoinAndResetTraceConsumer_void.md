# ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(void)

- ea: `0x1800106cc`
- end: `0x1800107a9`
- name: `?WaitForJoinAndResetTraceConsumer@ServiceEtwThreadHelper@@QEAAXXZ`
- size: `221`
- prototype: `void __fastcall(ServiceEtwThreadHelper *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18000e7f8`
- `0x1800102e0`

## callees

- `0x180005c6c`
- `0x18000d67c`
- `0x1800106cc`
- `0x1800112d4`
- `0x18001af04`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800106e3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001073f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001073f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ServiceEtwThreadHelper::WaitForJoinAndResetTraceConsumer(HANDLE **this)
{
  std::_Ref_count_base *v2; // rbx
  PresentTraceConsumerCore *v3; // rsi
  DWORD v4; // eax
  unsigned int i; // edi
  struct _RTL_CRITICAL_SECTION *v6; // [rsp+68h] [rbp+10h] BYREF

  EnterCriticalSection(&g::ShutdownCritsect);
  v6 = &g::ShutdownCritsect;
  v2 = qword_180043010;
  if ( qword_180043010 )
  {
    _InterlockedIncrement((volatile signed __int32 *)qword_180043010 + 2);
    v2 = qword_180043010;
  }
  v3 = g::spTraceConsumer;
  if ( g::spTraceConsumer )
  {
    v4 = 258;
    for ( i = 0; i < 2; ++i )
    {
      if ( !v4 )
        break;
      PresentTraceConsumerCore::StopPresentTraceSession(v3);
      v4 = *((_DWORD *)*this + 2) ? WaitForSingleObject(**this, 0x64u) : 0;
    }
    if ( *((_DWORD *)*this + 2) && v4 == 258 )
    {
      try
      {
        std::thread::detach((std::thread *)*this);
      }
      catch ( std::system_error )
      {
      }
    }
    (*(void (__fastcall **)(PresentTraceConsumerCore *, char *))(*(_QWORD *)g::spTraceConsumer + 24LL))(
      g::spTraceConsumer,
      (char *)g::spTraceConsumer + 304);
  }
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x1800106cc  push    rbx
0x1800106ce  push    rsi
0x1800106cf  push    rdi
0x1800106d0  push    r14
0x1800106d2  sub     rsp, 38h
0x1800106d6  mov     r14, rcx
0x1800106d9  lea     rbx, ?ShutdownCritsect@g@@3Vcritical_section@wil@@A; wil::critical_section g::ShutdownCritsect
0x1800106e0  mov     rcx, rbx; lpCriticalSection
0x1800106e3  call    cs:__imp_EnterCriticalSection
0x1800106e9  mov     [rsp+58h+arg_8], rbx
0x1800106ee  mov     rbx, cs:qword_180043010
0x1800106f5  test    rbx, rbx
0x1800106f8  jz      short loc_180010705
0x1800106fa  lock inc dword ptr [rbx+8]
0x1800106fe  mov     rbx, cs:qword_180043010
0x180010705  mov     rsi, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x18001070c  mov     [rsp+58h+var_38], rsi
0x180010711  mov     [rsp+58h+var_30], rbx
0x180010716  test    rsi, rsi
0x180010719  jz      short loc_180010787
0x18001071b  mov     eax, 102h
0x180010720  xor     edi, edi
0x180010722  test    eax, eax
0x180010724  jz      short loc_180010750
0x180010726  mov     rcx, rsi
0x180010729  call    ?StopPresentTraceSession@PresentTraceConsumerCore@@QEAAXW4StopTracingReasons@1@@Z; PresentTraceConsumerCore::StopPresentTraceSession(PresentTraceConsumerCore::StopTracingReasons)
0x18001072e  mov     rcx, [r14]
0x180010731  cmp     dword ptr [rcx+8], 0
0x180010735  jz      short loc_180010747
0x180010737  mov     edx, 64h ; 'd'; dwMilliseconds
0x18001073c  mov     rcx, [rcx]; hHandle
0x18001073f  call    cs:__imp_WaitForSingleObject
0x180010745  jmp     short loc_180010749
0x180010747  xor     eax, eax
0x180010749  inc     edi
0x18001074b  cmp     edi, 2
0x18001074e  jb      short loc_180010722
0x180010750  mov     rcx, [r14]; this
0x180010753  cmp     dword ptr [rcx+8], 0
0x180010757  jz      short loc_18001076D
0x180010759  cmp     eax, 102h
0x18001075e  jnz     short loc_18001076D
0x180010760  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180010765  nop
0x180010766  jmp     short loc_18001076D
0x180010768  mov     rbx, [rsp+58h+var_30]
0x18001076d  mov     rcx, cs:?spTraceConsumer@g@@3V?$shared_ptr@UServiceTraceConsumer@@@std@@A; std::shared_ptr<ServiceTraceConsumer> g::spTraceConsumer
0x180010774  mov     rax, [rcx]
0x180010777  lea     rdx, [rcx+130h]
0x18001077e  mov     rax, [rax+18h]
0x180010782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010787  test    rbx, rbx
0x18001078a  jz      short loc_180010795
0x18001078c  mov     rcx, rbx; this
0x18001078f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010794  nop
0x180010795  lea     rcx, [rsp+58h+arg_8]
0x18001079a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001079f  add     rsp, 38h
0x1800107a3  pop     r14
0x1800107a5  pop     rdi
0x1800107a6  pop     rsi
0x1800107a7  pop     rbx
0x1800107a8  retn
```
