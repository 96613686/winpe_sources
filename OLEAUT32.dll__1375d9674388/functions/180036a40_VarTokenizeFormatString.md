# VarTokenizeFormatString

- ea: `0x180036a40`
- end: `0x180036cd5`
- name: `VarTokenizeFormatString`
- size: `661`
- prototype: `HRESULT __stdcall(LPOLESTR pstrFormat, LPBYTE rgbTok, int cbTok, int iFirstDay, int iFirstWeek, LCID lcid, int *pcbActual)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180044920`

## callees

- `0x1800057e0`
- `0x180007590`
- `0x180026740`
- `0x18002ac34`
- `0x18002b020`
- `0x180036a40`
- `0x180036cdc`
- `0x18009a624`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180036b65`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180036b65`

## pseudocode

```c
HRESULT __stdcall VarTokenizeFormatString(
        LPOLESTR pstrFormat,
        LPBYTE rgbTok,
        int cbTok,
        int iFirstDay,
        int iFirstWeek,
        LCID lcid,
        int *pcbActual)
{
  DWORD v10; // r12d
  HRESULT result; // eax
  __int16 v12; // cx
  __int64 v13; // r14
  unsigned int i; // edi
  int cchCount2; // eax
  __int64 *v16; // rdx
  LPOLESTR v17; // rax
  struct tagNUMINFO *v18[10]; // [rsp+48h] [rbp-50h] BYREF

  if ( (unsigned int)iFirstDay > 7 )
    return -2147024809;
  v10 = 3;
  if ( (unsigned int)iFirstWeek > 3 || !rgbTok )
    return -2147024809;
  result = 0;
  if ( !pstrFormat || !*pstrFormat )
  {
    *rgbTok = 0;
    goto LABEL_16;
  }
  if ( cbTok < 0 )
    return -2147024809;
  v12 = 91;
  if ( *pstrFormat == 91 )
  {
    v17 = pstrFormat;
    do
    {
      if ( v12 == 59 )
        break;
      if ( !v12 )
        break;
      v12 = *++v17;
    }
    while ( *v17 != 93 );
    if ( *v17 == 93 && !v17[1] )
    {
      *rgbTok = 0;
LABEL_46:
      result = 0;
LABEL_16:
      if ( pcbActual )
        *pcbActual = *rgbTok;
      return result;
    }
  }
  v13 = -1;
  do
    ++v13;
  while ( pstrFormat[v13] );
  if ( (unsigned int)IsDBCS(lcid) )
  {
    v10 = 131075;
    if ( (unsigned int)IsJapan(lcid) )
      v10 = 196611;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 0x10 )
    {
      result = ParseFormatString(pstrFormat, 0, rgbTok, cbTok, iFirstDay, iFirstWeek, lcid);
      if ( result < 0 )
        return result;
      goto LABEL_16;
    }
    cchCount2 = (int)(&off_18009FEC0)[3 * (int)i + 1];
    if ( (_DWORD)v13 == cchCount2
      && CompareStringW(lcid, v10, pstrFormat, v13, (&off_18009FEC0)[3 * (int)i], cchCount2) == 2 )
    {
      break;
    }
  }
  _mm_lfence();
  v16 = (__int64 *)*(&off_18009FEC0 + 3 * (int)i + 1);
  if ( v16 )
    goto LABEL_21;
  if ( i != 12 )
  {
    if ( i == 2 )
    {
      v18[0] = 0;
      result = GetDateInfo(lcid, 0, v18);
      if ( result <= -1 )
        return result;
      v16 = qword_1800B4600;
      if ( !*((_DWORD *)v18[0] + 292) )
        v16 = qword_1800B45E8;
    }
LABEL_21:
    if ( *(unsigned __int8 *)v16 <= cbTok )
    {
      memcpy_0(rgbTok, v16, *(unsigned __int8 *)v16);
      goto LABEL_46;
    }
    return -2147352557;
  }
  v18[0] = 0;
  if ( (unsigned int)cbTok < 0x2E )
    return -2147352557;
  result = GetNumInfo(lcid, 0, v18);
  if ( result > -1 )
  {
    result = TokenizeNumericFormat(
               rgbTok,
               -1,
               -2,
               -2,
               -2,
               *((_DWORD *)v18[0] + 22) | 0x2001,
               *((_DWORD *)v18[0] + 23),
               0);
    if ( result > -1 )
      goto LABEL_46;
  }
  return result;
}

```

## disassembly

```asm
0x180036a40  mov     [rsp+arg_18], r9d
0x180036a45  push    rbx
0x180036a46  push    rbp
0x180036a47  push    rsi
0x180036a48  push    rdi
0x180036a49  push    r12
0x180036a4b  push    r13
0x180036a4d  push    r14
0x180036a4f  push    r15
0x180036a51  sub     rsp, 58h
0x180036a55  mov     r15d, r8d
0x180036a58  mov     rbx, rdx
0x180036a5b  mov     rsi, rcx
0x180036a5e  cmp     r9d, 7
0x180036a62  ja      loc_180036CCB
0x180036a68  mov     r12d, 3
0x180036a6e  cmp     [rsp+98h+iFirstWeek], r12d
0x180036a76  ja      loc_180036CCB
0x180036a7c  xor     r13d, r13d
0x180036a7f  test    rdx, rdx
0x180036a82  jz      loc_180036CCB
0x180036a88  mov     eax, r13d
0x180036a8b  test    rcx, rcx
0x180036a8e  jz      loc_180036B9A
0x180036a94  cmp     [rcx], r13w
0x180036a98  jz      loc_180036B9A
0x180036a9e  test    r8d, r8d
0x180036aa1  js      loc_180036CCB
0x180036aa7  lea     ecx, [r12+58h]
0x180036aac  cmp     [rsi], cx
0x180036aaf  jz      loc_180036BAB
0x180036ab5  or      r14, 0FFFFFFFFFFFFFFFFh
0x180036ab9  inc     r14
0x180036abc  cmp     [rsi+r14*2], r13w
0x180036ac1  jnz     short loc_180036AB9
0x180036ac3  mov     ebp, [rsp+98h+lcid]
0x180036aca  mov     ecx, ebp
0x180036acc  call    IsDBCS
0x180036ad1  test    eax, eax
0x180036ad3  jnz     loc_180036BE3
0x180036ad9  mov     edi, r13d
0x180036adc  lea     rcx, off_18009FEC0; "general number"
0x180036ae3  cmp     edi, 10h
0x180036ae6  jnb     short loc_180036AFD
0x180036ae8  movsxd  rax, edi
0x180036aeb  lea     r13, [rax+rax*2]
0x180036aef  mov     eax, [rcx+r13*8+10h]
0x180036af4  cmp     r14d, eax
0x180036af7  jz      short loc_180036B4D
0x180036af9  inc     edi
0x180036afb  jmp     short loc_180036AE3
0x180036afd  mov     eax, [rsp+98h+iFirstWeek]
0x180036b04  mov     r9d, r15d; int
0x180036b07  mov     [rsp+98h+var_68], ebp; unsigned int
0x180036b0b  mov     r8, rbx; unsigned __int8 *
0x180036b0e  mov     [rsp+98h+cchCount2], eax; int
0x180036b12  xor     edx, edx; int
0x180036b14  mov     eax, [rsp+98h+arg_18]
0x180036b1b  mov     rcx, rsi; unsigned __int16 *
0x180036b1e  mov     dword ptr [rsp+98h+lpString2], eax; int
0x180036b22  call    ?ParseFormatString@@YAJPEAGHPEAEHHHK@Z; ParseFormatString(ushort *,int,uchar *,int,int,int,ulong)
0x180036b27  test    eax, eax
0x180036b29  js      short loc_180036B3C
0x180036b2b  mov     rdx, [rsp+98h+pcbActual]
0x180036b33  test    rdx, rdx
0x180036b36  jnz     loc_180036CC1
0x180036b3c  add     rsp, 58h
0x180036b40  pop     r15
0x180036b42  pop     r14
0x180036b44  pop     r13
0x180036b46  pop     r12
0x180036b48  pop     rdi
0x180036b49  pop     rsi
0x180036b4a  pop     rbp
0x180036b4b  pop     rbx
0x180036b4c  retn
0x180036b4d  mov     [rsp+98h+cchCount2], eax; cchCount2
0x180036b51  mov     r9d, r14d; cchCount1
0x180036b54  mov     rax, [rcx+r13*8]
0x180036b58  mov     r8, rsi; lpString1
0x180036b5b  mov     ecx, ebp; Locale
0x180036b5d  mov     [rsp+98h+lpString2], rax; lpString2
0x180036b62  mov     edx, r12d; dwCmpFlags
0x180036b65  call    cs:__imp_CompareStringW
0x180036b6b  cmp     eax, 2
0x180036b6e  jnz     short loc_180036B9F
0x180036b70  lfence
0x180036b73  lea     rdx, off_18009FEC0; "general number"
0x180036b7a  mov     rdx, [rdx+r13*8+8]; Src
0x180036b7f  xor     r13d, r13d
0x180036b82  test    rdx, rdx
0x180036b85  jz      short loc_180036C00
0x180036b87  movzx   eax, byte ptr [rdx]
0x180036b8a  cmp     eax, r15d
0x180036b8d  jle     loc_180036CAE
0x180036b93  mov     eax, 80020013h
0x180036b98  jmp     short loc_180036B3C
0x180036b9a  mov     [rdx], r13b
0x180036b9d  jmp     short loc_180036B2B
0x180036b9f  lea     rcx, off_18009FEC0; "general number"
0x180036ba6  jmp     loc_180036AF9
0x180036bab  mov     rax, rsi
0x180036bae  cmp     cx, 3Bh ; ';'
0x180036bb2  jz      short loc_180036BC6
0x180036bb4  test    cx, cx
0x180036bb7  jz      short loc_180036BC6
0x180036bb9  add     rax, 2
0x180036bbd  movzx   ecx, word ptr [rax]
0x180036bc0  cmp     cx, 5Dh ; ']'
0x180036bc4  jnz     short loc_180036BAE
0x180036bc6  cmp     word ptr [rax], 5Dh ; ']'
0x180036bca  jnz     loc_180036AB5
0x180036bd0  cmp     [rax+2], r13w
0x180036bd5  jnz     loc_180036AB5
0x180036bdb  mov     [rdx], r13b
0x180036bde  jmp     loc_180036CB9
0x180036be3  mov     ecx, ebp
0x180036be5  mov     r12d, 20003h
0x180036beb  call    IsJapan
0x180036bf0  test    eax, eax
0x180036bf2  mov     ecx, 30003h
0x180036bf7  cmovnz  r12d, ecx
0x180036bfb  jmp     loc_180036AD9
0x180036c00  cmp     edi, 0Ch
0x180036c03  jnz     short loc_180036C66
0x180036c05  mov     [rsp+98h+var_50], r13
0x180036c0a  cmp     r15d, 2Eh ; '.'
0x180036c0e  jb      short loc_180036B93
0x180036c10  lea     r8, [rsp+98h+var_50]; struct tagNUMINFO **
0x180036c15  xor     edx, edx; unsigned int
0x180036c17  mov     ecx, ebp; unsigned int
0x180036c19  call    ?GetNumInfo@@YAJKKPEAPEAUtagNUMINFO@@@Z; GetNumInfo(ulong,ulong,tagNUMINFO * *)
0x180036c1e  cmp     eax, 0FFFFFFFFh
0x180036c21  jle     loc_180036B3C
0x180036c27  mov     rax, [rsp+98h+var_50]
0x180036c2c  lea     r8d, [rdi-0Eh]; int
0x180036c30  mov     [rsp+98h+var_60], r13d; unsigned int
0x180036c35  mov     r9d, r8d; int
0x180036c38  or      edx, 0FFFFFFFFh; int
0x180036c3b  mov     ecx, [rax+58h]
0x180036c3e  mov     eax, [rax+5Ch]
0x180036c41  or      ecx, 2001h
0x180036c47  mov     [rsp+98h+var_68], eax; int
0x180036c4b  mov     [rsp+98h+cchCount2], ecx; int
0x180036c4f  mov     rcx, rbx; unsigned __int8 *
0x180036c52  mov     dword ptr [rsp+98h+lpString2], r8d; int
0x180036c57  call    ?TokenizeNumericFormat@@YAJPEAEHHHHHHI@Z; TokenizeNumericFormat(uchar *,int,int,int,int,int,int,uint)
0x180036c5c  cmp     eax, 0FFFFFFFFh
0x180036c5f  jg      short loc_180036CB9
0x180036c61  jmp     loc_180036B3C
0x180036c66  cmp     edi, 2
0x180036c69  jnz     loc_180036B87
0x180036c6f  lea     r8, [rsp+98h+var_50]
0x180036c74  mov     [rsp+98h+var_50], r13
0x180036c79  xor     edx, edx
0x180036c7b  mov     ecx, ebp
0x180036c7d  call    GetDateInfo
0x180036c82  cmp     eax, 0FFFFFFFFh
0x180036c85  jle     loc_180036B3C
0x180036c8b  mov     rax, [rsp+98h+var_50]
0x180036c90  lea     rdx, qword_1800B4600
0x180036c97  lea     rcx, qword_1800B45E8
0x180036c9e  cmp     [rax+490h], r13d
0x180036ca5  cmovz   rdx, rcx
0x180036ca9  jmp     loc_180036B87
0x180036cae  mov     r8, rax; Size
0x180036cb1  mov     rcx, rbx; void *
0x180036cb4  call    memcpy_0
0x180036cb9  mov     eax, r13d
0x180036cbc  jmp     loc_180036B2B
0x180036cc1  movzx   ecx, byte ptr [rbx]
0x180036cc4  mov     [rdx], ecx
0x180036cc6  jmp     loc_180036B3C
0x180036ccb  mov     eax, 80070057h
0x180036cd0  jmp     loc_180036B3C
```
