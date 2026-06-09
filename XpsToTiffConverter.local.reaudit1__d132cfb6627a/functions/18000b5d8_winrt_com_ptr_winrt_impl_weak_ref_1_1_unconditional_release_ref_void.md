# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18000b5d8`
- end: `0x18000b625`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b16c`

## callees

- `0x180001a70`
- `0x18000b5d8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000b61e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000b61e`

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
0x18000b5d8  sub     rsp, 28h
0x18000b5dc  mov     r8, [rcx]
0x18000b5df  mov     qword ptr [rcx], 0
0x18000b5e6  or      ecx, 0FFFFFFFFh
0x18000b5e9  mov     eax, ecx
0x18000b5eb  lock xadd [r8+1Ch], eax
0x18000b5f1  cmp     eax, 1
0x18000b5f4  jnz     short loc_18000B615
0x18000b5f6  test    r8, r8
0x18000b5f9  jz      short loc_18000B615
0x18000b5fb  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000b603  sub     ecx, eax
0x18000b605  jnz     short loc_18000B61A
0x18000b607  nop
0x18000b608  mov     edx, 20h ; ' '; unsigned __int64
0x18000b60d  mov     rcx, r8; void *
0x18000b610  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b615  add     rsp, 28h
0x18000b619  retn
0x18000b61a  test    ecx, ecx
0x18000b61c  jns     short loc_18000B608
0x18000b61e  call    cs:__imp_abort
```
