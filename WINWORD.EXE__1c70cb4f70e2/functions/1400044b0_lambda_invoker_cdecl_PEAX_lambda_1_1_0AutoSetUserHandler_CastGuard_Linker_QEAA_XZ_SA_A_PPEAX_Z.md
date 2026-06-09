# ??$_lambda_invoker_cdecl_@PEAX@_lambda_1_@?1???0AutoSetUserHandler@CastGuard@Linker@@QEAA@XZ@SA?A_PPEAX@Z

- ea: `0x1400044b0`
- end: `0x1400044db`
- name: `??$_lambda_invoker_cdecl_@PEAX@_lambda_1_@?1???0AutoSetUserHandler@CastGuard@Linker@@QEAA@XZ@SA?A_PPEAX@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x140001020`
- `0x1400044b0`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400044d4`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x1400044d4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 `Linker::CastGuard::AutoSetUserHandler::AutoSetUserHandler'::`2'::_lambda_1_::_lambda_invoker_cdecl_<void *>()
{
  __int64 result; // rax

  if ( !qword_140009B48 || (result = qword_140009B48(), (_DWORD)result != 1) )
  {
    CrashWithRecovery(0, 0);
    JUMPOUT(0x1400044DALL);
  }
  return result;
}

```

## disassembly

```asm
0x1400044b0  sub     rsp, 28h
0x1400044b4  mov     rax, cs:qword_140009B48
0x1400044bb  test    rax, rax
0x1400044be  jz      short loc_1400044D0
0x1400044c0  call    cs:__guard_dispatch_icall_fptr
0x1400044c6  cmp     eax, 1
0x1400044c9  jnz     short loc_1400044D0
0x1400044cb  add     rsp, 28h
0x1400044cf  retn
0x1400044d0  xor     edx, edx
0x1400044d2  xor     ecx, ecx
0x1400044d4  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
