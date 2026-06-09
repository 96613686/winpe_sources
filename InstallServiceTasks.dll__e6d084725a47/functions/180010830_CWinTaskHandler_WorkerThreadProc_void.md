# CWinTaskHandler::WorkerThreadProc(void *)

- ea: `0x180010830`
- end: `0x180010977`
- name: `?WorkerThreadProc@CWinTaskHandler@@CAKPEAX@Z`
- size: `327`
- prototype: `__int64 __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callees

- `0x18000eb64`
- `0x180010830`
- `0x180012f10`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180010965`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180010965`

## string_xrefs

- `0x180010855`: `CWinTaskHandler::WorkerThreadProc`
- `0x18001090f`: `CWinTaskHandler::WorkerThreadProc`
- `0x18001086d`: `onecore\internal\admin\inc\WinTask.h`
- `0x18001092f`: `onecore\internal\admin\inc\WinTask.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWinTaskHandler::WorkerThreadProc(_DWORD *Parameter)
{
  int v2; // ebp
  HMODULE v3; // rdi
  __int64 v4; // rsi
  HINSTANCE v5; // rax

  if ( !Parameter )
    LogMessage(
      1u,
      "onecore\\internal\\admin\\inc\\WinTask.h",
      0x280u,
      "CWinTaskHandler::WorkerThreadProc",
      -1,
      L"Assert (%s): %s",
      0,
      0,
      L"0 != param",
      L"Failed");
  v2 = Parameter[4];
  v3 = 0;
  v4 = (*(unsigned int (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 64LL))(Parameter);
  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)Parameter + 6) + 32LL))(*((_QWORD *)Parameter + 6), v4);
  if ( v2 )
  {
    v5 = CWinTaskHandler::DetachDllModule((CWinTaskHandler *)Parameter);
    v3 = v5;
    if ( v5 )
    {
      if ( v5 == (HINSTANCE)-1LL )
        LogMessage(
          1u,
          "onecore\\internal\\admin\\inc\\WinTask.h",
          0x292u,
          "CWinTaskHandler::WorkerThreadProc",
          -1,
          L"Assert (%s): %s",
          0,
          0,
          L"((HANDLE)(LONG_PTR)-1) != hModule",
          L"Failed");
    }
    else
    {
      LogMessage(
        1u,
        "onecore\\internal\\admin\\inc\\WinTask.h",
        0x291u,
        "CWinTaskHandler::WorkerThreadProc",
        -1,
        L"Assert (%s): %s",
        0,
        0,
        L"0 != hModule",
        L"Failed");
    }
  }
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)Parameter + 16LL))(Parameter);
  if ( v2 )
    FreeLibraryAndExitThread(v3, v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010830  mov     r11, rsp
0x180010833  push    rbx
0x180010834  push    rbp
0x180010835  push    rsi
0x180010836  push    rdi
0x180010837  sub     rsp, 58h
0x18001083b  mov     rbx, rcx
0x18001083e  lea     rax, aFailed; "Failed"
0x180010845  lea     rcx, aAssertSS; "Assert (%s): %s"
0x18001084c  test    rbx, rbx
0x18001084f  jnz     short loc_180010890
0x180010851  mov     [r11-30h], rax
0x180010855  lea     r9, aCwintaskhandle_1; "CWinTaskHandler::WorkerThreadProc"
0x18001085c  lea     rax, a0Param; "0 != param"
0x180010863  mov     r8d, 280h; unsigned int
0x180010869  mov     [r11-38h], rax
0x18001086d  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x180010874  mov     [r11-40h], rbx
0x180010878  mov     [r11-48h], rbx
0x18001087c  mov     [r11-50h], rcx
0x180010880  lea     ecx, [rbx+1]; unsigned int
0x180010883  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x18001088b  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180010890  mov     rax, [rbx]
0x180010893  mov     rcx, rbx
0x180010896  mov     ebp, [rbx+10h]
0x180010899  xor     edi, edi
0x18001089b  mov     rax, [rax+40h]
0x18001089f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108a4  mov     rcx, [rbx+30h]
0x1800108a8  mov     esi, eax
0x1800108aa  mov     edx, esi
0x1800108ac  mov     rax, [rcx]
0x1800108af  mov     rax, [rax+20h]
0x1800108b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108b8  test    ebp, ebp
0x1800108ba  jz      loc_18001094D
0x1800108c0  mov     rcx, rbx; this
0x1800108c3  call    ?DetachDllModule@CWinTaskHandler@@AEAAPEAUHINSTANCE__@@XZ; CWinTaskHandler::DetachDllModule(void)
0x1800108c8  mov     rdi, rax
0x1800108cb  test    rax, rax
0x1800108ce  jnz     short loc_1800108EB
0x1800108d0  lea     rax, aFailed; "Failed"
0x1800108d7  mov     r8d, 291h
0x1800108dd  mov     [rsp+78h+var_30], rax
0x1800108e2  lea     rax, a0Hmodule; "0 != hModule"
0x1800108e9  jmp     short loc_18001090A
0x1800108eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800108ef  jnz     short loc_18001094D
0x1800108f1  lea     rax, aFailed; "Failed"
0x1800108f8  mov     r8d, 292h; unsigned int
0x1800108fe  mov     [rsp+78h+var_30], rax
0x180010903  lea     rax, aHandleLongPtr1_1; "((HANDLE)(LONG_PTR)-1) != hModule"
0x18001090a  mov     [rsp+78h+var_38], rax
0x18001090f  lea     r9, aCwintaskhandle_1; "CWinTaskHandler::WorkerThreadProc"
0x180010916  mov     [rsp+78h+var_40], 0; unsigned __int16 *
0x18001091f  lea     rax, aAssertSS; "Assert (%s): %s"
0x180010926  mov     [rsp+78h+var_48], 0; char *
0x18001092f  lea     rdx, aOnecoreInterna_2; "onecore\\internal\\admin\\inc\\WinTask."...
0x180010936  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x18001093b  mov     ecx, 1; unsigned int
0x180010940  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x180010948  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x18001094d  mov     rax, [rbx]
0x180010950  mov     rcx, rbx
0x180010953  mov     rax, [rax+10h]
0x180010957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001095c  test    ebp, ebp
0x18001095e  jz      short loc_18001096C
0x180010960  mov     edx, esi; dwExitCode
0x180010962  mov     rcx, rdi; hLibModule
0x180010965  call    cs:__imp_FreeLibraryAndExitThread
0x18001096b  int     3; Trap to Debugger
0x18001096c  mov     eax, esi
0x18001096e  add     rsp, 58h
0x180010972  pop     rdi
0x180010973  pop     rsi
0x180010974  pop     rbp
0x180010975  pop     rbx
0x180010976  retn
```
