# LoadSandboxDll(_pfnWinSpoolDrv *,ushort const *)

- ea: `0x140005ffc`
- end: `0x140006118`
- name: `?LoadSandboxDll@@YAJPEAU_pfnWinSpoolDrv@@PEBG@Z`
- size: `284`
- prototype: `__int64 __fastcall(struct _pfnWinSpoolDrv *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140006694`

## callees

- `0x140005d9c`
- `0x140005dc8`
- `0x140005ffc`
- `0x14000634c`
- `0x140006454`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x140006044`
- `KERNEL32!GetProcAddress` at `0x140006071`
- `KERNEL32!GetProcAddress` at `0x14000609f`
- `KERNEL32!GetProcAddress` at `0x140006044`
- `KERNEL32!GetProcAddress` at `0x140006071`
- `KERNEL32!GetProcAddress` at `0x14000609f`
- `KERNEL32!LoadLibraryW` at `0x140006010`
- `KERNEL32!LoadLibraryW` at `0x140006010`

## string_xrefs

- `0x140006098`: `DllCanUnloadNow`
- `0x1400060b9`: `Sandbox Host: GetProcAddress DllCanUnloadNow failed. Error hr: 0x%x`
- `0x1400060c0`: `LoadSandboxDll`
- `0x1400060e0`: `LoadSandboxDll`
- `0x1400060ff`: `LoadSandboxDll`
- `0x1400060d9`: `Sandbox Host: DLL %ws was loaded`
- `0x1400060f8`: `Sandbox Host: DLL %ws. Error 0x%x`
- `0x140006009`: `PrintIsolationProxy.dll`
- `0x1400060d2`: `PrintIsolationProxy.dll`
- `0x1400060f1`: `PrintIsolationProxy.dll`

## pseudocode

```c
__int64 __fastcall LoadSandboxDll(struct _pfnWinSpoolDrv *a1, const unsigned __int16 *a2)
{
  HMODULE LibraryW; // rax
  NCoreLibrary *v4; // rcx
  __int64 LastErrorAsHResult; // rbx
  NCoreLibrary *v6; // rcx
  FARPROC ProcAddress; // rax
  NCoreLibrary *v8; // rcx
  NCoreLibrary *v9; // rcx

  LibraryW = LoadLibraryW(LibFileName);
  g_hInprocSandbox = LibraryW;
  if ( LibraryW )
  {
    LODWORD(LastErrorAsHResult) = 0;
  }
  else
  {
    LODWORD(LastErrorAsHResult) = NCoreLibrary::GetLastErrorAsHResult(v4);
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_13;
    LibraryW = g_hInprocSandbox;
  }
  g_pfnCreate = (unsigned int (*)(int, struct IPrintSandbox **))GetProcAddress(LibraryW, (LPCSTR)0x190);
  if ( !g_pfnCreate )
  {
    LODWORD(LastErrorAsHResult) = NCoreLibrary::GetLastErrorAsHResult(v6);
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_13;
  }
  ProcAddress = GetProcAddress(g_hInprocSandbox, (LPCSTR)0x191);
  if ( !ProcAddress )
  {
    LODWORD(LastErrorAsHResult) = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8);
    if ( (int)LastErrorAsHResult >= 0 )
      goto LABEL_10;
LABEL_13:
    SandboxTelemetry::WriteDbgTraceError(
      "LoadSandboxDll",
      L"Sandbox Host: DLL %ws. Error 0x%x",
      LibFileName,
      (unsigned int)LastErrorAsHResult);
    return (unsigned int)LastErrorAsHResult;
  }
  ((void (__fastcall *)(struct _pfnWinSpoolDrv *))ProcAddress)(a1);
LABEL_10:
  g_pfnCanUnloadNow = (int (*)(void))GetProcAddress(g_hInprocSandbox, "DllCanUnloadNow");
  if ( !g_pfnCanUnloadNow )
  {
    LastErrorAsHResult = (unsigned int)NCoreLibrary::GetLastErrorAsHResult(v9);
    SandboxTelemetry::WriteDbgTraceError(
      "LoadSandboxDll",
      L"Sandbox Host: GetProcAddress DllCanUnloadNow failed. Error hr: 0x%x",
      LastErrorAsHResult);
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_13;
  }
  SandboxTelemetry::WriteDbgTraceInfo("LoadSandboxDll", L"Sandbox Host: DLL %ws was loaded", LibFileName);
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x140005ffc  mov     [rsp+arg_0], rbx
0x140006001  push    rdi
0x140006002  sub     rsp, 20h
0x140006006  mov     rdi, rcx
0x140006009  lea     rcx, LibFileName; "PrintIsolationProxy.dll"
0x140006010  call    cs:__imp_LoadLibraryW
0x140006016  mov     cs:?g_hInprocSandbox@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hInprocSandbox
0x14000601d  test    rax, rax
0x140006020  jz      short loc_140006026
0x140006022  xor     ebx, ebx
0x140006024  jmp     short loc_14000603C
0x140006026  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000602b  mov     ebx, eax
0x14000602d  test    eax, eax
0x14000602f  js      loc_1400060EE
0x140006035  mov     rax, cs:?g_hInprocSandbox@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInprocSandbox
0x14000603c  mov     edx, 190h; lpProcName
0x140006041  mov     rcx, rax; hModule
0x140006044  call    cs:__imp_GetProcAddress
0x14000604a  mov     cs:?g_pfnCreate@@3P6AKHPEAPEAUIPrintSandbox@@@ZEA, rax; ulong (*g_pfnCreate)(int,IPrintSandbox * *)
0x140006051  test    rax, rax
0x140006054  jnz     short loc_140006065
0x140006056  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x14000605b  mov     ebx, eax
0x14000605d  test    eax, eax
0x14000605f  js      loc_1400060EE
0x140006065  mov     rcx, cs:?g_hInprocSandbox@@3PEAUHINSTANCE__@@EA; hModule
0x14000606c  mov     edx, 191h; lpProcName
0x140006071  call    cs:__imp_GetProcAddress
0x140006077  test    rax, rax
0x14000607a  jz      short loc_140006086
0x14000607c  mov     rcx, rdi
0x14000607f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006084  jmp     short loc_140006091
0x140006086  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x14000608b  mov     ebx, eax
0x14000608d  test    eax, eax
0x14000608f  js      short loc_1400060EE
0x140006091  mov     rcx, cs:?g_hInprocSandbox@@3PEAUHINSTANCE__@@EA; hModule
0x140006098  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x14000609f  call    cs:__imp_GetProcAddress
0x1400060a5  mov     cs:?g_pfnCanUnloadNow@@3P6AJXZEA, rax; long (*g_pfnCanUnloadNow)(void)
0x1400060ac  test    rax, rax
0x1400060af  jnz     short loc_1400060D2
0x1400060b1  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x1400060b6  mov     r8d, eax
0x1400060b9  lea     rdx, aSandboxHostGet; "Sandbox Host: GetProcAddress DllCanUnlo"...
0x1400060c0  lea     rcx, aLoadsandboxdll; "LoadSandboxDll"
0x1400060c7  mov     ebx, eax
0x1400060c9  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400060ce  test    ebx, ebx
0x1400060d0  js      short loc_1400060EE
0x1400060d2  lea     r8, LibFileName; "PrintIsolationProxy.dll"
0x1400060d9  lea     rdx, aSandboxHostDll_0; "Sandbox Host: DLL %ws was loaded"
0x1400060e0  lea     rcx, aLoadsandboxdll; "LoadSandboxDll"
0x1400060e7  call    ?WriteDbgTraceInfo@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400060ec  jmp     short loc_14000610B
0x1400060ee  mov     r9d, ebx
0x1400060f1  lea     r8, LibFileName; "PrintIsolationProxy.dll"
0x1400060f8  lea     rdx, aSandboxHostDll; "Sandbox Host: DLL %ws. Error 0x%x"
0x1400060ff  lea     rcx, aLoadsandboxdll; "LoadSandboxDll"
0x140006106  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14000610b  mov     eax, ebx
0x14000610d  mov     rbx, [rsp+28h+arg_0]
0x140006112  add     rsp, 20h
0x140006116  pop     rdi
0x140006117  retn
```
