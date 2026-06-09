# I_UpdateReaderStateArray

- ea: `0x18001c158`
- end: `0x18001c6dd`
- name: `I_UpdateReaderStateArray`
- size: `1413`
- prototype: `__int64 __fastcall(__int64, LPVOID **, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001b00c`
- `0x18001ba4c`

## callees

- `0x180007178`
- `0x1800140d0`
- `0x18001714c`
- `0x180017178`
- `0x18001c158`
- `0x18001ca98`
- `0x18001cc6c`
- `0x18001dfe2`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c1da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c39d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c467`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c4b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c1da`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c39d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c467`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001c4b1`
- `WinSCard!SCardFreeMemory` at `0x18001c699`
- `WinSCard!SCardFreeMemory` at `0x18001c699`
- `WinSCard!SCardListReadersW` at `0x18001c1a9`
- `WinSCard!SCardListReadersW` at `0x18001c1a9`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x18001c4f5`
- `WinSCard!SCardGetDeviceTypeIdW` at `0x18001c4f5`

## string_xrefs

- `0x18001c192`: `SCard$AllReaders`

## pseudocode

```c
__int64 __fastcall I_UpdateReaderStateArray(__int64 a1, LPVOID **a2, int *a3)
{
  unsigned int v5; // r13d
  LPVOID *m; // rdi
  LPVOID *v7; // r12
  LONG v8; // eax
  LPVOID *v9; // r11
  unsigned int v10; // ebx
  LPVOID *v11; // rax
  __int64 v12; // rcx
  LPVOID *v13; // rsi
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  DWORD i; // ecx
  _WORD *v17; // rdx
  __int64 v18; // rax
  LPVOID *v19; // rax
  unsigned int v20; // r15d
  DWORD j; // edx
  unsigned int k; // r9d
  LPVOID *v23; // r8
  unsigned __int64 v24; // r11
  unsigned __int16 *v25; // rax
  __int64 v26; // rbx
  int v27; // ecx
  int v28; // r10d
  unsigned __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // rdx
  wchar_t *v32; // rax
  __int64 v33; // rcx
  unsigned __int64 v34; // rbx
  const wchar_t *v35; // r8
  __int64 v36; // rdx
  LPVOID *v37; // r8
  unsigned __int16 *v38; // rdx
  signed __int64 v39; // r9
  int v40; // eax
  int v41; // ecx
  LPVOID v42; // rax
  HANDLE v43; // rcx
  LPVOID *v44; // rax
  __int64 v45; // rcx
  __int64 v46; // r8
  wchar_t *v47; // rax
  __int64 v48; // rcx
  const wchar_t *v49; // r8
  __int64 v50; // rdx
  unsigned int DeviceTypeIdW; // eax
  int v52; // eax
  __int64 v53; // rax
  LPVOID **v54; // r15
  int *v55; // rax
  _QWORD *v56; // rcx
  int *v57; // rcx
  WCHAR mszReaders[4]; // [rsp+20h] [rbp-18h] BYREF
  DWORD pcchReaders; // [rsp+80h] [rbp+48h] BYREF
  LPVOID **v61; // [rsp+88h] [rbp+50h]
  int *v62; // [rsp+90h] [rbp+58h]
  int v63; // [rsp+98h] [rbp+60h] BYREF

  v62 = a3;
  v61 = a2;
  pcchReaders = -1;
  *(_QWORD *)mszReaders = 0;
  v63 = 0;
  v5 = 0;
  m = 0;
  v7 = 0;
  v8 = SCardListReadersW(*(_QWORD *)(a1 + 232), L"SCard$AllReaders", mszReaders, &pcchReaders);
  v9 = 0;
  v10 = v8;
  if ( v8 )
  {
    if ( v8 != -2146435026 )
    {
      v13 = 0;
      goto LABEL_80;
    }
    v10 = 0;
  }
  else
  {
    pcchReaders = 0;
    if ( *(_QWORD *)mszReaders )
    {
      for ( i = 0; ; pcchReaders = i )
      {
        v17 = (_WORD *)(*(_QWORD *)mszReaders + 2LL * i);
        if ( !*v17 )
          break;
        ++v5;
        v18 = -1;
        do
          ++v18;
        while ( v17[v18] );
        i += v18 + 1;
      }
    }
  }
  v11 = (LPVOID *)HeapAlloc(hHeap, 8u, (unsigned __int64)(v5 + 1) << 6);
  v9 = 0;
  v13 = v11;
  if ( !v11 )
  {
    WppTraceIndent(v12, 2);
    v10 = 8;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 194;
LABEL_9:
      WPP_SF_s(v14[2], v15, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
    }
    goto LABEL_10;
  }
  v19 = *a2;
  if ( *a2 && *v19 )
  {
    *(_OWORD *)v13 = *(_OWORD *)v19;
    *((_OWORD *)v13 + 1) = *((_OWORD *)v19 + 1);
    *((_OWORD *)v13 + 2) = *((_OWORD *)v19 + 2);
    *((_OWORD *)v13 + 3) = *((_OWORD *)v19 + 3);
  }
  else
  {
    *((_DWORD *)v13 + 4) = v5 << 16;
    *v13 = L"\\\\?PnP?\\Notification";
  }
  v20 = 0;
  for ( j = 0; ; j = v53 + pcchReaders + 1 )
  {
    pcchReaders = j;
    m = 0;
    if ( v20 >= v5 )
      goto LABEL_80;
    for ( k = 1; k < *v62; ++k )
    {
      v23 = *v61;
      if ( !*v61 )
        break;
      v24 = (unsigned __int64)k << 6;
      v25 = *(unsigned __int16 **)((char *)v23 + v24);
      v26 = *(_QWORD *)mszReaders + 2LL * j - (_QWORD)v25;
      do
      {
        v27 = *(unsigned __int16 *)((char *)v25 + v26);
        v28 = *v25 - v27;
        if ( v28 )
          break;
        ++v25;
      }
      while ( v27 );
      if ( !v28 )
      {
        LODWORD(m) = 1;
        v29 = (unsigned __int64)(v20 + 1) << 6;
        *(_OWORD *)((char *)v13 + v29) = *(_OWORD *)((char *)v23 + v24);
        *(_OWORD *)((char *)v13 + v29 + 16) = *(_OWORD *)((char *)v23 + v24 + 16);
        *(_OWORD *)((char *)v13 + v29 + 32) = *(_OWORD *)((char *)v23 + v24 + 32);
        *(_OWORD *)((char *)v13 + v29 + 48) = *(_OWORD *)((char *)v23 + v24 + 48);
        j = pcchReaders;
        break;
      }
    }
    v30 = -1;
    v31 = *(_QWORD *)mszReaders + 2LL * j;
    do
      ++v30;
    while ( *(_WORD *)(v31 + 2 * v30) );
    ++v20;
    v32 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v30 + 2);
    v34 = (unsigned __int64)v20 << 6;
    *(LPVOID *)((char *)v13 + v34) = v32;
    if ( !v32 )
    {
      WppTraceIndent(v33, 2);
      v10 = 8;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          195,
          &WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent);
      }
      v9 = 0;
      goto LABEL_79;
    }
    v35 = (const wchar_t *)(*(_QWORD *)mszReaders + 2LL * pcchReaders);
    v36 = -1;
    do
      ++v36;
    while ( v35[v36] );
    if ( StringCchCopyW(v32, v36 + 1, v35) < 0 )
    {
      v10 = 122;
LABEL_79:
      m = v9;
      goto LABEL_80;
    }
    if ( (_DWORD)m )
    {
      v37 = *(LPVOID **)(a1 + 112);
      for ( m = v37; ; m = (LPVOID *)m[30] )
      {
        if ( !m )
        {
          v10 = 1168;
          goto LABEL_80;
        }
        v38 = (unsigned __int16 *)(*(_QWORD *)mszReaders + 2LL * pcchReaders);
        v39 = (_BYTE *)*m - (_BYTE *)v38;
        do
        {
          v40 = *(unsigned __int16 *)((char *)v38 + v39);
          v41 = *v38 - v40;
          if ( v41 )
            break;
          ++v38;
        }
        while ( v40 );
        v42 = m[30];
        if ( !v41 )
          break;
        v37 = m;
      }
      if ( m == *(LPVOID **)(a1 + 112) )
        *(_QWORD *)(a1 + 112) = v42;
      else
        v37[30] = v42;
      goto LABEL_57;
    }
    v43 = hHeap;
    *(_DWORD *)((char *)v13 + v34 + 16) = 16;
    v44 = (LPVOID *)HeapAlloc(v43, 8u, 0xF8u);
    m = v44;
    if ( !v44 )
      break;
    memset_0(v44, 0, 0xF8u);
    v46 = -1;
    do
      ++v46;
    while ( (*(_WORD **)((char *)v13 + v34))[v46] );
    v47 = (wchar_t *)HeapAlloc(hHeap, 8u, 2 * v46 + 2);
    *m = v47;
    if ( !v47 )
    {
      WppTraceIndent(v48, 2);
      v10 = 8;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = 197;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
    v49 = *(const wchar_t **)((char *)v13 + v34);
    v50 = -1;
    do
      ++v50;
    while ( v49[v50] );
    if ( StringCchCopyW(v47, v50 + 1, v49) < 0 )
    {
      v10 = 122;
      goto LABEL_80;
    }
LABEL_57:
    DeviceTypeIdW = SCardGetDeviceTypeIdW(*(_QWORD *)(a1 + 232), *m, &v63);
    v9 = 0;
    v10 = DeviceTypeIdW;
    if ( DeviceTypeIdW )
    {
      v52 = 32;
      v10 = 0;
      v63 = 32;
    }
    else
    {
      v52 = v63;
    }
    *((_DWORD *)m + 3) = v52;
    m[30] = v7;
    v7 = m;
    v53 = -1;
    do
      ++v53;
    while ( *(_WORD *)(*(_QWORD *)mszReaders + 2LL * pcchReaders + 2 * v53) );
  }
  WppTraceIndent(v45, 2);
  v10 = 8;
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = 196;
    goto LABEL_9;
  }
LABEL_10:
  v9 = 0;
LABEL_80:
  v54 = v61;
  if ( *v61 )
  {
    I_FreeReaderStates(*v61, *v62);
    v55 = v62;
    v9 = 0;
    *v54 = 0;
    *v55 = 0;
  }
  v56 = *(_QWORD **)(a1 + 112);
  if ( v56 )
  {
    I_ReaderListFree(v56);
    v9 = 0;
    *(_QWORD *)(a1 + 112) = 0;
  }
  if ( !v10 )
  {
    v57 = v62;
    *v54 = v13;
    v13 = v9;
    *(_QWORD *)(a1 + 112) = v7;
    v7 = v9;
    *v57 = v5 + 1;
  }
  if ( *(_QWORD *)mszReaders )
    SCardFreeMemory(*(_QWORD *)(a1 + 232), *(LPCVOID *)mszReaders);
  if ( m )
    I_ReaderListFreeItem(m);
  if ( v13 )
    I_FreeReaderStates(v13, v5 + 1);
  if ( v7 )
    I_ReaderListFree(v7);
  return v10;
}

```

## disassembly

```asm
0x18001c158  mov     [rsp-40h+arg_10], r8
0x18001c15d  mov     [rsp-40h+arg_8], rdx
0x18001c162  push    rbp
0x18001c163  push    rbx
0x18001c164  push    rsi
0x18001c165  push    rdi
0x18001c166  push    r12
0x18001c168  push    r13
0x18001c16a  push    r14
0x18001c16c  push    r15
0x18001c16e  mov     rbp, rsp
0x18001c171  sub     rsp, 38h
0x18001c175  xor     eax, eax
0x18001c177  mov     [rbp+pcchReaders], 0FFFFFFFFh
0x18001c17e  mov     r15, rdx
0x18001c181  mov     qword ptr [rbp+mszReaders], rax
0x18001c185  mov     r14, rcx
0x18001c188  mov     [rbp+arg_18], eax
0x18001c18b  mov     rcx, [rcx+0E8h]; hContext
0x18001c192  lea     rdx, mszGroups; "SCard$AllReaders"
0x18001c199  lea     r9, [rbp+pcchReaders]; pcchReaders
0x18001c19d  mov     r13d, eax
0x18001c1a0  lea     r8, [rbp+mszReaders]; mszReaders
0x18001c1a4  mov     edi, eax
0x18001c1a6  mov     r12d, eax
0x18001c1a9  call    cs:__imp_SCardListReadersW
0x18001c1af  xor     r11d, r11d
0x18001c1b2  mov     ebx, eax
0x18001c1b4  test    eax, eax
0x18001c1b6  jz      loc_18001C245
0x18001c1bc  cmp     eax, 8010002Eh
0x18001c1c1  jnz     short loc_18001C23D
0x18001c1c3  mov     ebx, r11d
0x18001c1c6  mov     rcx, cs:hHeap; hHeap
0x18001c1cd  lea     r8d, [r13+1]
0x18001c1d1  shl     r8, 6; dwBytes
0x18001c1d5  mov     edx, 8; dwFlags
0x18001c1da  call    cs:__imp_HeapAlloc
0x18001c1e0  xor     r11d, r11d
0x18001c1e3  mov     rsi, rax
0x18001c1e6  test    rax, rax
0x18001c1e9  jnz     loc_18001C283
0x18001c1ef  lea     edx, [rax+2]
0x18001c1f2  call    WppTraceIndent
0x18001c1f7  lea     ebx, [rsi+8]
0x18001c1fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c201  lea     rdx, WPP_GLOBAL_Control
0x18001c208  cmp     rcx, rdx
0x18001c20b  jz      short loc_18001C235
0x18001c20d  test    byte ptr [rcx+1Ch], 1
0x18001c211  jz      short loc_18001C235
0x18001c213  cmp     byte ptr [rcx+19h], 2
0x18001c217  jb      short loc_18001C235
0x18001c219  mov     edx, 0C2h
0x18001c21e  mov     r9, cs:WPP_pszIndent
0x18001c225  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001c22c  mov     rcx, [rcx+10h]
0x18001c230  call    WPP_SF_s
0x18001c235  xor     r11d, r11d
0x18001c238  jmp     loc_18001C635
0x18001c23d  mov     rsi, r11
0x18001c240  jmp     loc_18001C635
0x18001c245  mov     r8, qword ptr [rbp+mszReaders]
0x18001c249  mov     [rbp+pcchReaders], r11d
0x18001c24d  test    r8, r8
0x18001c250  jz      loc_18001C1C6
0x18001c256  mov     ecx, r11d
0x18001c259  mov     eax, ecx
0x18001c25b  lea     rdx, [r8+rax*2]
0x18001c25f  cmp     r11w, [rdx]
0x18001c263  jz      loc_18001C1C6
0x18001c269  inc     r13d
0x18001c26c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c270  inc     rax
0x18001c273  cmp     [rdx+rax*2], r11w
0x18001c278  jnz     short loc_18001C270
0x18001c27a  inc     ecx
0x18001c27c  add     ecx, eax
0x18001c27e  mov     [rbp+pcchReaders], ecx
0x18001c281  jmp     short loc_18001C259
0x18001c283  mov     rax, [r15]
0x18001c286  test    rax, rax
0x18001c289  jz      short loc_18001C2B0
0x18001c28b  cmp     [rax], r11
0x18001c28e  jz      short loc_18001C2B0
0x18001c290  movups  xmm0, xmmword ptr [rax]
0x18001c293  movups  xmmword ptr [rsi], xmm0
0x18001c296  movups  xmm1, xmmword ptr [rax+10h]
0x18001c29a  movups  xmmword ptr [rsi+10h], xmm1
0x18001c29e  movups  xmm0, xmmword ptr [rax+20h]
0x18001c2a2  movups  xmmword ptr [rsi+20h], xmm0
0x18001c2a6  movups  xmm1, xmmword ptr [rax+30h]
0x18001c2aa  movups  xmmword ptr [rsi+30h], xmm1
0x18001c2ae  jmp     short loc_18001C2C3
0x18001c2b0  mov     eax, r13d
0x18001c2b3  shl     eax, 10h
0x18001c2b6  mov     [rsi+10h], eax
0x18001c2b9  lea     rax, aPnpNotificatio; "\\\\?PnP?\\Notification"
0x18001c2c0  mov     [rsi], rax
0x18001c2c3  mov     r15d, r11d
0x18001c2c6  mov     edx, r11d
0x18001c2c9  mov     [rbp+pcchReaders], edx
0x18001c2cc  mov     rdi, r11
0x18001c2cf  cmp     r15d, r13d
0x18001c2d2  jnb     loc_18001C635
0x18001c2d8  mov     r9d, 1
0x18001c2de  mov     rax, [rbp+arg_10]
0x18001c2e2  cmp     r9d, [rax]
0x18001c2e5  jnb     loc_18001C36E
0x18001c2eb  mov     rax, [rbp+arg_8]
0x18001c2ef  mov     r8, [rax]
0x18001c2f2  test    r8, r8
0x18001c2f5  jz      short loc_18001C36E
0x18001c2f7  mov     rax, qword ptr [rbp+mszReaders]
0x18001c2fb  mov     r11d, r9d
0x18001c2fe  shl     r11, 6
0x18001c302  mov     ecx, edx
0x18001c304  lea     rbx, [rax+rcx*2]
0x18001c308  mov     rax, [r11+r8]
0x18001c30c  sub     rbx, rax
0x18001c30f  movzx   r10d, word ptr [rax]
0x18001c313  movzx   ecx, word ptr [rax+rbx]
0x18001c317  sub     r10d, ecx
0x18001c31a  jnz     short loc_18001C324
0x18001c31c  add     rax, 2
0x18001c320  test    ecx, ecx
0x18001c322  jnz     short loc_18001C30F
0x18001c324  test    r10d, r10d
0x18001c327  jz      short loc_18001C331
0x18001c329  inc     r9d
0x18001c32c  xor     r11d, r11d
0x18001c32f  jmp     short loc_18001C2DE
0x18001c331  movups  xmm0, xmmword ptr [r11+r8]
0x18001c336  lea     ecx, [r15+1]
0x18001c33a  mov     edi, 1
0x18001c33f  shl     rcx, 6
0x18001c343  movups  xmmword ptr [rcx+rsi], xmm0
0x18001c347  movups  xmm1, xmmword ptr [r11+r8+10h]
0x18001c34d  movups  xmmword ptr [rcx+rsi+10h], xmm1
0x18001c352  movups  xmm0, xmmword ptr [r11+r8+20h]
0x18001c358  movups  xmmword ptr [rcx+rsi+20h], xmm0
0x18001c35d  movups  xmm1, xmmword ptr [r11+r8+30h]
0x18001c363  xor     r11d, r11d
0x18001c366  movups  xmmword ptr [rcx+rsi+30h], xmm1
0x18001c36b  mov     edx, [rbp+pcchReaders]
0x18001c36e  mov     rax, qword ptr [rbp+mszReaders]
0x18001c372  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c376  mov     ecx, edx
0x18001c378  lea     rdx, [rax+rcx*2]
0x18001c37c  inc     r8
0x18001c37f  cmp     [rdx+r8*2], r11w
0x18001c384  jnz     short loc_18001C37C
0x18001c386  mov     rcx, cs:hHeap; hHeap
0x18001c38d  lea     r8, ds:2[r8*2]; dwBytes
0x18001c395  mov     edx, 8; dwFlags
0x18001c39a  inc     r15d
0x18001c39d  call    cs:__imp_HeapAlloc
0x18001c3a3  mov     ebx, r15d
0x18001c3a6  xor     r11d, r11d
0x18001c3a9  shl     rbx, 6
0x18001c3ad  mov     [rbx+rsi], rax
0x18001c3b1  test    rax, rax
0x18001c3b4  jz      loc_18001C5E5
0x18001c3ba  mov     edx, [rbp+pcchReaders]
0x18001c3bd  mov     rcx, qword ptr [rbp+mszReaders]
0x18001c3c1  lea     r8, [rcx+rdx*2]; pszSrc
0x18001c3c5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c3c9  inc     rdx
0x18001c3cc  cmp     [r8+rdx*2], r11w
0x18001c3d1  jnz     short loc_18001C3C9
0x18001c3d3  inc     rdx; cchDest
0x18001c3d6  mov     rcx, rax; pszDest
0x18001c3d9  call    StringCchCopyW
0x18001c3de  test    eax, eax
0x18001c3e0  js      loc_18001C5DE
0x18001c3e6  test    edi, edi
0x18001c3e8  jz      short loc_18001C44D
0x18001c3ea  mov     r8, [r14+70h]
0x18001c3ee  mov     rdi, r8
0x18001c3f1  test    rdi, rdi
0x18001c3f4  jz      loc_18001C542
0x18001c3fa  mov     ecx, [rbp+pcchReaders]
0x18001c3fd  mov     rax, qword ptr [rbp+mszReaders]
0x18001c401  mov     r9, [rdi]
0x18001c404  lea     rdx, [rax+rcx*2]
0x18001c408  sub     r9, rdx
0x18001c40b  movzx   ecx, word ptr [rdx]
0x18001c40e  movzx   eax, word ptr [rdx+r9]
0x18001c413  sub     ecx, eax
0x18001c415  jnz     short loc_18001C41F
0x18001c417  add     rdx, 2
0x18001c41b  test    eax, eax
0x18001c41d  jnz     short loc_18001C40B
0x18001c41f  mov     rax, [rdi+0F0h]
0x18001c426  test    ecx, ecx
0x18001c428  jz      short loc_18001C432
0x18001c42a  mov     r8, rdi
0x18001c42d  mov     rdi, rax
0x18001c430  jmp     short loc_18001C3F1
0x18001c432  cmp     rdi, [r14+70h]
0x18001c436  jnz     short loc_18001C441
0x18001c438  mov     [r14+70h], rax
0x18001c43c  jmp     loc_18001C4E7
0x18001c441  mov     [r8+0F0h], rax
0x18001c448  jmp     loc_18001C4E7
0x18001c44d  mov     rcx, cs:hHeap; hHeap
0x18001c454  mov     edx, 8; dwFlags
0x18001c459  mov     r8d, 0F8h; dwBytes
0x18001c45f  mov     dword ptr [rbx+rsi+10h], 10h
0x18001c467  call    cs:__imp_HeapAlloc
0x18001c46d  mov     rdi, rax
0x18001c470  test    rax, rax
0x18001c473  jz      loc_18001C59A
0x18001c479  xor     edx, edx; Val
0x18001c47b  mov     r8d, 0F8h; Size
0x18001c481  mov     rcx, rax; void *
0x18001c484  call    memset_0
0x18001c489  mov     rax, [rbx+rsi]
0x18001c48d  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c491  xor     ecx, ecx
0x18001c493  inc     r8
0x18001c496  cmp     [rax+r8*2], cx
0x18001c49b  jnz     short loc_18001C493
0x18001c49d  mov     rcx, cs:hHeap; hHeap
0x18001c4a4  lea     r8, ds:2[r8*2]; dwBytes
0x18001c4ac  mov     edx, 8; dwFlags
0x18001c4b1  call    cs:__imp_HeapAlloc
0x18001c4b7  xor     r11d, r11d
0x18001c4ba  mov     [rdi], rax
0x18001c4bd  test    rax, rax
0x18001c4c0  jz      loc_18001C556
0x18001c4c6  mov     r8, [rbx+rsi]; pszSrc
0x18001c4ca  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c4ce  inc     rdx
0x18001c4d1  cmp     [r8+rdx*2], r11w
0x18001c4d6  jnz     short loc_18001C4CE
0x18001c4d8  inc     rdx; cchDest
0x18001c4db  mov     rcx, rax; pszDest
0x18001c4de  call    StringCchCopyW
0x18001c4e3  test    eax, eax
0x18001c4e5  js      short loc_18001C54C
0x18001c4e7  mov     rdx, [rdi]
0x18001c4ea  lea     r8, [rbp+arg_18]
0x18001c4ee  mov     rcx, [r14+0E8h]
0x18001c4f5  call    cs:__imp_SCardGetDeviceTypeIdW
0x18001c4fb  xor     r11d, r11d
0x18001c4fe  mov     ebx, eax
0x18001c500  test    eax, eax
0x18001c502  jz      short loc_18001C510
0x18001c504  lea     eax, [r11+20h]
0x18001c508  mov     ebx, r11d
0x18001c50b  mov     [rbp+arg_18], eax
0x18001c50e  jmp     short loc_18001C513
0x18001c510  mov     eax, [rbp+arg_18]
0x18001c513  mov     [rdi+0Ch], eax
0x18001c516  mov     [rdi+0F0h], r12
0x18001c51d  mov     r12, rdi
0x18001c520  mov     rax, qword ptr [rbp+mszReaders]
0x18001c524  mov     edx, [rbp+pcchReaders]
0x18001c527  lea     r8, [rax+rdx*2]
0x18001c52b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001c52f  inc     rax
0x18001c532  cmp     [r8+rax*2], r11w
0x18001c537  jnz     short loc_18001C52F
0x18001c539  inc     edx
0x18001c53b  add     edx, eax
0x18001c53d  jmp     loc_18001C2C9
0x18001c542  mov     ebx, 490h
0x18001c547  jmp     loc_18001C635
0x18001c54c  mov     ebx, 7Ah ; 'z'
0x18001c551  jmp     loc_18001C635
0x18001c556  mov     edx, 2
0x18001c55b  call    WppTraceIndent
0x18001c560  mov     ebx, 8
0x18001c565  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c56c  lea     rdx, WPP_GLOBAL_Control
0x18001c573  cmp     rcx, rdx
0x18001c576  jz      loc_18001C235
0x18001c57c  test    byte ptr [rcx+1Ch], 1
0x18001c580  jz      loc_18001C235
0x18001c586  cmp     byte ptr [rcx+19h], 2
0x18001c58a  jb      loc_18001C235
0x18001c590  mov     edx, 0C5h
0x18001c595  jmp     loc_18001C21E
0x18001c59a  mov     edx, 2
0x18001c59f  call    WppTraceIndent
0x18001c5a4  mov     ebx, 8
0x18001c5a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c5b0  lea     rdx, WPP_GLOBAL_Control
0x18001c5b7  cmp     rcx, rdx
0x18001c5ba  jz      loc_18001C235
0x18001c5c0  test    byte ptr [rcx+1Ch], 1
0x18001c5c4  jz      loc_18001C235
0x18001c5ca  cmp     byte ptr [rcx+19h], 2
0x18001c5ce  jb      loc_18001C235
0x18001c5d4  mov     edx, 0C4h
0x18001c5d9  jmp     loc_18001C21E
0x18001c5de  mov     ebx, 7Ah ; 'z'
0x18001c5e3  jmp     short loc_18001C632
0x18001c5e5  mov     edx, 2
  ... truncated ...
```
