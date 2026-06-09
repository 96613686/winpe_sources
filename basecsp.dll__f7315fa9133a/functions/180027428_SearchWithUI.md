# SearchWithUI

- ea: `0x180027428`
- end: `0x1800279ca`
- name: `SearchWithUI`
- size: `1442`
- prototype: `__int64 __fastcall(struct _CARD_MATCH_DATA *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026728`

## callees

- `0x18000a772`
- `0x18000de80`
- `0x180016eb0`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x180025fe0`
- `0x180026064`
- `0x180027428`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18002756b`
- `msvcrt!memcpy_s` at `0x18002756b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800277f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800277f6`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180027713`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x180027713`

## pseudocode

```c
__int64 __fastcall SearchWithUI(struct _CARD_MATCH_DATA *a1, struct _CARD_STATE **a2)
{
  bool v3; // zf
  ULONG ulInAuthBufferSize; // r13d
  unsigned __int16 *v5; // rax
  __int64 v6; // rcx
  unsigned __int16 *v7; // rdi
  int v8; // ebx
  PVOID v9; // rcx
  unsigned int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rax
  unsigned int v13; // ebx
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rax
  __int64 v18; // rcx
  DWORD v19; // eax
  unsigned int *v20; // r14
  unsigned __int16 *v21; // rax
  __int64 v22; // rcx
  unsigned __int16 *v23; // r12
  _BYTE *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rcx
  unsigned __int16 *v27; // rax
  size_t v29; // rbx
  unsigned __int16 *v30; // rax
  __int64 v31; // rcx
  unsigned __int16 *v32; // r15
  __int64 v33; // rcx
  _CREDUI_INFOW pUiInfo; // [rsp+50h] [rbp-19h] BYREF
  ULONG pulOutAuthBufferSize; // [rsp+D0h] [rbp+67h] BYREF
  struct _CARD_STATE **v36; // [rsp+D8h] [rbp+6Fh]
  ULONG pulAuthPackage; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+7Fh] BYREF

  v36 = a2;
  pulAuthPackage = -629;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  pv = 0;
  pulOutAuthBufferSize = 0;
  WppTraceIndent((__int64)a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v3 = *((_DWORD *)a1 + 9) == 2;
  *((_DWORD *)a1 + 299) = 1;
  if ( v3 )
  {
    ulInAuthBufferSize = *((_DWORD *)a1 + 298) + 40;
    v5 = (unsigned __int16 *)MIDL_user_allocate(ulInAuthBufferSize);
    v7 = v5;
    if ( !v5 )
    {
      WppTraceIndent(v6, 2u);
      v8 = 8;
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          107,
          &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
          WPP_pszIndent);
      }
      goto LABEL_42;
    }
    memset_0(v5, 0, ulInAuthBufferSize);
    *((_DWORD *)v7 + 2) = 2;
    *((_DWORD *)v7 + 5) = *((_DWORD *)a1 + 14);
    *((_DWORD *)v7 + 3) = 40;
    v10 = *((_DWORD *)a1 + 298);
    *((_DWORD *)v7 + 4) = v10;
    memcpy_s(v7 + 20, v10, *((const void *const *)a1 + 148), *((unsigned int *)a1 + 298));
    goto LABEL_28;
  }
  v11 = *((_QWORD *)a1 + 145);
  v12 = -1;
  v13 = 0;
  v14 = 0;
  if ( v11 )
  {
    v15 = -1;
    do
      ++v15;
    while ( *(_WORD *)(v11 + 2 * v15) );
    v13 = v15 + 1;
  }
  v16 = *((_QWORD *)a1 + 146);
  if ( v16 )
  {
    do
      ++v12;
    while ( *(_WORD *)(v16 + 2 * v12) );
    v14 = v12 + 1;
  }
  ulInAuthBufferSize = 2 * (v14 + v13) + 40;
  v17 = (unsigned __int16 *)MIDL_user_allocate(ulInAuthBufferSize);
  v7 = v17;
  if ( v17 )
  {
    memset_0(v17, 0, 2 * (v14 + v13) + 40);
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 7) = *((_DWORD *)a1 + 14);
    *((_DWORD *)v7 + 8) = *((_DWORD *)a1 + 8);
    *((_DWORD *)v7 + 5) = 2 * v13 + 40;
    *((_DWORD *)v7 + 3) = 40;
    *((_DWORD *)v7 + 4) = v13;
    *((_DWORD *)v7 + 6) = v14;
    if ( v13 )
    {
      v8 = StringCchCopyW(v7 + 20, v13, *((const unsigned __int16 **)a1 + 145));
      if ( v8 < 0 )
        goto LABEL_42;
    }
    if ( *((_DWORD *)v7 + 6) )
    {
      v8 = StringCchCopyW(
             (unsigned __int16 *)((char *)v7 + *((unsigned int *)v7 + 5)),
             *((unsigned int *)v7 + 6),
             *((const unsigned __int16 **)a1 + 146));
      if ( v8 < 0 )
        goto LABEL_42;
    }
LABEL_28:
    *(_DWORD *)v7 = *((_DWORD *)a1 + 22);
    *((_DWORD *)v7 + 1) = *((_DWORD *)a1 + 23);
    pUiInfo.hwndParent = (HWND)*((_QWORD *)a1 + 5);
    pUiInfo.pszCaptionText = (PCWSTR)*((_QWORD *)a1 + 143);
    pUiInfo.pszMessageText = (PCWSTR)*((_QWORD *)a1 + 144);
    pUiInfo.cbSize = 40;
    pUiInfo.hbmBanner = 0;
    v19 = CredUIPromptForWindowsCredentialsW(
            &pUiInfo,
            0,
            &pulAuthPackage,
            v7,
            ulInAuthBufferSize,
            &pv,
            &pulOutAuthBufferSize,
            0,
            0x10u);
    v8 = v19;
    if ( v19 == 1223 )
    {
      v8 = -2146434962;
    }
    else if ( !v19 )
    {
      if ( pulOutAuthBufferSize >= 0x10
        && (v20 = (unsigned int *)pv, *((_DWORD *)pv + 1))
        && *((_DWORD *)pv + 3)
        && (v9 = (PVOID)(2LL * *((unsigned int *)pv + 1)),
            pulOutAuthBufferSize >= (unsigned __int64)v9 + *(unsigned int *)pv)
        && pulOutAuthBufferSize >= *((unsigned int *)pv + 2) + 2 * (unsigned __int64)*((unsigned int *)pv + 3) )
      {
        v21 = (unsigned __int16 *)MIDL_user_allocate((size_t)v9);
        v23 = v21;
        if ( v21 )
        {
          memset_0(v21, 0, 2LL * v20[1]);
          v8 = StringCchCopyNW(v23, v20[1], (const unsigned __int16 *)((char *)v20 + *v20), v20[1]);
          if ( v8 >= 0 )
          {
            v29 = 2LL * (v20[3] + 1);
            v30 = (unsigned __int16 *)MIDL_user_allocate(v29);
            v32 = v30;
            if ( v30 )
            {
              memset_0(v30, 0, v29);
              v8 = StringCchCopyNW(v32, v20[3], (const unsigned __int16 *)((char *)v20 + v20[2]), v20[3]);
              if ( v8 >= 0 )
              {
                v8 = VerifyCard(v23, v32, a1, v36);
                if ( v8 )
                {
                  WppTraceIndent(v33, 2u);
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    WPP_SF_sD(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      111,
                      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
                      (_DWORD)WPP_pszIndent,
                      v8);
                  }
                }
              }
              CspFreeH(v32);
            }
            else
            {
              WppTraceIndent(v31, 2u);
              v8 = 8;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  110,
                  &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
                  WPP_pszIndent);
              }
            }
          }
          CspFreeH(v23);
        }
        else
        {
          WppTraceIndent(v22, 2u);
          v8 = 8;
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              109,
              &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
              WPP_pszIndent);
          }
        }
      }
      else
      {
        v8 = 13;
      }
    }
    goto LABEL_42;
  }
  WppTraceIndent(v18, 2u);
  v8 = 8;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
LABEL_42:
  v24 = pv;
  if ( pv )
  {
    v25 = pulOutAuthBufferSize;
    if ( pulOutAuthBufferSize )
    {
      do
      {
        *v24++ = 0;
        --v25;
      }
      while ( v25 );
    }
    CoTaskMemFree(pv);
  }
  if ( v7 )
  {
    v26 = ulInAuthBufferSize;
    v27 = v7;
    if ( ulInAuthBufferSize )
    {
      do
      {
        *(_BYTE *)v27 = 0;
        v27 = (unsigned __int16 *)((char *)v27 + 1);
        --v26;
      }
      while ( v26 );
    }
    CspFreeH(v7);
  }
  WppTraceIndent((__int64)v9, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      112,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      v8);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180027428  mov     [rsp-8+arg_8], rdx
0x18002742d  push    rbp
0x18002742e  push    rbx
0x18002742f  push    rsi
0x180027430  push    rdi
0x180027431  push    r12
0x180027433  push    r13
0x180027435  push    r14
0x180027437  push    r15
0x180027439  lea     rbp, [rsp-1Fh]
0x18002743e  sub     rsp, 88h
0x180027445  xorps   xmm0, xmm0
0x180027448  mov     [rbp+57h+pulAuthPackage], 0FFFFFD8Bh
0x18002744f  xor     r12d, r12d
0x180027452  xor     eax, eax
0x180027454  xor     edx, edx
0x180027456  mov     [rbp+57h+pUiInfo.hbmBanner], rax
0x18002745a  movups  xmmword ptr [rbp+57h+pUiInfo.cbSize], xmm0
0x18002745e  mov     [rbp+57h+pv], r12
0x180027462  mov     rsi, rcx
0x180027465  movups  xmmword ptr [rbp+57h+pUiInfo.pszMessageText], xmm0
0x180027469  mov     [rbp+57h+arg_0], r12d
0x18002746d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027472  mov     rcx, cs:WPP_GLOBAL_Control
0x180027479  lea     r15, WPP_GLOBAL_Control
0x180027480  cmp     rcx, r15
0x180027483  jz      short loc_1800274AD
0x180027485  test    byte ptr [rcx+1Ch], 2
0x180027489  jz      short loc_1800274AD
0x18002748b  cmp     byte ptr [rcx+19h], 5
0x18002748f  jb      short loc_1800274AD
0x180027491  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027498  lea     edx, [r12+6Ah]
0x18002749d  mov     rcx, [rcx+10h]
0x1800274a1  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800274a8  call    WPP_SF_s
0x1800274ad  cmp     dword ptr [rsi+24h], 2
0x1800274b1  mov     dword ptr [rsi+4ACh], 1
0x1800274bb  jnz     loc_180027576
0x1800274c1  mov     r13d, [rsi+4A8h]
0x1800274c8  add     r13d, 28h ; '('
0x1800274cc  mov     ecx, r13d; size
0x1800274cf  mov     ebx, r13d
0x1800274d2  call    MIDL_user_allocate
0x1800274d7  mov     rdi, rax
0x1800274da  test    rax, rax
0x1800274dd  jnz     short loc_18002752D
0x1800274df  lea     edx, [rax+2]
0x1800274e2  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800274e7  lea     ebx, [rdi+8]
0x1800274ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274f1  cmp     rcx, r15
0x1800274f4  jz      loc_1800277CE
0x1800274fa  test    byte ptr [rcx+1Ch], 1
0x1800274fe  jz      loc_1800277CE
0x180027504  cmp     byte ptr [rcx+19h], 2
0x180027508  jb      loc_1800277CE
0x18002750e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027515  lea     edx, [rdi+6Bh]
0x180027518  mov     rcx, [rcx+10h]
0x18002751c  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180027523  call    WPP_SF_s
0x180027528  jmp     loc_1800277CE
0x18002752d  mov     r8, rbx; Size
0x180027530  xor     edx, edx; Val
0x180027532  mov     rcx, rdi; void *
0x180027535  call    memset_0
0x18002753a  mov     dword ptr [rdi+8], 2
0x180027541  lea     rcx, [rdi+28h]; Destination
0x180027545  mov     eax, [rsi+38h]
0x180027548  mov     [rdi+14h], eax
0x18002754b  mov     dword ptr [rdi+0Ch], 28h ; '('
0x180027552  mov     eax, [rsi+4A8h]
0x180027558  mov     [rdi+10h], eax
0x18002755b  mov     edx, eax; DestinationSize
0x18002755d  mov     r9d, [rsi+4A8h]; SourceSize
0x180027564  mov     r8, [rsi+4A0h]; Source
0x18002756b  call    cs:__imp_memcpy_s
0x180027571  jmp     loc_1800276AE
0x180027576  mov     rdx, [rsi+488h]
0x18002757d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027581  mov     ebx, r12d
0x180027584  mov     r14d, r12d
0x180027587  test    rdx, rdx
0x18002758a  jz      short loc_18002759C
0x18002758c  mov     rcx, rax
0x18002758f  inc     rcx
0x180027592  cmp     [rdx+rcx*2], r12w
0x180027597  jnz     short loc_18002758F
0x180027599  lea     ebx, [rcx+1]
0x18002759c  mov     rcx, [rsi+490h]
0x1800275a3  test    rcx, rcx
0x1800275a6  jz      short loc_1800275B6
0x1800275a8  inc     rax
0x1800275ab  cmp     [rcx+rax*2], r12w
0x1800275b0  jnz     short loc_1800275A8
0x1800275b2  lea     r14d, [rax+1]
0x1800275b6  lea     eax, [r14+rbx]
0x1800275ba  lea     r13d, ds:28h[rax*2]
0x1800275c2  mov     ecx, r13d; size
0x1800275c5  mov     r15d, r13d
0x1800275c8  call    MIDL_user_allocate
0x1800275cd  mov     rdi, rax
0x1800275d0  test    rax, rax
0x1800275d3  jnz     short loc_18002762A
0x1800275d5  lea     edx, [rax+2]
0x1800275d8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800275dd  lea     ebx, [rdi+8]
0x1800275e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800275e7  lea     rsi, WPP_GLOBAL_Control
0x1800275ee  cmp     rcx, rsi
0x1800275f1  jz      loc_1800277D5
0x1800275f7  test    byte ptr [rcx+1Ch], 1
0x1800275fb  jz      loc_1800277D5
0x180027601  cmp     byte ptr [rcx+19h], 2
0x180027605  jb      loc_1800277D5
0x18002760b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027612  lea     edx, [rdi+6Ch]
0x180027615  mov     rcx, [rcx+10h]
0x180027619  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180027620  call    WPP_SF_s
0x180027625  jmp     loc_1800277D5
0x18002762a  mov     r8, r15; Size
0x18002762d  xor     edx, edx; Val
0x18002762f  mov     rcx, rdi; void *
0x180027632  call    memset_0
0x180027637  mov     dword ptr [rdi+8], 1
0x18002763e  mov     eax, [rsi+38h]
0x180027641  mov     [rdi+1Ch], eax
0x180027644  mov     eax, [rsi+20h]
0x180027647  mov     [rdi+20h], eax
0x18002764a  lea     eax, ds:28h[rbx*2]
0x180027651  mov     [rdi+14h], eax
0x180027654  mov     dword ptr [rdi+0Ch], 28h ; '('
0x18002765b  mov     [rdi+10h], ebx
0x18002765e  mov     [rdi+18h], r14d
0x180027662  test    ebx, ebx
0x180027664  jz      short loc_180027682
0x180027666  mov     r8, [rsi+488h]; unsigned __int16 *
0x18002766d  lea     rcx, [rdi+28h]; unsigned __int16 *
0x180027671  mov     edx, ebx; unsigned __int64
0x180027673  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027678  mov     ebx, eax
0x18002767a  test    eax, eax
0x18002767c  js      loc_1800277CE
0x180027682  cmp     [rdi+18h], r12d
0x180027686  jbe     short loc_1800276A7
0x180027688  mov     ecx, [rdi+14h]
0x18002768b  mov     edx, [rdi+18h]; unsigned __int64
0x18002768e  add     rcx, rdi; unsigned __int16 *
0x180027691  mov     r8, [rsi+490h]; unsigned __int16 *
0x180027698  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002769d  mov     ebx, eax
0x18002769f  test    eax, eax
0x1800276a1  js      loc_1800277CE
0x1800276a7  lea     r15, WPP_GLOBAL_Control
0x1800276ae  mov     eax, [rsi+58h]
0x1800276b1  lea     r8, [rbp+57h+pulAuthPackage]; pulAuthPackage
0x1800276b5  mov     [rdi], eax
0x1800276b7  lea     rcx, [rbp+57h+pUiInfo]; pUiInfo
0x1800276bb  mov     eax, [rsi+5Ch]
0x1800276be  mov     r9, rdi; pvInAuthBuffer
0x1800276c1  mov     [rdi+4], eax
0x1800276c4  xor     edx, edx; dwAuthError
0x1800276c6  mov     rax, [rsi+28h]
0x1800276ca  mov     [rbp+57h+pUiInfo.hwndParent], rax
0x1800276ce  mov     rax, [rsi+478h]
0x1800276d5  mov     [rbp+57h+pUiInfo.pszCaptionText], rax
0x1800276d9  mov     rax, [rsi+480h]
0x1800276e0  mov     [rsp+0C0h+dwFlags], 10h; dwFlags
0x1800276e8  mov     [rbp+57h+pUiInfo.pszMessageText], rax
0x1800276ec  lea     rax, [rbp+57h+arg_0]
0x1800276f0  mov     [rsp+0C0h+pfSave], r12; pfSave
0x1800276f5  mov     [rsp+0C0h+pulOutAuthBufferSize], rax; pulOutAuthBufferSize
0x1800276fa  lea     rax, [rbp+57h+pv]
0x1800276fe  mov     [rsp+0C0h+ppvOutAuthBuffer], rax; ppvOutAuthBuffer
0x180027703  mov     [rsp+0C0h+ulInAuthBufferSize], r13d; ulInAuthBufferSize
0x180027708  mov     [rbp+57h+pUiInfo.cbSize], 28h ; '('
0x18002770f  mov     [rbp+57h+pUiInfo.hbmBanner], r12
0x180027713  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x180027719  mov     ebx, eax
0x18002771b  cmp     eax, 4C7h
0x180027720  jnz     short loc_18002772C
0x180027722  mov     ebx, 8010006Eh
0x180027727  jmp     loc_1800277CE
0x18002772c  test    eax, eax
0x18002772e  jnz     loc_1800277CE
0x180027734  cmp     [rbp+57h+arg_0], 10h
0x180027738  jnb     short loc_180027744
0x18002773a  mov     ebx, 0Dh
0x18002773f  jmp     loc_1800277CE
0x180027744  mov     r14, [rbp+57h+pv]
0x180027748  cmp     [r14+4], r12d
0x18002774c  jz      short loc_18002773A
0x18002774e  cmp     [r14+0Ch], r12d
0x180027752  jz      short loc_18002773A
0x180027754  mov     ecx, [r14+4]
0x180027758  mov     eax, [r14]
0x18002775b  add     rcx, rcx; size
0x18002775e  mov     r8d, [rbp+57h+arg_0]
0x180027762  add     rax, rcx
0x180027765  cmp     r8, rax
0x180027768  jb      short loc_18002773A
0x18002776a  mov     edx, [r14+0Ch]
0x18002776e  mov     eax, [r14+8]
0x180027772  lea     rdx, [rax+rdx*2]
0x180027776  cmp     r8, rdx
0x180027779  jb      short loc_18002773A
0x18002777b  call    MIDL_user_allocate
0x180027780  mov     r12, rax
0x180027783  test    rax, rax
0x180027786  jnz     loc_180027878
0x18002778c  lea     edx, [rax+2]
0x18002778f  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180027794  lea     ebx, [r12+8]
0x180027799  mov     rcx, cs:WPP_GLOBAL_Control
0x1800277a0  cmp     rcx, r15
0x1800277a3  jz      short loc_1800277CB
0x1800277a5  test    byte ptr [rcx+1Ch], 1
0x1800277a9  jz      short loc_1800277CB
0x1800277ab  cmp     byte ptr [rcx+19h], 2
0x1800277af  jb      short loc_1800277CB
0x1800277b1  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800277b8  lea     edx, [rbx+65h]
0x1800277bb  mov     rcx, [rcx+10h]
0x1800277bf  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x1800277c6  call    WPP_SF_s
0x1800277cb  xor     r12d, r12d
0x1800277ce  lea     rsi, WPP_GLOBAL_Control
0x1800277d5  mov     rax, [rbp+57h+pv]
0x1800277d9  test    rax, rax
0x1800277dc  jz      short loc_1800277FC
0x1800277de  mov     ecx, [rbp+57h+arg_0]
0x1800277e1  test    rcx, rcx
0x1800277e4  jz      short loc_1800277F2
0x1800277e6  mov     [rax], r12b
0x1800277e9  inc     rax
0x1800277ec  sub     rcx, 1
0x1800277f0  jnz     short loc_1800277E6
0x1800277f2  mov     rcx, [rbp+57h+pv]; pv
0x1800277f6  call    cs:__imp_CoTaskMemFree
0x1800277fc  test    rdi, rdi
0x1800277ff  jz      short loc_180027820
0x180027801  mov     ecx, r13d
0x180027804  mov     rax, rdi
0x180027807  test    r13d, r13d
0x18002780a  jz      short loc_180027818
0x18002780c  mov     [rax], r12b
0x18002780f  inc     rax
0x180027812  sub     rcx, 1
0x180027816  jnz     short loc_18002780C
0x180027818  mov     rcx, rdi
0x18002781b  call    CspFreeH
0x180027820  mov     edx, 1
0x180027825  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002782a  mov     rcx, cs:WPP_GLOBAL_Control
0x180027831  cmp     rcx, rsi
0x180027834  jz      short loc_180027862
0x180027836  test    byte ptr [rcx+1Ch], 2
0x18002783a  jz      short loc_180027862
0x18002783c  cmp     byte ptr [rcx+19h], 5
0x180027840  jb      short loc_180027862
0x180027842  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180027849  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180027850  mov     rcx, [rcx+10h]
0x180027854  mov     edx, 70h ; 'p'
0x180027859  mov     [rsp+0C0h+ulInAuthBufferSize], ebx
0x18002785d  call    WPP_SF_sD
0x180027862  mov     eax, ebx
0x180027864  add     rsp, 88h
0x18002786b  pop     r15
0x18002786d  pop     r14
0x18002786f  pop     r13
0x180027871  pop     r12
0x180027873  pop     rdi
0x180027874  pop     rsi
0x180027875  pop     rbx
0x180027876  pop     rbp
0x180027877  retn
0x180027878  mov     r8d, [r14+4]
0x18002787c  xor     edx, edx; Val
0x18002787e  add     r8, r8; Size
0x180027881  mov     rcx, r12; void *
0x180027884  call    memset_0
0x180027889  mov     edx, [r14+4]; unsigned __int64
0x18002788d  mov     rcx, r12; unsigned __int16 *
0x180027890  mov     r8d, [r14]
0x180027893  mov     r9d, edx; unsigned __int64
0x180027896  add     r8, r14; unsigned __int16 *
0x180027899  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002789e  mov     ebx, eax
0x1800278a0  test    eax, eax
0x1800278a2  jns     short loc_1800278B0
0x1800278a4  lea     rsi, WPP_GLOBAL_Control
0x1800278ab  jmp     loc_1800279BA
0x1800278b0  mov     ebx, [r14+0Ch]
0x1800278b4  inc     ebx
0x1800278b6  add     rbx, rbx
0x1800278b9  mov     rcx, rbx; size
0x1800278bc  call    MIDL_user_allocate
  ... truncated ...
```
