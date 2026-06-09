# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x18000c050`
- end: `0x18000c0a2`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `82`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000bb30`

## callees

- `0x18000c050`
- `0x180018238`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000c09b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000c09b`

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
0x18000c050  sub     rsp, 28h
0x18000c054  mov     r8, [rcx]
0x18000c057  mov     qword ptr [rcx], 0
0x18000c05e  mov     ecx, 0FFFFFFFFh
0x18000c063  mov     eax, ecx
0x18000c065  lock xadd [r8+1Ch], eax
0x18000c06b  cmp     eax, 1
0x18000c06e  jnz     short loc_18000C092
0x18000c070  test    r8, r8
0x18000c073  jz      short loc_18000C092
0x18000c075  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000c07d  sub     ecx, eax
0x18000c07f  jnz     short loc_18000C097
0x18000c081  mov     edx, 20h ; ' '; unsigned __int64
0x18000c086  mov     rcx, r8; void *
0x18000c089  add     rsp, 28h
0x18000c08d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c092  add     rsp, 28h
0x18000c096  retn
0x18000c097  test    ecx, ecx
0x18000c099  jns     short loc_18000C081
0x18000c09b  call    cs:__imp_abort
```
