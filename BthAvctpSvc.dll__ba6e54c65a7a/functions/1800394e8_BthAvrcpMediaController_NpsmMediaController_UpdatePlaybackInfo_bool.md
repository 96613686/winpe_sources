# BthAvrcpMediaController::NpsmMediaController::UpdatePlaybackInfo(bool)

- ea: `0x1800394e8`
- end: `0x180039bb2`
- name: `?UpdatePlaybackInfo@NpsmMediaController@BthAvrcpMediaController@@AEAA?AUMediaStateChanges@12@_N@Z`
- size: `1738`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1800360d4`
- `0x1800361c0`
- `0x1800390a8`

## callees

- `0x1800235bc`
- `0x180023da8`
- `0x180037dac`
- `0x1800394e8`
- `0x18003a1f8`
- `0x18003a24c`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039593`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039623`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039593`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039623`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800395be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039b60`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800395be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039b60`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall BthAvrcpMediaController::NpsmMediaController::UpdatePlaybackInfo(__int64 a1, __int64 a2, char a3)
{
  int *v6; // r12
  int v7; // r15d
  BOOL HasActiveMediaPlayer; // r13d
  int v9; // esi
  PVOID *v10; // r10
  __int64 v11; // r8
  char v12; // si
  int v13; // edx
  int v14; // eax
  int v15; // ecx
  PVOID v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // r9
  __int64 v21; // r10
  BthAvrcpMediaController::NpsmMediaController *v22; // rcx
  __int64 v23; // r10
  __int64 v24; // r8
  int v25; // edx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  int v29; // esi
  unsigned int v31; // [rsp+30h] [rbp-48h]
  unsigned int v32; // [rsp+34h] [rbp-44h]
  unsigned int v33; // [rsp+80h] [rbp+8h]
  unsigned int v34; // [rsp+88h] [rbp+10h]
  unsigned int v35; // [rsp+98h] [rbp+20h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
  }
  v6 = (int *)(a1 + 224);
  v33 = *(_DWORD *)(a1 + 224);
  v34 = *(_DWORD *)(a1 + 228);
  v7 = *(_DWORD *)(a1 + 232);
  HasActiveMediaPlayer = BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer((BthAvrcpMediaController::NpsmMediaController *)a1);
  v35 = *(_DWORD *)(a1 + 272);
  v32 = *(_DWORD *)(a1 + 276);
  v31 = *(_DWORD *)(a1 + 280);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 328) + 24LL))(*(_QWORD *)(a1 + 328), a1 + 224);
  if ( a1 != -96 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  *(_DWORD *)a2 = 0;
  *(_WORD *)(a2 + 4) = 0;
  *(_BYTE *)(a2 + 6) = 0;
  if ( v9 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return a2;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        &WPP_95e767cb7999366f67a133efb5540c97_Traceguids,
        (unsigned int)v9);
LABEL_118:
      v10 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_119;
    }
    goto LABEL_119;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
  {
    v12 = v33;
  }
  else
  {
    v12 = v33;
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, v11, v33);
  }
  v13 = *v6;
  if ( (*v6 & 8) != 0 )
    v14 = *(_DWORD *)(a1 + 240);
  else
    v14 = 1;
  *(_DWORD *)(a1 + 276) = v14;
  if ( (v13 & 0x20) != 0 )
    v15 = (*(_DWORD *)(a1 + 256) != 0) + 1;
  else
    v15 = 1;
  *(_DWORD *)(a1 + 280) = v15;
  if ( (v13 & 2) == 0
    || !BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer((BthAvrcpMediaController::NpsmMediaController *)a1) )
  {
    if ( !a3 )
      goto LABEL_44;
    goto LABEL_43;
  }
  v11 = *(unsigned int *)(a1 + 232);
  switch ( *(_DWORD *)(a1 + 232) )
  {
    case 1:
      if ( (v12 & 2) == 0 || v7 != 1 )
        *(_BYTE *)(a2 + 5) = 1;
      goto LABEL_43;
    case 3:
      goto LABEL_44;
    case 4:
      goto LABEL_43;
  }
  if ( (unsigned int)(*(_DWORD *)(a1 + 232) - 5) >= 2 )
  {
    if ( WPP_GLOBAL_Control != v16
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 89);
    }
LABEL_43:
    *(_DWORD *)(a1 + 272) = 0;
    goto LABEL_44;
  }
  v17 = *(_DWORD *)(a1 + 284);
  if ( v17 == -1 )
  {
    v18 = 4;
  }
  else if ( v17 == 1 )
  {
    v18 = 3;
  }
  else
  {
    v18 = ((_DWORD)v11 != 5) + 1;
  }
  *(_DWORD *)(a1 + 272) = v18;
LABEL_44:
  v19 = *v6 & 1;
  v20 = v12 & 1;
  if ( (_DWORD)v20 == v19 )
  {
    if ( !v19 )
      goto LABEL_70;
    if ( HasActiveMediaPlayer != BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer((BthAvrcpMediaController::NpsmMediaController *)a1) )
    {
      *(_BYTE *)a2 = 1;
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      {
LABEL_65:
        if ( v34 != *(_DWORD *)(a1 + 228) )
        {
          *(_BYTE *)(a2 + 6) = 1;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, v11, v34);
            goto LABEL_70;
          }
        }
        goto LABEL_71;
      }
      BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(v22);
      WPP_SF_dd(*(_QWORD *)(v23 + 16), 93, v24, HasActiveMediaPlayer);
    }
    v10 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, v11, v20);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)v6 & 1) != 0 )
  {
    *(_BYTE *)(a2 + 6) = 1;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer((BthAvrcpMediaController::NpsmMediaController *)a1);
        WPP_SF_l(*(_QWORD *)(v21 + 16), 91);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
      {
        WPP_SF_d(v10[2], 92, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, *(unsigned int *)(a1 + 228));
LABEL_70:
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
LABEL_71:
  v25 = v12 & 2;
  if ( v25 != (*v6 & 2) && v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 5u )
  {
    WPP_SF_dd(v10[2], 95, v11, v25 != 0);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( (*(_BYTE *)v6 & 2) != 0 && v35 != *(_DWORD *)(a1 + 272) )
  {
    *(_BYTE *)(a2 + 1) = 1;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, v11, v35);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v26 = *v6 & 0x20;
  v27 = v12 & 0x20;
  if ( v27 == v26 )
  {
    if ( v26 )
    {
      if ( v31 != *(_DWORD *)(a1 + 280) )
      {
        *(_BYTE *)(a2 + 3) = 1;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, v11, v31);
          goto LABEL_98;
        }
      }
    }
  }
  else
  {
    *(_BYTE *)(a2 + 3) = 1;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, v11, v27 != 0);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)v6 & 0x20) != 0
      && v10 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v10 + 28) & 1) != 0
      && *((_BYTE *)v10 + 25) >= 5u )
    {
      WPP_SF_l(v10[2], 98);
LABEL_98:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v28 = *v6 & 8;
  v29 = v12 & 8;
  if ( v29 == v28 )
  {
    if ( v28 )
    {
      if ( v32 != *(_DWORD *)(a1 + 276) )
      {
        *(_BYTE *)(a2 + 2) = 1;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, v11, v32);
          goto LABEL_115;
        }
      }
    }
  }
  else
  {
    *(_BYTE *)(a2 + 2) = 1;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, v11, v29 != 0);
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( (*(_BYTE *)v6 & 8) != 0
      && v10 != &WPP_GLOBAL_Control
      && (*((_BYTE *)v10 + 28) & 1) != 0
      && *((_BYTE *)v10 + 25) >= 5u )
    {
      WPP_SF_l(v10[2], 101);
LABEL_115:
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( a1 != -96 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    goto LABEL_118;
  }
LABEL_119:
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_q(v10[2], 103, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
  return a2;
}

```

## disassembly

```asm
0x1800394e8  mov     [rsp+arg_10], rbx
0x1800394ed  push    rbp
0x1800394ee  push    rsi
0x1800394ef  push    rdi
0x1800394f0  push    r12
0x1800394f2  push    r13
0x1800394f4  push    r14
0x1800394f6  push    r15
0x1800394f8  sub     rsp, 40h
0x1800394fc  mov     bpl, r8b
0x1800394ff  mov     r14, rdx
0x180039502  mov     rdi, rcx
0x180039505  lea     rax, WPP_GLOBAL_Control
0x18003950c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039513  cmp     rcx, rax
0x180039516  jz      short loc_18003953C
0x180039518  test    byte ptr [rcx+1Ch], 1
0x18003951c  jz      short loc_18003953C
0x18003951e  cmp     byte ptr [rcx+19h], 4
0x180039522  jb      short loc_18003953C
0x180039524  mov     edx, 56h ; 'V'
0x180039529  mov     r9, rdi
0x18003952c  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039533  mov     rcx, [rcx+10h]
0x180039537  call    WPP_SF_q
0x18003953c  lea     r12, [rdi+0E0h]
0x180039543  mov     eax, [r12]
0x180039547  mov     [rsp+78h+arg_0], eax
0x18003954e  mov     eax, [r12+4]
0x180039553  mov     [rsp+78h+arg_8], eax
0x18003955a  mov     r15d, [r12+8]
0x18003955f  mov     rcx, rdi; this
0x180039562  call    ?HasActiveMediaPlayer@NpsmMediaController@BthAvrcpMediaController@@AEBA_NXZ; BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(void)
0x180039567  movzx   r13d, al
0x18003956b  mov     eax, [rdi+110h]
0x180039571  mov     [rsp+78h+arg_18], eax
0x180039578  mov     eax, [rdi+114h]
0x18003957e  mov     [rsp+78h+var_44], eax
0x180039582  mov     eax, [rdi+118h]
0x180039588  mov     [rsp+78h+var_48], eax
0x18003958c  lea     rbx, [rdi+60h]
0x180039590  mov     rcx, rbx; lpCriticalSection
0x180039593  call    cs:__imp_EnterCriticalSection
0x180039599  mov     [rsp+78h+var_40], rbx
0x18003959e  mov     rcx, [rdi+148h]
0x1800395a5  mov     rax, [rcx]
0x1800395a8  mov     rdx, r12
0x1800395ab  mov     rax, [rax+18h]
0x1800395af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395b4  mov     esi, eax
0x1800395b6  test    rbx, rbx
0x1800395b9  jz      short loc_1800395C4
0x1800395bb  mov     rcx, rbx; lpCriticalSection
0x1800395be  call    cs:__imp_LeaveCriticalSection
0x1800395c4  xor     eax, eax
0x1800395c6  mov     [r14], eax
0x1800395c9  mov     [r14+4], ax
0x1800395ce  mov     [r14+6], al
0x1800395d2  test    esi, esi
0x1800395d4  jns     short loc_180039620
0x1800395d6  mov     r10, cs:WPP_GLOBAL_Control
0x1800395dd  lea     r15, WPP_GLOBAL_Control
0x1800395e4  cmp     r10, r15
0x1800395e7  jz      loc_180039B97
0x1800395ed  lea     ebp, [rax+1]
0x1800395f0  test    [r10+1Ch], bpl
0x1800395f4  jz      loc_180039B6D
0x1800395fa  cmp     byte ptr [r10+19h], 2
0x1800395ff  jb      loc_180039B6D
0x180039605  lea     edx, [rax+57h]
0x180039608  mov     r9d, esi
0x18003960b  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039612  mov     rcx, [r10+10h]
0x180039616  call    WPP_SF_d
0x18003961b  jmp     loc_180039B66
0x180039620  mov     rcx, rbx; lpCriticalSection
0x180039623  call    cs:__imp_EnterCriticalSection
0x180039629  mov     rcx, cs:WPP_GLOBAL_Control
0x180039630  lea     r9, WPP_GLOBAL_Control
0x180039637  cmp     rcx, r9
0x18003963a  jz      short loc_180039671
0x18003963c  test    byte ptr [rcx+1Ch], 1
0x180039640  jz      short loc_180039671
0x180039642  mov     esi, [rsp+78h+arg_0]
0x180039649  cmp     byte ptr [rcx+19h], 4
0x18003964d  jb      short loc_180039678
0x18003964f  mov     edx, 58h ; 'X'
0x180039654  mov     eax, [r12]
0x180039658  mov     [rsp+78h+var_58], eax
0x18003965c  mov     r9d, esi
0x18003965f  mov     rcx, [rcx+10h]
0x180039663  call    WPP_SF_dd
0x180039668  lea     r9, WPP_GLOBAL_Control
0x18003966f  jmp     short loc_180039678
0x180039671  mov     esi, [rsp+78h+arg_0]
0x180039678  mov     edx, [r12]
0x18003967c  test    dl, 8
0x18003967f  jz      short loc_180039689
0x180039681  mov     eax, [rdi+0F0h]
0x180039687  jmp     short loc_18003968E
0x180039689  mov     eax, 1
0x18003968e  mov     [rdi+114h], eax
0x180039694  test    dl, 20h
0x180039697  jz      short loc_1800396A9
0x180039699  mov     eax, [rdi+100h]
0x18003969f  neg     eax
0x1800396a1  sbb     ecx, ecx
0x1800396a3  neg     ecx
0x1800396a5  inc     ecx
0x1800396a7  jmp     short loc_1800396AE
0x1800396a9  mov     ecx, 1
0x1800396ae  mov     [rdi+118h], ecx
0x1800396b4  test    dl, 2
0x1800396b7  jz      loc_180039769
0x1800396bd  mov     rcx, rdi; this
0x1800396c0  call    ?HasActiveMediaPlayer@NpsmMediaController@BthAvrcpMediaController@@AEBA_NXZ; BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(void)
0x1800396c5  test    al, al
0x1800396c7  jz      loc_180039769
0x1800396cd  mov     r8d, [rdi+0E8h]
0x1800396d4  mov     ecx, r8d
0x1800396d7  sub     ecx, 1
0x1800396da  jz      short loc_180039756
0x1800396dc  sub     ecx, 2
0x1800396df  jz      loc_180039778
0x1800396e5  sub     ecx, 1
0x1800396e8  jz      loc_18003976E
0x1800396ee  sub     ecx, 1
0x1800396f1  jz      short loc_180039725
0x1800396f3  cmp     ecx, 1
0x1800396f6  jz      short loc_180039725
0x1800396f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800396ff  cmp     rcx, r9
0x180039702  jz      short loc_18003976E
0x180039704  test    byte ptr [rcx+1Ch], 1
0x180039708  jz      short loc_18003976E
0x18003970a  mov     eax, 3
0x18003970f  cmp     [rcx+19h], al
0x180039712  jb      short loc_18003976E
0x180039714  lea     edx, [rax+56h]
0x180039717  mov     r9d, r8d
0x18003971a  mov     rcx, [rcx+10h]
0x18003971e  call    WPP_SF_l
0x180039723  jmp     short loc_18003976E
0x180039725  mov     eax, [rdi+11Ch]
0x18003972b  cmp     eax, 0FFFFFFFFh
0x18003972e  jnz     short loc_180039737
0x180039730  mov     eax, 4
0x180039735  jmp     short loc_18003974E
0x180039737  cmp     eax, 1
0x18003973a  jnz     short loc_180039743
0x18003973c  mov     eax, 3
0x180039741  jmp     short loc_18003974E
0x180039743  xor     eax, eax
0x180039745  cmp     r8d, 5
0x180039749  setnz   al
0x18003974c  inc     eax
0x18003974e  mov     [rdi+110h], eax
0x180039754  jmp     short loc_180039778
0x180039756  test    sil, 2
0x18003975a  jz      short loc_180039762
0x18003975c  cmp     r15d, 1
0x180039760  jz      short loc_18003976E
0x180039762  mov     byte ptr [r14+5], 1
0x180039767  jmp     short loc_18003976E
0x180039769  test    bpl, bpl
0x18003976c  jz      short loc_180039778
0x18003976e  mov     dword ptr [rdi+110h], 0
0x180039778  mov     eax, [r12]
0x18003977c  mov     ebp, 1
0x180039781  and     eax, ebp
0x180039783  mov     r9d, esi
0x180039786  and     r9d, ebp
0x180039789  cmp     r9d, eax
0x18003978c  jz      loc_180039854
0x180039792  mov     r10, cs:WPP_GLOBAL_Control
0x180039799  lea     r15, WPP_GLOBAL_Control
0x1800397a0  cmp     r10, r15
0x1800397a3  jz      short loc_1800397C9
0x1800397a5  test    [r10+1Ch], bpl
0x1800397a9  jz      short loc_1800397C9
0x1800397ab  cmp     byte ptr [r10+19h], 5
0x1800397b0  jb      short loc_1800397C9
0x1800397b2  lea     edx, [rbp+59h]
0x1800397b5  mov     [rsp+78h+var_58], eax
0x1800397b9  mov     rcx, [r10+10h]
0x1800397bd  call    WPP_SF_dd
0x1800397c2  mov     r10, cs:WPP_GLOBAL_Control
0x1800397c9  test    [r12], bpl
0x1800397cd  jz      loc_18003990F
0x1800397d3  mov     [r14+6], bpl
0x1800397d7  mov     r10, cs:WPP_GLOBAL_Control
0x1800397de  cmp     r10, r15
0x1800397e1  jz      loc_18003990F
0x1800397e7  test    [r10+1Ch], bpl
0x1800397eb  jz      short loc_180039815
0x1800397ed  cmp     byte ptr [r10+19h], 5
0x1800397f2  jb      short loc_180039815
0x1800397f4  mov     rcx, rdi; this
0x1800397f7  call    ?HasActiveMediaPlayer@NpsmMediaController@BthAvrcpMediaController@@AEBA_NXZ; BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(void)
0x1800397fc  movzx   r9d, al
0x180039800  mov     edx, 5Bh ; '['
0x180039805  mov     rcx, [r10+10h]
0x180039809  call    WPP_SF_l
0x18003980e  mov     r10, cs:WPP_GLOBAL_Control
0x180039815  cmp     r10, r15
0x180039818  jz      loc_18003990F
0x18003981e  test    [r10+1Ch], bpl
0x180039822  jz      loc_18003990F
0x180039828  cmp     byte ptr [r10+19h], 5
0x18003982d  jb      loc_18003990F
0x180039833  mov     edx, 5Ch ; '\'
0x180039838  mov     r9d, [rdi+0E4h]
0x18003983f  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039846  mov     rcx, [r10+10h]
0x18003984a  call    WPP_SF_d
0x18003984f  jmp     loc_180039908
0x180039854  test    eax, eax
0x180039856  jz      loc_180039901
0x18003985c  mov     rcx, rdi; this
0x18003985f  call    ?HasActiveMediaPlayer@NpsmMediaController@BthAvrcpMediaController@@AEBA_NXZ; BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(void)
0x180039864  cmp     r13b, al
0x180039867  jz      short loc_1800398AB
0x180039869  mov     [r14], bpl
0x18003986c  mov     r10, cs:WPP_GLOBAL_Control
0x180039873  lea     r15, WPP_GLOBAL_Control
0x18003987a  cmp     r10, r15
0x18003987d  jz      short loc_1800398B9
0x18003987f  test    [r10+1Ch], bpl
0x180039883  jz      short loc_1800398B9
0x180039885  cmp     byte ptr [r10+19h], 5
0x18003988a  jb      short loc_1800398B9
0x18003988c  call    ?HasActiveMediaPlayer@NpsmMediaController@BthAvrcpMediaController@@AEBA_NXZ; BthAvrcpMediaController::NpsmMediaController::HasActiveMediaPlayer(void)
0x180039891  movzx   ecx, al
0x180039894  mov     r9d, r13d
0x180039897  mov     edx, 5Dh ; ']'
0x18003989c  mov     [rsp+78h+var_58], ecx
0x1800398a0  mov     rcx, [r10+10h]
0x1800398a4  call    WPP_SF_dd
0x1800398a9  jmp     short loc_1800398B2
0x1800398ab  lea     r15, WPP_GLOBAL_Control
0x1800398b2  mov     r10, cs:WPP_GLOBAL_Control
0x1800398b9  mov     r9d, [rsp+78h+arg_8]
0x1800398c1  cmp     r9d, [rdi+0E4h]
0x1800398c8  jz      short loc_18003990F
0x1800398ca  mov     [r14+6], bpl
0x1800398ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800398d5  cmp     r10, r15
0x1800398d8  jz      short loc_18003990F
0x1800398da  test    [r10+1Ch], bpl
0x1800398de  jz      short loc_18003990F
0x1800398e0  cmp     byte ptr [r10+19h], 5
0x1800398e5  jb      short loc_18003990F
0x1800398e7  mov     edx, 5Eh ; '^'
0x1800398ec  mov     eax, [rdi+0E4h]
0x1800398f2  mov     [rsp+78h+var_58], eax
0x1800398f6  mov     rcx, [r10+10h]
0x1800398fa  call    WPP_SF_dd
0x1800398ff  jmp     short loc_180039908
0x180039901  lea     r15, WPP_GLOBAL_Control
0x180039908  mov     r10, cs:WPP_GLOBAL_Control
0x18003990f  mov     ecx, [r12]
0x180039913  and     ecx, 2
0x180039916  mov     edx, esi
0x180039918  and     edx, 2
0x18003991b  cmp     edx, ecx
0x18003991d  jz      short loc_18003995A
0x18003991f  cmp     r10, r15
0x180039922  jz      short loc_18003995A
0x180039924  test    [r10+1Ch], bpl
0x180039928  jz      short loc_18003995A
0x18003992a  cmp     byte ptr [r10+19h], 5
0x18003992f  jb      short loc_18003995A
0x180039931  xor     eax, eax
0x180039933  test    ecx, ecx
0x180039935  setnz   al
0x180039938  xor     r9d, r9d
0x18003993b  test    edx, edx
0x18003993d  setnz   r9b
0x180039941  mov     edx, 5Fh ; '_'
0x180039946  mov     [rsp+78h+var_58], eax
0x18003994a  mov     rcx, [r10+10h]
0x18003994e  call    WPP_SF_dd
0x180039953  mov     r10, cs:WPP_GLOBAL_Control
0x18003995a  test    byte ptr [r12], 2
0x18003995f  jz      short loc_1800399AE
0x180039961  mov     r9d, [rsp+78h+arg_18]
0x180039969  cmp     r9d, [rdi+110h]
0x180039970  jz      short loc_1800399AE
0x180039972  mov     [r14+1], bpl
0x180039976  mov     r10, cs:WPP_GLOBAL_Control
0x18003997d  cmp     r10, r15
0x180039980  jz      short loc_1800399AE
0x180039982  test    [r10+1Ch], bpl
0x180039986  jz      short loc_1800399AE
0x180039988  cmp     byte ptr [r10+19h], 5
0x18003998d  jb      short loc_1800399AE
0x18003998f  mov     edx, 60h ; '`'
0x180039994  mov     eax, [rdi+110h]
0x18003999a  mov     [rsp+78h+var_58], eax
0x18003999e  mov     rcx, [r10+10h]
  ... truncated ...
```
