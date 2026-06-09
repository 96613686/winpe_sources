# UnattendInitializeLogEx2

- ea: `0x140073db8`
- end: `0x140073f28`
- name: `UnattendInitializeLogEx2`
- size: `368`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting, service_task`

## callers

- `0x140071a28`

## callees

- `0x140005f30`
- `0x140073b10`
- `0x140073db8`
- `0x14007417c`
- `0x1400742ac`
- `0x140074d18`
- `0x140074d90`
- `0x14007d010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x140073f09`
- `KERNEL32!LeaveCriticalSection` at `0x140073f09`
- `KERNEL32!EnterCriticalSection` at `0x140073dda`
- `KERNEL32!EnterCriticalSection` at `0x140073dda`
- `KERNEL32!HeapFree` at `0x140073efc`
- `KERNEL32!HeapFree` at `0x140073efc`
- `KERNEL32!GetProcessHeap` at `0x140073eee`
- `KERNEL32!GetProcessHeap` at `0x140073eee`
- `KERNEL32!CloseHandle` at `0x140073e74`
- `KERNEL32!CloseHandle` at `0x140073e74`
- `KERNEL32!LoadLibraryExW` at `0x140073e86`
- `KERNEL32!LoadLibraryExW` at `0x140073e86`
- `KERNEL32!FreeLibrary` at `0x140073ee3`
- `KERNEL32!FreeLibrary` at `0x140073ee3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140073e61`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140073e61`

## string_xrefs

- `0x140073df3`: `%windir%\Logs\ReAgent\ReAgent.log`
- `0x140073e7d`: `wdscore.dll`

## pseudocode

```c
void UnattendInitializeLogEx2()
{
  const wchar_t *Expand; // rax
  WCHAR *v1; // rbx
  HANDLE FileW; // rax
  HANDLE ProcessHeap; // rax
  wchar_t pszDest[520]; // [rsp+40h] [rbp-428h] BYREF

  EnterCriticalSection(&CriticalSection);
  ++dword_1400AC660;
  if ( !dword_1400AC670 )
  {
    hLibModule = 0;
    Expand = (const wchar_t *)AllocateExpand(L"%windir%\\Logs\\ReAgent\\ReAgent.log");
    v1 = (WCHAR *)Expand;
    if ( Expand )
    {
      if ( (unsigned int)WdsGetParentPath(Expand, pszDest) )
        CreatePath(pszDest);
      if ( !(unsigned int)FileExists(v1) )
      {
        FileW = CreateFileW(v1, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
        if ( FileW == (HANDLE)-1LL )
          goto LABEL_17;
        CloseHandle(FileW);
      }
    }
    hLibModule = LoadLibraryExW(L"wdscore.dll", 0, 0);
    if ( hLibModule && (int)InitFuncPointerTable() >= 0 && qword_1400AC6A8 )
    {
      qword_1400AC6A8(v1, 50393088);
      dword_1400AC670 = 1;
      dword_1400AC698 = 1;
    }
    if ( !dword_1400AC670 && hLibModule )
      FreeLibrary(hLibModule);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
  }
LABEL_17:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x140073db8  push    rbx
0x140073dba  sub     rsp, 460h
0x140073dc1  mov     rax, cs:__security_cookie
0x140073dc8  xor     rax, rsp
0x140073dcb  mov     [rsp+468h+var_18], rax
0x140073dd3  lea     rcx, CriticalSection; lpCriticalSection
0x140073dda  call    cs:__imp_EnterCriticalSection
0x140073de0  inc     cs:dword_1400AC660
0x140073de6  cmp     cs:dword_1400AC670, 0
0x140073ded  jnz     loc_140073F02
0x140073df3  lea     rcx, aWindirLogsReag; "%windir%\\Logs\\ReAgent\\ReAgent.log"
0x140073dfa  mov     cs:hLibModule, 0
0x140073e05  call    AllocateExpand
0x140073e0a  mov     rbx, rax
0x140073e0d  test    rax, rax
0x140073e10  jz      short loc_140073E7A
0x140073e12  lea     rdx, [rsp+468h+pszDest]; pszDest
0x140073e17  mov     rcx, rax; pszSrc
0x140073e1a  call    WdsGetParentPath
0x140073e1f  test    eax, eax
0x140073e21  jz      short loc_140073E2D
0x140073e23  lea     rcx, [rsp+468h+pszDest]
0x140073e28  call    CreatePath
0x140073e2d  mov     rcx, rbx
0x140073e30  call    FileExists
0x140073e35  test    eax, eax
0x140073e37  jnz     short loc_140073E7A
0x140073e39  mov     [rsp+468h+hTemplateFile], 0; hTemplateFile
0x140073e42  lea     r8d, [rax+3]; dwShareMode
0x140073e46  mov     [rsp+468h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x140073e4e  xor     r9d, r9d; lpSecurityAttributes
0x140073e51  mov     edx, 0C0000000h; dwDesiredAccess
0x140073e56  mov     [rsp+468h+dwCreationDisposition], 4; dwCreationDisposition
0x140073e5e  mov     rcx, rbx; lpFileName
0x140073e61  call    cs:__imp_CreateFileW
0x140073e67  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140073e6b  jz      loc_140073F02
0x140073e71  mov     rcx, rax; hObject
0x140073e74  call    cs:__imp_CloseHandle
0x140073e7a  xor     r8d, r8d; dwFlags
0x140073e7d  lea     rcx, aWdscoreDll_0; "wdscore.dll"
0x140073e84  xor     edx, edx; hFile
0x140073e86  call    cs:__imp_LoadLibraryExW
0x140073e8c  mov     cs:hLibModule, rax
0x140073e93  test    rax, rax
0x140073e96  jz      short loc_140073ECE
0x140073e98  call    InitFuncPointerTable
0x140073e9d  test    eax, eax
0x140073e9f  js      short loc_140073ECE
0x140073ea1  mov     rax, cs:qword_1400AC6A8
0x140073ea8  test    rax, rax
0x140073eab  jz      short loc_140073ECE
0x140073ead  mov     edx, 300F000h
0x140073eb2  mov     rcx, rbx
0x140073eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140073eba  mov     cs:dword_1400AC670, 1
0x140073ec4  mov     cs:dword_1400AC698, 1
0x140073ece  cmp     cs:dword_1400AC670, 0
0x140073ed5  jnz     short loc_140073EE9
0x140073ed7  mov     rcx, cs:hLibModule; hLibModule
0x140073ede  test    rcx, rcx
0x140073ee1  jz      short loc_140073EE9
0x140073ee3  call    cs:__imp_FreeLibrary
0x140073ee9  test    rbx, rbx
0x140073eec  jz      short loc_140073F02
0x140073eee  call    cs:__imp_GetProcessHeap
0x140073ef4  mov     r8, rbx; lpMem
0x140073ef7  xor     edx, edx; dwFlags
0x140073ef9  mov     rcx, rax; hHeap
0x140073efc  call    cs:__imp_HeapFree
0x140073f02  lea     rcx, CriticalSection; lpCriticalSection
0x140073f09  call    cs:__imp_LeaveCriticalSection
0x140073f0f  mov     rcx, [rsp+468h+var_18]
0x140073f17  xor     rcx, rsp; StackCookie
0x140073f1a  call    __security_check_cookie
0x140073f1f  add     rsp, 460h
0x140073f26  pop     rbx
0x140073f27  retn
```
