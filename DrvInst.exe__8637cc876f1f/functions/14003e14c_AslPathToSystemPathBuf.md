# AslPathToSystemPathBuf

- ea: `0x14003e14c`
- end: `0x14003e246`
- name: `AslPathToSystemPathBuf`
- size: `250`
- prototype: `__int64 __fastcall(void *, __int64, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x140035aa0`
- `0x14003e090`
- `0x14004057c`
- `0x1400406b0`

## callees

- `0x14002fdc0`
- `0x14002fea8`
- `0x14003bf18`
- `0x14003e14c`
- `0x140045eea`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e1a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e1a3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003e1b9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003e1b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e18b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e18b`

## string_xrefs

- `0x14003e179`: `ntdll.dll`
- `0x14003e1da`: `Failed to get system root directory [%x]`
- `0x14003e1eb`: `AslPathToSystemPathBuf`
- `0x14003e223`: `AslPathToSystemPathBuf`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(void *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  __int64 (*ProcAddress)(void); // rax
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax

  memset_0(a1, 0, 2 * a2);
  v6 = (__int64)qword_140064238;
  if ( !qword_140064238 )
  {
    v6 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v8 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v6 = ProcAddress();
      FreeLibrary(v8);
    }
    qword_140064238 = (wchar_t *)v6;
  }
  v10 = RtlStringCchCopyW(a1, a2, v6);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = RtlStringCchCatW(a1, a2, a3);
    v11 = v12;
    if ( v12 < 0 )
    {
      AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1488, "Failed to cat string [%x]", v12);
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1477, "Failed to get system root directory [%x]", v10);
  }
  return v11;
}

```

## disassembly

```asm
0x14003e14c  push    rbx
0x14003e14e  push    rbp
0x14003e14f  push    rsi
0x14003e150  push    rdi
0x14003e151  push    r14
0x14003e153  sub     rsp, 30h
0x14003e157  mov     r14, r8
0x14003e15a  mov     rsi, rdx
0x14003e15d  lea     r8, [rdx+rdx]; Size
0x14003e161  mov     rbp, rcx
0x14003e164  xor     edx, edx; Val
0x14003e166  call    memset_0
0x14003e16b  mov     rbx, cs:qword_140064238
0x14003e172  test    rbx, rbx
0x14003e175  jnz     short loc_14003E1C6
0x14003e177  xor     edx, edx; hFile
0x14003e179  lea     rcx, LibFileName; "ntdll.dll"
0x14003e180  mov     r8d, 800h; dwFlags
0x14003e186  mov     ebx, 7FFE0030h
0x14003e18b  call    cs:__imp_LoadLibraryExW
0x14003e191  mov     rdi, rax
0x14003e194  test    rax, rax
0x14003e197  jz      short loc_14003E1BF
0x14003e199  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x14003e1a0  mov     rcx, rax; hModule
0x14003e1a3  call    cs:__imp_GetProcAddress
0x14003e1a9  test    rax, rax
0x14003e1ac  jz      short loc_14003E1B6
0x14003e1ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e1b3  mov     rbx, rax
0x14003e1b6  mov     rcx, rdi; hLibModule
0x14003e1b9  call    cs:__imp_FreeLibrary
0x14003e1bf  mov     cs:qword_140064238, rbx
0x14003e1c6  mov     r8, rbx
0x14003e1c9  mov     rdx, rsi
0x14003e1cc  mov     rcx, rbp
0x14003e1cf  call    RtlStringCchCopyW
0x14003e1d4  mov     ebx, eax
0x14003e1d6  test    eax, eax
0x14003e1d8  jns     short loc_14003E1FE
0x14003e1da  lea     r9, aFailedToGetSys; "Failed to get system root directory [%x"...
0x14003e1e1  mov     [rsp+58h+var_38], eax
0x14003e1e5  mov     r8d, 5C5h
0x14003e1eb  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x14003e1f2  mov     ecx, 1
0x14003e1f7  call    AslLogCallPrintf
0x14003e1fc  jmp     short loc_14003E239
0x14003e1fe  mov     r8, r14
0x14003e201  mov     rdx, rsi
0x14003e204  mov     rcx, rbp
0x14003e207  call    RtlStringCchCatW
0x14003e20c  mov     ebx, eax
0x14003e20e  test    eax, eax
0x14003e210  jns     short loc_14003E239
0x14003e212  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x14003e219  mov     [rsp+58h+var_38], eax
0x14003e21d  mov     r8d, 5D0h
0x14003e223  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x14003e22a  mov     ecx, 1
0x14003e22f  call    AslLogCallPrintf
0x14003e234  mov     ebx, 0C000000Dh
0x14003e239  mov     eax, ebx
0x14003e23b  add     rsp, 30h
0x14003e23f  pop     r14
0x14003e241  pop     rdi
0x14003e242  pop     rsi
0x14003e243  pop     rbp
0x14003e244  pop     rbx
0x14003e245  retn
```
