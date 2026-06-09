# FveEasUtil::GetVolumeMountPoint(ushort const *,ushort *,ulong)

- ea: `0x1800730f0`
- end: `0x180073409`
- name: `?GetVolumeMountPoint@FveEasUtil@@SAJPEBGPEAGK@Z`
- size: `793`
- prototype: `__int64 __fastcall(LPCWSTR lpszVolumeName, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18004aaec`
- `0x180075754`

## callees

- `0x180009f60`
- `0x18000dd60`
- `0x18000f760`
- `0x180024a18`
- `0x18002e628`
- `0x180034440`
- `0x1800345ec`
- `0x180034d28`
- `0x180071d48`
- `0x1800730f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073178`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073178`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180073164`
- `api-ms-win-core-file-l1-2-0!GetVolumePathNamesForVolumeNameW` at `0x180073164`

## pseudocode

```c
__int64 __fastcall FveEasUtil::GetVolumeMountPoint(LPCWSTR lpszVolumeName, unsigned __int16 *a2)
{
  ULONG v3; // r13d
  WCHAR *v4; // rbx
  DWORD v5; // esi
  unsigned int i; // edi
  unsigned __int64 v7; // rax
  WCHAR *v8; // rsi
  int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  unsigned int KnownLastErrorHR; // eax
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r14
  unsigned int v17; // eax
  __int64 v18; // r10
  ULONGLONG v19; // r15
  unsigned int v20; // eax
  __int64 v21; // r10
  unsigned __int64 v22; // rcx
  ULONGLONG ullOperand; // [rsp+20h] [rbp-20h] BYREF
  WCHAR *v25; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int64 v26; // [rsp+30h] [rbp-10h]
  DWORD cchReturnLength; // [rsp+90h] [rbp+50h] BYREF
  ULONG pulResult; // [rsp+98h] [rbp+58h] BYREF

  ullOperand = 0;
  cchReturnLength = 0;
  v3 = 260;
  v4 = 0;
  pulResult = 260;
  v25 = 0;
  v5 = 0;
  memset_0(a2, 0, 0x208u);
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      if ( i == 3 )
      {
        v12 = 2147549183LL;
        v9 = -2147418113;
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v11 = 114;
          goto LABEL_50;
        }
        goto LABEL_51;
      }
      goto LABEL_27;
    }
    if ( GetVolumePathNamesForVolumeNameW(lpszVolumeName, v4, v5, &cchReturnLength) )
      break;
    if ( GetLastError() != 234 )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v9 = KnownLastErrorHR;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_51;
      v11 = 112;
      goto LABEL_49;
    }
    if ( cchReturnLength <= 1 )
    {
      v9 = 0;
      goto LABEL_51;
    }
    v7 = 2LL * cchReturnLength;
    v8 = v4;
    if ( !is_mul_ok(cchReturnLength, 2u) )
      v7 = -1;
    v25 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v4 = v25;
    if ( v8 )
      operator delete(v8, (const struct std::nothrow_t *)2);
    if ( !v25 )
    {
      v9 = -2147024882;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v11 = 113;
        v12 = 2147942414LL;
LABEL_50:
        WPP_SF_d(v10[2], v11, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v12);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    v5 = cchReturnLength;
  }
  if ( v4 )
  {
LABEL_27:
    v14 = 0;
    v15 = v5;
    v16 = 0;
    v26 = v5;
    while ( v16 < v15 )
    {
      v17 = StringCchLengthW(&v4[v16], v15 - v16, &ullOperand);
      v9 = v17;
      if ( v17 )
      {
        if ( (PVOID *)v18 != &WPP_GLOBAL_Control && (*(_BYTE *)(v18 + 28) & 0x40) != 0 )
          WPP_SF_d(*(_QWORD *)(v18 + 16), 115, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v17);
        if ( v9 < 0 )
          goto LABEL_51;
      }
      v19 = ullOperand;
      if ( !ullOperand )
        break;
      if ( ullOperand < v3 )
      {
        v20 = ULongLongToULong(ullOperand, &pulResult);
        v9 = v20;
        if ( v20 )
        {
          if ( (PVOID *)v21 != &WPP_GLOBAL_Control && (*(_BYTE *)(v21 + 28) & 0x40) != 0 )
            WPP_SF_d(*(_QWORD *)(v21 + 16), 116, &WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids, v20);
          if ( v9 < 0 )
            goto LABEL_51;
        }
        v3 = pulResult;
        v14 = v16;
      }
      v15 = v26;
      v16 += v19;
    }
    v22 = v14 + v3;
    if ( v4[v22 - 1] == 92 )
      v4[v22 - 1] = 0;
    KnownLastErrorHR = StringCchCopyW(a2, 0x104u, &v4[v14]);
    v9 = KnownLastErrorHR;
    if ( !KnownLastErrorHR )
      goto LABEL_51;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_51;
    v11 = 117;
LABEL_49:
    v12 = KnownLastErrorHR;
    goto LABEL_50;
  }
  v12 = 2147549183LL;
  v9 = -2147418113;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v11 = 111;
    goto LABEL_50;
  }
LABEL_51:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>((void **)&v25);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800730f0  mov     [rsp-38h+arg_0], rbx
0x1800730f5  mov     [rsp-38h+cchReturnLength], r8d
0x1800730fa  mov     [rsp-38h+arg_8], rdx
0x1800730ff  push    rbp
0x180073100  push    rsi
0x180073101  push    rdi
0x180073102  push    r12
0x180073104  push    r13
0x180073106  push    r14
0x180073108  push    r15
0x18007310a  mov     rbp, rsp
0x18007310d  sub     rsp, 40h
0x180073111  mov     r15, rdx
0x180073114  mov     [rbp+ullOperand], 0
0x18007311c  mov     r14, rcx
0x18007311f  mov     [rbp+cchReturnLength], 0
0x180073126  mov     r13d, 104h
0x18007312c  xor     ebx, ebx
0x18007312e  mov     rcx, r15; void *
0x180073131  mov     [rbp+pulResult], r13d
0x180073135  xor     edx, edx; Val
0x180073137  mov     [rbp+var_18], rbx
0x18007313b  mov     r8d, 208h; Size
0x180073141  xor     esi, esi
0x180073143  call    memset_0
0x180073148  xor     edi, edi
0x18007314a  lea     r15d, [rbx+2]
0x18007314e  cmp     edi, 3
0x180073151  jnb     loc_180073284
0x180073157  lea     r9, [rbp+cchReturnLength]; lpcchReturnLength
0x18007315b  mov     r8d, esi; cchBufferLength
0x18007315e  mov     rdx, rbx; lpszVolumePathNames
0x180073161  mov     rcx, r14; lpszVolumeName
0x180073164  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x18007316b  nop     dword ptr [rax+rax+00h]
0x180073170  test    eax, eax
0x180073172  jnz     loc_18007324D
0x180073178  call    cs:__imp_GetLastError
0x18007317f  nop     dword ptr [rax+rax+00h]
0x180073184  cmp     eax, 0EAh
0x180073189  jnz     loc_18007321B
0x18007318f  cmp     [rbp+cchReturnLength], 1
0x180073193  jbe     short loc_180073214
0x180073195  mov     ecx, [rbp+cchReturnLength]
0x180073198  mov     rax, r15
0x18007319b  mul     rcx
0x18007319e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800731a5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800731ac  mov     rsi, rbx
0x1800731af  cmovb   rax, rcx
0x1800731b3  mov     rcx, rax; unsigned __int64
0x1800731b6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800731bb  mov     [rbp+var_18], rax
0x1800731bf  mov     rbx, rax
0x1800731c2  test    rsi, rsi
0x1800731c5  jz      short loc_1800731D2
0x1800731c7  mov     rdx, r15; struct std::nothrow_t *
0x1800731ca  mov     rcx, rsi; void *
0x1800731cd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800731d2  test    rbx, rbx
0x1800731d5  jz      short loc_1800731E1
0x1800731d7  mov     esi, [rbp+cchReturnLength]
0x1800731da  inc     edi
0x1800731dc  jmp     loc_18007314E
0x1800731e1  mov     edi, 8007000Eh
0x1800731e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800731ed  lea     rsi, WPP_GLOBAL_Control
0x1800731f4  cmp     rcx, rsi
0x1800731f7  jz      loc_1800733E5
0x1800731fd  test    byte ptr [rcx+1Ch], 40h
0x180073201  jz      loc_1800733E5
0x180073207  mov     edx, 71h ; 'q'
0x18007320c  mov     r9d, edi
0x18007320f  jmp     loc_1800733D5
0x180073214  xor     edi, edi
0x180073216  jmp     loc_1800733E5
0x18007321b  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x180073220  mov     edi, eax
0x180073222  mov     rcx, cs:WPP_GLOBAL_Control
0x180073229  lea     rsi, WPP_GLOBAL_Control
0x180073230  cmp     rcx, rsi
0x180073233  jz      loc_1800733E5
0x180073239  test    byte ptr [rcx+1Ch], 40h
0x18007323d  jz      loc_1800733E5
0x180073243  mov     edx, 70h ; 'p'
0x180073248  jmp     loc_1800733D2
0x18007324d  test    rbx, rbx
0x180073250  jnz     short loc_1800732BA
0x180073252  mov     r9d, 8000FFFFh
0x180073258  mov     edi, r9d
0x18007325b  mov     rcx, cs:WPP_GLOBAL_Control
0x180073262  lea     rsi, WPP_GLOBAL_Control
0x180073269  cmp     rcx, rsi
0x18007326c  jz      loc_1800733E5
0x180073272  test    byte ptr [rcx+1Ch], 40h
0x180073276  jz      loc_1800733E5
0x18007327c  lea     edx, [rbx+6Fh]
0x18007327f  jmp     loc_1800733D5
0x180073284  jnz     short loc_1800732BA
0x180073286  mov     r9d, 8000FFFFh
0x18007328c  mov     edi, r9d
0x18007328f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073296  lea     rsi, WPP_GLOBAL_Control
0x18007329d  cmp     rcx, rsi
0x1800732a0  jz      loc_1800733E5
0x1800732a6  test    byte ptr [rcx+1Ch], 40h
0x1800732aa  jz      loc_1800733E5
0x1800732b0  mov     edx, 72h ; 'r'
0x1800732b5  jmp     loc_1800733D5
0x1800732ba  mov     r10, cs:WPP_GLOBAL_Control
0x1800732c1  xor     r12d, r12d
0x1800732c4  mov     eax, esi
0x1800732c6  xor     r14d, r14d
0x1800732c9  mov     [rbp+var_10], rax
0x1800732cd  lea     rsi, WPP_GLOBAL_Control
0x1800732d4  cmp     r14, rax
0x1800732d7  jnb     loc_18007338E
0x1800732dd  mov     rdx, rax
0x1800732e0  lea     rcx, [rbx+r14*2]; unsigned __int16 *
0x1800732e4  sub     rdx, r14; unsigned __int64
0x1800732e7  lea     r8, [rbp+ullOperand]; unsigned __int64 *
0x1800732eb  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800732f0  mov     edi, eax
0x1800732f2  test    eax, eax
0x1800732f4  jz      short loc_180073329
0x1800732f6  cmp     r10, rsi
0x1800732f9  jz      short loc_180073321
0x1800732fb  test    byte ptr [r10+1Ch], 40h
0x180073300  jz      short loc_180073321
0x180073302  mov     rcx, [r10+10h]
0x180073306  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x18007330d  mov     edx, 73h ; 's'
0x180073312  mov     r9d, eax
0x180073315  call    WPP_SF_d
0x18007331a  mov     r10, cs:WPP_GLOBAL_Control
0x180073321  test    edi, edi
0x180073323  js      loc_1800733E5
0x180073329  mov     r15, [rbp+ullOperand]
0x18007332d  test    r15, r15
0x180073330  jz      short loc_18007338E
0x180073332  mov     eax, r13d
0x180073335  cmp     r15, rax
0x180073338  jnb     short loc_180073382
0x18007333a  lea     rdx, [rbp+pulResult]; pulResult
0x18007333e  mov     rcx, r15; ullOperand
0x180073341  call    ULongLongToULong
0x180073346  mov     edi, eax
0x180073348  test    eax, eax
0x18007334a  jz      short loc_18007337B
0x18007334c  cmp     r10, rsi
0x18007334f  jz      short loc_180073377
0x180073351  test    byte ptr [r10+1Ch], 40h
0x180073356  jz      short loc_180073377
0x180073358  mov     rcx, [r10+10h]
0x18007335c  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x180073363  mov     edx, 74h ; 't'
0x180073368  mov     r9d, eax
0x18007336b  call    WPP_SF_d
0x180073370  mov     r10, cs:WPP_GLOBAL_Control
0x180073377  test    edi, edi
0x180073379  js      short loc_1800733E5
0x18007337b  mov     r13d, [rbp+pulResult]
0x18007337f  mov     r12, r14
0x180073382  mov     rax, [rbp+var_10]
0x180073386  add     r14, r15
0x180073389  jmp     loc_1800732D4
0x18007338e  mov     ecx, r13d
0x180073391  add     rcx, r12
0x180073394  cmp     word ptr [rbx+rcx*2-2], 5Ch ; '\'
0x18007339a  jnz     short loc_1800733A3
0x18007339c  xor     eax, eax
0x18007339e  mov     [rbx+rcx*2-2], ax
0x1800733a3  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x1800733a7  lea     r8, [rbx+r12*2]; unsigned __int16 *
0x1800733ab  mov     edx, 104h; unsigned __int64
0x1800733b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800733b5  mov     edi, eax
0x1800733b7  test    eax, eax
0x1800733b9  jz      short loc_1800733E5
0x1800733bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800733c2  cmp     rcx, rsi
0x1800733c5  jz      short loc_1800733E5
0x1800733c7  test    byte ptr [rcx+1Ch], 40h
0x1800733cb  jz      short loc_1800733E5
0x1800733cd  mov     edx, 75h ; 'u'
0x1800733d2  mov     r9d, eax
0x1800733d5  mov     rcx, [rcx+10h]
0x1800733d9  lea     r8, WPP_594ec6ed84873d87f5bcccf654995dcc_Traceguids
0x1800733e0  call    WPP_SF_d
0x1800733e5  lea     rcx, [rbp+var_18]
0x1800733e9  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800733ee  mov     rbx, [rsp+40h+arg_0]
0x1800733f6  mov     eax, edi
0x1800733f8  add     rsp, 40h
0x1800733fc  pop     r15
0x1800733fe  pop     r14
0x180073400  pop     r13
0x180073402  pop     r12
0x180073404  pop     rdi
0x180073405  pop     rsi
0x180073406  pop     rbp
0x180073407  retn
```
