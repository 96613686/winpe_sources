# FileUtility::GetFullTempFilePath(void)

- ea: `0x180010ae4`
- end: `0x180010d1f`
- name: `?GetFullTempFilePath@FileUtility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ`
- size: `571`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180010750`

## callees

- `0x18000254c`
- `0x180005e24`
- `0x18000a2e4`
- `0x18000a540`
- `0x180010ae4`
- `0x180010d28`
- `0x180010f80`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180010c79`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180010c79`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c97`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010b75`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010c97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c89`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010b67`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010c89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010b5f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010b7d`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010bfc`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180010bfc`
- `CRYPT32!CryptBinaryToStringW` at `0x180010c2a`
- `CRYPT32!CryptBinaryToStringW` at `0x180010c2a`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180010c4c`
- `api-ms-win-core-path-l1-1-0!PathCchAppendEx` at `0x180010c4c`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180010b37`
- `profapi!__imp_GetBasicProfileFolderPathAlloc` at `0x180010b37`

## pseudocode

```c
_QWORD *__fastcall FileUtility::GetFullTempFilePath(_QWORD *a1)
{
  int BasicProfileFolderPathAlloc; // eax
  void *v3; // r15
  LPVOID *v4; // rsi
  void *v5; // r14
  DWORD LastError; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rsi
  unsigned __int16 *v10; // rbx
  HRESULT v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  HRESULT v15; // eax
  void *v16; // rbx
  HANDLE v17; // rax
  int pcchString; // [rsp+20h] [rbp-89h]
  int pcchStringa; // [rsp+20h] [rbp-89h]
  LPVOID lpMem; // [rsp+30h] [rbp-79h] BYREF
  DWORD v22; // [rsp+38h] [rbp-71h] BYREF
  LPVOID *p_lpMem; // [rsp+40h] [rbp-69h]
  void *v24; // [rsp+48h] [rbp-61h] BYREF
  char v25; // [rsp+50h] [rbp-59h]
  unsigned __int16 *v26; // [rsp+60h] [rbp-49h]
  GUID pguid; // [rsp+68h] [rbp-41h] BYREF
  WCHAR pszString[40]; // [rsp+80h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  lpMem = 0;
  p_lpMem = &lpMem;
  v24 = 0;
  v25 = 1;
  BasicProfileFolderPathAlloc = GetBasicProfileFolderPathAlloc(6, 0, &v24);
  if ( BasicProfileFolderPathAlloc < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)BasicProfileFolderPathAlloc,
      pcchString);
  if ( v25 )
  {
    v3 = v24;
    v4 = p_lpMem;
    v5 = *p_lpMem;
    if ( *p_lpMem )
    {
      LastError = GetLastError();
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      SetLastError(LastError);
    }
    *v4 = v3;
  }
  v8 = -1;
  do
    ++v8;
  while ( *((_WORD *)lpMem + v8) );
  if ( v8 + 46 < v8 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x10,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      v8 + 46 < v8 ? (const char *)0x80070216LL : 0,
      pcchString);
  v9 = v8 + 46;
  v10 = (unsigned __int16 *)operator new[](saturated_mul(v8 + 46, 2u));
  v26 = v10;
  StringCchCopyW(v10, v9, (const unsigned __int16 *)lpMem);
  pguid = 0;
  v22 = 38;
  v11 = CoCreateGuid(&pguid);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v11,
      pcchString);
  if ( !CryptBinaryToStringW((const BYTE *)&pguid, 0x10u, 0x4000000Cu, pszString, &v22) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, v12, v13, v14);
  v15 = PathCchAppendEx(v10, v9, pszString, 1u);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\fileutility.cpp",
      (const char *)(unsigned int)v15,
      pcchStringa);
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, v10);
  operator delete[](v10);
  v16 = lpMem;
  if ( lpMem )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v16);
  }
  return a1;
}

```

## disassembly

```asm
0x180010ae4  mov     [rsp-8+arg_8], rbx
0x180010ae9  mov     [rsp-8+arg_10], rsi
0x180010aee  push    rbp
0x180010aef  push    rdi
0x180010af0  push    r12
0x180010af2  push    r14
0x180010af4  push    r15
0x180010af6  lea     rbp, [rsp-37h]
0x180010afb  sub     rsp, 0E0h
0x180010b02  mov     rax, cs:__security_cookie
0x180010b09  xor     rax, rsp
0x180010b0c  mov     [rbp+57h+var_30], rax
0x180010b10  mov     rdi, rcx
0x180010b13  mov     [rbp+57h+lpMem], rcx
0x180010b17  xor     r12d, r12d
0x180010b1a  mov     [rbp+57h+lpMem], r12
0x180010b1e  lea     rax, [rbp+57h+lpMem]
0x180010b22  mov     [rbp+57h+var_C0], rax
0x180010b26  mov     [rbp+57h+var_B8], r12
0x180010b2a  mov     [rbp+57h+var_B0], 1
0x180010b2e  lea     r8, [rbp+57h+var_B8]
0x180010b32  xor     edx, edx
0x180010b34  lea     ecx, [rdx+6]
0x180010b37  call    cs:__imp_GetBasicProfileFolderPathAlloc
0x180010b3d  mov     rcx, [rbp+5Fh]; this
0x180010b41  test    eax, eax
0x180010b43  js      loc_180010CDD
0x180010b49  cmp     [rbp+57h+var_B0], r12b
0x180010b4d  jz      short loc_180010B86
0x180010b4f  mov     r15, [rbp+57h+var_B8]
0x180010b53  mov     rsi, [rbp+57h+var_C0]
0x180010b57  mov     r14, [rsi]
0x180010b5a  test    r14, r14
0x180010b5d  jz      short loc_180010B83
0x180010b5f  call    cs:__imp_GetLastError
0x180010b65  mov     ebx, eax
0x180010b67  call    cs:__imp_GetProcessHeap
0x180010b6d  mov     rcx, rax; hHeap
0x180010b70  mov     r8, r14; lpMem
0x180010b73  xor     edx, edx; dwFlags
0x180010b75  call    cs:__imp_HeapFree
0x180010b7b  mov     ecx, ebx; dwErrCode
0x180010b7d  call    cs:__imp_SetLastError
0x180010b83  mov     [rsi], r15
0x180010b86  mov     rax, [rbp+57h+lpMem]
0x180010b8a  or      r8, 0FFFFFFFFFFFFFFFFh
0x180010b8e  mov     rdx, r8
0x180010b91  inc     rdx
0x180010b94  cmp     [rax+rdx*2], r12w
0x180010b99  jnz     short loc_180010B91
0x180010b9b  lea     rax, [rdx+2Eh]
0x180010b9f  mov     rsi, r8
0x180010ba2  cmp     rax, rdx
0x180010ba5  cmovnb  rsi, rax
0x180010ba9  sbb     r9d, r9d
0x180010bac  and     r9d, 80070216h; char *
0x180010bb3  mov     rcx, [rbp+5Fh]; this
0x180010bb7  cmp     rax, rdx
0x180010bba  jb      loc_180010CF2
0x180010bc0  mov     eax, 2
0x180010bc5  mul     rsi
0x180010bc8  cmovb   rax, r8
0x180010bcc  mov     rcx, rax; unsigned __int64
0x180010bcf  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180010bd4  mov     rbx, rax
0x180010bd7  mov     [rbp+57h+var_A0], rax
0x180010bdb  mov     r8, [rbp+57h+lpMem]; unsigned __int16 *
0x180010bdf  mov     rdx, rsi; unsigned __int64
0x180010be2  mov     rcx, rax; unsigned __int16 *
0x180010be5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010bea  xorps   xmm0, xmm0
0x180010bed  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x180010bf1  mov     [rbp+57h+var_C8], 26h ; '&'
0x180010bf8  lea     rcx, [rbp+57h+pguid]; pguid
0x180010bfc  call    cs:__imp_CoCreateGuid
0x180010c02  mov     rcx, [rbp+5Fh]; this
0x180010c06  test    eax, eax
0x180010c08  js      loc_180010D04
0x180010c0e  lea     rax, [rbp+57h+var_C8]
0x180010c12  mov     qword ptr [rsp+100h+pcchString], rax; int
0x180010c17  lea     r9, [rbp+57h+pszString]; pszString
0x180010c1b  mov     edx, 10h; cbBinary
0x180010c20  mov     r8d, 4000000Ch; dwFlags
0x180010c26  lea     rcx, [rbp+57h+pguid]; pbBinary
0x180010c2a  call    cs:__imp_CryptBinaryToStringW
0x180010c30  mov     rcx, [rbp+5Fh]; this
0x180010c34  test    eax, eax
0x180010c36  jz      loc_180010D19
0x180010c3c  mov     r9d, 1; dwFlags
0x180010c42  lea     r8, [rbp+57h+pszString]; pszMore
0x180010c46  mov     rdx, rsi; cchPath
0x180010c49  mov     rcx, rbx; pszPath
0x180010c4c  call    cs:__imp_PathCchAppendEx
0x180010c52  mov     rcx, [rbp+5Fh]; this
0x180010c56  test    eax, eax
0x180010c58  js      short loc_180010CC8
0x180010c5a  mov     qword ptr [rdi+18h], 7
0x180010c62  mov     [rdi+10h], r12
0x180010c66  mov     [rdi], r12w
0x180010c6a  mov     rdx, rbx; Src
0x180010c6d  mov     rcx, rdi; void *
0x180010c70  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180010c75  nop
0x180010c76  mov     rcx, rbx
0x180010c79  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180010c7f  nop
0x180010c80  mov     rbx, [rbp+57h+lpMem]
0x180010c84  test    rbx, rbx
0x180010c87  jz      short loc_180010C9D
0x180010c89  call    cs:__imp_GetProcessHeap
0x180010c8f  mov     rcx, rax; hHeap
0x180010c92  mov     r8, rbx; lpMem
0x180010c95  xor     edx, edx; dwFlags
0x180010c97  call    cs:__imp_HeapFree
0x180010c9d  mov     rax, rdi
0x180010ca0  mov     rcx, [rbp+57h+var_30]
0x180010ca4  xor     rcx, rsp; StackCookie
0x180010ca7  call    __security_check_cookie
0x180010cac  lea     r11, [rsp+100h+var_20]
0x180010cb4  mov     rbx, [r11+38h]
0x180010cb8  mov     rsi, [r11+40h]
0x180010cbc  mov     rsp, r11
0x180010cbf  pop     r15
0x180010cc1  pop     r14
0x180010cc3  pop     r12
0x180010cc5  pop     rdi
0x180010cc6  pop     rbp
0x180010cc7  retn
0x180010cc8  mov     r9d, eax; char *
0x180010ccb  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180010cd2  mov     edx, 1Eh; void *
0x180010cd7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010cdd  mov     r9d, eax; char *
0x180010ce0  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180010ce7  mov     edx, 0Ch; void *
0x180010cec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010cf2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180010cf9  mov     edx, 10h; void *
0x180010cfe  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010d04  mov     r9d, eax; char *
0x180010d07  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\lib\\fileutili"...
0x180010d0e  mov     edx, 19h; void *
0x180010d13  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180010d19  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
