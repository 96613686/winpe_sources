# CModelDownloadComponent::EnsureModelFilePathExists(ushort *)

- ea: `0x14000e4c8`
- end: `0x14000e67e`
- name: `?EnsureModelFilePathExists@CModelDownloadComponent@@AEAAJPEAG@Z`
- size: `438`
- prototype: `__int64 __fastcall(CModelDownloadComponent *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000fafc`
- `0x1400104b0`

## callees

- `0x1400028d8`
- `0x140003198`
- `0x140003540`
- `0x14000985c`
- `0x14000e4c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000e562`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000e5e7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000e562`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x14000e5e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e59f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e59f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000e5ca`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000e5ca`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000e595`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x14000e595`

## string_xrefs

- `0x14000e62b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1111)`
- `0x14000e639`: `CModelDownloadComponent::EnsureModelFilePathExists`
- `0x14000e52b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1118)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::EnsureModelFilePathExists(
        CModelDownloadComponent *this,
        unsigned __int16 *a2)
{
  char *v3; // rsi
  wchar_t *v4; // rax
  wchar_t *v5; // rdi
  signed int v6; // ebx
  const wchar_t *v7; // rax
  wchar_t *v8; // rsi
  signed int LastError; // eax
  wchar_t *v10; // rbp
  int Delimiter; // [rsp+68h] [rbp+10h] BYREF
  wchar_t *Context; // [rsp+70h] [rbp+18h] BYREF

  wcscpy((wchar_t *)&Delimiter, L"\\");
  Context = 0;
  if ( !a2 || (v3 = (char *)this + 1164, !*((_WORD *)this + 582)) )
  {
    v6 = -2147024809;
    v7 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1111)";
    v5 = 0;
    goto LABEL_20;
  }
  v4 = (wchar_t *)operator new[](0x20Au, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v6 = -2147024882;
    v7 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1118)";
LABEL_20:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::EnsureModelFilePathExists",
      v7,
      v6);
    goto LABEL_21;
  }
  v6 = 0;
  swprintf_s(v4, 0x104u, L"%s", v3);
  v8 = wcstok_s(a2, (const wchar_t *)&Delimiter, &Context);
  if ( v8 )
  {
    while ( 1 )
    {
      v10 = wcstok_s(0, (const wchar_t *)&Delimiter, &Context);
      if ( !v10 )
        goto LABEL_18;
      swprintf_s(v5, 0x104u, L"%s\\%s", v5, v8);
      if ( !CreateDirectoryW(v5, 0) )
        break;
LABEL_16:
      v8 = v10;
    }
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 >= 0 )
    {
      v6 = -2147467259;
    }
    else if ( v6 == -2147024713 )
    {
LABEL_15:
      v6 = 0;
      goto LABEL_16;
    }
    if ( GetFileAttributesW(v5) == -1 )
      goto LABEL_16;
    goto LABEL_15;
  }
LABEL_18:
  swprintf_s(v5, 0x104u, L"%s\\%s", v5, v8);
  swprintf_s(a2, 0x104u, L"%s", v5);
LABEL_21:
  operator delete(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14000e4c8  mov     [rsp+arg_0], rbx
0x14000e4cd  mov     [rsp+arg_18], rbp
0x14000e4d2  push    rsi
0x14000e4d3  push    rdi
0x14000e4d4  push    r12
0x14000e4d6  push    r14
0x14000e4d8  push    r15
0x14000e4da  sub     rsp, 30h
0x14000e4de  mov     eax, dword ptr cs:SubBlock; "\\"
0x14000e4e4  xor     r15d, r15d
0x14000e4e7  mov     [rsp+58h+Delimiter], eax
0x14000e4eb  mov     r14, rdx
0x14000e4ee  mov     [rsp+58h+Context], r15
0x14000e4f3  test    rdx, rdx
0x14000e4f6  jz      loc_14000E626
0x14000e4fc  lea     rsi, [rcx+48Ch]
0x14000e503  cmp     [rsi], r15w
0x14000e507  jz      loc_14000E626
0x14000e50d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000e514  mov     ecx, 20Ah; unsigned __int64
0x14000e519  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14000e51e  mov     rdi, rax
0x14000e521  test    rax, rax
0x14000e524  jnz     short loc_14000E537
0x14000e526  mov     ebx, 8007000Eh
0x14000e52b  lea     rax, aOnecoreuapEndu_94; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e532  jmp     loc_14000E635
0x14000e537  mov     r12d, 104h
0x14000e53d  lea     r8, aS; "%s"
0x14000e544  mov     edx, r12d; BufferCount
0x14000e547  mov     r9, rsi
0x14000e54a  mov     rcx, rdi; Buffer
0x14000e54d  mov     ebx, r15d
0x14000e550  call    swprintf_s
0x14000e555  lea     r8, [rsp+58h+Context]; Context
0x14000e55a  mov     rcx, r14; String
0x14000e55d  lea     rdx, [rsp+58h+Delimiter]; Delimiter
0x14000e562  call    cs:__imp_wcstok_s
0x14000e568  mov     rsi, rax
0x14000e56b  test    rax, rax
0x14000e56e  jz      loc_14000E5F5
0x14000e574  jmp     short loc_14000E5DB
0x14000e576  mov     r9, rdi
0x14000e579  mov     [rsp+58h+var_38], rsi
0x14000e57e  lea     r8, aSS; "%s\\%s"
0x14000e585  mov     rdx, r12; BufferCount
0x14000e588  mov     rcx, rdi; Buffer
0x14000e58b  call    swprintf_s
0x14000e590  xor     edx, edx; lpSecurityAttributes
0x14000e592  mov     rcx, rdi; lpPathName
0x14000e595  call    cs:__imp_CreateDirectoryW
0x14000e59b  test    eax, eax
0x14000e59d  jnz     short loc_14000E5D8
0x14000e59f  call    cs:__imp_GetLastError
0x14000e5a5  mov     ebx, eax
0x14000e5a7  test    eax, eax
0x14000e5a9  jle     short loc_14000E5B4
0x14000e5ab  movzx   ebx, ax
0x14000e5ae  or      ebx, 80070000h
0x14000e5b4  test    ebx, ebx
0x14000e5b6  jns     short loc_14000E5C2
0x14000e5b8  cmp     ebx, 800700B7h
0x14000e5be  jz      short loc_14000E5D5
0x14000e5c0  jmp     short loc_14000E5C7
0x14000e5c2  mov     ebx, 80004005h
0x14000e5c7  mov     rcx, rdi; lpFileName
0x14000e5ca  call    cs:__imp_GetFileAttributesW
0x14000e5d0  cmp     eax, 0FFFFFFFFh
0x14000e5d3  jz      short loc_14000E5D8
0x14000e5d5  mov     ebx, r15d
0x14000e5d8  mov     rsi, rbp
0x14000e5db  lea     r8, [rsp+58h+Context]; Context
0x14000e5e0  xor     ecx, ecx; String
0x14000e5e2  lea     rdx, [rsp+58h+Delimiter]; Delimiter
0x14000e5e7  call    cs:__imp_wcstok_s
0x14000e5ed  mov     rbp, rax
0x14000e5f0  test    rax, rax
0x14000e5f3  jnz     short loc_14000E576
0x14000e5f5  mov     r9, rdi
0x14000e5f8  mov     [rsp+58h+var_38], rsi
0x14000e5fd  lea     r8, aSS; "%s\\%s"
0x14000e604  mov     rdx, r12; BufferCount
0x14000e607  mov     rcx, rdi; Buffer
0x14000e60a  call    swprintf_s
0x14000e60f  mov     r9, rdi
0x14000e612  lea     r8, aS; "%s"
0x14000e619  mov     rdx, r12; BufferCount
0x14000e61c  mov     rcx, r14; Buffer
0x14000e61f  call    swprintf_s
0x14000e624  jmp     short loc_14000E65D
0x14000e626  mov     ebx, 80070057h
0x14000e62b  lea     rax, aOnecoreuapEndu_109; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000e632  mov     rdi, r15
0x14000e635  mov     [rsp+58h+var_30], ebx
0x14000e639  lea     r9, aCmodeldownload_12; "CModelDownloadComponent::EnsureModelFil"...
0x14000e640  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000e647  mov     [rsp+58h+var_38], rax
0x14000e64c  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000e653  mov     ecx, 2; int
0x14000e658  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000e65d  mov     rcx, rdi; Block
0x14000e660  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000e665  mov     rbp, [rsp+58h+arg_18]
0x14000e66a  mov     eax, ebx
0x14000e66c  mov     rbx, [rsp+58h+arg_0]
0x14000e671  add     rsp, 30h
0x14000e675  pop     r15
0x14000e677  pop     r14
0x14000e679  pop     r12
0x14000e67b  pop     rdi
0x14000e67c  pop     rsi
0x14000e67d  retn
```
