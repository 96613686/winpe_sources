# MosDeleteDataAsyncOperation(HMOSHOST__ *,int,int,IMapsBrokerAsyncOperation * *)

- ea: `0x180009f30`
- end: `0x18000a188`
- name: `?MosDeleteDataAsyncOperation@@YAJPEAUHMOSHOST__@@HHPEAPEAUIMapsBrokerAsyncOperation@@@Z`
- size: `600`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, int, int, struct IMapsBrokerAsyncOperation **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002550`
- `0x180006214`
- `0x180007c10`
- `0x180007d70`
- `0x180007fc0`
- `0x180009798`
- `0x180009f30`
- `0x18000c41c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall MosDeleteDataAsyncOperation(
        struct HMOSHOST__ *a1,
        int a2,
        int a3,
        struct IMapsBrokerAsyncOperation **a4)
{
  unsigned int v8; // ebx
  __int64 v9; // rdx
  _BYTE *v10; // rdx
  char *v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rcx
  signed __int32 v15; // eax
  _QWORD *v16; // rdx
  int v17; // eax
  int v18; // edi
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  __int64 (__fastcall *v23)(); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h]
  char v25; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v26[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v27; // [rsp+88h] [rbp-78h]
  _DWORD v28[3]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+9Ch] [rbp-64h]
  int v30; // [rsp+A4h] [rbp-5Ch]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  _QWORD v33[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v34; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v27 = 0;
  v22 = 0;
  v24 = 0;
  if ( !a1 )
  {
    v8 = -2147467261;
    v9 = 462;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)v8,
      v21);
    if ( v27 )
    {
      v10 = v26;
      LOBYTE(v10) = v27 != v26;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v27 + 32LL))(v27, v10);
    }
    return v8;
  }
  v23 = CancelDeleteDataAsyncOperation;
  v12 = (char *)Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(&v21, &v23);
  v13 = 0;
  if ( &v25 != v12 )
  {
    v13 = *(_QWORD *)v12;
    *(_QWORD *)v12 = 0;
  }
  v24 = v13;
  v14 = v21;
  if ( v21 )
  {
    v21 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(v14);
  }
  if ( !v13 )
  {
    v8 = -2147024882;
    v9 = 465;
    goto LABEL_3;
  }
  v28[1] = a2;
  v28[0] = a3;
  v28[2] = 0;
  v29 = 1;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  do
    v15 = *(_DWORD *)(v13 + 12);
  while ( v15 != 0x7FFFFFFF && v15 != _InterlockedCompareExchange((volatile signed __int32 *)(v13 + 12), v15 + 1, v15) );
  v33[0] = off_1800131A0;
  v33[1] = v13;
  v34 = v33;
  std::function<void (long,MOS_GET_DATA_RESULT const &)>::swap(v33, v26);
  if ( v34 )
  {
    v16 = v33;
    LOBYTE(v16) = v34 != v33;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v34 + 32LL))(v34, v16);
  }
  v17 = RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Invoke(qword_18001C7C0, a1, v26, &v22);
  v18 = v17;
  if ( ((v17 + 2147023174) & 0xFFFFFFFA) == 0 && v17 != -2147023173 )
    MapsBrokerAsyncOperation::OnGetDataAsyncCallback(
      (MapsBrokerAsyncOperation *)v13,
      v17,
      (const struct MOS_GET_DATA_RESULT *)v28);
  if ( v18 >= 0 )
  {
    *(_QWORD *)(v13 + 56) = v22;
    *a4 = (struct IMapsBrokerAsyncOperation *)v13;
    if ( v27 )
    {
      v20 = v26;
      LOBYTE(v20) = v27 != v26;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v27 + 32LL))(v27, v20);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v18,
      v21);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(v13);
    if ( v27 )
    {
      v19 = v26;
      LOBYTE(v19) = v27 != v26;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v27 + 32LL))(v27, v19);
    }
    return (unsigned int)v18;
  }
}

```

## disassembly

```asm
0x180009f30  mov     [rsp-8+arg_8], rbx
0x180009f35  push    rbp
0x180009f36  push    rsi
0x180009f37  push    rdi
0x180009f38  push    r14
0x180009f3a  push    r15
0x180009f3c  lea     rbp, [rsp-10h]
0x180009f41  sub     rsp, 110h
0x180009f48  mov     rax, cs:__security_cookie
0x180009f4f  xor     rax, rsp
0x180009f52  mov     [rbp+30h+var_30], rax
0x180009f56  mov     r15, r9
0x180009f59  mov     edi, r8d
0x180009f5c  mov     esi, edx
0x180009f5e  mov     r14, rcx
0x180009f61  mov     [rbp+30h+var_A8], 0
0x180009f69  mov     [rsp+130h+var_108], 0
0x180009f72  mov     [rsp+130h+var_F8], 0
0x180009f7b  test    rcx, rcx
0x180009f7e  jnz     short loc_180009FC5
0x180009f80  mov     ebx, 80004003h
0x180009f85  mov     edx, 1CEh; void *
0x180009f8a  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009f91  mov     r9d, ebx; char *
0x180009f94  mov     rcx, [rbp+38h]; this
0x180009f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f9d  nop
0x180009f9e  mov     rcx, [rbp+30h+var_A8]
0x180009fa2  test    rcx, rcx
0x180009fa5  jz      short loc_180009FBE
0x180009fa7  mov     rax, [rcx]
0x180009faa  lea     rdx, [rsp+130h+var_E0]
0x180009faf  cmp     rcx, rdx
0x180009fb2  setnz   dl
0x180009fb5  mov     rax, [rax+20h]
0x180009fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fbe  mov     eax, ebx
0x180009fc0  jmp     loc_18000A165
0x180009fc5  lea     rax, CancelDeleteDataAsyncOperation
0x180009fcc  mov     [rsp+130h+var_100], rax
0x180009fd1  lea     rdx, [rsp+130h+var_100]
0x180009fd6  lea     rcx, [rsp+130h+var_110]
0x180009fdb  call    ??$Make@VMapsBrokerAsyncOperation@@P6AJPEAU_RPC_ASYNC_STATE@@@Z@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMapsBrokerAsyncOperation@@@12@$$QEAP6AJPEAU_RPC_ASYNC_STATE@@@Z@Z; Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(long (*&&)(_RPC_ASYNC_STATE *))
0x180009fe0  xor     ebx, ebx
0x180009fe2  lea     rcx, [rsp+130h+var_F0]
0x180009fe7  cmp     rcx, rax
0x180009fea  jz      short loc_180009FF6
0x180009fec  mov     rbx, [rax]
0x180009fef  mov     qword ptr [rax], 0
0x180009ff6  mov     [rsp+130h+var_F8], rbx
0x180009ffb  mov     rcx, [rsp+130h+var_110]
0x18000a000  test    rcx, rcx
0x18000a003  jz      short loc_18000A013
0x18000a005  mov     [rsp+130h+var_110], 0
0x18000a00e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000a013  test    rbx, rbx
0x18000a016  jnz     short loc_18000A027
0x18000a018  mov     ebx, 8007000Eh
0x18000a01d  mov     edx, 1D1h
0x18000a022  jmp     loc_180009F8A
0x18000a027  mov     [rbp+30h+var_9C], esi
0x18000a02a  mov     [rbp+30h+var_A0], edi
0x18000a02d  mov     [rbp+30h+var_98], 0
0x18000a034  mov     [rbp+30h+var_94], 1
0x18000a03c  mov     [rbp+30h+var_80], 0
0x18000a044  mov     [rbp+30h+var_8C], 0
0x18000a04b  mov     [rbp+30h+var_78], 0
0x18000a053  mov     edx, 7FFFFFFFh
0x18000a058  jmp     short loc_18000A064
0x18000a05a  lea     ecx, [rax+1]
0x18000a05d  lock cmpxchg [rbx+0Ch], ecx
0x18000a062  jz      short loc_18000A06B
0x18000a064  mov     eax, [rbx+0Ch]
0x18000a067  cmp     eax, edx
0x18000a069  jnz     short loc_18000A05A
0x18000a06b  lea     rax, off_1800131A0
0x18000a072  mov     [rbp+30h+var_70], rax
0x18000a076  mov     [rbp+30h+var_68], rbx
0x18000a07a  lea     rax, [rbp+30h+var_70]
0x18000a07e  mov     [rbp+30h+var_38], rax
0x18000a082  lea     rdx, [rsp+130h+var_E0]
0x18000a087  lea     rcx, [rbp+30h+var_70]
0x18000a08b  call    ?swap@?$function@$$A6AXJAEBUMOS_GET_DATA_RESULT@@@Z@std@@QEAAXAEAV12@@Z; std::function<void (long,MOS_GET_DATA_RESULT const &)>::swap(std::function<void (long,MOS_GET_DATA_RESULT const &)> &)
0x18000a090  mov     rcx, [rbp+30h+var_38]
0x18000a094  test    rcx, rcx
0x18000a097  jz      short loc_18000A0AF
0x18000a099  mov     rax, [rcx]
0x18000a09c  lea     rdx, [rbp+30h+var_70]
0x18000a0a0  cmp     rcx, rdx
0x18000a0a3  setnz   dl
0x18000a0a6  mov     rax, [rax+20h]
0x18000a0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0af  lea     r9, [rsp+130h+var_108]
0x18000a0b4  lea     r8, [rsp+130h+var_E0]
0x18000a0b9  mov     rdx, r14
0x18000a0bc  lea     rcx, qword_18001C7C0
0x18000a0c3  call    ?Invoke@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@QEAAJPEAXAEBURPC_MOS_GET_DATA_ASYNC@@PEAPEAU_RPC_ASYNC_STATE@@@Z; RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Invoke(void *,RPC_MOS_GET_DATA_ASYNC const &,_RPC_ASYNC_STATE * *)
0x18000a0c8  mov     edi, eax
0x18000a0ca  lea     ecx, [rax+7FF8F946h]
0x18000a0d0  test    ecx, 0FFFFFFFAh
0x18000a0d6  jnz     short loc_18000A0ED
0x18000a0d8  cmp     eax, 800706BBh
0x18000a0dd  jz      short loc_18000A0ED
0x18000a0df  lea     r8, [rbp+30h+var_A0]; struct MOS_GET_DATA_RESULT *
0x18000a0e3  mov     edx, eax; int
0x18000a0e5  mov     rcx, rbx; this
0x18000a0e8  call    ?OnGetDataAsyncCallback@MapsBrokerAsyncOperation@@QEAAXJAEBUMOS_GET_DATA_RESULT@@@Z; MapsBrokerAsyncOperation::OnGetDataAsyncCallback(long,MOS_GET_DATA_RESULT const &)
0x18000a0ed  test    edi, edi
0x18000a0ef  jns     short loc_18000A137
0x18000a0f1  mov     rcx, [rbp+38h]; this
0x18000a0f5  mov     r9d, edi; char *
0x18000a0f8  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a0ff  mov     edx, 1E6h; void *
0x18000a104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a109  nop
0x18000a10a  mov     rcx, rbx
0x18000a10d  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000a112  nop
0x18000a113  mov     rcx, [rbp+30h+var_A8]
0x18000a117  test    rcx, rcx
0x18000a11a  jz      short loc_18000A133
0x18000a11c  mov     rax, [rcx]
0x18000a11f  lea     rdx, [rsp+130h+var_E0]
0x18000a124  cmp     rcx, rdx
0x18000a127  setnz   dl
0x18000a12a  mov     rax, [rax+20h]
0x18000a12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a133  mov     eax, edi
0x18000a135  jmp     short loc_18000A165
0x18000a137  mov     rax, [rsp+130h+var_108]
0x18000a13c  mov     [rbx+38h], rax
0x18000a140  mov     [r15], rbx
0x18000a143  mov     rcx, [rbp+30h+var_A8]
0x18000a147  test    rcx, rcx
0x18000a14a  jz      short loc_18000A163
0x18000a14c  mov     rax, [rcx]
0x18000a14f  lea     rdx, [rsp+130h+var_E0]
0x18000a154  cmp     rcx, rdx
0x18000a157  setnz   dl
0x18000a15a  mov     rax, [rax+20h]
0x18000a15e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a163  xor     eax, eax
0x18000a165  mov     rcx, [rbp+30h+var_30]
0x18000a169  xor     rcx, rsp; StackCookie
0x18000a16c  call    __security_check_cookie
0x18000a171  mov     rbx, [rsp+130h+arg_8]
0x18000a179  add     rsp, 110h
0x18000a180  pop     r15
0x18000a182  pop     r14
0x18000a184  pop     rdi
0x18000a185  pop     rsi
0x18000a186  pop     rbp
0x18000a187  retn
```
