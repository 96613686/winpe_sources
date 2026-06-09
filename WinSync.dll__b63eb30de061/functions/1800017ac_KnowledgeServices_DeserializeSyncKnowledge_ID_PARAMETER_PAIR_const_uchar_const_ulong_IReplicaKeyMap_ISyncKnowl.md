# KnowledgeServices::DeserializeSyncKnowledge(_ID_PARAMETER_PAIR const &,uchar const *,ulong,IReplicaKeyMap *,ISyncKnowledge * *)

- ea: `0x1800017ac`
- end: `0x180001949`
- name: `?DeserializeSyncKnowledge@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEKPEAUIReplicaKeyMap@@PEAPEAUISyncKnowledge@@@Z`
- size: `413`
- prototype: `__int64 __fastcall(const struct _ID_PARAMETER_PAIR *, const unsigned __int8 *, int, struct IReplicaKeyMap *, struct ISyncKnowledge **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x180001010`

## callees

- `0x180001278`
- `0x1800017ac`
- `0x1800033bc`
- `0x1800093e4`
- `0x18000a0f0`
- `0x18000ebb0`
- `0x18001ae20`
- `0x180094010`

## string_xrefs

- `0x1800017c5`: `KnowledgeServices::DeserializeSyncKnowledge`
- `0x18000191e`: `KnowledgeServices::DeserializeSyncKnowledge`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::DeserializeSyncKnowledge(
        const struct _ID_PARAMETER_PAIR *a1,
        const unsigned __int8 *a2,
        int a3,
        struct IReplicaKeyMap *a4,
        struct ISyncKnowledge **a5)
{
  unsigned int v9; // edi
  USHORT cbIdSize; // cx
  BOOL fIsVariable; // eax
  SyncKnowledge *v12; // rax
  SyncKnowledge *v13; // rbx
  int v15; // eax
  _BYTE v16[8]; // [rsp+30h] [rbp-38h] BYREF
  const unsigned __int8 *v17; // [rsp+38h] [rbp-30h]
  int v18; // [rsp+44h] [rbp-24h]
  int v19; // [rsp+48h] [rbp-20h]
  BOOL v20; // [rsp+70h] [rbp+8h] BYREF
  USHORT v21; // [rsp+74h] [rbp+Ch]

  TraceKnowledgeFunctionEnter("KnowledgeServices::DeserializeSyncKnowledge");
  if ( !a2 || (v9 = 0, !a5) )
    v9 = -2147467261;
  cbIdSize = a1->cbIdSize;
  fIsVariable = a1->fIsVariable;
  v21 = cbIdSize;
  v20 = fIsVariable;
  if ( !v9 )
  {
    v9 = 0;
    if ( fIsVariable )
    {
      if ( cbIdSize <= 2u )
        v9 = -2147217408;
    }
    else
    {
      v15 = 0;
      if ( !cbIdSize )
        v15 = -2147217408;
      v9 = v15;
    }
  }
  StreamAdaptor::StreamAdaptor((StreamAdaptor *)v16);
  if ( v9 )
  {
    v13 = 0;
  }
  else
  {
    v17 = a2;
    v18 = a3;
    v19 = 0;
    v12 = (SyncKnowledge *)SeAlloc(0x2F8u);
    if ( v12 )
      v13 = SyncKnowledge::SyncKnowledge(v12);
    else
      v13 = 0;
    v9 = v13 == 0 ? 0x8007000E : 0;
    if ( v13 )
    {
      v9 = SyncKnowledge::InitializeByDeserializing(v13, (const struct IdFormat *)&v20, (struct StreamAdaptor *)v16, a4);
      if ( !v9 )
        v9 = (**(__int64 (__fastcall ***)(SyncKnowledge *, GUID *, struct ISyncKnowledge **))v13)(
               v13,
               &IID_ISyncKnowledge,
               a5);
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
      (unsigned int)"KnowledgeServices::DeserializeSyncKnowledge",
      v9);
  }
  if ( v13 )
    (*(void (__fastcall **)(SyncKnowledge *))(*(_QWORD *)v13 + 16LL))(v13);
  return v9;
}

```

## disassembly

```asm
0x1800017ac  mov     [rsp+arg_8], rbx
0x1800017b1  mov     [rsp+arg_10], rsi
0x1800017b6  push    rdi
0x1800017b7  push    r14
0x1800017b9  push    r15
0x1800017bb  sub     rsp, 50h
0x1800017bf  mov     rbx, rcx
0x1800017c2  mov     r15, r9
0x1800017c5  lea     rcx, aKnowledgeservi_5; "KnowledgeServices::DeserializeSyncKnowl"...
0x1800017cc  mov     r14d, r8d
0x1800017cf  mov     rsi, rdx
0x1800017d2  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x1800017d7  test    rsi, rsi
0x1800017da  jz      loc_18000193F
0x1800017e0  xor     edi, edi
0x1800017e2  cmp     [rsp+68h+arg_20], rdi
0x1800017ea  jz      loc_18000193F
0x1800017f0  movzx   ecx, word ptr [rbx+4]
0x1800017f4  mov     eax, [rbx]
0x1800017f6  mov     [rsp+68h+arg_4], cx
0x1800017fb  mov     [rsp+68h+arg_0], eax
0x1800017ff  test    edi, edi
0x180001801  jz      loc_1800018D0
0x180001807  lea     rcx, [rsp+68h+var_38]; this
0x18000180c  call    ??0StreamAdaptor@@QEAA@XZ; StreamAdaptor::StreamAdaptor(void)
0x180001811  test    edi, edi
0x180001813  jnz     loc_1800018FC
0x180001819  mov     ecx, 2F8h; unsigned __int64
0x18000181e  mov     [rsp+68h+var_30], rsi
0x180001823  mov     [rsp+68h+var_24], r14d
0x180001828  mov     [rsp+68h+var_20], edi
0x18000182c  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180001831  test    rax, rax
0x180001834  jnz     loc_1800018EC
0x18000183a  xor     ebx, ebx
0x18000183c  mov     rax, rbx
0x18000183f  neg     rax
0x180001842  sbb     edi, edi
0x180001844  not     edi
0x180001846  and     edi, 8007000Eh
0x18000184c  test    rbx, rbx
0x18000184f  jz      short loc_18000188B
0x180001851  mov     r9, r15; struct IReplicaKeyMap *
0x180001854  lea     r8, [rsp+68h+var_38]; struct StreamAdaptor *
0x180001859  lea     rdx, [rsp+68h+arg_0]; struct IdFormat *
0x18000185e  mov     rcx, rbx; this
0x180001861  call    ?InitializeByDeserializing@SyncKnowledge@@QEAAJAEBUIdFormat@@AEAVStreamAdaptor@@PEAUIReplicaKeyMap@@@Z; SyncKnowledge::InitializeByDeserializing(IdFormat const &,StreamAdaptor &,IReplicaKeyMap *)
0x180001866  mov     edi, eax
0x180001868  test    eax, eax
0x18000186a  jnz     short loc_18000188B
0x18000186c  mov     rax, [rbx]
0x18000186f  lea     rdx, IID_ISyncKnowledge
0x180001876  mov     r8, [rsp+68h+arg_20]
0x18000187e  mov     rcx, rbx
0x180001881  mov     rax, [rax]
0x180001884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001889  mov     edi, eax
0x18000188b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001892  lea     rax, WPP_GLOBAL_Control
0x180001899  cmp     rcx, rax
0x18000189c  jz      short loc_1800018A4
0x18000189e  test    byte ptr [rcx+1Ch], 1
0x1800018a2  jnz     short loc_180001914
0x1800018a4  test    rbx, rbx
0x1800018a7  jz      short loc_1800018B8
0x1800018a9  mov     rax, [rbx]
0x1800018ac  mov     rcx, rbx
0x1800018af  mov     rax, [rax+10h]
0x1800018b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018b8  lea     r11, [rsp+68h+var_18]
0x1800018bd  mov     eax, edi
0x1800018bf  mov     rbx, [r11+28h]
0x1800018c3  mov     rsi, [r11+30h]
0x1800018c7  mov     rsp, r11
0x1800018ca  pop     r15
0x1800018cc  pop     r14
0x1800018ce  pop     rdi
0x1800018cf  retn
0x1800018d0  xor     edi, edi
0x1800018d2  test    eax, eax
0x1800018d4  jnz     short loc_180001900
0x1800018d6  mov     eax, edi
0x1800018d8  xor     edx, edx
0x1800018da  mov     edi, 80041000h
0x1800018df  cmp     dx, cx
0x1800018e2  cmovz   eax, edi
0x1800018e5  mov     edi, eax
0x1800018e7  jmp     loc_180001807
0x1800018ec  mov     rcx, rax; this
0x1800018ef  call    ??0SyncKnowledge@@QEAA@XZ; SyncKnowledge::SyncKnowledge(void)
0x1800018f4  mov     rbx, rax
0x1800018f7  jmp     loc_18000183C
0x1800018fc  xor     ebx, ebx
0x1800018fe  jmp     short loc_18000188B
0x180001900  cmp     cx, 2
0x180001904  ja      loc_180001807
0x18000190a  mov     edi, 80041000h
0x18000190f  jmp     loc_180001807
0x180001914  cmp     byte ptr [rcx+19h], 5
0x180001918  jb      short loc_1800018A4
0x18000191a  mov     rcx, [rcx+10h]
0x18000191e  lea     r9, aKnowledgeservi_5; "KnowledgeServices::DeserializeSyncKnowl"...
0x180001925  mov     edx, 0Bh
0x18000192a  mov     [rsp+68h+var_48], edi
0x18000192e  lea     r8, WPP_e65626ae806d36e8966776faf765a664_Traceguids
0x180001935  call    WPP_SF_sD
0x18000193a  jmp     loc_1800018A4
0x18000193f  mov     edi, 80004003h
0x180001944  jmp     loc_1800017F0
```
