# TmGetDescriptionFromVersionInfo(uchar *,ulong,ushort const *,HSTRING__ * *)

- ea: `0x1800d04fc`
- end: `0x1800d060d`
- name: `?TmGetDescriptionFromVersionInfo@@YAJPEAEKPEBGPEAPEAUHSTRING__@@@Z`
- size: `273`
- prototype: `int(unsigned __int8 *, unsigned int, const unsigned __int16 *, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x1800d6704`

## callees

- `0x180006e50`
- `0x18000f038`
- `0x1800d03a8`
- `0x1800d04fc`
- `0x1800d09d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d05e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800d05e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800d059b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1800d059b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800d05a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800d05a6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1800d05c1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveBlanksW` at `0x1800d05c1`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800d05b6`
- `api-ms-win-core-string-l2-1-0!CharUpperBuffW` at `0x1800d05b6`

## pseudocode

```c
HRESULT __fastcall TmGetDescriptionFromVersionInfo(
        unsigned __int8 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  __int64 v6; // rdx
  unsigned int v8; // [rsp+20h] [rbp-E0h]
  bool v9; // [rsp+28h] [rbp-D8h]
  WCHAR pszPath[264]; // [rsp+30h] [rbp-D0h] BYREF

  *a4 = 0;
  if ( !a3 || !*a3 )
    return 0;
  pszPath[0] = 0;
  if ( (!a1 || !a2 || (int)TmGetStringFromVersionInfo(a1, a2, L"FileDescription", pszPath, v8, v9) < 0 || !pszPath[0])
    && ((int)TmGetDescriptionFromShellFolder(a3, pszPath, (unsigned int)a3) < 0 || !pszPath[0]) )
  {
    StringCchCopyW(pszPath, 0x104u, a3);
    PathStripPathW(pszPath);
    PathRemoveExtensionW(pszPath);
    CharUpperBuffW(pszPath, 1u);
  }
  PathRemoveBlanksW(pszPath);
  v6 = -1;
  do
    ++v6;
  while ( pszPath[v6] );
  return WindowsCreateString(pszPath, v6, a4);
}

```

## disassembly

```asm
0x1800d04fc  mov     [rsp-8+arg_8], rbx
0x1800d0501  push    rbp
0x1800d0502  push    rsi
0x1800d0503  push    rdi
0x1800d0504  lea     rbp, [rsp-150h]
0x1800d050c  sub     rsp, 250h
0x1800d0513  mov     rax, cs:__security_cookie
0x1800d051a  xor     rax, rsp
0x1800d051d  mov     [rbp+160h+var_20], rax
0x1800d0524  xor     esi, esi
0x1800d0526  mov     rdi, r9
0x1800d0529  mov     [r9], rsi
0x1800d052c  mov     rbx, r8
0x1800d052f  test    r8, r8
0x1800d0532  jz      loc_1800D05E9
0x1800d0538  cmp     si, [r8]
0x1800d053c  jz      loc_1800D05E9
0x1800d0542  mov     [rsp+260h+pszPath], si
0x1800d0547  test    rcx, rcx
0x1800d054a  jz      short loc_1800D056C
0x1800d054c  test    edx, edx
0x1800d054e  jz      short loc_1800D056C
0x1800d0550  lea     r9, [rsp+260h+pszPath]; unsigned __int16 *
0x1800d0555  lea     r8, aFiledescriptio; "FileDescription"
0x1800d055c  call    ?TmGetStringFromVersionInfo@@YAJQEBEKPEAG1K_N@Z; TmGetStringFromVersionInfo(uchar const * const,ulong,ushort *,ushort *,ulong,bool)
0x1800d0561  test    eax, eax
0x1800d0563  js      short loc_1800D056C
0x1800d0565  cmp     si, [rsp+260h+pszPath]
0x1800d056a  jnz     short loc_1800D05BC
0x1800d056c  lea     rdx, [rsp+260h+pszPath]; pszBuf
0x1800d0571  mov     rcx, rbx; pszName
0x1800d0574  call    ?TmGetDescriptionFromShellFolder@@YAJPEBGPEAGK@Z; TmGetDescriptionFromShellFolder(ushort const *,ushort *,ulong)
0x1800d0579  test    eax, eax
0x1800d057b  js      short loc_1800D0584
0x1800d057d  cmp     si, [rsp+260h+pszPath]
0x1800d0582  jnz     short loc_1800D05BC
0x1800d0584  mov     r8, rbx; unsigned __int16 *
0x1800d0587  lea     rcx, [rsp+260h+pszPath]; unsigned __int16 *
0x1800d058c  mov     edx, 104h; unsigned __int64
0x1800d0591  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800d0596  lea     rcx, [rsp+260h+pszPath]; pszPath
0x1800d059b  call    cs:__imp_PathStripPathW
0x1800d05a1  lea     rcx, [rsp+260h+pszPath]; pszPath
0x1800d05a6  call    cs:__imp_PathRemoveExtensionW
0x1800d05ac  mov     edx, 1; cchLength
0x1800d05b1  lea     rcx, [rsp+260h+pszPath]; lpsz
0x1800d05b6  call    cs:__imp_CharUpperBuffW
0x1800d05bc  lea     rcx, [rsp+260h+pszPath]; pszPath
0x1800d05c1  call    cs:__imp_PathRemoveBlanksW
0x1800d05c7  lea     rax, [rsp+260h+pszPath]
0x1800d05cc  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800d05d0  inc     rdx; length
0x1800d05d3  cmp     [rax+rdx*2], si
0x1800d05d7  jnz     short loc_1800D05D0
0x1800d05d9  mov     r8, rdi; string
0x1800d05dc  lea     rcx, [rsp+260h+pszPath]; sourceString
0x1800d05e1  call    cs:__imp_WindowsCreateString
0x1800d05e7  jmp     short loc_1800D05EB
0x1800d05e9  xor     eax, eax
0x1800d05eb  mov     rcx, [rbp+160h+var_20]
0x1800d05f2  xor     rcx, rsp; StackCookie
0x1800d05f5  call    __security_check_cookie
0x1800d05fa  mov     rbx, [rsp+260h+arg_8]
0x1800d0602  add     rsp, 250h
0x1800d0609  pop     rdi
0x1800d060a  pop     rsi
0x1800d060b  pop     rbp
0x1800d060c  retn
```
