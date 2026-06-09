# DuplicateString(ushort const *,char * *)

- ea: `0x18002003c`
- end: `0x180020117`
- name: `?DuplicateString@@YAJPEBGPEAPEAD@Z`
- size: `219`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e1b8`

## callees

- `0x18002003c`
- `0x1800206c4`
- `0x1800846c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180020088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800200e1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800200d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800200d7`

## string_xrefs

- `0x1800200a8`: `com\complus\dtc\shared\util\stringutil.cpp`
- `0x18002009b`: `DuplicateString, CoTaskMemAlloc(dwSourceLength * sizeof(WCHAR)) failed`
- `0x180020057`: `DuplicateString (com\complus\dtc\shared\util\stringutil.cpp@190): DuplicateString, ppszDest != NULL`

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
0x18002003c  push    rbx
0x18002003e  push    rbp
0x18002003f  push    rsi
0x180020040  push    rdi
0x180020041  push    r14
0x180020043  push    r15
0x180020045  sub     rsp, 48h
0x180020049  xor     r15d, r15d
0x18002004c  mov     rdi, rdx
0x18002004f  mov     rsi, rcx
0x180020052  test    rdx, rdx
0x180020055  jnz     short loc_180020064
0x180020057  lea     rcx, aDuplicatestrin_0; "DuplicateString (com\\complus\\dtc\\sha"...
0x18002005e  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x180020064  mov     [rdx], r15
0x180020067  mov     ebx, r15d
0x18002006a  test    rsi, rsi
0x18002006d  jz      loc_180020108
0x180020073  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020077  inc     rax
0x18002007a  cmp     [rcx+rax*2], r15w
0x18002007f  jnz     short loc_180020077
0x180020081  lea     r14d, [rax+1]
0x180020085  mov     ecx, r14d; cb
0x180020088  call    cs:__imp_CoTaskMemAlloc
0x18002008e  mov     rbp, rax
0x180020091  test    rax, rax
0x180020094  jnz     short loc_1800200B8
0x180020096  mov     ebx, 8007000Eh
0x18002009b  lea     rdx, aDuplicatestrin_1; "DuplicateString, CoTaskMemAlloc(dwSourc"...
0x1800200a2  mov     r9d, 0CAh; unsigned int
0x1800200a8  lea     r8, aComComplusDtcS_0; "com\\complus\\dtc\\shared\\util\\string"...
0x1800200af  mov     ecx, ebx; int
0x1800200b1  call    ?TraceFileW@@YAXJPEAGPEBGI@Z; TraceFileW(long,ushort *,ushort const *,uint)
0x1800200b6  jmp     short loc_180020108
0x1800200b8  mov     [rsp+78h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1800200bd  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800200c1  mov     [rsp+78h+lpDefaultChar], r15; lpDefaultChar
0x1800200c6  mov     r8, rsi; lpWideCharStr
0x1800200c9  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1800200ce  xor     edx, edx; dwFlags
0x1800200d0  xor     ecx, ecx; CodePage
0x1800200d2  mov     [rsp+78h+lpMultiByteStr], rbp; lpMultiByteStr
0x1800200d7  call    cs:__imp_WideCharToMultiByte
0x1800200dd  test    eax, eax
0x1800200df  jnz     short loc_180020105
0x1800200e1  call    cs:__imp_GetLastError
0x1800200e7  mov     ebx, eax
0x1800200e9  test    eax, eax
0x1800200eb  jle     short loc_1800200F6
0x1800200ed  movzx   ebx, ax
0x1800200f0  or      ebx, 80070000h
0x1800200f6  mov     r9d, 0D7h
0x1800200fc  lea     rdx, aDuplicatestrin; "DuplicateString, MultiByteToWideChar fa"...
0x180020103  jmp     short loc_1800200A8
0x180020105  mov     [rdi], rbp
0x180020108  mov     eax, ebx
0x18002010a  add     rsp, 48h
0x18002010e  pop     r15
0x180020110  pop     r14
0x180020112  pop     rdi
0x180020113  pop     rsi
0x180020114  pop     rbp
0x180020115  pop     rbx
0x180020116  retn
```
