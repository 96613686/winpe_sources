# Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl::InitializeKernelTraceControlFunctions(void)

- ea: `0x14000f938`
- end: `0x14000f9d3`
- name: `?InitializeKernelTraceControlFunctions@KernelTraceControl@StandardCollector@DiagnosticsHub@Microsoft@@AEAAKXZ`
- size: `155`
- prototype: `DWORD __fastcall(Microsoft::DiagnosticsHub::StandardCollector::KernelTraceControl *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000f838`

## callees

- `0x14000a278`
- `0x14000f510`
- `0x14000f938`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000f98c`
- `KERNEL32!GetProcAddress` at `0x14000f9ae`
- `KERNEL32!GetProcAddress` at `0x14000f98c`
- `KERNEL32!GetProcAddress` at `0x14000f9ae`
- `KERNEL32!GetLastError` at `0x14000f97a`
- `KERNEL32!GetLastError` at `0x14000f97a`

## string_xrefs

- `0x14000f96e`: `D:\a\_work\1\s\sources\Core\DiagnosticsHub.Common\KernelTraceControl.cpp`
- `0x14000f960`: `Failed to load KernelTraceControl.dll.`
- `0x14000f982`: `CreateMergedTraceFile`
- `0x14000f99b`: `Failed to locate CreateMergedTraceFile KernelTraceControl function.`
- `0x14000f9a7`: `UpdateHeapTrace`
- `0x14000f9bd`: `Failed to locate UpdateHeapTrace KernelTraceControl function.`

## pseudocode

```c
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
0x14000f938  mov     [rsp+arg_0], rbx
0x14000f93d  push    rdi
0x14000f93e  sub     rsp, 20h
0x14000f942  cmp     qword ptr [rcx+8], 0
0x14000f947  mov     rbx, rcx
0x14000f94a  jz      short loc_14000F953
0x14000f94c  cmp     qword ptr [rcx+10h], 0
0x14000f951  jnz     short loc_14000F9C6
0x14000f953  call    _anonymous_namespace___LoadKernelTraceControl
0x14000f958  mov     [rbx], rax
0x14000f95b  test    rax, rax
0x14000f95e  jnz     short loc_14000F982
0x14000f960  lea     r8, aFailedToLoadKe; "Failed to load KernelTraceControl.dll."
0x14000f967  lea     rcx, [rbx+0C0h]; this
0x14000f96e  lea     rdx, aDAWork1SSource_2; "D:\\a\\_work\\1\\s\\sources\\Core\\Diag"...
0x14000f975  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x14000f97a  call    cs:__imp_GetLastError
0x14000f980  jmp     short loc_14000F9C8
0x14000f982  lea     rdx, aCreatemergedtr; "CreateMergedTraceFile"
0x14000f989  mov     rcx, rax; hModule
0x14000f98c  call    cs:__imp_GetProcAddress
0x14000f992  mov     [rbx+8], rax
0x14000f996  test    rax, rax
0x14000f999  jnz     short loc_14000F9A4
0x14000f99b  lea     r8, aFailedToLocate; "Failed to locate CreateMergedTraceFile "...
0x14000f9a2  jmp     short loc_14000F967
0x14000f9a4  mov     rcx, [rbx]; hModule
0x14000f9a7  lea     rdx, aUpdateheaptrac; "UpdateHeapTrace"
0x14000f9ae  call    cs:__imp_GetProcAddress
0x14000f9b4  mov     [rbx+10h], rax
0x14000f9b8  test    rax, rax
0x14000f9bb  jnz     short loc_14000F9C6
0x14000f9bd  lea     r8, aFailedToLocate_0; "Failed to locate UpdateHeapTrace Kernel"...
0x14000f9c4  jmp     short loc_14000F967
0x14000f9c6  xor     eax, eax
0x14000f9c8  mov     rbx, [rsp+28h+arg_0]
0x14000f9cd  add     rsp, 20h
0x14000f9d1  pop     rdi
0x14000f9d2  retn
```
