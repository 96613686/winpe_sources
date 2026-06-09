# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x180006f30`
- end: `0x180006f82`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006c90`

## callees

- `0x180006f30`
- `0x180007660`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006f7b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006f7b`

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
0x180006f30  sub     rsp, 28h
0x180006f34  mov     r8, [rcx]
0x180006f37  mov     qword ptr [rcx], 0
0x180006f3e  mov     ecx, 0FFFFFFFFh
0x180006f43  mov     eax, ecx
0x180006f45  lock xadd [r8+1Ch], eax
0x180006f4b  cmp     eax, 1
0x180006f4e  jnz     short loc_180006F72
0x180006f50  test    r8, r8
0x180006f53  jz      short loc_180006F72
0x180006f55  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180006f5d  sub     ecx, eax
0x180006f5f  jnz     short loc_180006F77
0x180006f61  mov     edx, 20h ; ' '; unsigned __int64
0x180006f66  mov     rcx, r8; void *
0x180006f69  add     rsp, 28h
0x180006f6d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180006f72  add     rsp, 28h
0x180006f76  retn
0x180006f77  test    ecx, ecx
0x180006f79  jns     short loc_180006F61
0x180006f7b  call    cs:__imp_abort
```
