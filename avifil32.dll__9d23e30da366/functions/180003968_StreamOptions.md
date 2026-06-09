# StreamOptions

- ea: `0x180003968`
- end: `0x180003ebc`
- name: `StreamOptions`
- size: `1364`
- prototype: `__int64 __fastcall(HWND hWnd)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003050`

## callees

- `0x180001460`
- `0x180001d0c`
- `0x180003968`
- `0x180008300`
- `0x1800086a0`
- `0x180018010`

## import_xrefs

- `MSVFW32!ICCompressorChoose` at `0x180003af2`
- `MSVFW32!ICCompressorChoose` at `0x180003af2`
- `MSVFW32!ICCompressorFree` at `0x180003ba3`
- `MSVFW32!ICCompressorFree` at `0x180003ba3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180003d2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalReAlloc` at `0x180003d2e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003cfb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003e92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003cfb`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180003e92`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003d37`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003de3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003d37`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180003de3`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003cf2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003d1c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e89`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e9f`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003cf2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003d1c`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e89`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180003e9f`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003cde`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003dda`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003cde`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180003dda`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003ea8`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180003ea8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c20`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c01`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180003c20`
- `MSACM32!acmFormatChooseW` at `0x180003e48`
- `MSACM32!acmFormatChooseW` at `0x180003e48`
- `MSACM32!acmMetrics` at `0x180003ca7`
- `MSACM32!acmMetrics` at `0x180003ca7`
- `MSACM32!acmGetVersion` at `0x180003bdc`
- `MSACM32!acmGetVersion` at `0x180003bdc`
- `USER32!MessageBeep` at `0x180003e77`
- `USER32!MessageBeep` at `0x180003e77`
- `USER32!MessageBoxW` at `0x180003c3d`
- `USER32!MessageBoxW` at `0x180003c3d`

## pseudocode

```c
__int64 __fastcall StreamOptions(HWND hWnd)
{
  __int64 v2; // rbx
  __int64 v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  unsigned int v7; // ebx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // rax
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned int v17; // edx
  HGLOBAL v18; // rax
  HGLOBAL v19; // rax
  SIZE_T v20; // rbx
  HGLOBAL v21; // rax
  LPVOID v22; // rax
  __int64 v23; // rax
  unsigned int v24; // eax
  int v25; // eax
  HGLOBAL v26; // rax
  LPWAVEFORMATEX pwfxEnum; // rbx
  unsigned int v28; // eax
  MMRESULT v29; // edi
  HGLOBAL v30; // rax
  HGLOBAL v31; // rax
  unsigned int pMetric; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v33[3]; // [rsp+34h] [rbp-CCh] BYREF
  tACMFORMATCHOOSEW pafmtc; // [rsp+40h] [rbp-C0h] BYREF
  struct _AVISTREAMINFOW psi; // [rsp+200h] [rbp+100h] BYREF
  WCHAR Caption[40]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR Buffer[160]; // [rsp+320h] [rbp+220h] BYREF

  memset_0(&psi, 0, sizeof(psi));
  pMetric = 0;
  if ( AVIStreamInfoW(*(PAVISTREAM *)(gapAVI + 8LL * gnCurStream), &psi, 204) )
    return 0;
  if ( psi.fccType == 1935960438 )
  {
    v2 = gnCurStream;
    v3 = gapOpt;
    v4 = *(_QWORD *)(gapOpt + 8LL * gnCurStream);
    if ( (*(_BYTE *)(v4 + 20) & 8) == 0 )
    {
      *(_OWORD *)v4 = 0;
      *(_OWORD *)(v4 + 16) = 0;
      *(_OWORD *)(v4 + 32) = 0;
      *(_QWORD *)(v4 + 48) = 0;
      *(_DWORD *)(*(_QWORD *)(v3 + 8 * v2) + 4LL) = 541215044;
      *(_DWORD *)(*(_QWORD *)(v3 + 8 * v2) + 12LL) = -1;
    }
    memset_0(&gCompVars.hic, 0, 0x58u);
    gCompVars.cbSize = 96;
    gCompVars.dwFlags = 1;
    gCompVars.fccHandler = *(_DWORD *)(*(_QWORD *)(v3 + 8 * v2) + 4LL);
    gCompVars.lQ = *(_DWORD *)(*(_QWORD *)(v3 + 8 * v2) + 12LL);
    gCompVars.lpState = *(LPVOID *)(*(_QWORD *)(v3 + 8 * v2) + 40LL);
    gCompVars.cbState = *(_DWORD *)(*(_QWORD *)(v3 + 8 * v2) + 48LL);
    v5 = *(_QWORD *)(v3 + 8 * v2);
    if ( (*(_BYTE *)(v5 + 20) & 4) != 0 )
      gCompVars.lKey = *(_DWORD *)(v5 + 8);
    else
      gCompVars.lKey = 0;
    v6 = *(_QWORD *)(v3 + 8 * v2);
    if ( (*(_BYTE *)(v6 + 20) & 2) != 0 )
      gCompVars.lDataRate = *(_DWORD *)(v6 + 16) >> 10;
    else
      gCompVars.lDataRate = 0;
    v7 = ICCompressorChoose(hWnd, guiFlags, 0, *(LPVOID *)(gapAVI + 8 * v2), &gCompVars, 0);
    v8 = gnCurStream;
    v9 = gapOpt;
    *(_QWORD *)(*(_QWORD *)(gapOpt + 8LL * gnCurStream) + 40LL) = gCompVars.lpState;
    *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 48LL) = gCompVars.cbState;
    gCompVars.lpState = 0;
    *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 4LL) = gCompVars.fccHandler;
    *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 12LL) = gCompVars.lQ;
    *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 8LL) = gCompVars.lKey;
    *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 16LL) = gCompVars.lDataRate << 10;
    v10 = *(_QWORD *)(v9 + 8 * v8);
    if ( gCompVars.lKey )
      *(_DWORD *)(v10 + 20) |= 4u;
    else
      *(_DWORD *)(v10 + 20) &= ~4u;
    v11 = *(_QWORD *)(v9 + 8 * v8);
    if ( gCompVars.lDataRate )
      *(_DWORD *)(v11 + 20) |= 2u;
    else
      *(_DWORD *)(v11 + 20) &= ~2u;
    if ( v7 )
      *(_DWORD *)(*(_QWORD *)(v9 + 8 * v8) + 20LL) |= 8u;
    ICCompressorFree(&gCompVars);
    return v7;
  }
  v7 = 0;
  if ( psi.fccType == 1935963489 )
  {
    memset_0(&pafmtc, 0, sizeof(pafmtc));
    v33[0] = 0;
    if ( acmGetVersion() < 0x2000000 )
    {
      LoadStringW(ghMod, 0xBAu, Buffer, 160);
      LoadStringW(ghMod, 0xBBu, Caption, 40);
      MessageBoxW(hWnd, Buffer, Caption, 0x10u);
      return 0;
    }
    memset_0(&pafmtc.fdwStyle, 0, 0x1B8u);
    pafmtc.cbStruct = 444;
    v13 = *(_BYTE *)(*(_QWORD *)(gapOpt + 8LL * gnCurStream) + 20LL) & 8;
    pafmtc.hwndOwner = hWnd;
    pafmtc.fdwStyle = 8 * v13;
    acmMetrics(0, 0x32u, &pMetric);
    LODWORD(v14) = gnCurStream;
    v15 = gapOpt;
    v16 = *(_QWORD *)(gapOpt + 8LL * gnCurStream);
    v17 = *(_DWORD *)(v16 + 32);
    if ( v17 && *(_QWORD *)(v16 + 24) || !pMetric )
    {
      if ( v17 >= pMetric || !pMetric )
      {
LABEL_32:
        v23 = *(_QWORD *)(v15 + 8LL * (int)v14);
        if ( *(_QWORD *)(v23 + 24) )
        {
          pafmtc.pwfx = *(LPWAVEFORMATEX *)(v23 + 24);
          pafmtc.cbwfx = *(_DWORD *)(*(_QWORD *)(v15 + 8LL * (int)v14) + 32LL);
          v24 = AVIStreamStart(*(PAVISTREAM *)(gapAVI + 8LL * (int)v14));
          (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _DWORD *))(**(_QWORD **)(gapAVI + 8LL * gnCurStream) + 48LL))(
            *(_QWORD *)(gapAVI + 8LL * gnCurStream),
            v24,
            0,
            v33);
          v25 = v33[0];
          if ( (unsigned __int64)v33[0] <= 0x12 )
            v25 = 18;
          v33[0] = v25;
          v26 = GlobalAlloc(0x42u, v25);
          pafmtc.pwfxEnum = (LPWAVEFORMATEX)GlobalLock(v26);
          pwfxEnum = pafmtc.pwfxEnum;
          if ( pafmtc.pwfxEnum )
          {
            v28 = AVIStreamStart(*(PAVISTREAM *)(gapAVI + 8LL * gnCurStream));
            (*(void (__fastcall **)(_QWORD, _QWORD, LPWAVEFORMATEX, _DWORD *))(**(_QWORD **)(gapAVI + 8LL * gnCurStream)
                                                                             + 48LL))(
              *(_QWORD *)(gapAVI + 8LL * gnCurStream),
              v28,
              pwfxEnum,
              v33);
            pafmtc.fdwEnum |= 0x100000u;
          }
          v29 = acmFormatChooseW(&pafmtc);
          if ( v29 )
          {
            if ( v29 != 515 )
              MessageBeep(0);
          }
          else
          {
            *(_DWORD *)(*(_QWORD *)(gapOpt + 8LL * gnCurStream) + 20LL) |= 8u;
          }
          if ( pafmtc.pwfxEnum )
          {
            v30 = GlobalHandle(pafmtc.pwfxEnum);
            GlobalUnlock(v30);
            v31 = GlobalHandle(pafmtc.pwfxEnum);
            GlobalFree(v31);
          }
          return v29 == 0;
        }
        return 0;
      }
      v19 = GlobalHandle(*(LPCVOID *)(v16 + 24));
      GlobalUnlock(v19);
      v20 = (int)pMetric;
      v21 = GlobalHandle(*(LPCVOID *)(*(_QWORD *)(gapOpt + 8LL * gnCurStream) + 24LL));
      v18 = GlobalReAlloc(v21, v20, 2u);
    }
    else
    {
      v18 = GlobalAlloc(2u, (int)pMetric);
    }
    v22 = GlobalLock(v18);
    v14 = gnCurStream;
    v15 = gapOpt;
    *(_QWORD *)(*(_QWORD *)(gapOpt + 8LL * gnCurStream) + 24LL) = v22;
    *(_DWORD *)(*(_QWORD *)(v15 + 8 * v14) + 32LL) = pMetric;
    goto LABEL_32;
  }
  return v7;
}

```

## disassembly

```asm
0x180003968  push    rbp
0x18000396a  push    rbx
0x18000396b  push    rsi
0x18000396c  push    rdi
0x18000396d  lea     rbp, [rsp-378h]
0x180003975  sub     rsp, 478h
0x18000397c  mov     rax, cs:__security_cookie
0x180003983  xor     rax, rsp
0x180003986  mov     [rbp+390h+var_30], rax
0x18000398d  mov     rsi, rcx
0x180003990  mov     ebx, 0CCh
0x180003995  mov     r8d, ebx; Size
0x180003998  lea     rcx, [rbp+390h+psi]; void *
0x18000399f  xor     edx, edx; Val
0x1800039a1  call    memset_0
0x1800039a6  movsxd  rax, cs:gnCurStream
0x1800039ad  lea     rdx, [rbp+390h+psi]; psi
0x1800039b4  mov     rcx, cs:gapAVI
0x1800039bb  mov     r8d, ebx; lSize
0x1800039be  mov     [rsp+490h+pMetric], 0
0x1800039c6  mov     rcx, [rcx+rax*8]; pavi
0x1800039ca  call    AVIStreamInfoW
0x1800039cf  test    eax, eax
0x1800039d1  jnz     loc_180003C43
0x1800039d7  cmp     [rbp+390h+psi.fccType], 73646976h
0x1800039e1  jnz     loc_180003BAE
0x1800039e7  movsxd  rbx, cs:gnCurStream
0x1800039ee  mov     rdi, cs:gapOpt
0x1800039f5  mov     rax, [rdi+rbx*8]
0x1800039f9  test    byte ptr [rax+14h], 8
0x1800039fd  jnz     short loc_180003A29
0x1800039ff  xorps   xmm0, xmm0
0x180003a02  xor     ecx, ecx
0x180003a04  movups  xmmword ptr [rax], xmm0
0x180003a07  movups  xmmword ptr [rax+10h], xmm0
0x180003a0b  movups  xmmword ptr [rax+20h], xmm0
0x180003a0f  mov     [rax+30h], rcx
0x180003a13  mov     rax, [rdi+rbx*8]
0x180003a17  mov     dword ptr [rax+4], 20424944h
0x180003a1e  mov     rax, [rdi+rbx*8]
0x180003a22  mov     dword ptr [rax+0Ch], 0FFFFFFFFh
0x180003a29  xor     edx, edx; Val
0x180003a2b  lea     rcx, gCompVars.hic; void *
0x180003a32  lea     r8d, [rdx+58h]; Size
0x180003a36  call    memset_0
0x180003a3b  mov     cs:gCompVars.cbSize, 60h ; '`'
0x180003a45  mov     cs:gCompVars.dwFlags, 1
0x180003a4f  mov     rax, [rdi+rbx*8]
0x180003a53  mov     ecx, [rax+4]
0x180003a56  mov     cs:gCompVars.fccHandler, ecx
0x180003a5c  mov     rax, [rdi+rbx*8]
0x180003a60  mov     ecx, [rax+0Ch]
0x180003a63  mov     cs:gCompVars.lQ, ecx
0x180003a69  mov     rax, [rdi+rbx*8]
0x180003a6d  mov     rcx, [rax+28h]
0x180003a71  mov     cs:gCompVars.lpState, rcx
0x180003a78  mov     rax, [rdi+rbx*8]
0x180003a7c  mov     ecx, [rax+30h]
0x180003a7f  mov     cs:gCompVars.cbState, ecx
0x180003a85  mov     rax, [rdi+rbx*8]
0x180003a89  test    byte ptr [rax+14h], 4
0x180003a8d  jz      short loc_180003A9A
0x180003a8f  mov     eax, [rax+8]
0x180003a92  mov     cs:gCompVars.lKey, eax
0x180003a98  jmp     short loc_180003AA4
0x180003a9a  mov     cs:gCompVars.lKey, 0
0x180003aa4  mov     rax, [rdi+rbx*8]
0x180003aa8  test    byte ptr [rax+14h], 2
0x180003aac  jz      short loc_180003ABC
0x180003aae  mov     eax, [rax+10h]
0x180003ab1  shr     eax, 0Ah
0x180003ab4  mov     cs:gCompVars.lDataRate, eax
0x180003aba  jmp     short loc_180003AC6
0x180003abc  mov     cs:gCompVars.lDataRate, 0
0x180003ac6  mov     r9, cs:gapAVI
0x180003acd  lea     rdi, gCompVars
0x180003ad4  mov     edx, cs:guiFlags; uiFlags
0x180003ada  xor     r8d, r8d; pvIn
0x180003add  mov     [rsp+490h+lpszTitle], 0; lpszTitle
0x180003ae6  mov     rcx, rsi; hwnd
0x180003ae9  mov     [rsp+490h+pc], rdi; pc
0x180003aee  mov     r9, [r9+rbx*8]; lpData
0x180003af2  call    cs:__imp_ICCompressorChoose
0x180003af8  mov     rcx, cs:gCompVars.lpState
0x180003aff  mov     ebx, eax
0x180003b01  movsxd  r8, cs:gnCurStream
0x180003b08  mov     r9, cs:gapOpt
0x180003b0f  mov     rdx, [r9+r8*8]
0x180003b13  mov     [rdx+28h], rcx
0x180003b17  mov     rdx, [r9+r8*8]
0x180003b1b  mov     ecx, cs:gCompVars.cbState
0x180003b21  mov     [rdx+30h], ecx
0x180003b24  mov     ecx, cs:gCompVars.fccHandler
0x180003b2a  mov     cs:gCompVars.lpState, 0
0x180003b35  mov     rdx, [r9+r8*8]
0x180003b39  mov     [rdx+4], ecx
0x180003b3c  mov     eax, cs:gCompVars.lQ
0x180003b42  mov     rcx, [r9+r8*8]
0x180003b46  mov     [rcx+0Ch], eax
0x180003b49  mov     rcx, [r9+r8*8]
0x180003b4d  mov     eax, cs:gCompVars.lKey
0x180003b53  mov     [rcx+8], eax
0x180003b56  mov     rax, [r9+r8*8]
0x180003b5a  mov     ecx, cs:gCompVars.lDataRate
0x180003b60  shl     ecx, 0Ah
0x180003b63  mov     [rax+10h], ecx
0x180003b66  cmp     cs:gCompVars.lKey, 0
0x180003b6d  mov     rax, [r9+r8*8]
0x180003b71  jz      short loc_180003B79
0x180003b73  or      dword ptr [rax+14h], 4
0x180003b77  jmp     short loc_180003B7D
0x180003b79  and     dword ptr [rax+14h], 0FFFFFFFBh
0x180003b7d  cmp     cs:gCompVars.lDataRate, 0
0x180003b84  mov     rax, [r9+r8*8]
0x180003b88  jz      short loc_180003B90
0x180003b8a  or      dword ptr [rax+14h], 2
0x180003b8e  jmp     short loc_180003B94
0x180003b90  and     dword ptr [rax+14h], 0FFFFFFFDh
0x180003b94  test    ebx, ebx
0x180003b96  jz      short loc_180003BA0
0x180003b98  mov     rax, [r9+r8*8]
0x180003b9c  or      dword ptr [rax+14h], 8
0x180003ba0  mov     rcx, rdi; pc
0x180003ba3  call    cs:__imp_ICCompressorFree
0x180003ba9  jmp     loc_180003EB5
0x180003bae  xor     ebx, ebx
0x180003bb0  cmp     [rbp+390h+psi.fccType], 73647561h
0x180003bba  jnz     loc_180003EB5
0x180003bc0  mov     ebx, 1BCh
0x180003bc5  lea     rcx, [rsp+490h+pafmtc]; void *
0x180003bca  mov     r8d, ebx; Size
0x180003bcd  xor     edx, edx; Val
0x180003bcf  call    memset_0
0x180003bd4  mov     [rsp+490h+var_45C], 0
0x180003bdc  call    cs:__imp_acmGetVersion
0x180003be2  cmp     eax, 2000000h
0x180003be7  jnb     short loc_180003C60
0x180003be9  mov     rcx, cs:ghMod; hInstance
0x180003bf0  lea     r8, [rbp+390h+Buffer]; lpBuffer
0x180003bf7  mov     r9d, 0A0h; cchBufferMax
0x180003bfd  lea     edx, [r9+1Ah]; uID
0x180003c01  call    cs:__imp_LoadStringW
0x180003c07  mov     rcx, cs:ghMod; hInstance
0x180003c0e  lea     r8, [rbp+390h+Caption]; lpBuffer
0x180003c15  mov     r9d, 28h ; '('; cchBufferMax
0x180003c1b  mov     edx, 0BBh; uID
0x180003c20  call    cs:__imp_LoadStringW
0x180003c26  mov     r9d, 10h; uType
0x180003c2c  lea     r8, [rbp+390h+Caption]; lpCaption
0x180003c33  lea     rdx, [rbp+390h+Buffer]; lpText
0x180003c3a  mov     rcx, rsi; hWnd
0x180003c3d  call    cs:__imp_MessageBoxW
0x180003c43  xor     eax, eax
0x180003c45  mov     rcx, [rbp+390h+var_30]
0x180003c4c  xor     rcx, rsp; StackCookie
0x180003c4f  call    __security_check_cookie
0x180003c54  add     rsp, 478h
0x180003c5b  pop     rdi
0x180003c5c  pop     rsi
0x180003c5d  pop     rbx
0x180003c5e  pop     rbp
0x180003c5f  retn
0x180003c60  xor     edx, edx; Val
0x180003c62  lea     rcx, [rsp+490h+pafmtc.fdwStyle]; void *
0x180003c67  mov     r8d, 1B8h; Size
0x180003c6d  call    memset_0
0x180003c72  mov     rax, cs:gapOpt
0x180003c79  lea     r8, [rsp+490h+pMetric]; pMetric
0x180003c7e  movsxd  rcx, cs:gnCurStream
0x180003c85  mov     edx, 32h ; '2'; uMetric
0x180003c8a  mov     [rsp+490h+pafmtc.cbStruct], ebx
0x180003c8e  mov     rcx, [rax+rcx*8]
0x180003c92  movzx   eax, byte ptr [rcx+14h]
0x180003c96  xor     ecx, ecx; hao
0x180003c98  and     eax, 8
0x180003c9b  mov     [rsp+490h+pafmtc.hwndOwner], rsi
0x180003ca0  shl     eax, 3
0x180003ca3  mov     [rsp+490h+pafmtc.fdwStyle], eax
0x180003ca7  call    cs:__imp_acmMetrics
0x180003cad  movsxd  r9, cs:gnCurStream
0x180003cb4  mov     r8, cs:gapOpt
0x180003cbb  movsxd  rax, [rsp+490h+pMetric]
0x180003cc0  mov     rcx, [r8+r9*8]
0x180003cc4  mov     edx, [rcx+20h]
0x180003cc7  test    edx, edx
0x180003cc9  jz      short loc_180003CD2
0x180003ccb  cmp     qword ptr [rcx+18h], 0
0x180003cd0  jnz     short loc_180003CE6
0x180003cd2  test    eax, eax
0x180003cd4  jz      short loc_180003CE6
0x180003cd6  mov     rdx, rax; dwBytes
0x180003cd9  mov     ecx, 2; uFlags
0x180003cde  call    cs:__imp_GlobalAlloc
0x180003ce4  jmp     short loc_180003D34
0x180003ce6  cmp     edx, eax
0x180003ce8  jnb     short loc_180003D5E
0x180003cea  test    eax, eax
0x180003cec  jz      short loc_180003D5E
0x180003cee  mov     rcx, [rcx+18h]; pMem
0x180003cf2  call    cs:__imp_GlobalHandle
0x180003cf8  mov     rcx, rax; hMem
0x180003cfb  call    cs:__imp_GlobalUnlock
0x180003d01  movsxd  rcx, cs:gnCurStream
0x180003d08  mov     rax, cs:gapOpt
0x180003d0f  movsxd  rbx, [rsp+490h+pMetric]
0x180003d14  mov     rcx, [rax+rcx*8]
0x180003d18  mov     rcx, [rcx+18h]; pMem
0x180003d1c  call    cs:__imp_GlobalHandle
0x180003d22  mov     r8d, 2; uFlags
0x180003d28  mov     rdx, rbx; dwBytes
0x180003d2b  mov     rcx, rax; hMem
0x180003d2e  call    cs:__imp_GlobalReAlloc
0x180003d34  mov     rcx, rax; hMem
0x180003d37  call    cs:__imp_GlobalLock
0x180003d3d  movsxd  r9, cs:gnCurStream
0x180003d44  mov     r8, cs:gapOpt
0x180003d4b  mov     rcx, [r8+r9*8]
0x180003d4f  mov     [rcx+18h], rax
0x180003d53  mov     rcx, [r8+r9*8]
0x180003d57  mov     eax, [rsp+490h+pMetric]
0x180003d5b  mov     [rcx+20h], eax
0x180003d5e  movsxd  rdx, r9d
0x180003d61  mov     rax, [r8+rdx*8]
0x180003d65  mov     rcx, [rax+18h]
0x180003d69  test    rcx, rcx
0x180003d6c  jz      loc_180003C43
0x180003d72  mov     [rsp+490h+pafmtc.pwfx], rcx
0x180003d77  mov     rax, [r8+rdx*8]
0x180003d7b  mov     ecx, [rax+20h]
0x180003d7e  mov     [rsp+490h+pafmtc.cbwfx], ecx
0x180003d82  mov     rcx, cs:gapAVI
0x180003d89  mov     rcx, [rcx+rdx*8]; pavi
0x180003d8d  call    AVIStreamStart
0x180003d92  movsxd  rdx, cs:gnCurStream
0x180003d99  lea     r9, [rsp+490h+var_45C]
0x180003d9e  mov     rcx, cs:gapAVI
0x180003da5  mov     r10d, eax
0x180003da8  xor     r8d, r8d
0x180003dab  mov     rcx, [rcx+rdx*8]
0x180003daf  mov     rdx, [rcx]
0x180003db2  mov     rax, [rdx+30h]
0x180003db6  mov     edx, r10d
0x180003db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dbe  movsxd  rax, [rsp+490h+var_45C]
0x180003dc3  cmp     rax, 12h
0x180003dc7  ja      short loc_180003DCE
0x180003dc9  mov     eax, 12h
0x180003dce  movsxd  rdx, eax; dwBytes
0x180003dd1  mov     ecx, 42h ; 'B'; uFlags
0x180003dd6  mov     [rsp+490h+var_45C], eax
0x180003dda  call    cs:__imp_GlobalAlloc
0x180003de0  mov     rcx, rax; hMem
0x180003de3  call    cs:__imp_GlobalLock
0x180003de9  mov     [rbp+390h+pafmtc.pwfxEnum], rax
0x180003df0  mov     rbx, rax
0x180003df3  test    rax, rax
0x180003df6  jz      short loc_180003E43
0x180003df8  movsxd  rdx, cs:gnCurStream
0x180003dff  mov     rcx, cs:gapAVI
0x180003e06  mov     rcx, [rcx+rdx*8]; pavi
0x180003e0a  call    AVIStreamStart
0x180003e0f  movsxd  rdx, cs:gnCurStream
0x180003e16  lea     r9, [rsp+490h+var_45C]
0x180003e1b  mov     rcx, cs:gapAVI
0x180003e22  mov     r10d, eax
0x180003e25  mov     r8, rbx
0x180003e28  mov     rcx, [rcx+rdx*8]
0x180003e2c  mov     rdx, [rcx]
0x180003e2f  mov     rax, [rdx+30h]
0x180003e33  mov     edx, r10d
0x180003e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3b  bts     [rbp+390h+pafmtc.fdwEnum], 14h
0x180003e43  lea     rcx, [rsp+490h+pafmtc]; pafmtc
0x180003e48  call    cs:__imp_acmFormatChooseW
0x180003e4e  mov     edi, eax
0x180003e50  test    eax, eax
0x180003e52  jnz     short loc_180003E6D
0x180003e54  movsxd  rdx, cs:gnCurStream
0x180003e5b  mov     rcx, cs:gapOpt
0x180003e62  mov     r8, [rcx+rdx*8]
0x180003e66  or      dword ptr [r8+14h], 8
0x180003e6b  jmp     short loc_180003E7D
0x180003e6d  cmp     edi, 203h
0x180003e73  jz      short loc_180003E7D
0x180003e75  xor     ecx, ecx; uType
0x180003e77  call    cs:__imp_MessageBeep
0x180003e7d  mov     rcx, [rbp+390h+pafmtc.pwfxEnum]; pMem
0x180003e84  test    rcx, rcx
0x180003e87  jz      short loc_180003EAE
0x180003e89  call    cs:__imp_GlobalHandle
0x180003e8f  mov     rcx, rax; hMem
0x180003e92  call    cs:__imp_GlobalUnlock
0x180003e98  mov     rcx, [rbp+390h+pafmtc.pwfxEnum]; pMem
0x180003e9f  call    cs:__imp_GlobalHandle
0x180003ea5  mov     rcx, rax; hMem
0x180003ea8  call    cs:__imp_GlobalFree
0x180003eae  xor     ebx, ebx
0x180003eb0  test    edi, edi
0x180003eb2  setz    bl
0x180003eb5  mov     eax, ebx
  ... truncated ...
```
