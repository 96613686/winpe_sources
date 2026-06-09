# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18001a744`
- end: `0x18001a791`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180019f1c`

## callees

- `0x180003914`
- `0x18001a744`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001a78a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001a78a`

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
0x18001a744  sub     rsp, 28h
0x18001a748  mov     r8, [rcx]
0x18001a74b  mov     qword ptr [rcx], 0
0x18001a752  or      ecx, 0FFFFFFFFh
0x18001a755  mov     eax, ecx
0x18001a757  lock xadd [r8+1Ch], eax
0x18001a75d  cmp     eax, 1
0x18001a760  jnz     short loc_18001A781
0x18001a762  test    r8, r8
0x18001a765  jz      short loc_18001A781
0x18001a767  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18001a76f  sub     ecx, eax
0x18001a771  jnz     short loc_18001A786
0x18001a773  nop
0x18001a774  mov     edx, 20h ; ' '
0x18001a779  mov     rcx, r8; Block
0x18001a77c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001a781  add     rsp, 28h
0x18001a785  retn
0x18001a786  test    ecx, ecx
0x18001a788  jns     short loc_18001A774
0x18001a78a  call    cs:__imp_abort
```
