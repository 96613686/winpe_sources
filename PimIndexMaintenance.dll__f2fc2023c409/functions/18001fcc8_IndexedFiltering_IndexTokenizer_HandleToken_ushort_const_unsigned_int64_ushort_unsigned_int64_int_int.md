# IndexedFiltering::IndexTokenizer::HandleToken(ushort const *,unsigned __int64,ushort *,unsigned __int64,int,int *)

- ea: `0x18001fcc8`
- end: `0x18001fede`
- name: `?HandleToken@IndexTokenizer@IndexedFiltering@@AEAAJPEBG_KPEAG1HPEAH@Z`
- size: `534`
- prototype: `__int64 __fastcall(IndexedFiltering::IndexTokenizer *this, const unsigned __int16 *, unsigned __int64, unsigned __int16 *, size_t cchDest, int, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x18001f98c`

## callees

- `0x180002da8`
- `0x180012978`
- `0x18001d638`
- `0x18001f69c`
- `0x18001fcc8`
- `0x180020024`
- `0x18002009c`
- `0x1800201e8`
- `0x180021240`

## string_xrefs

- `0x18001fdd3`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indextokenizer.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexTokenizer::HandleToken(
        IndexedFiltering::IndexTokenizer *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        unsigned __int16 *a4,
        size_t cchDest,
        int a6,
        int *a7)
{
  int *v7; // r12
  STRSAFE_LPWSTR v8; // r15
  __int64 v12; // rdx
  __int64 v13; // rcx
  int updated; // ebx
  int v15; // edi
  int v16; // r15d
  int v17; // eax
  int v18; // r13d
  HRESULT v19; // eax
  int v20; // r11d
  int v21; // esi
  BOOL v22; // r12d
  BOOL v23; // r9d
  __int64 v24; // r8
  int v25; // esi
  HRESULT v26; // eax
  unsigned __int64 v28; // [rsp+20h] [rbp-61h]
  int v29; // [rsp+40h] [rbp-41h] BYREF
  int v30; // [rsp+44h] [rbp-3Dh] BYREF
  size_t pcchLength; // [rsp+48h] [rbp-39h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+50h] [rbp-31h]
  int *v33; // [rsp+58h] [rbp-29h]
  wchar_t psz[8]; // [rsp+60h] [rbp-21h] BYREF

  v7 = a7;
  v8 = a4;
  v33 = a7;
  pszDest = a4;
  v29 = 0;
  if ( !a2 )
    Log_AssertionEvent_6(this, 0, 225);
  if ( !v8 )
    Log_AssertionEvent_6(this, a2, 226);
  if ( *v8 )
    Log_AssertionEvent_6(this, a2, 227);
  if ( !a7 )
    Log_AssertionEvent_6(this, a2, 228);
  updated = IndexedFiltering::IndexTokenizer::RemoveSkippable(this, a2, a3, psz, v28, a6, &v29);
  if ( updated < 0 )
    return (unsigned int)updated;
  if ( !psz[0] )
    return 0;
  v15 = 1;
  if ( (*((_BYTE *)this + 16) & 1) == 0 )
  {
    v16 = 0;
    pcchLength = 0;
    v17 = *((_DWORD *)this + 19);
    v30 = 0;
    if ( a6 )
    {
      if ( v17 )
      {
LABEL_14:
        v18 = 0;
        goto LABEL_15;
      }
    }
    else if ( !v17 )
    {
      goto LABEL_14;
    }
    v18 = 1;
LABEL_15:
    v19 = StringCchLengthW(psz, 7u, &pcchLength);
    updated = v19;
    if ( v19 < 0 )
    {
      Log_HREvent(
        (unsigned int)v19,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indextokenizer.cpp",
        251);
      return (unsigned int)updated;
    }
    v21 = v29;
    v22 = pcchLength == 6;
    v23 = v18 && pcchLength != 6;
    updated = IndexedFiltering::IndexTokenizer::UpdateRunOnTokens(this, psz, v20, v23, v29);
    if ( updated < 0 )
      return (unsigned int)updated;
    if ( v22 || !a6 || *((_DWORD *)this + 19) || *((char *)this + 16) < 0 )
      goto LABEL_31;
    updated = IndexedFiltering::IndexTokenizer::AppendWrapAroundTokenToString((wchar_t *)this, psz, v24, &v30);
    if ( updated < 0 )
      return (unsigned int)updated;
    v16 = v30;
    if ( !v30 )
    {
LABEL_31:
      if ( !v18 || !v22 )
        v15 = 0;
    }
    v25 = v16 | v21;
    if ( v15 )
    {
      v8 = pszDest;
      v7 = v33;
      goto LABEL_36;
    }
    return 0;
  }
  v25 = v29;
LABEL_36:
  if ( cchDest < 7 )
    Log_AssertionEvent_6(v13, v12, 289);
  v26 = StringCchCatW(v8, cchDest, psz);
  updated = 0;
  if ( v26 != -2147024774 )
    updated = v26;
  if ( updated >= 0 )
  {
    *v7 = v25;
    return 0;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x18001fcc8  push    rbp
0x18001fcca  push    rbx
0x18001fccb  push    rsi
0x18001fccc  push    rdi
0x18001fccd  push    r12
0x18001fccf  push    r13
0x18001fcd1  push    r14
0x18001fcd3  push    r15
0x18001fcd5  lea     rbp, [rsp-7]
0x18001fcda  sub     rsp, 88h
0x18001fce1  mov     rax, cs:__security_cookie
0x18001fce8  xor     rax, rsp
0x18001fceb  mov     [rbp+3Fh+var_50], rax
0x18001fcef  mov     r12, [rbp+3Fh+arg_30]
0x18001fcf3  mov     r15, r9
0x18001fcf6  mov     [rbp+3Fh+var_68], r12
0x18001fcfa  mov     rdi, r8
0x18001fcfd  mov     [rbp+3Fh+pszDest], r9
0x18001fd01  mov     rbx, rdx
0x18001fd04  mov     [rbp+3Fh+var_80], 0
0x18001fd0b  mov     r14, rcx
0x18001fd0e  test    rdx, rdx
0x18001fd11  jnz     short loc_18001FD1E
0x18001fd13  mov     r8d, 0E1h
0x18001fd19  call    Log_AssertionEvent_6
0x18001fd1e  test    r15, r15
0x18001fd21  jnz     short loc_18001FD2E
0x18001fd23  mov     r8d, 0E2h
0x18001fd29  call    Log_AssertionEvent_6
0x18001fd2e  xor     eax, eax
0x18001fd30  cmp     ax, [r15]
0x18001fd34  jz      short loc_18001FD41
0x18001fd36  mov     r8d, 0E3h
0x18001fd3c  call    Log_AssertionEvent_6
0x18001fd41  test    r12, r12
0x18001fd44  jnz     short loc_18001FD51
0x18001fd46  mov     r8d, 0E4h
0x18001fd4c  call    Log_AssertionEvent_6
0x18001fd51  lea     rax, [rbp+3Fh+var_80]
0x18001fd55  mov     r8, rdi; unsigned __int64
0x18001fd58  mov     [rsp+0C0h+var_90], rax; int *
0x18001fd5d  lea     r9, [rbp+3Fh+psz]; unsigned __int16 *
0x18001fd61  mov     eax, [rbp+3Fh+arg_28]
0x18001fd64  mov     rdx, rbx; unsigned __int16 *
0x18001fd67  mov     rcx, r14; this
0x18001fd6a  mov     [rsp+0C0h+var_98], eax; int
0x18001fd6e  call    ?RemoveSkippable@IndexTokenizer@IndexedFiltering@@AEAAJPEBG_KPEAG1HPEAH@Z; IndexedFiltering::IndexTokenizer::RemoveSkippable(ushort const *,unsigned __int64,ushort *,unsigned __int64,int,int *)
0x18001fd73  mov     ebx, eax
0x18001fd75  test    eax, eax
0x18001fd77  js      loc_18001FEBC
0x18001fd7d  xor     eax, eax
0x18001fd7f  cmp     ax, [rbp+3Fh+psz]
0x18001fd83  jz      loc_18001FEBA
0x18001fd89  lea     edi, [rax+1]
0x18001fd8c  test    [r14+10h], dil
0x18001fd90  jnz     loc_18001FE83
0x18001fd96  mov     r11d, [rbp+3Fh+arg_28]
0x18001fd9a  xor     r15d, r15d
0x18001fd9d  mov     [rbp+3Fh+pcchLength], rax
0x18001fda1  mov     eax, [r14+4Ch]
0x18001fda5  mov     [rbp+3Fh+var_7C], r15d
0x18001fda9  test    r11d, r11d
0x18001fdac  jz      short loc_18001FDE8
0x18001fdae  test    eax, eax
0x18001fdb0  jz      short loc_18001FDEC
0x18001fdb2  xor     r13d, r13d
0x18001fdb5  lea     r8, [rbp+3Fh+pcchLength]; pcchLength
0x18001fdb9  mov     edx, 7; cchMax
0x18001fdbe  lea     rcx, [rbp+3Fh+psz]; psz
0x18001fdc2  call    StringCchLengthW
0x18001fdc7  mov     ebx, eax
0x18001fdc9  test    eax, eax
0x18001fdcb  jns     short loc_18001FDF1
0x18001fdcd  mov     r9d, 0FBh
0x18001fdd3  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001fdda  mov     edx, edi
0x18001fddc  mov     ecx, eax
0x18001fdde  call    Log_HREvent
0x18001fde3  jmp     loc_18001FEBC
0x18001fde8  test    eax, eax
0x18001fdea  jz      short loc_18001FDB2
0x18001fdec  mov     r13d, edi
0x18001fdef  jmp     short loc_18001FDB5
0x18001fdf1  mov     esi, [rbp+3Fh+var_80]
0x18001fdf4  xor     r12d, r12d
0x18001fdf7  cmp     [rbp+3Fh+pcchLength], 6
0x18001fdfc  setz    r12b
0x18001fe00  test    r13d, r13d
0x18001fe03  jz      short loc_18001FE0F
0x18001fe05  test    r12d, r12d
0x18001fe08  jnz     short loc_18001FE0F
0x18001fe0a  mov     r9d, edi
0x18001fe0d  jmp     short loc_18001FE12
0x18001fe0f  xor     r9d, r9d; int
0x18001fe12  mov     r8d, r11d; int
0x18001fe15  mov     dword ptr [rsp+0C0h+var_A0], esi; int
0x18001fe19  lea     rdx, [rbp+3Fh+psz]; unsigned __int16 *
0x18001fe1d  mov     rcx, r14; this
0x18001fe20  call    ?UpdateRunOnTokens@IndexTokenizer@IndexedFiltering@@AEAAJPEBGHHH@Z; IndexedFiltering::IndexTokenizer::UpdateRunOnTokens(ushort const *,int,int,int)
0x18001fe25  mov     ebx, eax
0x18001fe27  test    eax, eax
0x18001fe29  js      loc_18001FEBC
0x18001fe2f  test    r12d, r12d
0x18001fe32  jnz     short loc_18001FE66
0x18001fe34  cmp     [rbp+3Fh+arg_28], r15d
0x18001fe38  jz      short loc_18001FE66
0x18001fe3a  cmp     [r14+4Ch], r15d
0x18001fe3e  jnz     short loc_18001FE66
0x18001fe40  test    byte ptr [r14+10h], 80h
0x18001fe45  jnz     short loc_18001FE66
0x18001fe47  lea     r9, [rbp+3Fh+var_7C]; int *
0x18001fe4b  mov     rcx, r14; this
0x18001fe4e  lea     rdx, [rbp+3Fh+psz]; unsigned __int16 *
0x18001fe52  call    ?AppendWrapAroundTokenToString@IndexTokenizer@IndexedFiltering@@AEAAJPEAG_KPEAH@Z; IndexedFiltering::IndexTokenizer::AppendWrapAroundTokenToString(ushort *,unsigned __int64,int *)
0x18001fe57  mov     ebx, eax
0x18001fe59  test    eax, eax
0x18001fe5b  js      short loc_18001FEBC
0x18001fe5d  mov     r15d, [rbp+3Fh+var_7C]
0x18001fe61  test    r15d, r15d
0x18001fe64  jnz     short loc_18001FE72
0x18001fe66  test    r13d, r13d
0x18001fe69  jz      short loc_18001FE70
0x18001fe6b  test    r12d, r12d
0x18001fe6e  jnz     short loc_18001FE72
0x18001fe70  xor     edi, edi
0x18001fe72  or      esi, r15d
0x18001fe75  test    edi, edi
0x18001fe77  jz      short loc_18001FEBA
0x18001fe79  mov     r15, [rbp+3Fh+pszDest]
0x18001fe7d  mov     r12, [rbp+3Fh+var_68]
0x18001fe81  jmp     short loc_18001FE86
0x18001fe83  mov     esi, [rbp+3Fh+var_80]
0x18001fe86  cmp     [rbp+3Fh+cchDest], 7
0x18001fe8b  jnb     short loc_18001FE98
0x18001fe8d  mov     r8d, 121h
0x18001fe93  call    Log_AssertionEvent_6
0x18001fe98  mov     rdx, [rbp+3Fh+cchDest]; cchDest
0x18001fe9c  lea     r8, [rbp+3Fh+psz]; pszSrc
0x18001fea0  mov     rcx, r15; pszDest
0x18001fea3  call    StringCchCatW
0x18001fea8  xor     ebx, ebx
0x18001feaa  cmp     eax, 8007007Ah
0x18001feaf  cmovnz  ebx, eax
0x18001feb2  test    ebx, ebx
0x18001feb4  js      short loc_18001FEBC
0x18001feb6  mov     [r12], esi
0x18001feba  xor     ebx, ebx
0x18001febc  mov     eax, ebx
0x18001febe  mov     rcx, [rbp+3Fh+var_50]
0x18001fec2  xor     rcx, rsp; StackCookie
0x18001fec5  call    __security_check_cookie
0x18001feca  add     rsp, 88h
0x18001fed1  pop     r15
0x18001fed3  pop     r14
0x18001fed5  pop     r13
0x18001fed7  pop     r12
0x18001fed9  pop     rdi
0x18001feda  pop     rsi
0x18001fedb  pop     rbx
0x18001fedc  pop     rbp
0x18001fedd  retn
```
