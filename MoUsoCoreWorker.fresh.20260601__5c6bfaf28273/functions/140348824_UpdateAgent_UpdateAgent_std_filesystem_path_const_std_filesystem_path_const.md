# UpdateAgent::UpdateAgent(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x140348824`
- end: `0x1403488fd`
- name: `??0UpdateAgent@@QEAA@AEBVpath@filesystem@std@@0@Z`
- size: `217`
- prototype: `UpdateAgent *__fastcall(UpdateAgent *this, const struct std::filesystem::path *, const struct std::filesystem::path *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140307b7c`
- `0x140307e30`
- `0x140307f9c`
- `0x140348200`
- `0x14034a1bc`

## callees

- `0x14003c578`
- `0x1400447ac`
- `0x140348824`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14034886a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14034886a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140348887`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140348887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1403488ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1403488ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14034888f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14034888f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14034887c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14034887c`

## string_xrefs

- `0x1403488a3`: `CreateDeploymentSession`
- `0x1403488d9`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\localprovider\UpdateAgent.cpp`
- `0x1403488eb`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\localprovider\UpdateAgent.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=23 #try_helpers=1
UpdateAgent *__fastcall UpdateAgent::UpdateAgent(
        UpdateAgent *this,
        const struct std::filesystem::path *a2,
        const struct std::filesystem::path *a3)
{
  HMODULE Library; // rsi
  const char *v6; // r9
  HMODULE v7; // rbp
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  const char *v10; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  std::wstring::wstring(this, a2);
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const struct std::filesystem::path **)a3;
  Library = LoadLibraryExW((LPCWSTR)a3, 0, 0);
  v7 = (HMODULE)*((_QWORD *)this + 5);
  if ( v7 )
  {
    LastError = GetLastError();
    FreeLibrary(v7);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 5) = Library;
  if ( !Library )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x10,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\localprovider\\UpdateAgent.cpp",
      v6);
  ProcAddress = GetProcAddress(Library, "CreateDeploymentSession");
  *((_QWORD *)this + 4) = ProcAddress;
  if ( !ProcAddress )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\localprovider\\UpdateAgent.cpp",
      v10);
  return this;
}

```

## disassembly

```asm
0x140348824  mov     rax, rsp
0x140348827  mov     [rax+10h], rbx
0x14034882b  mov     [rax+18h], rbp
0x14034882f  mov     [rax+20h], rsi
0x140348833  mov     [rax+8], rcx
0x140348837  push    rdi
0x140348838  sub     rsp, 20h
0x14034883c  mov     rbx, r8
0x14034883f  mov     rdi, rcx
0x140348842  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140348847  nop
0x140348848  mov     qword ptr [rdi+20h], 0
0x140348850  mov     qword ptr [rdi+28h], 0
0x140348858  cmp     qword ptr [rbx+18h], 7
0x14034885d  jbe     short loc_140348862
0x14034885f  mov     rbx, [rbx]
0x140348862  xor     r8d, r8d; dwFlags
0x140348865  xor     edx, edx; hFile
0x140348867  mov     rcx, rbx; lpLibFileName
0x14034886a  call    cs:__imp_LoadLibraryExW
0x140348870  mov     rsi, rax
0x140348873  mov     rbp, [rdi+28h]
0x140348877  test    rbp, rbp
0x14034887a  jz      short loc_140348895
0x14034887c  call    cs:__imp_GetLastError
0x140348882  mov     ebx, eax
0x140348884  mov     rcx, rbp; hLibModule
0x140348887  call    cs:__imp_FreeLibrary
0x14034888d  mov     ecx, ebx; dwErrCode
0x14034888f  call    cs:__imp_SetLastError
0x140348895  mov     [rdi+28h], rsi
0x140348899  mov     rcx, [rsp+28h]; this
0x14034889e  test    rsi, rsi
0x1403488a1  jz      short loc_1403488EB
0x1403488a3  lea     rdx, aCreatedeployme; "CreateDeploymentSession"
0x1403488aa  mov     rcx, rsi; hModule
0x1403488ad  call    cs:__imp_GetProcAddress
0x1403488b3  mov     [rdi+20h], rax
0x1403488b7  mov     rcx, [rsp+28h]; this
0x1403488bc  test    rax, rax
0x1403488bf  jz      short loc_1403488D9
0x1403488c1  mov     rax, rdi
0x1403488c4  mov     rbx, [rsp+28h+arg_8]
0x1403488c9  mov     rbp, [rsp+28h+arg_10]
0x1403488ce  mov     rsi, [rsp+28h+arg_18]
0x1403488d3  add     rsp, 20h
0x1403488d7  pop     rdi
0x1403488d8  retn
0x1403488d9  lea     r8, aCW1SSrcOrchest_57; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403488e0  mov     edx, 15h; void *
0x1403488e5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1403488eb  lea     r8, aCW1SSrcOrchest_57; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403488f2  mov     edx, 10h; void *
0x1403488f7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
