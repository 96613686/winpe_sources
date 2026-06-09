# utl::out_ptr_t<utl::unique_ptr<ISequentialStream,tlx::release_delete>,ISequentialStream *,>::~out_ptr_t<utl::unique_ptr<ISequentialStream,tlx::release_delete>,ISequentialStream *,>(void)

- ea: `0x180002244`
- end: `0x180002271`
- name: `??1?$out_ptr_t@V?$unique_ptr@UISequentialStream@@Urelease_delete@tlx@@@utl@@PEAUISequentialStream@@$$V@utl@@QEAA@XZ`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d38`

## callees

- `0x180002244`
- `0x180003010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall utl::out_ptr_t<utl::unique_ptr<ISequentialStream,tlx::release_delete>,ISequentialStream *,>::~out_ptr_t<utl::unique_ptr<ISequentialStream,tlx::release_delete>,ISequentialStream *,>(
        __int64 *a1)
{
  __int64 v1; // rdx
  __int64 *result; // rax
  __int64 v3; // rcx

  v1 = *a1;
  if ( *a1 )
  {
    result = (__int64 *)a1[1];
    v3 = *result;
    *result = v1;
    if ( v3 )
      return (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  return result;
}

```

## disassembly

```asm
0x180002244  sub     rsp, 28h
0x180002248  mov     rdx, [rcx]
0x18000224b  test    rdx, rdx
0x18000224e  jz      short loc_18000226C
0x180002250  mov     rax, [rcx+8]
0x180002254  mov     rcx, [rax]
0x180002257  mov     [rax], rdx
0x18000225a  test    rcx, rcx
0x18000225d  jz      short loc_18000226C
0x18000225f  mov     rax, [rcx]
0x180002262  mov     rax, [rax+10h]
0x180002266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000226b  nop
0x18000226c  add     rsp, 28h
0x180002270  retn
```
