# CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(char *,unsigned __int64,ushort * *,unsigned __int64 *)

- ea: `0x1800ac1f0`
- end: `0x1800ac31f`
- name: `?ConvertMultiByteToWideChar@CMetadataPngItxtReaderWriter@@MEAAJPEAD_KPEAPEAGPEA_K@Z`
- size: `303`
- prototype: `int(CMetadataPngItxtReaderWriter *__hidden this, char *, unsigned __int64, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c2c80`
- `0x1801ae050`

## callees

- `0x1800ac1f0`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ac232`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ac232`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac23c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ac28b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac2d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ac2d4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ac227`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ac2b2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ac227`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ac2b2`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(
        CMetadataPngItxtReaderWriter *this,
        char *a2,
        int a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 cchWideChar; // rsi
  signed int LastError; // eax
  unsigned int v10; // ebx
  unsigned __int64 v11; // rcx
  WCHAR *lpWideCharStr; // rax
  unsigned __int16 *v13; // rdi

  cchWideChar = MultiByteToWideChar(0xFDE9u, 8u, a2, a3, 0, 0);
  SetLastError(0);
  if ( !(_DWORD)cchWideChar )
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    if ( (v10 & 0x80000000) == 0 )
      v10 = -2003292268;
    goto LABEL_17;
  }
  if ( !a4 )
  {
LABEL_21:
    v10 = 0;
    *a5 = cchWideChar;
    return v10;
  }
  v11 = cchWideChar + 1;
  if ( cchWideChar + 1 < cchWideChar || !is_mul_ok(v11, 2u) )
  {
    v10 = -2147024362;
    goto LABEL_17;
  }
  lpWideCharStr = (WCHAR *)CoTaskMemAlloc(2 * v11);
  v13 = lpWideCharStr;
  if ( !lpWideCharStr )
  {
    v10 = -2147024882;
LABEL_17:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v10);
    return v10;
  }
  if ( (_DWORD)cchWideChar == MultiByteToWideChar(0xFDE9u, 8u, a2, a3, lpWideCharStr, cchWideChar) )
  {
    v13[cchWideChar] = 0;
    *a4 = v13;
    goto LABEL_21;
  }
  v10 = -2003292317;
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(-2003292317);
  CoTaskMemFree(v13);
  return v10;
}

```

## disassembly

```asm
0x1800ac1f0  push    rbx
0x1800ac1f2  push    rbp
0x1800ac1f3  push    rsi
0x1800ac1f4  push    rdi
0x1800ac1f5  push    r14
0x1800ac1f7  push    r15
0x1800ac1f9  sub     rsp, 48h
0x1800ac1fd  mov     r14, r9
0x1800ac200  mov     [rsp+78h+cchWideChar], 0; cchWideChar
0x1800ac208  mov     r9d, r8d; cbMultiByte
0x1800ac20b  mov     [rsp+78h+lpWideCharStr], 0; lpWideCharStr
0x1800ac214  mov     rbp, r8
0x1800ac217  mov     r15, rdx
0x1800ac21a  mov     r8, rdx; lpMultiByteStr
0x1800ac21d  mov     ecx, 0FDE9h; CodePage
0x1800ac222  mov     edx, 8; dwFlags
0x1800ac227  call    cs:__imp_MultiByteToWideChar
0x1800ac22d  xor     ecx, ecx; dwErrCode
0x1800ac22f  movsxd  rsi, eax
0x1800ac232  call    cs:__imp_SetLastError
0x1800ac238  test    esi, esi
0x1800ac23a  jnz     short loc_1800AC260
0x1800ac23c  call    cs:__imp_GetLastError
0x1800ac242  mov     ebx, eax
0x1800ac244  test    eax, eax
0x1800ac246  jle     short loc_1800AC251
0x1800ac248  movzx   ebx, ax
0x1800ac24b  or      ebx, 80070000h
0x1800ac251  test    ebx, ebx
0x1800ac253  mov     eax, 88982F94h
0x1800ac258  cmovns  ebx, eax
0x1800ac25b  jmp     loc_1800AC2EE
0x1800ac260  test    r14, r14
0x1800ac263  jz      loc_1800AC310
0x1800ac269  lea     rcx, [rsi+1]
0x1800ac26d  cmp     rcx, rsi
0x1800ac270  jb      short loc_1800AC2E9
0x1800ac272  mov     eax, 2
0x1800ac277  mov     [rsp+78h+var_48], 0
0x1800ac280  mul     rcx
0x1800ac283  test    rdx, rdx
0x1800ac286  jnz     short loc_1800AC2E9
0x1800ac288  mov     rcx, rax; cb
0x1800ac28b  call    cs:__imp_CoTaskMemAlloc
0x1800ac291  mov     rdi, rax
0x1800ac294  test    rax, rax
0x1800ac297  jz      short loc_1800AC300
0x1800ac299  mov     [rsp+78h+cchWideChar], esi; cchWideChar
0x1800ac29d  mov     r9d, ebp; cbMultiByte
0x1800ac2a0  mov     r8, r15; lpMultiByteStr
0x1800ac2a3  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x1800ac2a8  mov     edx, 8; dwFlags
0x1800ac2ad  mov     ecx, 0FDE9h; CodePage
0x1800ac2b2  call    cs:__imp_MultiByteToWideChar
0x1800ac2b8  cmp     esi, eax
0x1800ac2ba  jz      short loc_1800AC307
0x1800ac2bc  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ac2c3  mov     ebx, 88982F63h
0x1800ac2c8  jz      short loc_1800AC2D1
0x1800ac2ca  mov     ecx, ebx; int
0x1800ac2cc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ac2d1  mov     rcx, rdi; pv
0x1800ac2d4  call    cs:__imp_CoTaskMemFree
0x1800ac2da  mov     eax, ebx
0x1800ac2dc  add     rsp, 48h
0x1800ac2e0  pop     r15
0x1800ac2e2  pop     r14
0x1800ac2e4  pop     rdi
0x1800ac2e5  pop     rsi
0x1800ac2e6  pop     rbp
0x1800ac2e7  pop     rbx
0x1800ac2e8  retn
0x1800ac2e9  mov     ebx, 80070216h
0x1800ac2ee  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ac2f5  jz      short loc_1800AC2DA
0x1800ac2f7  mov     ecx, ebx; int
0x1800ac2f9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ac2fe  jmp     short loc_1800AC2DA
0x1800ac300  mov     ebx, 8007000Eh
0x1800ac305  jmp     short loc_1800AC2EE
0x1800ac307  xor     eax, eax
0x1800ac309  mov     [rdi+rsi*2], ax
0x1800ac30d  mov     [r14], rdi
0x1800ac310  mov     rcx, [rsp+78h+arg_20]
0x1800ac318  xor     ebx, ebx
0x1800ac31a  mov     [rcx], rsi
0x1800ac31d  jmp     short loc_1800AC2DA
```
