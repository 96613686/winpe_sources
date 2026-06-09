# Windows::_anonymous_namespace_::FciCbFileDelete

- ea: `0x14024c4b0`
- end: `0x14024c671`
- name: `Windows::_anonymous_namespace_::FciCbFileDelete`
- size: `449`
- prototype: `int __cdecl(LPSTR pszFile, int *err, void *pv)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops`

## callees

- `0x140044b90`
- `0x140044f20`
- `0x140045404`
- `0x14024a094`
- `0x14024a1f4`
- `0x14024c4b0`
- `0x140379070`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024c627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14024c627`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14024c58a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14024c61d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14024c58a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14024c61d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14024c5d4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14024c5d4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024c606`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x14024c606`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::_anonymous_namespace_::FciCbFileDelete(LPSTR pszFile, DWORD *err, void *pv)
{
  __int64 v4; // r8
  __int64 v5; // rbx
  const WCHAR *v6; // rcx
  BOOL v7; // eax
  LPCWSTR *v8; // rax
  __int64 CanonicalUNCPath; // rax
  DWORD FileAttributesW; // ebx
  const WCHAR *v11; // rcx
  const WCHAR *v12; // rcx
  _OWORD v14[2]; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v15[32]; // [rsp+40h] [rbp-58h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+60h] [rbp-38h] BYREF
  __m128i si128; // [rsp+70h] [rbp-28h]

  *(_OWORD *)lpFileName = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpFileName[0]) = 0;
  memset(v14, 0, sizeof(v14));
  v4 = -1;
  do
    ++v4;
  while ( pszFile[v4] );
  try
  {
    std::string::_Construct<1,char const *>(v14, pszFile);
    v5 = MultiByteToUnicode(v15, v14);
    if ( lpFileName != (LPCWSTR *)v5 )
    {
      std::wstring::~wstring(lpFileName);
      *(_OWORD *)lpFileName = *(_OWORD *)v5;
      si128 = *(__m128i *)(v5 + 16);
      *(_QWORD *)(v5 + 16) = 0;
      *(_QWORD *)(v5 + 24) = 7;
      *(_WORD *)v5 = 0;
    }
    std::wstring::~wstring(v15);
    std::string::_Tidy_deallocate(v14);
    v6 = (const WCHAR *)lpFileName;
    if ( si128.m128i_i64[1] > 7uLL )
      v6 = lpFileName[0];
    v7 = DeleteFileW(v6);
  }
  catch ( ... )
  {
    goto LABEL_23;
  }
  if ( v7 )
    goto LABEL_22;
  v8 = lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (LPCWSTR *)lpFileName[0];
  *(_QWORD *)&v14[0] = v8;
  *((_QWORD *)&v14[0] + 1) = si128.m128i_i64[0];
  CanonicalUNCPath = Windows::_anonymous_namespace_::GetCanonicalUNCPath((__int64)v15, (__int64)v14);
  if ( *(_QWORD *)(CanonicalUNCPath + 24) > 7u )
    CanonicalUNCPath = *(_QWORD *)CanonicalUNCPath;
  FileAttributesW = GetFileAttributesW((LPCWSTR)CanonicalUNCPath);
  std::wstring::~wstring(v15);
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) != 0 )
    goto LABEL_22;
  v11 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v11 = lpFileName[0];
  SetFileAttributesW(v11, 0x80u);
  v12 = (const WCHAR *)lpFileName;
  if ( si128.m128i_i64[1] > 7uLL )
    v12 = lpFileName[0];
  if ( DeleteFileW(v12) )
  {
LABEL_22:
    std::wstring::~wstring(lpFileName);
    return 0;
  }
  else
  {
    *err = GetLastError();
LABEL_23:
    std::wstring::~wstring(lpFileName);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x14024c4b0  mov     [rsp+arg_10], rbx
0x14024c4b5  mov     [rsp+arg_18], rsi
0x14024c4ba  push    rdi
0x14024c4bb  sub     rsp, 90h
0x14024c4c2  mov     rax, cs:__security_cookie
0x14024c4c9  xor     rax, rsp
0x14024c4cc  mov     [rsp+98h+var_18], rax
0x14024c4d4  mov     rdi, rdx
0x14024c4d7  xorps   xmm0, xmm0
0x14024c4da  movups  xmmword ptr [rsp+98h+lpFileName], xmm0
0x14024c4df  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14024c4e7  movdqu  [rsp+98h+var_28], xmm1
0x14024c4ed  xor     esi, esi
0x14024c4ef  mov     word ptr [rsp+98h+lpFileName], si
0x14024c4f4  movups  [rsp+98h+var_78], xmm0
0x14024c4f9  xorps   xmm1, xmm1
0x14024c4fc  movdqu  [rsp+98h+var_68], xmm1
0x14024c502  or      r8, 0FFFFFFFFFFFFFFFFh
0x14024c506  inc     r8
0x14024c509  cmp     [rcx+r8], sil
0x14024c50d  jnz     short loc_14024C506
0x14024c50f  mov     rdx, rcx
0x14024c512  lea     rcx, [rsp+98h+var_78]
0x14024c517  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x14024c51c  nop
0x14024c51d  lea     rdx, [rsp+98h+var_78]
0x14024c522  lea     rcx, [rsp+98h+var_58]
0x14024c527  call    MultiByteToUnicode
0x14024c52c  mov     rbx, rax
0x14024c52f  lea     rax, [rsp+98h+lpFileName]
0x14024c534  cmp     rax, rbx
0x14024c537  jz      short loc_14024C563
0x14024c539  lea     rcx, [rsp+98h+lpFileName]
0x14024c53e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024c543  movups  xmm0, xmmword ptr [rbx]
0x14024c546  movups  xmmword ptr [rsp+98h+lpFileName], xmm0
0x14024c54b  movups  xmm1, xmmword ptr [rbx+10h]
0x14024c54f  movups  [rsp+98h+var_28], xmm1
0x14024c554  mov     [rbx+10h], rsi
0x14024c558  mov     qword ptr [rbx+18h], 7
0x14024c560  mov     [rbx], si
0x14024c563  lea     rcx, [rsp+98h+var_58]
0x14024c568  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024c56d  nop
0x14024c56e  lea     rcx, [rsp+98h+var_78]
0x14024c573  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024c578  nop
0x14024c579  lea     rcx, [rsp+98h+lpFileName]
0x14024c57e  cmp     qword ptr [rsp+98h+var_28+8], 7
0x14024c584  cmova   rcx, [rsp+98h+lpFileName]; lpFileName
0x14024c58a  call    cs:__imp_DeleteFileW
0x14024c590  test    eax, eax
0x14024c592  jnz     loc_14024C631
0x14024c598  lea     rax, [rsp+98h+lpFileName]
0x14024c59d  cmp     qword ptr [rsp+98h+var_28+8], 7
0x14024c5a3  cmova   rax, [rsp+98h+lpFileName]
0x14024c5a9  mov     qword ptr [rsp+98h+var_78], rax
0x14024c5ae  mov     rax, qword ptr [rsp+98h+var_28]
0x14024c5b3  mov     qword ptr [rsp+98h+var_78+8], rax
0x14024c5b8  lea     rdx, [rsp+98h+var_78]
0x14024c5bd  lea     rcx, [rsp+98h+var_58]
0x14024c5c2  call    Windows___anonymous_namespace___GetCanonicalUNCPath
0x14024c5c7  cmp     qword ptr [rax+18h], 7
0x14024c5cc  jbe     short loc_14024C5D1
0x14024c5ce  mov     rax, [rax]
0x14024c5d1  mov     rcx, rax; lpFileName
0x14024c5d4  call    cs:__imp_GetFileAttributesW
0x14024c5da  mov     ebx, eax
0x14024c5dc  lea     rcx, [rsp+98h+var_58]
0x14024c5e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024c5e6  cmp     ebx, 0FFFFFFFFh
0x14024c5e9  jz      short loc_14024C631
0x14024c5eb  test    bl, 10h
0x14024c5ee  jnz     short loc_14024C631
0x14024c5f0  lea     rcx, [rsp+98h+lpFileName]
0x14024c5f5  cmp     qword ptr [rsp+98h+var_28+8], 7
0x14024c5fb  cmova   rcx, [rsp+98h+lpFileName]; lpFileName
0x14024c601  mov     edx, 80h; dwFileAttributes
0x14024c606  call    cs:__imp_SetFileAttributesW
0x14024c60c  lea     rcx, [rsp+98h+lpFileName]
0x14024c611  cmp     qword ptr [rsp+98h+var_28+8], 7
0x14024c617  cmova   rcx, [rsp+98h+lpFileName]; lpFileName
0x14024c61d  call    cs:__imp_DeleteFileW
0x14024c623  test    eax, eax
0x14024c625  jnz     short loc_14024C631
0x14024c627  call    cs:__imp_GetLastError
0x14024c62d  mov     [rdi], eax
0x14024c62f  jmp     short loc_14024C63F
0x14024c631  lea     rcx, [rsp+98h+lpFileName]
0x14024c636  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024c63b  xor     eax, eax
0x14024c63d  jmp     short loc_14024C64C
0x14024c63f  lea     rcx, [rsp+98h+lpFileName]
0x14024c644  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024c649  or      eax, 0FFFFFFFFh
0x14024c64c  mov     rcx, [rsp+98h+var_18]
0x14024c654  xor     rcx, rsp; StackCookie
0x14024c657  call    __security_check_cookie
0x14024c65c  lea     r11, [rsp+98h+var_8]
0x14024c664  mov     rbx, [r11+20h]
0x14024c668  mov     rsi, [r11+28h]
0x14024c66c  mov     rsp, r11
0x14024c66f  pop     rdi
0x14024c670  retn
```
