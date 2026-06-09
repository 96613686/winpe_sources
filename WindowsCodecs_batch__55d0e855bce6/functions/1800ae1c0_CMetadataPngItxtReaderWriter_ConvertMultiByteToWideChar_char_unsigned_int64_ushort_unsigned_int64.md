# CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(char *,unsigned __int64,ushort * *,unsigned __int64 *)

- ea: `0x1800ae1c0`
- end: `0x1800ae318`
- name: `?ConvertMultiByteToWideChar@CMetadataPngItxtReaderWriter@@MEAAJPEAD_KPEAPEAGPEA_K@Z`
- size: `344`
- prototype: `int(CMetadataPngItxtReaderWriter *__hidden this, char *, unsigned __int64, unsigned __int16 **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800c5020`
- `0x1801b1670`

## callees

- `0x1800ae1c0`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae208`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800ae208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae218`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae218`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800ae271`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae2c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ae2c6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ae1f7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ae29e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ae1f7`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800ae29e`

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
0x1800ae1c0  push    rbx
0x1800ae1c2  push    rbp
0x1800ae1c3  push    rsi
0x1800ae1c4  push    rdi
0x1800ae1c5  push    r14
0x1800ae1c7  push    r15
0x1800ae1c9  sub     rsp, 48h
0x1800ae1cd  mov     r14, r9
0x1800ae1d0  mov     [rsp+78h+cchWideChar], 0; cchWideChar
0x1800ae1d8  mov     r9d, r8d; cbMultiByte
0x1800ae1db  mov     [rsp+78h+lpWideCharStr], 0; lpWideCharStr
0x1800ae1e4  mov     rbp, r8
0x1800ae1e7  mov     r15, rdx
0x1800ae1ea  mov     r8, rdx; lpMultiByteStr
0x1800ae1ed  mov     ecx, 0FDE9h; CodePage
0x1800ae1f2  mov     edx, 8; dwFlags
0x1800ae1f7  call    cs:__imp_MultiByteToWideChar
0x1800ae1fe  nop     dword ptr [rax+rax+00h]
0x1800ae203  xor     ecx, ecx; dwErrCode
0x1800ae205  movsxd  rsi, eax
0x1800ae208  call    cs:__imp_SetLastError
0x1800ae20f  nop     dword ptr [rax+rax+00h]
0x1800ae214  test    esi, esi
0x1800ae216  jnz     short loc_1800AE242
0x1800ae218  call    cs:__imp_GetLastError
0x1800ae21f  nop     dword ptr [rax+rax+00h]
0x1800ae224  mov     ebx, eax
0x1800ae226  test    eax, eax
0x1800ae228  jle     short loc_1800AE233
0x1800ae22a  movzx   ebx, ax
0x1800ae22d  or      ebx, 80070000h
0x1800ae233  test    ebx, ebx
0x1800ae235  mov     eax, 88982F94h
0x1800ae23a  cmovns  ebx, eax
0x1800ae23d  jmp     loc_1800AE2E7
0x1800ae242  test    r14, r14
0x1800ae245  jz      loc_1800AE309
0x1800ae24b  lea     rcx, [rsi+1]
0x1800ae24f  cmp     rcx, rsi
0x1800ae252  jb      loc_1800AE2E2
0x1800ae258  mov     eax, 2
0x1800ae25d  mov     [rsp+78h+var_48], 0
0x1800ae266  mul     rcx
0x1800ae269  test    rdx, rdx
0x1800ae26c  jnz     short loc_1800AE2E2
0x1800ae26e  mov     rcx, rax; cb
0x1800ae271  call    cs:__imp_CoTaskMemAlloc
0x1800ae278  nop     dword ptr [rax+rax+00h]
0x1800ae27d  mov     rdi, rax
0x1800ae280  test    rax, rax
0x1800ae283  jz      short loc_1800AE2F9
0x1800ae285  mov     [rsp+78h+cchWideChar], esi; cchWideChar
0x1800ae289  mov     r9d, ebp; cbMultiByte
0x1800ae28c  mov     r8, r15; lpMultiByteStr
0x1800ae28f  mov     [rsp+78h+lpWideCharStr], rax; lpWideCharStr
0x1800ae294  mov     edx, 8; dwFlags
0x1800ae299  mov     ecx, 0FDE9h; CodePage
0x1800ae29e  call    cs:__imp_MultiByteToWideChar
0x1800ae2a5  nop     dword ptr [rax+rax+00h]
0x1800ae2aa  cmp     esi, eax
0x1800ae2ac  jz      short loc_1800AE300
0x1800ae2ae  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ae2b5  mov     ebx, 88982F63h
0x1800ae2ba  jz      short loc_1800AE2C3
0x1800ae2bc  mov     ecx, ebx; int
0x1800ae2be  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ae2c3  mov     rcx, rdi; pv
0x1800ae2c6  call    cs:__imp_CoTaskMemFree
0x1800ae2cd  nop     dword ptr [rax+rax+00h]
0x1800ae2d2  mov     eax, ebx
0x1800ae2d4  add     rsp, 48h
0x1800ae2d8  pop     r15
0x1800ae2da  pop     r14
0x1800ae2dc  pop     rdi
0x1800ae2dd  pop     rsi
0x1800ae2de  pop     rbp
0x1800ae2df  pop     rbx
0x1800ae2e0  retn
0x1800ae2e2  mov     ebx, 80070216h
0x1800ae2e7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800ae2ee  jz      short loc_1800AE2D2
0x1800ae2f0  mov     ecx, ebx; int
0x1800ae2f2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800ae2f7  jmp     short loc_1800AE2D2
0x1800ae2f9  mov     ebx, 8007000Eh
0x1800ae2fe  jmp     short loc_1800AE2E7
0x1800ae300  xor     eax, eax
0x1800ae302  mov     [rdi+rsi*2], ax
0x1800ae306  mov     [r14], rdi
0x1800ae309  mov     rcx, [rsp+78h+arg_20]
0x1800ae311  xor     ebx, ebx
0x1800ae313  mov     [rcx], rsi
0x1800ae316  jmp     short loc_1800AE2D2
```
