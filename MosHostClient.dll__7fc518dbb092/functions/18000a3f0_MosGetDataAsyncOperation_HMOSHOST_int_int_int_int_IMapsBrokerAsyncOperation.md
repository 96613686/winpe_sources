# MosGetDataAsyncOperation(HMOSHOST__ *,int,int,int,int,IMapsBrokerAsyncOperation * *)

- ea: `0x18000a3f0`
- end: `0x18000a655`
- name: `?MosGetDataAsyncOperation@@YAJPEAUHMOSHOST__@@HHHHPEAPEAUIMapsBrokerAsyncOperation@@@Z`
- size: `613`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, int, int, int, int, struct IMapsBrokerAsyncOperation **)`
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
- `0x18000a3f0`
- `0x18000c41c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall MosGetDataAsyncOperation(
        struct HMOSHOST__ *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        struct IMapsBrokerAsyncOperation **a6)
{
  unsigned int v10; // ebx
  __int64 v11; // rdx
  _BYTE *v12; // rdx
  char *v14; // rax
  __int64 v15; // rbx
  signed __int32 v16; // eax
  _QWORD *v17; // rdx
  int v18; // eax
  int v19; // edi
  _BYTE *v20; // rdx
  _BYTE *v21; // rdx
  __int64 v22; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v23; // [rsp+28h] [rbp-D8h] BYREF
  __int64 (__fastcall *v24)(); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  char v26; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v28; // [rsp+88h] [rbp-78h]
  _DWORD v29[4]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v30; // [rsp+A0h] [rbp-60h]
  __int64 v31; // [rsp+B0h] [rbp-50h]
  __int64 v32; // [rsp+B8h] [rbp-48h]
  _QWORD v33[7]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v34; // [rsp+F8h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  v28 = 0;
  v23 = 0;
  v25 = 0;
  if ( !a1 )
  {
    v10 = -2147467261;
    v11 = 417;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)v10,
      v22);
    if ( v28 )
    {
      v12 = v27;
      LOBYTE(v12) = v28 != v27;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v12);
    }
    return v10;
  }
  v24 = CancelGetDataAsyncOperation;
  v14 = (char *)Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(&v22, &v24);
  v15 = 0;
  if ( &v26 != v14 )
  {
    v15 = *(_QWORD *)v14;
    *(_QWORD *)v14 = 0;
  }
  v25 = v15;
  if ( v22 )
  {
    v22 = 0;
    ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release)();
  }
  if ( !v15 )
  {
    v10 = -2147024882;
    v11 = 420;
    goto LABEL_3;
  }
  v29[1] = a2;
  v29[0] = a3;
  v29[2] = a4;
  v29[3] = a5;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  do
    v16 = *(_DWORD *)(v15 + 12);
  while ( v16 != 0x7FFFFFFF && v16 != _InterlockedCompareExchange((volatile signed __int32 *)(v15 + 12), v16 + 1, v16) );
  v33[0] = off_180013170;
  v33[1] = v15;
  v34 = v33;
  std::function<void (long,MOS_GET_DATA_RESULT const &)>::swap(v33, v27);
  if ( v34 )
  {
    v17 = v33;
    LOBYTE(v17) = v34 != v33;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v34 + 32LL))(v34, v17);
  }
  v18 = RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Invoke(qword_18001C840, a1, v27, &v23);
  v19 = v18;
  if ( ((v18 + 2147023174) & 0xFFFFFFFA) == 0 && v18 != -2147023173 )
    MapsBrokerAsyncOperation::OnGetDataAsyncCallback(
      (MapsBrokerAsyncOperation *)v15,
      v18,
      (const struct MOS_GET_DATA_RESULT *)v29);
  if ( v19 >= 0 )
  {
    *(_QWORD *)(v15 + 56) = v23;
    *a6 = (struct IMapsBrokerAsyncOperation *)v15;
    if ( v28 )
    {
      v21 = v27;
      LOBYTE(v21) = v28 != v27;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v21);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B9,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v19,
      v22);
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(v15);
    if ( v28 )
    {
      v20 = v27;
      LOBYTE(v20) = v28 != v27;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v28 + 32LL))(v28, v20);
    }
    return (unsigned int)v19;
  }
}

```

## disassembly

```asm
0x18000a3f0  mov     [rsp-8+arg_8], rbx
0x18000a3f5  mov     [rsp-8+arg_10], rsi
0x18000a3fa  push    rbp
0x18000a3fb  push    rdi
0x18000a3fc  push    r12
0x18000a3fe  push    r14
0x18000a400  push    r15
0x18000a402  lea     rbp, [rsp-10h]
0x18000a407  sub     rsp, 110h
0x18000a40e  mov     rax, cs:__security_cookie
0x18000a415  xor     rax, rsp
0x18000a418  mov     [rbp+30h+var_30], rax
0x18000a41c  mov     edi, r9d
0x18000a41f  mov     esi, r8d
0x18000a422  mov     r14d, edx
0x18000a425  mov     r15, rcx
0x18000a428  mov     r12, [rbp+30h+arg_28]
0x18000a42c  mov     [rbp+30h+var_A8], 0
0x18000a434  mov     [rsp+130h+var_108], 0
0x18000a43d  mov     [rsp+130h+var_F8], 0
0x18000a446  test    rcx, rcx
0x18000a449  jnz     short loc_18000A490
0x18000a44b  mov     ebx, 80004003h
0x18000a450  mov     edx, 1A1h; void *
0x18000a455  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a45c  mov     r9d, ebx; char *
0x18000a45f  mov     rcx, [rbp+38h]; this
0x18000a463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a468  nop
0x18000a469  mov     rcx, [rbp+30h+var_A8]
0x18000a46d  test    rcx, rcx
0x18000a470  jz      short loc_18000A489
0x18000a472  mov     rax, [rcx]
0x18000a475  lea     rdx, [rsp+130h+var_E0]
0x18000a47a  cmp     rcx, rdx
0x18000a47d  setnz   dl
0x18000a480  mov     rax, [rax+20h]
0x18000a484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a489  mov     eax, ebx
0x18000a48b  jmp     loc_18000A62D
0x18000a490  lea     rax, CancelGetDataAsyncOperation
0x18000a497  mov     [rsp+130h+var_100], rax
0x18000a49c  lea     rdx, [rsp+130h+var_100]
0x18000a4a1  lea     rcx, [rsp+130h+var_110]
0x18000a4a6  call    ??$Make@VMapsBrokerAsyncOperation@@P6AJPEAU_RPC_ASYNC_STATE@@@Z@Details@WRL@Microsoft@@YA?AV?$ComPtr@VMapsBrokerAsyncOperation@@@12@$$QEAP6AJPEAU_RPC_ASYNC_STATE@@@Z@Z; Microsoft::WRL::Details::Make<MapsBrokerAsyncOperation,long (*)(_RPC_ASYNC_STATE *)>(long (*&&)(_RPC_ASYNC_STATE *))
0x18000a4ab  xor     ebx, ebx
0x18000a4ad  lea     rcx, [rsp+130h+var_F0]
0x18000a4b2  cmp     rcx, rax
0x18000a4b5  jz      short loc_18000A4C1
0x18000a4b7  mov     rbx, [rax]
0x18000a4ba  mov     qword ptr [rax], 0
0x18000a4c1  mov     [rsp+130h+var_F8], rbx
0x18000a4c6  mov     rcx, [rsp+130h+var_110]
0x18000a4cb  test    rcx, rcx
0x18000a4ce  jz      short loc_18000A4DE
0x18000a4d0  mov     [rsp+130h+var_110], 0
0x18000a4d9  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000a4de  test    rbx, rbx
0x18000a4e1  jnz     short loc_18000A4F2
0x18000a4e3  mov     ebx, 8007000Eh
0x18000a4e8  mov     edx, 1A4h
0x18000a4ed  jmp     loc_18000A455
0x18000a4f2  mov     [rbp+30h+var_9C], r14d
0x18000a4f6  mov     [rbp+30h+var_A0], esi
0x18000a4f9  mov     [rbp+30h+var_98], edi
0x18000a4fc  mov     eax, [rbp+30h+arg_20]
0x18000a4ff  mov     [rbp+30h+var_94], eax
0x18000a502  mov     [rbp+30h+var_80], 0
0x18000a50a  mov     [rbp+30h+var_90], 0
0x18000a512  mov     [rbp+30h+var_78], 0
0x18000a51a  mov     edx, 7FFFFFFFh
0x18000a51f  jmp     short loc_18000A52B
0x18000a521  lea     ecx, [rax+1]
0x18000a524  lock cmpxchg [rbx+0Ch], ecx
0x18000a529  jz      short loc_18000A532
0x18000a52b  mov     eax, [rbx+0Ch]
0x18000a52e  cmp     eax, edx
0x18000a530  jnz     short loc_18000A521
0x18000a532  lea     rax, off_180013170
0x18000a539  mov     [rbp+30h+var_70], rax
0x18000a53d  mov     [rbp+30h+var_68], rbx
0x18000a541  lea     rax, [rbp+30h+var_70]
0x18000a545  mov     [rbp+30h+var_38], rax
0x18000a549  lea     rdx, [rsp+130h+var_E0]
0x18000a54e  lea     rcx, [rbp+30h+var_70]
0x18000a552  call    ?swap@?$function@$$A6AXJAEBUMOS_GET_DATA_RESULT@@@Z@std@@QEAAXAEAV12@@Z; std::function<void (long,MOS_GET_DATA_RESULT const &)>::swap(std::function<void (long,MOS_GET_DATA_RESULT const &)> &)
0x18000a557  mov     rcx, [rbp+30h+var_38]
0x18000a55b  test    rcx, rcx
0x18000a55e  jz      short loc_18000A576
0x18000a560  mov     rax, [rcx]
0x18000a563  lea     rdx, [rbp+30h+var_70]
0x18000a567  cmp     rcx, rdx
0x18000a56a  setnz   dl
0x18000a56d  mov     rax, [rax+20h]
0x18000a571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a576  lea     r9, [rsp+130h+var_108]
0x18000a57b  lea     r8, [rsp+130h+var_E0]
0x18000a580  mov     rdx, r15
0x18000a583  lea     rcx, qword_18001C840
0x18000a58a  call    ?Invoke@?$RpcAsyncHelper@URPC_MOS_GET_DATA_ASYNC@@@@QEAAJPEAXAEBURPC_MOS_GET_DATA_ASYNC@@PEAPEAU_RPC_ASYNC_STATE@@@Z; RpcAsyncHelper<RPC_MOS_GET_DATA_ASYNC>::Invoke(void *,RPC_MOS_GET_DATA_ASYNC const &,_RPC_ASYNC_STATE * *)
0x18000a58f  mov     edi, eax
0x18000a591  lea     ecx, [rax+7FF8F946h]
0x18000a597  test    ecx, 0FFFFFFFAh
0x18000a59d  jnz     short loc_18000A5B4
0x18000a59f  cmp     eax, 800706BBh
0x18000a5a4  jz      short loc_18000A5B4
0x18000a5a6  lea     r8, [rbp+30h+var_A0]; struct MOS_GET_DATA_RESULT *
0x18000a5aa  mov     edx, eax; int
0x18000a5ac  mov     rcx, rbx; this
0x18000a5af  call    ?OnGetDataAsyncCallback@MapsBrokerAsyncOperation@@QEAAXJAEBUMOS_GET_DATA_RESULT@@@Z; MapsBrokerAsyncOperation::OnGetDataAsyncCallback(long,MOS_GET_DATA_RESULT const &)
0x18000a5b4  test    edi, edi
0x18000a5b6  jns     short loc_18000A5FE
0x18000a5b8  mov     rcx, [rbp+38h]; this
0x18000a5bc  mov     r9d, edi; char *
0x18000a5bf  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a5c6  mov     edx, 1B9h; void *
0x18000a5cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5d0  nop
0x18000a5d1  mov     rcx, rbx
0x18000a5d4  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)
0x18000a5d9  nop
0x18000a5da  mov     rcx, [rbp+30h+var_A8]
0x18000a5de  test    rcx, rcx
0x18000a5e1  jz      short loc_18000A5FA
0x18000a5e3  mov     rax, [rcx]
0x18000a5e6  lea     rdx, [rsp+130h+var_E0]
0x18000a5eb  cmp     rcx, rdx
0x18000a5ee  setnz   dl
0x18000a5f1  mov     rax, [rax+20h]
0x18000a5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fa  mov     eax, edi
0x18000a5fc  jmp     short loc_18000A62D
0x18000a5fe  mov     rax, [rsp+130h+var_108]
0x18000a603  mov     [rbx+38h], rax
0x18000a607  mov     [r12], rbx
0x18000a60b  mov     rcx, [rbp+30h+var_A8]
0x18000a60f  test    rcx, rcx
0x18000a612  jz      short loc_18000A62B
0x18000a614  mov     rax, [rcx]
0x18000a617  lea     rdx, [rsp+130h+var_E0]
0x18000a61c  cmp     rcx, rdx
0x18000a61f  setnz   dl
0x18000a622  mov     rax, [rax+20h]
0x18000a626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a62b  xor     eax, eax
0x18000a62d  mov     rcx, [rbp+30h+var_30]
0x18000a631  xor     rcx, rsp; StackCookie
0x18000a634  call    __security_check_cookie
0x18000a639  lea     r11, [rsp+130h+var_20]
0x18000a641  mov     rbx, [r11+38h]
0x18000a645  mov     rsi, [r11+40h]
0x18000a649  mov     rsp, r11
0x18000a64c  pop     r15
0x18000a64e  pop     r14
0x18000a650  pop     r12
0x18000a652  pop     rdi
0x18000a653  pop     rbp
0x18000a654  retn
```
