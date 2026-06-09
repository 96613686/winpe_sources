# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x180009fc0`
- end: `0x18000a00d`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009558`

## callees

- `0x180001940`
- `0x180009fc0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000a006`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000a006`

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
0x180009fc0  sub     rsp, 28h
0x180009fc4  mov     r8, [rcx]
0x180009fc7  mov     qword ptr [rcx], 0
0x180009fce  or      ecx, 0FFFFFFFFh
0x180009fd1  mov     eax, ecx
0x180009fd3  lock xadd [r8+1Ch], eax
0x180009fd9  cmp     eax, 1
0x180009fdc  jnz     short loc_180009FFD
0x180009fde  test    r8, r8
0x180009fe1  jz      short loc_180009FFD
0x180009fe3  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009feb  sub     ecx, eax
0x180009fed  jnz     short loc_18000A002
0x180009fef  nop
0x180009ff0  mov     edx, 20h ; ' '; unsigned __int64
0x180009ff5  mov     rcx, r8; void *
0x180009ff8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009ffd  add     rsp, 28h
0x18000a001  retn
0x18000a002  test    ecx, ecx
0x18000a004  jns     short loc_180009FF0
0x18000a006  call    cs:__imp_abort
```
