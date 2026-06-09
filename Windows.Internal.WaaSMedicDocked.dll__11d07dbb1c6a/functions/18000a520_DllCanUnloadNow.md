# DllCanUnloadNow

- ea: `0x18000a520`
- end: `0x18000a5ea`
- name: `DllCanUnloadNow`
- size: `202`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000212d`
- `0x18000a520`
- `0x18000b1e4`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000a543`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000a543`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // edi
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  PSLIST_ENTRY v3; // r8
  struct _SLIST_ENTRY *Next; // r9
  struct _SLIST_ENTRY *v5; // rsi
  __int128 v6; // rt0
  unsigned __int8 v7; // tt

  InitOnceExecuteOnce(
    &Microsoft::WRL::Module<1,Microsoft::WRL::Details::DefaultModule<1>>::initOnceInProc_,
    _lambda_5f1dd388c03885d19ee806198d2ac5ef_::_lambda_invoker_cdecl_,
    0,
    0);
  v0 = 1;
  byte_180013788 = 1;
  if ( Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&Microsoft::WRL::Details::StaticStorage<Microsoft::WRL::Details::DefaultModule<1>,0,int>::instance_,
         v1,
         0,
         v2)
    && !`winrt::get_module_lock'::`2'::s_lock )
  {
    v3 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
    if ( v3 )
    {
      do
      {
        Next = v3[-1].Next;
        v5 = v3->Next;
        if ( Next )
        {
          v6 = (unsigned __int64)v3[-1].Next;
          v7 = _InterlockedCompareExchange128((volatile signed __int64 *)&v3[-1], 0, 0, (signed __int64 *)&v6);
          if ( v7 != 0 )
            ((void (__fastcall *)(struct _SLIST_ENTRY *))Next->Next[1].Next)(Next);
        }
        v3 = v5;
      }
      while ( v5 );
    }
    return 0;
  }
  return v0;
}

```

## disassembly

```asm
0x18000a520  mov     [rsp+arg_0], rbx
0x18000a525  mov     [rsp+arg_8], rsi
0x18000a52a  push    rdi
0x18000a52b  sub     rsp, 30h
0x18000a52f  xor     r9d, r9d; Context
0x18000a532  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_5f1dd388c03885d19ee806198d2ac5ef_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000a539  xor     r8d, r8d; Parameter
0x18000a53c  lea     rcx, ?initOnceInProc_@?$Module@$00V?$DefaultModule@$00@Details@WRL@Microsoft@@@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18000a543  call    cs:__imp_InitOnceExecuteOnce
0x18000a549  mov     edi, 1
0x18000a54e  lea     rcx, ?instance_@?$StaticStorage@V?$DefaultModule@$00@Details@WRL@Microsoft@@$0A@H@Details@WRL@Microsoft@@0V1234@A; this
0x18000a555  xor     r8d, r8d; unsigned __int16 *
0x18000a558  mov     cs:byte_180013788, dil
0x18000a55f  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000a564  test    al, al
0x18000a566  jz      short loc_18000A5D8
0x18000a568  mov     eax, cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000a56e  nop
0x18000a56f  test    eax, eax
0x18000a571  jnz     short loc_18000A5D8
0x18000a573  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000a57a  call    WINRT_IMPL_InterlockedFlushSList
0x18000a57f  mov     r8, rax
0x18000a582  test    rax, rax
0x18000a585  jz      short loc_18000A5D6
0x18000a587  mov     r9, [r8-10h]
0x18000a58b  mov     rsi, [r8]
0x18000a58e  nop
0x18000a58f  test    r9, r9
0x18000a592  jz      short loc_18000A5CE
0x18000a594  xor     edx, edx
0x18000a596  mov     [rsp+38h+var_18], r9
0x18000a59b  xor     ecx, ecx
0x18000a59d  mov     [rsp+38h+var_10], rdx
0x18000a5a2  xor     ebx, ebx
0x18000a5a4  mov     rax, r9
0x18000a5a7  lock cmpxchg16b xmmword ptr [r8-10h]
0x18000a5ad  mov     [rsp+38h+var_18], rax
0x18000a5b2  setz    al
0x18000a5b5  mov     [rsp+38h+var_10], rdx
0x18000a5ba  cmp     al, dil
0x18000a5bd  jnz     short loc_18000A5CE
0x18000a5bf  mov     rax, [r9]
0x18000a5c2  mov     rcx, r9
0x18000a5c5  mov     rax, [rax+10h]
0x18000a5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ce  mov     r8, rsi
0x18000a5d1  test    rsi, rsi
0x18000a5d4  jnz     short loc_18000A587
0x18000a5d6  xor     edi, edi
0x18000a5d8  mov     rbx, [rsp+38h+arg_0]
0x18000a5dd  mov     eax, edi
0x18000a5df  mov     rsi, [rsp+38h+arg_8]
0x18000a5e4  add     rsp, 30h
0x18000a5e8  pop     rdi
0x18000a5e9  retn
```
