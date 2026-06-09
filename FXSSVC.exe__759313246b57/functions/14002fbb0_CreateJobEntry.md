# CreateJobEntry

- ea: `0x14002fbb0`
- end: `0x140030031`
- name: `CreateJobEntry`
- size: `1153`
- prototype: `char *__fastcall(__int64, DWORD_PTR, int)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x140034da0`
- `0x1400351d8`

## callees

- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140004f64`
- `0x14002fbb0`
- `0x14003600c`
- `0x14004ea44`
- `0x1400698ec`
- `0x14006998c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002fc14`
- `KERNEL32!GetLastError` at `0x14002ff9f`
- `KERNEL32!GetLastError` at `0x14002fc14`
- `KERNEL32!GetLastError` at `0x14002ff9f`
- `KERNEL32!SetLastError` at `0x14002fffd`
- `KERNEL32!SetLastError` at `0x14002fffd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002ff64`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14002ff64`
- `KERNEL32!EnterCriticalSection` at `0x14002ff7a`
- `KERNEL32!EnterCriticalSection` at `0x14002ff7a`
- `KERNEL32!LeaveCriticalSection` at `0x14002ffe0`
- `KERNEL32!LeaveCriticalSection` at `0x140030012`
- `KERNEL32!LeaveCriticalSection` at `0x14002ffe0`
- `KERNEL32!LeaveCriticalSection` at `0x140030012`

## pseudocode

```c
char *__fastcall CreateJobEntry(__int64 a1, DWORD_PTR a2, int a3)
{
  char *v6; // rax
  char *v7; // rdi
  DWORD LastError; // ebx
  _WORD *v9; // r8
  __int64 v10; // rax
  _WORD *v11; // rcx
  const WCHAR *v12; // rcx
  DWORD v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r10
  _WORD *v18; // rcx
  unsigned int v19; // esi
  CMapDeviceId *v20; // rcx
  __int64 v21; // rdx
  _WORD *v22; // rax
  _WORD *v23; // r8
  _WORD *v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // r10
  _WORD *v29; // rcx
  _WORD *v30; // rax
  _WORD *v31; // r8
  _WORD *v32; // rcx
  DWORD v33; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 160, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
  }
  v6 = (char *)pMemAlloc(0x6D0u);
  v7 = v6;
  if ( !v6 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids);
    }
    goto LABEL_77;
  }
  memset_0(v6, 0, 0x6D0u);
  if ( !a1 )
    goto LABEL_68;
  v9 = v7 + 588;
  v10 = -1;
  v11 = (_WORD *)(a1 + 648);
  do
    ++v10;
  while ( v11[v10] );
  if ( v10 )
  {
    v25 = 2147483646;
    v26 = 256;
    v27 = 2147483646;
    v28 = 256;
    do
    {
      if ( !v27 )
        break;
      if ( !*v11 )
        break;
      *v9++ = *v11++;
      --v27;
      --v28;
    }
    while ( v28 );
    v29 = v9 - 1;
    v19 = v28 == 0 ? 0x8007007A : 0;
    if ( v28 )
      v29 = v9;
    *v29 = 0;
    if ( v28 )
    {
      v30 = *(_WORD **)(a1 + 464);
      v31 = v7 + 76;
      do
      {
        if ( !v25 )
          break;
        if ( !*v30 )
          break;
        *v31++ = *v30++;
        --v25;
        --v26;
      }
      while ( v26 );
      v32 = v31 - 1;
      v19 = v26 == 0 ? 0x8007007A : 0;
      if ( v26 )
        v32 = v31;
      *v32 = 0;
      if ( v26 )
        goto LABEL_68;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 166;
        goto LABEL_31;
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 165;
        goto LABEL_31;
      }
    }
    goto LABEL_32;
  }
  v12 = *(const WCHAR **)(a1 + 464);
  if ( !a3 )
  {
    v14 = 2147483646;
    v15 = 256;
    v16 = 2147483646;
    v17 = 256;
    do
    {
      if ( !v16 )
        break;
      if ( !*v12 )
        break;
      *v9++ = *v12++;
      --v16;
      --v17;
    }
    while ( v17 );
    v18 = v9 - 1;
    v19 = v17 == 0 ? 0x8007007A : 0;
    if ( v17 )
      v18 = v9;
    *v18 = 0;
    if ( v17 )
    {
      v22 = *(_WORD **)(a1 + 464);
      v23 = v7 + 76;
      do
      {
        if ( !v14 )
          break;
        if ( !*v22 )
          break;
        *v23++ = *v22++;
        --v14;
        --v15;
      }
      while ( v15 );
      v24 = v23 - 1;
      v19 = v15 == 0 ? 0x8007007A : 0;
      if ( v15 )
        v24 = v23;
      *v24 = 0;
      if ( v15 )
        goto LABEL_68;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 164;
        goto LABEL_31;
      }
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v21 = 163;
LABEL_31:
        WPP_SF_d(*((_QWORD *)v20 + 2), v21, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v19);
      }
    }
LABEL_32:
    LastError = (unsigned __int16)v19;
    if ( (v19 & 0x1FFF0000) != 0x70000 )
      LastError = v19;
    goto LABEL_76;
  }
  v13 = TranslateCanonicalNumber(v12, (unsigned __int16 *)v7 + 38);
  LastError = v13;
  if ( !v13 )
  {
LABEL_68:
    *((_DWORD *)v7 + 6) = 0;
    *((_QWORD *)v7 + 4) = 0;
    *((_QWORD *)v7 + 2) = a2;
    *((_DWORD *)v7 + 18) = -1;
    *((_DWORD *)v7 + 275) = 0;
    *((_QWORD *)v7 + 138) = a1;
    *((_DWORD *)v7 + 278) = 0;
    memset_0(v7 + 1120, 0, 0x58u);
    *((_DWORD *)v7 + 280) = 88;
    *((_DWORD *)v7 + 282) = 1;
    GetSystemTimeAsFileTime((LPFILETIME)v7 + 5);
    EnterCriticalSection(&g_CsLine);
    if ( (*(_BYTE *)(a2 + 76) & 4) != 0 || *(_DWORD *)(a2 + 32) || (unsigned int)OpenTapiLine(a2) )
    {
      *(_QWORD *)(a2 + 48) = v7;
      LeaveCriticalSection(&g_CsLine);
      return v7;
    }
    v33 = GetLastError();
    LastError = v33;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 167, &WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids, v33);
    }
    LeaveCriticalSection(&g_CsLine);
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      162,
      (unsigned int)&WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids,
      *(_QWORD *)(a1 + 464),
      v13);
  }
LABEL_76:
  pMemFree(v7);
LABEL_77:
  v7 = 0;
  if ( LastError )
    SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x14002fbb0  push    rbx
0x14002fbb2  push    rbp
0x14002fbb3  push    rsi
0x14002fbb4  push    rdi
0x14002fbb5  push    r13
0x14002fbb7  push    r14
0x14002fbb9  push    r15
0x14002fbbb  sub     rsp, 30h
0x14002fbbf  mov     ebx, r8d
0x14002fbc2  mov     r14, rdx
0x14002fbc5  mov     rbp, rcx
0x14002fbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fbcf  lea     r13, WPP_GLOBAL_Control
0x14002fbd6  lea     rsi, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fbdd  cmp     rcx, r13
0x14002fbe0  jz      short loc_14002FBFF
0x14002fbe2  test    byte ptr [rcx+1Ch], 4
0x14002fbe6  jz      short loc_14002FBFF
0x14002fbe8  cmp     byte ptr [rcx+19h], 5
0x14002fbec  jb      short loc_14002FBFF
0x14002fbee  mov     rcx, [rcx+10h]
0x14002fbf2  mov     edx, 0A0h
0x14002fbf7  mov     r8, rsi
0x14002fbfa  call    WPP_SF_
0x14002fbff  mov     ecx, 6D0h; dwBytes
0x14002fc04  call    pMemAlloc
0x14002fc09  xor     r15d, r15d
0x14002fc0c  mov     rdi, rax
0x14002fc0f  test    rax, rax
0x14002fc12  jnz     short loc_14002FC5C
0x14002fc14  call    cs:__imp_GetLastError
0x14002fc1b  nop     dword ptr [rax+rax+00h]
0x14002fc20  mov     ebx, eax
0x14002fc22  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fc29  cmp     rcx, r13
0x14002fc2c  jz      loc_14002FFF4
0x14002fc32  test    byte ptr [rcx+1Ch], 4
0x14002fc36  jz      loc_14002FFF4
0x14002fc3c  cmp     byte ptr [rcx+19h], 2
0x14002fc40  jb      loc_14002FFF4
0x14002fc46  mov     rcx, [rcx+10h]
0x14002fc4a  mov     edx, 0A1h
0x14002fc4f  mov     r8, rsi
0x14002fc52  call    WPP_SF_
0x14002fc57  jmp     loc_14002FFF4
0x14002fc5c  xor     edx, edx; Val
0x14002fc5e  mov     r8d, 6D0h; Size
0x14002fc64  mov     rcx, rdi; void *
0x14002fc67  call    memset_0
0x14002fc6c  test    rbp, rbp
0x14002fc6f  jz      loc_14002FF13
0x14002fc75  lea     r8, [rdi+24Ch]
0x14002fc7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002fc80  lea     rcx, [rbp+288h]
0x14002fc87  inc     rax
0x14002fc8a  cmp     [rcx+rax*2], r15w
0x14002fc8f  jnz     short loc_14002FC87
0x14002fc91  test    rax, rax
0x14002fc94  jnz     loc_14002FE13
0x14002fc9a  mov     rcx, [rbp+1D0h]; lpszAddressIn
0x14002fca1  test    ebx, ebx
0x14002fca3  jz      short loc_14002FD02
0x14002fca5  lea     rax, [rdi+4Ch]
0x14002fca9  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x14002fcae  call    TranslateCanonicalNumber
0x14002fcb3  mov     ebx, eax
0x14002fcb5  test    eax, eax
0x14002fcb7  jz      loc_14002FF13
0x14002fcbd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fcc4  cmp     rcx, r13
0x14002fcc7  jz      loc_14002FFEC
0x14002fccd  test    byte ptr [rcx+1Ch], 4
0x14002fcd1  jz      loc_14002FFEC
0x14002fcd7  cmp     byte ptr [rcx+19h], 2
0x14002fcdb  jb      loc_14002FFEC
0x14002fce1  mov     r9, [rbp+1D0h]
0x14002fce8  mov     edx, 0A2h
0x14002fced  mov     rcx, [rcx+10h]
0x14002fcf1  mov     r8, rsi
0x14002fcf4  mov     dword ptr [rsp+68h+var_48], eax
0x14002fcf8  call    WPP_SF_Sd
0x14002fcfd  jmp     loc_14002FFEC
0x14002fd02  mov     r9d, 7FFFFFFEh
0x14002fd08  mov     edx, 100h
0x14002fd0d  mov     eax, r9d
0x14002fd10  mov     r10d, edx
0x14002fd13  test    rax, rax
0x14002fd16  jz      short loc_14002FD37
0x14002fd18  movzx   r11d, word ptr [rcx]
0x14002fd1c  test    r11w, r11w
0x14002fd20  jz      short loc_14002FD37
0x14002fd22  mov     [r8], r11w
0x14002fd26  add     rcx, 2
0x14002fd2a  add     r8, 2
0x14002fd2e  dec     rax
0x14002fd31  sub     r10, 1
0x14002fd35  jnz     short loc_14002FD13
0x14002fd37  mov     rax, r10
0x14002fd3a  lea     rcx, [r8-2]
0x14002fd3e  neg     rax
0x14002fd41  mov     r11d, 8007007Ah
0x14002fd47  sbb     esi, esi
0x14002fd49  not     esi
0x14002fd4b  and     esi, r11d
0x14002fd4e  test    r10, r10
0x14002fd51  cmovnz  rcx, r8
0x14002fd55  mov     [rcx], r15w
0x14002fd59  jnz     short loc_14002FDA2
0x14002fd5b  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fd62  cmp     rcx, r13
0x14002fd65  jz      short loc_14002FD8B
0x14002fd67  test    byte ptr [rcx+1Ch], 4
0x14002fd6b  jz      short loc_14002FD8B
0x14002fd6d  cmp     byte ptr [rcx+19h], 2
0x14002fd71  jb      short loc_14002FD8B
0x14002fd73  mov     edx, 0A3h
0x14002fd78  mov     rcx, [rcx+10h]
0x14002fd7c  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002fd83  mov     r9d, esi
0x14002fd86  call    WPP_SF_d
0x14002fd8b  mov     eax, esi
0x14002fd8d  movzx   ebx, si
0x14002fd90  and     eax, 1FFF0000h
0x14002fd95  cmp     eax, 70000h
0x14002fd9a  cmovnz  ebx, esi
0x14002fd9d  jmp     loc_14002FFEC
0x14002fda2  mov     rax, [rbp+1D0h]
0x14002fda9  lea     r8, [rdi+4Ch]
0x14002fdad  test    r9, r9
0x14002fdb0  jz      short loc_14002FDCF
0x14002fdb2  movzx   ecx, word ptr [rax]
0x14002fdb5  test    cx, cx
0x14002fdb8  jz      short loc_14002FDCF
0x14002fdba  mov     [r8], cx
0x14002fdbe  add     rax, 2
0x14002fdc2  add     r8, 2
0x14002fdc6  dec     r9
0x14002fdc9  sub     rdx, 1
0x14002fdcd  jnz     short loc_14002FDAD
0x14002fdcf  mov     rax, rdx
0x14002fdd2  lea     rcx, [r8-2]
0x14002fdd6  neg     rax
0x14002fdd9  sbb     esi, esi
0x14002fddb  not     esi
0x14002fddd  and     esi, r11d
0x14002fde0  test    rdx, rdx
0x14002fde3  cmovnz  rcx, r8
0x14002fde7  mov     [rcx], r15w
0x14002fdeb  jnz     loc_14002FF13
0x14002fdf1  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fdf8  cmp     rcx, r13
0x14002fdfb  jz      short loc_14002FD8B
0x14002fdfd  test    byte ptr [rcx+1Ch], 4
0x14002fe01  jz      short loc_14002FD8B
0x14002fe03  cmp     byte ptr [rcx+19h], 2
0x14002fe07  jb      short loc_14002FD8B
0x14002fe09  mov     edx, 0A4h
0x14002fe0e  jmp     loc_14002FD78
0x14002fe13  mov     r9d, 7FFFFFFEh
0x14002fe19  mov     edx, 100h
0x14002fe1e  mov     eax, r9d
0x14002fe21  mov     r10d, edx
0x14002fe24  test    rax, rax
0x14002fe27  jz      short loc_14002FE48
0x14002fe29  movzx   r11d, word ptr [rcx]
0x14002fe2d  test    r11w, r11w
0x14002fe31  jz      short loc_14002FE48
0x14002fe33  mov     [r8], r11w
0x14002fe37  add     rcx, 2
0x14002fe3b  add     r8, 2
0x14002fe3f  dec     rax
0x14002fe42  sub     r10, 1
0x14002fe46  jnz     short loc_14002FE24
0x14002fe48  mov     rax, r10
0x14002fe4b  lea     rcx, [r8-2]
0x14002fe4f  neg     rax
0x14002fe52  mov     r11d, 8007007Ah
0x14002fe58  sbb     esi, esi
0x14002fe5a  not     esi
0x14002fe5c  and     esi, r11d
0x14002fe5f  test    r10, r10
0x14002fe62  cmovnz  rcx, r8
0x14002fe66  mov     [rcx], r15w
0x14002fe6a  jnz     short loc_14002FE9A
0x14002fe6c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002fe73  cmp     rcx, r13
0x14002fe76  jz      loc_14002FD8B
0x14002fe7c  test    byte ptr [rcx+1Ch], 4
0x14002fe80  jz      loc_14002FD8B
0x14002fe86  cmp     byte ptr [rcx+19h], 2
0x14002fe8a  jb      loc_14002FD8B
0x14002fe90  mov     edx, 0A5h
0x14002fe95  jmp     loc_14002FD78
0x14002fe9a  mov     rax, [rbp+1D0h]
0x14002fea1  lea     r8, [rdi+4Ch]
0x14002fea5  test    r9, r9
0x14002fea8  jz      short loc_14002FEC7
0x14002feaa  movzx   ecx, word ptr [rax]
0x14002fead  test    cx, cx
0x14002feb0  jz      short loc_14002FEC7
0x14002feb2  mov     [r8], cx
0x14002feb6  add     rax, 2
0x14002feba  add     r8, 2
0x14002febe  dec     r9
0x14002fec1  sub     rdx, 1
0x14002fec5  jnz     short loc_14002FEA5
0x14002fec7  mov     rax, rdx
0x14002feca  lea     rcx, [r8-2]
0x14002fece  neg     rax
0x14002fed1  sbb     esi, esi
0x14002fed3  not     esi
0x14002fed5  and     esi, r11d
0x14002fed8  test    rdx, rdx
0x14002fedb  cmovnz  rcx, r8
0x14002fedf  mov     [rcx], r15w
0x14002fee3  jnz     short loc_14002FF13
0x14002fee5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002feec  cmp     rcx, r13
0x14002feef  jz      loc_14002FD8B
0x14002fef5  test    byte ptr [rcx+1Ch], 4
0x14002fef9  jz      loc_14002FD8B
0x14002feff  cmp     byte ptr [rcx+19h], 2
0x14002ff03  jb      loc_14002FD8B
0x14002ff09  mov     edx, 0A6h
0x14002ff0e  jmp     loc_14002FD78
0x14002ff13  lea     rbx, [rdi+460h]
0x14002ff1a  mov     [rdi+18h], r15d
0x14002ff1e  mov     esi, 58h ; 'X'
0x14002ff23  mov     [rdi+20h], r15
0x14002ff27  mov     r8d, esi; Size
0x14002ff2a  mov     [rdi+10h], r14
0x14002ff2e  mov     rcx, rbx; void *
0x14002ff31  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x14002ff38  xor     edx, edx; Val
0x14002ff3a  mov     [rdi+44Ch], r15d
0x14002ff41  mov     [rdi+450h], rbp
0x14002ff48  mov     [rdi+458h], r15d
0x14002ff4f  call    memset_0
0x14002ff54  lea     rcx, [rdi+28h]; lpSystemTimeAsFileTime
0x14002ff58  mov     [rbx], esi
0x14002ff5a  mov     dword ptr [rdi+468h], 1
0x14002ff64  call    cs:__imp_GetSystemTimeAsFileTime
0x14002ff6b  nop     dword ptr [rax+rax+00h]
0x14002ff70  lea     rsi, ?g_CsLine@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_CsLine
0x14002ff77  mov     rcx, rsi; lpCriticalSection
0x14002ff7a  call    cs:__imp_EnterCriticalSection
0x14002ff81  nop     dword ptr [rax+rax+00h]
0x14002ff86  test    byte ptr [r14+4Ch], 4
0x14002ff8b  jnz     short loc_14003000B
0x14002ff8d  cmp     [r14+20h], r15d
0x14002ff91  jnz     short loc_14003000B
0x14002ff93  mov     rcx, r14; dwCallbackInstance
0x14002ff96  call    ?OpenTapiLine@@YAHPEAU_LINE_INFO@@@Z; OpenTapiLine(_LINE_INFO *)
0x14002ff9b  test    eax, eax
0x14002ff9d  jnz     short loc_14003000B
0x14002ff9f  call    cs:__imp_GetLastError
0x14002ffa6  nop     dword ptr [rax+rax+00h]
0x14002ffab  mov     ebx, eax
0x14002ffad  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ffb4  cmp     rcx, r13
0x14002ffb7  jz      short loc_14002FFDD
0x14002ffb9  test    byte ptr [rcx+1Ch], 4
0x14002ffbd  jz      short loc_14002FFDD
0x14002ffbf  cmp     byte ptr [rcx+19h], 2
0x14002ffc3  jb      short loc_14002FFDD
0x14002ffc5  mov     rcx, [rcx+10h]
0x14002ffc9  lea     r8, WPP_eb6e59e4ccd13b14d69f105e119b08de_Traceguids
0x14002ffd0  mov     edx, 0A7h
0x14002ffd5  mov     r9d, eax
0x14002ffd8  call    WPP_SF_d
0x14002ffdd  mov     rcx, rsi; lpCriticalSection
0x14002ffe0  call    cs:__imp_LeaveCriticalSection
0x14002ffe7  nop     dword ptr [rax+rax+00h]
0x14002ffec  mov     rcx, rdi; lpMem
0x14002ffef  call    pMemFree
0x14002fff4  mov     rdi, r15
0x14002fff7  test    ebx, ebx
0x14002fff9  jz      short loc_14003001E
0x14002fffb  mov     ecx, ebx; dwErrCode
0x14002fffd  call    cs:__imp_SetLastError
0x140030004  nop     dword ptr [rax+rax+00h]
0x140030009  jmp     short loc_14003001E
0x14003000b  mov     rcx, rsi; lpCriticalSection
0x14003000e  mov     [r14+30h], rdi
0x140030012  call    cs:__imp_LeaveCriticalSection
0x140030019  nop     dword ptr [rax+rax+00h]
0x14003001e  mov     rax, rdi
0x140030021  add     rsp, 30h
0x140030025  pop     r15
0x140030027  pop     r14
0x140030029  pop     r13
0x14003002b  pop     rdi
0x14003002c  pop     rsi
0x14003002d  pop     rbp
0x14003002e  pop     rbx
0x14003002f  retn
```
