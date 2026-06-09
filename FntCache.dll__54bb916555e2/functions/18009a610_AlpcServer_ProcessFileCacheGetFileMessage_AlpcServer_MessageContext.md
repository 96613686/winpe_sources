# AlpcServer::ProcessFileCacheGetFileMessage(AlpcServer::MessageContext &)

- ea: `0x18009a610`
- end: `0x18009a9df`
- name: `?ProcessFileCacheGetFileMessage@AlpcServer@@AEAAXAEAUMessageContext@1@@Z`
- size: `975`
- prototype: `void __fastcall(AlpcServer *__hidden this, struct AlpcServer::MessageContext *)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c8c8`

## callees

- `0x18000c614`
- `0x18000cd54`
- `0x18000d688`
- `0x180010388`
- `0x180010490`
- `0x1800217ac`
- `0x18004ff84`
- `0x1800974a8`
- `0x18009a610`
- `0x18009e07c`
- `0x1800a1558`
- `0x1800a5328`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800b9a04`
- `0x1800b9e8c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a879`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009a879`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall AlpcServer::ProcessFileCacheGetFileMessage(AlpcServer *this, struct AlpcServer::MessageContext *a2)
{
  __int64 v4; // rsi
  struct IExceptionHandler *v5; // rcx
  CommunicationPortContext *CommunicationPortContext; // r13
  struct IFontCacheClientState *ClientContext; // rax
  struct IFontCacheClientState *v8; // r15
  __int64 **v9; // rax
  __int64 *v10; // rcx
  __int64 *v11; // rcx
  unsigned int v12; // eax
  bool v13; // zf
  __int64 v14; // rax
  __int64 v15; // rbx
  int v16; // eax
  HANDLE v17; // rbx
  __int64 v18; // rax
  HANDLE v19; // rbx
  __int64 v20; // rax
  __int64 *v21; // [rsp+30h] [rbp-D8h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-D0h] BYREF
  struct IExceptionHandler *v23; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v25[4]; // [rsp+50h] [rbp-B8h] BYREF
  struct _PORT_MESSAGE v26; // [rsp+70h] [rbp-98h] BYREF
  int v27; // [rsp+98h] [rbp-70h]
  int v28; // [rsp+A0h] [rbp-68h]
  int v30; // [rsp+A8h] [rbp-60h]
  int v31; // [rsp+ACh] [rbp-5Ch]
  __int64 v32; // [rsp+B0h] [rbp-58h]
  __int64 v33; // [rsp+B8h] [rbp-50h]
  __int64 v34; // [rsp+C0h] [rbp-48h]

  v25[1] = this;
  v25[2] = a2;
  *((_QWORD *)this + 3) = 0x656C6966746567LL;
  EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(this, g_stateTag);
  v4 = CastAlpcMessage<AlpcRequest<16>>(*(_QWORD *)a2, *((_QWORD *)a2 + 1));
  memset_0(&v26, 0, 0x58u);
  try
  {
    v26 = *(struct _PORT_MESSAGE *)v4;
    v26.u1.Length = 5767216;
    v27 = 16;
    v21 = 0;
    v23 = 0;
    (*(void (__fastcall **)(_QWORD, struct IExceptionHandler **))(**((_QWORD **)this + 5) + 56LL))(
      *((_QWORD *)this + 5),
      &v23);
    v5 = v23;
    if ( !v23 )
    {
      v28 = -2003283955;
      goto LABEL_21;
    }
    CommunicationPortContext = AlpcServer::GetCommunicationPortContext(
                                 this,
                                 *((struct _ALPC_MESSAGE_ATTRIBUTES **)a2 + 2),
                                 *(struct _PORT_MESSAGE **)a2);
    ClientContext = CommunicationPortContext::GetClientContext(
                      CommunicationPortContext,
                      *((struct IFontCacheServerInternal **)this + 5));
    v8 = ClientContext;
    if ( *(_BYTE *)(v4 + 48) )
      (*(void (__fastcall **)(struct IFontCacheClientState *))(*(_QWORD *)ClientContext + 24LL))(ClientContext);
    if ( *(_DWORD *)(v4 + 52) )
    {
      v9 = (__int64 **)(*(__int64 (__fastcall **)(struct IFontCacheClientState *, HANDLE *))(*(_QWORD *)v8 + 48LL))(
                         v8,
                         &hObject);
      if ( &v21 != v9 )
      {
        v10 = *v9;
        *v9 = 0;
        v21 = v10;
      }
      ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&hObject);
      v11 = v21;
      if ( !v21 )
      {
        Exception::Exception((Exception *)&hObject, -2147024809, 0);
        EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<ArgumentException>(
          this,
          &hObject,
          1668312161,
          1014);
      }
    }
    else
    {
      v12 = (*(__int64 (__fastcall **)(struct IExceptionHandler *, __int64, __int64, _QWORD, __int64 **))(*(_QWORD *)v23 + 32LL))(
              v23,
              v4 + 60,
              v4 + 76,
              *(unsigned int *)(v4 + 56),
              &v21);
      EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrowIfFailed(
        this,
        v12,
        0x464763706C61LL,
        1019);
      v11 = v21;
    }
    v13 = (*(unsigned int (__fastcall **)(__int64 *))(*v11 + 24))(v11) == 0;
    v14 = *v21;
    if ( v13 )
    {
      v15 = (*(__int64 (**)(void))(v14 + 32))();
      ImpersonateAndOpenClientProcessHandle(&hObject, CommunicationPortContext);
      ServerCacheContext::CloneEventHandle(&v24, v15, hObject);
      v34 = v24;
    }
    else
    {
      if ( !(*(unsigned int (**)(void))(v14 + 40))() )
        goto LABEL_16;
      v30 = (*(__int64 (__fastcall **)(__int64 *))(*v21 + 48))(v21);
      if ( !*(_BYTE *)(v4 + 49) )
        goto LABEL_16;
      ImpersonateAndOpenClientProcessHandle(&hObject, CommunicationPortContext);
      v17 = hObject;
      v18 = (*(__int64 (__fastcall **)(__int64 *))(*v21 + 56))(v21);
      CloneFileMappingHandle(&v24, v18, v17);
      v19 = hObject;
      v20 = (*(__int64 (__fastcall **)(__int64 *))(*v21 + 64))(v21);
      CloneFileMappingHandle(v25, v20, v19);
      if ( !v24 || !v25[0] )
        OSException::ThrowLastError();
      v32 = v24;
      v33 = v25[0];
    }
    if ( hObject )
      CloseHandle(hObject);
LABEL_16:
    v16 = *(_DWORD *)(v4 + 52);
    if ( !v16 )
    {
      if ( !*(_BYTE *)(v4 + 48) )
      {
LABEL_20:
        v5 = v23;
LABEL_21:
        if ( v5 )
          (*(void (__fastcall **)(struct IExceptionHandler *))(*(_QWORD *)v5 + 16LL))(v5);
        goto LABEL_35;
      }
      v16 = (*(__int64 (__fastcall **)(struct IFontCacheClientState *, __int64 *))(*(_QWORD *)v8 + 32LL))(v8, v21);
    }
    v31 = v16;
    goto LABEL_20;
  }
  catch ( ... )
  {
    MapExceptionToHresult(v5);
  }
LABEL_35:
  AlpcServer::SendReply(this, a2, &v26, *((struct _ALPC_MESSAGE_ATTRIBUTES **)a2 + 2));
  if ( v21 )
    (*(void (__fastcall **)(__int64 *))(*v21 + 16))(v21);
}

```

## disassembly

```asm
0x18009a610  mov     [rsp+arg_10], rbx
0x18009a615  push    rsi
0x18009a616  push    r12
0x18009a618  push    r13
0x18009a61a  push    r14
0x18009a61c  push    r15
0x18009a61e  sub     rsp, 0E0h
0x18009a625  mov     rax, cs:__security_cookie
0x18009a62c  xor     rax, rsp
0x18009a62f  mov     [rsp+108h+var_38], rax
0x18009a637  mov     r12, rdx
0x18009a63a  mov     r14, rcx
0x18009a63d  mov     [rsp+108h+var_B0], rcx
0x18009a642  mov     [rsp+108h+var_A8], rdx
0x18009a647  mov     r8, 656C6966746567h
0x18009a651  mov     [rcx+18h], r8
0x18009a655  mov     rdx, cs:?g_stateTag@@3VEventTag@@B; EventTag const g_stateTag
0x18009a65c  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(EventTag,EventTag)
0x18009a661  mov     rdx, [r12+8]
0x18009a666  mov     rcx, [r12]
0x18009a66a  call    ??$CastAlpcMessage@U?$AlpcRequest@$0BA@@@@@YAPEAU?$AlpcRequest@$0BA@@@PEAU_PORT_MESSAGE@@_K@Z; CastAlpcMessage<AlpcRequest<16>>(_PORT_MESSAGE *,unsigned __int64)
0x18009a66f  mov     rsi, rax
0x18009a672  xor     edx, edx; Val
0x18009a674  lea     r8d, [rdx+58h]; Size
0x18009a678  lea     rcx, [rsp+108h+var_98]; void *
0x18009a67d  call    memset_0
0x18009a682  movzx   ecx, word ptr [rsi]
0x18009a685  mov     word ptr [rsp+108h+var_98.u1], cx
0x18009a68a  movzx   ecx, word ptr [rsi+2]
0x18009a68e  mov     word ptr [rsp+108h+var_98.u1+2], cx
0x18009a693  movups  xmm0, xmmword ptr [rsi+4]
0x18009a697  movups  xmmword ptr [rsp+108h+var_98.u2], xmm0
0x18009a69c  movups  xmm1, xmmword ptr [rsi+14h]
0x18009a6a0  movups  xmmword ptr [rsp+108h+var_98.8+0Ch], xmm1
0x18009a6a8  mov     eax, [rsi+24h]
0x18009a6ab  mov     dword ptr [rsp+108h+var_98.20h+4], eax
0x18009a6b2  mov     dword ptr [rsp+108h+var_98.u1], 580030h
0x18009a6ba  mov     rbx, 464763706C61h
0x18009a6c4  mov     [rsp+108h+var_70], 10h
0x18009a6cf  mov     [rsp+108h+var_D8], 0
0x18009a6d8  mov     [rsp+108h+var_C8], 0
0x18009a6e1  mov     rcx, [r14+28h]
0x18009a6e5  mov     rax, [rcx]
0x18009a6e8  lea     rdx, [rsp+108h+var_C8]
0x18009a6ed  mov     rax, [rax+38h]
0x18009a6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6f6  mov     rcx, [rsp+108h+var_C8]
0x18009a6fb  test    rcx, rcx
0x18009a6fe  jnz     short loc_18009A710
0x18009a700  mov     [rsp+108h+var_68], 8898500Dh
0x18009a70b  jmp     loc_18009A8AB
0x18009a710  mov     r8, [r12]; struct _PORT_MESSAGE *
0x18009a714  mov     rdx, [r12+10h]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18009a719  mov     rcx, r14; this
0x18009a71c  call    ?GetCommunicationPortContext@AlpcServer@@AEAAAEAVCommunicationPortContext@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAU_PORT_MESSAGE@@@Z; AlpcServer::GetCommunicationPortContext(_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *)
0x18009a721  mov     r13, rax
0x18009a724  mov     rdx, [r14+28h]; struct IFontCacheServerInternal *
0x18009a728  mov     rcx, rax; this
0x18009a72b  call    ?GetClientContext@CommunicationPortContext@@QEAAAEAUIFontCacheClientState@@PEAUIFontCacheServerInternal@@@Z; CommunicationPortContext::GetClientContext(IFontCacheServerInternal *)
0x18009a730  mov     r15, rax
0x18009a733  cmp     byte ptr [rsi+30h], 0
0x18009a737  jz      short loc_18009A748
0x18009a739  mov     rcx, [rax]
0x18009a73c  mov     rax, [rcx+18h]
0x18009a740  mov     rcx, r15
0x18009a743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a748  mov     r8d, [rsi+34h]
0x18009a74c  test    r8d, r8d
0x18009a74f  jz      loc_18009A7DB
0x18009a755  mov     rax, [r15]
0x18009a758  lea     rdx, [rsp+108h+hObject]
0x18009a75d  mov     rcx, r15
0x18009a760  mov     rax, [rax+30h]
0x18009a764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a769  lea     rcx, [rsp+108h+var_D8]
0x18009a76e  cmp     rcx, rax
0x18009a771  jz      short loc_18009A79C
0x18009a773  mov     rdx, [rsp+108h+var_D8]
0x18009a778  mov     rcx, [rax]
0x18009a77b  mov     qword ptr [rax], 0
0x18009a782  mov     [rsp+108h+var_D8], rcx
0x18009a787  test    rdx, rdx
0x18009a78a  jz      short loc_18009A79C
0x18009a78c  mov     rax, [rdx]
0x18009a78f  mov     rcx, rdx
0x18009a792  mov     rax, [rax+10h]
0x18009a796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a79b  nop
0x18009a79c  lea     rcx, [rsp+108h+hObject]
0x18009a7a1  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18009a7a6  mov     rcx, [rsp+108h+var_D8]
0x18009a7ab  test    rcx, rcx
0x18009a7ae  jnz     short loc_18009A81A
0x18009a7b0  xor     r8d, r8d; unsigned int
0x18009a7b3  mov     edx, 80070057h; int
0x18009a7b8  lea     rcx, [rsp+108h+hObject]; this
0x18009a7bd  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x18009a7c2  mov     r9d, 3F6h
0x18009a7c8  mov     r8d, 63706C61h
0x18009a7ce  lea     rdx, [rsp+108h+hObject]
0x18009a7d3  mov     rcx, r14
0x18009a7d6  call    ??$LogAndThrow@VArgumentException@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXAEBVArgumentException@@VEventTag@@I@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x18009a7db  mov     rcx, [rsp+108h+var_C8]
0x18009a7e0  mov     rax, [rcx]
0x18009a7e3  lea     r8, [rsi+4Ch]
0x18009a7e7  lea     rdx, [rsi+3Ch]
0x18009a7eb  lea     r9, [rsp+108h+var_D8]
0x18009a7f0  mov     [rsp+108h+var_E8], r9
0x18009a7f5  mov     r9d, [rsi+38h]
0x18009a7f9  mov     rax, [rax+20h]
0x18009a7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a802  mov     r9d, 3FBh
0x18009a808  mov     r8, rbx
0x18009a80b  mov     edx, eax
0x18009a80d  mov     rcx, r14
0x18009a810  call    ?LogAndThrowIfFailed@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXJVEventTag@@I@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrowIfFailed(long,EventTag,uint)
0x18009a815  mov     rcx, [rsp+108h+var_D8]
0x18009a81a  mov     rax, [rcx]
0x18009a81d  mov     rax, [rax+18h]
0x18009a821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a826  mov     rcx, [rsp+108h+var_D8]
0x18009a82b  test    eax, eax
0x18009a82d  mov     rax, [rcx]
0x18009a830  jnz     loc_18009A8C2
0x18009a836  mov     rax, [rax+20h]
0x18009a83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a83f  mov     rbx, rax
0x18009a842  mov     rdx, r13
0x18009a845  lea     rcx, [rsp+108h+hObject]
0x18009a84a  call    ?ImpersonateAndOpenClientProcessHandle@@YA?AVWin32Handle@@AEAVCommunicationPortContext@@@Z; ImpersonateAndOpenClientProcessHandle(CommunicationPortContext &)
0x18009a84f  nop
0x18009a850  mov     r8, [rsp+108h+hObject]
0x18009a855  mov     rdx, rbx
0x18009a858  lea     rcx, [rsp+108h+var_C0]
0x18009a85d  call    ?CloneEventHandle@ServerCacheContext@@SA?AV?$ScopedHandle@UEventHandlePolicy@@PEAX@@PEAX0@Z; ServerCacheContext::CloneEventHandle(void *,void *)
0x18009a862  mov     rax, [rsp+108h+var_C0]
0x18009a867  mov     [rsp+108h+var_48], rax
0x18009a86f  mov     rcx, [rsp+108h+hObject]; hObject
0x18009a874  test    rcx, rcx
0x18009a877  jz      short loc_18009A87F
0x18009a879  call    cs:__imp_CloseHandle
0x18009a87f  mov     eax, [rsi+34h]
0x18009a882  test    eax, eax
0x18009a884  jnz     short loc_18009A89F
0x18009a886  cmp     [rsi+30h], al
0x18009a889  jz      short loc_18009A8A6
0x18009a88b  mov     rax, [r15]
0x18009a88e  mov     rdx, [rsp+108h+var_D8]
0x18009a893  mov     rcx, r15
0x18009a896  mov     rax, [rax+20h]
0x18009a89a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a89f  mov     [rsp+108h+var_5C], eax
0x18009a8a6  mov     rcx, [rsp+108h+var_C8]
0x18009a8ab  test    rcx, rcx
0x18009a8ae  jz      short loc_18009A8BD
0x18009a8b0  mov     rax, [rcx]
0x18009a8b3  mov     rax, [rax+10h]
0x18009a8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8bc  nop
0x18009a8bd  jmp     loc_18009A989
0x18009a8c2  mov     rax, [rax+28h]
0x18009a8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8cb  mov     [rsp+108h+var_64], eax
0x18009a8d2  test    eax, eax
0x18009a8d4  jz      short loc_18009A87F
0x18009a8d6  mov     rcx, [rsp+108h+var_D8]
0x18009a8db  mov     rax, [rcx]
0x18009a8de  mov     rax, [rax+30h]
0x18009a8e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a8e7  mov     [rsp+108h+var_60], eax
0x18009a8ee  cmp     byte ptr [rsi+31h], 0
0x18009a8f2  jz      short loc_18009A87F
0x18009a8f4  mov     rdx, r13
0x18009a8f7  lea     rcx, [rsp+108h+hObject]
0x18009a8fc  call    ?ImpersonateAndOpenClientProcessHandle@@YA?AVWin32Handle@@AEAVCommunicationPortContext@@@Z; ImpersonateAndOpenClientProcessHandle(CommunicationPortContext &)
0x18009a901  nop
0x18009a902  mov     rbx, [rsp+108h+hObject]
0x18009a907  mov     rcx, [rsp+108h+var_D8]
0x18009a90c  mov     rax, [rcx]
0x18009a90f  mov     rax, [rax+38h]
0x18009a913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a918  mov     r8, rbx
0x18009a91b  mov     rdx, rax
0x18009a91e  lea     rcx, [rsp+108h+var_C0]
0x18009a923  call    ?CloneFileMappingHandle@@YA?AVWin32Handle@@PEAX0@Z; CloneFileMappingHandle(void *,void *)
0x18009a928  nop
0x18009a929  mov     rbx, [rsp+108h+hObject]
0x18009a92e  mov     rcx, [rsp+108h+var_D8]
0x18009a933  mov     rax, [rcx]
0x18009a936  mov     rax, [rax+40h]
0x18009a93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a93f  mov     r8, rbx
0x18009a942  mov     rdx, rax
0x18009a945  lea     rcx, [rsp+108h+var_B8]
0x18009a94a  call    ?CloneFileMappingHandle@@YA?AVWin32Handle@@PEAX0@Z; CloneFileMappingHandle(void *,void *)
0x18009a94f  nop
0x18009a950  mov     rcx, [rsp+108h+var_C0]
0x18009a955  test    rcx, rcx
0x18009a958  jz      short loc_18009A979
0x18009a95a  mov     rax, [rsp+108h+var_B8]
0x18009a95f  test    rax, rax
0x18009a962  jz      short loc_18009A979
0x18009a964  mov     [rsp+108h+var_58], rcx
0x18009a96c  mov     [rsp+108h+var_50], rax
0x18009a974  jmp     loc_18009A86F
0x18009a979  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x18009a97f  mov     r14, [rsp+108h+var_B0]
0x18009a984  mov     r12, [rsp+108h+var_A8]
0x18009a989  mov     r9, [r12+10h]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x18009a98e  lea     r8, [rsp+108h+var_98]; struct _PORT_MESSAGE *
0x18009a993  mov     rdx, r12; struct AlpcServer::MessageContext *
0x18009a996  mov     rcx, r14; this
0x18009a999  call    ?SendReply@AlpcServer@@AEAAXAEAUMessageContext@1@PEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@@Z; AlpcServer::SendReply(AlpcServer::MessageContext &,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *)
0x18009a99e  nop
0x18009a99f  mov     rcx, [rsp+108h+var_D8]
0x18009a9a4  test    rcx, rcx
0x18009a9a7  jz      short loc_18009A9B6
0x18009a9a9  mov     rax, [rcx]
0x18009a9ac  mov     rax, [rax+10h]
0x18009a9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a9b5  nop
0x18009a9b6  mov     rcx, [rsp+108h+var_38]
0x18009a9be  xor     rcx, rsp; StackCookie
0x18009a9c1  call    __security_check_cookie
0x18009a9c6  mov     rbx, [rsp+108h+arg_10]
0x18009a9ce  add     rsp, 0E0h
0x18009a9d5  pop     r15
0x18009a9d7  pop     r14
0x18009a9d9  pop     r13
0x18009a9db  pop     r12
0x18009a9dd  pop     rsi
0x18009a9de  retn
```
