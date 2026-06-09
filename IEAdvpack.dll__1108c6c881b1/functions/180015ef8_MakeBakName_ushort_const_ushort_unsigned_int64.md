# MakeBakName(ushort const *,ushort *,unsigned __int64)

- ea: `0x180015ef8`
- end: `0x18001608c`
- name: `?MakeBakName@@YAHPEBGPEAG_K@Z`
- size: `404`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x180016268`

## callees

- `0x1800022bc`
- `0x1800035c8`
- `0x18000521c`
- `0x180015ef8`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x180015f7e`
- `USER32!CharNextW` at `0x180015f7e`
- `USER32!CharPrevW` at `0x180015f5b`
- `USER32!CharPrevW` at `0x180015f6f`
- `USER32!CharPrevW` at `0x180015f5b`
- `USER32!CharPrevW` at `0x180015f6f`
- `KERNEL32!GetTempFileNameW` at `0x180016060`
- `KERNEL32!GetTempFileNameW` at `0x180016060`
- `KERNEL32!GetFileAttributesW` at `0x18001601b`
- `KERNEL32!GetFileAttributesW` at `0x18001601b`

## pseudocode

```c
_BOOL8 __fastcall MakeBakName(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  BOOL v4; // esi
  __int64 v5; // rax
  const WCHAR *i; // rdx
  LPWSTR v7; // rax
  const WCHAR *v8; // rbx
  int v9; // ecx
  WCHAR *v10; // rsi
  DWORD FileAttributesW; // eax
  ULONG v13; // [rsp+20h] [rbp-58h]
  WCHAR pszMore[16]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  StringCchCopyW(a2, 0x104u, a1);
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  for ( i = &a2[v5]; ; i = v7 )
  {
    v7 = CharPrevW(a2, i);
    v8 = v7;
    if ( v7 <= a2 || !*v7 || *v7 == 92 )
      break;
  }
  if ( *CharPrevW(a2, v7) == 58 )
    v8 = CharNextW(v8);
  v9 = dword_180032348;
  *v8 = 0;
  if ( v9 >= 1000 )
  {
LABEL_18:
    *v8 = 0;
    CreateFullPath(a1, 0);
    return (BOOL)GetTempFileNameW(a2, L"IE4", 0, a2);
  }
  else
  {
    while ( !v4 )
    {
      *v8 = 0;
      dword_180032348 = v9 + 1;
      StringCchPrintfW(pszMore, 0xEu, L"IEBAK%03d.TMP", (unsigned int)v9);
      v10 = pszMore;
      if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
      {
        do
          ++v10;
        while ( *v10 == 92 );
      }
      PathCchCombineEx(a2, 0x104u, a2, v10, v13);
      FileAttributesW = GetFileAttributesW(a2);
      v9 = dword_180032348;
      v4 = FileAttributesW == -1;
      if ( dword_180032348 >= 1000 )
      {
        if ( FileAttributesW == -1 )
          return v4;
        goto LABEL_18;
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180015ef8  mov     [rsp+arg_10], rbx
0x180015efd  mov     [rsp+arg_18], rbp
0x180015f02  push    rsi
0x180015f03  push    rdi
0x180015f04  push    r14
0x180015f06  sub     rsp, 60h
0x180015f0a  mov     rax, cs:__security_cookie
0x180015f11  xor     rax, rsp
0x180015f14  mov     [rsp+78h+var_28], rax
0x180015f19  mov     rdi, rdx
0x180015f1c  mov     rbp, rcx
0x180015f1f  mov     r8, rcx; unsigned __int16 *
0x180015f22  xor     r14d, r14d
0x180015f25  mov     rcx, rdi; unsigned __int16 *
0x180015f28  mov     edx, 104h; unsigned __int64
0x180015f2d  mov     esi, r14d
0x180015f30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015f35  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015f39  inc     rax
0x180015f3c  cmp     [rdi+rax*2], r14w
0x180015f41  jnz     short loc_180015F39
0x180015f43  lea     rdx, [rdi+rax*2]
0x180015f47  jmp     short loc_180015F58
0x180015f49  cmp     [rbx], r14w
0x180015f4d  jz      short loc_180015F69
0x180015f4f  cmp     word ptr [rbx], 5Ch ; '\'
0x180015f53  jz      short loc_180015F69
0x180015f55  mov     rdx, rbx; lpszCurrent
0x180015f58  mov     rcx, rdi; lpszStart
0x180015f5b  call    cs:__imp_CharPrevW
0x180015f61  mov     rbx, rax
0x180015f64  cmp     rax, rdi
0x180015f67  ja      short loc_180015F49
0x180015f69  mov     rdx, rbx; lpszCurrent
0x180015f6c  mov     rcx, rdi; lpszStart
0x180015f6f  call    cs:__imp_CharPrevW
0x180015f75  cmp     word ptr [rax], 3Ah ; ':'
0x180015f79  jnz     short loc_180015F87
0x180015f7b  mov     rcx, rbx; lpsz
0x180015f7e  call    cs:__imp_CharNextW
0x180015f84  mov     rbx, rax
0x180015f87  mov     ecx, cs:dword_180032348
0x180015f8d  mov     [rbx], r14w
0x180015f91  cmp     ecx, 3E8h
0x180015f97  jge     loc_180016042
0x180015f9d  test    esi, esi
0x180015f9f  jnz     loc_180016068
0x180015fa5  lea     eax, [rcx+1]
0x180015fa8  mov     [rbx], r14w
0x180015fac  mov     r9d, ecx
0x180015faf  mov     cs:dword_180032348, eax
0x180015fb5  lea     rcx, [rsp+78h+pszMore]; unsigned __int16 *
0x180015fba  lea     r8, aIebak03dTmp; "IEBAK%03d.TMP"
0x180015fc1  lea     edx, [rsi+0Eh]; unsigned __int64
0x180015fc4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180015fc9  lea     r8, IsBackslash
0x180015fd0  xor     edx, edx
0x180015fd2  lea     rcx, [rsp+78h+pszMore]; unsigned __int16 *
0x180015fd7  lea     rsi, [rsp+78h+pszMore]
0x180015fdc  call    PathIsUnc2
0x180015fe1  test    eax, eax
0x180015fe3  jnz     short loc_180016005
0x180015fe5  lea     rcx, [rsp+78h+pszMore]; unsigned __int16 *
0x180015fea  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x180015fef  test    al, al
0x180015ff1  jnz     short loc_180016005
0x180015ff3  cmp     [rsp+78h+pszMore], 5Ch ; '\'
0x180015ff9  jnz     short loc_180016005
0x180015ffb  add     rsi, 2
0x180015fff  cmp     word ptr [rsi], 5Ch ; '\'
0x180016003  jz      short loc_180015FFB
0x180016005  mov     r9, rsi; pszMore
0x180016008  mov     r8, rdi; pszPathIn
0x18001600b  mov     edx, 104h; cchPathOut
0x180016010  mov     rcx, rdi; pszPathOut
0x180016013  call    PathCchCombineEx
0x180016018  mov     rcx, rdi; lpFileName
0x18001601b  call    cs:__imp_GetFileAttributesW
0x180016021  mov     ecx, cs:dword_180032348
0x180016027  mov     esi, r14d
0x18001602a  cmp     eax, 0FFFFFFFFh
0x18001602d  setz    sil
0x180016031  cmp     ecx, 3E8h
0x180016037  jl      loc_180015F9D
0x18001603d  cmp     eax, 0FFFFFFFFh
0x180016040  jz      short loc_180016068
0x180016042  xor     edx, edx; int
0x180016044  mov     [rbx], r14w
0x180016048  mov     rcx, rbp; unsigned __int16 *
0x18001604b  call    ?CreateFullPath@@YAJPEBGH@Z; CreateFullPath(ushort const *,int)
0x180016050  mov     r9, rdi; lpTempFileName
0x180016053  lea     rdx, aIe4; "IE4"
0x18001605a  xor     r8d, r8d; uUnique
0x18001605d  mov     rcx, rdi; lpPathName
0x180016060  call    cs:__imp_GetTempFileNameW
0x180016066  mov     esi, eax
0x180016068  mov     eax, esi
0x18001606a  mov     rcx, [rsp+78h+var_28]
0x18001606f  xor     rcx, rsp; StackCookie
0x180016072  call    __security_check_cookie
0x180016077  lea     r11, [rsp+78h+var_18]
0x18001607c  mov     rbx, [r11+30h]
0x180016080  mov     rbp, [r11+38h]
0x180016084  mov     rsp, r11
0x180016087  pop     r14
0x180016089  pop     rdi
0x18001608a  pop     rsi
0x18001608b  retn
```
