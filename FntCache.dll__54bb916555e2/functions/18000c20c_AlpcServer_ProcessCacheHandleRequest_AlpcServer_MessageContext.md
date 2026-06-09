# AlpcServer::ProcessCacheHandleRequest(AlpcServer::MessageContext &)

- ea: `0x18000c20c`
- end: `0x18000c55c`
- name: `?ProcessCacheHandleRequest@AlpcServer@@AEAAXAEAUMessageContext@1@@Z`
- size: `848`
- prototype: `void __fastcall(AlpcServer *__hidden this, struct AlpcServer::MessageContext *)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c8c8`

## callees

- `0x18000bd98`
- `0x18000c20c`
- `0x18000c614`
- `0x18000cd54`
- `0x18000d268`
- `0x18000d2bc`
- `0x18000d380`
- `0x18000d620`
- `0x18000d688`
- `0x18000d710`
- `0x18000d7ec`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c35a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c35a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall AlpcServer::ProcessCacheHandleRequest(AlpcServer *this, struct AlpcServer::MessageContext *a2)
{
  __int64 v4; // r12
  struct _ALPC_MESSAGE_ATTRIBUTES **v5; // r15
  struct CommunicationPortContext *CommunicationPortContext; // rdi
  const char *v7; // rdx
  const struct AlpcImpersonator *v8; // rdx
  __int64 v9; // r13
  void **v10; // rax
  void *v11; // rdi
  unsigned int *v12; // r12
  struct IExceptionHandler *v13; // rcx
  __int64 *v14; // rax
  __int64 v15; // r8
  int v16; // r9d
  struct CommunicationPortContext *v17; // [rsp+30h] [rbp-108h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-100h] BYREF
  __int128 v19; // [rsp+40h] [rbp-F8h]
  void *v20; // [rsp+50h] [rbp-E8h] BYREF
  void *v21; // [rsp+58h] [rbp-E0h]
  char *v22; // [rsp+60h] [rbp-D8h]
  AlpcServer *v23; // [rsp+68h] [rbp-D0h]
  struct AlpcServer::MessageContext *v24; // [rsp+70h] [rbp-C8h]
  _PORT_MESSAGE v25; // [rsp+80h] [rbp-B8h] BYREF
  int v26; // [rsp+A8h] [rbp-90h]
  __int64 v27; // [rsp+B0h] [rbp-88h]
  HANDLE v28; // [rsp+B8h] [rbp-80h]
  int v29; // [rsp+C0h] [rbp-78h]
  _DWORD v30[2]; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-60h]
  int v32; // [rsp+E0h] [rbp-58h]
  int v33; // [rsp+E4h] [rbp-54h]
  __int64 v34; // [rsp+E8h] [rbp-50h]
  int v35; // [rsp+F0h] [rbp-48h]
  int v36; // [rsp+F4h] [rbp-44h]
  int v37; // [rsp+F8h] [rbp-40h]
  int v38; // [rsp+FCh] [rbp-3Ch]

  v23 = this;
  v24 = a2;
  *((_QWORD *)this + 3) = 0x656C646E616863LL;
  EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(
    (__int64)this,
    g_stateTag,
    0x656C646E616863LL);
  v4 = CastAlpcMessage<AlpcRequest<8>>(*(_QWORD *)a2, *((_QWORD *)a2 + 1));
  memset_0(&v25, 0, 0x48u);
  v25 = *(_PORT_MESSAGE *)v4;
  v25.u1.Length = 4718624;
  v26 = 8;
  v5 = (struct _ALPC_MESSAGE_ATTRIBUTES **)((char *)a2 + 16);
  v22 = (char *)a2 + 16;
  if ( *(_DWORD *)(v4 + 48) == 129 )
  {
    CommunicationPortContext = AlpcServer::GetCommunicationPortContext(this, *v5, *(struct _PORT_MESSAGE **)a2);
    v21 = 0;
    v17 = CommunicationPortContext;
    CommunicationPortContext::ImpersonateClient(CommunicationPortContext, v7);
    if ( !*((_QWORD *)CommunicationPortContext + 6) )
      CommunicationPortContext::InitializeClientContext(
        CommunicationPortContext,
        v8,
        *((struct IFontCacheServerInternal **)this + 5));
    v9 = *((_QWORD *)CommunicationPortContext + 6);
    v10 = (void **)OpenClientProcessHandle(&hObject, (__int64 *)&v17);
    v20 = *v10;
    v11 = v20;
    *v10 = 0;
    v21 = v11;
    if ( hObject )
      CloseHandle(hObject);
    AlpcImpersonator::~AlpcImpersonator((AlpcImpersonator *)&v17);
    try
    {
      v17 = 0;
      hObject = 0;
      v12 = (unsigned int *)(v4 + 52);
      *(_QWORD *)&v19 = v12;
      v29 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, struct CommunicationPortContext **, HANDLE *))(*(_QWORD *)v9 + 88LL))(
              v9,
              v11,
              *v12,
              &v17,
              &hObject);
      v27 = (__int64)v17;
      v13 = (struct IExceptionHandler *)hObject;
      v28 = hObject;
    }
    catch ( ... )
    {
      MapExceptionToHresult(v13);
    }
    v14 = (__int64 *)EventTagFromCacheType(&v20, *v12);
    v19 = 0;
    v30[0] = 0;
    v30[1] = 0;
    v31 = *v14;
    v32 = 0;
    v33 = 0;
    v34 = v15;
    v19 = 0;
    v35 = 1;
    v36 = 0;
    v37 = v16;
    v38 = 0;
    EventLogger::LogGenericEvent(*((_DWORD *)this + 4), 0x72765363706C41LL, 0x656E6F6C63LL, (__int64)v30, 3);
    AlpcServer::SendReply(this, a2, &v25, *v5);
    if ( v11 )
      CloseHandle(v11);
  }
  else
  {
    v29 = -2003283960;
    AlpcServer::SendReply(this, a2, &v25, *v5);
  }
}

```

## disassembly

```asm
0x18000c20c  mov     [rsp+arg_10], rbx
0x18000c211  mov     [rsp+arg_18], rsi
0x18000c216  push    rdi
0x18000c217  push    r12
0x18000c219  push    r13
0x18000c21b  push    r14
0x18000c21d  push    r15
0x18000c21f  sub     rsp, 110h
0x18000c226  mov     rax, cs:__security_cookie
0x18000c22d  xor     rax, rsp
0x18000c230  mov     [rsp+138h+var_38], rax
0x18000c238  mov     r14, rdx
0x18000c23b  mov     rsi, rcx
0x18000c23e  mov     [rsp+138h+var_D0], rcx
0x18000c243  mov     [rsp+138h+var_C8], rdx
0x18000c248  mov     r8, 656C646E616863h
0x18000c252  mov     [rcx+18h], r8
0x18000c256  mov     rdx, cs:?g_stateTag@@3VEventTag@@B; EventTag const g_stateTag
0x18000c25d  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(EventTag,EventTag)
0x18000c262  mov     rdx, [r14+8]
0x18000c266  mov     rcx, [r14]
0x18000c269  call    ??$CastAlpcMessage@U?$AlpcRequest@$07@@@@YAPEAU?$AlpcRequest@$07@@PEAU_PORT_MESSAGE@@_K@Z; CastAlpcMessage<AlpcRequest<8>>(_PORT_MESSAGE *,unsigned __int64)
0x18000c26e  mov     r12, rax
0x18000c271  xor     edx, edx; Val
0x18000c273  lea     r8d, [rdx+48h]; Size
0x18000c277  lea     rcx, [rsp+138h+var_B8]; void *
0x18000c27f  call    memset_0
0x18000c284  movzx   ecx, word ptr [r12]
0x18000c289  mov     word ptr [rsp+138h+var_B8.u1], cx
0x18000c291  movzx   ecx, word ptr [r12+2]
0x18000c297  mov     word ptr [rsp+138h+var_B8.u1+2], cx
0x18000c29f  movups  xmm0, xmmword ptr [r12+4]
0x18000c2a5  movups  xmmword ptr [rsp+138h+var_B8.u2], xmm0
0x18000c2ad  movups  xmm1, xmmword ptr [r12+14h]
0x18000c2b3  movups  xmmword ptr [rsp+138h+var_B8.8+0Ch], xmm1
0x18000c2bb  mov     eax, [r12+24h]
0x18000c2c0  mov     dword ptr [rsp+138h+var_B8.20h+4], eax
0x18000c2c7  mov     dword ptr [rsp+138h+var_B8.u1], 480020h
0x18000c2d2  mov     [rsp+138h+var_90], 8
0x18000c2dd  lea     r15, [r14+10h]
0x18000c2e1  mov     [rsp+138h+var_D8], r15
0x18000c2e6  mov     rcx, rsi; this
0x18000c2e9  cmp     dword ptr [r12+30h], 81h
0x18000c2f2  jnz     loc_18000C503
0x18000c2f8  mov     r8, [r14]; struct _PORT_MESSAGE *
0x18000c2fb  mov     rdx, [r15]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18000c2fe  call    ?GetCommunicationPortContext@AlpcServer@@AEAAAEAVCommunicationPortContext@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAU_PORT_MESSAGE@@@Z; AlpcServer::GetCommunicationPortContext(_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *)
0x18000c303  mov     rdi, rax
0x18000c306  xor     ebx, ebx
0x18000c308  mov     [rsp+138h+var_E0], rbx
0x18000c30d  mov     [rsp+138h+var_108], rax
0x18000c312  mov     rcx, rax; this
0x18000c315  call    ?ImpersonateClient@CommunicationPortContext@@QEAAXXZ; CommunicationPortContext::ImpersonateClient(void)
0x18000c31a  nop
0x18000c31b  cmp     [rdi+30h], rbx
0x18000c31f  jnz     short loc_18000C32D
0x18000c321  mov     r8, [rsi+28h]; struct IFontCacheServerInternal *
0x18000c325  mov     rcx, rdi; this
0x18000c328  call    ?InitializeClientContext@CommunicationPortContext@@AEAAXAEBVAlpcImpersonator@@PEAUIFontCacheServerInternal@@@Z; CommunicationPortContext::InitializeClientContext(AlpcImpersonator const &,IFontCacheServerInternal *)
0x18000c32d  mov     r13, [rdi+30h]
0x18000c331  lea     rdx, [rsp+138h+var_108]
0x18000c336  lea     rcx, [rsp+138h+hObject]
0x18000c33b  call    ?OpenClientProcessHandle@@YA?AVWin32Handle@@AEBVAlpcImpersonator@@@Z; OpenClientProcessHandle(AlpcImpersonator const &)
0x18000c340  mov     rdi, [rax]
0x18000c343  mov     [rsp+138h+var_E8], rdi
0x18000c348  mov     [rax], rbx
0x18000c34b  mov     [rsp+138h+var_E0], rdi
0x18000c350  mov     rcx, [rsp+138h+hObject]; hObject
0x18000c355  test    rcx, rcx
0x18000c358  jz      short loc_18000C361
0x18000c35a  call    cs:__imp_CloseHandle
0x18000c360  nop
0x18000c361  lea     rcx, [rsp+138h+var_108]; this
0x18000c366  call    ??1AlpcImpersonator@@QEAA@XZ; AlpcImpersonator::~AlpcImpersonator(void)
0x18000c36b  nop
0x18000c36c  mov     [rsp+138h+var_108], rbx
0x18000c371  mov     [rsp+138h+hObject], rbx
0x18000c376  add     r12, 34h ; '4'
0x18000c37a  mov     qword ptr [rsp+138h+var_F8], r12
0x18000c37f  mov     rax, [r13+0]
0x18000c383  lea     rcx, [rsp+138h+hObject]
0x18000c388  mov     [rsp+138h+var_118], rcx
0x18000c38d  lea     r9, [rsp+138h+var_108]
0x18000c392  mov     r8d, [r12]
0x18000c396  mov     rdx, rdi
0x18000c399  mov     rcx, r13
0x18000c39c  mov     rax, [rax+58h]
0x18000c3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3a5  mov     r9d, eax
0x18000c3a8  mov     [rsp+138h+var_78], eax
0x18000c3af  mov     rdx, [rsp+138h+var_108]
0x18000c3b4  mov     [rsp+138h+var_88], rdx
0x18000c3bc  mov     rcx, [rsp+138h+hObject]
0x18000c3c1  mov     [rsp+138h+var_80], rcx
0x18000c3c9  test    rdx, rdx
0x18000c3cc  jz      loc_18000C4DE
0x18000c3d2  mov     r8, 6568636163h
0x18000c3dc  mov     edx, [r12]
0x18000c3e0  lea     rcx, [rsp+138h+var_E8]
0x18000c3e5  call    ?EventTagFromCacheType@@YA?AVEventTag@@H@Z; EventTagFromCacheType(int)
0x18000c3ea  mov     r10, 656E6F6C63h
0x18000c3f4  xorps   xmm0, xmm0
0x18000c3f7  movups  [rsp+138h+var_F8], xmm0
0x18000c3fc  mov     [rsp+138h+var_68], ebx
0x18000c403  mov     ecx, dword ptr [rsp+138h+var_F8+4]
0x18000c407  mov     [rsp+138h+var_64], ecx
0x18000c40e  mov     rax, [rax]
0x18000c411  mov     [rsp+138h+var_60], rax
0x18000c419  movups  [rsp+138h+var_F8], xmm0
0x18000c41e  mov     [rsp+138h+var_58], ebx
0x18000c425  mov     eax, dword ptr [rsp+138h+var_F8+4]
0x18000c429  mov     [rsp+138h+var_54], eax
0x18000c430  mov     [rsp+138h+var_50], r8
0x18000c438  movups  [rsp+138h+var_F8], xmm0
0x18000c43d  mov     [rsp+138h+var_48], 1
0x18000c448  mov     eax, dword ptr [rsp+138h+var_F8+4]
0x18000c44c  mov     [rsp+138h+var_44], eax
0x18000c453  mov     [rsp+138h+var_40], r9d
0x18000c45b  mov     eax, dword ptr [rsp+138h+var_F8+0Ch]
0x18000c45f  mov     [rsp+138h+var_3C], eax
0x18000c466  mov     rdx, 72765363706C41h
0x18000c470  mov     [rsp+138h+var_118], 3
0x18000c479  lea     r9, [rsp+138h+var_68]
0x18000c481  mov     r8, r10
0x18000c484  mov     ecx, [rsi+10h]
0x18000c487  call    ?LogGenericEvent@EventLogger@@SAXIVEventTag@@0PEBU__MIDL___MIDL_itf_serverinterface_0000_0000_0002@@_K@Z; EventLogger::LogGenericEvent(uint,EventTag,EventTag,__MIDL___MIDL_itf_serverinterface_0000_0000_0002 const *,unsigned __int64)
0x18000c48c  mov     r9, [r15]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18000c48f  lea     r8, [rsp+138h+var_B8]; struct _PORT_MESSAGE *
0x18000c497  mov     rdx, r14; struct AlpcServer::MessageContext *
0x18000c49a  mov     rcx, rsi; this
0x18000c49d  call    ?SendReply@AlpcServer@@AEAAXAEAUMessageContext@1@PEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@@Z; AlpcServer::SendReply(AlpcServer::MessageContext &,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *)
0x18000c4a2  nop
0x18000c4a3  test    rdi, rdi
0x18000c4a6  jz      short loc_18000C4B1
0x18000c4a8  mov     rcx, rdi; hObject
0x18000c4ab  call    cs:__imp_CloseHandle
0x18000c4b1  mov     rcx, [rsp+138h+var_38]
0x18000c4b9  xor     rcx, rsp; StackCookie
0x18000c4bc  call    __security_check_cookie
0x18000c4c1  lea     r11, [rsp+138h+var_28]
0x18000c4c9  mov     rbx, [r11+40h]
0x18000c4cd  mov     rsi, [r11+48h]
0x18000c4d1  mov     rsp, r11
0x18000c4d4  pop     r15
0x18000c4d6  pop     r14
0x18000c4d8  pop     r13
0x18000c4da  pop     r12
0x18000c4dc  pop     rdi
0x18000c4dd  retn
0x18000c4de  neg     rcx
0x18000c4e1  sbb     r8, r8
0x18000c4e4  mov     rax, 1FEF30400h
0x18000c4ee  and     r8, rax
0x18000c4f1  mov     rax, 726F727265h
0x18000c4fb  add     r8, rax
0x18000c4fe  jmp     loc_18000C3DC
0x18000c503  mov     [rsp+138h+var_78], 88985008h
0x18000c50e  mov     r9, [r15]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18000c511  lea     r8, [rsp+138h+var_B8]; struct _PORT_MESSAGE *
0x18000c519  mov     rdx, r14; struct AlpcServer::MessageContext *
0x18000c51c  call    ?SendReply@AlpcServer@@AEAAXAEAUMessageContext@1@PEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@@Z; AlpcServer::SendReply(AlpcServer::MessageContext &,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *)
0x18000c521  jmp     short loc_18000C4B1
0x18000c523  xor     ebx, ebx
0x18000c525  mov     r9d, [rsp+138h+var_78]
0x18000c52d  mov     rcx, [rsp+138h+var_80]
0x18000c535  mov     rdx, [rsp+138h+var_88]
0x18000c53d  mov     r15, [rsp+138h+var_D8]
0x18000c542  mov     rsi, [rsp+138h+var_D0]
0x18000c547  mov     r14, [rsp+138h+var_C8]
0x18000c54c  mov     r12, qword ptr [rsp+138h+var_F8]
0x18000c551  mov     rdi, [rsp+138h+var_E8]
0x18000c556  jmp     loc_18000C3C9
```
