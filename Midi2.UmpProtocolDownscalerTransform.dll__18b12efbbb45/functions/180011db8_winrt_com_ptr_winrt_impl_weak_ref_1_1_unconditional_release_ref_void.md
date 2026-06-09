# winrt::com_ptr<winrt::impl::weak_ref<1,1>>::unconditional_release_ref(void)

- ea: `0x180011db8`
- end: `0x180011e05`
- name: `?unconditional_release_ref@?$com_ptr@U?$weak_ref@$00$00@impl@winrt@@@winrt@@AEAAXXZ`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800114f0`

## callees

- `0x180002e94`
- `0x180011db8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011dfe`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180011dfe`

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
0x180011db8  sub     rsp, 28h
0x180011dbc  mov     r8, [rcx]
0x180011dbf  mov     qword ptr [rcx], 0
0x180011dc6  or      ecx, 0FFFFFFFFh
0x180011dc9  mov     eax, ecx
0x180011dcb  lock xadd [r8+1Ch], eax
0x180011dd1  cmp     eax, 1
0x180011dd4  jnz     short loc_180011DF5
0x180011dd6  test    r8, r8
0x180011dd9  jz      short loc_180011DF5
0x180011ddb  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ecx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180011de3  sub     ecx, eax
0x180011de5  jnz     short loc_180011DFA
0x180011de7  nop
0x180011de8  mov     edx, 20h ; ' '
0x180011ded  mov     rcx, r8; Block
0x180011df0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011df5  add     rsp, 28h
0x180011df9  retn
0x180011dfa  test    ecx, ecx
0x180011dfc  jns     short loc_180011DE8
0x180011dfe  call    cs:__imp_abort
```
