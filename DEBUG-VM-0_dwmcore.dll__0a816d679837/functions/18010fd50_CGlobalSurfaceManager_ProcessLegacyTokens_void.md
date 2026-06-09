# CGlobalSurfaceManager::ProcessLegacyTokens(void)

- ea: `0x18010fd50`
- end: `0x18011029c`
- name: `?ProcessLegacyTokens@CGlobalSurfaceManager@@AEAAJXZ`
- size: `1356`
- prototype: `__int64 __fastcall(CGlobalSurfaceManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18010e9e0`

## callees

- `0x180042de0`
- `0x1800441f0`
- `0x180044350`
- `0x1800cf1c0`
- `0x18010fd50`
- `0x1801102a4`
- `0x180110480`
- `0x180110b90`
- `0x180187378`
- `0x1801ca4bc`
- `0x180228490`

## import_xrefs

- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x18010fe44`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180110138`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x18010fe44`
- `win32u!NtDCompositionGetFrameLegacyTokens` at `0x180110138`

## pseudocode

```c
__int64 __fastcall CGlobalSurfaceManager::ProcessLegacyTokens(CGlobalSurfaceManager *this, __int64 a2, __int64 a3)
{
  int v4; // r14d
  int v5; // r13d
  _QWORD *v6; // rax
  __int128 v7; // rdi
  unsigned int *v8; // r8
  int v9; // edi
  __int64 v10; // rcx
  int FrameLegacyTokens; // eax
  unsigned int *v12; // r8
  int v13; // esi
  unsigned int v14; // eax
  __int64 v15; // r12
  unsigned int j; // esi
  int v18; // eax
  char *v19; // rax
  CGdiSpriteBitmap *TargetResource; // rax
  unsigned int i; // esi
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // r13d
  int v26; // eax
  bool v27; // r12
  __int64 v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // eax
  bool v32[4]; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v33; // [rsp+3Ch] [rbp-CCh] BYREF
  int v34; // [rsp+40h] [rbp-C8h] BYREF
  int v35; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  void *v37; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v39; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+78h] [rbp-90h]
  _BYTE v41[16]; // [rsp+80h] [rbp-88h] BYREF
  void **v42; // [rsp+90h] [rbp-78h]
  __int64 v43; // [rsp+98h] [rbp-70h]
  void **v44; // [rsp+A0h] [rbp-68h]
  __int64 v45; // [rsp+A8h] [rbp-60h]
  _QWORD v46[2]; // [rsp+B0h] [rbp-58h] BYREF
  _QWORD v47[2]; // [rsp+C0h] [rbp-48h] BYREF
  char v48; // [rsp+D0h] [rbp-38h] BYREF
  int *v49; // [rsp+E0h] [rbp-28h]
  __int64 v50; // [rsp+E8h] [rbp-20h]
  int *v51; // [rsp+F0h] [rbp-18h]
  __int64 v52; // [rsp+F8h] [rbp-10h]

  v4 = 0;
  v5 = 0;
  v33 = 0;
  v35 = 0;
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Start,
      a3,
      1,
      v46);
  v6 = (_QWORD *)((char *)this + 384);
  v40 = 0;
  v39 = 0;
  if ( &v39 != (__int128 *)((char *)this + 384) )
  {
    *(_QWORD *)&v7 = *v6;
    *v6 = 0;
    *((_QWORD *)&v7 + 1) = *((_QWORD *)this + 49);
    *((_QWORD *)this + 49) = 0;
    v40 = *((_QWORD *)this + 50);
    v39 = v7;
    for ( *((_QWORD *)this + 50) = 0; (_QWORD)v7 != *((_QWORD *)&v7 + 1); *(_QWORD *)&v7 = v7 + 8 )
    {
      TargetResource = (CGdiSpriteBitmap *)CWeakReference<CGdiSpriteBitmap>::GetTargetResource(*(_QWORD *)v7);
      if ( TargetResource )
      {
        *((_BYTE *)TargetResource + 153) = 1;
        CGdiSpriteBitmap::EnsureBitmapRealization(TargetResource);
      }
    }
  }
  std::vector<wil::com_ptr_t<CWeakReference<CGdiSpriteBitmap>,wil::err_returncode_policy>>::_Tidy(&v39);
  v9 = 0;
  if ( *((_DWORD *)this + 70) )
  {
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(&Microsoft_Windows_Dwm_Core_Provider_Context, "^", v8, 1, v46);
    for ( i = 0; i < *((_DWORD *)this + 70); ++i )
    {
      v22 = *((_QWORD *)this + 32);
      v23 = 16LL * i;
      v32[0] = 0;
      ++*(_DWORD *)(v23 + v22);
      v24 = *((_QWORD *)this + 32);
      v25 = *(_DWORD *)(v23 + v24);
      v37 = *(void **)(v23 + v24 + 8);
      v26 = CLegacySurfaceManager::ProcessToken(
              (CGlobalSurfaceManager *)((char *)this + 152),
              (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v37,
              v8,
              v32);
      v9 = v26;
      if ( v26 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v26, 0x110u, 0);
        break;
      }
      v27 = v32[0];
      if ( v32[0] || v25 > 0x64 )
      {
        v30 = DynArray<ClipPlaneIterator::LineSegment,0>::RemoveAt((char *)this + 256, i);
        v9 = v30;
        if ( v30 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v30, 0x118u, 0);
          break;
        }
        operator delete(v37);
        if ( !v27 )
          ++*((_DWORD *)this + 63);
        --i;
      }
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
      McGenEventWrite_EventWriteTransfer(
        &Microsoft_Windows_Dwm_Core_Provider_Context,
        &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Stop,
        v8,
        1,
        v47);
    if ( v9 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v9, 0xF0u, 0);
      v5 = 0;
      goto LABEL_15;
    }
    v5 = 0;
  }
  v10 = 0;
  if ( g_pComposition )
    v10 = *((_QWORD *)g_pComposition + 110);
  v47[0] = v10;
  FrameLegacyTokens = NtDCompositionGetFrameLegacyTokens(v47, &v33, &v35);
  if ( FrameLegacyTokens < 0 )
  {
    v13 = FrameLegacyTokens | 0x10000000;
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, FrameLegacyTokens | 0x10000000, 0x1Du, 0);
  }
  else
  {
    v13 = 0;
  }
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
  {
    v38 = v33;
    v49 = &v34;
    v51 = (int *)&v38;
    v19 = &v48;
    v34 = v13;
    v50 = 4;
    v52 = 4;
LABEL_22:
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_GetPresentHistory,
      v12,
      3,
      v19);
  }
  while ( 1 )
  {
    *((_DWORD *)this + 62) = v13;
    if ( v13 < 0 )
      break;
    v14 = v33;
    v4 += v33;
    v15 = *((_QWORD *)this + 13);
    for ( j = 0; j < v14; ++j )
    {
      v32[0] = 0;
      v18 = CLegacySurfaceManager::ProcessToken(
              (CGlobalSurfaceManager *)((char *)this + 152),
              (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v15,
              v12,
              v32);
      v9 = v18;
      if ( v18 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0x103u, 0);
        goto LABEL_15;
      }
      if ( !v32[0] )
      {
        v31 = CLegacySurfaceManager::AddUnclaimedToken(
                (CGlobalSurfaceManager *)((char *)this + 152),
                (const struct _D3DKMT_PRESENTHISTORYTOKEN *)v15);
        v9 = v31;
        if ( v31 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v31, 0x108u, 0);
          goto LABEL_15;
        }
      }
      v15 += *(unsigned int *)(v15 + 4);
      v14 = v33;
    }
    if ( !v35 )
      break;
    ++v5;
    v28 = 0;
    if ( g_pComposition )
      v28 = *((_QWORD *)g_pComposition + 110);
    v46[0] = v28;
    v29 = NtDCompositionGetFrameLegacyTokens(v46, &v33, &v35);
    if ( v29 < 0 )
    {
      v13 = v29 | 0x10000000;
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v29 | 0x10000000, 0x1Du, 0);
    }
    else
    {
      v13 = 0;
    }
    if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
    {
      LODWORD(v37) = v33;
      v42 = (void **)&v36;
      v44 = &v37;
      v19 = v41;
      LODWORD(v36) = v13;
      v43 = 4;
      v45 = 4;
      goto LABEL_22;
    }
  }
LABEL_15:
  if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x10) != 0 )
  {
    LODWORD(v36) = v5;
    v42 = &v37;
    LODWORD(v37) = v4;
    v44 = (void **)&v36;
    v43 = 4;
    v45 = 4;
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Dwm_Core_Provider_Context,
      &EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Stop,
      v12,
      3,
      v41);
  }
  dword_1803BADFC += v4;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18010fd50  mov     r11, rsp
0x18010fd53  push    rbp
0x18010fd54  push    r12
0x18010fd56  push    r13
0x18010fd58  push    r14
0x18010fd5a  lea     rbp, [r11-28h]
0x18010fd5e  sub     rsp, 108h
0x18010fd65  mov     rax, cs:__security_cookie
0x18010fd6c  xor     rax, rsp
0x18010fd6f  mov     [rbp+20h+var_28], rax
0x18010fd73  xor     r12d, r12d
0x18010fd76  mov     [r11+10h], rbx
0x18010fd7a  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18010fd81  mov     rbx, rcx
0x18010fd84  mov     [r11-28h], r15
0x18010fd88  mov     r14d, r12d
0x18010fd8b  mov     r13d, r12d
0x18010fd8e  mov     [rsp+120h+var_EC], r12d
0x18010fd93  mov     [rsp+120h+var_E0], r12d
0x18010fd98  jnz     loc_18010FF67
0x18010fd9e  lea     rax, [rbx+180h]
0x18010fda5  mov     [rsp+120h+arg_10], rsi
0x18010fdad  lea     rcx, [rsp+120h+var_C8+8]
0x18010fdb2  mov     [rsp+120h+arg_18], rdi
0x18010fdba  mov     [rsp+120h+var_B0], r12
0x18010fdbf  xorps   xmm0, xmm0
0x18010fdc2  movdqu  [rsp+120h+var_C8+8], xmm0
0x18010fdc8  cmp     rcx, rax
0x18010fdcb  jz      short loc_18010FDFB
0x18010fdcd  mov     rdi, [rax]
0x18010fdd0  mov     [rax], r12
0x18010fdd3  mov     rsi, [rax+8]
0x18010fdd7  mov     [rax+8], r12
0x18010fddb  mov     rcx, [rax+10h]
0x18010fddf  mov     [rsp+120h+var_B0], rcx
0x18010fde4  mov     qword ptr [rsp+120h+var_C8+8], rdi
0x18010fde9  mov     [rsp+120h+var_B8], rsi
0x18010fdee  mov     [rax+10h], r12
0x18010fdf2  cmp     rdi, rsi
0x18010fdf5  jnz     loc_18010FFE3
0x18010fdfb  lea     rcx, [rsp+120h+var_C8+8]
0x18010fe00  call    ?_Tidy@?$vector@V?$com_ptr_t@V?$CWeakReference@VCGdiSpriteBitmap@@@@Uerr_returncode_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@V?$CWeakReference@VCGdiSpriteBitmap@@@@Uerr_returncode_policy@wil@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::com_ptr_t<CWeakReference<CGdiSpriteBitmap>,wil::err_returncode_policy>>::_Tidy(void)
0x18010fe05  lea     r15, [rbx+98h]
0x18010fe0c  mov     edi, r12d
0x18010fe0f  cmp     [r15+80h], r12d
0x18010fe16  ja      loc_180110035
0x18010fe1c  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x18010fe23  mov     rcx, r12
0x18010fe26  test    rax, rax
0x18010fe29  jz      short loc_18010FE32
0x18010fe2b  mov     rcx, [rax+370h]
0x18010fe32  mov     [rbp+20h+var_68], rcx
0x18010fe36  lea     r8, [rsp+120h+var_E0]
0x18010fe3b  lea     rcx, [rbp+20h+var_68]
0x18010fe3f  lea     rdx, [rsp+120h+var_EC]
0x18010fe44  call    cs:__imp_NtDCompositionGetFrameLegacyTokens
0x18010fe4a  mov     esi, eax
0x18010fe4c  test    eax, eax
0x18010fe4e  js      loc_180110237
0x18010fe54  mov     esi, r12d
0x18010fe57  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18010fe5e  jnz     loc_18010FF8E
0x18010fe64  mov     [rbx+0F8h], esi
0x18010fe6a  test    esi, esi
0x18010fe6c  js      short loc_18010FE8E
0x18010fe6e  mov     eax, [rsp+120h+var_EC]
0x18010fe72  add     r14d, eax
0x18010fe75  mov     r12, [rbx+68h]
0x18010fe79  xor     esi, esi
0x18010fe7b  cmp     esi, eax
0x18010fe7d  jb      loc_18010FF2A
0x18010fe83  cmp     [rsp+120h+var_E0], 0
0x18010fe88  jnz     loc_18011010A
0x18010fe8e  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18010fe95  mov     r15, [rsp+100h]
0x18010fe9d  mov     rsi, [rsp+120h+arg_10]
0x18010fea5  mov     rbx, [rsp+120h+arg_8]
0x18010fead  jz      short loc_18010FEFE
0x18010feaf  lea     rax, [rsp+120h+var_D0]
0x18010feb4  mov     dword ptr [rsp+120h+var_D8], r13d
0x18010feb9  mov     [rbp+20h+var_98], rax
0x18010febd  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Stop
0x18010fec4  lea     rax, [rsp+120h+var_D8]
0x18010fec9  mov     dword ptr [rsp+120h+var_D0], r14d
0x18010fece  mov     [rbp+20h+var_88], rax
0x18010fed2  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x18010fed9  lea     rax, [rsp+78h]
0x18010fede  mov     [rbp+20h+var_90], 4
0x18010fee6  mov     r9d, 3
0x18010feec  mov     qword ptr [rsp+120h+var_100], rax
0x18010fef1  mov     [rbp+20h+var_80], 4
0x18010fef9  call    McGenEventWrite_EventWriteTransfer
0x18010fefe  add     cs:dword_1803BADFC, r14d
0x18010ff05  mov     eax, edi
0x18010ff07  mov     rdi, [rsp+120h+arg_18]
0x18010ff0f  mov     rcx, [rbp+20h+var_28]
0x18010ff13  xor     rcx, rsp; StackCookie
0x18010ff16  call    __security_check_cookie
0x18010ff1b  add     rsp, 108h
0x18010ff22  pop     r14
0x18010ff24  pop     r13
0x18010ff26  pop     r12
0x18010ff28  pop     rbp
0x18010ff29  retn
0x18010ff2a  lea     r9, [rsp+120h+var_F0]; bool *
0x18010ff2f  mov     [rsp+120h+var_F0], 0
0x18010ff34  mov     rdx, r12; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x18010ff37  mov     rcx, r15; this
0x18010ff3a  call    ?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z; CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)
0x18010ff3f  mov     edi, eax
0x18010ff41  test    eax, eax
0x18010ff43  js      loc_18011000E
0x18010ff49  cmp     [rsp+120h+var_F0], 0
0x18010ff4e  jz      loc_18011020D
0x18010ff54  mov     eax, [r12+4]
0x18010ff59  add     r12, rax
0x18010ff5c  mov     eax, [rsp+120h+var_EC]
0x18010ff60  inc     esi
0x18010ff62  jmp     loc_18010FE7B
0x18010ff67  lea     rax, [rbp+20h+var_78]
0x18010ff6b  mov     r9d, 1
0x18010ff71  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_Start
0x18010ff78  mov     qword ptr [rsp+120h+var_100], rax
0x18010ff7d  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x18010ff84  call    McGenEventWrite_EventWriteTransfer
0x18010ff89  jmp     loc_18010FD9E
0x18010ff8e  mov     eax, [rsp+120h+var_EC]
0x18010ff92  mov     dword ptr [rsp+120h+var_C8], eax
0x18010ff96  lea     rax, [rsp+120h+var_E8]
0x18010ff9b  mov     [rbp+20h+var_48], rax
0x18010ff9f  lea     rax, [rsp+120h+var_C8]
0x18010ffa4  mov     [rbp+20h+var_38], rax
0x18010ffa8  lea     rax, [rbp+20h+var_58]
0x18010ffac  mov     [rsp+120h+var_E8], esi
0x18010ffb0  mov     [rbp+20h+var_40], 4
0x18010ffb8  mov     [rbp+20h+var_30], 4
0x18010ffc0  mov     r9d, 3
0x18010ffc6  mov     qword ptr [rsp+120h+var_100], rax
0x18010ffcb  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSPRESENTHISTORY_GetPresentHistory
0x18010ffd2  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x18010ffd9  call    McGenEventWrite_EventWriteTransfer
0x18010ffde  jmp     loc_18010FE64
0x18010ffe3  mov     rcx, [rdi]
0x18010ffe6  call    ?GetTargetResource@?$CWeakReference@VCGdiSpriteBitmap@@@@QEBAPEAVCGdiSpriteBitmap@@XZ; CWeakReference<CGdiSpriteBitmap>::GetTargetResource(void)
0x18010ffeb  test    rax, rax
0x18010ffee  jz      short loc_18010FFFF
0x18010fff0  mov     rcx, rax; this
0x18010fff3  mov     byte ptr [rax+99h], 1
0x18010fffa  call    ?EnsureBitmapRealization@CGdiSpriteBitmap@@AEAA_NXZ; CGdiSpriteBitmap::EnsureBitmapRealization(void)
0x18010ffff  add     rdi, 8
0x180110003  cmp     rdi, rsi
0x180110006  jz      loc_18010FDFB
0x18011000c  jmp     short loc_18010FFE3
0x18011000e  xor     r12d, r12d
0x180110011  mov     [rsp+120h+var_F8], r12; void *
0x180110016  mov     [rsp+120h+var_100], 103h; unsigned int
0x18011001e  mov     r9d, eax; int
0x180110021  xor     r8d, r8d; unsigned int
0x180110024  xor     edx, edx; int *
0x180110026  mov     ecx, 14h; unsigned int
0x18011002b  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180110030  jmp     loc_18010FE8E
0x180110035  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x18011003c  jnz     loc_1801101B7
0x180110042  mov     esi, r12d
0x180110045  cmp     esi, [r15+80h]
0x18011004c  jnb     short loc_1801100A9
0x18011004e  mov     rax, [r15+68h]
0x180110052  lea     r9, [rsp+120h+var_F0]; bool *
0x180110057  mov     ecx, esi
0x180110059  shl     rcx, 4
0x18011005d  mov     [rsp+120h+var_F0], r14b
0x180110062  inc     dword ptr [rcx+rax]
0x180110065  mov     rax, [r15+68h]
0x180110069  mov     r13d, [rcx+rax]
0x18011006d  mov     rax, [rcx+rax+8]
0x180110072  mov     rcx, r15; this
0x180110075  mov     rdx, rax; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x180110078  mov     [rsp+120h+var_D0], rax
0x18011007d  call    ?ProcessToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@PEAIPEA_N@Z; CLegacySurfaceManager::ProcessToken(_D3DKMT_PRESENTHISTORYTOKEN const *,uint *,bool *)
0x180110082  mov     edi, eax
0x180110084  test    eax, eax
0x180110086  js      loc_180110190
0x18011008c  movzx   r12d, [rsp+120h+var_F0]
0x180110092  test    r12b, r12b
0x180110095  jnz     loc_1801101DE
0x18011009b  cmp     r13d, 64h ; 'd'
0x18011009f  ja      loc_1801101DE
0x1801100a5  inc     esi
0x1801100a7  jmp     short loc_180110045
0x1801100a9  xor     r12d, r12d
0x1801100ac  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x1801100b3  jz      short loc_1801100D7
0x1801100b5  lea     rax, [rbp+20h+var_68]
0x1801100b9  mov     r9d, 1
0x1801100bf  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Stop
0x1801100c6  mov     qword ptr [rsp+120h+var_100], rax
0x1801100cb  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801100d2  call    McGenEventWrite_EventWriteTransfer
0x1801100d7  test    edi, edi
0x1801100d9  js      short loc_1801100E3
0x1801100db  mov     r13d, r14d
0x1801100de  jmp     loc_18010FE1C
0x1801100e3  mov     [rsp+120h+var_F8], r12; void *
0x1801100e8  mov     r9d, edi; int
0x1801100eb  xor     r8d, r8d; unsigned int
0x1801100ee  mov     [rsp+120h+var_100], 0F0h; unsigned int
0x1801100f6  xor     edx, edx; int *
0x1801100f8  mov     ecx, 14h; unsigned int
0x1801100fd  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180110102  mov     r13d, r14d
0x180110105  jmp     loc_18010FE8E
0x18011010a  mov     rax, cs:?g_pComposition@@3PEAVCComposition@@EA; CComposition * g_pComposition
0x180110111  xor     r12d, r12d
0x180110114  inc     r13d
0x180110117  mov     ecx, r12d
0x18011011a  test    rax, rax
0x18011011d  jz      short loc_180110126
0x18011011f  mov     rcx, [rax+370h]
0x180110126  mov     [rbp+20h+var_78], rcx
0x18011012a  lea     r8, [rsp+120h+var_E0]
0x18011012f  lea     rcx, [rbp+20h+var_78]
0x180110133  lea     rdx, [rsp+120h+var_EC]
0x180110138  call    cs:__imp_NtDCompositionGetFrameLegacyTokens
0x18011013e  mov     esi, eax
0x180110140  test    eax, eax
0x180110142  js      loc_18011025F
0x180110148  mov     esi, r12d
0x18011014b  test    byte ptr cs:Microsoft_Windows_Dwm_CoreEnableBits, 10h
0x180110152  jz      loc_18010FE64
0x180110158  mov     eax, [rsp+120h+var_EC]
0x18011015c  mov     dword ptr [rsp+120h+var_D0], eax
0x180110160  lea     rax, [rsp+120h+var_D8]
0x180110165  mov     [rbp+20h+var_98], rax
0x180110169  lea     rax, [rsp+120h+var_D0]
0x18011016e  mov     [rbp+20h+var_88], rax
0x180110172  lea     rax, [rsp+78h]
0x180110177  mov     dword ptr [rsp+120h+var_D8], esi
0x18011017b  mov     [rbp+20h+var_90], 4
0x180110183  mov     [rbp+20h+var_80], 4
0x18011018b  jmp     loc_18010FFC0
0x180110190  xor     r12d, r12d
0x180110193  mov     [rsp+120h+var_F8], r12; void *
0x180110198  mov     [rsp+120h+var_100], 110h; unsigned int
0x1801101a0  mov     r9d, eax; int
0x1801101a3  xor     r8d, r8d; unsigned int
0x1801101a6  xor     edx, edx; int *
0x1801101a8  mov     ecx, 14h; unsigned int
0x1801101ad  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1801101b2  jmp     loc_1801100AC
0x1801101b7  lea     rax, [rbp+20h+var_78]
0x1801101bb  mov     r9d, 1
0x1801101c1  lea     rdx, EVTDESC_MILEVENT_MEDIA_UCE_PROCESSDEFERREDTOKENS_Start; "^"
0x1801101c8  mov     qword ptr [rsp+120h+var_100], rax
0x1801101cd  lea     rcx, Microsoft_Windows_Dwm_Core_Provider_Context
0x1801101d4  call    McGenEventWrite_EventWriteTransfer
0x1801101d9  jmp     loc_180110042
0x1801101de  mov     edx, esi
0x1801101e0  lea     rcx, [r15+68h]
0x1801101e4  call    ?RemoveAt@?$DynArray@ULineSegment@ClipPlaneIterator@@$0A@@@QEAAJI@Z; DynArray<ClipPlaneIterator::LineSegment,0>::RemoveAt(uint)
0x1801101e9  mov     edi, eax
0x1801101eb  test    eax, eax
0x1801101ed  js      loc_180110287
0x1801101f3  mov     rcx, [rsp+120h+var_D0]; void *
0x1801101f8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801101fd  test    r12b, r12b
0x180110200  jnz     short loc_180110206
0x180110202  inc     dword ptr [r15+64h]
0x180110206  dec     esi
0x180110208  jmp     loc_1801100A5
0x18011020d  mov     rdx, r12; struct _D3DKMT_PRESENTHISTORYTOKEN *
0x180110210  mov     rcx, r15; this
0x180110213  call    ?AddUnclaimedToken@CLegacySurfaceManager@@IEAAJPEBU_D3DKMT_PRESENTHISTORYTOKEN@@@Z; CLegacySurfaceManager::AddUnclaimedToken(_D3DKMT_PRESENTHISTORYTOKEN const *)
0x180110218  mov     edi, eax
0x18011021a  test    eax, eax
0x18011021c  jns     loc_18010FF54
0x180110222  xor     r12d, r12d
0x180110225  mov     [rsp+120h+var_F8], r12
0x18011022a  mov     [rsp+120h+var_100], 108h
0x180110232  jmp     loc_18011001E
0x180110237  bts     esi, 1Ch
0x18011023b  mov     [rsp+120h+var_F8], r12; void *
0x180110240  mov     r9d, esi; int
0x180110243  mov     [rsp+120h+var_100], 1Dh; unsigned int
0x18011024b  xor     r8d, r8d; unsigned int
0x18011024e  xor     edx, edx; int *
0x180110250  mov     ecx, 14h; unsigned int
0x180110255  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18011025a  jmp     loc_18010FE57
0x18011025f  bts     esi, 1Ch
0x180110263  mov     [rsp+120h+var_F8], r12; void *
0x180110268  mov     r9d, esi; int
0x18011026b  mov     [rsp+120h+var_100], 1Dh; unsigned int
0x180110273  xor     r8d, r8d; unsigned int
0x180110276  xor     edx, edx; int *
0x180110278  mov     ecx, 14h; unsigned int
0x18011027d  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180110282  jmp     loc_18011014B
0x180110287  xor     r12d, r12d
0x18011028a  mov     [rsp+120h+var_F8], r12
  ... truncated ...
```
