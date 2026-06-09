# _dynamic_atexit_destructor_for___AtlModule__

- ea: `0x180002070`
- end: `0x1800020ec`
- name: `_dynamic_atexit_destructor_for___AtlModule__`
- size: `124`
- prototype: `void __fastcall(ATL::CAtlComModule *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002070`
- `0x180002320`
- `0x180002380`
- `0x18000b3b0`
- `0x18000c010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800020a2`
- `KERNEL32!DeleteCriticalSection` at `0x1800020a2`

## pseudocode

```c
void __fastcall dynamic_atexit_destructor_for___AtlModule__(ATL::CAtlComModule *a1)
{
  ATL::CAtlComModule::ExecuteObjectMain(a1, 0);
  if ( qword_180012898 )
  {
    if ( qword_1800128A0 )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)&qword_180012898);
      qword_1800128A0 = 0;
    }
    if ( qword_1800128D0 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800128D0 + 16LL))(qword_1800128D0);
    DeleteCriticalSection((LPCRITICAL_SECTION)&CriticalSection);
    qword_180012898 = 0;
  }
}

```

## disassembly

```asm
0x180002070  sub     rsp, 28h
0x180002074  xor     edx, edx; bool
0x180002076  call    ?ExecuteObjectMain@CAtlComModule@ATL@@QEAAX_N@Z; ATL::CAtlComModule::ExecuteObjectMain(bool)
0x18000207b  nop
0x18000207c  cmp     dword ptr cs:qword_180012898, 0
0x180002083  jz      short loc_1800020B2
0x180002085  cmp     cs:qword_1800128A0, 0
0x18000208d  jnz     short loc_1800020C4
0x18000208f  mov     rcx, cs:qword_1800128D0
0x180002096  test    rcx, rcx
0x180002099  jnz     short loc_1800020DD
0x18000209b  lea     rcx, CriticalSection; lpCriticalSection
0x1800020a2  call    cs:__imp_DeleteCriticalSection
0x1800020a8  mov     dword ptr cs:qword_180012898, 0
0x1800020b2  lea     rcx, qword_180012898
0x1800020b9  call    _guard_check_icall_nop
0x1800020be  nop
0x1800020bf  add     rsp, 28h
0x1800020c3  retn
0x1800020c4  lea     rcx, qword_180012898; struct ATL::_ATL_MODULE70 *
0x1800020cb  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x1800020d0  mov     cs:qword_1800128A0, 0
0x1800020db  jmp     short loc_18000208F
0x1800020dd  mov     rax, [rcx]
0x1800020e0  mov     rax, [rax+10h]
0x1800020e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020e9  jmp     short loc_18000209B
```
