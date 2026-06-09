# KnowledgeServices::CreateSyncKnowledge(_ID_PARAMETERS const &,unsigned __int64,IReplicaKeyMap *,ISyncKnowledge * *)

- ea: `0x180008df4`
- end: `0x180008fa3`
- name: `?CreateSyncKnowledge@KnowledgeServices@@SAJAEBU_ID_PARAMETERS@@_KPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(const struct _ID_PARAMETERS *, __int64, struct IReplicaKeyMap *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x180006fe0`

## callees

- `0x18000767c`
- `0x180008df4`
- `0x180008fac`
- `0x1800093e4`
- `0x18000a0f0`
- `0x18000ebb0`
- `0x18001ae20`
- `0x180094010`

## string_xrefs

- `0x180008e0c`: `KnowledgeServices::CreateSyncKnowledge`
- `0x180008f7b`: `KnowledgeServices::CreateSyncKnowledge`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::CreateSyncKnowledge(
        const struct _ID_PARAMETERS *a1,
        __int64 a2,
        struct IReplicaKeyMap *a3,
        struct ISyncKnowledge **a4)
{
  int v7; // edx
  unsigned int v8; // esi
  struct IReplicaKeyMap *v9; // rdi
  SyncKnowledge *v10; // rbx
  SyncKnowledge *v11; // rax
  BOOL fIsVariable; // [rsp+30h] [rbp-38h] BYREF
  USHORT cbIdSize; // [rsp+34h] [rbp-34h]
  BOOL v15; // [rsp+38h] [rbp-30h]
  USHORT v16; // [rsp+3Ch] [rbp-2Ch]
  BOOL v17; // [rsp+40h] [rbp-28h]
  USHORT v18; // [rsp+44h] [rbp-24h]

  TraceKnowledgeFunctionEnter("KnowledgeServices::CreateSyncKnowledge");
  if ( !a3 || (v8 = 0, !a4) )
    v8 = -2147467261;
  fIsVariable = a1->replicaId.fIsVariable;
  cbIdSize = a1->replicaId.cbIdSize;
  v15 = a1->itemId.fIsVariable;
  v16 = a1->itemId.cbIdSize;
  v17 = a1->changeUnitId.fIsVariable;
  v18 = a1->changeUnitId.cbIdSize;
  if ( !v8 )
    v8 = IdFormat::Validate((IdFormat *)&fIsVariable, v7);
  v9 = 0;
  if ( !v8 )
  {
    v9 = a3;
    if ( a3 )
      ((void (__fastcall *)(struct IReplicaKeyMap *))a3->lpVtbl->AddRef)(a3);
    v8 = a3 == 0 ? 0x8007000E : 0;
  }
  v10 = 0;
  if ( !v8 )
  {
    v11 = (SyncKnowledge *)SeAlloc(0x2F8u);
    if ( v11 )
      v10 = SyncKnowledge::SyncKnowledge(v11);
    v8 = v10 == 0 ? 0x8007000E : 0;
    if ( v10 )
    {
      v8 = SyncKnowledge::Initialize(v10);
      if ( !v8 )
        v8 = (**(__int64 (__fastcall ***)(SyncKnowledge *, GUID *, struct ISyncKnowledge **))v10)(
               v10,
               &IID_ISyncKnowledge,
               a4);
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
      (unsigned int)"KnowledgeServices::CreateSyncKnowledge",
      v8);
  }
  if ( v10 )
    (*(void (__fastcall **)(SyncKnowledge *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v9 )
    ((void (__fastcall *)(struct IReplicaKeyMap *))v9->lpVtbl->Release)(v9);
  return v8;
}

```

## disassembly

```asm
0x180008df4  mov     [rsp+arg_8], rbx
0x180008df9  mov     [rsp+arg_10], rbp
0x180008dfe  push    rsi
0x180008dff  push    rdi
0x180008e00  push    r14
0x180008e02  sub     rsp, 50h
0x180008e06  mov     rdi, rcx
0x180008e09  mov     rbp, r9
0x180008e0c  lea     rcx, aKnowledgeservi_7; "KnowledgeServices::CreateSyncKnowledge"
0x180008e13  mov     rbx, r8
0x180008e16  mov     r14, rdx
0x180008e19  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x180008e1e  test    rbx, rbx
0x180008e21  jz      loc_180008F99
0x180008e27  xor     esi, esi
0x180008e29  test    rbp, rbp
0x180008e2c  jz      loc_180008F99
0x180008e32  mov     eax, [rdi+4]
0x180008e35  mov     [rsp+68h+var_38], eax
0x180008e39  movzx   eax, word ptr [rdi+8]
0x180008e3d  mov     [rsp+68h+var_34], ax
0x180008e42  mov     eax, [rdi+0Ch]
0x180008e45  mov     [rsp+68h+var_30], eax
0x180008e49  movzx   eax, word ptr [rdi+10h]
0x180008e4d  mov     [rsp+68h+var_2C], ax
0x180008e52  mov     eax, [rdi+14h]
0x180008e55  mov     [rsp+68h+var_28], eax
0x180008e59  movzx   eax, word ptr [rdi+18h]
0x180008e5d  mov     [rsp+68h+var_24], ax
0x180008e62  test    esi, esi
0x180008e64  jnz     short loc_180008E72
0x180008e66  lea     rcx, [rsp+68h+var_38]; this
0x180008e6b  call    ?Validate@IdFormat@@QEBAJH@Z; IdFormat::Validate(int)
0x180008e70  mov     esi, eax
0x180008e72  xor     edi, edi
0x180008e74  mov     [rsp+68h+arg_0], rdi
0x180008e79  test    esi, esi
0x180008e7b  jnz     short loc_180008E9B
0x180008e7d  mov     [rsp+68h+arg_0], rbx
0x180008e82  mov     rdi, rbx
0x180008e85  test    rbx, rbx
0x180008e88  jnz     loc_180008F5D
0x180008e8e  neg     rbx
0x180008e91  sbb     esi, esi
0x180008e93  not     esi
0x180008e95  and     esi, 8007000Eh
0x180008e9b  xor     ebx, ebx
0x180008e9d  test    esi, esi
0x180008e9f  jnz     short loc_180008F05
0x180008ea1  mov     ecx, 2F8h; unsigned __int64
0x180008ea6  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180008eab  test    rax, rax
0x180008eae  jz      short loc_180008EBB
0x180008eb0  mov     rcx, rax; this
0x180008eb3  call    ??0SyncKnowledge@@QEAA@XZ; SyncKnowledge::SyncKnowledge(void)
0x180008eb8  mov     rbx, rax
0x180008ebb  mov     rax, rbx
0x180008ebe  neg     rax
0x180008ec1  sbb     esi, esi
0x180008ec3  not     esi
0x180008ec5  and     esi, 8007000Eh
0x180008ecb  test    rbx, rbx
0x180008ece  jz      short loc_180008F05
0x180008ed0  lea     r9, [rsp+68h+arg_0]
0x180008ed5  mov     r8, r14
0x180008ed8  lea     rdx, [rsp+68h+var_38]
0x180008edd  mov     rcx, rbx; this
0x180008ee0  call    ?Initialize@SyncKnowledge@@QEAAJAEBUIdDescription@@_KAEAV?$SharedRefPtr@UIReplicaKeyMap@@@@@Z; SyncKnowledge::Initialize(IdDescription const &,unsigned __int64,SharedRefPtr<IReplicaKeyMap> &)
0x180008ee5  mov     esi, eax
0x180008ee7  test    eax, eax
0x180008ee9  jnz     short loc_180008F05
0x180008eeb  mov     rax, [rbx]
0x180008eee  lea     rdx, IID_ISyncKnowledge
0x180008ef5  mov     r8, rbp
0x180008ef8  mov     rcx, rbx
0x180008efb  mov     rax, [rax]
0x180008efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f03  mov     esi, eax
0x180008f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f0c  lea     rax, WPP_GLOBAL_Control
0x180008f13  cmp     rcx, rax
0x180008f16  jz      short loc_180008F1E
0x180008f18  test    byte ptr [rcx+1Ch], 1
0x180008f1c  jnz     short loc_180008F71
0x180008f1e  test    rbx, rbx
0x180008f21  jz      short loc_180008F32
0x180008f23  mov     rax, [rbx]
0x180008f26  mov     rcx, rbx
0x180008f29  mov     rax, [rax+10h]
0x180008f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f32  test    rdi, rdi
0x180008f35  jz      short loc_180008F46
0x180008f37  mov     rax, [rdi]
0x180008f3a  mov     rcx, rdi
0x180008f3d  mov     rax, [rax+10h]
0x180008f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f46  lea     r11, [rsp+68h+var_18]
0x180008f4b  mov     eax, esi
0x180008f4d  mov     rbx, [r11+28h]
0x180008f51  mov     rbp, [r11+30h]
0x180008f55  mov     rsp, r11
0x180008f58  pop     r14
0x180008f5a  pop     rdi
0x180008f5b  pop     rsi
0x180008f5c  retn
0x180008f5d  mov     rax, [rbx]
0x180008f60  mov     rcx, rbx
0x180008f63  mov     rax, [rax+8]
0x180008f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f6c  jmp     loc_180008E8E
0x180008f71  cmp     byte ptr [rcx+19h], 5
0x180008f75  jb      short loc_180008F1E
0x180008f77  mov     rcx, [rcx+10h]
0x180008f7b  lea     r9, aKnowledgeservi_7; "KnowledgeServices::CreateSyncKnowledge"
0x180008f82  mov     edx, 0Bh
0x180008f87  mov     [rsp+68h+var_48], esi
0x180008f8b  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x180008f92  call    WPP_SF_sD
0x180008f97  jmp     short loc_180008F1E
0x180008f99  mov     esi, 80004003h
0x180008f9e  jmp     loc_180008E32
```
