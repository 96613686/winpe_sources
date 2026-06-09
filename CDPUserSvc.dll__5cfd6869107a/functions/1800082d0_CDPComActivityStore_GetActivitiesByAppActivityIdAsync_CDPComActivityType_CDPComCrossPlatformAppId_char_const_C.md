# CDPComActivityStore::GetActivitiesByAppActivityIdAsync(CDPComActivityType,CDPComCrossPlatformAppId *,char const *,CDPComDownloadOptionFlags,CDPComNotifierData *,uint,char const *)

- ea: `0x1800082d0`
- end: `0x18000880e`
- name: `?GetActivitiesByAppActivityIdAsync@CDPComActivityStore@@UEAAJW4CDPComActivityType@@PEAUCDPComCrossPlatformAppId@@PEBDW4CDPComDownloadOptionFlags@@PEAUCDPComNotifierData@@I2@Z`
- size: `1342`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800082d0`
- `0x180008814`
- `0x1800097d0`
- `0x18000bc20`
- `0x18001e798`
- `0x180020cc4`
- `0x180023b70`
- `0x18002c5a0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800085d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008620`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800086bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008778`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800085d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008620`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800086bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008728`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180008778`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000831a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000831a`
- `cdp!CDPCreateCrossPlatformAppId` at `0x18000833b`
- `cdp!CDPCreateCrossPlatformAppId` at `0x18000833b`

## string_xrefs

- `0x1800087f5`: `onecoreuap\windows\cdp\service\cdpusersvc\CDPComActivityStore.h`
- `0x180008633`: `onecoreuap\windows\cdp\common\internal\onecore\ComConversions.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDPComActivityStore::GetActivitiesByAppActivityIdAsync(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        __int64 a4,
        __int16 a5,
        __int64 a6,
        int a7,
        __int64 a8)
{
  __int64 v9; // r15
  RTL_SRWLOCK *v10; // r13
  std::_Ref_count_base *v11; // r12
  int v12; // r14d
  __int64 v13; // rbx
  _DWORD *v14; // rax
  std::_Ref_count_base *v15; // rcx
  volatile signed __int32 *v16; // rbx
  _QWORD *v17; // rbx
  _QWORD *v18; // rdi
  __int64 v19; // rax
  int v20; // eax
  __int64 v21; // rdx
  std::_Ref_count_base *v22; // rcx
  __int64 v23; // r9
  volatile signed __int32 *v24; // rbx
  void *v25; // rbx
  _QWORD *v26; // rdi
  __int64 *ActivitiesByAppActivityId; // rax
  __int64 v28; // rcx
  std::_Ref_count_base *v29; // rcx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r9
  int v34; // eax
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // r9
  volatile signed __int32 *v38; // rdi
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  std::_Ref_count_base *v42; // rax
  std::_Ref_count_base *v43; // rcx
  unsigned int v44; // edi
  int v45; // [rsp+20h] [rbp-58h]
  int v46; // [rsp+40h] [rbp-38h] BYREF
  std::_Ref_count_base *v47[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v48; // [rsp+58h] [rbp-20h] BYREF
  std::_Ref_count_base *v49; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  unsigned int v52; // [rsp+C8h] [rbp+50h]
  __int64 v53; // [rsp+D0h] [rbp+58h] BYREF
  __int64 v54; // [rsp+D8h] [rbp+60h]

  v54 = a4;
  v52 = a2;
  if ( !a3 )
  {
    v46 = 1455;
LABEL_73:
    LODWORD(v53) = -2147024809;
    Log<long &,char const (&)[27],int>(a1, a2, &v53, a4, &v46);
    return (unsigned int)v53;
  }
  if ( !a4 )
  {
    v46 = 1456;
    goto LABEL_73;
  }
  v9 = a6;
  if ( !a6 )
  {
    v46 = 1457;
    goto LABEL_73;
  }
  v10 = (RTL_SRWLOCK *)(a1 + 32);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  v11 = 0;
  *(_OWORD *)v47 = 0;
  v48 = 0;
  v49 = (std::_Ref_count_base *)v47;
  v12 = CDPCreateCrossPlatformAppId(&v48);
  v13 = v48;
  if ( v48 )
  {
    v14 = operator new(0x18u);
    v14[2] = 1;
    v14[3] = 1;
    *(_QWORD *)v14 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
    *((_QWORD *)v14 + 2) = v13;
    v15 = v49;
    *(_QWORD *)v49 = v13;
    v16 = (volatile signed __int32 *)*((_QWORD *)v15 + 1);
    *((_QWORD *)v15 + 1) = v14;
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  else
  {
    v42 = v49;
    *(_QWORD *)v49 = 0;
    v43 = (std::_Ref_count_base *)*((_QWORD *)v42 + 1);
    *((_QWORD *)v42 + 1) = 0;
    if ( v43 )
      std::_Ref_count_base::_Decref(v43);
  }
  if ( v12 < 0 )
  {
    v40 = (unsigned int)v12;
    v41 = 71;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\windows\\cdp\\common\\internal\\onecore\\ComConversions.h",
      (const char *)v40,
      v45);
    v22 = v47[1];
    if ( v47[1] )
      std::_Ref_count_base::_Decref(v47[1]);
  }
  else
  {
    v17 = (_QWORD *)*((_QWORD *)a3 + 1);
    v18 = &v17[2 * *a3];
    while ( 1 )
    {
      v19 = *(_QWORD *)v47[0];
      if ( v17 == v18 )
        break;
      v20 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, _QWORD, _QWORD))(v19 + 64))(v47[0], *v17, v17[1]);
      v12 = v20;
      if ( v20 < 0 )
      {
        v40 = (unsigned int)v20;
        v41 = 74;
        goto LABEL_49;
      }
      v17 += 2;
    }
    (*(void (**)(void))(v19 + 8))();
    v11 = v47[0];
    v24 = (volatile signed __int32 *)v47[1];
    if ( v47[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v47[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
        if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
      }
    }
    v12 = 0;
  }
  if ( v11 )
  {
    v25 = operator new(0x18u);
    *((_DWORD *)v25 + 2) = 1;
    *((_DWORD *)v25 + 3) = 1;
    *(_QWORD *)v25 = &std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable';
    *((_QWORD *)v25 + 2) = v11;
  }
  else
  {
    v25 = (void *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    v11 = 0;
  }
  if ( v12 >= 0 )
  {
    v26 = (_QWORD *)(a1 + 176);
    v53 = v9;
    if ( *(_QWORD *)(a1 + 176) )
      goto LABEL_28;
    ActivitiesByAppActivityId = cdp::MakeSharedNoThrow<ServiceCallbackNotifier<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>,CDPComNotifierData * &>(
                                  &v48,
                                  &v53);
    v28 = *ActivitiesByAppActivityId;
    v21 = ActivitiesByAppActivityId[1];
    *ActivitiesByAppActivityId = 0;
    ActivitiesByAppActivityId[1] = 0;
    *v26 = v28;
    v29 = *(std::_Ref_count_base **)(a1 + 184);
    *(_QWORD *)(a1 + 184) = v21;
    if ( v29 )
      std::_Ref_count_base::_Decref(v29);
    v22 = v49;
    if ( v49 )
      std::_Ref_count_base::_Decref(v49);
    if ( *v26 )
    {
LABEL_28:
      v30 = 0;
    }
    else
    {
      LODWORD(v53) = -2147024882;
      v46 = 191;
      Log<long &,char const (&)[40],int>(
        (__int64)v22,
        v21,
        &v53,
        "onecoreuap\\windows\\cdp\\service\\cdpusersvc\\CDPComActivityStore.h",
        &v46);
      v30 = v53;
    }
    if ( v30 < 0 )
    {
      LODWORD(v53) = v30;
      v46 = 1463;
      Log<long &,char const (&)[27],int>((__int64)v22, v21, &v53, v23, &v46);
      if ( v25 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
      if ( v10 )
        goto LABEL_70;
    }
    else
    {
      cdp::MakeSharedNoThrow<ActivitiesByAppActivityIdCallback,std::shared_ptr<ServiceCallbackNotifier<enum CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>> &,unsigned int &>(
        &v48,
        v26,
        &a7);
      if ( v48 )
      {
        LOWORD(v45) = a5;
        v34 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, std::_Ref_count_base *, __int64, int, __int64, __int64))(**(_QWORD **)(a1 + 16) + 136LL))(
                *(_QWORD *)(a1 + 16),
                v52,
                v11,
                v54,
                v45,
                v48,
                a8);
        if ( v34 >= 0 )
        {
          v38 = (volatile signed __int32 *)v49;
          if ( v49 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v49 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
              if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
            }
          }
          if ( v25 )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(void *))v25)(v25);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)v25 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(void *))(*(_QWORD *)v25 + 8LL))(v25);
            }
          }
          if ( v10 )
            ReleaseSRWLockShared(v10);
          return 0;
        }
        LODWORD(v53) = v34;
        v46 = 1469;
        Log<long &,char const (&)[27],int>(v36, v35, &v53, v37, &v46);
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
        if ( v25 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
        if ( v10 )
        {
LABEL_70:
          ReleaseSRWLockShared(v10);
          return (unsigned int)v53;
        }
      }
      else
      {
        LODWORD(v53) = -2147024882;
        v46 = 1467;
        Log<long &,char const (&)[27],int>(v32, v31, &v53, v33, &v46);
        if ( v49 )
          std::_Ref_count_base::_Decref(v49);
        if ( v25 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
        if ( v10 )
          goto LABEL_70;
      }
    }
    return (unsigned int)v53;
  }
  LODWORD(v53) = v12;
  v46 = 1461;
  Log<long &,char const (&)[27],int>((__int64)v22, v21, &v53, v23, &v46);
  v44 = v53;
  if ( v25 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v25);
  if ( v10 )
    ReleaseSRWLockShared(v10);
  return v44;
}

```

## disassembly

```asm
0x1800082d0  mov     [rsp-40h+arg_18], r9
0x1800082d5  mov     [rsp-40h+arg_8], edx
0x1800082d9  mov     [rsp-40h+arg_0], rcx
0x1800082de  push    rbp
0x1800082df  push    rbx
0x1800082e0  push    rsi
0x1800082e1  push    rdi
0x1800082e2  push    r12
0x1800082e4  push    r13
0x1800082e6  push    r14
0x1800082e8  push    r15
0x1800082ea  mov     rbp, rsp
0x1800082ed  sub     rsp, 78h
0x1800082f1  mov     rdi, r8
0x1800082f4  test    r8, r8
0x1800082f7  jz      loc_180008786
0x1800082fd  test    r9, r9
0x180008300  jz      loc_1800087B4
0x180008306  mov     r15, [rbp+arg_28]
0x18000830a  test    r15, r15
0x18000830d  jz      loc_18000878F
0x180008313  lea     r13, [rcx+20h]
0x180008317  mov     rcx, r13; SRWLock
0x18000831a  call    cs:__imp_AcquireSRWLockShared
0x180008320  xor     r12d, r12d
0x180008323  xorps   xmm0, xmm0
0x180008326  movdqu  xmmword ptr [rbp+var_30], xmm0
0x18000832b  mov     [rbp+var_20], r12
0x18000832f  lea     rax, [rbp+var_30]
0x180008333  mov     [rbp+var_18], rax
0x180008337  lea     rcx, [rbp+var_20]
0x18000833b  call    cs:__imp_CDPCreateCrossPlatformAppId
0x180008341  mov     r14d, eax
0x180008344  mov     esi, 0FFFFFFFFh
0x180008349  mov     rbx, [rbp+var_20]
0x18000834d  test    rbx, rbx
0x180008350  jz      loc_1800086C9
0x180008356  mov     ecx, 18h; Size
0x18000835b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008360  mov     dword ptr [rax+8], 1
0x180008367  mov     dword ptr [rax+0Ch], 1
0x18000836e  lea     rcx, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x180008375  mov     [rax], rcx
0x180008378  mov     [rax+10h], rbx
0x18000837c  mov     rcx, [rbp+var_18]
0x180008380  mov     [rcx], rbx
0x180008383  mov     rbx, [rcx+8]
0x180008387  mov     [rcx+8], rax
0x18000838b  test    rbx, rbx
0x18000838e  jz      short loc_1800083BA
0x180008390  mov     eax, esi
0x180008392  lock xadd [rbx+8], eax
0x180008397  cmp     eax, 1
0x18000839a  jnz     short loc_1800083BA
0x18000839c  mov     rax, [rbx]
0x18000839f  mov     rcx, rbx
0x1800083a2  mov     rax, [rax]
0x1800083a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083aa  mov     eax, esi
0x1800083ac  lock xadd [rbx+0Ch], eax
0x1800083b1  cmp     eax, 1
0x1800083b4  jz      loc_1800087BD
0x1800083ba  test    r14d, r14d
0x1800083bd  js      loc_1800087D1
0x1800083c3  mov     rbx, [rdi+8]
0x1800083c7  mov     edi, [rdi]
0x1800083c9  shl     rdi, 4
0x1800083cd  add     rdi, rbx
0x1800083d0  mov     rcx, [rbp+var_30]
0x1800083d4  mov     rax, [rcx]
0x1800083d7  cmp     rbx, rdi
0x1800083da  jz      short loc_1800083FD
0x1800083dc  mov     r8, [rbx+8]
0x1800083e0  mov     rdx, [rbx]
0x1800083e3  mov     rax, [rax+40h]
0x1800083e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ec  mov     r14d, eax
0x1800083ef  test    eax, eax
0x1800083f1  js      loc_18000862B
0x1800083f7  add     rbx, 10h
0x1800083fb  jmp     short loc_1800083D0
0x1800083fd  mov     rax, [rax+8]
0x180008401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008406  mov     r12, [rbp+var_30]
0x18000840a  mov     rbx, [rbp+var_30+8]
0x18000840e  test    rbx, rbx
0x180008411  jz      short loc_180008448
0x180008413  mov     eax, esi
0x180008415  lock xadd [rbx+8], eax
0x18000841a  cmp     eax, 1
0x18000841d  jnz     short loc_180008448
0x18000841f  mov     rax, [rbx]
0x180008422  mov     rcx, rbx
0x180008425  mov     rax, [rax]
0x180008428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842d  mov     eax, esi
0x18000842f  lock xadd [rbx+0Ch], eax
0x180008434  cmp     eax, 1
0x180008437  jnz     short loc_180008448
0x180008439  mov     rax, [rbx]
0x18000843c  mov     rcx, rbx
0x18000843f  mov     rax, [rax+8]
0x180008443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008448  xor     r14d, r14d
0x18000844b  test    r12, r12
0x18000844e  jz      loc_18000865A
0x180008454  mov     ecx, 18h; Size
0x180008459  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000845e  mov     rbx, rax
0x180008461  mov     dword ptr [rax+8], 1
0x180008468  mov     dword ptr [rax+0Ch], 1
0x18000846f  lea     rax, ??_7?$_Ref_count_resource@PEAVICDPCrossPlatformAppId@@U?$iunknown_deleter@VICDPCrossPlatformAppId@@@detail@cdp@@@std@@6B@; const std::_Ref_count_resource<ICDPCrossPlatformAppId *,cdp::detail::iunknown_deleter<ICDPCrossPlatformAppId>>::`vftable'
0x180008476  mov     [rbx], rax
0x180008479  mov     [rbx+10h], r12
0x18000847d  test    r14d, r14d
0x180008480  js      loc_1800086F3
0x180008486  mov     r14, [rbp+arg_0]
0x18000848a  lea     rdi, [r14+0B0h]
0x180008491  mov     [rbp+arg_10], r15
0x180008495  cmp     qword ptr [rdi], 0
0x180008499  jnz     short loc_1800084EB
0x18000849b  lea     rdx, [rbp+arg_10]
0x18000849f  lea     rcx, [rbp+var_20]
0x1800084a3  call    ??$MakeSharedNoThrow@V?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@AEAPEAUCDPComNotifierData@@@cdp@@YA?AV?$shared_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@@std@@AEAPEAUCDPComNotifierData@@@Z; cdp::MakeSharedNoThrow<ServiceCallbackNotifier<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>,CDPComNotifierData * &>(CDPComNotifierData * &)
0x1800084a8  mov     rcx, [rax]
0x1800084ab  mov     rdx, [rax+8]
0x1800084af  mov     qword ptr [rax], 0
0x1800084b6  mov     qword ptr [rax+8], 0
0x1800084be  mov     [rdi], rcx
0x1800084c1  mov     rcx, [rdi+8]; this
0x1800084c5  mov     [rdi+8], rdx
0x1800084c9  test    rcx, rcx
0x1800084cc  jz      short loc_1800084D3
0x1800084ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800084d3  mov     rcx, [rbp+var_18]; this
0x1800084d7  test    rcx, rcx
0x1800084da  jz      short loc_1800084E1
0x1800084dc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800084e1  cmp     qword ptr [rdi], 0
0x1800084e5  jz      loc_1800087DE
0x1800084eb  xor     eax, eax
0x1800084ed  test    eax, eax
0x1800084ef  js      loc_1800085EA
0x1800084f5  lea     r8, [rbp+arg_30]
0x1800084f9  mov     rdx, rdi
0x1800084fc  lea     rcx, [rbp+var_20]
0x180008500  call    ??$MakeSharedNoThrow@VActivitiesByAppActivityIdCallback@@AEAV?$shared_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@@std@@AEAI@cdp@@YA?AV?$shared_ptr@VActivitiesByAppActivityIdCallback@@@std@@AEAV?$shared_ptr@V?$ServiceCallbackNotifier@W4CDPComGetActivitiesByAppActivityIdResultType@@UCDPComGetActivitiesByAppActivityIdResult@@@@@2@AEAI@Z; cdp::MakeSharedNoThrow<ActivitiesByAppActivityIdCallback,std::shared_ptr<ServiceCallbackNotifier<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>> &,uint &>(std::shared_ptr<ServiceCallbackNotifier<CDPComGetActivitiesByAppActivityIdResultType,CDPComGetActivitiesByAppActivityIdResult>> &,uint &)
0x180008505  mov     r8, [rbp+var_20]
0x180008509  test    r8, r8
0x18000850c  jz      loc_180008674
0x180008512  mov     rcx, [r14+10h]
0x180008516  mov     rax, [rcx]
0x180008519  movzx   r9d, [rbp+arg_20]
0x18000851e  mov     rdx, [rbp+arg_38]
0x180008525  mov     [rsp+78h+var_48], rdx
0x18000852a  mov     [rsp+78h+var_50], r8
0x18000852f  mov     word ptr [rsp+78h+var_58], r9w
0x180008535  mov     r9, [rbp+arg_18]
0x180008539  mov     r8, r12
0x18000853c  mov     edx, [rbp+arg_8]
0x18000853f  mov     rax, [rax+88h]
0x180008546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854b  test    eax, eax
0x18000854d  js      loc_180008735
0x180008553  mov     rdi, [rbp+var_18]
0x180008557  test    rdi, rdi
0x18000855a  jz      short loc_180008591
0x18000855c  mov     eax, esi
0x18000855e  lock xadd [rdi+8], eax
0x180008563  cmp     eax, 1
0x180008566  jnz     short loc_180008591
0x180008568  mov     rax, [rdi]
0x18000856b  mov     rcx, rdi
0x18000856e  mov     rax, [rax]
0x180008571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008576  mov     eax, esi
0x180008578  lock xadd [rdi+0Ch], eax
0x18000857d  cmp     eax, 1
0x180008580  jnz     short loc_180008591
0x180008582  mov     rax, [rdi]
0x180008585  mov     rcx, rdi
0x180008588  mov     rax, [rax+8]
0x18000858c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008591  test    rbx, rbx
0x180008594  jz      short loc_1800085C9
0x180008596  mov     eax, esi
0x180008598  lock xadd [rbx+8], eax
0x18000859d  cmp     eax, 1
0x1800085a0  jnz     short loc_1800085C9
0x1800085a2  mov     rax, [rbx]
0x1800085a5  mov     rcx, rbx
0x1800085a8  mov     rax, [rax]
0x1800085ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b0  lock xadd [rbx+0Ch], esi
0x1800085b5  cmp     esi, 1
0x1800085b8  jnz     short loc_1800085C9
0x1800085ba  mov     rax, [rbx]
0x1800085bd  mov     rcx, rbx
0x1800085c0  mov     rax, [rax+8]
0x1800085c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c9  test    r13, r13
0x1800085cc  jz      short loc_1800085D7
0x1800085ce  mov     rcx, r13; SRWLock
0x1800085d1  call    cs:__imp_ReleaseSRWLockShared
0x1800085d7  xor     eax, eax
0x1800085d9  add     rsp, 78h
0x1800085dd  pop     r15
0x1800085df  pop     r14
0x1800085e1  pop     r13
0x1800085e3  pop     r12
0x1800085e5  pop     rdi
0x1800085e6  pop     rsi
0x1800085e7  pop     rbx
0x1800085e8  pop     rbp
0x1800085e9  retn
0x1800085ea  mov     dword ptr [rbp+arg_10], eax
0x1800085ed  mov     [rbp+var_38], 5B7h
0x1800085f4  lea     rax, [rbp+var_38]
0x1800085f8  mov     [rsp+78h+var_58], rax
0x1800085fd  lea     r8, [rbp+arg_10]
0x180008601  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180008606  test    rbx, rbx
0x180008609  jz      short loc_180008613
0x18000860b  mov     rcx, rbx; this
0x18000860e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008613  test    r13, r13
0x180008616  jnz     short loc_18000861D
0x180008618  mov     eax, dword ptr [rbp+arg_10]
0x18000861b  jmp     short loc_1800085D9
0x18000861d  mov     rcx, r13; SRWLock
0x180008620  call    cs:__imp_ReleaseSRWLockShared
0x180008626  mov     eax, dword ptr [rbp+arg_10]
0x180008629  jmp     short loc_1800085D9
0x18000862b  mov     r9d, eax; char *
0x18000862e  mov     edx, 4Ah ; 'J'; void *
0x180008633  lea     r8, aOnecoreuapWind_4; "onecoreuap\\windows\\cdp\\common\\inter"...
0x18000863a  mov     rcx, [rbp+40h]; this
0x18000863e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008643  mov     rcx, [rbp+var_30+8]; this
0x180008647  test    rcx, rcx
0x18000864a  jz      loc_18000844B
0x180008650  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008655  jmp     loc_18000844B
0x18000865a  xorps   xmm1, xmm1
0x18000865d  xorps   xmm0, xmm0
0x180008660  psrldq  xmm0, 8
0x180008665  movq    rbx, xmm0
0x18000866a  movq    r12, xmm1
0x18000866f  jmp     loc_18000847D
0x180008674  mov     dword ptr [rbp+arg_10], 8007000Eh
0x18000867b  mov     [rbp+var_38], 5BBh
0x180008682  lea     rax, [rbp+var_38]
0x180008686  mov     [rsp+78h+var_58], rax
0x18000868b  lea     r8, [rbp+arg_10]
0x18000868f  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180008694  mov     rcx, [rbp+var_18]; this
0x180008698  test    rcx, rcx
0x18000869b  jz      short loc_1800086A2
0x18000869d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800086a2  test    rbx, rbx
0x1800086a5  jz      short loc_1800086AF
0x1800086a7  mov     rcx, rbx; this
0x1800086aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800086af  test    r13, r13
0x1800086b2  jz      loc_180008618
0x1800086b8  mov     rcx, r13; SRWLock
0x1800086bb  call    cs:__imp_ReleaseSRWLockShared
0x1800086c1  mov     eax, dword ptr [rbp+arg_10]
0x1800086c4  jmp     loc_1800085D9
0x1800086c9  mov     rax, [rbp+var_18]
0x1800086cd  mov     qword ptr [rax], 0
0x1800086d4  mov     rcx, [rax+8]; this
0x1800086d8  mov     qword ptr [rax+8], 0
0x1800086e0  test    rcx, rcx
0x1800086e3  jz      loc_1800083BA
0x1800086e9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800086ee  jmp     loc_1800083BA
0x1800086f3  mov     dword ptr [rbp+arg_10], r14d
0x1800086f7  mov     [rbp+var_38], 5B5h
0x1800086fe  lea     rax, [rbp+var_38]
0x180008702  mov     [rsp+78h+var_58], rax
0x180008707  lea     r8, [rbp+arg_10]
0x18000870b  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180008710  mov     edi, dword ptr [rbp+arg_10]
0x180008713  test    rbx, rbx
0x180008716  jz      short loc_180008720
0x180008718  mov     rcx, rbx; this
0x18000871b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180008720  test    r13, r13
0x180008723  jz      short loc_18000872E
0x180008725  mov     rcx, r13; SRWLock
0x180008728  call    cs:__imp_ReleaseSRWLockShared
0x18000872e  mov     eax, edi
0x180008730  jmp     loc_1800085D9
0x180008735  mov     dword ptr [rbp+arg_10], eax
0x180008738  mov     [rbp+var_38], 5BDh
0x18000873f  lea     rax, [rbp+var_38]
0x180008743  mov     [rsp+78h+var_58], rax
0x180008748  lea     r8, [rbp+arg_10]
0x18000874c  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
  ... truncated ...
```
