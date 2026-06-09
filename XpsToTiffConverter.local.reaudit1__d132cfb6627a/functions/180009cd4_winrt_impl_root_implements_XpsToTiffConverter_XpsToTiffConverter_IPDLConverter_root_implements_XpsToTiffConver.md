# winrt::impl::root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>::~root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>(void)

- ea: `0x180009cd4`
- end: `0x180009d54`
- name: `??1?$root_implements@UXpsToTiffConverter@1@UIPDLConverter@@@impl@winrt@@MEAA@XZ`
- size: `128`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009dd8`
- `0x18000c1a8`
- `0x18000c1d0`

## callees

- `0x180001a70`
- `0x180009cd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009d4d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180009d4d`

## pseudocode

```c
void __fastcall winrt::impl::root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>::~root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>(
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
0x180009cd4  push    rbx
0x180009cd6  sub     rsp, 20h
0x180009cda  mov     rax, [rcx+8]
0x180009cde  or      ebx, 0FFFFFFFFh
0x180009ce1  test    rax, rax
0x180009ce4  js      short loc_180009CF4
0x180009ce6  lea     rdx, [rax-1]
0x180009cea  lock cmpxchg [rcx+8], rdx
0x180009cf0  jnz     short loc_180009CDE
0x180009cf2  jmp     short loc_180009D35
0x180009cf4  lea     rcx, [rax+rax]; void *
0x180009cf8  mov     eax, ebx
0x180009cfa  lock xadd [rcx+18h], eax
0x180009cff  cmp     eax, 1
0x180009d02  jnz     short loc_180009D35
0x180009d04  mov     eax, ebx
0x180009d06  lock xadd [rcx+1Ch], eax
0x180009d0b  cmp     eax, 1
0x180009d0e  jnz     short loc_180009D35
0x180009d10  test    rcx, rcx
0x180009d13  jz      short loc_180009D35
0x180009d15  mov     eax, ebx
0x180009d17  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009d1f  sub     eax, 1
0x180009d22  jnz     short loc_180009D27
0x180009d24  nop
0x180009d25  jmp     short loc_180009D2B
0x180009d27  test    eax, eax
0x180009d29  js      short loc_180009D4D
0x180009d2b  mov     edx, 20h ; ' '; unsigned __int64
0x180009d30  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009d35  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, ebx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180009d3d  sub     ebx, 1
0x180009d40  jnz     short loc_180009D49
0x180009d42  nop
0x180009d43  add     rsp, 20h
0x180009d47  pop     rbx
0x180009d48  retn
0x180009d49  test    ebx, ebx
0x180009d4b  jns     short loc_180009D43
0x180009d4d  call    cs:__imp_abort
```
