# Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule

- ea: `0x18003a47c`
- end: `0x18003a562`
- name: `Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003a568`

## callees

- `0x18002ff90`
- `0x180036d78`
- `0x180036ed8`
- `0x18003a47c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a4c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a4c7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a4f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a4f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a521`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003a521`

## string_xrefs

- `0x18003a530`: `C:\__w\1\s\src\orchestrator\system\windows\common\DockedHelpers.cpp`
- `0x18003a4c0`: `UsoDocked.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HMODULE Windows::DockedHelpers::_anonymous_namespace_::GetUsoDockedModule()
{
  int v0; // eax
  HMODULE v1; // rbx
  HMODULE Library; // rax
  const char *v3; // r9
  HMODULE v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( (unsigned int)mtx_do_lock(qword_18009D2D0) )
    std::_Throw_Cpp_error(5);
  v0 = dword_18009D31C;
  if ( dword_18009D31C == 0x7FFFFFFF )
  {
    dword_18009D31C = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v1 = hLibModule;
  if ( !hLibModule )
  {
    Library = LoadLibraryExW(L"UsoDocked.dll", 0, 0x800u);
    v1 = Library;
    if ( !Library )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x19,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\DockedHelpers.cpp",
        v3);
    v4 = hLibModule;
    hLibModule = Library;
    if ( v4 )
    {
      FreeLibrary(v4);
      v1 = hLibModule;
    }
    v0 = dword_18009D31C;
  }
  dword_18009D31C = v0 - 1;
  if ( v0 == 1 )
  {
    dword_18009D318 = -1;
    ReleaseSRWLockExclusive(&stru_18009D2E0);
  }
  return v1;
}

```

## disassembly

```asm
0x18003a47c  push    rbx
0x18003a47e  sub     rsp, 20h
0x18003a482  lea     rcx, qword_18009D2D0
0x18003a489  mov     [rsp+28h+arg_0], rcx
0x18003a48e  call    mtx_do_lock
0x18003a493  test    eax, eax
0x18003a495  jnz     loc_18003A542
0x18003a49b  mov     eax, cs:dword_18009D31C
0x18003a4a1  cmp     eax, 7FFFFFFFh
0x18003a4a6  jz      loc_18003A54D
0x18003a4ac  mov     rbx, cs:hLibModule
0x18003a4b3  test    rbx, rbx
0x18003a4b6  jnz     short loc_18003A505
0x18003a4b8  xor     edx, edx; hFile
0x18003a4ba  mov     r8d, 800h; dwFlags
0x18003a4c0  lea     rcx, aUsodockedDll; "UsoDocked.dll"
0x18003a4c7  call    cs:__imp_LoadLibraryExW
0x18003a4cd  mov     rbx, rax
0x18003a4d0  mov     [rsp+28h+arg_8], rax
0x18003a4d5  mov     rcx, [rsp+28h]; this
0x18003a4da  test    rax, rax
0x18003a4dd  jz      short loc_18003A530
0x18003a4df  mov     rcx, cs:hLibModule; hLibModule
0x18003a4e6  mov     cs:hLibModule, rax
0x18003a4ed  test    rcx, rcx
0x18003a4f0  jz      short loc_18003A4FF
0x18003a4f2  call    cs:__imp_FreeLibrary
0x18003a4f8  mov     rbx, cs:hLibModule
0x18003a4ff  mov     eax, cs:dword_18009D31C
0x18003a505  sub     eax, 1
0x18003a508  mov     cs:dword_18009D31C, eax
0x18003a50e  jnz     short loc_18003A527
0x18003a510  mov     cs:dword_18009D318, 0FFFFFFFFh
0x18003a51a  lea     rcx, stru_18009D2E0; SRWLock
0x18003a521  call    cs:__imp_ReleaseSRWLockExclusive
0x18003a527  mov     rax, rbx
0x18003a52a  add     rsp, 20h
0x18003a52e  pop     rbx
0x18003a52f  retn
0x18003a530  lea     r8, aCW1SSrcOrchest_1; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003a537  mov     edx, 19h; void *
0x18003a53c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003a542  mov     ecx, 5; int
0x18003a547  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18003a54d  mov     cs:dword_18009D31C, 7FFFFFFEh
0x18003a557  mov     ecx, 6; int
0x18003a55c  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
