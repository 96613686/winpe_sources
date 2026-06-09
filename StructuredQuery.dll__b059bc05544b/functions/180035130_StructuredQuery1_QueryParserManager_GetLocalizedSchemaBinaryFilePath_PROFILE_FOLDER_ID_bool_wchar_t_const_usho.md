# StructuredQuery1::QueryParserManager::GetLocalizedSchemaBinaryFilePath(_PROFILE_FOLDER_ID,bool,wchar_t const *,ushort,wchar_t const *,wchar_t *,ulong)

- ea: `0x180035130`
- end: `0x1800352d0`
- name: `?GetLocalizedSchemaBinaryFilePath@QueryParserManager@StructuredQuery1@@AEAAJW4_PROFILE_FOLDER_ID@@_NPEB_WG2PEA_WK@Z`
- size: `416`
- prototype: `int __high(enum _PROFILE_FOLDER_ID, bool, const wchar_t *, unsigned __int16, const wchar_t *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x180034f50`

## callees

- `0x180035130`
- `0x1800352d8`
- `0x180035e7c`
- `0x18003e5d0`
- `0x18005daf0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800352b5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800352b5`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18003519f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800351cf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180035222`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18003525f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18003519f`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800351cf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180035222`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18003525f`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180035185`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x180035185`

## pseudocode

```c
int __fastcall StructuredQuery1::QueryParserManager::GetLocalizedSchemaBinaryFilePath(
        __int64 a1,
        unsigned int a2,
        char a3,
        const WCHAR *a4,
        unsigned __int16 a5,
        wchar_t *a6,
        wchar_t *pszPath)
{
  int result; // eax
  const WCHAR *v11; // r8
  WCHAR pszMore[8]; // [rsp+30h] [rbp-48h] BYREF

  if ( a6 )
  {
    result = StringCchCopyW(pszPath, 0x104u, a6);
LABEL_9:
    if ( result < 0 )
      return result;
    goto LABEL_10;
  }
  result = GetBasicProfileFolderPath(a2, 0, pszPath, 260);
  if ( result < 0 )
    return result;
  result = PathCchAppend(pszPath, 0x104u, L"Microsoft");
  if ( result < 0 )
    return result;
  if ( a3 )
  {
    result = StructuredQuery1::EnsureDirectoryExists(pszPath);
    if ( result < 0 )
      return result;
  }
  result = PathCchAppend(pszPath, 0x104u, L"Windows");
  if ( result < 0 )
    return result;
  if ( a3 )
  {
    result = StructuredQuery1::EnsureDirectoryExists(pszPath);
    goto LABEL_9;
  }
LABEL_10:
  if ( !*(_BYTE *)(a1 + 56)
    || (result = StringCchPrintfW(pszMore, 6u, L"%hu", a5), result >= 0)
    && (result = PathCchAppend(pszPath, 0x104u, pszMore), result >= 0)
    && (!a3 || (result = StructuredQuery1::EnsureDirectoryExists(pszPath), result >= 0)) )
  {
    v11 = *(const WCHAR **)(a1 + 24);
    if ( !v11 )
    {
      if ( a4 )
      {
        if ( *a4 )
        {
          v11 = L"StructuredQuerySchema.bin";
          return PathCchAppend(pszPath, 0x104u, v11);
        }
        if ( CompareStringW(0x7Fu, 1u, a4, -1, (PCNZWCH)&cchOriginalDestLength, -1) == 2 )
        {
          v11 = L"StructuredQuerySchemaTrivial.bin";
          return PathCchAppend(pszPath, 0x104u, v11);
        }
      }
      return -2147024809;
    }
    return PathCchAppend(pszPath, 0x104u, v11);
  }
  return result;
}

```

## disassembly

```asm
0x180035130  mov     [rsp+arg_10], rbx
0x180035135  push    rbp
0x180035136  push    rsi
0x180035137  push    rdi
0x180035138  push    r14
0x18003513a  push    r15
0x18003513c  sub     rsp, 50h
0x180035140  mov     rax, cs:__security_cookie
0x180035147  xor     rax, rsp
0x18003514a  mov     [rsp+78h+var_38], rax
0x18003514f  mov     rbx, [rsp+78h+pszPath]
0x180035157  mov     sil, r8b
0x18003515a  mov     r8, [rsp+78h+arg_28]; wchar_t *
0x180035162  xor     r15d, r15d
0x180035165  mov     rbp, r9
0x180035168  mov     eax, edx
0x18003516a  mov     r14, rcx
0x18003516d  mov     edi, 104h
0x180035172  test    r8, r8
0x180035175  jnz     loc_180035286
0x18003517b  mov     r9d, edi
0x18003517e  mov     r8, rbx
0x180035181  xor     edx, edx
0x180035183  mov     ecx, eax
0x180035185  call    cs:__imp_GetBasicProfileFolderPath
0x18003518b  test    eax, eax
0x18003518d  js      loc_180035265
0x180035193  lea     r8, pszMore; "Microsoft"
0x18003519a  mov     edx, edi; cchPath
0x18003519c  mov     rcx, rbx; pszPath
0x18003519f  call    cs:__imp_PathCchAppend
0x1800351a5  test    eax, eax
0x1800351a7  js      loc_180035265
0x1800351ad  test    sil, sil
0x1800351b0  jz      short loc_1800351C2
0x1800351b2  mov     rcx, rbx
0x1800351b5  call    StructuredQuery1__EnsureDirectoryExists
0x1800351ba  test    eax, eax
0x1800351bc  js      loc_180035265
0x1800351c2  lea     r8, aWindows; "Windows"
0x1800351c9  mov     rdx, rdi; cchPath
0x1800351cc  mov     rcx, rbx; pszPath
0x1800351cf  call    cs:__imp_PathCchAppend
0x1800351d5  test    eax, eax
0x1800351d7  js      loc_180035265
0x1800351dd  test    sil, sil
0x1800351e0  jz      short loc_1800351EE
0x1800351e2  mov     rcx, rbx
0x1800351e5  call    StructuredQuery1__EnsureDirectoryExists
0x1800351ea  test    eax, eax
0x1800351ec  js      short loc_180035265
0x1800351ee  cmp     [r14+38h], r15b
0x1800351f2  jz      short loc_18003523D
0x1800351f4  movzx   r9d, [rsp+78h+arg_20]
0x1800351fd  lea     r8, aHu_0; "%hu"
0x180035204  mov     edx, 6; unsigned __int64
0x180035209  lea     rcx, [rsp+78h+pszMore]; wchar_t *
0x18003520e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180035213  test    eax, eax
0x180035215  js      short loc_180035265
0x180035217  lea     r8, [rsp+78h+pszMore]; pszMore
0x18003521c  mov     rdx, rdi; cchPath
0x18003521f  mov     rcx, rbx; pszPath
0x180035222  call    cs:__imp_PathCchAppend
0x180035228  test    eax, eax
0x18003522a  js      short loc_180035265
0x18003522c  test    sil, sil
0x18003522f  jz      short loc_18003523D
0x180035231  mov     rcx, rbx
0x180035234  call    StructuredQuery1__EnsureDirectoryExists
0x180035239  test    eax, eax
0x18003523b  js      short loc_180035265
0x18003523d  mov     r8, [r14+18h]
0x180035241  test    r8, r8
0x180035244  jnz     short loc_180035259
0x180035246  test    rbp, rbp
0x180035249  jz      short loc_1800352C9
0x18003524b  cmp     [rbp+0], r15w
0x180035250  jz      short loc_180035296
0x180035252  lea     r8, aStructuredquer_3; "StructuredQuerySchema.bin"
0x180035259  mov     rdx, rdi; cchPath
0x18003525c  mov     rcx, rbx; pszPath
0x18003525f  call    cs:__imp_PathCchAppend
0x180035265  mov     rcx, [rsp+78h+var_38]
0x18003526a  xor     rcx, rsp; StackCookie
0x18003526d  call    __security_check_cookie
0x180035272  mov     rbx, [rsp+78h+arg_10]
0x18003527a  add     rsp, 50h
0x18003527e  pop     r15
0x180035280  pop     r14
0x180035282  pop     rdi
0x180035283  pop     rsi
0x180035284  pop     rbp
0x180035285  retn
0x180035286  mov     rdx, rdi; unsigned __int64
0x180035289  mov     rcx, rbx; wchar_t *
0x18003528c  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180035291  jmp     loc_1800351EA
0x180035296  or      r9d, 0FFFFFFFFh; cchCount1
0x18003529a  lea     rax, cchOriginalDestLength
0x1800352a1  mov     [rsp+78h+cchCount2], r9d; cchCount2
0x1800352a6  mov     r8, rbp; lpString1
0x1800352a9  mov     [rsp+78h+lpString2], rax; lpString2
0x1800352ae  lea     edx, [r9+2]; dwCmpFlags
0x1800352b2  lea     ecx, [rdx+7Eh]; Locale
0x1800352b5  call    cs:__imp_CompareStringW
0x1800352bb  cmp     eax, 2
0x1800352be  jnz     short loc_1800352C9
0x1800352c0  lea     r8, aStructuredquer_1; "StructuredQuerySchemaTrivial.bin"
0x1800352c7  jmp     short loc_180035259
0x1800352c9  mov     eax, 80070057h
0x1800352ce  jmp     short loc_180035265
```
