# AslPathToSystemPathBuf

- ea: `0x18006bed8`
- end: `0x18006bfd2`
- name: `AslPathToSystemPathBuf`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18006ac74`
- `0x18006ada8`
- `0x18006be1c`
- `0x18011c8f0`

## callees

- `0x1800197d4`
- `0x18002256c`
- `0x1800250cc`
- `0x18005a8bc`
- `0x18006bed8`
- `0x180130010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18006bf17`
- `KERNEL32!LoadLibraryExW` at `0x18006bf17`
- `KERNEL32!FreeLibrary` at `0x18006bf45`
- `KERNEL32!FreeLibrary` at `0x18006bf45`
- `KERNEL32!GetProcAddress` at `0x18006bf2f`
- `KERNEL32!GetProcAddress` at `0x18006bf2f`

## string_xrefs

- `0x18006bf05`: `ntdll.dll`
- `0x18006bf66`: `Failed to get system root directory [%x]`
- `0x18006bf77`: `AslPathToSystemPathBuf`
- `0x18006bfaf`: `AslPathToSystemPathBuf`

## pseudocode

```c
__int64 __fastcall AslPathToSystemPathBuf(_WORD *a1, __int64 a2, _WORD *a3)
{
  __int64 v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // rdi
  __int64 (*ProcAddress)(void); // rax
  int v10; // ebx

  memset_0(a1, 0, 2 * a2);
  v6 = (__int64)qword_180183C08;
  if ( !qword_180183C08 )
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
    qword_180183C08 = (wchar_t *)v6;
  }
  v10 = RtlStringCchCopyW(a1, a2, v6);
  if ( v10 >= 0 )
  {
    v10 = RtlStringCchCatW(a1, a2, a3);
    if ( v10 < 0 )
    {
      AslLogCallPrintf(1, (unsigned int)"AslPathToSystemPathBuf", 1488, (unsigned int)"Failed to cat string [%x]");
      return (unsigned int)-1073741811;
    }
  }
  else
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"AslPathToSystemPathBuf",
      1477,
      (unsigned int)"Failed to get system root directory [%x]");
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18006bed8  push    rbx
0x18006beda  push    rbp
0x18006bedb  push    rsi
0x18006bedc  push    rdi
0x18006bedd  push    r14
0x18006bedf  sub     rsp, 30h
0x18006bee3  mov     r14, r8
0x18006bee6  mov     rsi, rdx
0x18006bee9  lea     r8, [rdx+rdx]; Size
0x18006beed  mov     rbp, rcx
0x18006bef0  xor     edx, edx; Val
0x18006bef2  call    memset_0
0x18006bef7  mov     rbx, cs:qword_180183C08
0x18006befe  test    rbx, rbx
0x18006bf01  jnz     short loc_18006BF52
0x18006bf03  xor     edx, edx; hFile
0x18006bf05  lea     rcx, LibFileName; "ntdll.dll"
0x18006bf0c  mov     r8d, 800h; dwFlags
0x18006bf12  mov     ebx, 7FFE0030h
0x18006bf17  call    cs:__imp_LoadLibraryExW
0x18006bf1d  mov     rdi, rax
0x18006bf20  test    rax, rax
0x18006bf23  jz      short loc_18006BF4B
0x18006bf25  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18006bf2c  mov     rcx, rax; hModule
0x18006bf2f  call    cs:__imp_GetProcAddress
0x18006bf35  test    rax, rax
0x18006bf38  jz      short loc_18006BF42
0x18006bf3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006bf3f  mov     rbx, rax
0x18006bf42  mov     rcx, rdi; hLibModule
0x18006bf45  call    cs:__imp_FreeLibrary
0x18006bf4b  mov     cs:qword_180183C08, rbx
0x18006bf52  mov     r8, rbx
0x18006bf55  mov     rdx, rsi
0x18006bf58  mov     rcx, rbp
0x18006bf5b  call    RtlStringCchCopyW
0x18006bf60  mov     ebx, eax
0x18006bf62  test    eax, eax
0x18006bf64  jns     short loc_18006BF8A
0x18006bf66  lea     r9, aFailedToGetSys; "Failed to get system root directory [%x"...
0x18006bf6d  mov     [rsp+58h+var_38], eax
0x18006bf71  mov     r8d, 5C5h
0x18006bf77  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x18006bf7e  mov     ecx, 1
0x18006bf83  call    AslLogCallPrintf
0x18006bf88  jmp     short loc_18006BFC5
0x18006bf8a  mov     r8, r14
0x18006bf8d  mov     rdx, rsi
0x18006bf90  mov     rcx, rbp
0x18006bf93  call    RtlStringCchCatW
0x18006bf98  mov     ebx, eax
0x18006bf9a  test    eax, eax
0x18006bf9c  jns     short loc_18006BFC5
0x18006bf9e  lea     r9, aFailedToCatStr; "Failed to cat string [%x]"
0x18006bfa5  mov     [rsp+58h+var_38], eax
0x18006bfa9  mov     r8d, 5D0h
0x18006bfaf  lea     rdx, aAslpathtosyste_0; "AslPathToSystemPathBuf"
0x18006bfb6  mov     ecx, 1
0x18006bfbb  call    AslLogCallPrintf
0x18006bfc0  mov     ebx, 0C000000Dh
0x18006bfc5  mov     eax, ebx
0x18006bfc7  add     rsp, 30h
0x18006bfcb  pop     r14
0x18006bfcd  pop     rdi
0x18006bfce  pop     rsi
0x18006bfcf  pop     rbp
0x18006bfd0  pop     rbx
0x18006bfd1  retn
```
