# AslEnvVarQuery

- ea: `0x140040800`
- end: `0x140040a2c`
- name: `AslEnvVarQuery`
- size: `556`
- prototype: `__int64 __fastcall(WCHAR *, const wchar_t *, unsigned __int64, _WORD *, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400353f4`
- `0x1400400c8`

## callees

- `0x140040800`
- `0x140045ed2`
- `0x140047010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x140040837`
- `msvcrt!_wcsnicmp` at `0x140040837`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140040930`
- `ntdll!RtlUpcaseUnicodeChar` at `0x14004093c`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140040930`
- `ntdll!RtlUpcaseUnicodeChar` at `0x14004093c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004087d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14004087d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140040893`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140040893`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140040865`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140040865`

## string_xrefs

- `0x140040853`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall AslEnvVarQuery(
        WCHAR *a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        _WORD *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rsi
  HMODULE Library; // rax
  HMODULE v12; // rbx
  __int64 (*ProcAddress)(void); // rax
  unsigned __int64 v14; // rdi
  __int64 result; // rax
  WCHAR *v16; // rbp
  WCHAR *v17; // r13
  WCHAR *v18; // r15
  WCHAR v19; // bx
  WCHAR v20; // di
  int v21; // edx
  WCHAR v22; // ax
  WCHAR *v23; // rcx
  unsigned __int64 v24; // rsi

  if ( a3 < 0xA || _wcsnicmp(a2, L"systemroot", 0xAu) )
  {
    if ( !a1 )
      return 3221225728LL;
    v16 = (WCHAR *)&a2[a3];
    while ( 1 )
    {
      if ( !*a1 )
        return 3221225728LL;
      v17 = a1;
      v18 = (WCHAR *)a2;
      if ( a2 >= v16 )
      {
LABEL_25:
        if ( v18 == v16 && *a1 == 61 )
        {
          v21 = 1;
          goto LABEL_34;
        }
      }
      else
      {
        while ( *a1 )
        {
          v19 = *a1;
          v20 = RtlUpcaseUnicodeChar(*v18);
          if ( RtlUpcaseUnicodeChar(v19) == v20 )
          {
            ++a1;
            if ( ++v18 < v16 )
              continue;
          }
          goto LABEL_25;
        }
      }
      v22 = *a1;
      if ( !*a1 )
        goto LABEL_38;
      do
      {
        if ( v22 == 61 && a1 != v17 )
          break;
        v22 = *++a1;
      }
      while ( *a1 );
      if ( !*a1 )
        goto LABEL_38;
      v21 = 0;
LABEL_34:
      v23 = a1;
      do
      {
        if ( (__int64)(((char *)a1 - (char *)v23) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
          break;
        ++a1;
      }
      while ( *a1 );
      if ( v21 )
      {
        v24 = a1 - (v23 + 1);
        if ( v24 < a5 )
        {
          memcpy_0(a4, v23 + 1, 2 * v24);
          a4[v24] = 0;
          result = 0;
        }
        else
        {
          if ( a4 && a5 )
            *a4 = 0;
          result = 3221225507LL;
          ++v24;
        }
        *a6 = v24;
        return result;
      }
LABEL_38:
      ++a1;
    }
  }
  v10 = (__int64)qword_140064238;
  if ( !qword_140064238 )
  {
    v10 = 2147352624;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v12 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "RtlGetNtSystemRoot");
      if ( ProcAddress )
        v10 = ProcAddress();
      FreeLibrary(v12);
    }
    qword_140064238 = (wchar_t *)v10;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v10 + 2 * v14) );
  if ( v14 < a5 )
  {
    memcpy_0(a4, (const void *)v10, 2 * v14);
    a4[v14] = 0;
    result = 0;
  }
  else
  {
    if ( a4 )
    {
      if ( a5 )
        *a4 = 0;
    }
    result = 3221225507LL;
    ++v14;
  }
  *a6 = v14;
  return result;
}

```

## disassembly

```asm
0x140040800  push    rbx
0x140040802  push    rbp
0x140040803  push    rsi
0x140040804  push    rdi
0x140040805  push    r12
0x140040807  push    r13
0x140040809  push    r14
0x14004080b  push    r15
0x14004080d  sub     rsp, 28h
0x140040811  xor     r15d, r15d
0x140040814  mov     rbx, r8
0x140040817  mov     r14, r9
0x14004081a  mov     r12, rdx
0x14004081d  mov     rsi, rcx
0x140040820  lea     r8d, [r15+0Ah]; MaxCount
0x140040824  cmp     rbx, r8
0x140040827  jb      loc_140040900
0x14004082d  lea     rdx, aSystemroot_1; "systemroot"
0x140040834  mov     rcx, r12; String1
0x140040837  call    cs:__imp__wcsnicmp
0x14004083d  test    eax, eax
0x14004083f  jnz     loc_140040900
0x140040845  mov     rsi, cs:qword_140064238
0x14004084c  test    rsi, rsi
0x14004084f  jnz     short loc_1400408A0
0x140040851  xor     edx, edx; hFile
0x140040853  lea     rcx, LibFileName; "ntdll.dll"
0x14004085a  mov     r8d, 800h; dwFlags
0x140040860  mov     esi, 7FFE0030h
0x140040865  call    cs:__imp_LoadLibraryExW
0x14004086b  mov     rbx, rax
0x14004086e  test    rax, rax
0x140040871  jz      short loc_140040899
0x140040873  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x14004087a  mov     rcx, rax; hModule
0x14004087d  call    cs:__imp_GetProcAddress
0x140040883  test    rax, rax
0x140040886  jz      short loc_140040890
0x140040888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004088d  mov     rsi, rax
0x140040890  mov     rcx, rbx; hLibModule
0x140040893  call    cs:__imp_FreeLibrary
0x140040899  mov     cs:qword_140064238, rsi
0x1400408a0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400408a4  inc     rdi
0x1400408a7  cmp     [rsi+rdi*2], r15w
0x1400408ac  jnz     short loc_1400408A4
0x1400408ae  cmp     rdi, [rsp+68h+arg_20]
0x1400408b6  jb      short loc_1400408D6
0x1400408b8  test    r14, r14
0x1400408bb  jz      short loc_1400408CC
0x1400408bd  cmp     [rsp+68h+arg_20], 1
0x1400408c6  jb      short loc_1400408CC
0x1400408c8  mov     [r14], r15w
0x1400408cc  mov     eax, 0C0000023h
0x1400408d1  inc     rdi
0x1400408d4  jmp     short loc_1400408F0
0x1400408d6  lea     rbx, [rdi+rdi]
0x1400408da  mov     rdx, rsi; Src
0x1400408dd  mov     r8, rbx; Size
0x1400408e0  mov     rcx, r14; void *
0x1400408e3  call    memcpy_0
0x1400408e8  mov     [rbx+r14], r15w
0x1400408ed  mov     eax, r15d
0x1400408f0  mov     rcx, [rsp+68h+arg_28]
0x1400408f8  mov     [rcx], rdi
0x1400408fb  jmp     loc_140040A1B
0x140040900  test    rsi, rsi
0x140040903  jz      loc_140040A16
0x140040909  lea     rbp, [r12+rbx*2]
0x14004090d  cmp     [rsi], r15w
0x140040911  jz      loc_140040A16
0x140040917  mov     r13, rsi
0x14004091a  mov     r15, r12
0x14004091d  cmp     r12, rbp
0x140040920  jnb     short loc_140040954
0x140040922  xor     eax, eax
0x140040924  cmp     [rsi], ax
0x140040927  jz      short loc_140040969
0x140040929  movzx   ecx, word ptr [r15]; Source
0x14004092d  movzx   ebx, word ptr [rsi]
0x140040930  call    cs:__imp_RtlUpcaseUnicodeChar
0x140040936  movzx   ecx, bx; Source
0x140040939  movzx   edi, ax
0x14004093c  call    cs:__imp_RtlUpcaseUnicodeChar
0x140040942  cmp     ax, di
0x140040945  jnz     short loc_140040954
0x140040947  add     rsi, 2
0x14004094b  add     r15, 2
0x14004094f  cmp     r15, rbp
0x140040952  jb      short loc_140040922
0x140040954  cmp     r15, rbp
0x140040957  jnz     short loc_140040969
0x140040959  cmp     word ptr [rsi], 3Dh ; '='
0x14004095d  jnz     short loc_140040969
0x14004095f  mov     edx, 1
0x140040964  xor     r15d, r15d
0x140040967  jmp     short loc_140040994
0x140040969  movzx   eax, word ptr [rsi]
0x14004096c  xor     r15d, r15d
0x14004096f  test    ax, ax
0x140040972  jz      short loc_1400409B7
0x140040974  cmp     ax, 3Dh ; '='
0x140040978  jnz     short loc_14004097F
0x14004097a  cmp     rsi, r13
0x14004097d  jnz     short loc_14004098B
0x14004097f  add     rsi, 2
0x140040983  movzx   eax, word ptr [rsi]
0x140040986  test    ax, ax
0x140040989  jnz     short loc_140040974
0x14004098b  cmp     [rsi], r15w
0x14004098f  jz      short loc_1400409B7
0x140040991  mov     edx, r15d
0x140040994  mov     rcx, rsi
0x140040997  mov     rax, rsi
0x14004099a  sub     rax, rcx
0x14004099d  and     rax, 0FFFFFFFFFFFFFFFEh
0x1400409a1  cmp     rax, 0FFFEh
0x1400409a7  jge     short loc_1400409B3
0x1400409a9  add     rsi, 2
0x1400409ad  cmp     [rsi], r15w
0x1400409b1  jnz     short loc_140040997
0x1400409b3  test    edx, edx
0x1400409b5  jnz     short loc_1400409C0
0x1400409b7  add     rsi, 2
0x1400409bb  jmp     loc_14004090D
0x1400409c0  mov     rdi, [rsp+68h+arg_28]
0x1400409c8  lea     rdx, [rcx+2]; Src
0x1400409cc  sub     rsi, rdx
0x1400409cf  sar     rsi, 1
0x1400409d2  cmp     rsi, [rsp+68h+arg_20]
0x1400409da  jb      short loc_1400409FA
0x1400409dc  test    r14, r14
0x1400409df  jz      short loc_1400409F0
0x1400409e1  cmp     [rsp+68h+arg_20], 1
0x1400409ea  jb      short loc_1400409F0
0x1400409ec  mov     [r14], r15w
0x1400409f0  mov     eax, 0C0000023h
0x1400409f5  inc     rsi
0x1400409f8  jmp     short loc_140040A11
0x1400409fa  lea     rbx, [rsi+rsi]
0x1400409fe  mov     rcx, r14; void *
0x140040a01  mov     r8, rbx; Size
0x140040a04  call    memcpy_0
0x140040a09  mov     [rbx+r14], r15w
0x140040a0e  mov     eax, r15d
0x140040a11  mov     [rdi], rsi
0x140040a14  jmp     short loc_140040A1B
0x140040a16  mov     eax, 0C0000100h
0x140040a1b  add     rsp, 28h
0x140040a1f  pop     r15
0x140040a21  pop     r14
0x140040a23  pop     r13
0x140040a25  pop     r12
0x140040a27  pop     rdi
0x140040a28  pop     rsi
0x140040a29  pop     rbp
0x140040a2a  pop     rbx
0x140040a2b  retn
```
