# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x18000c380`
- end: `0x18000c48b`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `267`
- prototype: `__int64 __fastcall(_DWORD *lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x180001fd8`
- `0x18000280c`
- `0x18000c380`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c477`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x18000c477`

## string_xrefs

- `0x18000c3b2`: `CWinTaskHandler::WorkerThreadProc`
- `0x18000c436`: `CWinTaskHandler::WorkerThreadProc`
- `0x18000c3be`: `onecore\internal\admin\inc\WinTask.h`
- `0x18000c442`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *lpThreadParameter)
{
  int v2; // ebp
  HMODULE v3; // rdi
  __int64 v4; // rsi
  HINSTANCE v5; // rax
  const wchar_t *v6; // rax
  unsigned int v7; // r8d

  if ( !lpThreadParameter )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x280u,
      "CWinTaskHandler::WorkerThreadProc",
      (wchar_t *)L"Assert (%s): %s",
      L"0 != param",
      L"Failed");
  v2 = lpThreadParameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 64LL))(lpThreadParameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)lpThreadParameter + 6) + 32LL))(
    *((_QWORD *)lpThreadParameter + 6),
    v4);
  if ( v2 )
  {
    v5 = CWinTaskHandler::DetachDllModule((CWinTaskHandler *)lpThreadParameter);
    v3 = v5;
    if ( v5 )
    {
      if ( v5 != (HINSTANCE)-1LL )
        goto LABEL_9;
      v6 = L"((HANDLE)(LONG_PTR)-1) != hModule";
      v7 = 658;
    }
    else
    {
      v6 = L"0 != hModule";
      v7 = 657;
    }
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      v7,
      "CWinTaskHandler::WorkerThreadProc",
      (wchar_t *)L"Assert (%s): %s",
      v6,
      L"Failed");
  }
LABEL_9:
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)lpThreadParameter + 16LL))(lpThreadParameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000c380  push    rbx
0x18000c382  push    rbp
0x18000c383  push    rsi
0x18000c384  push    rdi
0x18000c385  push    r13
0x18000c387  sub     rsp, 40h
0x18000c38b  mov     rbx, rcx
0x18000c38e  lea     r13, aFailed; "Failed"
0x18000c395  lea     rcx, aAssertSS; "Assert (%s): %s"
0x18000c39c  test    rbx, rbx
0x18000c39f  jnz     short loc_18000C3D3
0x18000c3a1  lea     rax, a0Param; "0 != param"
0x18000c3a8  mov     [rsp+68h+var_38], r13
0x18000c3ad  mov     [rsp+68h+var_40], rax
0x18000c3b2  lea     r9, aCwintaskhandle_1; "CWinTaskHandler::WorkerThreadProc"
0x18000c3b9  mov     [rsp+68h+var_48], rcx; unsigned __int16 *
0x18000c3be  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000c3c5  lea     ecx, [rbx+1]; unsigned int
0x18000c3c8  mov     r8d, 280h; unsigned int
0x18000c3ce  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c3d3  mov     rax, [rbx]
0x18000c3d6  mov     rcx, rbx
0x18000c3d9  mov     ebp, [rbx+10h]
0x18000c3dc  xor     edi, edi
0x18000c3de  mov     rax, [rax+40h]
0x18000c3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3e7  mov     rcx, [rbx+30h]
0x18000c3eb  mov     esi, eax
0x18000c3ed  mov     edx, esi
0x18000c3ef  mov     rax, [rcx]
0x18000c3f2  mov     rax, [rax+20h]
0x18000c3f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3fb  test    ebp, ebp
0x18000c3fd  jz      short loc_18000C45F
0x18000c3ff  mov     rcx, rbx; this
0x18000c402  call    ?DetachDllModule@CWinTaskHandler@@AEAAPEAUHINSTANCE__@@XZ; CWinTaskHandler::DetachDllModule(void)
0x18000c407  mov     rdi, rax
0x18000c40a  test    rax, rax
0x18000c40d  jnz     short loc_18000C41E
0x18000c40f  lea     rax, a0Hmodule; "0 != hModule"
0x18000c416  mov     r8d, 291h
0x18000c41c  jmp     short loc_18000C431
0x18000c41e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000c422  jnz     short loc_18000C45F
0x18000c424  lea     rax, aHandleLongPtr1_1; "((HANDLE)(LONG_PTR)-1) != hModule"
0x18000c42b  mov     r8d, 292h; unsigned int
0x18000c431  mov     [rsp+68h+var_38], r13
0x18000c436  lea     r9, aCwintaskhandle_1; "CWinTaskHandler::WorkerThreadProc"
0x18000c43d  mov     [rsp+68h+var_40], rax
0x18000c442  lea     rdx, aOnecoreInterna; "onecore\\internal\\admin\\inc\\WinTask."...
0x18000c449  lea     rax, aAssertSS; "Assert (%s): %s"
0x18000c450  mov     ecx, 1; unsigned int
0x18000c455  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18000c45a  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18000c45f  mov     rax, [rbx]
0x18000c462  mov     rcx, rbx
0x18000c465  mov     rax, [rax+10h]
0x18000c469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c46e  test    ebp, ebp
0x18000c470  jz      short loc_18000C47E
0x18000c472  mov     edx, esi; dwExitCode
0x18000c474  mov     rcx, rdi; hLibModule
0x18000c477  call    cs:__imp_FreeLibraryAndExitThread
0x18000c47d  int     3; Trap to Debugger
0x18000c47e  mov     eax, esi
0x18000c480  add     rsp, 40h
0x18000c484  pop     r13
0x18000c486  pop     rdi
0x18000c487  pop     rsi
0x18000c488  pop     rbp
0x18000c489  pop     rbx
0x18000c48a  retn
```
