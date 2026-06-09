# PARSTloadIncludeFile

- ea: `0x180047da0`
- end: `0x180047f4c`
- name: `PARSTloadIncludeFile`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d1d8`

## callees

- `0x180007220`
- `0x180009f84`
- `0x18000ca18`
- `0x180024718`
- `0x180033504`
- `0x18003e6f0`
- `0x180047da0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047e80`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180047e80`
- `KERNEL32!LocalFree` at `0x180047f05`
- `KERNEL32!LocalFree` at `0x180047f13`
- `KERNEL32!LocalFree` at `0x180047f05`
- `KERNEL32!LocalFree` at `0x180047f13`
- `KERNEL32!LocalAlloc` at `0x180047e5c`
- `KERNEL32!LocalAlloc` at `0x180047e5c`

## string_xrefs

- `0x180047eb9`: `Internal Error: Must specify fully qualified path to Root GPD file.`

## pseudocode

```c
__int64 __fastcall PARSTloadIncludeFile(unsigned int *a1, const wchar_t *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  wchar_t *v7; // rbp
  unsigned int v8; // ebx
  __int64 v9; // rax
  wchar_t *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // ecx
  __int64 v13; // rbx
  wchar_t *v14; // rax
  wchar_t *v15; // rax
  __int64 v17; // [rsp+50h] [rbp+8h] BYREF

  v3 = 56LL * *a1;
  v4 = *(_QWORD *)(a3 + 480);
  v17 = 0;
  if ( (*(_BYTE *)(v3 + v4 + 52) & 1) == 0 && (unsigned int)BparseString(v4 + 24 + v3, &v17) )
  {
    v7 = (wchar_t *)PwstrAnsiToUnicode((LPCCH)(*(_QWORD *)a3 + HIDWORD(v17)));
    if ( !v7 )
      return 6;
    v9 = -1;
    v10 = 0;
    v11 = -1;
    do
      ++v11;
    while ( v7[v11] );
    do
      ++v9;
    while ( a2[v9] );
    v12 = v9 + v11;
    if ( v12 < (unsigned int)v9 || (v13 = v12 + 1, (unsigned int)v13 < v12) )
    {
      LODWORD(v13) = -1;
    }
    else if ( (unsigned __int64)(2 * v13) <= 0xFFFFFFFF )
    {
      v14 = (wchar_t *)LocalAlloc(0, (unsigned int)(2 * v13));
      v10 = v14;
      if ( v14 )
      {
        StringCchCopyW(v14, (unsigned int)v13, a2);
        v15 = wcsrchr(v10, 0x5Cu);
        if ( v15 )
        {
          v15[1] = 0;
          StringCchCatW(v10, (unsigned int)v13, v7);
          v8 = (unsigned int)BloadFile(v10, a3) != 0 ? 2 : 6;
          goto LABEL_18;
        }
        WriteDbgTraceErrorGpd(
          (__int64)"PARSTloadIncludeFile",
          "Internal Error: Must specify fully qualified path to Root GPD file.");
LABEL_17:
        v8 = 6;
LABEL_18:
        LocalFree(v7);
        if ( v10 )
          LocalFree(v10);
        return v8;
      }
    }
    WriteDbgTraceErrorGpd((__int64)"PARSTloadIncludeFile", "Fatal: unable to alloc requested memory: %d WCHARs.", v13);
    *(_DWORD *)(a3 + 2224) = 2;
    *(_DWORD *)(a3 + 2220) = 3;
    goto LABEL_17;
  }
  WriteDbgTraceErrorGpd((__int64)"PARSTloadIncludeFile", "syntax error in filename for *Include keyword.");
  return 6;
}

```

## disassembly

```asm
0x180047da0  mov     r11, rsp
0x180047da3  mov     [r11+10h], rbx
0x180047da7  mov     [r11+18h], rbp
0x180047dab  push    rsi
0x180047dac  push    rdi
0x180047dad  push    r12
0x180047daf  push    r14
0x180047db1  push    r15
0x180047db3  sub     rsp, 20h
0x180047db7  mov     eax, [rcx]
0x180047db9  xor     r12d, r12d
0x180047dbc  imul    rcx, rax, 38h ; '8'
0x180047dc0  mov     rax, [r8+1E0h]
0x180047dc7  mov     rsi, r8
0x180047dca  mov     r15, rdx
0x180047dcd  mov     [r11+8], r12
0x180047dd1  test    byte ptr [rcx+rax+34h], 1
0x180047dd6  jnz     loc_180047F1D
0x180047ddc  add     rax, 18h
0x180047de0  lea     rdx, [r11+8]
0x180047de4  add     rcx, rax
0x180047de7  call    BparseString
0x180047dec  test    eax, eax
0x180047dee  jz      loc_180047F1D
0x180047df4  mov     ecx, [rsp+48h+arg_4]
0x180047df8  mov     rdx, rsi
0x180047dfb  add     rcx, [rsi]; lpMultiByteStr
0x180047dfe  call    PwstrAnsiToUnicode
0x180047e03  mov     rbp, rax
0x180047e06  test    rax, rax
0x180047e09  jnz     short loc_180047E13
0x180047e0b  lea     ebx, [rax+6]
0x180047e0e  jmp     loc_180047F19
0x180047e13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180047e17  mov     rdi, r12
0x180047e1a  mov     rcx, rax
0x180047e1d  inc     rcx
0x180047e20  cmp     [rbp+rcx*2+0], r12w
0x180047e26  jnz     short loc_180047E1D
0x180047e28  inc     rax
0x180047e2b  cmp     [r15+rax*2], r12w
0x180047e30  jnz     short loc_180047E28
0x180047e32  add     ecx, eax
0x180047e34  cmp     ecx, eax
0x180047e36  jb      loc_180047ECE
0x180047e3c  lea     ebx, [rcx+1]
0x180047e3f  cmp     ebx, ecx
0x180047e41  jb      loc_180047ECE
0x180047e47  lea     rcx, [rbx+rbx]
0x180047e4b  mov     r14d, ebx
0x180047e4e  mov     eax, 0FFFFFFFFh
0x180047e53  cmp     rcx, rax
0x180047e56  ja      short loc_180047ED3
0x180047e58  mov     edx, ecx; uBytes
0x180047e5a  xor     ecx, ecx; uFlags
0x180047e5c  call    cs:__imp_LocalAlloc
0x180047e62  mov     rdi, rax
0x180047e65  test    rax, rax
0x180047e68  jz      short loc_180047ED3
0x180047e6a  mov     r8, r15; pszSrc
0x180047e6d  mov     edx, r14d; cchDest
0x180047e70  mov     rcx, rax; pszDest
0x180047e73  call    StringCchCopyW
0x180047e78  mov     edx, 5Ch ; '\'; Ch
0x180047e7d  mov     rcx, rdi; Str
0x180047e80  call    cs:__imp_wcsrchr
0x180047e86  test    rax, rax
0x180047e89  jz      short loc_180047EB9
0x180047e8b  mov     r8, rbp; pszSrc
0x180047e8e  mov     [rax+2], r12w
0x180047e93  mov     edx, r14d; cchDest
0x180047e96  mov     rcx, rdi; pszDest
0x180047e99  call    StringCchCatW
0x180047e9e  mov     rdx, rsi
0x180047ea1  mov     rcx, rdi; pszSrc
0x180047ea4  call    BloadFile
0x180047ea9  neg     eax
0x180047eab  mov     ebx, 6
0x180047eb0  sbb     ecx, ecx
0x180047eb2  and     ecx, 0FFFFFFFCh
0x180047eb5  add     ebx, ecx
0x180047eb7  jmp     short loc_180047F02
0x180047eb9  lea     rdx, aInternalErrorM; "Internal Error: Must specify fully qual"...
0x180047ec0  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x180047ec7  call    WriteDbgTraceErrorGpd
0x180047ecc  jmp     short loc_180047EFD
0x180047ece  mov     ebx, 0FFFFFFFFh
0x180047ed3  mov     r8d, ebx
0x180047ed6  lea     rdx, aFatalUnableToA_0; "Fatal: unable to alloc requested memory"...
0x180047edd  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x180047ee4  call    WriteDbgTraceErrorGpd
0x180047ee9  mov     dword ptr [rsi+8B0h], 2
0x180047ef3  mov     dword ptr [rsi+8ACh], 3
0x180047efd  mov     ebx, 6
0x180047f02  mov     rcx, rbp; hMem
0x180047f05  call    cs:__imp_LocalFree
0x180047f0b  test    rdi, rdi
0x180047f0e  jz      short loc_180047F19
0x180047f10  mov     rcx, rdi; hMem
0x180047f13  call    cs:__imp_LocalFree
0x180047f19  mov     eax, ebx
0x180047f1b  jmp     short loc_180047F35
0x180047f1d  lea     rdx, aSyntaxErrorInF; "syntax error in filename for *Include k"...
0x180047f24  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x180047f2b  call    WriteDbgTraceErrorGpd
0x180047f30  mov     eax, 6
0x180047f35  mov     rbx, [rsp+48h+arg_8]
0x180047f3a  mov     rbp, [rsp+48h+arg_10]
0x180047f3f  add     rsp, 20h
0x180047f43  pop     r15
0x180047f45  pop     r14
0x180047f47  pop     r12
0x180047f49  pop     rdi
0x180047f4a  pop     rsi
0x180047f4b  retn
```
