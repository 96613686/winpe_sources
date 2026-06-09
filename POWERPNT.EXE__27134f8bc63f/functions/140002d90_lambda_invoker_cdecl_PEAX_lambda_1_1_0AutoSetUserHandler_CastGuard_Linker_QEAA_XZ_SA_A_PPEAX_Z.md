# ??$_lambda_invoker_cdecl_@PEAX@_lambda_1_@?1???0AutoSetUserHandler@CastGuard@Linker@@QEAA@XZ@SA?A_PPEAX@Z

- ea: `0x140002d90`
- end: `0x140002dba`
- name: `??$_lambda_invoker_cdecl_@PEAX@_lambda_1_@?1???0AutoSetUserHandler@CastGuard@Linker@@QEAA@XZ@SA?A_PPEAX@Z`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140001540`
- `0x140002970`
- `0x140002d90`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 `Linker::CastGuard::AutoSetUserHandler::AutoSetUserHandler'::`2'::_lambda_1_::_lambda_invoker_cdecl_<void *>()
{
  __int64 result; // rax

  if ( !qword_1400057F8 || (result = qword_1400057F8(), (_DWORD)result != 1) )
    CrashWithRecovery(0, 0);
  return result;
}

```

## disassembly

```asm
0x140002d90  sub     rsp, 28h
0x140002d94  mov     rax, cs:qword_1400057F8
0x140002d9b  test    rax, rax
0x140002d9e  jz      short loc_140002DB0
0x140002da0  call    cs:__guard_dispatch_icall_fptr
0x140002da6  cmp     eax, 1
0x140002da9  jnz     short loc_140002DB0
0x140002dab  add     rsp, 28h
0x140002daf  retn
0x140002db0  xor     edx, edx; struct CrashContext *
0x140002db2  xor     ecx, ecx; unsigned int
0x140002db4  call    ?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
