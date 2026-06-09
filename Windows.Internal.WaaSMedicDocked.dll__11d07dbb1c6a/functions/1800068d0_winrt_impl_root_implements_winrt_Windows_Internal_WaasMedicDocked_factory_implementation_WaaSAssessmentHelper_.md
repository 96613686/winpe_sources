# winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>::~root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>(void)

- ea: `0x1800068d0`
- end: `0x180006950`
- name: `??1?$root_implements@VWaaSAssessmentHelper@factory_implementation@WaasMedicDocked@Internal@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180006a0c`
- `0x180006a80`
- `0x180006ac0`
- `0x180006b30`
- `0x180006ba0`
- `0x180008230`
- `0x18000a7d0`

## callees

- `0x180001940`
- `0x1800068d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006949`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180006949`

## pseudocode

```c
void __fastcall winrt::impl::root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>::~root_implements<winrt::Windows::Internal::WaasMedicDocked::factory_implementation::WaaSAssessmentHelper,winrt::Windows::Foundation::IActivationFactory>(
        __int64 a1)
{
  signed __int64 v1; // rax
  signed __int64 v2; // rtt
  volatile signed __int32 *v3; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  while ( v1 >= 0 )
  {
    v2 = v1;
    v1 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v1 - 1, v1);
    if ( v2 == v1 )
      goto LABEL_10;
  }
  v3 = (volatile signed __int32 *)(2 * v1);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(2 * v1 + 24), 0xFFFFFFFF) == 1
    && _InterlockedExchangeAdd(v3 + 7, 0xFFFFFFFF) == 1
    && v3 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      goto LABEL_11;
    operator delete((void *)v3);
  }
LABEL_10:
  if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
LABEL_11:
    abort();
}

```

## disassembly

```asm
0x1800068d0  push    rbx
0x1800068d2  sub     rsp, 20h
0x1800068d6  mov     rax, [rcx+8]
0x1800068da  or      ebx, 0FFFFFFFFh
0x1800068dd  test    rax, rax
0x1800068e0  js      short loc_1800068F0
0x1800068e2  lea     rdx, [rax-1]
0x1800068e6  lock cmpxchg [rcx+8], rdx
0x1800068ec  jnz     short loc_1800068DA
0x1800068ee  jmp     short loc_180006931
0x1800068f0  lea     rcx, [rax+rax]; void *
0x1800068f4  mov     eax, ebx
0x1800068f6  lock xadd [rcx+18h], eax
0x1800068fb  cmp     eax, 1
0x1800068fe  jnz     short loc_180006931
0x180006900  mov     eax, ebx
0x180006902  lock xadd [rcx+1Ch], eax
0x180006907  cmp     eax, 1
0x18000690a  jnz     short loc_180006931
0x18000690c  test    rcx, rcx
0x18000690f  jz      short loc_180006931
0x180006911  mov     eax, ebx
0x180006913  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000691b  sub     eax, 1
0x18000691e  jnz     short loc_180006923
0x180006920  nop
0x180006921  jmp     short loc_180006927
0x180006923  test    eax, eax
0x180006925  js      short loc_180006949
0x180006927  mov     edx, 20h ; ' '; unsigned __int64
0x18000692c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006931  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006939  sub     ebx, 1
0x18000693c  jnz     short loc_180006945
0x18000693e  nop
0x18000693f  add     rsp, 20h
0x180006943  pop     rbx
0x180006944  retn
0x180006945  test    ebx, ebx
0x180006947  jns     short loc_18000693F
0x180006949  call    cs:__imp_abort
```
