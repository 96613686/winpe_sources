# DllCanUnloadNow

- ea: `0x18000d550`
- end: `0x18000d5df`
- name: `DllCanUnloadNow`
- size: `143`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002e41`
- `0x18000d550`
- `0x18000f010`

## import_xrefs

- `RPCRT4!NdrDllCanUnloadNow` at `0x18000d5d8`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  PSLIST_ENTRY v0; // r8
  struct _SLIST_ENTRY *Next; // r9
  struct _SLIST_ENTRY *v2; // rdi
  __int128 v3; // rt0
  unsigned __int8 v4; // tt

  if ( !`winrt::get_module_lock'::`2'::s_lock )
  {
    v0 = WINRT_IMPL_InterlockedFlushSList(&`winrt::impl::get_factory_cache'::`2'::cache);
    if ( v0 )
    {
      do
      {
        Next = v0[-1].Next;
        v2 = v0->Next;
        if ( Next )
        {
          v3 = (unsigned __int64)v0[-1].Next;
          v4 = _InterlockedCompareExchange128((volatile signed __int64 *)&v0[-1], 0, 0, (signed __int64 *)&v3);
          if ( v4 != 0 )
            ((void (__fastcall *)(struct _SLIST_ENTRY *))Next->Next[1].Next)(Next);
        }
        v0 = v2;
      }
      while ( v2 );
    }
  }
  return NdrDllCanUnloadNow(&gPFactory);
}

```

## disassembly

```asm
0x18000d550  mov     [rsp+arg_0], rbx
0x18000d555  push    rdi
0x18000d556  sub     rsp, 30h
0x18000d55a  mov     eax, cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d560  nop
0x18000d561  test    eax, eax
0x18000d563  jnz     short loc_18000D5C7
0x18000d565  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000d56c  call    WINRT_IMPL_InterlockedFlushSList
0x18000d571  mov     r8, rax
0x18000d574  test    rax, rax
0x18000d577  jz      short loc_18000D5C7
0x18000d579  mov     r9, [r8-10h]
0x18000d57d  mov     rdi, [r8]
0x18000d580  nop
0x18000d581  test    r9, r9
0x18000d584  jz      short loc_18000D5BF
0x18000d586  xor     edx, edx
0x18000d588  mov     [rsp+38h+var_18], r9
0x18000d58d  xor     ecx, ecx
0x18000d58f  mov     [rsp+38h+var_10], rdx
0x18000d594  xor     ebx, ebx
0x18000d596  mov     rax, r9
0x18000d599  lock cmpxchg16b xmmword ptr [r8-10h]
0x18000d59f  mov     [rsp+38h+var_18], rax
0x18000d5a4  setz    al
0x18000d5a7  mov     [rsp+38h+var_10], rdx
0x18000d5ac  cmp     al, 1
0x18000d5ae  jnz     short loc_18000D5BF
0x18000d5b0  mov     rax, [r9]
0x18000d5b3  mov     rcx, r9
0x18000d5b6  mov     rax, [rax+10h]
0x18000d5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5bf  mov     r8, rdi
0x18000d5c2  test    rdi, rdi
0x18000d5c5  jnz     short loc_18000D579
0x18000d5c7  lea     rcx, gPFactory
0x18000d5ce  mov     rbx, [rsp+38h+arg_0]
0x18000d5d3  add     rsp, 30h
0x18000d5d7  pop     rdi
0x18000d5d8  jmp     cs:__imp_NdrDllCanUnloadNow
```
