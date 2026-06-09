# AslEnvVarQuery

- ea: `0x18002c8dc`
- end: `0x18002cb04`
- name: `AslEnvVarQuery`
- size: `552`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180017b80`
- `0x18002c6fc`
- `0x180042568`

## callees

- `0x18002c8dc`
- `0x180039a66`
- `0x18005921d`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x18002ca19`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002ca25`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002ca19`
- `ntdll!RtlUpcaseUnicodeChar` at `0x18002ca25`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c940`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c940`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c96e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c96e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c958`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c958`

## string_xrefs

- `0x18002c92e`: `ntdll.dll`

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

  if ( a3 < 0xA || wcsnicmp_0(a2, L"systemroot", 0xAu) )
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
  v10 = (__int64)String1;
  if ( !String1 )
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
    String1 = (wchar_t *)v10;
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
0x18002c8dc  push    rbx
0x18002c8de  push    rbp
0x18002c8df  push    rsi
0x18002c8e0  push    rdi
0x18002c8e1  push    r12
0x18002c8e3  push    r13
0x18002c8e5  push    r14
0x18002c8e7  push    r15
0x18002c8e9  sub     rsp, 28h
0x18002c8ed  xor     r15d, r15d
0x18002c8f0  mov     rbx, r8
0x18002c8f3  mov     r14, r9
0x18002c8f6  mov     r12, rdx
0x18002c8f9  mov     rsi, rcx
0x18002c8fc  lea     r8d, [r15+0Ah]; MaxCount
0x18002c900  cmp     rbx, r8
0x18002c903  jb      loc_18002C9E9
0x18002c909  lea     rdx, aSystemroot_1; "systemroot"
0x18002c910  mov     rcx, r12; String1
0x18002c913  call    _wcsnicmp_0
0x18002c918  test    eax, eax
0x18002c91a  jnz     loc_18002C9E9
0x18002c920  mov     rdi, cs:String1
0x18002c927  test    rdi, rdi
0x18002c92a  jnz     short loc_18002C97B
0x18002c92c  xor     edx, edx; hFile
0x18002c92e  lea     rcx, LibFileName; "ntdll.dll"
0x18002c935  mov     r8d, 800h; dwFlags
0x18002c93b  mov     edi, 7FFE0030h
0x18002c940  call    cs:__imp_LoadLibraryExW
0x18002c946  mov     rbx, rax
0x18002c949  test    rax, rax
0x18002c94c  jz      short loc_18002C974
0x18002c94e  lea     rdx, aRtlgetntsystem; "RtlGetNtSystemRoot"
0x18002c955  mov     rcx, rax; hModule
0x18002c958  call    cs:__imp_GetProcAddress
0x18002c95e  test    rax, rax
0x18002c961  jz      short loc_18002C96B
0x18002c963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c968  mov     rdi, rax
0x18002c96b  mov     rcx, rbx; hLibModule
0x18002c96e  call    cs:__imp_FreeLibrary
0x18002c974  mov     cs:String1, rdi
0x18002c97b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002c97f  inc     rbx
0x18002c982  cmp     [rdi+rbx*2], r15w
0x18002c987  jnz     short loc_18002C97F
0x18002c989  cmp     rbx, [rsp+68h+arg_20]
0x18002c991  jb      short loc_18002C9C0
0x18002c993  test    r14, r14
0x18002c996  jz      short loc_18002C9A7
0x18002c998  cmp     [rsp+68h+arg_20], 1
0x18002c9a1  jb      short loc_18002C9A7
0x18002c9a3  mov     [r14], r15w
0x18002c9a7  lea     rcx, [rbx+1]
0x18002c9ab  mov     rax, [rsp+68h+arg_28]
0x18002c9b3  mov     [rax], rcx
0x18002c9b6  mov     eax, 0C0000023h
0x18002c9bb  jmp     loc_18002CAF3
0x18002c9c0  mov     rax, [rsp+68h+arg_28]
0x18002c9c8  mov     rdx, rdi; Src
0x18002c9cb  mov     [rax], rbx
0x18002c9ce  add     rbx, rbx
0x18002c9d1  mov     r8, rbx; Size
0x18002c9d4  mov     rcx, r14; void *
0x18002c9d7  call    memcpy_0
0x18002c9dc  mov     [rbx+r14], r15w
0x18002c9e1  mov     eax, r15d
0x18002c9e4  jmp     loc_18002CAF3
0x18002c9e9  test    rsi, rsi
0x18002c9ec  jz      loc_18002CAEE
0x18002c9f2  lea     rbp, [r12+rbx*2]
0x18002c9f6  cmp     [rsi], r15w
0x18002c9fa  jz      loc_18002CAEE
0x18002ca00  mov     r13, rsi
0x18002ca03  mov     r15, r12
0x18002ca06  cmp     r12, rbp
0x18002ca09  jnb     short loc_18002CA3D
0x18002ca0b  xor     eax, eax
0x18002ca0d  cmp     [rsi], ax
0x18002ca10  jz      short loc_18002CA52
0x18002ca12  movzx   ecx, word ptr [r15]; Source
0x18002ca16  movzx   ebx, word ptr [rsi]
0x18002ca19  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002ca1f  movzx   ecx, bx; Source
0x18002ca22  movzx   edi, ax
0x18002ca25  call    cs:__imp_RtlUpcaseUnicodeChar
0x18002ca2b  cmp     ax, di
0x18002ca2e  jnz     short loc_18002CA3D
0x18002ca30  add     rsi, 2
0x18002ca34  add     r15, 2
0x18002ca38  cmp     r15, rbp
0x18002ca3b  jb      short loc_18002CA0B
0x18002ca3d  cmp     r15, rbp
0x18002ca40  jnz     short loc_18002CA52
0x18002ca42  cmp     word ptr [rsi], 3Dh ; '='
0x18002ca46  jnz     short loc_18002CA52
0x18002ca48  mov     edx, 1
0x18002ca4d  xor     r15d, r15d
0x18002ca50  jmp     short loc_18002CA7D
0x18002ca52  movzx   eax, word ptr [rsi]
0x18002ca55  xor     r15d, r15d
0x18002ca58  test    ax, ax
0x18002ca5b  jz      short loc_18002CAA0
0x18002ca5d  cmp     ax, 3Dh ; '='
0x18002ca61  jnz     short loc_18002CA68
0x18002ca63  cmp     rsi, r13
0x18002ca66  jnz     short loc_18002CA74
0x18002ca68  add     rsi, 2
0x18002ca6c  movzx   eax, word ptr [rsi]
0x18002ca6f  test    ax, ax
0x18002ca72  jnz     short loc_18002CA5D
0x18002ca74  cmp     [rsi], r15w
0x18002ca78  jz      short loc_18002CAA0
0x18002ca7a  mov     edx, r15d
0x18002ca7d  mov     rcx, rsi
0x18002ca80  mov     rax, rsi
0x18002ca83  sub     rax, rcx
0x18002ca86  and     rax, 0FFFFFFFFFFFFFFFEh
0x18002ca8a  cmp     rax, 0FFFEh
0x18002ca90  jge     short loc_18002CA9C
0x18002ca92  add     rsi, 2
0x18002ca96  cmp     [rsi], r15w
0x18002ca9a  jnz     short loc_18002CA80
0x18002ca9c  test    edx, edx
0x18002ca9e  jnz     short loc_18002CAA9
0x18002caa0  add     rsi, 2
0x18002caa4  jmp     loc_18002C9F6
0x18002caa9  lea     rdx, [rcx+2]
0x18002caad  sub     rsi, rdx
0x18002cab0  sar     rsi, 1
0x18002cab3  cmp     rsi, [rsp+68h+arg_20]
0x18002cabb  jb      short loc_18002CADA
0x18002cabd  test    r14, r14
0x18002cac0  jz      short loc_18002CAD1
0x18002cac2  cmp     [rsp+68h+arg_20], 1
0x18002cacb  jb      short loc_18002CAD1
0x18002cacd  mov     [r14], r15w
0x18002cad1  lea     rcx, [rsi+1]
0x18002cad5  jmp     loc_18002C9AB
0x18002cada  mov     rax, [rsp+68h+arg_28]
0x18002cae2  lea     rbx, [rsi+rsi]
0x18002cae6  mov     [rax], rsi
0x18002cae9  jmp     loc_18002C9D1
0x18002caee  mov     eax, 0C0000100h
0x18002caf3  add     rsp, 28h
0x18002caf7  pop     r15
0x18002caf9  pop     r14
0x18002cafb  pop     r13
0x18002cafd  pop     r12
0x18002caff  pop     rdi
0x18002cb00  pop     rsi
0x18002cb01  pop     rbp
0x18002cb02  pop     rbx
0x18002cb03  retn
```
