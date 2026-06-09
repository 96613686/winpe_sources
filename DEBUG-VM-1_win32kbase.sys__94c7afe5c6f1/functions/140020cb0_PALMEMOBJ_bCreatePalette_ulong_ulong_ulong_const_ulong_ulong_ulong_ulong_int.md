# PALMEMOBJ::bCreatePalette(ulong,ulong,ulong const *,ulong,ulong,ulong,ulong,int)

- ea: `0x140020cb0`
- end: `0x140021600`
- name: `?bCreatePalette@PALMEMOBJ@@QEAAHKKPEBKKKKKH@Z`
- size: `2384`
- prototype: `__int64 __fastcall(PALMEMOBJ *__hidden this, unsigned int, unsigned int, const unsigned int *, unsigned int, unsigned int, unsigned int, unsigned int, int)`
- caller_count: `6`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x140021c00`
- `0x14010b42c`
- `0x140174e10`
- `0x1401b0c40`
- `0x1401e5988`
- `0x1402db008`

## callees

- `0x1400204f0`
- `0x140020cb0`
- `0x140021608`
- `0x14002164c`
- `0x1400411c0`
- `0x140041450`
- `0x140042490`
- `0x14008e14c`
- `0x1400900c8`
- `0x140090964`
- `0x1401ad340`
- `0x140238c40`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140020e11`
- `ntoskrnl!ExAllocatePool2` at `0x1400211f7`
- `ntoskrnl!ExAllocatePool2` at `0x14002137a`
- `ntoskrnl!ExAllocatePool2` at `0x140020e11`
- `ntoskrnl!ExAllocatePool2` at `0x1400211f7`
- `ntoskrnl!ExAllocatePool2` at `0x14002137a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021245`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x140021245`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002113f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002113f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140020daa`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140020daa`
- `WIN32K!W32GetSessionState` at `0x140020cda`
- `WIN32K!W32GetSessionState` at `0x140020d82`
- `WIN32K!W32GetSessionState` at `0x1400210ef`
- `WIN32K!W32GetSessionState` at `0x140020cda`
- `WIN32K!W32GetSessionState` at `0x140020d82`
- `WIN32K!W32GetSessionState` at `0x1400210ef`
- `WIN32K!W32GetUserSessionState` at `0x140020dcb`
- `WIN32K!W32GetUserSessionState` at `0x140020dcb`

## pseudocode

```c
__int64 __fastcall PALMEMOBJ::bCreatePalette(
        struct OBJECT **this,
        int a2,
        unsigned int a3,
        const unsigned int *a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        int a9)
{
  __int64 SessionState; // rax
  unsigned int v13; // r13d
  unsigned int v14; // r15d
  unsigned int v15; // ebx
  unsigned int v16; // esi
  unsigned int v17; // edi
  __int64 v18; // rcx
  struct OBJECT *v19; // rax
  __int64 UserSessionState; // rax
  unsigned __int64 v21; // rcx
  __int64 v22; // r13
  int v23; // eax
  __int64 Pool2; // rcx
  _DWORD *v25; // r8
  int k; // ecx
  int v27; // eax
  unsigned int v28; // edx
  int v29; // eax
  int v30; // r9d
  unsigned int v31; // eax
  _DWORD *v32; // r10
  int m; // ecx
  int v34; // eax
  unsigned int v35; // edx
  int v36; // eax
  int v37; // r8d
  _DWORD *v38; // r9
  int n; // ecx
  int v40; // eax
  unsigned int v41; // edx
  int v42; // eax
  struct Gre::Base::SESSION_GLOBALS *v43; // rsi
  int v44; // r8d
  struct OBJECT *v45; // rax
  int v46; // ecx
  int v47; // ecx
  struct HOBJ__ *inserted; // rax
  struct OBJECT *v49; // rbx
  unsigned int v50; // r8d
  void *v52; // rcx
  struct OBJECT *v53; // rbx
  __int64 v54; // rcx
  _DWORD *v55; // rdx
  int v56; // r12d
  _DWORD *v57; // rcx
  const unsigned int *v58; // r9
  _QWORD *v59; // rax
  unsigned int j; // r8d
  int v61; // eax
  unsigned __int64 i; // rax
  int v63; // r12d
  unsigned __int64 Buffer; // [rsp+20h] [rbp-148h]
  __int64 Buffera; // [rsp+20h] [rbp-148h]
  PVOID Bufferb; // [rsp+20h] [rbp-148h]
  struct Gre::Base::SESSION_GLOBALS *v67; // [rsp+28h] [rbp-140h]
  unsigned __int64 v68; // [rsp+30h] [rbp-138h]
  _BYTE v70[32]; // [rsp+60h] [rbp-108h] BYREF
  struct OBJECT *v71; // [rsp+80h] [rbp-E8h]
  PVOID BackTrace[27]; // [rsp+90h] [rbp-D8h] BYREF
  char v73; // [rsp+178h] [rbp+10h]
  unsigned int v74; // [rsp+180h] [rbp+18h]

  v74 = a3;
  SessionState = W32GetSessionState(this);
  if ( a2 != 16 )
  {
    if ( a2 == 1 )
    {
      v13 = 4 * a3 + 4;
      if ( !a3 )
        return 0;
      v14 = a8 & 0x3102F00;
      goto LABEL_8;
    }
    if ( a2 == 2 )
    {
      v15 = a5;
      if ( !a5 )
        return 0;
      v17 = a7;
      if ( !a7 )
        return 0;
      v16 = a6;
      if ( !a6 )
        return 0;
      v14 = a8 & 0x3100300;
      v74 = 0;
      v13 = 52;
      goto LABEL_9;
    }
    if ( a2 != 4 && a2 != 8 )
      return 0;
  }
  v13 = 4;
  v14 = a8 & 0x3100100 | 0x200;
  v74 = 0;
  if ( a2 != 16 )
  {
    if ( a2 == 4 )
    {
      v15 = 255;
      v16 = 65280;
      v17 = 16711680;
    }
    else
    {
      v15 = 16711680;
      v16 = 65280;
      v17 = 255;
    }
    v13 = 52;
    goto LABEL_9;
  }
LABEL_8:
  v15 = a5;
  v16 = a6;
  v17 = a7;
LABEL_9:
  v67 = *(struct Gre::Base::SESSION_GLOBALS **)(SessionState + 88);
  v18 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v67) + 88) + 4384LL) + 8LL);
  if ( v18 )
    v19 = (struct OBJECT *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)(v18 + 48));
  else
    v19 = 0;
  *this = v19;
  if ( !v19 )
    return 0;
  if ( !v13 )
    goto LABEL_80;
  UserSessionState = W32GetUserSessionState(v18);
  v21 = v13;
  Buffer = v13;
  v22 = UserSessionState + 72016;
  v23 = *(_DWORD *)(UserSessionState + 72016);
  if ( !v23 )
    goto LABEL_14;
  if ( v23 != 1 )
  {
    if ( v23 == 2 )
    {
      if ( (*(_DWORD *)(v22 + 80) & 0x6C706147) != 0x6C706147 )
      {
LABEL_14:
        Pool2 = ExAllocatePool2(256, v21, 1819304263);
        if ( Pool2 )
          _InterlockedIncrement64((volatile signed __int64 *)(v22 + 112));
        goto LABEL_16;
      }
      for ( i = 0; ; ++i )
      {
        v68 = i;
        if ( i >= *(unsigned int *)(v22 + 84) )
          goto LABEL_14;
        if ( *(_DWORD *)(v22 + 4 * i + 48) == 1819304263 )
          break;
      }
      if ( v21 < 0x1000 || (v73 = 0, (v21 & 0xFFF) != 0) )
      {
        v73 = 1;
        v21 += 16LL;
      }
      Buffera = ExAllocatePool2(256, v21, 1819304263);
      if ( Buffera )
      {
        _InterlockedIncrement64((volatile signed __int64 *)(v22 + 128));
        memset(BackTrace, 0, 0xA0u);
        RtlCaptureStackBackTrace(0, 0x14u, BackTrace, 0);
        if ( v73 && (unsigned __int64)(Buffera & 0xFFF) + 16 < 0x1000 )
        {
          if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<1>(
                                  v22,
                                  Buffera,
                                  v68,
                                  BackTrace) )
          {
            Pool2 = Buffera + 16;
            goto LABEL_16;
          }
        }
        else if ( (unsigned __int8)NSInstrumentation::CLeakTrackingAllocator::AssociateAllocationWithBacktrace<0>(
                                     v22,
                                     Buffera,
                                     v68,
                                     BackTrace) )
        {
          Pool2 = Buffera;
          goto LABEL_16;
        }
        _InterlockedIncrement64((volatile signed __int64 *)(v22 + 136));
        _lambda_2af9a864ca5eb776d3057466a2e51944_::_lambda_invoker_cdecl_<void *>((PVOID)Buffera);
        goto LABEL_80;
      }
    }
    goto LABEL_80;
  }
  if ( !NSInstrumentation::CLeakTrackingAllocator::EnsurePoolTagIncrement(
          (NSInstrumentation::CLeakTrackingAllocator *)v22,
          0x6C706147u)
    || Buffer + 16 < Buffer )
  {
LABEL_80:
    Pool2 = 0;
    goto LABEL_16;
  }
  v59 = (_QWORD *)ExAllocatePool2(256, Buffer + 16, 1819304263);
  if ( !v59 )
  {
    Bufferb = 0;
    goto LABEL_95;
  }
  _InterlockedIncrement64((volatile signed __int64 *)(v22 + 112));
  *v59 = 1819304263;
  Pool2 = (__int64)(v59 + 2);
  Bufferb = v59 + 2;
  if ( v59 == (_QWORD *)-16LL )
  {
LABEL_95:
    NSInstrumentation::CPointerHashTable::LookupInterlockedDecrement(
      *(NSInstrumentation::CPointerHashTable **)(v22 + 8),
      (const void *)0x6C706147);
    Pool2 = (__int64)Bufferb;
  }
LABEL_16:
  *((_QWORD *)*this + 16) = Pool2;
  if ( *((_QWORD *)*this + 16) )
  {
    *((_DWORD *)*this + 6) = v14 | a2;
    *((_DWORD *)*this + 7) = v74;
    *((_DWORD *)*this + 8) = _InterlockedIncrement((volatile signed __int32 *)v67 + 944);
    *((_QWORD *)*this + 5) = 0;
    *((_QWORD *)*this + 6) = 0;
    *((_DWORD *)*this + 15) = 0;
    *((_DWORD *)*this + 14) = 0;
    *((_QWORD *)*this + 9) = 0;
    *((_QWORD *)*this + 10) = 0;
    *((_QWORD *)*this + 11) = 0;
    *((_DWORD *)*this + 9) = 0;
    *((_QWORD *)*this + 13) = 0;
    *((_QWORD *)*this + 15) = *this;
    *((_QWORD *)*this + 14) = *((_QWORD *)*this + 16);
    if ( a2 != 8 )
    {
      v56 = a2 - 1;
      if ( !v56 )
      {
        v57 = (_DWORD *)*((_QWORD *)*this + 14);
        v58 = a4;
        if ( a4 )
        {
          for ( j = 0; j < v74; ++j )
          {
            v61 = *v58++;
            *v57++ = v61;
          }
          v44 = 4;
          v43 = v67;
LABEL_48:
          v45 = *this;
          if ( *((_DWORD *)*this + 7) )
          {
            v47 = 2;
            v44 = 1;
LABEL_53:
            *((_DWORD *)v45 + 25) = v44;
            *((_DWORD *)*this + 24) = v47;
            HmgInsertObjectHelper::HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
            inserted = 0;
            if ( !v71 )
            {
              v49 = *this;
              v50 = 11;
              if ( !a9 )
                v50 = 3;
              inserted = HmgInsertObjectInternal(v43, *this, v50, 8u);
              if ( !inserted )
              {
LABEL_60:
                HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
                v52 = (void *)*((_QWORD *)*this + 16);
                if ( v52 )
                  GreDeleteFastMutex(v52);
                v53 = *this;
                v54 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(W32GetSessionState(v52) + 88) + 4384LL) + 8LL);
                if ( v54 )
                {
                  *(_OWORD *)v53 = 0;
                  *((_OWORD *)v53 + 1) = 0;
                  *((_OWORD *)v53 + 2) = 0;
                  *((_OWORD *)v53 + 3) = 0;
                  *((_OWORD *)v53 + 4) = 0;
                  *((_OWORD *)v53 + 5) = 0;
                  *((_OWORD *)v53 + 6) = 0;
                  *((_OWORD *)v53 + 7) = 0;
                  *((_OWORD *)v53 + 8) = 0;
                  ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v54 + 48), v53);
                }
                *this = 0;
                return 0;
              }
              v71 = v49;
            }
            if ( inserted )
            {
              HmgInsertObjectHelper::~HmgInsertObjectHelper((HmgInsertObjectHelper *)v70);
              return 1;
            }
            goto LABEL_60;
          }
          v46 = *((_DWORD *)v45 + 6);
          if ( (v46 & 2) == 0 )
          {
            if ( (v46 & 8) != 0 )
              v44 = 6;
            else
              v44 = 8 - ((v46 & 0x10) != 0);
            goto LABEL_52;
          }
          v55 = (_DWORD *)*((_QWORD *)v45 + 14);
          if ( v55[2] == 31 )
          {
            if ( v55[1] == 2016 && *v55 == 63488 )
            {
              v44 = 3;
              goto LABEL_52;
            }
            if ( v55[1] == 992 && *v55 == 31744 )
              goto LABEL_52;
          }
          v44 = 5;
LABEL_52:
          v47 = v44;
          goto LABEL_53;
        }
        if ( !v74 )
        {
          v43 = v67;
          goto LABEL_47;
        }
        memset(v57, 0, 4LL * v74);
LABEL_46:
        v43 = v67;
LABEL_47:
        v44 = 4;
        goto LABEL_48;
      }
      v63 = v56 - 1;
      if ( v63 && v63 != 2 )
      {
        v43 = v67;
        goto LABEL_47;
      }
    }
    **((_DWORD **)*this + 14) = v15;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 4LL) = v16;
    *(_DWORD *)(*((_QWORD *)*this + 14) + 8LL) = v17;
    if ( v15 == 255 && v16 == 65280 && v17 == 16711680 )
    {
      *((_DWORD *)*this + 6) |= 4u;
    }
    else if ( v15 == 63488 && v16 == 2016 && v17 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x400000u;
    }
    else if ( v15 == 31744 && v16 == 992 && v17 == 31 )
    {
      *((_DWORD *)*this + 6) |= 0x200000u;
    }
    v25 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( k = 0; (v15 & 1) == 0; ++k )
      v15 >>= 1;
    v27 = k;
    do
    {
      v15 >>= 1;
      ++v27;
    }
    while ( (v15 & 1) != 0 );
    v28 = v27 - k;
    v25[9] = v27 - k;
    v29 = v27 - 8;
    if ( v28 <= 8 )
      v29 = k;
    v25[6] = v29;
    v30 = 8;
    if ( v28 > 8 )
      v31 = 0;
    else
      v31 = 8 - v28;
    v25[3] = v31;
    v32 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( m = 0; (v16 & 1) == 0; ++m )
      v16 >>= 1;
    v34 = m;
    do
    {
      v16 >>= 1;
      ++v34;
    }
    while ( (v16 & 1) != 0 );
    v35 = v34 - m;
    v32[10] = v34 - m;
    v36 = v34 - 8;
    if ( v35 <= 8 )
      v36 = m;
    v32[7] = v36;
    v37 = 16;
    if ( v35 <= 8 )
      v30 = 16 - v35;
    v32[4] = v30;
    v38 = (_DWORD *)*((_QWORD *)*this + 14);
    for ( n = 0; (v17 & 1) == 0; ++n )
      v17 >>= 1;
    v40 = n;
    do
    {
      v17 >>= 1;
      ++v40;
    }
    while ( (v17 & 1) != 0 );
    v41 = v40 - n;
    v38[11] = v40 - n;
    v42 = v40 - 8;
    if ( v41 <= 8 )
      v42 = n;
    v38[8] = v42;
    if ( v41 <= 8 )
      v37 = 24 - v41;
    v38[5] = v37;
    goto LABEL_46;
  }
  XEPALOBJ_FreePaletteMemory(this);
  return 0;
}

```

## disassembly

```asm
0x140020cb0  mov     [rsp+arg_10], r8d
0x140020cb5  mov     [rsp+arg_0], rcx
0x140020cba  push    rbx
0x140020cbb  push    rsi
0x140020cbc  push    rdi
0x140020cbd  push    r12
0x140020cbf  push    r13
0x140020cc1  push    r14
0x140020cc3  push    r15
0x140020cc5  sub     rsp, 130h
0x140020ccc  mov     [rsp+168h+var_118], r9
0x140020cd1  mov     ebx, r8d
0x140020cd4  mov     r12d, edx
0x140020cd7  mov     r14, rcx
0x140020cda  call    cs:__imp_W32GetSessionState
0x140020ce1  nop     dword ptr [rax+rax+00h]
0x140020ce6  cmp     r12d, 10h
0x140020cea  jnz     loc_140021170
0x140020cf0  mov     r13d, 4
0x140020cf6  mov     r15d, [rsp+168h+arg_38]
0x140020cfe  and     r15d, 3100100h
0x140020d05  bts     r15d, 9
0x140020d0a  mov     [rsp+168h+arg_10], 0
0x140020d15  cmp     r12d, 10h
0x140020d19  jz      short loc_140020D64
0x140020d1b  cmp     r12d, r13d
0x140020d1e  jz      loc_140021322
0x140020d24  cmp     r12d, 8
0x140020d28  jnz     loc_140021567
0x140020d2e  mov     ebx, 0FF0000h
0x140020d33  mov     esi, 0FF00h
0x140020d38  mov     edi, 0FFh
0x140020d3d  mov     r13d, 34h ; '4'
0x140020d43  jmp     short loc_140020D79
0x140020d45  lea     r13d, ds:4[rbx*4]
0x140020d4d  test    ebx, ebx
0x140020d4f  jz      loc_14002114E
0x140020d55  mov     r15d, [rsp+168h+arg_38]
0x140020d5d  and     r15d, 3102F00h
0x140020d64  mov     ebx, [rsp+168h+arg_20]
0x140020d6b  mov     esi, [rsp+168h+arg_28]
0x140020d72  mov     edi, [rsp+168h+arg_30]
0x140020d79  mov     rcx, [rax+58h]
0x140020d7d  mov     [rsp+168h+var_140], rcx
0x140020d82  call    cs:__imp_W32GetSessionState
0x140020d89  nop     dword ptr [rax+rax+00h]
0x140020d8e  mov     rcx, [rax+58h]
0x140020d92  mov     rax, [rcx+1120h]
0x140020d99  mov     rcx, [rax+8]
0x140020d9d  test    rcx, rcx
0x140020da0  jz      loc_140021581
0x140020da6  add     rcx, 30h ; '0'; Lookaside
0x140020daa  call    cs:__imp_ExAllocateFromLookasideListEx
0x140020db1  nop     dword ptr [rax+rax+00h]
0x140020db6  mov     [r14], rax
0x140020db9  test    rax, rax
0x140020dbc  jz      loc_14002114E
0x140020dc2  test    r13d, r13d
0x140020dc5  jz      loc_140021296
0x140020dcb  call    cs:__imp_W32GetUserSessionState
0x140020dd2  nop     dword ptr [rax+rax+00h]
0x140020dd7  add     rax, 11950h
0x140020ddd  mov     [rsp+168h+var_130], 6C706147h
0x140020de5  mov     [rsp+168h+var_120], 100h
0x140020dee  mov     ecx, r13d
0x140020df1  mov     [rsp+168h+Buffer], rcx
0x140020df6  mov     r13, rax
0x140020df9  mov     eax, [rax]
0x140020dfb  test    eax, eax
0x140020dfd  jnz     loc_14002133C
0x140020e03  mov     r8d, 6C706147h
0x140020e09  mov     rdx, rcx
0x140020e0c  mov     ecx, 100h
0x140020e11  call    cs:__imp_ExAllocatePool2
0x140020e18  nop     dword ptr [rax+rax+00h]
0x140020e1d  mov     rcx, rax
0x140020e20  test    rax, rax
0x140020e23  jz      short loc_140020E2A
0x140020e25  lock inc qword ptr [r13+70h]
0x140020e2a  xor     r13d, r13d
0x140020e2d  mov     rax, [r14]
0x140020e30  mov     [rax+80h], rcx
0x140020e37  mov     rcx, [r14]
0x140020e3a  cmp     qword ptr [rcx+80h], 0
0x140020e42  jz      loc_1400215A3
0x140020e48  mov     r10, [rsp+168h+var_140]
0x140020e4d  mov     [rsp+168h+var_120], r10
0x140020e52  mov     r9d, 1
0x140020e58  mov     eax, r12d
0x140020e5b  or      eax, r15d
0x140020e5e  mov     [rcx+18h], eax
0x140020e61  mov     rax, [r14]
0x140020e64  mov     edx, [rsp+168h+arg_10]
0x140020e6b  mov     [rax+1Ch], edx
0x140020e6e  mov     ecx, r9d
0x140020e71  lock xadd [r10+0EC0h], ecx
0x140020e7a  inc     ecx
0x140020e7c  mov     rax, [r14]
0x140020e7f  mov     [rax+20h], ecx
0x140020e82  mov     rax, [r14]
0x140020e85  mov     [rax+28h], r13
0x140020e89  mov     rax, [r14]
0x140020e8c  mov     [rax+30h], r13
0x140020e90  mov     rax, [r14]
0x140020e93  mov     [rax+3Ch], r13d
0x140020e97  mov     rax, [r14]
0x140020e9a  mov     [rax+38h], r13d
0x140020e9e  mov     rax, [r14]
0x140020ea1  mov     [rax+48h], r13
0x140020ea5  mov     rax, [r14]
0x140020ea8  mov     [rax+50h], r13
0x140020eac  mov     rax, [r14]
0x140020eaf  mov     [rax+58h], r13
0x140020eb3  mov     rax, [r14]
0x140020eb6  mov     [rax+24h], r13d
0x140020eba  mov     rax, [r14]
0x140020ebd  mov     [rax+68h], r13
0x140020ec1  mov     rax, [r14]
0x140020ec4  mov     [rax+78h], rax
0x140020ec8  mov     rcx, [r14]
0x140020ecb  mov     rax, [rcx+80h]
0x140020ed2  mov     [rcx+70h], rax
0x140020ed6  cmp     r12d, 8
0x140020eda  jnz     loc_1400212C3
0x140020ee0  mov     rax, [r14]
0x140020ee3  mov     rcx, [rax+70h]
0x140020ee7  mov     [rcx], ebx
0x140020ee9  mov     rax, [r14]
0x140020eec  mov     rcx, [rax+70h]
0x140020ef0  mov     [rcx+4], esi
0x140020ef3  mov     rax, [r14]
0x140020ef6  mov     rcx, [rax+70h]
0x140020efa  mov     [rcx+8], edi
0x140020efd  cmp     ebx, 0FFh
0x140020f03  jz      loc_1400215CB
0x140020f09  cmp     ebx, 0F800h
0x140020f0f  jz      loc_140021475
0x140020f15  cmp     ebx, 7C00h
0x140020f1b  jz      loc_1400213E4
0x140020f21  mov     rax, [r14]
0x140020f24  mov     r8, [rax+70h]
0x140020f28  mov     ecx, r13d
0x140020f2b  test    r9b, bl
0x140020f2e  jnz     short loc_140020F39
0x140020f30  shr     ebx, 1
0x140020f32  inc     ecx
0x140020f34  test    r9b, bl
0x140020f37  jz      short loc_140020F30
0x140020f39  mov     eax, ecx
0x140020f3b  nop     dword ptr [rax+rax+00h]
0x140020f40  shr     ebx, 1
0x140020f42  inc     eax
0x140020f44  test    r9b, bl
0x140020f47  jnz     short loc_140020F40
0x140020f49  mov     edx, eax
0x140020f4b  sub     edx, ecx
0x140020f4d  mov     [r8+24h], edx
0x140020f51  add     eax, 0FFFFFFF8h
0x140020f54  cmp     edx, 8
0x140020f57  cmovbe  eax, ecx
0x140020f5a  mov     [r8+18h], eax
0x140020f5e  mov     r9d, 8
0x140020f64  ja      loc_14002146D
0x140020f6a  mov     eax, r9d
0x140020f6d  sub     eax, edx
0x140020f6f  mov     [r8+0Ch], eax
0x140020f73  mov     rax, [r14]
0x140020f76  mov     r10, [rax+70h]
0x140020f7a  mov     ecx, r13d
0x140020f7d  test    sil, 1
0x140020f81  jnz     short loc_140020F8D
0x140020f83  shr     esi, 1
0x140020f85  inc     ecx
0x140020f87  test    sil, 1
0x140020f8b  jz      short loc_140020F83
0x140020f8d  mov     eax, ecx
0x140020f8f  nop
0x140020f90  shr     esi, 1
0x140020f92  inc     eax
0x140020f94  test    sil, 1
0x140020f98  jnz     short loc_140020F90
0x140020f9a  mov     edx, eax
0x140020f9c  sub     edx, ecx
0x140020f9e  mov     [r10+28h], edx
0x140020fa2  add     eax, 0FFFFFFF8h
0x140020fa5  cmp     edx, 8
0x140020fa8  cmovbe  eax, ecx
0x140020fab  mov     [r10+1Ch], eax
0x140020faf  mov     r8d, 10h
0x140020fb5  ja      short loc_140020FBD
0x140020fb7  mov     r9d, r8d
0x140020fba  sub     r9d, edx
0x140020fbd  mov     [r10+10h], r9d
0x140020fc1  mov     rax, [r14]
0x140020fc4  mov     r9, [rax+70h]
0x140020fc8  mov     ecx, r13d
0x140020fcb  test    dil, 1
0x140020fcf  jnz     short loc_140020FDB
0x140020fd1  shr     edi, 1
0x140020fd3  inc     ecx
0x140020fd5  test    dil, 1
0x140020fd9  jz      short loc_140020FD1
0x140020fdb  mov     eax, ecx
0x140020fdd  nop     dword ptr [rax]
0x140020fe0  shr     edi, 1
0x140020fe2  inc     eax
0x140020fe4  test    dil, 1
0x140020fe8  jnz     short loc_140020FE0
0x140020fea  mov     edx, eax
0x140020fec  sub     edx, ecx
0x140020fee  mov     [r9+2Ch], edx
0x140020ff2  add     eax, 0FFFFFFF8h
0x140020ff5  cmp     edx, 8
0x140020ff8  cmovbe  eax, ecx
0x140020ffb  mov     [r9+20h], eax
0x140020fff  ja      short loc_14002100A
0x140021001  mov     r8d, 18h
0x140021007  sub     r8d, edx
0x14002100a  mov     [r9+14h], r8d
0x14002100e  mov     rsi, [rsp+168h+var_140]
0x140021013  mov     r9d, 1
0x140021019  mov     r8d, 4
0x14002101f  mov     rax, [r14]
0x140021022  cmp     dword ptr [rax+1Ch], 0
0x140021026  jnz     loc_1400212A1
0x14002102c  mov     ecx, [rax+18h]
0x14002102f  test    cl, 2
0x140021032  jnz     loc_140021155
0x140021038  test    cl, 8
0x14002103b  jz      loc_1400215EF
0x140021041  mov     r8d, 6
0x140021047  mov     edi, 3
0x14002104c  mov     ecx, r8d
0x14002104f  mov     [rax+64h], r8d
0x140021053  mov     rax, [r14]
0x140021056  mov     [rax+60h], ecx
0x140021059  test    r9d, r9d
0x14002105c  jz      short loc_1400210D8
0x14002105e  lea     rcx, [rsp+168h+var_108]; this
0x140021063  call    ??0HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::HmgInsertObjectHelper(void)
0x140021068  mov     rax, r13
0x14002106b  cmp     [rsp+168h+var_E8], 0
0x140021074  jnz     short loc_1400210A6
0x140021076  mov     rbx, [r14]
0x140021079  mov     r8d, 0Bh
0x14002107f  cmp     [rsp+168h+arg_40], 0
0x140021087  cmovz   r8d, edi; unsigned int
0x14002108b  mov     r9b, 8; unsigned __int8
0x14002108e  mov     rdx, rbx; struct OBJECT *
0x140021091  mov     rcx, rsi; struct Gre::Base::SESSION_GLOBALS *
0x140021094  call    ?HmgInsertObjectInternal@@YAPEAUHOBJ__@@AEAUSESSION_GLOBALS@Base@Gre@@PEAXKE@Z; HmgInsertObjectInternal(Gre::Base::SESSION_GLOBALS &,void *,ulong,uchar)
0x140021099  test    rax, rax
0x14002109c  jz      short loc_1400210CE
0x14002109e  mov     [rsp+168h+var_E8], rbx
0x1400210a6  test    rax, rax
0x1400210a9  jz      short loc_1400210CE
0x1400210ab  lea     rcx, [rsp+168h+var_108]; this
0x1400210b0  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x1400210b5  mov     eax, 1
0x1400210ba  add     rsp, 130h
0x1400210c1  pop     r15
0x1400210c3  pop     r14
0x1400210c5  pop     r13
0x1400210c7  pop     r12
0x1400210c9  pop     rdi
0x1400210ca  pop     rsi
0x1400210cb  pop     rbx
0x1400210cc  retn
0x1400210ce  lea     rcx, [rsp+168h+var_108]; this
0x1400210d3  call    ??1HmgInsertObjectHelper@@QEAA@XZ; HmgInsertObjectHelper::~HmgInsertObjectHelper(void)
0x1400210d8  mov     rax, [r14]
0x1400210db  mov     rcx, [rax+80h]; Buffer
0x1400210e2  test    rcx, rcx
0x1400210e5  jz      short loc_1400210EC
0x1400210e7  call    GreDeleteFastMutex
0x1400210ec  mov     rbx, [r14]
0x1400210ef  call    cs:__imp_W32GetSessionState
0x1400210f6  nop     dword ptr [rax+rax+00h]
0x1400210fb  mov     rcx, [rax+58h]
0x1400210ff  mov     rax, [rcx+1120h]
0x140021106  mov     rcx, [rax+8]
0x14002110a  test    rcx, rcx
0x14002110d  jz      short loc_14002114B
0x14002110f  xorps   xmm0, xmm0
0x140021112  movups  xmmword ptr [rbx], xmm0
0x140021115  movups  xmmword ptr [rbx+10h], xmm0
0x140021119  movups  xmmword ptr [rbx+20h], xmm0
0x14002111d  movups  xmmword ptr [rbx+30h], xmm0
0x140021121  movups  xmmword ptr [rbx+40h], xmm0
0x140021125  movups  xmmword ptr [rbx+50h], xmm0
0x140021129  movups  xmmword ptr [rbx+60h], xmm0
0x14002112d  movups  xmmword ptr [rbx+70h], xmm0
0x140021131  movups  xmmword ptr [rbx+80h], xmm0
0x140021138  add     rcx, 30h ; '0'; Lookaside
0x14002113c  mov     rdx, rbx; Entry
0x14002113f  call    cs:__imp_ExFreeToLookasideListEx
0x140021146  nop     dword ptr [rax+rax+00h]
0x14002114b  mov     [r14], r13
0x14002114e  xor     eax, eax
0x140021150  jmp     loc_1400210BA
  ... truncated ...
```
