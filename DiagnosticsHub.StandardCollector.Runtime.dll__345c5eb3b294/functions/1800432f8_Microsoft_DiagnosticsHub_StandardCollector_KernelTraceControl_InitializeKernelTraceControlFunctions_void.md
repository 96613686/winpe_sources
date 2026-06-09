# Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::InitializeKernelTraceControlFunctions(void)

- ea: `0x1800432f8`
- end: `0x180043393`
- name: `?InitializeKernelTraceControlFunctions@KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@AEAAKXZ`
- size: `155`
- prototype: `DWORD __fastcall(Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004317c`
- `0x18004327c`

## callees

- `0x18003d864`
- `0x180042e38`
- `0x1800432f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004333a`
- `KERNEL32!GetLastError` at `0x18004333a`
- `KERNEL32!GetProcAddress` at `0x18004334c`
- `KERNEL32!GetProcAddress` at `0x18004336e`
- `KERNEL32!GetProcAddress` at `0x18004334c`
- `KERNEL32!GetProcAddress` at `0x18004336e`

## string_xrefs

- `0x18004332e`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x180043320`: `Failed to load KernelTraceControl.dll.`
- `0x180043342`: `CreateMergedTraceFile`
- `0x18004335b`: `Failed to locate CreateMergedTraceFile KernelTraceControl function.`
- `0x180043367`: `UpdateHeapTrace`
- `0x18004337d`: `Failed to locate UpdateHeapTrace KernelTraceControl function.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
DWORD __fastcall Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::InitializeKernelTraceControlFunctions(
        Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *this)
{
  HMODULE KernelTraceControl; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  if ( !*((_QWORD *)this + 1) || !*((_QWORD *)this + 2) )
  {
    KernelTraceControl = (HMODULE)anonymous_namespace_::LoadKernelTraceControl();
    *(_QWORD *)this = KernelTraceControl;
    if ( !KernelTraceControl )
    {
      DiagHubCommon::LogStream::Write(
        (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 192),
        L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
        L"Failed to load KernelTraceControl.dll.");
      return GetLastError();
    }
    ProcAddress = GetProcAddress(KernelTraceControl, "CreateMergedTraceFile");
    *((_QWORD *)this + 1) = ProcAddress;
    if ( !ProcAddress )
    {
      DiagHubCommon::LogStream::Write(
        (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 192),
        L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
        L"Failed to locate CreateMergedTraceFile KernelTraceControl function.");
      return GetLastError();
    }
    v5 = GetProcAddress(*(HMODULE *)this, "UpdateHeapTrace");
    *((_QWORD *)this + 2) = v5;
    if ( !v5 )
    {
      DiagHubCommon::LogStream::Write(
        (Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *)((char *)this + 192),
        L"D:\\a\\_work\\1\\s\\sources\\Core\\DiagnosticsHub.Common\\KernelTraceControl.cpp",
        L"Failed to locate UpdateHeapTrace KernelTraceControl function.");
      return GetLastError();
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800432f8  mov     [rsp+arg_0], rbx
0x1800432fd  push    rdi
0x1800432fe  sub     rsp, 20h
0x180043302  cmp     qword ptr [rcx+8], 0
0x180043307  mov     rbx, rcx
0x18004330a  jz      short loc_180043313
0x18004330c  cmp     qword ptr [rcx+10h], 0
0x180043311  jnz     short loc_180043386
0x180043313  call    _anonymous_namespace___LoadKernelTraceControl
0x180043318  mov     [rbx], rax
0x18004331b  test    rax, rax
0x18004331e  jnz     short loc_180043342
0x180043320  lea     r8, aFailedToLoadKe; "Failed to load KernelTraceControl.dll."
0x180043327  lea     rcx, [rbx+0C0h]; this
0x18004332e  lea     rdx, aDAWork1SSource_14; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x180043335  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x18004333a  call    cs:__imp_GetLastError
0x180043340  jmp     short loc_180043388
0x180043342  lea     rdx, aCreatemergedtr; "CreateMergedTraceFile"
0x180043349  mov     rcx, rax; hModule
0x18004334c  call    cs:__imp_GetProcAddress
0x180043352  mov     [rbx+8], rax
0x180043356  test    rax, rax
0x180043359  jnz     short loc_180043364
0x18004335b  lea     r8, aFailedToLocate; "Failed to locate CreateMergedTraceFile "...
0x180043362  jmp     short loc_180043327
0x180043364  mov     rcx, [rbx]; hModule
0x180043367  lea     rdx, aUpdateheaptrac; "UpdateHeapTrace"
0x18004336e  call    cs:__imp_GetProcAddress
0x180043374  mov     [rbx+10h], rax
0x180043378  test    rax, rax
0x18004337b  jnz     short loc_180043386
0x18004337d  lea     r8, aFailedToLocate_0; "Failed to locate UpdateHeapTrace Kernel"...
0x180043384  jmp     short loc_180043327
0x180043386  xor     eax, eax
0x180043388  mov     rbx, [rsp+28h+arg_0]
0x18004338d  add     rsp, 20h
0x180043391  pop     rdi
0x180043392  retn
```
