# GreValidateVisrgn

- ea: `0x140010594`
- end: `0x140010ad7`
- name: `GreValidateVisrgn`
- size: `1347`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000f760`
- `0x140014ea0`
- `0x14003c7e0`
- `0x1400b1300`

## callees

- `0x1400103d0`
- `0x140010594`
- `0x140010b90`
- `0x140010c18`
- `0x14001b910`
- `0x14001bca0`
- `0x14001bf60`
- `0x14001c970`
- `0x14001e2b4`
- `0x1400393dc`
- `0x14003f8c0`
- `0x14010f2b0`
- `0x14012283c`
- `0x140238b10`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1400106af`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400106af`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400106c4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400106c4`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010601`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001073b`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x140010601`
- `ntoskrnl!PsGetCurrentThreadWin32Thread` at `0x14001073b`
- `WIN32K!W32GetSessionState` at `0x1400105cb`
- `WIN32K!W32GetSessionState` at `0x140010802`
- `WIN32K!W32GetSessionState` at `0x140010857`
- `WIN32K!W32GetSessionState` at `0x140010973`
- `WIN32K!W32GetSessionState` at `0x1400105cb`
- `WIN32K!W32GetSessionState` at `0x140010802`
- `WIN32K!W32GetSessionState` at `0x140010857`
- `WIN32K!W32GetSessionState` at `0x140010973`

## pseudocode

```c
void __fastcall GreValidateVisrgn(__int64 a1, int a2)
{
  unsigned int v3; // ebx
  __int64 *CurrentThreadWin32Thread; // rax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // di
  DC *v9; // rax
  DC *v10; // rdx
  int v11; // eax
  int v12; // ecx
  unsigned int v13; // eax
  DC *v14; // r15
  struct _GRETHREAD *v15; // rax
  unsigned __int64 v16; // rcx
  struct _GRETHREAD *v17; // rbx
  __int64 v18; // rdx
  DC *v19; // rbx
  __int64 v20; // r14
  _DWORD *v21; // rsi
  __int64 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  unsigned __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  unsigned int *v28; // r9
  unsigned int *v29; // r10
  unsigned int *v30; // rax
  int v31; // eax
  int v32; // r11d
  LONG v33; // r8d
  LONG v34; // edx
  bool v35; // zf
  __int64 v36; // rax
  struct _GRETHREAD *v37; // rax
  __int64 v38; // rcx
  __int64 SessionState; // rax
  __int64 v40; // rax
  __int64 v41; // rcx
  int v42; // r14d
  LONG v43; // ebx
  __int64 v44; // rax
  bool v45; // cc
  LONG v46; // r10d
  __int64 v47; // rax
  HSURF v48; // rdx
  int v49; // r8d
  int v50; // eax
  __int128 v51; // [rsp+20h] [rbp-79h] BYREF
  __int128 v52; // [rsp+30h] [rbp-69h]
  unsigned int *v53; // [rsp+40h] [rbp-59h]
  DC *v54; // [rsp+50h] [rbp-49h] BYREF
  int v55; // [rsp+58h] [rbp-41h]
  __int64 v56; // [rsp+60h] [rbp-39h]
  __int64 v57; // [rsp+68h] [rbp-31h]
  __int128 v58; // [rsp+70h] [rbp-29h] BYREF
  __int128 v59; // [rsp+80h] [rbp-19h]
  __int64 v60; // [rsp+90h] [rbp-9h] BYREF
  _BYTE v61[16]; // [rsp+98h] [rbp-1h] BYREF
  struct _RECTL v62; // [rsp+A8h] [rbp+Fh] BYREF

  v54 = 0;
  v3 = a1;
  v55 = 0;
  v56 = *(_QWORD *)(W32GetSessionState(a1) + 88);
  v57 = 0;
  v54 = 0;
  v55 = 0;
  v58 = 0;
  v59 = 0;
  CurrentThreadWin32Thread = (__int64 *)PsGetCurrentThreadWin32Thread(v56);
  if ( CurrentThreadWin32Thread )
    v5 = *CurrentThreadWin32Thread;
  else
    v5 = 0;
  v6 = (v5 + 8) & -(__int64)(v5 != 0);
  *(_QWORD *)&v59 = &v54;
  *((_QWORD *)&v59 + 1) = UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic;
  if ( v6 )
  {
    v7 = *(_QWORD *)(((v5 + 8) & -(__int64)(v5 != 0)) + 0x58);
    if ( *(_QWORD *)(v7 + 8) != v6 + 88 )
      goto LABEL_5;
    *(_QWORD *)&v58 = *(_QWORD *)(v6 + 88);
    *((_QWORD *)&v58 + 1) = v6 + 88;
    *(_QWORD *)(v7 + 8) = &v58;
    *(_QWORD *)(v6 + 88) = &v58;
  }
  else
  {
    *((_QWORD *)&v58 + 1) = &v58;
    *(_QWORD *)&v58 = &v58;
  }
  v8 = 1;
  v9 = (DC *)HmgShareLock(v56, v3, 1, 1);
  v54 = v9;
  v10 = v9;
  if ( v9 )
  {
    v11 = *((_DWORD *)v9 + 9);
    v12 = v11 | 0x100000;
    v13 = v11 & 0xFFEFFFFF;
    if ( !a2 )
      v12 = v13;
    *((_DWORD *)v10 + 9) = v12;
    v14 = v54;
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx((char *)v14 + 1112, 0);
    GrepAcquireLockValidate<37>();
    v15 = GreGetCurrentThreadCrossSessionCheck();
    v17 = v15;
    if ( v15 )
    {
      v18 = *(_QWORD *)v15;
      if ( (*(_QWORD *)v15 & 0xFFFFFFC000000000uLL) != 0 && (v18 & 0x4000000000LL) == 0 )
      {
        v16 = 0;
        v49 = 38;
        do
        {
          v50 = v16;
          if ( ((1LL << v16) & 0xFFFFFFDFFFFFFFFFuLL & v18) == 0 )
            v50 = v49;
          ++v16;
          v49 = v50;
        }
        while ( v16 < 0x40 );
        if ( v50 > 38 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM(v16, v18);
      }
      *(_QWORD *)v17 |= 0x4000000000uLL;
    }
    v19 = v54;
    if ( (*((_DWORD *)v54 + 9) & 0x100000) == 0
      || (v20 = *((_QWORD *)v54 + 6)) == 0
      || (v21 = (_DWORD *)*((_QWORD *)v54 + 142)) == 0 )
    {
LABEL_33:
      v37 = GreGetCurrentThreadCrossSessionCheck();
      if ( v37 )
        *(_QWORD *)v37 &= ~0x4000000000uLL;
      GrePushLock::ReleaseLock((DC *)((char *)v14 + 1112));
      if ( !v8 )
      {
        DC::AcquireDcVisRgnExclusive(v54);
        v60 = *((_QWORD *)v54 + 142);
        if ( v60 )
          RGNOBJ::vSet((RGNOBJ *)&v60, &v62);
        _reset___lambda_call_V_lambda_1___1__AcquireDcVisRgnExclusive_DC__QEAA_XZ__details_wil__QEAAXXZ(v61);
      }
      if ( v54 )
      {
        SessionState = W32GetSessionState(v38);
        HmgDecrementShareReferenceCount(*(_QWORD *)(SessionState + 88), (unsigned int *)v54);
        v54 = 0;
      }
      v40 = v58;
      if ( *(__int128 **)(v58 + 8) == &v58 )
      {
        v41 = *((_QWORD *)&v58 + 1);
        if ( **((__int128 ***)&v58 + 1) == &v58 )
        {
          **((_QWORD **)&v58 + 1) = v58;
          *(_QWORD *)(v40 + 8) = v41;
          return;
        }
      }
LABEL_5:
      __fastfail(3u);
    }
    v51 = 0;
    v52 = 0;
    v22 = (__int64 *)PsGetCurrentThreadWin32Thread(v16);
    if ( v22 )
      v23 = *v22;
    else
      v23 = 0;
    v24 = v23 + 8;
    v25 = -v23;
    v26 = v24 & -(__int64)(v25 != 0);
    *(_QWORD *)&v52 = &v51;
    *((_QWORD *)&v52 + 1) = UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic;
    if ( v26 )
    {
      v27 = *(_QWORD *)((v24 & -(__int64)(v25 != 0)) + 0x58);
      if ( *(_QWORD *)(v27 + 8) != v26 + 88 )
        goto LABEL_5;
      *(_QWORD *)&v51 = *(_QWORD *)(v26 + 88);
      *((_QWORD *)&v51 + 1) = v26 + 88;
      *(_QWORD *)(v27 + 8) = &v51;
      v25 = (unsigned __int64)&v51;
      *(_QWORD *)(v26 + 88) = &v51;
    }
    else
    {
      *((_QWORD *)&v51 + 1) = &v51;
      *(_QWORD *)&v51 = &v51;
    }
    v28 = 0;
    v35 = (*((_DWORD *)v19 + 9) & 0x40000) == 0;
    v53 = 0;
    if ( v35 )
    {
      v29 = (unsigned int *)*((_QWORD *)v19 + 62);
    }
    else
    {
      v48 = (HSURF)*((_QWORD *)v19 + 268);
      if ( v48 )
      {
        SURFREF::vLock((SURFREF *)&v51, v48);
        v28 = v53;
        v29 = v53;
        v30 = v53;
LABEL_24:
        if ( !v29 )
        {
          v35 = v30 == 0;
          goto LABEL_30;
        }
        if ( (*(_DWORD *)(v20 + 40) & 0x20000) != 0 && (v29[40] & 0x80000000) != 0
          || (v31 = *((_DWORD *)v19 + 9), (v31 & 0x1000) != 0) && (v31 & 0x4000) == 0
          || (v32 = v21[13], v33 = v21[15], v32 == v33)
          || (v25 = (unsigned int)v21[14], v34 = v21[16], (_DWORD)v25 == v34)
          || v32 == 0x7FFFFFFF && v34 == 0x80000000 && (_DWORD)v25 == 0x7FFFFFFF && v33 == 0x80000000 )
        {
LABEL_29:
          v35 = v28 == 0;
LABEL_30:
          if ( !v35 )
          {
            v36 = W32GetSessionState(v25);
            HmgDecrementShareReferenceCount(*(_QWORD *)(v36 + 88), v53);
          }
          PopThreadGuardedObject(&v51);
          goto LABEL_33;
        }
        v42 = v21[13];
        v43 = v21[14];
        v44 = *(_QWORD *)((char *)v29 + ((v29[41] & 0x800) != 0 ? 0x294 : 0) + 56);
        if ( v32 >= v33 )
        {
          if ( v32 > v33 )
          {
            v42 = v21[15];
            v33 = v21[13];
          }
          v45 = (int)v25 <= v34;
        }
        else
        {
          v45 = (int)v25 <= v34;
          if ( (int)v25 < v34 )
          {
            if ( v32 >= 0 && (int)v44 >= v33 && (v25 & 0x80000000) == 0LL && SHIDWORD(v44) >= v34 )
              goto LABEL_29;
            goto LABEL_56;
          }
        }
        if ( !v45 )
        {
          v43 = v21[16];
          v34 = v21[14];
        }
LABEL_56:
        v46 = 0;
        if ( v42 >= 0 )
          v46 = v42;
        if ( v43 < 0 )
          v43 = 0;
        if ( (int)v44 < v33 )
          v33 = v44;
        if ( SHIDWORD(v44) < v34 )
          v34 = HIDWORD(v44);
        if ( v33 < v46 )
        {
          v46 = v33;
        }
        else if ( v34 < v43 )
        {
          v43 = v34;
        }
        v62.left = v46;
        v62.top = v43;
        v62.right = v33;
        v62.bottom = v34;
        if ( v28 )
        {
          v47 = W32GetSessionState(0);
          HmgDecrementShareReferenceCount(*(_QWORD *)(v47 + 88), v53);
        }
        PopThreadGuardedObject(&v51);
        v8 = 0;
        goto LABEL_33;
      }
      v29 = *(unsigned int **)(v20 + 2544);
    }
    v30 = 0;
    goto LABEL_24;
  }
  DCOBJA::~DCOBJA((DCOBJA *)&v54);
}

```

## disassembly

```asm
0x140010594  push    rbp
0x140010596  push    rbx
0x140010597  push    rsi
0x140010598  push    rdi
0x140010599  push    r14
0x14001059b  push    r15
0x14001059d  lea     rbp, [rsp-2Fh]
0x1400105a2  sub     rsp, 0C8h
0x1400105a9  mov     rax, cs:__security_cookie
0x1400105b0  xor     rax, rsp
0x1400105b3  mov     [rbp+57h+var_38], rax
0x1400105b7  mov     esi, edx
0x1400105b9  mov     [rbp+57h+var_A0], 0
0x1400105c1  mov     rbx, rcx
0x1400105c4  mov     [rbp+57h+var_98], 0
0x1400105cb  call    cs:__imp_W32GetSessionState
0x1400105d2  nop     dword ptr [rax+rax+00h]
0x1400105d7  xorps   xmm0, xmm0
0x1400105da  mov     rcx, [rax+58h]
0x1400105de  mov     [rbp+57h+var_90], rcx
0x1400105e2  mov     [rbp+57h+var_88], 0
0x1400105ea  mov     [rbp+57h+var_A0], 0
0x1400105f2  mov     [rbp+57h+var_98], 0
0x1400105f9  movups  [rbp+57h+var_80], xmm0
0x1400105fd  movups  [rbp+57h+var_70], xmm0
0x140010601  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010608  nop     dword ptr [rax+rax+00h]
0x14001060d  test    rax, rax
0x140010610  jz      loc_1400109D8
0x140010616  mov     rcx, [rax]
0x140010619  lea     rax, [rcx+8]
0x14001061d  neg     rcx
0x140010620  sbb     rdx, rdx
0x140010623  and     rdx, rax
0x140010626  lea     rax, [rbp+57h+var_A0]
0x14001062a  mov     qword ptr [rbp+57h+var_70], rax
0x14001062e  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VDCOBJA@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<DCOBJA>::OnUnexpectedThreadTerminationStatic(void *)
0x140010635  mov     qword ptr [rbp+57h+var_70+8], rax
0x140010639  jz      loc_1400109FE
0x14001063f  lea     rax, [rdx+58h]
0x140010643  mov     rcx, [rax]
0x140010646  cmp     [rcx+8], rax
0x14001064a  jz      short loc_140010653
0x14001064c  mov     ecx, 3
0x140010651  int     29h; Win8: RtlFailFast(ecx)
0x140010653  mov     qword ptr [rbp+57h+var_80], rcx
0x140010657  lea     rdx, [rbp+57h+var_80]
0x14001065b  mov     qword ptr [rbp+57h+var_80+8], rax
0x14001065f  mov     [rcx+8], rdx
0x140010663  lea     rcx, [rbp+57h+var_80]
0x140010667  mov     [rax], rcx
0x14001066a  mov     rcx, [rbp+57h+var_90]
0x14001066e  mov     edi, 1
0x140010673  mov     r9d, edi
0x140010676  mov     r8b, dil
0x140010679  mov     rdx, rbx
0x14001067c  call    ?HmgShareLock@@YAPEAU_BASEOBJECT@@AEAUSESSION_GLOBALS@Base@Gre@@PEAUHOBJ__@@EW4HandleLockOptions@@@Z; HmgShareLock(Gre::Base::SESSION_GLOBALS &,HOBJ__ *,uchar,HandleLockOptions)
0x140010681  mov     [rbp+57h+var_A0], rax
0x140010685  mov     rdx, rax
0x140010688  test    rax, rax
0x14001068b  jz      loc_1400108BF
0x140010691  mov     ecx, [rax+24h]
0x140010694  mov     r14d, 100000h
0x14001069a  mov     eax, ecx
0x14001069c  or      ecx, r14d
0x14001069f  btr     eax, 14h
0x1400106a3  test    esi, esi
0x1400106a5  cmovz   ecx, eax
0x1400106a8  mov     [rdx+24h], ecx
0x1400106ab  mov     r15, [rbp+57h+var_A0]
0x1400106af  call    cs:__imp_KeEnterCriticalRegion
0x1400106b6  nop     dword ptr [rax+rax+00h]
0x1400106bb  xor     edx, edx
0x1400106bd  lea     rcx, [r15+458h]
0x1400106c4  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400106cb  nop     dword ptr [rax+rax+00h]
0x1400106d0  call    ??$GrepAcquireLockValidate@$0CF@@@YAXXZ; GrepAcquireLockValidate<37>(void)
0x1400106d5  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x1400106da  mov     rbx, rax
0x1400106dd  test    rax, rax
0x1400106e0  jz      short loc_140010705
0x1400106e2  mov     rdx, [rax]
0x1400106e5  mov     rsi, 4000000000h
0x1400106ef  mov     rax, 0FFFFFFC000000000h
0x1400106f9  test    rax, rdx
0x1400106fc  jnz     loc_140010A6F
0x140010702  or      [rbx], rsi
0x140010705  mov     rbx, [rbp+57h+var_A0]
0x140010709  test    [rbx+24h], r14d
0x14001070d  jz      loc_140010824
0x140010713  mov     r14, [rbx+30h]
0x140010717  test    r14, r14
0x14001071a  jz      loc_140010824
0x140010720  mov     rsi, [rbx+470h]
0x140010727  test    rsi, rsi
0x14001072a  jz      loc_140010824
0x140010730  xorps   xmm0, xmm0
0x140010733  movups  [rbp+57h+var_D0], xmm0
0x140010737  movups  [rbp+57h+var_C0], xmm0
0x14001073b  call    cs:__imp_PsGetCurrentThreadWin32Thread
0x140010742  nop     dword ptr [rax+rax+00h]
0x140010747  test    rax, rax
0x14001074a  jz      loc_1400109DF
0x140010750  mov     rcx, [rax]
0x140010753  lea     rax, [rcx+8]
0x140010757  neg     rcx
0x14001075a  sbb     rdx, rdx
0x14001075d  and     rdx, rax
0x140010760  lea     rax, [rbp+57h+var_D0]
0x140010764  mov     qword ptr [rbp+57h+var_C0], rax
0x140010768  lea     rax, ?OnUnexpectedThreadTerminationStatic@?$UnexpectedThreadTerminationHandler@VCOLORSPACEREF@@@@SAXPEAX@Z; UnexpectedThreadTerminationHandler<COLORSPACEREF>::OnUnexpectedThreadTerminationStatic(void *)
0x14001076f  mov     qword ptr [rbp+57h+var_C0+8], rax
0x140010773  jz      loc_140010A2B
0x140010779  lea     rax, [rdx+58h]
0x14001077d  mov     rcx, [rax]
0x140010780  cmp     [rcx+8], rax
0x140010784  jnz     loc_14001064C
0x14001078a  mov     qword ptr [rbp+57h+var_D0], rcx
0x14001078e  lea     rdx, [rbp+57h+var_D0]
0x140010792  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140010796  mov     [rcx+8], rdx
0x14001079a  lea     rcx, [rbp+57h+var_D0]
0x14001079e  mov     [rax], rcx
0x1400107a1  xor     r9d, r9d
0x1400107a4  test    dword ptr [rbx+24h], 40000h
0x1400107ab  mov     [rbp+57h+var_B0], r9
0x1400107af  jnz     loc_1400109E6
0x1400107b5  mov     r10, [rbx+1F0h]
0x1400107bc  xor     eax, eax
0x1400107be  test    r10, r10
0x1400107c1  jz      loc_1400108CA
0x1400107c7  test    dword ptr [r14+28h], 20000h
0x1400107cf  jnz     loc_14001099D
0x1400107d5  mov     eax, [rbx+24h]
0x1400107d8  bt      eax, 0Ch
0x1400107dc  jb      loc_140010AB9
0x1400107e2  mov     r11d, [rsi+34h]
0x1400107e6  mov     r8d, [rsi+3Ch]
0x1400107ea  cmp     r11d, r8d
0x1400107ed  jz      short loc_1400107FD
0x1400107ef  mov     ecx, [rsi+38h]
0x1400107f2  mov     edx, [rsi+40h]
0x1400107f5  cmp     ecx, edx
0x1400107f7  jnz     loc_1400108D2
0x1400107fd  test    r9, r9
0x140010800  jz      short loc_14001081B
0x140010802  call    cs:__imp_W32GetSessionState
0x140010809  nop     dword ptr [rax+rax+00h]
0x14001080e  mov     rdx, [rbp+57h+var_B0]
0x140010812  mov     rcx, [rax+58h]
0x140010816  call    HmgDecrementShareReferenceCount
0x14001081b  lea     rcx, [rbp+57h+var_D0]
0x14001081f  call    PopThreadGuardedObject
0x140010824  call    ?GreGetCurrentThreadCrossSessionCheck@@YAPEAU_GRETHREAD@@XZ; GreGetCurrentThreadCrossSessionCheck(void)
0x140010829  test    rax, rax
0x14001082c  jz      short loc_14001083B
0x14001082e  mov     rcx, 0FFFFFFBFFFFFFFFFh
0x140010838  and     [rax], rcx
0x14001083b  lea     rcx, [r15+458h]; this
0x140010842  call    ?ReleaseLock@GrePushLock@@QEBAXXZ; GrePushLock::ReleaseLock(void)
0x140010847  test    dil, dil
0x14001084a  jz      loc_140010A40
0x140010850  cmp     [rbp+57h+var_A0], 0
0x140010855  jz      short loc_140010878
0x140010857  call    cs:__imp_W32GetSessionState
0x14001085e  nop     dword ptr [rax+rax+00h]
0x140010863  mov     rdx, [rbp+57h+var_A0]
0x140010867  mov     rcx, [rax+58h]
0x14001086b  call    HmgDecrementShareReferenceCount
0x140010870  mov     [rbp+57h+var_A0], 0
0x140010878  mov     rax, qword ptr [rbp+57h+var_80]
0x14001087c  lea     rcx, [rbp+57h+var_80]
0x140010880  cmp     [rax+8], rcx
0x140010884  jnz     loc_14001064C
0x14001088a  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x14001088e  lea     rdx, [rbp+57h+var_80]
0x140010892  cmp     [rcx], rdx
0x140010895  jnz     loc_14001064C
0x14001089b  mov     [rcx], rax
0x14001089e  mov     [rax+8], rcx
0x1400108a2  mov     rcx, [rbp+57h+var_38]
0x1400108a6  xor     rcx, rsp; StackCookie
0x1400108a9  call    __security_check_cookie
0x1400108ae  add     rsp, 0C8h
0x1400108b5  pop     r15
0x1400108b7  pop     r14
0x1400108b9  pop     rdi
0x1400108ba  pop     rsi
0x1400108bb  pop     rbx
0x1400108bc  pop     rbp
0x1400108bd  retn
0x1400108bf  lea     rcx, [rbp+57h+var_A0]; this
0x1400108c3  call    ??1DCOBJA@@QEAA@XZ; DCOBJA::~DCOBJA(void)
0x1400108c8  jmp     short loc_1400108A2
0x1400108ca  test    rax, rax
0x1400108cd  jmp     loc_140010800
0x1400108d2  mov     eax, 7FFFFFFFh
0x1400108d7  cmp     r11d, eax
0x1400108da  jz      loc_1400109B5
0x1400108e0  mov     eax, [r10+0A4h]
0x1400108e7  mov     r14d, r11d
0x1400108ea  and     eax, 800h
0x1400108ef  mov     ebx, ecx
0x1400108f1  neg     eax
0x1400108f3  sbb     rax, rax
0x1400108f6  and     eax, 294h
0x1400108fb  mov     rax, [rax+r10+38h]
0x140010900  mov     rsi, rax
0x140010903  shr     rsi, 20h
0x140010907  cmp     r11d, r8d
0x14001090a  jge     short loc_140010928
0x14001090c  cmp     ecx, edx
0x14001090e  jge     short loc_140010932
0x140010910  test    r11d, r11d
0x140010913  js      short loc_140010938
0x140010915  cmp     eax, r8d
0x140010918  jl      short loc_140010938
0x14001091a  test    ecx, ecx
0x14001091c  js      short loc_140010938
0x14001091e  cmp     esi, edx
0x140010920  jge     loc_1400107FD
0x140010926  jmp     short loc_140010938
0x140010928  jle     short loc_140010930
0x14001092a  mov     r14d, r8d
0x14001092d  mov     r8d, r11d
0x140010930  cmp     ecx, edx
0x140010932  jle     short loc_140010938
0x140010934  mov     ebx, edx
0x140010936  mov     edx, ecx
0x140010938  xor     r10d, r10d
0x14001093b  test    r14d, r14d
0x14001093e  cmovns  r10d, r14d
0x140010942  xor     ecx, ecx
0x140010944  test    ebx, ebx
0x140010946  cmovs   ebx, ecx
0x140010949  cmp     eax, r8d
0x14001094c  cmovl   r8d, eax
0x140010950  cmp     esi, edx
0x140010952  cmovl   edx, esi
0x140010955  cmp     r8d, r10d
0x140010958  jl      short loc_1400109B0
0x14001095a  cmp     edx, ebx
0x14001095c  jge     short loc_140010960
0x14001095e  mov     ebx, edx
0x140010960  mov     [rbp+57h+var_48.left], r10d
0x140010964  mov     [rbp+57h+var_48.top], ebx
0x140010967  mov     [rbp+57h+var_48.right], r8d
0x14001096b  mov     [rbp+57h+var_48.bottom], edx
0x14001096e  test    r9, r9
0x140010971  jz      short loc_14001098C
0x140010973  call    cs:__imp_W32GetSessionState
0x14001097a  nop     dword ptr [rax+rax+00h]
0x14001097f  mov     rdx, [rbp+57h+var_B0]
0x140010983  mov     rcx, [rax+58h]
0x140010987  call    HmgDecrementShareReferenceCount
0x14001098c  lea     rcx, [rbp+57h+var_D0]
0x140010990  call    PopThreadGuardedObject
0x140010995  xor     dil, dil
0x140010998  jmp     loc_140010824
0x14001099d  cmp     dword ptr [r10+0A0h], 0
0x1400109a5  jge     loc_1400107D5
0x1400109ab  jmp     loc_1400107FD
0x1400109b0  mov     r10d, r8d
0x1400109b3  jmp     short loc_140010960
0x1400109b5  mov     ebx, 80000000h
0x1400109ba  cmp     edx, ebx
0x1400109bc  jnz     loc_1400108E0
0x1400109c2  cmp     ecx, eax
0x1400109c4  jnz     loc_1400108E0
0x1400109ca  cmp     r8d, ebx
0x1400109cd  jnz     loc_1400108E0
0x1400109d3  jmp     loc_1400107FD
0x1400109d8  xor     ecx, ecx
0x1400109da  jmp     loc_140010619
0x1400109df  xor     ecx, ecx
0x1400109e1  jmp     loc_140010753
0x1400109e6  mov     rdx, [rbx+860h]; HSURF
0x1400109ed  test    rdx, rdx
0x1400109f0  jnz     short loc_140010A13
0x1400109f2  mov     r10, [r14+9F0h]
0x1400109f9  jmp     loc_1400107BC
0x1400109fe  lea     rax, [rbp+57h+var_80]
0x140010a02  mov     qword ptr [rbp+57h+var_80+8], rax
0x140010a06  lea     rax, [rbp+57h+var_80]
0x140010a0a  mov     qword ptr [rbp+57h+var_80], rax
0x140010a0e  jmp     loc_14001066A
0x140010a13  lea     rcx, [rbp+57h+var_D0]; this
0x140010a17  call    ?vLock@SURFREF@@QEAAXPEAUHSURF__@@@Z; SURFREF::vLock(HSURF__ *)
0x140010a1c  mov     r9, [rbp+57h+var_B0]
0x140010a20  mov     r10, r9
0x140010a23  mov     rax, r9
0x140010a26  jmp     loc_1400107BE
0x140010a2b  lea     rax, [rbp+57h+var_D0]
0x140010a2f  mov     qword ptr [rbp+57h+var_D0+8], rax
0x140010a33  lea     rax, [rbp+57h+var_D0]
0x140010a37  mov     qword ptr [rbp+57h+var_D0], rax
0x140010a3b  jmp     loc_1400107A1
0x140010a40  mov     rcx, [rbp+57h+var_A0]; this
0x140010a44  lea     rdx, [rbp+57h+var_58]
0x140010a48  call    ?AcquireDcVisRgnExclusive@DC@@QEAA@XZ; DC::AcquireDcVisRgnExclusive(void)
  ... truncated ...
```
