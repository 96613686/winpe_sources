# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18000d4fc`
- end: `0x18000d549`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000d13c`

## callees

- `0x180002540`
- `0x18000d4fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000d542`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000d542`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // r8

  v1 = *a1;
  *a1 = 0;
  if ( _InterlockedExchangeAdd(v1 + 7, 0xFFFFFFFF) == 1 && v1 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete((void *)v1);
  }
}

```

## disassembly

```asm
0x18000d4fc  sub     rsp, 28h
0x18000d500  mov     r8, [rcx]
0x18000d503  mov     qword ptr [rcx], 0
0x18000d50a  or      ecx, 0FFFFFFFFh
0x18000d50d  mov     eax, ecx
0x18000d50f  lock xadd [r8+1Ch], eax
0x18000d515  cmp     eax, 1
0x18000d518  jnz     short loc_18000D539
0x18000d51a  test    r8, r8
0x18000d51d  jz      short loc_18000D539
0x18000d51f  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d527  sub     ecx, eax
0x18000d529  jnz     short loc_18000D53E
0x18000d52b  nop
0x18000d52c  mov     edx, 20h ; ' '; unsigned __int64
0x18000d531  mov     rcx, r8; void *
0x18000d534  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000d539  add     rsp, 28h
0x18000d53d  retn
0x18000d53e  test    ecx, ecx
0x18000d540  jns     short loc_18000D52C
0x18000d542  call    cs:__imp_abort
```
