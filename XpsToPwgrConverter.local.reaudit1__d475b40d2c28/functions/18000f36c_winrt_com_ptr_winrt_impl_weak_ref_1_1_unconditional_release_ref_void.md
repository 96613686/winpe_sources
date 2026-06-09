# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18000f36c`
- end: `0x18000f3b9`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000f12c`

## callees

- `0x180001b30`
- `0x18000f36c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f3b2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000f3b2`

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
0x18000f36c  sub     rsp, 28h
0x18000f370  mov     r8, [rcx]
0x18000f373  mov     qword ptr [rcx], 0
0x18000f37a  or      ecx, 0FFFFFFFFh
0x18000f37d  mov     eax, ecx
0x18000f37f  lock xadd [r8+1Ch], eax
0x18000f385  cmp     eax, 1
0x18000f388  jnz     short loc_18000F3A9
0x18000f38a  test    r8, r8
0x18000f38d  jz      short loc_18000F3A9
0x18000f38f  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000f397  sub     ecx, eax
0x18000f399  jnz     short loc_18000F3AE
0x18000f39b  nop
0x18000f39c  mov     edx, 20h ; ' '; unsigned __int64
0x18000f3a1  mov     rcx, r8; void *
0x18000f3a4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f3a9  add     rsp, 28h
0x18000f3ad  retn
0x18000f3ae  test    ecx, ecx
0x18000f3b0  jns     short loc_18000F39C
0x18000f3b2  call    cs:__imp_abort
```
