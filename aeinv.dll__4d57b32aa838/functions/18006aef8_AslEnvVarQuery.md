# AslEnvVarQuery

- ea: `0x18006aef8`
- end: `0x18006b120`
- name: `AslEnvVarQuery`
- size: `552`
- prototype: `__int64 __fastcall(WCHAR *, const wchar_t *, unsigned __int64, _WORD *, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f780`
- `0x18011c1d4`

## callees

- `0x18005a7d8`
- `0x18006aef8`
- `0x180125490`
- `0x180130010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18006b035`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18006b041`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18006b035`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18006b041`
- `KERNEL32!LoadLibraryExW` at `0x18006af5c`
- `KERNEL32!LoadLibraryExW` at `0x18006af5c`
- `KERNEL32!FreeLibrary` at `0x18006af8a`
- `KERNEL32!FreeLibrary` at `0x18006af8a`
- `KERNEL32!GetProcAddress` at `0x18006af74`
- `KERNEL32!GetProcAddress` at `0x18006af74`

## string_xrefs

- `0x18006af4a`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AslEnvVarQuery(
        WCHAR *a1,
        const wchar_t *a2,
        unsigned __int64 a3,
        _WORD *a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  __int64 v10; // rdi
  HMODULE Library; // rax
  HMODULE v12; // rbx
  __int64 (*ProcAddress)(void); // rax
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  const void *v17; // rdx
  size_t v18; // rbx
  WCHAR *v19; // rbp
  WCHAR *v20; // r13
  WCHAR *v21; // r15
  WCHAR v22; // bx
  WCHAR v23; // di
  int v24; // edx
  WCHAR v25; // ax
  WCHAR *v26; // rcx
  unsigned __int64 v27; // rsi

  if ( a3 < 0xA || wcsnicmp(a2, L"systemroot", 0xAu) )
  {
    if ( !a1 )
      return 3221225728LL;
    v19 = (WCHAR *)&a2[a3];
    while ( 1 )
    {
      if ( !*a1 )
        return 3221225728LL;
      v20 = a1;
      v21 = (WCHAR *)a2;
      if ( a2 >= v19 )
      {
LABEL_26:
        if ( v21 == v19 && *a1 == 61 )
        {
          v24 = 1;
          goto LABEL_35;
        }
      }
      else
      {
        while ( *a1 )
        {
          v22 = *a1;
          v23 = RtlUpcaseUnicodeChar(*v21);
          if ( RtlUpcaseUnicodeChar(v22) == v23 )
          {
            ++a1;
            if ( ++v21 < v19 )
              continue;
          }
          goto LABEL_26;
        }
      }
      v25 = *a1;
      if ( !*a1 )
        goto LABEL_39;
      do
      {
        if ( v25 == 61 && a1 != v20 )
          break;
        v25 = *++a1;
      }
      while ( *a1 );
      if ( !*a1 )
        goto LABEL_39;
      v24 = 0;
LABEL_35:
      v26 = a1;
      do
      {
        if ( (__int64)(((char *)a1 - (char *)v26) & 0xFFFFFFFFFFFFFFFEuLL) >= 65534 )
          break;
        ++a1;
      }
      while ( *a1 );
      if ( v24 )
      {
        v17 = v26 + 1;
        v27 = a1 - (v26 + 1);
        if ( v27 < a5 )
        {
          v18 = v27;
          *a6 = v27;
          goto LABEL_18;
        }
        if ( a4 && a5 )
          *a4 = 0;
        v15 = v27 + 1;
        goto LABEL_16;
      }
LABEL_39:
      ++a1;
    }
  }
  v10 = (__int64)qword_180183C08;
  if ( !qword_180183C08 )
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
    qword_180183C08 = (wchar_t *)v10;
  }
  v14 = -1;
  do
    ++v14;
  while ( *(_WORD *)(v10 + 2 * v14) );
  if ( v14 < a5 )
  {
    v17 = (const void *)v10;
    *a6 = v14;
    v18 = v14;
LABEL_18:
    memcpy_0(a4, v17, v18 * 2);
    a4[v18] = 0;
    return 0;
  }
  else
  {
    if ( a4 )
    {
      if ( a5 )
        *a4 = 0;
    }
    v15 = v14 + 1;
LABEL_16:
    *a6 = v15;
    return 3221225507LL;
  }
}

```

## disassembly

```asm
0x18006aef8  push    rbx
0x18006aefa  push    rbp
0x18006aefb  push    rsi
0x18006aefc  push    rdi
0x18006aefd  push    r12
0x18006aeff  push    r13
0x18006af01  push    r14
0x18006af03  push    r15
0x18006af05  sub     rsp, 28h
0x18006af09  xor     r15d, r15d
0x18006af0c  mov     rbx, r8
0x18006af0f  mov     r14, r9
0x18006af12  mov     r12, rdx
0x18006af15  mov     rsi, rcx
0x18006af18  lea     r8d, [r15+0Ah]; MaxCount
0x18006af1c  cmp     rbx, r8
0x18006af1f  jb      loc_18006B005
0x18006af25  lea     rdx, aSystemroot_1; "systemroot"
0x18006af2c  mov     rcx, r12; String1
0x18006af2f  call    _wcsnicmp
0x18006af34  test    eax, eax
0x18006af36  jnz     loc_18006B005
0x18006af3c  mov     rdi, cs:qword_180183C08
0x18006af43  test    rdi, rdi
0x18006af46  jnz     short loc_18006AF97
0x18006af48  xor     edx, edx; hFile
0x18006af4a  lea     rcx, LibFileName; "ntdll.dll"
0x18006af51  mov     r8d, 800h; dwFlags
0x18006af57  mov     edi, 7FFE0030h
0x18006af5c  call    cs:__imp_LoadLibraryExW
0x18006af62  mov     rbx, rax
0x18006af65  test    rax, rax
0x18006af68  jz      short loc_18006AF90
0x18006af6a  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18006af71  mov     rcx, rax; hModule
0x18006af74  call    cs:__imp_GetProcAddress
0x18006af7a  test    rax, rax
0x18006af7d  jz      short loc_18006AF87
0x18006af7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006af84  mov     rdi, rax
0x18006af87  mov     rcx, rbx; hLibModule
0x18006af8a  call    cs:__imp_FreeLibrary
0x18006af90  mov     cs:qword_180183C08, rdi
0x18006af97  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18006af9b  inc     rbx
0x18006af9e  cmp     [rdi+rbx*2], r15w
0x18006afa3  jnz     short loc_18006AF9B
0x18006afa5  cmp     rbx, [rsp+68h+arg_20]
0x18006afad  jb      short loc_18006AFDC
0x18006afaf  test    r14, r14
0x18006afb2  jz      short loc_18006AFC3
0x18006afb4  cmp     [rsp+68h+arg_20], 1
0x18006afbd  jb      short loc_18006AFC3
0x18006afbf  mov     [r14], r15w
0x18006afc3  lea     rcx, [rbx+1]
0x18006afc7  mov     rax, [rsp+68h+arg_28]
0x18006afcf  mov     [rax], rcx
0x18006afd2  mov     eax, 0C0000023h
0x18006afd7  jmp     loc_18006B10F
0x18006afdc  mov     rax, [rsp+68h+arg_28]
0x18006afe4  mov     rdx, rdi; Src
0x18006afe7  mov     [rax], rbx
0x18006afea  add     rbx, rbx
0x18006afed  mov     r8, rbx; Size
0x18006aff0  mov     rcx, r14; void *
0x18006aff3  call    memcpy_0
0x18006aff8  mov     [rbx+r14], r15w
0x18006affd  mov     eax, r15d
0x18006b000  jmp     loc_18006B10F
0x18006b005  test    rsi, rsi
0x18006b008  jz      loc_18006B10A
0x18006b00e  lea     rbp, [r12+rbx*2]
0x18006b012  cmp     [rsi], r15w
0x18006b016  jz      loc_18006B10A
0x18006b01c  mov     r13, rsi
0x18006b01f  mov     r15, r12
0x18006b022  cmp     r12, rbp
0x18006b025  jnb     short loc_18006B059
0x18006b027  xor     eax, eax
0x18006b029  cmp     [rsi], ax
0x18006b02c  jz      short loc_18006B06E
0x18006b02e  movzx   ecx, word ptr [r15]; Source
0x18006b032  movzx   ebx, word ptr [rsi]
0x18006b035  call    cs:__imp_RtlUpcaseUnicodeChar
0x18006b03b  movzx   ecx, bx; Source
0x18006b03e  movzx   edi, ax
0x18006b041  call    cs:__imp_RtlUpcaseUnicodeChar
0x18006b047  cmp     ax, di
0x18006b04a  jnz     short loc_18006B059
0x18006b04c  add     rsi, 2
0x18006b050  add     r15, 2
0x18006b054  cmp     r15, rbp
0x18006b057  jb      short loc_18006B027
0x18006b059  cmp     r15, rbp
0x18006b05c  jnz     short loc_18006B06E
0x18006b05e  cmp     word ptr [rsi], 3Dh ; '='
0x18006b062  jnz     short loc_18006B06E
0x18006b064  mov     edx, 1
0x18006b069  xor     r15d, r15d
0x18006b06c  jmp     short loc_18006B099
0x18006b06e  movzx   eax, word ptr [rsi]
0x18006b071  xor     r15d, r15d
0x18006b074  test    ax, ax
0x18006b077  jz      short loc_18006B0BC
0x18006b079  cmp     ax, 3Dh ; '='
0x18006b07d  jnz     short loc_18006B084
0x18006b07f  cmp     rsi, r13
0x18006b082  jnz     short loc_18006B090
0x18006b084  add     rsi, 2
0x18006b088  movzx   eax, word ptr [rsi]
0x18006b08b  test    ax, ax
0x18006b08e  jnz     short loc_18006B079
0x18006b090  cmp     [rsi], r15w
0x18006b094  jz      short loc_18006B0BC
0x18006b096  mov     edx, r15d
0x18006b099  mov     rcx, rsi
0x18006b09c  mov     rax, rsi
0x18006b09f  sub     rax, rcx
0x18006b0a2  and     rax, 0FFFFFFFFFFFFFFFEh
0x18006b0a6  cmp     rax, 0FFFEh
0x18006b0ac  jge     short loc_18006B0B8
0x18006b0ae  add     rsi, 2
0x18006b0b2  cmp     [rsi], r15w
0x18006b0b6  jnz     short loc_18006B09C
0x18006b0b8  test    edx, edx
0x18006b0ba  jnz     short loc_18006B0C5
0x18006b0bc  add     rsi, 2
0x18006b0c0  jmp     loc_18006B012
0x18006b0c5  lea     rdx, [rcx+2]
0x18006b0c9  sub     rsi, rdx
0x18006b0cc  sar     rsi, 1
0x18006b0cf  cmp     rsi, [rsp+68h+arg_20]
0x18006b0d7  jb      short loc_18006B0F6
0x18006b0d9  test    r14, r14
0x18006b0dc  jz      short loc_18006B0ED
0x18006b0de  cmp     [rsp+68h+arg_20], 1
0x18006b0e7  jb      short loc_18006B0ED
0x18006b0e9  mov     [r14], r15w
0x18006b0ed  lea     rcx, [rsi+1]
0x18006b0f1  jmp     loc_18006AFC7
0x18006b0f6  mov     rax, [rsp+68h+arg_28]
0x18006b0fe  lea     rbx, [rsi+rsi]
0x18006b102  mov     [rax], rsi
0x18006b105  jmp     loc_18006AFED
0x18006b10a  mov     eax, 0C0000100h
0x18006b10f  add     rsp, 28h
0x18006b113  pop     r15
0x18006b115  pop     r14
0x18006b117  pop     r13
0x18006b119  pop     r12
0x18006b11b  pop     rdi
0x18006b11c  pop     rsi
0x18006b11d  pop     rbp
0x18006b11e  pop     rbx
0x18006b11f  retn
```
