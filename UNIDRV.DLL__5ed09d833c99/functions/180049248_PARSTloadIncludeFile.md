# PARSTloadIncludeFile

- ea: `0x180049248`
- end: `0x180049411`
- name: `PARSTloadIncludeFile`
- size: `457`
- prototype: `__int64 __fastcall(unsigned int *, const wchar_t *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000d218`

## callees

- `0x180007150`
- `0x180009f7c`
- `0x18000ca1c`
- `0x180024c98`
- `0x180033e78`
- `0x18003f5c4`
- `0x180049248`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180049332`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180049332`
- `KERNEL32!LocalFree` at `0x1800493bd`
- `KERNEL32!LocalFree` at `0x1800493d1`
- `KERNEL32!LocalFree` at `0x1800493bd`
- `KERNEL32!LocalFree` at `0x1800493d1`
- `KERNEL32!LocalAlloc` at `0x180049308`
- `KERNEL32!LocalAlloc` at `0x180049308`

## string_xrefs

- `0x180049371`: `Internal Error: Must specify fully qualified path to Root GPD file.`

## pseudocode

```c
__int64 __fastcall PARSTloadIncludeFile(unsigned int *a1, const wchar_t *a2, __int64 a3)
{
  __int64 v3; // rcx
  __int64 v4; // rax
  WCHAR *v7; // rbp
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
  if ( (*(_BYTE *)(v3 + v4 + 52) & 1) == 0 && (unsigned int)BparseString((const char **)(v4 + 24 + v3), (int *)&v17, a3) )
  {
    v7 = PwstrAnsiToUnicode((LPCCH)(*(_QWORD *)a3 + HIDWORD(v17)), a3);
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
0x180049248  mov     r11, rsp
0x18004924b  mov     [r11+10h], rbx
0x18004924f  mov     [r11+18h], rbp
0x180049253  push    rsi
0x180049254  push    rdi
0x180049255  push    r12
0x180049257  push    r14
0x180049259  push    r15
0x18004925b  sub     rsp, 20h
0x18004925f  mov     eax, [rcx]
0x180049261  xor     r12d, r12d
0x180049264  imul    rcx, rax, 38h ; '8'
0x180049268  mov     rax, [r8+1E0h]
0x18004926f  mov     rsi, r8
0x180049272  mov     r15, rdx
0x180049275  mov     [r11+8], r12
0x180049279  test    byte ptr [rcx+rax+34h], 1
0x18004927e  jnz     loc_1800493E1
0x180049284  add     rax, 18h
0x180049288  lea     rdx, [r11+8]
0x18004928c  add     rcx, rax
0x18004928f  call    BparseString
0x180049294  test    eax, eax
0x180049296  jz      loc_1800493E1
0x18004929c  mov     ecx, [rsp+48h+arg_4]
0x1800492a0  mov     rdx, rsi
0x1800492a3  add     rcx, [rsi]; lpMultiByteStr
0x1800492a6  call    PwstrAnsiToUnicode
0x1800492ab  mov     rbp, rax
0x1800492ae  test    rax, rax
0x1800492b1  jnz     short loc_1800492BB
0x1800492b3  lea     ebx, [rax+6]
0x1800492b6  jmp     loc_1800493DD
0x1800492bb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800492bf  mov     rdi, r12
0x1800492c2  mov     rcx, rax
0x1800492c5  inc     rcx
0x1800492c8  cmp     [rbp+rcx*2+0], r12w
0x1800492ce  jnz     short loc_1800492C5
0x1800492d0  inc     rax
0x1800492d3  cmp     [r15+rax*2], r12w
0x1800492d8  jnz     short loc_1800492D0
0x1800492da  add     ecx, eax
0x1800492dc  cmp     ecx, eax
0x1800492de  jb      loc_180049386
0x1800492e4  lea     ebx, [rcx+1]
0x1800492e7  cmp     ebx, ecx
0x1800492e9  jb      loc_180049386
0x1800492ef  lea     rcx, [rbx+rbx]
0x1800492f3  mov     r14d, ebx
0x1800492f6  mov     eax, 0FFFFFFFFh
0x1800492fb  cmp     rcx, rax
0x1800492fe  ja      loc_18004938B
0x180049304  mov     edx, ecx; uBytes
0x180049306  xor     ecx, ecx; uFlags
0x180049308  call    cs:__imp_LocalAlloc
0x18004930f  nop     dword ptr [rax+rax+00h]
0x180049314  mov     rdi, rax
0x180049317  test    rax, rax
0x18004931a  jz      short loc_18004938B
0x18004931c  mov     r8, r15; pszSrc
0x18004931f  mov     edx, r14d; cchDest
0x180049322  mov     rcx, rax; pszDest
0x180049325  call    StringCchCopyW
0x18004932a  mov     edx, 5Ch ; '\'; Ch
0x18004932f  mov     rcx, rdi; Str
0x180049332  call    cs:__imp_wcsrchr
0x180049339  nop     dword ptr [rax+rax+00h]
0x18004933e  test    rax, rax
0x180049341  jz      short loc_180049371
0x180049343  mov     r8, rbp; pszSrc
0x180049346  mov     [rax+2], r12w
0x18004934b  mov     edx, r14d; cchDest
0x18004934e  mov     rcx, rdi; pszDest
0x180049351  call    StringCchCatW
0x180049356  mov     rdx, rsi
0x180049359  mov     rcx, rdi; pszSrc
0x18004935c  call    BloadFile
0x180049361  neg     eax
0x180049363  mov     ebx, 6
0x180049368  sbb     ecx, ecx
0x18004936a  and     ecx, 0FFFFFFFCh
0x18004936d  add     ebx, ecx
0x18004936f  jmp     short loc_1800493BA
0x180049371  lea     rdx, aInternalErrorM; "Internal Error: Must specify fully qual"...
0x180049378  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x18004937f  call    WriteDbgTraceErrorGpd
0x180049384  jmp     short loc_1800493B5
0x180049386  mov     ebx, 0FFFFFFFFh
0x18004938b  mov     r8d, ebx
0x18004938e  lea     rdx, aFatalUnableToA_0; "Fatal: unable to alloc requested memory"...
0x180049395  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x18004939c  call    WriteDbgTraceErrorGpd
0x1800493a1  mov     dword ptr [rsi+8B0h], 2
0x1800493ab  mov     dword ptr [rsi+8ACh], 3
0x1800493b5  mov     ebx, 6
0x1800493ba  mov     rcx, rbp; hMem
0x1800493bd  call    cs:__imp_LocalFree
0x1800493c4  nop     dword ptr [rax+rax+00h]
0x1800493c9  test    rdi, rdi
0x1800493cc  jz      short loc_1800493DD
0x1800493ce  mov     rcx, rdi; hMem
0x1800493d1  call    cs:__imp_LocalFree
0x1800493d8  nop     dword ptr [rax+rax+00h]
0x1800493dd  mov     eax, ebx
0x1800493df  jmp     short loc_1800493F9
0x1800493e1  lea     rdx, aSyntaxErrorInF; "syntax error in filename for *Include k"...
0x1800493e8  lea     rcx, aParstloadinclu; "PARSTloadIncludeFile"
0x1800493ef  call    WriteDbgTraceErrorGpd
0x1800493f4  mov     eax, 6
0x1800493f9  mov     rbx, [rsp+48h+arg_8]
0x1800493fe  mov     rbp, [rsp+48h+arg_10]
0x180049403  add     rsp, 20h
0x180049407  pop     r15
0x180049409  pop     r14
0x18004940b  pop     r12
0x18004940d  pop     rdi
0x18004940e  pop     rsi
0x18004940f  retn
```
