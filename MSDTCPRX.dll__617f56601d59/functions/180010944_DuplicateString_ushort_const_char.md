# DuplicateString(ushort const *,char * *)

- ea: `0x180010944`
- end: `0x180010a1f`
- name: `?DuplicateString@@YAJPEBGPEAPEAD@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180075dbc`
- `0x180077430`

## callees

- `0x18000d5f4`
- `0x180010944`
- `0x18001156c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010990`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800109df`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800109df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e9`

## string_xrefs

- `0x1800109b0`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x1800109a3`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`
- `0x18001095f`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@190): DuplicateString, ppszDest != NULL`

## pseudocode

```c
__int64 __fastcall DuplicateString(LPCWCH lpWideCharStr, char **a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // rax
  char *v8; // rbp
  unsigned __int16 *v9; // rdx
  unsigned int v10; // r9d
  signed int LastError; // eax

  if ( !a2 )
    DtcInternalErrorW(L"DuplicateString (com\\complus\\dtc\\shared\\util\\stringutil.cpp@190): DuplicateString, ppszDest != NULL");
  *a2 = 0;
  v4 = 0;
  if ( lpWideCharStr )
  {
    v5 = -1;
    do
      ++v5;
    while ( lpWideCharStr[v5] );
    cbMultiByte = v5 + 1;
    lpMultiByteStr = (CHAR *)CoTaskMemAlloc((unsigned int)(v5 + 1));
    v8 = lpMultiByteStr;
    if ( lpMultiByteStr )
    {
      if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
      {
        *a2 = v8;
        return v4;
      }
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      v10 = 215;
      v9 = L"DuplicateString, MultiByteToWideChar failed";
    }
    else
    {
      v4 = -2147024882;
      v9 = L"DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed";
      v10 = 202;
    }
    TraceFileW(v4, v9, L"com\\complus\\dtc\\shared\\util\\stringutil.cpp", v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180010944  push    rbx
0x180010946  push    rbp
0x180010947  push    rsi
0x180010948  push    rdi
0x180010949  push    r14
0x18001094b  push    r15
0x18001094d  sub     rsp, 48h
0x180010951  xor     r15d, r15d
0x180010954  mov     rdi, rdx
0x180010957  mov     rsi, rcx
0x18001095a  test    rdx, rdx
0x18001095d  jnz     short loc_18001096C
0x18001095f  lea     rcx, aDuplicatestrin_2; "DuplicateString (com\\complus\\dtc\\sha"...
0x180010966  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001096c  mov     [rdx], r15
0x18001096f  mov     ebx, r15d
0x180010972  test    rsi, rsi
0x180010975  jz      loc_180010A10
0x18001097b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001097f  inc     rax
0x180010982  cmp     [rcx+rax*2], r15w
0x180010987  jnz     short loc_18001097F
0x180010989  lea     r14d, [rax+1]
0x18001098d  mov     ecx, r14d; cb
0x180010990  call    cs:__imp_CoTaskMemAlloc
0x180010996  mov     rbp, rax
0x180010999  test    rax, rax
0x18001099c  jnz     short loc_1800109C0
0x18001099e  mov     ebx, 8007000Eh
0x1800109a3  lea     rdx, aDuplicatestrin_3; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x1800109aa  mov     r9d, 0CAh; unsigned int
0x1800109b0  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x1800109b7  mov     ecx, ebx; int
0x1800109b9  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800109be  jmp     short loc_180010A10
0x1800109c0  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800109c5  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800109c9  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x1800109ce  mov     r8, rsi; lpWideCharStr
0x1800109d1  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1800109d6  xor     edx, edx; dwFlags
0x1800109d8  xor     ecx, ecx; CodePage
0x1800109da  mov     [rsp+78h+lpMultiByteStr], rbp; lpMultiByteStr
0x1800109df  call    cs:__imp_WideCharToMultiByte
0x1800109e5  test    eax, eax
0x1800109e7  jnz     short loc_180010A0D
0x1800109e9  call    cs:__imp_GetLastError
0x1800109ef  mov     ebx, eax
0x1800109f1  test    eax, eax
0x1800109f3  jle     short loc_1800109FE
0x1800109f5  movzx   ebx, ax
0x1800109f8  or      ebx, 80070000h
0x1800109fe  mov     r9d, 0D7h
0x180010a04  lea     rdx, aDuplicatestrin_0; "DuplicateString, MultiByteToWideChar fa"...
0x180010a0b  jmp     short loc_1800109B0
0x180010a0d  mov     [rdi], rbp
0x180010a10  mov     eax, ebx
0x180010a12  add     rsp, 48h
0x180010a16  pop     r15
0x180010a18  pop     r14
0x180010a1a  pop     rdi
0x180010a1b  pop     rsi
0x180010a1c  pop     rbp
0x180010a1d  pop     rbx
0x180010a1e  retn
```
