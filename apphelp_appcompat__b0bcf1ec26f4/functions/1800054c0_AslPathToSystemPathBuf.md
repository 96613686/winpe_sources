# AslPathToSystemPathBuf

- ea: `0x1800054c0`
- end: `0x1800055cb`
- name: `AslPathToSystemPathBuf`
- size: `267`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180004b30`
- `0x180004c1c`
- `0x18003c73c`
- `0x18003c870`

## callees

- `0x1800054c0`
- `0x1800055e0`
- `0x180005660`
- `0x18000f114`
- `0x180059235`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005538`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005538`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005566`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005566`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005550`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005550`

## string_xrefs

- `0x180005578`: `Failed to get system root directory [%x]`
- `0x180005589`: `AslPathToSystemPathBuf`
- `0x1800055b0`: `AslPathToSystemPathBuf`
- `0x180005526`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(void *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  HMODULE Library; // rax
  HMODULE v12; // rdi
  __int64 (*ProcAddress)(void); // rax

  memset_0(a1, 0, 2 * a2);
  v6 = (__int64)String1;
  if ( !String1 )
  {
    v6 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v12 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v6 = ProcAddress();
      FreeLibrary(v12);
    }
    String1 = (wchar_t *)v6;
  }
  v7 = RtlStringCchCopyW(a1, a2, v6);
  v8 = v7;
  if ( v7 < 0 )
  {
    AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1477, "Failed to get system root directory [%x]", v7);
  }
  else
  {
    v9 = RtlStringCchCatW(a1, a2, a3);
    v8 = v9;
    if ( v9 < 0 )
    {
      AslLogCallPrintf(1, "AslPathToSystemPathBuf", 1488, "Failed to cat string [%x]", v9);
      return (unsigned int)-1073741811;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800054c0  push    rbx
0x1800054c2  push    rbp
0x1800054c3  push    rsi
0x1800054c4  push    rdi
0x1800054c5  push    r14
0x1800054c7  sub     rsp, 30h
0x1800054cb  mov     r14, r8
0x1800054ce  mov     rsi, rdx
0x1800054d1  lea     r8, [rdx+rdx]; Size
0x1800054d5  mov     rbp, rcx
0x1800054d8  xor     edx, edx; Val
0x1800054da  call    memset_0
0x1800054df  mov     rbx, cs:String1
0x1800054e6  test    rbx, rbx
0x1800054e9  jz      short loc_180005524
0x1800054eb  mov     r8, rbx
0x1800054ee  mov     rdx, rsi
0x1800054f1  mov     rcx, rbp
0x1800054f4  call    RtlStringCchCopyW
0x1800054f9  mov     ebx, eax
0x1800054fb  test    eax, eax
0x1800054fd  js      short loc_180005578
0x1800054ff  mov     r8, r14
0x180005502  mov     rdx, rsi
0x180005505  mov     rcx, rbp
0x180005508  call    RtlStringCchCatW
0x18000550d  mov     ebx, eax
0x18000550f  test    eax, eax
0x180005511  js      loc_18000559F
0x180005517  mov     eax, ebx
0x180005519  add     rsp, 30h
0x18000551d  pop     r14
0x18000551f  pop     rdi
0x180005520  pop     rsi
0x180005521  pop     rbp
0x180005522  pop     rbx
0x180005523  retn
0x180005524  xor     edx, edx; hFile
0x180005526  lea     rcx, LibFileName; "ntdll.dll"
0x18000552d  mov     r8d, 800h; dwFlags
0x180005533  mov     ebx, 7FFE0030h
0x180005538  call    cs:__imp_LoadLibraryExW
0x18000553e  mov     rdi, rax
0x180005541  test    rax, rax
0x180005544  jz      short loc_18000556C
0x180005546  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18000554d  mov     rcx, rax; hModule
0x180005550  call    cs:__imp_GetProcAddress
0x180005556  test    rax, rax
0x180005559  jz      short loc_180005563
0x18000555b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005560  mov     rbx, rax
0x180005563  mov     rcx, rdi; hLibModule
0x180005566  call    cs:__imp_FreeLibrary
0x18000556c  mov     cs:String1, rbx
0x180005573  jmp     loc_1800054EB
0x180005578  lea     r9, aFailedToGetSys; "Failed to get system root directory [%x"...
0x18000557f  mov     [rsp+58h+var_38], eax
0x180005583  mov     r8d, 5C5h
0x180005589  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x180005590  mov     ecx, 1
0x180005595  call    AslLogCallPrintf
0x18000559a  jmp     loc_180005517
0x18000559f  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x1800055a6  mov     [rsp+58h+var_38], eax
0x1800055aa  mov     r8d, 5D0h
0x1800055b0  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x1800055b7  mov     ecx, 1
0x1800055bc  call    AslLogCallPrintf
0x1800055c1  mov     ebx, 0C000000Dh
0x1800055c6  jmp     loc_180005517
```
