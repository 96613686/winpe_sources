# CTxtRange::GetText(ushort * *)

- ea: `0x1800b5de0`
- end: `0x1800b602c`
- name: `?GetText@CTxtRange@@UEAAJPEAPEAG@Z`
- size: `588`
- prototype: `__int64 __fastcall(CTxtRange *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting`

## callees

- `0x180021150`
- `0x180021928`
- `0x180021a20`
- `0x180021c38`
- `0x18002ab44`
- `0x18002abb0`
- `0x1800b5de0`
- `0x1800b6034`
- `0x1800df014`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5fa1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5fa1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b5f85`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b5f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b5f0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800b5f0e`

## string_xrefs

- `0x1800b5f78`: `oleaut32.dll`

## pseudocode

```c
__int64 __fastcall CTxtRange::GetText(CTxtRange *this, unsigned __int16 **a2)
{
  __int64 v2; // rax
  int v5; // edi
  __int64 v6; // rcx
  __int64 (__fastcall *v7)(_QWORD, _QWORD); // rax
  unsigned int v8; // r14d
  int v9; // r15d
  unsigned __int16 *v10; // rdi
  __m128i v11; // xmm1
  __int64 v12; // rdx
  __int64 v13; // rcx
  WCHAR *v14; // rdi
  UINT32 v15; // eax
  __int64 result; // rax
  HMODULE Library; // rax
  CTxtEdit *v18; // rcx
  __int128 v19; // [rsp+30h] [rbp-20h] BYREF
  __int64 v20; // [rsp+40h] [rbp-10h]
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  PCNZWCH sourceString; // [rsp+90h] [rbp+40h] BYREF

  v2 = *((_QWORD *)this + 3);
  if ( !v2 || !*(_QWORD *)(v2 + 40) )
    return 2147746303LL;
  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v5 = *((_DWORD *)this + 26);
  if ( !v5 )
    return 0;
  v6 = *((_QWORD *)this + 3);
  if ( v6 )
    v6 = *(_QWORD *)(v6 + 40);
  if ( (*(_BYTE *)(v6 + 176) & 0x10) != 0 && (*(_DWORD *)(v6 + 280) & 0x800) == 0 )
    return 2147500037LL;
  if ( (unsigned int)CTxtEdit::IsPlaceHolderStorySelected((CTxtEdit *)v6) )
    return 0;
  v7 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1802DD6E8;
  v8 = -v5;
  if ( v5 > 0 )
    v8 = v5;
  v9 = *((_DWORD *)this + 10) - v5;
  if ( v5 < 0 )
    v9 = *((_DWORD *)this + 10);
  if ( !qword_1802DD6E8 )
  {
    CWriteLock::CWriteLock(&string, 0);
    if ( !qword_1802DD6E8 )
    {
      Library = hModule;
      if ( hModule || (Library = LoadLibraryExW(L"oleaut32.dll", 0, 0x800u), (hModule = Library) != 0) )
        qword_1802DD6E8 = (__int64)GetProcAddress(Library, "SysAllocStringLen");
    }
    CWriteLock::~CWriteLock((CWriteLock *)&string);
    v7 = (__int64 (__fastcall *)(_QWORD, _QWORD))qword_1802DD6E8;
    if ( !qword_1802DD6E8 )
    {
      sourceString = 0;
      return 2147942414LL;
    }
  }
  sourceString = (PCNZWCH)v7(0, v8);
  v10 = (unsigned __int16 *)sourceString;
  if ( !sourceString )
    return 2147942414LL;
  v11 = (__m128i)*((unsigned __int64 *)this + 5);
  v19 = *(_OWORD *)((char *)this + 24);
  v20 = v11.m128i_i64[0];
  CTxtPtr::Move((CTxtPtr *)&v19, v9 - _mm_cvtsi128_si32(v11));
  CTxtPtr::GetText((CTxtPtr *)&v19, v8, v10);
  v12 = *((_QWORD *)this + 3);
  if ( v12 )
    v13 = *(_QWORD *)(v12 + 40);
  else
    v13 = 0;
  if ( !*(_QWORD *)(v13 + 576)
    || ((string = 0, !v12) ? (v18 = 0) : (v18 = *(CTxtEdit **)(v12 + 40)),
        result = CTxtEdit::HostFilter(v18, 0x56Du, 0, (__int64)&sourceString, (__int64 *)&string),
        (int)result >= 0) )
  {
    v14 = (WCHAR *)sourceString;
    if ( (*((_DWORD *)this + 29) & 0x100000) != 0 )
    {
      string = 0;
      v15 = CW32System::SysStringLen((unsigned __int16 *)sourceString);
      WindowsCreateString(v14, v15, &string);
      *a2 = (unsigned __int16 *)string;
      CW32System::SysFreeString(v14);
    }
    else
    {
      *a2 = (unsigned __int16 *)sourceString;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800b5de0  mov     [rsp-28h+arg_8], rbx
0x1800b5de5  push    rbp
0x1800b5de6  push    rsi
0x1800b5de7  push    rdi
0x1800b5de8  push    r14
0x1800b5dea  push    r15
0x1800b5dec  mov     rbp, rsp
0x1800b5def  sub     rsp, 50h
0x1800b5df3  mov     rax, [rcx+18h]
0x1800b5df7  mov     rsi, rdx
0x1800b5dfa  mov     rbx, rcx
0x1800b5dfd  test    rax, rax
0x1800b5e00  jz      loc_1800B5FD5
0x1800b5e06  cmp     qword ptr [rax+28h], 0
0x1800b5e0b  jz      loc_1800B5FD5
0x1800b5e11  test    rdx, rdx
0x1800b5e14  jz      loc_1800B6022
0x1800b5e1a  mov     qword ptr [rdx], 0
0x1800b5e21  mov     edi, [rcx+68h]
0x1800b5e24  test    edi, edi
0x1800b5e26  jz      loc_1800B5F23
0x1800b5e2c  mov     rcx, [rcx+18h]
0x1800b5e30  test    rcx, rcx
0x1800b5e33  jz      short loc_1800B5E39
0x1800b5e35  mov     rcx, [rcx+28h]; this
0x1800b5e39  test    byte ptr [rcx+0B0h], 10h
0x1800b5e40  jnz     loc_1800B5F3E
0x1800b5e46  call    ?IsPlaceHolderStorySelected@CTxtEdit@@QEAAHXZ; CTxtEdit::IsPlaceHolderStorySelected(void)
0x1800b5e4b  test    eax, eax
0x1800b5e4d  jnz     loc_1800B5F23
0x1800b5e53  mov     r15d, [rbx+28h]
0x1800b5e57  mov     r14d, edi
0x1800b5e5a  mov     rax, cs:qword_1802DD6E8
0x1800b5e61  neg     r14d
0x1800b5e64  cmovs   r14d, edi
0x1800b5e68  sub     r15d, edi
0x1800b5e6b  test    edi, edi
0x1800b5e6d  cmovs   r15d, [rbx+28h]
0x1800b5e72  test    rax, rax
0x1800b5e75  jz      loc_1800B5F55
0x1800b5e7b  mov     edx, r14d
0x1800b5e7e  xor     ecx, ecx
0x1800b5e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5e85  mov     [rbp+sourceString], rax
0x1800b5e89  mov     rdi, rax
0x1800b5e8c  test    rax, rax
0x1800b5e8f  jz      loc_1800B5FCB
0x1800b5e95  movsd   xmm1, qword ptr [rbx+28h]
0x1800b5e9a  lea     rcx, [rbp+var_20]; this
0x1800b5e9e  movups  xmm0, xmmword ptr [rbx+18h]
0x1800b5ea2  movd    eax, xmm1
0x1800b5ea6  movups  [rbp+var_20], xmm0
0x1800b5eaa  sub     r15d, eax
0x1800b5ead  movsd   [rbp+var_10], xmm1
0x1800b5eb2  mov     edx, r15d; int
0x1800b5eb5  call    ?Move@CTxtPtr@@QEAAJJ@Z; CTxtPtr::Move(long)
0x1800b5eba  mov     r8, rdi; unsigned __int16 *
0x1800b5ebd  lea     rcx, [rbp+var_20]; this
0x1800b5ec1  mov     edx, r14d; int
0x1800b5ec4  call    ?GetText@CTxtPtr@@QEBAJJPEAG@Z; CTxtPtr::GetText(long,ushort *)
0x1800b5ec9  mov     rdx, [rbx+18h]
0x1800b5ecd  test    rdx, rdx
0x1800b5ed0  jz      loc_1800B5FDF
0x1800b5ed6  mov     rcx, [rdx+28h]
0x1800b5eda  cmp     qword ptr [rcx+240h], 0
0x1800b5ee2  jnz     loc_1800B5FE6
0x1800b5ee8  test    dword ptr [rbx+74h], 100000h
0x1800b5eef  mov     rdi, [rbp+sourceString]
0x1800b5ef3  jz      short loc_1800B5F39
0x1800b5ef5  mov     rcx, rdi; unsigned __int16 *
0x1800b5ef8  mov     [rbp+string], 0
0x1800b5f00  call    ?SysStringLen@CW32System@@SAIPEAG@Z; CW32System::SysStringLen(ushort *)
0x1800b5f05  mov     edx, eax; length
0x1800b5f07  lea     r8, [rbp+string]; string
0x1800b5f0b  mov     rcx, rdi; sourceString
0x1800b5f0e  call    cs:__imp_WindowsCreateString
0x1800b5f14  mov     rax, [rbp+string]
0x1800b5f18  mov     rcx, rdi; unsigned __int16 *
0x1800b5f1b  mov     [rsi], rax
0x1800b5f1e  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800b5f23  xor     eax, eax
0x1800b5f25  mov     rbx, [rsp+50h+arg_8]
0x1800b5f2d  add     rsp, 50h
0x1800b5f31  pop     r15
0x1800b5f33  pop     r14
0x1800b5f35  pop     rdi
0x1800b5f36  pop     rsi
0x1800b5f37  pop     rbp
0x1800b5f38  retn
0x1800b5f39  mov     [rsi], rdi
0x1800b5f3c  jmp     short loc_1800B5F23
0x1800b5f3e  test    dword ptr [rcx+118h], 800h
0x1800b5f48  jnz     loc_1800B5E46
0x1800b5f4e  mov     eax, 80004005h
0x1800b5f53  jmp     short loc_1800B5F25
0x1800b5f55  xor     edx, edx
0x1800b5f57  lea     rcx, [rbp+string]
0x1800b5f5b  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x1800b5f60  cmp     cs:qword_1802DD6E8, 0
0x1800b5f68  jnz     short loc_1800B5FAE
0x1800b5f6a  mov     rax, cs:hModule
0x1800b5f71  test    rax, rax
0x1800b5f74  jnz     short loc_1800B5F97
0x1800b5f76  xor     edx, edx; hFile
0x1800b5f78  lea     rcx, LibFileName; "oleaut32.dll"
0x1800b5f7f  mov     r8d, 800h; dwFlags
0x1800b5f85  call    cs:__imp_LoadLibraryExW
0x1800b5f8b  mov     cs:hModule, rax
0x1800b5f92  test    rax, rax
0x1800b5f95  jz      short loc_1800B5FAE
0x1800b5f97  lea     rdx, aSysallocstring_0; "SysAllocStringLen"
0x1800b5f9e  mov     rcx, rax; hModule
0x1800b5fa1  call    cs:__imp_GetProcAddress
0x1800b5fa7  mov     cs:qword_1802DD6E8, rax
0x1800b5fae  lea     rcx, [rbp+string]; this
0x1800b5fb2  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x1800b5fb7  mov     rax, cs:qword_1802DD6E8
0x1800b5fbe  test    rax, rax
0x1800b5fc1  jnz     loc_1800B5E7B
0x1800b5fc7  mov     [rbp+sourceString], rax
0x1800b5fcb  mov     eax, 8007000Eh
0x1800b5fd0  jmp     loc_1800B5F25
0x1800b5fd5  mov     eax, 800401FFh
0x1800b5fda  jmp     loc_1800B5F25
0x1800b5fdf  xor     ecx, ecx
0x1800b5fe1  jmp     loc_1800B5EDA
0x1800b5fe6  mov     [rbp+string], 0
0x1800b5fee  test    rdx, rdx
0x1800b5ff1  jz      short loc_1800B601E
0x1800b5ff3  mov     rcx, [rdx+28h]; this
0x1800b5ff7  lea     rax, [rbp+string]
0x1800b5ffb  xor     r8d, r8d; unsigned __int64
0x1800b5ffe  lea     r9, [rbp+sourceString]; __int64
0x1800b6002  mov     [rsp+50h+var_30], rax; __int64 *
0x1800b6007  mov     edx, 56Dh; unsigned int
0x1800b600c  call    ?HostFilter@CTxtEdit@@QEAAJI_K_JPEA_J@Z; CTxtEdit::HostFilter(uint,unsigned __int64,__int64,__int64 *)
0x1800b6011  test    eax, eax
0x1800b6013  js      loc_1800B5F25
0x1800b6019  jmp     loc_1800B5EE8
0x1800b601e  xor     ecx, ecx
0x1800b6020  jmp     short loc_1800B5FF7
0x1800b6022  mov     eax, 80070057h
0x1800b6027  jmp     loc_1800B5F25
```
