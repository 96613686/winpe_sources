# DllMain

- ea: `0x1800133cc`
- end: `0x1800134b1`
- name: `DllMain`
- size: `229`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001344`

## callees

- `0x1800133cc`
- `0x180034098`
- `0x180034154`
- `0x180034558`
- `0x18003466c`
- `0x1800348c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013486`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180013486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013421`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013491`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180013491`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013467`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180013467`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800133fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x1800133fe`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013407`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180013407`

## string_xrefs

- `0x1800133f7`: `Unable to Create Debug Print Object \n`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  signed int LastError; // eax
  bool v5; // sf
  _QWORD *v6; // rbx
  void *v7; // rdi
  DWORD v8; // eax

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      g_pDebug = (HGLOBAL)PuCreateDebugPrintsObject(hinstDLL, fdwReason, lpvReserved);
      if ( !g_pDebug )
        OutputDebugStringA("Unable to Create Debug Print Object \n");
      DisableThreadLibraryCalls(hinstDLL);
      g_hModule = hinstDLL;
      if ( !(unsigned int)InitializeIISUtilProcessAttach() )
      {
        LastError = GetLastError();
        v5 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = LastError < 0;
        }
        if ( v5 )
          g_hrInitStatus = LastError;
      }
    }
  }
  else
  {
    TerminateIISUtilProcessDetach();
    v6 = g_pDebug;
    if ( g_pDebug )
    {
      v7 = (void *)*((_QWORD *)g_pDebug + 82);
      if ( v7 )
      {
        CMemoryLog::~CMemoryLog(*((CMemoryLog **)g_pDebug + 82));
        LocalFree(v7);
        v6[82] = 0;
      }
      v8 = PuCloseDbgPrintFile(v6);
      if ( v8 )
        SetLastError(v8);
      else
        v6 = GlobalFree(v6);
    }
    g_pDebug = v6;
  }
  return 1;
}

```

## disassembly

```asm
0x1800133cc  mov     [rsp+arg_0], rbx
0x1800133d1  push    rdi
0x1800133d2  sub     rsp, 20h
0x1800133d6  mov     rbx, rcx
0x1800133d9  test    edx, edx
0x1800133db  jz      short loc_18001343F
0x1800133dd  cmp     edx, 1
0x1800133e0  jnz     loc_1800134A1
0x1800133e6  call    PuCreateDebugPrintsObject
0x1800133eb  mov     cs:g_pDebug, rax
0x1800133f2  test    rax, rax
0x1800133f5  jnz     short loc_180013404
0x1800133f7  lea     rcx, OutputString; "Unable to Create Debug Print Object \n"
0x1800133fe  call    cs:__imp_OutputDebugStringA
0x180013404  mov     rcx, rbx; hLibModule
0x180013407  call    cs:__imp_DisableThreadLibraryCalls
0x18001340d  mov     cs:?g_hModule@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hModule
0x180013414  call    InitializeIISUtilProcessAttach
0x180013419  test    eax, eax
0x18001341b  jnz     loc_1800134A1
0x180013421  call    cs:__imp_GetLastError
0x180013427  test    eax, eax
0x180013429  jle     short loc_180013435
0x18001342b  movzx   eax, ax
0x18001342e  or      eax, 80070000h
0x180013433  test    eax, eax
0x180013435  jns     short loc_1800134A1
0x180013437  mov     cs:?g_hrInitStatus@@3JA, eax; long g_hrInitStatus
0x18001343d  jmp     short loc_1800134A1
0x18001343f  call    TerminateIISUtilProcessDetach
0x180013444  mov     rbx, cs:g_pDebug
0x18001344b  test    rbx, rbx
0x18001344e  jz      short loc_18001349A
0x180013450  mov     rdi, [rbx+290h]
0x180013457  test    rdi, rdi
0x18001345a  jz      short loc_180013478
0x18001345c  mov     rcx, rdi; this
0x18001345f  call    ??1CMemoryLog@@QEAA@XZ; CMemoryLog::~CMemoryLog(void)
0x180013464  mov     rcx, rdi; hMem
0x180013467  call    cs:__imp_LocalFree
0x18001346d  mov     qword ptr [rbx+290h], 0
0x180013478  mov     rcx, rbx
0x18001347b  call    PuCloseDbgPrintFile
0x180013480  test    eax, eax
0x180013482  jz      short loc_18001348E
0x180013484  mov     ecx, eax; dwErrCode
0x180013486  call    cs:__imp_SetLastError
0x18001348c  jmp     short loc_18001349A
0x18001348e  mov     rcx, rbx; hMem
0x180013491  call    cs:__imp_GlobalFree
0x180013497  mov     rbx, rax
0x18001349a  mov     cs:g_pDebug, rbx
0x1800134a1  mov     rbx, [rsp+28h+arg_0]
0x1800134a6  mov     eax, 1
0x1800134ab  add     rsp, 20h
0x1800134af  pop     rdi
0x1800134b0  retn
```
