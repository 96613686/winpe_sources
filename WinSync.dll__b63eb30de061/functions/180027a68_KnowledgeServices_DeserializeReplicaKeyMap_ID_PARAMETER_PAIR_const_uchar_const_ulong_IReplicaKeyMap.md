# KnowledgeServices::DeserializeReplicaKeyMap(_ID_PARAMETER_PAIR const &,uchar const *,ulong,IReplicaKeyMap * *)

- ea: `0x180027a68`
- end: `0x180027b6d`
- name: `?DeserializeReplicaKeyMap@KnowledgeServices@@SAJAEBU_ID_PARAMETER_PAIR@@PEBEKPEAPEAUIReplicaKeyMap@@@Z`
- size: `261`
- prototype: `__int64 __fastcall(const struct _ID_PARAMETER_PAIR *, const unsigned __int8 *, int, struct IReplicaKeyMap **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18002d070`

## callees

- `0x1800033bc`
- `0x180005e8c`
- `0x18000724c`
- `0x180007584`
- `0x1800095bc`
- `0x18000a0f0`
- `0x18000c9a0`
- `0x18000ebb0`
- `0x18001df64`
- `0x180027a68`
- `0x180094010`

## string_xrefs

- `0x180027a80`: `KnowledgeServices::DeserializeReplicaKeyMap`
- `0x180027b42`: `KnowledgeServices::DeserializeReplicaKeyMap`

## pseudocode

```c
__int64 __fastcall KnowledgeServices::DeserializeReplicaKeyMap(
        const struct _ID_PARAMETER_PAIR *a1,
        const unsigned __int8 *a2,
        int a3,
        struct IReplicaKeyMap **a4)
{
  unsigned int v8; // edi
  ReplicaKeyMap *v9; // rax
  ReplicaKeyMap *v10; // rbx
  _BYTE v12[8]; // [rsp+20h] [rbp-38h] BYREF
  const unsigned __int8 *v13; // [rsp+28h] [rbp-30h]
  int v14; // [rsp+34h] [rbp-24h]
  int v15; // [rsp+38h] [rbp-20h]
  ReplicaKeyMap *v16; // [rsp+78h] [rbp+20h] BYREF

  TraceKnowledgeFunctionEnter("KnowledgeServices::DeserializeReplicaKeyMap");
  if ( !a4 || (v8 = 0, !a2) )
    v8 = -2147467261;
  StreamAdaptor::StreamAdaptor((StreamAdaptor *)v12);
  if ( !v8 )
  {
    v13 = a2;
    v14 = a3;
    v15 = 0;
  }
  ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>();
  if ( !v8 )
  {
    v9 = (ReplicaKeyMap *)SeAlloc(0xB0u);
    if ( v9 )
      v9 = ReplicaKeyMap::ReplicaKeyMap(v9);
    v8 = ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach((__int64 *)&v16, (__int64)v9);
    if ( !v8 )
    {
      v10 = v16;
      v8 = ReplicaKeyMap::InitializeByDeserializing(v16, (struct StreamAdaptor *)v12);
      if ( !v8 )
      {
        if ( a1->fIsVariable == *((_DWORD *)v10 + 26) && a1->cbIdSize == *((_WORD *)v10 + 54) )
          v8 = (**(__int64 (__fastcall ***)(ReplicaKeyMap *, GUID *, struct IReplicaKeyMap **))v10)(
                 v10,
                 &IID_IReplicaKeyMap,
                 a4);
        else
          v8 = -2147217408;
      }
    }
  }
  TraceKnowledgeFunctionLeaveHR("KnowledgeServices::DeserializeReplicaKeyMap", v8);
  SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>((__int64 *)&v16);
  return v8;
}

```

## disassembly

```asm
0x180027a68  mov     [rsp+arg_0], rbx
0x180027a6d  mov     [rsp+arg_8], rbp
0x180027a72  push    rsi
0x180027a73  push    rdi
0x180027a74  push    r14
0x180027a76  sub     rsp, 40h
0x180027a7a  mov     rsi, rcx
0x180027a7d  mov     r14, r9
0x180027a80  lea     rcx, aKnowledgeservi_8; "KnowledgeServices::DeserializeReplicaKe"...
0x180027a87  mov     ebp, r8d
0x180027a8a  mov     rbx, rdx
0x180027a8d  call    ?TraceKnowledgeFunctionEnter@@YAXPEBD@Z; TraceKnowledgeFunctionEnter(char const *)
0x180027a92  test    r14, r14
0x180027a95  jz      short loc_180027A9E
0x180027a97  xor     edi, edi
0x180027a99  test    rbx, rbx
0x180027a9c  jnz     short loc_180027AA3
0x180027a9e  mov     edi, 80004003h
0x180027aa3  lea     rcx, [rsp+58h+var_38]; this
0x180027aa8  call    ??0StreamAdaptor@@QEAA@XZ; StreamAdaptor::StreamAdaptor(void)
0x180027aad  test    edi, edi
0x180027aaf  jnz     short loc_180027ABE
0x180027ab1  mov     [rsp+58h+var_30], rbx
0x180027ab6  mov     [rsp+58h+var_24], ebp
0x180027aba  mov     [rsp+58h+var_20], edi
0x180027abe  lea     rcx, [rsp+58h+arg_18]
0x180027ac3  call    ??0?$ScopedRefPtr@UIReplicaKeyMap@@@@QEAA@PEAUIReplicaKeyMap@@@Z; ScopedRefPtr<IReplicaKeyMap>::ScopedRefPtr<IReplicaKeyMap>(IReplicaKeyMap *)
0x180027ac8  test    edi, edi
0x180027aca  jnz     short loc_180027B40
0x180027acc  mov     ecx, 0B0h; unsigned __int64
0x180027ad1  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x180027ad6  test    rax, rax
0x180027ad9  jz      short loc_180027AE3
0x180027adb  mov     rcx, rax; this
0x180027ade  call    ??0ReplicaKeyMap@@QEAA@XZ; ReplicaKeyMap::ReplicaKeyMap(void)
0x180027ae3  mov     rdx, rax
0x180027ae6  lea     rcx, [rsp+58h+arg_18]
0x180027aeb  call    ?Attach@?$ScopedPtrBase@VReplicaKeyMap@@V?$ScopedRefPtr@VReplicaKeyMap@@@@@@QEAAJPEAVReplicaKeyMap@@@Z; ScopedPtrBase<ReplicaKeyMap,ScopedRefPtr<ReplicaKeyMap>>::Attach(ReplicaKeyMap *)
0x180027af0  mov     edi, eax
0x180027af2  test    eax, eax
0x180027af4  jnz     short loc_180027B40
0x180027af6  mov     rbx, [rsp+58h+arg_18]
0x180027afb  lea     rdx, [rsp+58h+var_38]; struct StreamAdaptor *
0x180027b00  mov     rcx, rbx; this
0x180027b03  call    ?InitializeByDeserializing@ReplicaKeyMap@@QEAAJAEAVStreamAdaptor@@@Z; ReplicaKeyMap::InitializeByDeserializing(StreamAdaptor &)
0x180027b08  mov     edi, eax
0x180027b0a  test    eax, eax
0x180027b0c  jnz     short loc_180027B40
0x180027b0e  mov     eax, [rbx+68h]
0x180027b11  cmp     [rsi], eax
0x180027b13  jnz     short loc_180027B3B
0x180027b15  movzx   eax, word ptr [rbx+6Ch]
0x180027b19  cmp     [rsi+4], ax
0x180027b1d  jnz     short loc_180027B3B
0x180027b1f  mov     rax, [rbx]
0x180027b22  lea     rdx, IID_IReplicaKeyMap
0x180027b29  mov     r8, r14
0x180027b2c  mov     rcx, rbx
0x180027b2f  mov     rax, [rax]
0x180027b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b37  mov     edi, eax
0x180027b39  jmp     short loc_180027B40
0x180027b3b  mov     edi, 80041000h
0x180027b40  mov     edx, edi; int
0x180027b42  lea     rcx, aKnowledgeservi_8; "KnowledgeServices::DeserializeReplicaKe"...
0x180027b49  call    ?TraceKnowledgeFunctionLeaveHR@@YAXPEBDJ@Z; TraceKnowledgeFunctionLeaveHR(char const *,long)
0x180027b4e  lea     rcx, [rsp+58h+arg_18]
0x180027b53  call    ??1?$SharedRefPtr@UICoreFragmentInspector@@@@QEAA@XZ; SharedRefPtr<ICoreFragmentInspector>::~SharedRefPtr<ICoreFragmentInspector>(void)
0x180027b58  mov     rbx, [rsp+58h+arg_0]
0x180027b5d  mov     eax, edi
0x180027b5f  mov     rbp, [rsp+58h+arg_8]
0x180027b64  add     rsp, 40h
0x180027b68  pop     r14
0x180027b6a  pop     rdi
0x180027b6b  pop     rsi
0x180027b6c  retn
```
