# CWinSATTaskMangerTask::TNThreadProcS(void *)

- ea: `0x1800217b0`
- end: `0x1800217f3`
- name: `?TNThreadProcS@CWinSATTaskMangerTask@@CAKPEAX@Z`
- size: `67`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1800213a4`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800217e6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x1800217e6`

## pseudocode

```c
void __fastcall __noreturn CWinSATTaskMangerTask::TNThreadProcS(CWinSATTaskMangerTask *Parameter)
{
  DWORD v2; // eax
  __int64 v3; // rdx
  DWORD v4; // edi
  HMODULE v5; // rbx

  v2 = CWinSATTaskMangerTask::TNThreadProc(Parameter);
  v3 = *(_QWORD *)Parameter;
  v4 = v2;
  v5 = (HMODULE)*((_QWORD *)Parameter + 12);
  *((_QWORD *)Parameter + 12) = 0;
  (*(void (__fastcall **)(CWinSATTaskMangerTask *))(v3 + 16))(Parameter);
  FreeLibraryAndExitThread(v5, v4);
}

```

## disassembly

```asm
0x1800217b0  mov     [rsp+arg_0], rbx
0x1800217b5  mov     [rsp+arg_8], rsi
0x1800217ba  push    rdi
0x1800217bb  sub     rsp, 20h
0x1800217bf  mov     rsi, rcx
0x1800217c2  call    ?TNThreadProc@CWinSATTaskMangerTask@@AEAAKXZ; CWinSATTaskMangerTask::TNThreadProc(void)
0x1800217c7  mov     rdx, [rsi]
0x1800217ca  mov     edi, eax
0x1800217cc  mov     rbx, [rsi+60h]
0x1800217d0  mov     rcx, rsi
0x1800217d3  and     qword ptr [rsi+60h], 0
0x1800217d8  mov     rax, [rdx+10h]
0x1800217dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217e1  mov     edx, edi; dwExitCode
0x1800217e3  mov     rcx, rbx; hLibModule
0x1800217e6  call    cs:__imp_FreeLibraryAndExitThread
0x1800217ed  nop     dword ptr [rax+rax+00h]
0x1800217f2  int     3; Trap to Debugger
```
