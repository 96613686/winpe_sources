# AslEnvVarQuery

- ea: `0x18002fc4c`
- end: `0x18002fe77`
- name: `AslEnvVarQuery`
- size: `555`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18002f798`

## callees

- `0x18000689c`
- `0x180006920`
- `0x18002fc4c`
- `0x1800eb010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002fd7b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002fd87`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002fd7b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002fd87`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fcde`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002fcde`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fcb0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002fcb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fcc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002fcc8`

## string_xrefs

- `0x18002fc9e`: `ntdll.dll`

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

  if ( a3 < 0xA || wcsnicmp(a2, L"systemroot", 0xAu) )
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
  v10 = (__int64)qword_1801228E8;
  if ( !qword_1801228E8 )
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
    qword_1801228E8 = (void *)v10;
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
0x18002fc4c  push    rbx
0x18002fc4e  push    rbp
0x18002fc4f  push    rsi
0x18002fc50  push    rdi
0x18002fc51  push    r12
0x18002fc53  push    r13
0x18002fc55  push    r14
0x18002fc57  push    r15
0x18002fc59  sub     rsp, 28h
0x18002fc5d  xor     r15d, r15d
0x18002fc60  mov     rbx, r8
0x18002fc63  mov     r14, r9
0x18002fc66  mov     r12, rdx
0x18002fc69  mov     rsi, rcx
0x18002fc6c  lea     r8d, [r15+0Ah]; MaxCount
0x18002fc70  cmp     rbx, r8
0x18002fc73  jb      loc_18002FD4B
0x18002fc79  lea     rdx, aSystemroot_1; "systemroot"
0x18002fc80  mov     rcx, r12; String1
0x18002fc83  call    _wcsnicmp
0x18002fc88  test    eax, eax
0x18002fc8a  jnz     loc_18002FD4B
0x18002fc90  mov     rsi, cs:qword_1801228E8
0x18002fc97  test    rsi, rsi
0x18002fc9a  jnz     short loc_18002FCEB
0x18002fc9c  xor     edx, edx; hFile
0x18002fc9e  lea     rcx, LibFileName; "ntdll.dll"
0x18002fca5  mov     r8d, 800h; dwFlags
0x18002fcab  mov     esi, 7FFE0030h
0x18002fcb0  call    cs:__imp_LoadLibraryExW
0x18002fcb6  mov     rbx, rax
0x18002fcb9  test    rax, rax
0x18002fcbc  jz      short loc_18002FCE4
0x18002fcbe  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18002fcc5  mov     rcx, rax; hModule
0x18002fcc8  call    cs:__imp_GetProcAddress
0x18002fcce  test    rax, rax
0x18002fcd1  jz      short loc_18002FCDB
0x18002fcd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcd8  mov     rsi, rax
0x18002fcdb  mov     rcx, rbx; hLibModule
0x18002fcde  call    cs:__imp_FreeLibrary
0x18002fce4  mov     cs:qword_1801228E8, rsi
0x18002fceb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002fcef  inc     rdi
0x18002fcf2  cmp     [rsi+rdi*2], r15w
0x18002fcf7  jnz     short loc_18002FCEF
0x18002fcf9  cmp     rdi, [rsp+68h+arg_20]
0x18002fd01  jb      short loc_18002FD21
0x18002fd03  test    r14, r14
0x18002fd06  jz      short loc_18002FD17
0x18002fd08  cmp     [rsp+68h+arg_20], 1
0x18002fd11  jb      short loc_18002FD17
0x18002fd13  mov     [r14], r15w
0x18002fd17  mov     eax, 0C0000023h
0x18002fd1c  inc     rdi
0x18002fd1f  jmp     short loc_18002FD3B
0x18002fd21  lea     rbx, [rdi+rdi]
0x18002fd25  mov     rdx, rsi; Src
0x18002fd28  mov     r8, rbx; Size
0x18002fd2b  mov     rcx, r14; void *
0x18002fd2e  call    memcpy_0
0x18002fd33  mov     [rbx+r14], r15w
0x18002fd38  mov     eax, r15d
0x18002fd3b  mov     rcx, [rsp+68h+arg_28]
0x18002fd43  mov     [rcx], rdi
0x18002fd46  jmp     loc_18002FE66
0x18002fd4b  test    rsi, rsi
0x18002fd4e  jz      loc_18002FE61
0x18002fd54  lea     rbp, [r12+rbx*2]
0x18002fd58  cmp     [rsi], r15w
0x18002fd5c  jz      loc_18002FE61
0x18002fd62  mov     r13, rsi
0x18002fd65  mov     r15, r12
0x18002fd68  cmp     r12, rbp
0x18002fd6b  jnb     short loc_18002FD9F
0x18002fd6d  xor     eax, eax
0x18002fd6f  cmp     [rsi], ax
0x18002fd72  jz      short loc_18002FDB4
0x18002fd74  movzx   ecx, word ptr [r15]; Source
0x18002fd78  movzx   ebx, word ptr [rsi]
0x18002fd7b  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002fd81  movzx   ecx, bx; Source
0x18002fd84  movzx   edi, ax
0x18002fd87  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002fd8d  cmp     ax, di
0x18002fd90  jnz     short loc_18002FD9F
0x18002fd92  add     rsi, 2
0x18002fd96  add     r15, 2
0x18002fd9a  cmp     r15, rbp
0x18002fd9d  jb      short loc_18002FD6D
0x18002fd9f  cmp     r15, rbp
0x18002fda2  jnz     short loc_18002FDB4
0x18002fda4  cmp     word ptr [rsi], 3Dh ; '='
0x18002fda8  jnz     short loc_18002FDB4
0x18002fdaa  mov     edx, 1
0x18002fdaf  xor     r15d, r15d
0x18002fdb2  jmp     short loc_18002FDDF
0x18002fdb4  movzx   eax, word ptr [rsi]
0x18002fdb7  xor     r15d, r15d
0x18002fdba  test    ax, ax
0x18002fdbd  jz      short loc_18002FE02
0x18002fdbf  cmp     ax, 3Dh ; '='
0x18002fdc3  jnz     short loc_18002FDCA
0x18002fdc5  cmp     rsi, r13
0x18002fdc8  jnz     short loc_18002FDD6
0x18002fdca  add     rsi, 2
0x18002fdce  movzx   eax, word ptr [rsi]
0x18002fdd1  test    ax, ax
0x18002fdd4  jnz     short loc_18002FDBF
0x18002fdd6  cmp     [rsi], r15w
0x18002fdda  jz      short loc_18002FE02
0x18002fddc  mov     edx, r15d
0x18002fddf  mov     rcx, rsi
0x18002fde2  mov     rax, rsi
0x18002fde5  sub     rax, rcx
0x18002fde8  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002fdec  cmp     rax, 0FFFEh
0x18002fdf2  jge     short loc_18002FDFE
0x18002fdf4  add     rsi, 2
0x18002fdf8  cmp     [rsi], r15w
0x18002fdfc  jnz     short loc_18002FDE2
0x18002fdfe  test    edx, edx
0x18002fe00  jnz     short loc_18002FE0B
0x18002fe02  add     rsi, 2
0x18002fe06  jmp     loc_18002FD58
0x18002fe0b  mov     rdi, [rsp+68h+arg_28]
0x18002fe13  lea     rdx, [rcx+2]; Src
0x18002fe17  sub     rsi, rdx
0x18002fe1a  sar     rsi, 1
0x18002fe1d  cmp     rsi, [rsp+68h+arg_20]
0x18002fe25  jb      short loc_18002FE45
0x18002fe27  test    r14, r14
0x18002fe2a  jz      short loc_18002FE3B
0x18002fe2c  cmp     [rsp+68h+arg_20], 1
0x18002fe35  jb      short loc_18002FE3B
0x18002fe37  mov     [r14], r15w
0x18002fe3b  mov     eax, 0C0000023h
0x18002fe40  inc     rsi
0x18002fe43  jmp     short loc_18002FE5C
0x18002fe45  lea     rbx, [rsi+rsi]
0x18002fe49  mov     rcx, r14; void *
0x18002fe4c  mov     r8, rbx; Size
0x18002fe4f  call    memcpy_0
0x18002fe54  mov     [rbx+r14], r15w
0x18002fe59  mov     eax, r15d
0x18002fe5c  mov     [rdi], rsi
0x18002fe5f  jmp     short loc_18002FE66
0x18002fe61  mov     eax, 0C0000100h
0x18002fe66  add     rsp, 28h
0x18002fe6a  pop     r15
0x18002fe6c  pop     r14
0x18002fe6e  pop     r13
0x18002fe70  pop     r12
0x18002fe72  pop     rdi
0x18002fe73  pop     rsi
0x18002fe74  pop     rbp
0x18002fe75  pop     rbx
0x18002fe76  retn
```
