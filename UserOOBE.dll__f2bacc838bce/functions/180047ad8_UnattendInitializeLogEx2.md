# UnattendInitializeLogEx2

- ea: `0x180047ad8`
- end: `0x180047bc7`
- name: `UnattendInitializeLogEx2`
- size: `239`
- prototype: `void()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180008d90`

## callees

- `0x180047830`
- `0x180047ad8`
- `0x180049484`
- `0x18004a000`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047b95`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180047b95`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180047b31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180047b31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ae5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180047ae5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180047bc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047ba0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180047ba0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047bae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180047bae`

## string_xrefs

- `0x180047b28`: `wdscore.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void UnattendInitializeLogEx2()
{
  __int64 Expand; // rax
  void *v1; // rbx
  HMODULE Library; // rax
  HANDLE ProcessHeap; // rax

  EnterCriticalSection(&CriticalSection);
  ++dword_18006E720;
  if ( dword_18006E6F8 )
    goto LABEL_14;
  hLibModule = 0;
  Expand = AllocateExpand(L"%windir%\\Panther\\UnattendGC");
  v1 = (void *)Expand;
  if ( Expand )
    CreatePath(Expand);
  Library = LoadLibraryExW(L"wdscore.dll", 0, 0);
  hLibModule = Library;
  if ( !Library )
    goto LABEL_9;
  if ( (int)InitFuncPointerTable() < 0 || !qword_18006E700 )
  {
    Library = hLibModule;
LABEL_9:
    if ( !dword_18006E6F8 && Library )
      FreeLibrary(Library);
    goto LABEL_12;
  }
  qword_18006E700(0, 50393088, v1);
  dword_18006E6F8 = 1;
  dword_18006E740 = 1;
LABEL_12:
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
LABEL_14:
  LeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180047ad8  push    rbx
0x180047ada  sub     rsp, 20h
0x180047ade  lea     rcx, CriticalSection; lpCriticalSection
0x180047ae5  call    cs:__imp_EnterCriticalSection
0x180047aeb  inc     cs:dword_18006E720
0x180047af1  cmp     cs:dword_18006E6F8, 0
0x180047af8  jnz     loc_180047BB4
0x180047afe  lea     rcx, Src; "%windir%\\Panther\\UnattendGC"
0x180047b05  mov     cs:hLibModule, 0
0x180047b10  call    AllocateExpand
0x180047b15  mov     rbx, rax
0x180047b18  test    rax, rax
0x180047b1b  jz      short loc_180047B25
0x180047b1d  mov     rcx, rax
0x180047b20  call    CreatePath
0x180047b25  xor     r8d, r8d; dwFlags
0x180047b28  lea     rcx, aWdscoreDll; "wdscore.dll"
0x180047b2f  xor     edx, edx; hFile
0x180047b31  call    cs:__imp_LoadLibraryExW
0x180047b37  mov     cs:hLibModule, rax
0x180047b3e  test    rax, rax
0x180047b41  jz      short loc_180047B84
0x180047b43  call    InitFuncPointerTable
0x180047b48  test    eax, eax
0x180047b4a  js      short loc_180047B7D
0x180047b4c  mov     rax, cs:qword_18006E700
0x180047b53  test    rax, rax
0x180047b56  jz      short loc_180047B7D
0x180047b58  mov     r8, rbx
0x180047b5b  mov     edx, 300F000h
0x180047b60  xor     ecx, ecx
0x180047b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047b67  mov     cs:dword_18006E6F8, 1
0x180047b71  mov     cs:dword_18006E740, 1
0x180047b7b  jmp     short loc_180047B9B
0x180047b7d  mov     rax, cs:hLibModule
0x180047b84  cmp     cs:dword_18006E6F8, 0
0x180047b8b  jnz     short loc_180047B9B
0x180047b8d  test    rax, rax
0x180047b90  jz      short loc_180047B9B
0x180047b92  mov     rcx, rax; hLibModule
0x180047b95  call    cs:__imp_FreeLibrary
0x180047b9b  test    rbx, rbx
0x180047b9e  jz      short loc_180047BB4
0x180047ba0  call    cs:__imp_GetProcessHeap
0x180047ba6  mov     r8, rbx; lpMem
0x180047ba9  xor     edx, edx; dwFlags
0x180047bab  mov     rcx, rax; hHeap
0x180047bae  call    cs:__imp_HeapFree
0x180047bb4  lea     rcx, CriticalSection
0x180047bbb  add     rsp, 20h
0x180047bbf  pop     rbx
0x180047bc0  jmp     cs:__imp_LeaveCriticalSection
```
