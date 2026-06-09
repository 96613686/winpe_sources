# BthAvrcpMediaController::NpsmMediaController::UpdateMediaState(bool,std::optional<MediaPlaybackDataChangedEvent>)

- ea: `0x1800390a8`
- end: `0x1800394df`
- name: `?UpdateMediaState@NpsmMediaController@BthAvrcpMediaController@@AEAAX_NV?$optional@W4MediaPlaybackDataChangedEvent@@@std@@@Z`
- size: `1079`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180037ea0`
- `0x180038bc4`

## callees

- `0x1800039c0`
- `0x18000ab4c`
- `0x18000e0c0`
- `0x1800235bc`
- `0x180032a88`
- `0x18003508c`
- `0x1800390a8`
- `0x1800394e8`
- `0x180039bb8`
- `0x18003a1f8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800391af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393e5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800391af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800393e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003920f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039402`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003920f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180039402`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall BthAvrcpMediaController::NpsmMediaController::UpdateMediaState(__int64 a1, char a2, __int64 a3)
{
  int v3; // ebx
  __int64 updated; // rax
  __int64 v7; // r8
  const char *v8; // r9
  __int64 *v9; // rdi
  __int64 *i; // rsi
  __int64 v11; // rbx
  int v12; // r15d
  const char *v13; // r9
  int v14; // [rsp+20h] [rbp-68h]
  int v15[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v16; // [rsp+38h] [rbp-50h]
  __int128 v17; // [rsp+40h] [rbp-48h] BYREF
  __int64 *v18; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  char v20; // [rsp+A4h] [rbp+1Ch]
  int v21; // [rsp+A8h] [rbp+20h] BYREF
  __int16 v22; // [rsp+ACh] [rbp+24h]
  char v23; // [rsp+AEh] [rbp+26h]

  v20 = BYTE4(a3);
  v3 = a3;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
  }
  v17 = 0;
  v18 = 0;
  try
  {
    BthAvrcpMediaController::NpsmMediaController::UpdatePlaybackInfo(a1, (__int64)&v21, a2);
    if ( (_BYTE)v21 )
    {
      *(_QWORD *)v15 = 10;
      if ( *((__int64 **)&v17 + 1) == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          v15);
      }
      else
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        *((_QWORD *)&v17 + 1) += 8LL;
      }
    }
    if ( BYTE1(v21) )
    {
      *(_QWORD *)v15 = 1;
      if ( *((__int64 **)&v17 + 1) == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          v15);
      }
      else
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        *((_QWORD *)&v17 + 1) += 8LL;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
      v16 = a1 + 96;
      if ( *(_BYTE *)(a1 + 216) && *(_DWORD *)(a1 + 272) )
      {
        *(_QWORD *)v15 = 2;
        if ( *((__int64 **)&v17 + 1) == v18 )
        {
          std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
            &v17,
            *((_QWORD *)&v17 + 1),
            v15);
        }
        else
        {
          **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
          *((_QWORD *)&v17 + 1) += 8LL;
        }
        *(_BYTE *)(a1 + 216) = 0;
      }
      if ( a1 != -96 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
    }
    if ( HIBYTE(v22) )
    {
      *(_QWORD *)v15 = 14;
      if ( *((__int64 **)&v17 + 1) == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          v15);
      }
      else
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        *((_QWORD *)&v17 + 1) += 8LL;
      }
    }
    if ( HIWORD(v21) )
    {
      *(_QWORD *)v15 = 8;
      if ( *((__int64 **)&v17 + 1) == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          v15);
      }
      else
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        *((_QWORD *)&v17 + 1) += 8LL;
      }
    }
    if ( v23 )
    {
      *(_QWORD *)v15 = 15;
      if ( *((__int64 **)&v17 + 1) == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          v15);
      }
      else
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        *((_QWORD *)&v17 + 1) += 8LL;
      }
    }
    updated = BthAvrcpMediaController::NpsmMediaController::UpdateTrackMetadata(a1, (__int64)v15);
    v21 = *(_DWORD *)updated;
    v22 = *(_WORD *)(updated + 4);
    v23 = *(_BYTE *)(updated + 6);
    if ( (_BYTE)v22 )
    {
      *(_QWORD *)v15 = 2;
      if ( *((__int64 **)&v17 + 1) != v18 )
      {
        **((_QWORD **)&v17 + 1) = *(_QWORD *)v15;
        v9 = (__int64 *)(*((_QWORD *)&v17 + 1) + 8LL);
        *((_QWORD *)&v17 + 1) += 8LL;
        goto LABEL_39;
      }
      std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(
        &v17,
        *((_QWORD *)&v17 + 1),
        v15);
    }
    v9 = (__int64 *)*((_QWORD *)&v17 + 1);
LABEL_39:
    if ( v20 && v3 == 2 )
    {
      *(_QWORD *)v15 = 5;
      if ( v9 == v18 )
      {
        std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(&v17, v9, v15);
        v9 = (__int64 *)*((_QWORD *)&v17 + 1);
      }
      else
      {
        *v9 = *(_QWORD *)v15;
        v9 = (__int64 *)(*((_QWORD *)&v17 + 1) + 8LL);
        *((_QWORD *)&v17 + 1) += 8LL;
      }
    }
    for ( i = (__int64 *)v17; i != v9; ++i )
    {
      v11 = *i;
      *(_QWORD *)v15 = *i;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v14 = HIDWORD(v11);
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 83, v7, (unsigned int)v11);
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
      v12 = Microsoft::WRL::EventSource<IBthAvMediaEventHandler,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<BthAvMediaApiEvent>(
              a1 + 72,
              v11);
      if ( a1 != -32 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
      if ( v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = v15[1];
          WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, v7, (unsigned int)v11);
        }
        v13 = (const char *)(unsigned int)wil::verify_hresult<long>((unsigned int)v12);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3D6,
          (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
          v13,
          v14);
      }
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, &WPP_95e767cb7999366f67a133efb5540c97_Traceguids, a1);
    }
    if ( (_QWORD)v17 )
      std::_Deallocate<16>(
        (void *)v17,
        (struct std::nothrow_t *)(((unsigned __int64)v18 - v17) & 0xFFFFFFFFFFFFFFF8uLL));
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x3DB,
      (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\tg\\npsmmediacontroller\\lib\\npsmmediacontroller.cpp",
      v8);
  }
}

```

## disassembly

```asm
0x1800390a8  mov     [rsp+arg_0], rbx
0x1800390ad  mov     [rsp+arg_8], rsi
0x1800390b2  mov     [rsp+arg_10], r8
0x1800390b7  push    rdi
0x1800390b8  push    r12
0x1800390ba  push    r13
0x1800390bc  push    r14
0x1800390be  push    r15
0x1800390c0  sub     rsp, 60h
0x1800390c4  mov     rbx, r8
0x1800390c7  mov     dil, dl
0x1800390ca  mov     r14, rcx
0x1800390cd  lea     r15, WPP_GLOBAL_Control
0x1800390d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800390db  cmp     rcx, r15
0x1800390de  jz      short loc_180039104
0x1800390e0  test    byte ptr [rcx+1Ch], 1
0x1800390e4  jz      short loc_180039104
0x1800390e6  cmp     byte ptr [rcx+19h], 4
0x1800390ea  jb      short loc_180039104
0x1800390ec  mov     edx, 52h ; 'R'
0x1800390f1  mov     r9, r14
0x1800390f4  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x1800390fb  mov     rcx, [rcx+10h]
0x1800390ff  call    WPP_SF_q
0x180039104  xorps   xmm0, xmm0
0x180039107  movdqu  [rsp+88h+var_48], xmm0
0x18003910d  xor     r13d, r13d
0x180039110  mov     [rsp+88h+var_38], r13
0x180039115  mov     r8b, dil
0x180039118  lea     rdx, [rsp+88h+arg_18]
0x180039120  mov     rcx, r14
0x180039123  call    ?UpdatePlaybackInfo@NpsmMediaController@BthAvrcpMediaController@@AEAA?AUMediaStateChanges@12@_N@Z; BthAvrcpMediaController::NpsmMediaController::UpdatePlaybackInfo(bool)
0x180039128  cmp     byte ptr [rsp+88h+arg_18], r13b
0x180039130  jz      short loc_180039166
0x180039132  mov     qword ptr [rsp+88h+var_58], 0Ah
0x18003913b  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180039140  cmp     rdx, [rsp+88h+var_38]
0x180039145  jz      short loc_180039157
0x180039147  mov     rax, qword ptr [rsp+88h+var_58]
0x18003914c  mov     [rdx], rax
0x18003914f  add     qword ptr [rsp+88h+var_48+8], 8
0x180039155  jmp     short loc_180039166
0x180039157  lea     r8, [rsp+88h+var_58]
0x18003915c  lea     rcx, [rsp+88h+var_48]
0x180039161  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x180039166  cmp     byte ptr [rsp+88h+arg_18+1], r13b
0x18003916e  jz      loc_180039215
0x180039174  mov     qword ptr [rsp+88h+var_58], 1
0x18003917d  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180039182  cmp     rdx, [rsp+88h+var_38]
0x180039187  jz      short loc_180039199
0x180039189  mov     rax, qword ptr [rsp+88h+var_58]
0x18003918e  mov     [rdx], rax
0x180039191  add     qword ptr [rsp+88h+var_48+8], 8
0x180039197  jmp     short loc_1800391A8
0x180039199  lea     r8, [rsp+88h+var_58]
0x18003919e  lea     rcx, [rsp+88h+var_48]
0x1800391a3  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x1800391a8  lea     rdi, [r14+60h]
0x1800391ac  mov     rcx, rdi; lpCriticalSection
0x1800391af  call    cs:__imp_EnterCriticalSection
0x1800391b5  mov     [rsp+88h+var_50], rdi
0x1800391ba  cmp     [r14+0D8h], r13b
0x1800391c1  jz      short loc_180039207
0x1800391c3  cmp     [r14+110h], r13d
0x1800391ca  jz      short loc_180039207
0x1800391cc  mov     qword ptr [rsp+88h+var_58], 2
0x1800391d5  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x1800391da  cmp     rdx, [rsp+88h+var_38]
0x1800391df  jz      short loc_1800391F1
0x1800391e1  mov     rax, qword ptr [rsp+88h+var_58]
0x1800391e6  mov     [rdx], rax
0x1800391e9  add     qword ptr [rsp+88h+var_48+8], 8
0x1800391ef  jmp     short loc_180039200
0x1800391f1  lea     r8, [rsp+88h+var_58]
0x1800391f6  lea     rcx, [rsp+88h+var_48]
0x1800391fb  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x180039200  mov     [r14+0D8h], r13b
0x180039207  test    rdi, rdi
0x18003920a  jz      short loc_180039215
0x18003920c  mov     rcx, rdi; lpCriticalSection
0x18003920f  call    cs:__imp_LeaveCriticalSection
0x180039215  cmp     [rsp+88h+arg_1D], r13b
0x18003921d  jz      short loc_180039253
0x18003921f  mov     qword ptr [rsp+88h+var_58], 0Eh
0x180039228  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x18003922d  cmp     rdx, [rsp+88h+var_38]
0x180039232  jz      short loc_180039244
0x180039234  mov     rax, qword ptr [rsp+88h+var_58]
0x180039239  mov     [rdx], rax
0x18003923c  add     qword ptr [rsp+88h+var_48+8], 8
0x180039242  jmp     short loc_180039253
0x180039244  lea     r8, [rsp+88h+var_58]
0x180039249  lea     rcx, [rsp+88h+var_48]
0x18003924e  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x180039253  cmp     byte ptr [rsp+88h+arg_18+2], r13b
0x18003925b  jnz     short loc_180039267
0x18003925d  cmp     byte ptr [rsp+88h+arg_18+3], r13b
0x180039265  jz      short loc_18003929B
0x180039267  mov     qword ptr [rsp+88h+var_58], 8
0x180039270  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180039275  cmp     rdx, [rsp+88h+var_38]
0x18003927a  jz      short loc_18003928C
0x18003927c  mov     rax, qword ptr [rsp+88h+var_58]
0x180039281  mov     [rdx], rax
0x180039284  add     qword ptr [rsp+88h+var_48+8], 8
0x18003928a  jmp     short loc_18003929B
0x18003928c  lea     r8, [rsp+88h+var_58]
0x180039291  lea     rcx, [rsp+88h+var_48]
0x180039296  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x18003929b  cmp     [rsp+88h+arg_1E], r13b
0x1800392a3  jz      short loc_1800392D9
0x1800392a5  mov     qword ptr [rsp+88h+var_58], 0Fh
0x1800392ae  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x1800392b3  cmp     rdx, [rsp+88h+var_38]
0x1800392b8  jz      short loc_1800392CA
0x1800392ba  mov     rax, qword ptr [rsp+88h+var_58]
0x1800392bf  mov     [rdx], rax
0x1800392c2  add     qword ptr [rsp+88h+var_48+8], 8
0x1800392c8  jmp     short loc_1800392D9
0x1800392ca  lea     r8, [rsp+88h+var_58]
0x1800392cf  lea     rcx, [rsp+88h+var_48]
0x1800392d4  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x1800392d9  lea     rdx, [rsp+88h+var_58]
0x1800392de  mov     rcx, r14
0x1800392e1  call    ?UpdateTrackMetadata@NpsmMediaController@BthAvrcpMediaController@@AEAA?AUMediaStateChanges@12@XZ; BthAvrcpMediaController::NpsmMediaController::UpdateTrackMetadata(void)
0x1800392e6  mov     ecx, [rax]
0x1800392e8  mov     [rsp+88h+arg_18], ecx
0x1800392ef  movzx   ecx, word ptr [rax+4]
0x1800392f3  mov     [rsp+0ACh], cx
0x1800392fb  mov     al, [rax+6]
0x1800392fe  mov     [rsp+88h+arg_1E], al
0x180039305  test    cl, cl
0x180039307  jz      short loc_180039345
0x180039309  mov     qword ptr [rsp+88h+var_58], 2
0x180039312  mov     rdx, qword ptr [rsp+88h+var_48+8]
0x180039317  cmp     rdx, [rsp+88h+var_38]
0x18003931c  jz      short loc_180039336
0x18003931e  mov     rax, qword ptr [rsp+88h+var_58]
0x180039323  mov     [rdx], rax
0x180039326  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x18003932b  add     rdi, 8
0x18003932f  mov     qword ptr [rsp+88h+var_48+8], rdi
0x180039334  jmp     short loc_18003934A
0x180039336  lea     r8, [rsp+88h+var_58]
0x18003933b  lea     rcx, [rsp+88h+var_48]
0x180039340  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x180039345  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x18003934a  cmp     byte ptr [rsp+88h+arg_10+4], r13b
0x180039352  jz      short loc_180039398
0x180039354  cmp     ebx, 2
0x180039357  jnz     short loc_180039398
0x180039359  mov     qword ptr [rsp+88h+var_58], 5
0x180039362  cmp     rdi, [rsp+88h+var_38]
0x180039367  jz      short loc_180039381
0x180039369  mov     rax, qword ptr [rsp+88h+var_58]
0x18003936e  mov     [rdi], rax
0x180039371  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x180039376  add     rdi, 8
0x18003937a  mov     qword ptr [rsp+88h+var_48+8], rdi
0x18003937f  jmp     short loc_180039398
0x180039381  lea     r8, [rsp+88h+var_58]
0x180039386  mov     rdx, rdi
0x180039389  lea     rcx, [rsp+88h+var_48]
0x18003938e  call    ??$_Emplace_reallocate@AEBUBthAvMediaPlayerSetting@@@?$vector@UBthAvMediaPlayerSetting@@V?$allocator@UBthAvMediaPlayerSetting@@@std@@@std@@AEAAPEAUBthAvMediaPlayerSetting@@QEAU2@AEBU2@@Z; std::vector<BthAvMediaPlayerSetting>::_Emplace_reallocate<BthAvMediaPlayerSetting const &>(BthAvMediaPlayerSetting * const,BthAvMediaPlayerSetting const &)
0x180039393  mov     rdi, qword ptr [rsp+88h+var_48+8]
0x180039398  mov     rsi, qword ptr [rsp+88h+var_48]
0x18003939d  cmp     rsi, rdi
0x1800393a0  jz      short loc_18003941A
0x1800393a2  mov     rbx, [rsi]
0x1800393a5  mov     qword ptr [rsp+88h+var_58], rbx
0x1800393aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800393b1  cmp     rcx, r15
0x1800393b4  jz      short loc_1800393DE
0x1800393b6  test    byte ptr [rcx+1Ch], 1
0x1800393ba  jz      short loc_1800393DE
0x1800393bc  cmp     byte ptr [rcx+19h], 4
0x1800393c0  jb      short loc_1800393DE
0x1800393c2  mov     rax, rbx
0x1800393c5  shr     rax, 20h
0x1800393c9  mov     edx, 53h ; 'S'
0x1800393ce  mov     [rsp+88h+var_68], eax
0x1800393d2  mov     r9d, ebx
0x1800393d5  mov     rcx, [rcx+10h]
0x1800393d9  call    WPP_SF_dd
0x1800393de  lea     r12, [r14+20h]
0x1800393e2  mov     rcx, r12; lpCriticalSection
0x1800393e5  call    cs:__imp_EnterCriticalSection
0x1800393eb  lea     rcx, [r14+48h]
0x1800393ef  mov     rdx, rbx
0x1800393f2  call    ??$InvokeAll@UBthAvMediaApiEvent@@@?$EventSource@UIBthAvMediaEventHandler@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJUBthAvMediaApiEvent@@@Z; Microsoft::WRL::EventSource<IBthAvMediaEventHandler,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<BthAvMediaApiEvent>(BthAvMediaApiEvent)
0x1800393f7  mov     r15d, eax
0x1800393fa  test    r12, r12
0x1800393fd  jz      short loc_180039408
0x1800393ff  mov     rcx, r12; lpCriticalSection
0x180039402  call    cs:__imp_LeaveCriticalSection
0x180039408  test    r15d, r15d
0x18003940b  js      short loc_180039481
0x18003940d  add     rsi, 8
0x180039411  lea     r15, WPP_GLOBAL_Control
0x180039418  jmp     short loc_18003939D
0x18003941a  mov     rcx, cs:WPP_GLOBAL_Control
0x180039421  cmp     rcx, r15
0x180039424  jz      short loc_18003944B
0x180039426  test    byte ptr [rcx+1Ch], 1
0x18003942a  jz      short loc_18003944B
0x18003942c  cmp     byte ptr [rcx+19h], 4
0x180039430  jb      short loc_18003944B
0x180039432  mov     edx, 55h ; 'U'
0x180039437  mov     r9, r14
0x18003943a  lea     r8, WPP_95e767cb7999366f67a133efb5540c97_Traceguids
0x180039441  mov     rcx, [rcx+10h]
0x180039445  call    WPP_SF_q
0x18003944a  nop
0x18003944b  mov     rcx, qword ptr [rsp+88h+var_48]
0x180039450  test    rcx, rcx
0x180039453  jz      short loc_180039467
0x180039455  mov     rdx, [rsp+88h+var_38]
0x18003945a  sub     rdx, rcx
0x18003945d  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180039461  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180039466  nop
0x180039467  lea     r11, [rsp+88h+var_28]
0x18003946c  mov     rbx, [r11+30h]
0x180039470  mov     rsi, [r11+38h]
0x180039474  mov     rsp, r11
0x180039477  pop     r15
0x180039479  pop     r14
0x18003947b  pop     r13
0x18003947d  pop     r12
0x18003947f  pop     rdi
0x180039480  retn
0x180039481  mov     rcx, cs:WPP_GLOBAL_Control
0x180039488  lea     rax, WPP_GLOBAL_Control
0x18003948f  cmp     rcx, rax
0x180039492  jz      short loc_1800394B9
0x180039494  test    byte ptr [rcx+1Ch], 1
0x180039498  jz      short loc_1800394B9
0x18003949a  cmp     byte ptr [rcx+19h], 2
0x18003949e  jb      short loc_1800394B9
0x1800394a0  mov     edx, 54h ; 'T'
0x1800394a5  mov     eax, [rsp+88h+var_58+4]
0x1800394a9  mov     [rsp+88h+var_68], eax; int
0x1800394ad  mov     r9d, ebx
0x1800394b0  mov     rcx, [rcx+10h]
0x1800394b4  call    WPP_SF_dd
0x1800394b9  mov     ecx, r15d
0x1800394bc  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800394c1  mov     r9d, eax; char *
0x1800394c4  mov     rcx, [rsp+88h]; this
0x1800394cc  lea     r8, aOnecoreDrivers_39; "onecore\\drivers\\bluetooth\\profiles\\"...
0x1800394d3  mov     edx, 3D6h; void *
0x1800394d8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
