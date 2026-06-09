# winWrite

- ea: `0x180029a60`
- end: `0x180029cd4`
- name: `winWrite`
- size: `628`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180012470`
- `0x18001fbd8`
- `0x1800293d4`
- `0x180029a60`
- `0x180029cdc`
- `0x1800388f0`
- `0x18003af40`
- `0x18003f650`
- `0x1800421fc`
- `0x1800449f0`
- `0x180044fc0`
- `0x1800a4470`
- `0x1800a8010`

## string_xrefs

- `0x180029c76`: `winWrite1`
- `0x180029b58`: `winWrite2`

## pseudocode

```c
__int64 __fastcall winWrite(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rdi
  int v5; // eax
  DWORD v9; // edi
  const char *v11; // rsi
  const char *v12; // rbx
  const char *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v16; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v17; // [rsp+4Ch] [rbp-B4h] BYREF
  _QWORD v18[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v19; // [rsp+60h] [rbp-A0h]
  int v20; // [rsp+64h] [rbp-9Ch]
  __int64 v21; // [rsp+68h] [rbp-98h]
  char v22[512]; // [rsp+70h] [rbp-90h] BYREF

  v19 = a4;
  LODWORD(v15) = 0;
  v4 = a4;
  v5 = HIDWORD(a4) & 0x7FFFFFFF;
  v16 = 0;
  v17 = 0;
  v18[0] = 0;
  v18[1] = 0;
  v21 = 0;
  while ( 2 )
  {
    v20 = v5;
    while ( 1 )
    {
      if ( a3 <= 0 )
      {
        winLogIoerr((unsigned int)v15, 49550);
        return 0;
      }
      if ( (unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, unsigned int *, _QWORD *))off_1800C4410)(
                           *(_QWORD *)(a1 + 16),
                           a2,
                           (unsigned int)a3,
                           &v16,
                           v18) )
        break;
      if ( !(unsigned int)winRetryIoerr(&v15, &v17) )
      {
        v9 = v17;
        goto LABEL_11;
      }
    }
    if ( v16 && v16 <= a3 )
    {
      v4 += v16;
      a2 += v16;
      v19 = v4;
      v5 = HIDWORD(v4) & 0x7FFFFFFF;
      a3 -= v16;
      continue;
    }
    break;
  }
  v9 = off_1800C40C8();
LABEL_11:
  *(_DWORD *)(a1 + 32) = v9;
  if ( v9 != 39 && v9 != 112 )
    return winLogErrorAtLine(778, v9, (unsigned int)"winWrite2", *(_QWORD *)(a1 + 48), 49548);
  v11 = *(const char **)(a1 + 48);
  v22[0] = 0;
  v15 = 0;
  if ( (unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, _QWORD, __int64 *, _DWORD, _QWORD))off_1800C3FC0)(
                       4864,
                       0,
                       v9,
                       0,
                       &v15,
                       0,
                       0) )
  {
    sqlite3BeginBenignMalloc();
    v12 = (const char *)winUnicodeToUtf8(v15);
    sqlite3EndBenignMalloc();
    ((void (__fastcall *)(__int64))off_1800C42A8)(v15);
    sqlite3_snprintf(500, v22, "%s", v12);
    sqlite3_free(v12);
  }
  else
  {
    sqlite3_snprintf(500, v22, "OsError 0x%lx (%lu)", v9, v9);
  }
  v13 = (const char *)&Src;
  v14 = 0;
  if ( v11 )
    v13 = v11;
  if ( v22[0] )
  {
    do
    {
      if ( v22[(int)v14] == 13 )
        break;
      if ( v22[(int)v14] == 10 )
        break;
      v14 = (unsigned int)(v14 + 1);
    }
    while ( v22[(int)v14] );
  }
  if ( (unsigned __int64)(int)v14 >= 0x1F4 )
    _report_rangecheckfailure(v14, v13);
  v22[(int)v14] = 0;
  sqlite3_log(13, "os_win.c:%d: (%lu) %s(%s) - %s", 49543, v9, "winWrite1", v13, v22);
  return 13;
}

```

## disassembly

```asm
0x180029a60  push    rbp
0x180029a62  push    rbx
0x180029a63  push    rsi
0x180029a64  push    rdi
0x180029a65  push    r14
0x180029a67  push    r15
0x180029a69  lea     rbp, [rsp-188h]
0x180029a71  sub     rsp, 288h
0x180029a78  mov     rax, cs:__security_cookie
0x180029a7f  xor     rax, rsp
0x180029a82  mov     [rbp+1B0h+var_40], rax
0x180029a89  xor     r15d, r15d
0x180029a8c  mov     [rsp+2B0h+var_250], r9d
0x180029a91  mov     rax, r9
0x180029a94  mov     dword ptr [rsp+2B0h+var_270], r15d
0x180029a99  sar     rax, 20h
0x180029a9d  mov     rdi, r9
0x180029aa0  btr     eax, 1Fh
0x180029aa4  mov     [rsp+2B0h+var_268], r15d
0x180029aa9  mov     ebx, r8d
0x180029aac  mov     [rsp+2B0h+var_264], r15d
0x180029ab1  mov     r14, rdx
0x180029ab4  mov     [rsp+2B0h+var_260], r15
0x180029ab9  mov     rsi, rcx
0x180029abc  mov     [rsp+2B0h+var_258], r15
0x180029ac1  mov     [rsp+2B0h+var_248], r15
0x180029ac6  mov     [rsp+2B0h+var_24C], eax
0x180029aca  test    ebx, ebx
0x180029acc  jle     loc_180029CA5
0x180029ad2  mov     rcx, [rsi+10h]
0x180029ad6  lea     rax, [rsp+2B0h+var_260]
0x180029adb  mov     [rsp+2B0h+var_290], rax
0x180029ae0  lea     r9, [rsp+2B0h+var_268]
0x180029ae5  mov     rax, cs:off_1800C4410
0x180029aec  mov     r8d, ebx
0x180029aef  mov     rdx, r14
0x180029af2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af7  test    eax, eax
0x180029af9  jnz     short loc_180029B14
0x180029afb  lea     rdx, [rsp+2B0h+var_264]
0x180029b00  lea     rcx, [rsp+2B0h+var_270]
0x180029b05  call    winRetryIoerr
0x180029b0a  test    eax, eax
0x180029b0c  jnz     short loc_180029ACA
0x180029b0e  mov     edi, [rsp+2B0h+var_264]
0x180029b12  jmp     short loc_180029B47
0x180029b14  mov     edx, [rsp+2B0h+var_268]
0x180029b18  test    edx, edx
0x180029b1a  jz      short loc_180029B39
0x180029b1c  cmp     edx, ebx
0x180029b1e  ja      short loc_180029B39
0x180029b20  add     rdi, rdx
0x180029b23  add     r14, rdx
0x180029b26  mov     rax, rdi
0x180029b29  mov     [rsp+2B0h+var_250], edi
0x180029b2d  sar     rax, 20h
0x180029b31  btr     eax, 1Fh
0x180029b35  sub     ebx, edx
0x180029b37  jmp     short loc_180029AC6
0x180029b39  mov     rax, cs:off_1800C40C8
0x180029b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b45  mov     edi, eax
0x180029b47  mov     [rsi+20h], edi
0x180029b4a  cmp     edi, 27h ; '''
0x180029b4d  jz      short loc_180029B78
0x180029b4f  cmp     edi, 70h ; 'p'
0x180029b52  jz      short loc_180029B78
0x180029b54  mov     r9, [rsi+30h]
0x180029b58  lea     r8, aWinwrite2; "winWrite2"
0x180029b5f  mov     edx, edi
0x180029b61  mov     dword ptr [rsp+2B0h+var_290], 0C18Ch
0x180029b69  mov     ecx, 30Ah
0x180029b6e  call    winLogErrorAtLine
0x180029b73  jmp     loc_180029CB5
0x180029b78  mov     rsi, [rsi+30h]
0x180029b7c  lea     rax, [rsp+2B0h+var_270]
0x180029b81  mov     [rsp+2B0h+var_280], r15
0x180029b86  xor     r9d, r9d
0x180029b89  mov     dword ptr [rsp+2B0h+var_288], r15d
0x180029b8e  mov     r8d, edi
0x180029b91  mov     [rsp+2B0h+var_290], rax
0x180029b96  xor     edx, edx
0x180029b98  mov     rax, cs:off_1800C3FC0
0x180029b9f  mov     ecx, 1300h
0x180029ba4  mov     [rsp+2B0h+var_240], r15b
0x180029ba9  mov     [rsp+2B0h+var_270], r15
0x180029bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bb3  test    eax, eax
0x180029bb5  jz      short loc_180029C02
0x180029bb7  call    sqlite3BeginBenignMalloc
0x180029bbc  mov     rcx, [rsp+2B0h+var_270]
0x180029bc1  call    winUnicodeToUtf8
0x180029bc6  mov     rbx, rax
0x180029bc9  call    sqlite3EndBenignMalloc
0x180029bce  mov     rcx, [rsp+2B0h+var_270]
0x180029bd3  mov     rax, cs:off_1800C42A8
0x180029bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029bdf  mov     r9, rbx
0x180029be2  lea     r8, aS_10; "%s"
0x180029be9  lea     rdx, [rsp+2B0h+var_240]
0x180029bee  mov     ecx, 1F4h
0x180029bf3  call    sqlite3_snprintf
0x180029bf8  mov     rcx, rbx
0x180029bfb  call    sqlite3_free
0x180029c00  jmp     short loc_180029C1F
0x180029c02  mov     r9d, edi
0x180029c05  mov     dword ptr [rsp+2B0h+var_290], edi
0x180029c09  lea     r8, aOserror0xLxLu; "OsError 0x%lx (%lu)"
0x180029c10  mov     ecx, 1F4h
0x180029c15  lea     rdx, [rsp+2B0h+var_240]
0x180029c1a  call    sqlite3_snprintf
0x180029c1f  test    rsi, rsi
0x180029c22  lea     rdx, Src
0x180029c29  mov     ecx, r15d
0x180029c2c  mov     ebx, 0Dh
0x180029c31  cmovnz  rdx, rsi
0x180029c35  cmp     [rsp+2B0h+var_240], r15b
0x180029c3a  jz      short loc_180029C58
0x180029c3c  movsxd  rax, ecx
0x180029c3f  cmp     [rsp+rax+2B0h+var_240], bl
0x180029c43  jz      short loc_180029C58
0x180029c45  cmp     [rsp+rax+2B0h+var_240], 0Ah
0x180029c4a  jz      short loc_180029C58
0x180029c4c  inc     ecx
0x180029c4e  movsxd  rax, ecx
0x180029c51  cmp     [rsp+rax+2B0h+var_240], r15b
0x180029c56  jnz     short loc_180029C3C
0x180029c58  movsxd  r8, ecx
0x180029c5b  cmp     r8, 1F4h
0x180029c62  jnb     short loc_180029C9F
0x180029c64  lea     rcx, [rsp+2B0h+var_240]
0x180029c69  mov     [rsp+r8+2B0h+var_240], r15b
0x180029c6e  mov     [rsp+2B0h+var_280], rcx
0x180029c73  mov     r9d, edi
0x180029c76  lea     rcx, aWinwrite1; "winWrite1"
0x180029c7d  mov     [rsp+2B0h+var_288], rdx
0x180029c82  mov     [rsp+2B0h+var_290], rcx
0x180029c87  lea     rdx, aOsWinCDLuSSS; "os_win.c:%d: (%lu) %s(%s) - %s"
0x180029c8e  mov     ecx, ebx
0x180029c90  mov     r8d, 0C187h
0x180029c96  call    sqlite3_log
0x180029c9b  mov     eax, ebx
0x180029c9d  jmp     short loc_180029CB5
0x180029c9f  call    __report_rangecheckfailure
0x180029ca5  mov     ecx, dword ptr [rsp+2B0h+var_270]
0x180029ca9  mov     edx, 0C18Eh
0x180029cae  call    winLogIoerr
0x180029cb3  xor     eax, eax
0x180029cb5  mov     rcx, [rbp+1B0h+var_40]
0x180029cbc  xor     rcx, rsp; StackCookie
0x180029cbf  call    __security_check_cookie
0x180029cc4  add     rsp, 288h
0x180029ccb  pop     r15
0x180029ccd  pop     r14
0x180029ccf  pop     rdi
0x180029cd0  pop     rsi
0x180029cd1  pop     rbx
0x180029cd2  pop     rbp
0x180029cd3  retn
```
