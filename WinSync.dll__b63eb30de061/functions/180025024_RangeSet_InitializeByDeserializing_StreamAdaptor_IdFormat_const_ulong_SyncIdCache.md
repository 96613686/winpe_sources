# RangeSet::InitializeByDeserializing(StreamAdaptor &,IdFormat const &,ulong,SyncIdCache *)

- ea: `0x180025024`
- end: `0x180025403`
- name: `?InitializeByDeserializing@RangeSet@@QEAAJAEAVStreamAdaptor@@AEBUIdFormat@@KPEAVSyncIdCache@@@Z`
- size: `991`
- prototype: `__int64 __fastcall(RangeSet *this, struct StreamAdaptor *, const struct IdFormat *, unsigned int, struct SyncIdCache *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180027334`

## callees

- `0x180007114`
- `0x180008ab0`
- `0x180009840`
- `0x18000c270`
- `0x180011f60`
- `0x1800137c0`
- `0x18001a038`
- `0x18001a1f0`
- `0x18001ae20`
- `0x180025024`
- `0x180025740`
- `0x180090358`

## pseudocode

```c
__int64 __fastcall RangeSet::InitializeByDeserializing(
        RangeSet *this,
        struct StreamAdaptor *a2,
        const struct IdFormat *a3,
        unsigned int a4,
        struct SyncIdCache *a5)
{
  struct StreamAdaptor *v6; // r12
  RangeSet *v7; // r11
  __int64 v8; // r8
  unsigned __int64 v9; // r9
  __int64 v10; // rcx
  __int64 v11; // r10
  int v12; // edx
  unsigned int v13; // edi
  int v14; // edx
  unsigned int v15; // r14d
  int v16; // ecx
  int v17; // ebx
  unsigned int i; // eax
  __int64 v19; // rdx
  unsigned int v20; // r12d
  unsigned int v22; // [rsp+30h] [rbp-50h]
  int v23; // [rsp+34h] [rbp-4Ch] BYREF
  _BYTE v24[4]; // [rsp+38h] [rbp-48h] BYREF
  int v25; // [rsp+3Ch] [rbp-44h]
  __int64 v26; // [rsp+40h] [rbp-40h]
  _BYTE v27[4]; // [rsp+48h] [rbp-38h] BYREF
  int v28; // [rsp+4Ch] [rbp-34h]
  __int64 v29; // [rsp+50h] [rbp-30h]
  _BYTE v30[4]; // [rsp+58h] [rbp-28h] BYREF
  int v31; // [rsp+5Ch] [rbp-24h]
  __int64 v32; // [rsp+60h] [rbp-20h]
  _BYTE v33[4]; // [rsp+68h] [rbp-18h] BYREF
  int v34; // [rsp+6Ch] [rbp-14h]
  __int64 v35; // [rsp+70h] [rbp-10h]
  unsigned int v36; // [rsp+78h] [rbp-8h]

  v6 = a2;
  v7 = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      "RangeSet::InitializeByDeserializing");
    v7 = this;
  }
  v8 = *((unsigned int *)v6 + 4);
  v9 = *((unsigned int *)v6 + 5);
  if ( v8 + 4 > v9 || (v10 = (unsigned int)(v8 + 4), (unsigned int)v10 < (unsigned int)v8) )
  {
    v13 = -2147217396;
    goto LABEL_21;
  }
  v11 = *((_QWORD *)v6 + 1);
  v12 = *(unsigned __int8 *)(v11 + v8 + 3)
      | ((*(unsigned __int8 *)(v11 + v8 + 2)
        | (((*(unsigned __int8 *)(v11 + v8) << 8) | *(unsigned __int8 *)(v11 + v8 + 1)) << 8)) << 8);
  *((_DWORD *)v6 + 4) = v10;
  if ( v12 != 22 )
  {
    v13 = v12 != 22 ? 0x8004100C : 0;
LABEL_21:
    v15 = 0;
    goto LABEL_22;
  }
  if ( v10 + 4 > v9 || (v14 = v8 + 8, (int)v8 + 8 < (unsigned int)(v8 + 4)) )
  {
    v15 = 0;
    v13 = -2147217396;
    v14 = v8 + 4;
  }
  else
  {
    v15 = *(unsigned __int8 *)(v10 + v11 + 3)
        | ((*(unsigned __int8 *)(v10 + v11 + 2)
          | (((*(unsigned __int8 *)(v10 + v11) << 8) | *(unsigned __int8 *)(v10 + v11 + 1)) << 8)) << 8);
    *((_DWORD *)v6 + 4) = v14;
    v13 = 0;
  }
  if ( !v13 )
  {
    v16 = 3;
    if ( !*(_DWORD *)a3 )
      v16 = *((unsigned __int16 *)a3 + 2);
    if ( v15 && v15 <= ((int)v9 - v14) / (unsigned int)(v16 + 4) )
    {
      *((_DWORD *)v7 + 2) = 0;
      *((_DWORD *)v7 + 4) = v15;
      *((_DWORD *)v7 + 8) = 0;
    }
    else
    {
      v13 = -2147217396;
    }
  }
LABEL_22:
  v31 = 0;
  v32 = 0;
  if ( v13 )
  {
LABEL_35:
    RangeSet::Recycle(this);
  }
  else
  {
    v17 = -1;
    for ( i = 0; ; i = v22 + 1 )
    {
      v22 = i;
      if ( i >= v15 )
        break;
      v25 = 0;
      v26 = 0;
      v13 = SyncId::InitializeByDeserializing((SyncId *)v24, a3, v6);
      if ( v13 )
        goto LABEL_34;
      v19 = *((unsigned int *)v6 + 4);
      if ( v19 + 4 > (unsigned __int64)*((unsigned int *)v6 + 5)
        || (int)v19 + 4 < (unsigned int)v19
        || (v20 = *(unsigned __int8 *)(*((_QWORD *)v6 + 1) + v19 + 3)
                | ((*(unsigned __int8 *)(*((_QWORD *)v6 + 1) + v19 + 2)
                  | (((*(unsigned __int8 *)(*((_QWORD *)v6 + 1) + v19) << 8)
                    | *(unsigned __int8 *)(*((_QWORD *)v6 + 1) + v19 + 1)) << 8)) << 8),
            *((_DWORD *)a2 + 4) = v19 + 4,
            v20 > a4)
        || v17 != -1 && v17 == v20 )
      {
LABEL_33:
        v13 = -2147217396;
LABEL_34:
        SyncId::~SyncId((SyncId *)v24);
        goto LABEL_35;
      }
      if ( v22 )
      {
        if ( (int)SyncId::Compare((const struct SyncId *)v24, (const struct SyncId *)v30) <= 0 )
          goto LABEL_33;
      }
      else if ( !(unsigned int)SyncId::IsZeroId((SyncId *)v24) )
      {
        goto LABEL_33;
      }
      if ( a5 )
      {
        v28 = 0;
        v29 = 0;
        v23 = 1;
        v13 = HashTable<SyncId,int,DefaultHashTableContext>::LookupOrAddItemReturnKey(a5, v24, &v23, v27);
        if ( v13
          || (v34 = v28,
              v35 = v29,
              SyncId::AddRef((SyncId *)v33),
              v36 = v20,
              v13 = RangeSet::RangeVector::Add((RangeSet *)((char *)this + 8), (const struct Range *)v33),
              SyncId::~SyncId((SyncId *)v33),
              v13) )
        {
          SyncId::~SyncId((SyncId *)v27);
          goto LABEL_34;
        }
        SyncId::operator=(v30, v27);
        SyncId::~SyncId((SyncId *)v27);
      }
      else
      {
        v34 = v25;
        v35 = v26;
        SyncId::AddRef((SyncId *)v33);
        v36 = v20;
        v13 = RangeSet::RangeVector::Add((RangeSet *)((char *)this + 8), (const struct Range *)v33);
        SyncId::~SyncId((SyncId *)v33);
        if ( v13 )
          goto LABEL_34;
        SyncId::operator=(v30, v24);
      }
      v17 = v20;
      SyncId::~SyncId((SyncId *)v24);
      v6 = a2;
    }
    if ( (RangeSet *)((char *)this + 40) != a3 )
    {
      *((_DWORD *)this + 10) = *(_DWORD *)a3;
      *((_WORD *)this + 22) = *((_WORD *)a3 + 2);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      (unsigned int)WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids,
      (unsigned int)"RangeSet::InitializeByDeserializing",
      v13);
  }
  SyncId::~SyncId((SyncId *)v30);
  return v13;
}

```

## disassembly

```asm
0x180025024  mov     [rsp-38h+arg_18], r9d
0x180025029  mov     [rsp-38h+arg_8], rdx
0x18002502e  mov     [rsp-38h+arg_0], rcx
0x180025033  push    rbp
0x180025034  push    rbx
0x180025035  push    rdi
0x180025036  push    r12
0x180025038  push    r13
0x18002503a  push    r14
0x18002503c  push    r15
0x18002503e  mov     rbp, rsp
0x180025041  sub     rsp, 80h
0x180025048  mov     r13, r8
0x18002504b  mov     r12, rdx
0x18002504e  mov     r11, rcx
0x180025051  mov     rcx, cs:WPP_GLOBAL_Control
0x180025058  lea     rax, WPP_GLOBAL_Control
0x18002505f  cmp     rcx, rax
0x180025062  jz      short loc_180025090
0x180025064  test    byte ptr [rcx+1Ch], 40h
0x180025068  jz      short loc_180025090
0x18002506a  cmp     byte ptr [rcx+19h], 5
0x18002506e  jb      short loc_180025090
0x180025070  mov     rcx, [rcx+10h]
0x180025074  lea     r9, aRangesetInitia_0; "RangeSet::InitializeByDeserializing"
0x18002507b  mov     edx, 0Ch
0x180025080  lea     r8, WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids
0x180025087  call    WPP_SF_s
0x18002508c  mov     r11, [rbp+arg_0]
0x180025090  mov     r8d, [r12+10h]
0x180025095  mov     r9d, [r12+14h]
0x18002509a  lea     rax, [r8+4]
0x18002509e  cmp     rax, r9
0x1800250a1  ja      loc_180025191
0x1800250a7  lea     ecx, [r8+4]
0x1800250ab  cmp     ecx, r8d
0x1800250ae  jb      loc_180025191
0x1800250b4  mov     r10, [r12+8]
0x1800250b9  mov     r15d, 8004100Ch
0x1800250bf  movzx   eax, byte ptr [r10+r8]
0x1800250c4  movzx   edx, byte ptr [r10+r8+1]
0x1800250ca  shl     eax, 8
0x1800250cd  or      edx, eax
0x1800250cf  movzx   eax, byte ptr [r10+r8+2]
0x1800250d5  shl     edx, 8
0x1800250d8  or      edx, eax
0x1800250da  movzx   eax, byte ptr [r10+r8+3]
0x1800250e0  shl     edx, 8
0x1800250e3  or      edx, eax
0x1800250e5  mov     [r12+10h], ecx
0x1800250ea  mov     eax, 16h
0x1800250ef  cmp     edx, eax
0x1800250f1  jz      short loc_180025101
0x1800250f3  sub     eax, edx
0x1800250f5  neg     eax
0x1800250f7  sbb     edi, edi
0x1800250f9  and     edi, r15d
0x1800250fc  jmp     loc_18002519A
0x180025101  lea     rax, [rcx+4]
0x180025105  cmp     rax, r9
0x180025108  ja      short loc_180025145
0x18002510a  lea     edx, [rcx+4]
0x18002510d  cmp     edx, ecx
0x18002510f  jb      short loc_180025145
0x180025111  movzx   eax, byte ptr [rcx+r10]
0x180025116  movzx   r14d, byte ptr [rcx+r10+1]
0x18002511c  shl     eax, 8
0x18002511f  or      r14d, eax
0x180025122  movzx   eax, byte ptr [rcx+r10+2]
0x180025128  shl     r14d, 8
0x18002512c  or      r14d, eax
0x18002512f  movzx   eax, byte ptr [rcx+r10+3]
0x180025135  shl     r14d, 8
0x180025139  or      r14d, eax
0x18002513c  mov     [r12+10h], edx
0x180025141  xor     edi, edi
0x180025143  jmp     short loc_18002514D
0x180025145  xor     r14d, r14d
0x180025148  mov     edi, r15d
0x18002514b  mov     edx, ecx
0x18002514d  test    edi, edi
0x18002514f  jnz     short loc_18002519D
0x180025151  lea     ecx, [rdi+3]
0x180025154  cmp     [r13+0], edi
0x180025158  jnz     short loc_18002515F
0x18002515a  movzx   ecx, word ptr [r13+4]
0x18002515f  test    r14d, r14d
0x180025162  jz      short loc_18002518C
0x180025164  sub     r9d, edx
0x180025167  add     ecx, 4
0x18002516a  xor     edx, edx
0x18002516c  mov     eax, r9d
0x18002516f  div     ecx
0x180025171  cmp     r14d, eax
0x180025174  ja      short loc_18002518C
0x180025176  mov     dword ptr [r11+8], 0
0x18002517e  mov     [r11+10h], r14d
0x180025182  mov     dword ptr [r11+20h], 0
0x18002518a  jmp     short loc_18002519D
0x18002518c  mov     edi, r15d
0x18002518f  jmp     short loc_18002519D
0x180025191  mov     r15d, 8004100Ch
0x180025197  mov     edi, r15d
0x18002519a  xor     r14d, r14d
0x18002519d  mov     [rbp+var_24], 0
0x1800251a4  mov     [rbp+var_20], 0
0x1800251ac  test    edi, edi
0x1800251ae  jnz     loc_180025269
0x1800251b4  or      ebx, 0FFFFFFFFh
0x1800251b7  xor     eax, eax
0x1800251b9  mov     [rbp+var_50], eax
0x1800251bc  cmp     eax, r14d
0x1800251bf  jnb     loc_1800253DE
0x1800251c5  mov     r8, r12; struct StreamAdaptor *
0x1800251c8  mov     [rbp+var_44], 0
0x1800251cf  mov     rdx, r13; struct IdFormat *
0x1800251d2  mov     [rbp+var_40], 0
0x1800251da  lea     rcx, [rbp+var_48]; this
0x1800251de  call    ?InitializeByDeserializing@SyncId@@QEAAJAEBUIdFormat@@AEAVStreamAdaptor@@@Z; SyncId::InitializeByDeserializing(IdFormat const &,StreamAdaptor &)
0x1800251e3  mov     edi, eax
0x1800251e5  test    eax, eax
0x1800251e7  jnz     short loc_180025260
0x1800251e9  mov     edx, [r12+10h]
0x1800251ee  mov     eax, [r12+14h]
0x1800251f3  lea     rcx, [rdx+4]
0x1800251f7  cmp     rcx, rax
0x1800251fa  ja      short loc_18002525D
0x1800251fc  lea     r8d, [rdx+4]
0x180025200  cmp     r8d, edx
0x180025203  jb      short loc_18002525D
0x180025205  mov     rcx, [r12+8]
0x18002520a  movzx   eax, byte ptr [rcx+rdx]
0x18002520e  movzx   r12d, byte ptr [rcx+rdx+1]
0x180025214  shl     eax, 8
0x180025217  or      r12d, eax
0x18002521a  movzx   eax, byte ptr [rcx+rdx+2]
0x18002521f  shl     r12d, 8
0x180025223  or      r12d, eax
0x180025226  movzx   eax, byte ptr [rcx+rdx+3]
0x18002522b  shl     r12d, 8
0x18002522f  or      r12d, eax
0x180025232  mov     rax, [rbp+arg_8]
0x180025236  mov     [rax+10h], r8d
0x18002523a  cmp     r12d, [rbp+arg_18]
0x18002523e  ja      short loc_18002525D
0x180025240  cmp     ebx, 0FFFFFFFFh
0x180025243  jz      short loc_18002524A
0x180025245  cmp     ebx, r12d
0x180025248  jz      short loc_18002525D
0x18002524a  cmp     [rbp+var_50], 0
0x18002524e  lea     rcx, [rbp+var_48]; struct SyncId *
0x180025252  jnz     short loc_1800252CF
0x180025254  call    ?IsZeroId@SyncId@@QEBAHXZ; SyncId::IsZeroId(void)
0x180025259  test    eax, eax
0x18002525b  jnz     short loc_1800252DC
0x18002525d  mov     edi, r15d
0x180025260  lea     rcx, [rbp+var_48]; this
0x180025264  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x180025269  mov     rcx, [rbp+arg_0]; this
0x18002526d  call    ?Recycle@RangeSet@@QEAAXXZ; RangeSet::Recycle(void)
0x180025272  mov     rcx, cs:WPP_GLOBAL_Control
0x180025279  lea     rax, WPP_GLOBAL_Control
0x180025280  cmp     rcx, rax
0x180025283  jz      short loc_1800252B1
0x180025285  test    byte ptr [rcx+1Ch], 40h
0x180025289  jz      short loc_1800252B1
0x18002528b  cmp     byte ptr [rcx+19h], 5
0x18002528f  jb      short loc_1800252B1
0x180025291  mov     rcx, [rcx+10h]
0x180025295  lea     r9, aRangesetInitia_0; "RangeSet::InitializeByDeserializing"
0x18002529c  mov     edx, 0Dh
0x1800252a1  mov     [rsp+80h+var_60], edi
0x1800252a5  lea     r8, WPP_ff88f7f000e13ecf98ed337d60498caa_Traceguids
0x1800252ac  call    WPP_SF_sD
0x1800252b1  lea     rcx, [rbp+var_28]; this
0x1800252b5  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x1800252ba  mov     eax, edi
0x1800252bc  add     rsp, 80h
0x1800252c3  pop     r15
0x1800252c5  pop     r14
0x1800252c7  pop     r13
0x1800252c9  pop     r12
0x1800252cb  pop     rdi
0x1800252cc  pop     rbx
0x1800252cd  pop     rbp
0x1800252ce  retn
0x1800252cf  lea     rdx, [rbp+var_28]; struct SyncId *
0x1800252d3  call    ?Compare@SyncId@@SAJAEBV1@0@Z; SyncId::Compare(SyncId const &,SyncId const &)
0x1800252d8  test    eax, eax
0x1800252da  jle     short loc_18002525D
0x1800252dc  cmp     [rbp+arg_20], 0
0x1800252e1  jnz     short loc_180025334
0x1800252e3  mov     eax, [rbp+var_44]
0x1800252e6  lea     rcx, [rbp+var_18]; this
0x1800252ea  mov     [rbp+var_14], eax
0x1800252ed  mov     rax, [rbp+var_40]
0x1800252f1  mov     [rbp+var_10], rax
0x1800252f5  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x1800252fa  mov     rcx, [rbp+arg_0]
0x1800252fe  lea     rdx, [rbp+var_18]; struct Range *
0x180025302  add     rcx, 8; this
0x180025306  mov     [rbp+var_8], r12d
0x18002530a  call    ?Add@RangeVector@RangeSet@@QEAAJAEBURange@@@Z; RangeSet::RangeVector::Add(Range const &)
0x18002530f  lea     rcx, [rbp+var_18]; this
0x180025313  mov     edi, eax
0x180025315  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18002531a  test    edi, edi
0x18002531c  jnz     loc_180025260
0x180025322  lea     rdx, [rbp+var_48]
0x180025326  lea     rcx, [rbp+var_28]
0x18002532a  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x18002532f  jmp     loc_1800253B6
0x180025334  mov     rcx, [rbp+arg_20]
0x180025338  lea     r9, [rbp+var_38]
0x18002533c  lea     r8, [rbp+var_4C]
0x180025340  mov     [rbp+var_34], 0
0x180025347  lea     rdx, [rbp+var_48]
0x18002534b  mov     [rbp+var_30], 0
0x180025353  mov     [rbp+var_4C], 1
0x18002535a  call    ?LookupOrAddItemReturnKey@?$HashTable@VSyncId@@HVDefaultHashTableContext@@@@QEAAJAEBVSyncId@@AEBHAEAV2@@Z; HashTable<SyncId,int,DefaultHashTableContext>::LookupOrAddItemReturnKey(SyncId const &,int const &,SyncId &)
0x18002535f  mov     edi, eax
0x180025361  test    eax, eax
0x180025363  jnz     short loc_1800253D0
0x180025365  mov     eax, [rbp+var_34]
0x180025368  lea     rcx, [rbp+var_18]; this
0x18002536c  mov     [rbp+var_14], eax
0x18002536f  mov     rax, [rbp+var_30]
0x180025373  mov     [rbp+var_10], rax
0x180025377  call    ?AddRef@SyncId@@AEAAXXZ; SyncId::AddRef(void)
0x18002537c  mov     rcx, [rbp+arg_0]
0x180025380  lea     rdx, [rbp+var_18]; struct Range *
0x180025384  add     rcx, 8; this
0x180025388  mov     [rbp+var_8], r12d
0x18002538c  call    ?Add@RangeVector@RangeSet@@QEAAJAEBURange@@@Z; RangeSet::RangeVector::Add(Range const &)
0x180025391  lea     rcx, [rbp+var_18]; this
0x180025395  mov     edi, eax
0x180025397  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18002539c  test    edi, edi
0x18002539e  jnz     short loc_1800253D0
0x1800253a0  lea     rdx, [rbp+var_38]
0x1800253a4  lea     rcx, [rbp+var_28]
0x1800253a8  call    ??4SyncId@@QEAAAEAV0@AEBV0@@Z; SyncId::operator=(SyncId const &)
0x1800253ad  lea     rcx, [rbp+var_38]; this
0x1800253b1  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x1800253b6  lea     rcx, [rbp+var_48]; this
0x1800253ba  mov     ebx, r12d
0x1800253bd  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x1800253c2  mov     eax, [rbp+var_50]
0x1800253c5  mov     r12, [rbp+arg_8]
0x1800253c9  inc     eax
0x1800253cb  jmp     loc_1800251B9
0x1800253d0  lea     rcx, [rbp+var_38]; this
0x1800253d4  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x1800253d9  jmp     loc_180025260
0x1800253de  mov     rcx, [rbp+arg_0]
0x1800253e2  add     rcx, 28h ; '('
0x1800253e6  cmp     rcx, r13
0x1800253e9  jz      loc_180025272
0x1800253ef  mov     eax, [r13+0]
0x1800253f3  mov     [rcx], eax
0x1800253f5  movzx   eax, word ptr [r13+4]
0x1800253fa  mov     [rcx+4], ax
0x1800253fe  jmp     loc_180025272
```
