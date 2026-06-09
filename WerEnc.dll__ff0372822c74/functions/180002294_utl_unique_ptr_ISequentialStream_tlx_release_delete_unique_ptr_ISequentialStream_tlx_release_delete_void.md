# utl::unique_ptr<ISequentialStream,tlx::release_delete>::~unique_ptr<ISequentialStream,tlx::release_delete>(void)

- ea: `0x180002294`
- end: `0x1800022b2`
- name: `??1?$unique_ptr@UISequentialStream@@Urelease_delete@tlx@@@utl@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002d6e`
- `0x180002d80`

## callees

- `0x180002294`
- `0x180003010`

## pseudocode

```c
__int64 __fastcall utl::unique_ptr<ISequentialStream,tlx::release_delete>::~unique_ptr<ISequentialStream,tlx::release_delete>(
        __int64 *a1)
{
  __int64 v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
  return result;
}

```

## disassembly

```asm
0x180002294  sub     rsp, 28h
0x180002298  mov     rcx, [rcx]
0x18000229b  test    rcx, rcx
0x18000229e  jz      short loc_1800022AD
0x1800022a0  mov     rax, [rcx]
0x1800022a3  mov     rax, [rax+10h]
0x1800022a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022ac  nop
0x1800022ad  add     rsp, 28h
0x1800022b1  retn
```
