# FreeLibraryThreadMain(void *)

- ea: `0x180024320`
- end: `0x18002435c`
- name: `?FreeLibraryThreadMain@@YAKPEAX@Z`
- size: `60`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180024320`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180024355`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibraryAndExitThread` at `0x180024355`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180024332`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180024332`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180024324`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024346`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180024346`

## pseudocode

```c
void __fastcall __noreturn FreeLibraryThreadMain(PVOID Parameter)
{
  HANDLE CurrentThread; // rax
  BOOL v2; // eax
  DWORD v3; // ecx

  CurrentThread = GetCurrentThread();
  v2 = SetThreadPriority(CurrentThread, -2);
  v3 = 1000;
  if ( !v2 )
    v3 = 120000;
  Sleep(v3);
  FreeLibraryAndExitThread(g_hProxy, 0);
}

```

## disassembly

```asm
0x180024320  sub     rsp, 28h
0x180024324  call    cs:__imp_GetCurrentThread
0x18002432a  mov     rcx, rax; hThread
0x18002432d  mov     edx, 0FFFFFFFEh; nPriority
0x180024332  call    cs:__imp_SetThreadPriority
0x180024338  mov     ecx, 3E8h
0x18002433d  test    eax, eax
0x18002433f  jnz     short loc_180024346
0x180024341  mov     ecx, 1D4C0h; dwMilliseconds
0x180024346  call    cs:__imp_Sleep
0x18002434c  mov     rcx, cs:?g_hProxy@@3PEAUHINSTANCE__@@EA; hLibModule
0x180024353  xor     edx, edx; dwExitCode
0x180024355  call    cs:__imp_FreeLibraryAndExitThread
```
