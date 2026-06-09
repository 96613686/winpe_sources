# Base::Path::MakeAbsolute(void)

- ea: `0x18002e608`
- end: `0x18002e6b4`
- name: `?MakeAbsolute@Path@Base@@QEAAAEAV12@XZ`
- size: `172`
- prototype: `struct Path *__fastcall(Base::Path *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002e524`

## callees

- `0x1800041a4`
- `0x180004908`
- `0x180025f90`
- `0x18002e608`
- `0x18002ec48`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x18002e671`
- `KERNEL32!GetFullPathNameW` at `0x18002e671`
- `SHLWAPI!PathIsRelativeW` at `0x18002e614`
- `SHLWAPI!PathIsRelativeW` at `0x18002e614`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e68e`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e68e`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002e67b`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002e67b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct Path *__fastcall Base::Path::MakeAbsolute(Base::Path *this)
{
  __int64 v2; // r8
  DWORD FullPathNameW; // eax
  int v4; // edx
  Base *v5; // rcx
  LPCWSTR lpFileName; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR FilePart; // [rsp+38h] [rbp+10h] BYREF

  if ( PathIsRelativeW(*(LPCWSTR *)this) )
  {
    Base::String::String((Base::String *)&lpFileName, this);
    FilePart = 0;
    if ( ((*(_DWORD *)(*(_QWORD *)this - 12LL) - 260) | (1 - *(_DWORD *)(*(_QWORD *)this - 8LL))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(this, 260, v2);
    FullPathNameW = GetFullPathNameW(lpFileName, 0x105u, *(LPWSTR *)this, &FilePart);
    if ( !FullPathNameW )
    {
      Base::ThrowLastError(v5);
      __debugbreak();
    }
    if ( FullPathNameW > 0x104 )
    {
      Base::Throw((Base *)0x800700CELL, v4);
      __debugbreak();
    }
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(this, 0xFFFFFFFFLL);
    Base::String::~String((Base::String *)&lpFileName);
  }
  return this;
}

```

## disassembly

```asm
0x18002e608  push    rbx
0x18002e60a  sub     rsp, 20h
0x18002e60e  mov     rbx, rcx
0x18002e611  mov     rcx, [rcx]; pszPath
0x18002e614  call    cs:__imp_PathIsRelativeW
0x18002e61a  nop
0x18002e61b  test    eax, eax
0x18002e61d  jz      loc_18002E6AB
0x18002e623  mov     rdx, rbx; struct Base::String *
0x18002e626  lea     rcx, [rsp+28h+lpFileName]; this
0x18002e62b  call    ??0String@Base@@QEAA@AEBV01@@Z; Base::String::String(Base::String const &)
0x18002e630  nop
0x18002e631  mov     [rsp+28h+FilePart], 0
0x18002e63a  mov     rax, [rbx]
0x18002e63d  mov     edx, 1
0x18002e642  sub     edx, [rax-8]
0x18002e645  mov     ecx, [rax-0Ch]
0x18002e648  sub     ecx, 104h
0x18002e64e  or      edx, ecx
0x18002e650  jge     short loc_18002E65F
0x18002e652  mov     edx, 104h
0x18002e657  mov     rcx, rbx
0x18002e65a  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e65f  lea     r9, [rsp+28h+FilePart]; lpFilePart
0x18002e664  mov     r8, [rbx]; lpBuffer
0x18002e667  mov     edx, 105h; nBufferLength
0x18002e66c  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18002e671  call    cs:__imp_GetFullPathNameW
0x18002e677  test    eax, eax
0x18002e679  jnz     short loc_18002E682
0x18002e67b  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002e681  int     3; Trap to Debugger
0x18002e682  cmp     eax, 104h
0x18002e687  jbe     short loc_18002E695
0x18002e689  mov     ecx, 800700CEh
0x18002e68e  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e694  int     3; Trap to Debugger
0x18002e695  or      edx, 0FFFFFFFFh
0x18002e698  mov     rcx, rbx
0x18002e69b  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e6a0  nop
0x18002e6a1  lea     rcx, [rsp+28h+lpFileName]; this
0x18002e6a6  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e6ab  mov     rax, rbx
0x18002e6ae  add     rsp, 20h
0x18002e6b2  pop     rbx
0x18002e6b3  retn
```
