# CMetadataPngItxtReaderWriter::ConvertWideCharToMultiByte(ushort *,unsigned __int64,char * *,unsigned __int64 *)

- ea: `0x1800d6530`
- end: `0x1800d66c0`
- name: `?ConvertWideCharToMultiByte@CMetadataPngItxtReaderWriter@@MEAAJPEAG_KPEAPEADPEA_K@Z`
- size: `400`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *this, unsigned __int16 *, int, char **, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800d5e40`
- `0x1800d6250`
- `0x1800d6340`
- `0x1800d6760`

## callees

- `0x1800bd9d4`
- `0x1800d6530`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6588`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6602`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6588`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d6602`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d666d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d6612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d666d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d65aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d65aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d66a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d66a4`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d6577`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d65f2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d6577`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800d65f2`

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
0x1800d6530  mov     rax, rsp
0x1800d6533  push    rbx
0x1800d6534  push    rbp
0x1800d6535  push    rsi
0x1800d6536  push    rdi
0x1800d6537  push    r14
0x1800d6539  push    r15
0x1800d653b  sub     rsp, 48h
0x1800d653f  mov     qword ptr [rax-40h], 0
0x1800d6547  mov     r14, r9
0x1800d654a  mov     qword ptr [rax-48h], 0
0x1800d6552  mov     r9d, r8d; cchWideChar
0x1800d6555  mov     rbp, r8
0x1800d6558  mov     dword ptr [rax-50h], 0
0x1800d655f  mov     r8, rdx; lpWideCharStr
0x1800d6562  mov     qword ptr [rax-58h], 0
0x1800d656a  mov     r15, rdx
0x1800d656d  mov     ecx, 0FDE9h; CodePage
0x1800d6572  mov     edx, 80h; dwFlags
0x1800d6577  call    cs:__imp_WideCharToMultiByte
0x1800d657e  nop     dword ptr [rax+rax+00h]
0x1800d6583  xor     ecx, ecx; dwErrCode
0x1800d6585  movsxd  rsi, eax
0x1800d6588  call    cs:__imp_SetLastError
0x1800d658f  nop     dword ptr [rax+rax+00h]
0x1800d6594  test    esi, esi
0x1800d6596  jz      loc_1800D666B
0x1800d659c  xor     ebx, ebx
0x1800d659e  test    r14, r14
0x1800d65a1  jz      loc_1800D665C
0x1800d65a7  mov     rcx, rsi; cb
0x1800d65aa  call    cs:__imp_CoTaskMemAlloc
0x1800d65b1  nop     dword ptr [rax+rax+00h]
0x1800d65b6  mov     rdi, rax
0x1800d65b9  test    rax, rax
0x1800d65bc  jnz     short loc_1800D65CF
0x1800d65be  mov     ebx, 8007000Eh
0x1800d65c3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d65ca  jmp     loc_1800D6698
0x1800d65cf  mov     [rsp+78h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1800d65d4  mov     r9d, ebp; cchWideChar
0x1800d65d7  mov     [rsp+78h+lpDefaultChar], rbx; lpDefaultChar
0x1800d65dc  mov     r8, r15; lpWideCharStr
0x1800d65df  mov     [rsp+78h+cbMultiByte], esi; cbMultiByte
0x1800d65e3  mov     edx, 80h; dwFlags
0x1800d65e8  mov     ecx, 0FDE9h; CodePage
0x1800d65ed  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800d65f2  call    cs:__imp_WideCharToMultiByte
0x1800d65f9  nop     dword ptr [rax+rax+00h]
0x1800d65fe  xor     ecx, ecx; dwErrCode
0x1800d6600  mov     ebp, eax
0x1800d6602  call    cs:__imp_SetLastError
0x1800d6609  nop     dword ptr [rax+rax+00h]
0x1800d660e  test    ebp, ebp
0x1800d6610  jnz     short loc_1800D6647
0x1800d6612  call    cs:__imp_GetLastError
0x1800d6619  nop     dword ptr [rax+rax+00h]
0x1800d661e  mov     ebx, eax
0x1800d6620  test    eax, eax
0x1800d6622  jle     short loc_1800D662D
0x1800d6624  movzx   ebx, ax
0x1800d6627  or      ebx, 80070000h
0x1800d662d  test    ebx, ebx
0x1800d662f  mov     eax, 88982F94h
0x1800d6634  cmovns  ebx, eax
0x1800d6637  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d663e  jz      short loc_1800D6647
0x1800d6640  mov     ecx, ebx; int
0x1800d6642  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d6647  test    ebx, ebx
0x1800d6649  js      short loc_1800D66A1
0x1800d664b  cmp     ebp, esi
0x1800d664d  jz      short loc_1800D6659
0x1800d664f  mov     ebx, 88982F63h
0x1800d6654  jmp     loc_1800D65C3
0x1800d6659  mov     [r14], rdi
0x1800d665c  mov     rax, [rsp+78h+arg_20]
0x1800d6664  xor     edi, edi
0x1800d6666  mov     [rax], rsi
0x1800d6669  jmp     short loc_1800D66A1
0x1800d666b  xor     edi, edi
0x1800d666d  call    cs:__imp_GetLastError
0x1800d6674  nop     dword ptr [rax+rax+00h]
0x1800d6679  mov     ebx, eax
0x1800d667b  test    eax, eax
0x1800d667d  jle     short loc_1800D6688
0x1800d667f  movzx   ebx, ax
0x1800d6682  or      ebx, 80070000h
0x1800d6688  test    ebx, ebx
0x1800d668a  mov     eax, 88982F94h
0x1800d668f  cmovns  ebx, eax
0x1800d6692  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1800d6698  jz      short loc_1800D66A1
0x1800d669a  mov     ecx, ebx; int
0x1800d669c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d66a1  mov     rcx, rdi; pv
0x1800d66a4  call    cs:__imp_CoTaskMemFree
0x1800d66ab  nop     dword ptr [rax+rax+00h]
0x1800d66b0  mov     eax, ebx
0x1800d66b2  add     rsp, 48h
0x1800d66b6  pop     r15
0x1800d66b8  pop     r14
0x1800d66ba  pop     rdi
0x1800d66bb  pop     rsi
0x1800d66bc  pop     rbp
0x1800d66bd  pop     rbx
0x1800d66be  retn
```
