# CConnectJob::CheckAndRequestPMKIDUpdate(ulong,CBSSEntry * *)

- ea: `0x1400a22d4`
- end: `0x1400a263c`
- name: `?CheckAndRequestPMKIDUpdate@CConnectJob@@AEAA_NKPEAPEAVCBSSEntry@@@Z`
- size: `872`
- prototype: `bool __fastcall(CConnectJob *__hidden this, unsigned int, struct CBSSEntry **)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400a2644`
- `0x1400adae0`

## callees

- `0x14000688c`
- `0x140009420`
- `0x14000c940`
- `0x140017130`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002bd34`
- `0x14002ef48`
- `0x140071720`
- `0x140089258`
- `0x1400a22d4`

## pseudocode

```c
bool __fastcall CConnectJob::CheckAndRequestPMKIDUpdate(CConnectJob *this, unsigned int a2, struct CBSSEntry **a3)
{
  unsigned __int64 v3; // rsi
  struct DOT11_NWF_BSSID_CANDIDATE *v6; // rbx
  struct CPort *PortFromPortId; // rbp
  int v8; // r8d
  const struct _DOT11_SSID *v9; // rdx
  bool v10; // di
  PDEVICE_OBJECT v12; // rcx
  int v13; // r9d
  CPropertyCache *PortPropertyCache; // rax
  unsigned int v15; // r11d
  __int64 v16; // r10
  struct CBSSEntry *v17; // rcx
  __int64 v18; // r9
  struct CBSSEntry *v19; // r8
  __int64 v20; // rdx
  struct CBSSEntry *v21; // rax
  __int64 v22; // [rsp+38h] [rbp-40h]
  unsigned __int8 v23; // [rsp+80h] [rbp+8h] BYREF

  v3 = a2;
  v6 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(*((CAdapter **)this + 67), *((_WORD *)this + 26));
  v9 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      v8,
      291,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4));
    v9 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  }
  if ( (*((_DWORD *)this + 158) & 1) != 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        v8,
        292,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
    }
    goto LABEL_10;
  }
  v23 = 0;
  CPropertyCache::GetPropertyBoolean((struct CPort *)((char *)PortFromPortId + 480), 0x14u, &v23);
  if ( v23 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    v12 = WPP_GLOBAL_Control;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
      goto LABEL_10;
    v13 = 293;
    goto LABEL_22;
  }
  if ( !(_DWORD)v3 || *((_BYTE *)this + 2784) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_14;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qDdd(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v9,
        v8,
        294,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4),
        v3,
        *((unsigned __int8 *)this + 2784));
    }
  }
  else
  {
    PortPropertyCache = COidJobBase::GetPortPropertyCache((struct CPortPropertyCache **)this);
    if ( !CPropertyCache::GetPropertyBooleanOrDefault(PortPropertyCache, 0x30u, 0) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_14;
      v12 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_10;
      v13 = 295;
      goto LABEL_22;
    }
    v6 = (struct DOT11_NWF_BSSID_CANDIDATE *)operator new(saturated_mul(v3, 0x10u));
    if ( !v6 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_14;
      v12 = WPP_GLOBAL_Control;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 5u && !LOWORD(WPP_GLOBAL_Control->DeviceType) )
        goto LABEL_10;
      v13 = 296;
LABEL_22:
      LOBYTE(v9) = 5;
      WPP_RECORDER_SF_qD(
        v12->DeviceExtension,
        (_DWORD)v9,
        v8,
        v13,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        (char)this,
        *((_DWORD *)this + 4));
      goto LABEL_10;
    }
    v15 = 0;
    v16 = 0;
    do
    {
      v17 = a3[v16];
      v18 = 2 * v16;
      *((_DWORD *)v6 + 2 * v18) = *((_DWORD *)v17 + 8);
      *((_WORD *)v6 + 4 * v18 + 2) = *((_WORD *)v17 + 18);
      v19 = a3[v16];
      ++v15;
      v20 = *((_BYTE *)v19 + 44) != 0 ? 6 : 0;
      *(_DWORD *)((char *)v6 + 8 * v18 + 6) = *(_DWORD *)((char *)v19 + v20 + 32);
      *((_WORD *)v6 + 4 * v18 + 5) = *(_WORD *)((char *)v19 + v20 + 36);
      v21 = a3[v16++];
      *((_DWORD *)v6 + 2 * v18 + 3) = *((_DWORD *)v21 + 222);
    }
    while ( v15 < (unsigned int)v3 );
    *((_DWORD *)this + 1391) = CPort::PerformPMKIDRequest(PortFromPortId, v3, v6);
  }
LABEL_10:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v9) = 5;
    LODWORD(v22) = 0;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v9,
      v8,
      297,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      (char)this,
      *((_DWORD *)this + 4),
      v22);
  }
LABEL_14:
  v10 = *((_DWORD *)this + 1391) != 0;
  if ( v6 )
    operator delete(v6);
  return v10;
}

```

## disassembly

```asm
0x1400a22d4  mov     [rsp+arg_8], rbx
0x1400a22d9  mov     [rsp+arg_10], rbp
0x1400a22de  push    rsi
0x1400a22df  push    rdi
0x1400a22e0  push    r13
0x1400a22e2  push    r14
0x1400a22e4  push    r15
0x1400a22e6  sub     rsp, 50h
0x1400a22ea  xor     r15d, r15d
0x1400a22ed  mov     esi, edx
0x1400a22ef  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400a22f3  mov     rdi, rcx
0x1400a22f6  mov     rcx, [rcx+218h]; this
0x1400a22fd  mov     r14, r8
0x1400a2300  mov     ebx, r15d
0x1400a2303  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400a2308  mov     rbp, rax
0x1400a230b  lea     r13, WPP_RECORDER_INITIALIZED
0x1400a2312  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a2319  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a2320  jz      short loc_1400A235F
0x1400a2322  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2329  cmp     byte ptr [rcx+29h], 5
0x1400a232d  jnb     short loc_1400A2336
0x1400a232f  cmp     [rcx+48h], r15w
0x1400a2334  jz      short loc_1400A235F
0x1400a2336  mov     eax, [rdi+10h]
0x1400a2339  mov     r9d, 123h
0x1400a233f  mov     rcx, [rcx+40h]
0x1400a2343  mov     [rsp+78h+var_48], eax
0x1400a2347  mov     [rsp+78h+var_50], rdi
0x1400a234c  mov     [rsp+78h+var_58], rdx
0x1400a2351  mov     dl, 5
0x1400a2353  call    WPP_RECORDER_SF_qD
0x1400a2358  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a235f  mov     eax, [rdi+278h]
0x1400a2365  test    al, 1
0x1400a2367  jz      loc_1400A2430
0x1400a236d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a2374  jz      loc_1400A23FB
0x1400a237a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a2381  cmp     byte ptr [rcx+29h], 5
0x1400a2385  jnb     short loc_1400A238E
0x1400a2387  cmp     [rcx+48h], r15w
0x1400a238c  jz      short loc_1400A23B0
0x1400a238e  mov     eax, [rdi+10h]
0x1400a2391  mov     r9d, 124h
0x1400a2397  mov     rcx, [rcx+40h]
0x1400a239b  mov     [rsp+78h+var_48], eax
0x1400a239f  mov     [rsp+78h+var_50], rdi
0x1400a23a4  mov     [rsp+78h+var_58], rdx
0x1400a23a9  mov     dl, 5
0x1400a23ab  call    WPP_RECORDER_SF_qD
0x1400a23b0  lea     rsi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a23b7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a23be  jz      short loc_1400A23FB
0x1400a23c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a23c7  cmp     byte ptr [rcx+29h], 5
0x1400a23cb  jnb     short loc_1400A23D4
0x1400a23cd  cmp     [rcx+48h], r15w
0x1400a23d2  jz      short loc_1400A23FB
0x1400a23d4  mov     eax, [rdi+10h]
0x1400a23d7  mov     r9d, 129h
0x1400a23dd  mov     rcx, [rcx+40h]
0x1400a23e1  mov     dl, 5
0x1400a23e3  mov     dword ptr [rsp+78h+var_40], r15d
0x1400a23e8  mov     [rsp+78h+var_48], eax
0x1400a23ec  mov     [rsp+78h+var_50], rdi
0x1400a23f1  mov     [rsp+78h+var_58], rsi
0x1400a23f6  call    WPP_RECORDER_SF_qDD
0x1400a23fb  cmp     [rdi+15BCh], r15d
0x1400a2402  setnz   dil
0x1400a2406  test    rbx, rbx
0x1400a2409  jz      short loc_1400A2413
0x1400a240b  mov     rcx, rbx; void *
0x1400a240e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400a2413  lea     r11, [rsp+78h+var_28]
0x1400a2418  mov     al, dil
0x1400a241b  mov     rbx, [r11+38h]
0x1400a241f  mov     rbp, [r11+40h]
0x1400a2423  mov     rsp, r11
0x1400a2426  pop     r15
0x1400a2428  pop     r14
0x1400a242a  pop     r13
0x1400a242c  pop     rdi
0x1400a242d  pop     rsi
0x1400a242e  retn
0x1400a2430  lea     rcx, [rbp+1E0h]; this
0x1400a2437  mov     [rsp+78h+arg_0], r15b
0x1400a243f  lea     r8, [rsp+78h+arg_0]; unsigned __int8 *
0x1400a2447  mov     edx, 14h; unsigned int
0x1400a244c  call    ?GetPropertyBoolean@CPropertyCache@@QEAAHKPEAE@Z; CPropertyCache::GetPropertyBoolean(ulong,uchar *)
0x1400a2451  cmp     [rsp+78h+arg_0], r15b
0x1400a2459  jz      short loc_1400A24AA
0x1400a245b  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a2462  jz      short loc_1400A23FB
0x1400a2464  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a246b  cmp     byte ptr [rcx+29h], 5
0x1400a246f  jnb     short loc_1400A247C
0x1400a2471  cmp     [rcx+48h], r15w
0x1400a2476  jz      loc_1400A23B0
0x1400a247c  mov     r9d, 125h
0x1400a2482  mov     eax, [rdi+10h]
0x1400a2485  lea     rsi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a248c  mov     rcx, [rcx+40h]
0x1400a2490  mov     dl, 5
0x1400a2492  mov     [rsp+78h+var_48], eax
0x1400a2496  mov     [rsp+78h+var_50], rdi
0x1400a249b  mov     [rsp+78h+var_58], rsi
0x1400a24a0  call    WPP_RECORDER_SF_qD
0x1400a24a5  jmp     loc_1400A23B7
0x1400a24aa  test    esi, esi
0x1400a24ac  jz      loc_1400A25DA
0x1400a24b2  cmp     [rdi+0AE0h], r15b
0x1400a24b9  jnz     loc_1400A25DA
0x1400a24bf  mov     rcx, rdi; this
0x1400a24c2  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400a24c7  xor     r8d, r8d; unsigned __int8
0x1400a24ca  mov     rcx, rax; this
0x1400a24cd  lea     edx, [r8+30h]; unsigned int
0x1400a24d1  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400a24d6  test    al, al
0x1400a24d8  jnz     short loc_1400A250A
0x1400a24da  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a24e1  jz      loc_1400A23FB
0x1400a24e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a24ee  cmp     byte ptr [rcx+29h], 5
0x1400a24f2  jnb     short loc_1400A24FF
0x1400a24f4  cmp     [rcx+48h], r15w
0x1400a24f9  jz      loc_1400A23B0
0x1400a24ff  mov     r9d, 127h
0x1400a2505  jmp     loc_1400A2482
0x1400a250a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1400a2511  mov     eax, 10h
0x1400a2516  mul     rsi
0x1400a2519  cmovb   rax, rcx
0x1400a251d  mov     rcx, rax; unsigned __int64
0x1400a2520  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400a2525  mov     rbx, rax
0x1400a2528  test    rax, rax
0x1400a252b  jz      short loc_1400A25AA
0x1400a252d  mov     r11d, r15d
0x1400a2530  test    esi, esi
0x1400a2532  jz      short loc_1400A2592
0x1400a2534  mov     r10, r15
0x1400a2537  mov     rcx, [r14+r10*8]
0x1400a253b  mov     r9, r10
0x1400a253e  add     r9, r9
0x1400a2541  mov     eax, [rcx+20h]
0x1400a2544  mov     [rbx+r9*8], eax
0x1400a2548  movzx   eax, word ptr [rcx+24h]
0x1400a254c  mov     [rbx+r9*8+4], ax
0x1400a2552  mov     r8, [r14+r10*8]
0x1400a2556  mov     al, [r8+2Ch]
0x1400a255a  neg     al
0x1400a255c  sbb     rdx, rdx
0x1400a255f  inc     r11d
0x1400a2562  and     edx, 6
0x1400a2565  mov     eax, [rdx+r8+20h]
0x1400a256a  mov     [rbx+r9*8+6], eax
0x1400a256f  movzx   eax, word ptr [rdx+r8+24h]
0x1400a2575  mov     [rbx+r9*8+0Ah], ax
0x1400a257b  mov     rax, [r14+r10*8]
0x1400a257f  inc     r10
0x1400a2582  mov     edx, [rax+378h]
0x1400a2588  mov     [rbx+r9*8+0Ch], edx
0x1400a258d  cmp     r11d, esi
0x1400a2590  jb      short loc_1400A2537
0x1400a2592  mov     r8, rbx; struct DOT11_NWF_BSSID_CANDIDATE *
0x1400a2595  mov     edx, esi; unsigned int
0x1400a2597  mov     rcx, rbp; this
0x1400a259a  call    ?PerformPMKIDRequest@CPort@@QEAAKKPEAUDOT11_NWF_BSSID_CANDIDATE@@@Z; CPort::PerformPMKIDRequest(ulong,DOT11_NWF_BSSID_CANDIDATE *)
0x1400a259f  mov     [rdi+15BCh], eax
0x1400a25a5  jmp     loc_1400A23B0
0x1400a25aa  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a25b1  jz      loc_1400A23FB
0x1400a25b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a25be  cmp     byte ptr [rcx+29h], 5
0x1400a25c2  jnb     short loc_1400A25CF
0x1400a25c4  cmp     [rcx+48h], r15w
0x1400a25c9  jz      loc_1400A23B0
0x1400a25cf  mov     r9d, 128h
0x1400a25d5  jmp     loc_1400A2482
0x1400a25da  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400a25e1  jz      loc_1400A23FB
0x1400a25e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a25ee  cmp     byte ptr [rcx+29h], 5
0x1400a25f2  jnb     short loc_1400A25FF
0x1400a25f4  cmp     [rcx+48h], r15w
0x1400a25f9  jz      loc_1400A23B0
0x1400a25ff  movzx   eax, byte ptr [rdi+0AE0h]
0x1400a2606  mov     r9d, 126h
0x1400a260c  mov     rcx, [rcx+40h]
0x1400a2610  mov     dl, 5
0x1400a2612  mov     [rsp+78h+var_38], eax
0x1400a2616  mov     eax, [rdi+10h]
0x1400a2619  mov     dword ptr [rsp+78h+var_40], esi
0x1400a261d  lea     rsi, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400a2624  mov     [rsp+78h+var_48], eax
0x1400a2628  mov     [rsp+78h+var_50], rdi
0x1400a262d  mov     [rsp+78h+var_58], rsi
0x1400a2632  call    WPP_RECORDER_SF_qDdd
0x1400a2637  jmp     loc_1400A23B7
```
