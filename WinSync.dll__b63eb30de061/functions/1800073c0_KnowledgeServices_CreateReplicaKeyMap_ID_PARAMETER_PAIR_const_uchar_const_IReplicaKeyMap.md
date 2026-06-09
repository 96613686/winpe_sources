# KnowledgeServices::CreateReplicaKeyMap(_ID_PARAMETER_PAIR const &,uchar const *,IReplicaKeyMap * *)

- ea: `0x1800073c0`
- end: `0x18000757b`
- name: `?CreateReplicaKeyMap@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEPEAPEAUIReplicaKeyMap@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(const struct _ID_PARAMETER_PAIR *, const unsigned __int8 *, struct IReplicaKeyMap **)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task`

## callers

- `0x1800072e0`

## callees

- `0x18000724c`
- `0x1800073c0`
- `0x180007584`
- `0x18000759c`
- `0x18000a0f0`
- `0x18000bde0`
- `0x18000ebb0`
- `0x180011bb0`
- `0x180011f60`
- `0x18001ae20`
- `0x180094010`

## string_xrefs

- `0x1800073db`: `KnowledgeServices::CreateReplicaKeyMap`
- `0x18000755d`: `KnowledgeServices::CreateReplicaKeyMap`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateReplicaKeyMap(
        const struct _ID_PARAMETER_PAIR *a1,
        const unsigned __int8 *a2,
        struct IReplicaKeyMap **a3)
{
  USHORT cbIdSize; // cx
  BOOL fIsVariable; // eax
  unsigned int v8; // edi
  int v9; // eax
  ReplicaKeyMap *v10; // rax
  ReplicaKeyMap *v11; // rbx
  _BYTE v13[4]; // [rsp+30h] [rbp-10h] BYREF
  int v14; // [rsp+34h] [rbp-Ch]
  __int64 v15; // [rsp+38h] [rbp-8h]
  BOOL v16; // [rsp+60h] [rbp+20h] BYREF
  USHORT v17; // [rsp+64h] [rbp+24h]
  ReplicaKeyMap *v18; // [rsp+70h] [rbp+30h]

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateReplicaKeyMap");
  cbIdSize = a1->cbIdSize;
  v17 = cbIdSize;
  fIsVariable = a1->fIsVariable;
  v16 = a1->fIsVariable;
  v8 = a3 == 0 ? 0x80004003 : 0;
  if ( a3 )
  {
    v8 = 0;
    if ( fIsVariable )
    {
      if ( cbIdSize <= 2u )
        v8 = -2147217408;
    }
    else
    {
      v9 = 0;
      if ( !cbIdSize )
        v9 = -2147217408;
      v8 = v9;
    }
  }
  if ( !v8 )
    v8 = KnowledgeServices::ValidateIdBytes((const struct IdFormat *)&v16, a2);
  v14 = 0;
  v15 = 0;
  if ( !v8 )
    v8 = SyncId::Initialize((SyncId *)v13, (const struct IdFormat *)&v16, a2);
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( v8 )
  {
    v11 = v18;
  }
  else
  {
    v10 = (ReplicaKeyMap *)SeAlloc(0xB0u);
    if ( v10 )
      v11 = ReplicaKeyMap::ReplicaKeyMap(v10);
    else
      v11 = 0;
    if ( v18 )
      (*(void (__fastcall **)(ReplicaKeyMap *))(*(_QWORD *)v18 + 16LL))(v18);
    v8 = v11 == 0 ? 0x8007000E : 0;
    if ( v11 )
    {
      v8 = ReplicaKeyMap::Initialize(v11, (const struct IdFormat *)&v16, (const struct SyncId *)v13);
      if ( !v8 )
        v8 = (**(__int64 (__fastcall ***)(ReplicaKeyMap *, GUID *, struct IReplicaKeyMap **))v11)(
               v11,
               &IID_IReplicaKeyMap,
               a3);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)WPP_e65626ae806d36e8966776faf765a664_Traceguids,
      (unsigned int)"KnowledgeServices::CreateReplicaKeyMap",
      v8);
  }
  if ( v11 )
    (*(void (__fastcall **)(ReplicaKeyMap *))(*(_QWORD *)v11 + 16LL))(v11);
  SyncId::~SyncId((SyncId *)v13);
  return v8;
}

```

## disassembly

```asm
0x1800073c0  mov     [rsp-18h+arg_8], rbx
0x1800073c5  mov     [rsp-18h+arg_18], rsi
0x1800073ca  push    rbp
0x1800073cb  push    rdi
0x1800073cc  push    r14
0x1800073ce  mov     rbp, rsp
0x1800073d1  sub     rsp, 40h
0x1800073d5  mov     rbx, rcx
0x1800073d8  mov     r14, r8
0x1800073db  lea     rcx, aKnowledgeservi_1; "KnowledgeServices::CreateReplicaKeyMap"
0x1800073e2  mov     rsi, rdx
0x1800073e5  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800073ea  movzx   ecx, word ptr [rbx+4]
0x1800073ee  mov     rax, r14
0x1800073f1  neg     rax
0x1800073f4  mov     [rbp+arg_4], cx
0x1800073f8  mov     eax, [rbx]
0x1800073fa  sbb     edi, edi
0x1800073fc  mov     [rbp+arg_0], eax
0x1800073ff  not     edi
0x180007401  and     edi, 80004003h
0x180007407  test    r14, r14
0x18000740a  jz      short loc_180007427
0x18000740c  xor     edi, edi
0x18000740e  test    eax, eax
0x180007410  jnz     loc_18000753F
0x180007416  mov     eax, edi
0x180007418  xor     edx, edx
0x18000741a  mov     edi, 80041000h
0x18000741f  cmp     dx, cx
0x180007422  cmovz   eax, edi
0x180007425  mov     edi, eax
0x180007427  test    edi, edi
0x180007429  jnz     short loc_180007439
0x18000742b  mov     rdx, rsi; unsigned __int8 *
0x18000742e  lea     rcx, [rbp+arg_0]; struct IdFormat *
0x180007432  call    ?ValidateIdBytes@KnowledgeServices@@SAJAEBUIdFormat@@PEBE@Z; KnowledgeServices::ValidateIdBytes(IdFormat const &,uchar const *)
0x180007437  mov     edi, eax
0x180007439  mov     [rbp+var_C], 0
0x180007440  mov     [rbp+var_8], 0
0x180007448  test    edi, edi
0x18000744a  jnz     short loc_18000745E
0x18000744c  mov     r8, rsi; unsigned __int8 *
0x18000744f  lea     rdx, [rbp+arg_0]; struct IdFormat *
0x180007453  lea     rcx, [rbp+var_10]; this
0x180007457  call    ?Initialize@SyncId@@QEAAJAEBUIdFormat@@PEBE@Z; SyncId::Initialize(IdFormat const &,uchar const *)
0x18000745c  mov     edi, eax
0x18000745e  lea     rcx, [rbp+arg_10]
0x180007462  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180007467  test    edi, edi
0x180007469  jnz     loc_180007532
0x18000746f  mov     ecx, 0B0h; unsigned __int64
0x180007474  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180007479  test    rax, rax
0x18000747c  jz      loc_180007538
0x180007482  mov     rcx, rax; this
0x180007485  call    ??0ReplicaKeyMap@@QEAA@XZ; ReplicaKeyMap::ReplicaKeyMap(void)
0x18000748a  mov     rbx, rax
0x18000748d  mov     rcx, [rbp+arg_10]
0x180007491  test    rcx, rcx
0x180007494  jz      short loc_1800074A2
0x180007496  mov     rax, [rcx]
0x180007499  mov     rax, [rax+10h]
0x18000749d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074a2  mov     rax, rbx
0x1800074a5  neg     rax
0x1800074a8  sbb     edi, edi
0x1800074aa  not     edi
0x1800074ac  and     edi, 8007000Eh
0x1800074b2  test    rbx, rbx
0x1800074b5  jz      short loc_1800074E7
0x1800074b7  lea     r8, [rbp+var_10]; struct SyncId *
0x1800074bb  mov     rcx, rbx; this
0x1800074be  lea     rdx, [rbp+arg_0]; struct IdFormat *
0x1800074c2  call    ?Initialize@ReplicaKeyMap@@QEAAJAEBUIdFormat@@AEBVSyncId@@@Z; ReplicaKeyMap::Initialize(IdFormat const &,SyncId const &)
0x1800074c7  mov     edi, eax
0x1800074c9  test    eax, eax
0x1800074cb  jnz     short loc_1800074E7
0x1800074cd  mov     rax, [rbx]
0x1800074d0  lea     rdx, IID_IReplicaKeyMap
0x1800074d7  mov     r8, r14
0x1800074da  mov     rcx, rbx
0x1800074dd  mov     rax, [rax]
0x1800074e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e5  mov     edi, eax
0x1800074e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074ee  lea     rax, WPP_GLOBAL_Control
0x1800074f5  cmp     rcx, rax
0x1800074f8  jz      short loc_180007500
0x1800074fa  test    byte ptr [rcx+1Ch], 1
0x1800074fe  jnz     short loc_180007553
0x180007500  test    rbx, rbx
0x180007503  jz      short loc_180007514
0x180007505  mov     rax, [rbx]
0x180007508  mov     rcx, rbx
0x18000750b  mov     rax, [rax+10h]
0x18000750f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007514  lea     rcx, [rbp+var_10]; this
0x180007518  call    ??1SyncId@@QEAA@XZ; SyncId::~SyncId(void)
0x18000751d  mov     rbx, [rsp+40h+arg_8]
0x180007522  mov     eax, edi
0x180007524  mov     rsi, [rsp+40h+arg_18]
0x180007529  add     rsp, 40h
0x18000752d  pop     r14
0x18000752f  pop     rdi
0x180007530  pop     rbp
0x180007531  retn
0x180007532  mov     rbx, [rbp+arg_10]
0x180007536  jmp     short loc_1800074E7
0x180007538  xor     ebx, ebx
0x18000753a  jmp     loc_18000748D
0x18000753f  cmp     cx, 2
0x180007543  ja      loc_180007427
0x180007549  mov     edi, 80041000h
0x18000754e  jmp     loc_180007427
0x180007553  cmp     byte ptr [rcx+19h], 5
0x180007557  jb      short loc_180007500
0x180007559  mov     rcx, [rcx+10h]
0x18000755d  lea     r9, aKnowledgeservi_1; "KnowledgeServices::CreateReplicaKeyMap"
0x180007564  mov     edx, 0Bh
0x180007569  mov     [rsp+40h+var_20], edi
0x18000756d  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x180007574  call    WPP_SF_sD
0x180007579  jmp     short loc_180007500
```
