# CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)

- ea: `0x1800d3b60`
- end: `0x1800d3cbf`
- name: `?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z`
- size: `351`
- prototype: `int(CMetadataPngItxtReaderWriter *__hidden this, unsigned __int16 *, unsigned __int64, char **, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d3480`
- `0x1800d3890`
- `0x1800d3980`
- `0x1800d3d60`

## callees

- `0x1800bb784`
- `0x1800d3b60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3bb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3c1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3bb2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d3c1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d3c79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d3bce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3caa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d3caa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d3ba7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d3c10`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d3ba7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d3c10`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(
        CMetadataPngItxtReaderWriter *this,
        unsigned __int16 *a2,
        int a3,
        char **a4,
        unsigned __int64 *a5)
{
  unsigned __int64 cbMultiByte; // rsi
  signed int v9; // ebx
  CHAR *lpMultiByteStr; // rax
  char *v11; // rdi
  bool v12; // zf
  int v13; // ebp
  signed int v14; // eax
  signed int LastError; // eax

  cbMultiByte = WideCharToMultiByte(0xFDE9u, 0x80u, a2, a3, 0, 0, 0, 0);
  SetLastError(0);
  if ( !(_DWORD)cbMultiByte )
  {
    v11 = 0;
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2003292268;
    v12 = (_DWORD)g_doStackCaptures == 0;
    goto LABEL_23;
  }
  v9 = 0;
  if ( !a4 )
    goto LABEL_17;
  lpMultiByteStr = (CHAR *)CoTaskMemAlloc(cbMultiByte);
  v11 = lpMultiByteStr;
  if ( !lpMultiByteStr )
  {
    v9 = -2147024882;
LABEL_5:
    v12 = (_DWORD)g_doStackCaptures == 0;
LABEL_23:
    if ( !v12 )
      DoStackCapture(v9);
    goto LABEL_25;
  }
  v13 = WideCharToMultiByte(0xFDE9u, 0x80u, a2, a3, lpMultiByteStr, cbMultiByte, 0, 0);
  SetLastError(0);
  if ( !v13 )
  {
    v14 = GetLastError();
    v9 = v14;
    if ( v14 > 0 )
      v9 = (unsigned __int16)v14 | 0x80070000;
    if ( v9 >= 0 )
      v9 = -2003292268;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(v9);
  }
  if ( v9 >= 0 )
  {
    if ( v13 != (_DWORD)cbMultiByte )
    {
      v9 = -2003292317;
      goto LABEL_5;
    }
    *a4 = v11;
LABEL_17:
    v11 = 0;
    *a5 = cbMultiByte;
  }
LABEL_25:
  CoTaskMemFree(v11);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800d3b60  mov     rax, rsp
0x1800d3b63  push    rbx
0x1800d3b64  push    rbp
0x1800d3b65  push    rsi
0x1800d3b66  push    rdi
0x1800d3b67  push    r14
0x1800d3b69  push    r15
0x1800d3b6b  sub     rsp, 48h
0x1800d3b6f  mov     qword ptr [rax-40h], 0
0x1800d3b77  mov     r14, r9
0x1800d3b7a  mov     qword ptr [rax-48h], 0
0x1800d3b82  mov     r9d, r8d; cchWideChar
0x1800d3b85  mov     rbp, r8
0x1800d3b88  mov     dword ptr [rax-50h], 0
0x1800d3b8f  mov     r8, rdx; lpWideCharStr
0x1800d3b92  mov     qword ptr [rax-58h], 0
0x1800d3b9a  mov     r15, rdx
0x1800d3b9d  mov     ecx, 0FDE9h; CodePage
0x1800d3ba2  mov     edx, 80h; dwFlags
0x1800d3ba7  call    cs:__imp_WideCharToMultiByte
0x1800d3bad  xor     ecx, ecx; dwErrCode
0x1800d3baf  movsxd  rsi, eax
0x1800d3bb2  call    cs:__imp_SetLastError
0x1800d3bb8  test    esi, esi
0x1800d3bba  jz      loc_1800D3C77
0x1800d3bc0  xor     ebx, ebx
0x1800d3bc2  test    r14, r14
0x1800d3bc5  jz      loc_1800D3C68
0x1800d3bcb  mov     rcx, rsi; cb
0x1800d3bce  call    cs:__imp_CoTaskMemAlloc
0x1800d3bd4  mov     rdi, rax
0x1800d3bd7  test    rax, rax
0x1800d3bda  jnz     short loc_1800D3BED
0x1800d3bdc  mov     ebx, 8007000Eh
0x1800d3be1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d3be8  jmp     loc_1800D3C9E
0x1800d3bed  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1800d3bf2  mov     r9d, ebp; cchWideChar
0x1800d3bf5  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x1800d3bfa  mov     r8, r15; lpWideCharStr
0x1800d3bfd  mov     [rsp+78h+cbMultiByte], esi; cbMultiByte
0x1800d3c01  mov     edx, 80h; dwFlags
0x1800d3c06  mov     ecx, 0FDE9h; CodePage
0x1800d3c0b  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800d3c10  call    cs:__imp_WideCharToMultiByte
0x1800d3c16  xor     ecx, ecx; dwErrCode
0x1800d3c18  mov     ebp, eax
0x1800d3c1a  call    cs:__imp_SetLastError
0x1800d3c20  test    ebp, ebp
0x1800d3c22  jnz     short loc_1800D3C53
0x1800d3c24  call    cs:__imp_GetLastError
0x1800d3c2a  mov     ebx, eax
0x1800d3c2c  test    eax, eax
0x1800d3c2e  jle     short loc_1800D3C39
0x1800d3c30  movzx   ebx, ax
0x1800d3c33  or      ebx, 80070000h
0x1800d3c39  test    ebx, ebx
0x1800d3c3b  mov     eax, 88982F94h
0x1800d3c40  cmovns  ebx, eax
0x1800d3c43  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d3c4a  jz      short loc_1800D3C53
0x1800d3c4c  mov     ecx, ebx; int
0x1800d3c4e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3c53  test    ebx, ebx
0x1800d3c55  js      short loc_1800D3CA7
0x1800d3c57  cmp     ebp, esi
0x1800d3c59  jz      short loc_1800D3C65
0x1800d3c5b  mov     ebx, 88982F63h
0x1800d3c60  jmp     loc_1800D3BE1
0x1800d3c65  mov     [r14], rdi
0x1800d3c68  mov     rax, [rsp+78h+arg_20]
0x1800d3c70  xor     edi, edi
0x1800d3c72  mov     [rax], rsi
0x1800d3c75  jmp     short loc_1800D3CA7
0x1800d3c77  xor     edi, edi
0x1800d3c79  call    cs:__imp_GetLastError
0x1800d3c7f  mov     ebx, eax
0x1800d3c81  test    eax, eax
0x1800d3c83  jle     short loc_1800D3C8E
0x1800d3c85  movzx   ebx, ax
0x1800d3c88  or      ebx, 80070000h
0x1800d3c8e  test    ebx, ebx
0x1800d3c90  mov     eax, 88982F94h
0x1800d3c95  cmovns  ebx, eax
0x1800d3c98  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d3c9e  jz      short loc_1800D3CA7
0x1800d3ca0  mov     ecx, ebx; int
0x1800d3ca2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d3ca7  mov     rcx, rdi; pv
0x1800d3caa  call    cs:__imp_CoTaskMemFree
0x1800d3cb0  mov     eax, ebx
0x1800d3cb2  add     rsp, 48h
0x1800d3cb6  pop     r15
0x1800d3cb8  pop     r14
0x1800d3cba  pop     rdi
0x1800d3cbb  pop     rsi
0x1800d3cbc  pop     rbp
0x1800d3cbd  pop     rbx
0x1800d3cbe  retn
```
