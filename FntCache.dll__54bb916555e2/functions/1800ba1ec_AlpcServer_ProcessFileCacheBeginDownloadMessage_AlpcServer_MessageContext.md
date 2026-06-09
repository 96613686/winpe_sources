# AlpcServer::ProcessFileCacheBeginDownloadMessage(AlpcServer::MessageContext &)

- ea: `0x1800ba1ec`
- end: `0x1800ba4e5`
- name: `?ProcessFileCacheBeginDownloadMessage@AlpcServer@@AEAAXAEAUMessageContext@1@@Z`
- size: `761`
- prototype: `void __fastcall(AlpcServer *__hidden this, struct AlpcServer::MessageContext *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000c8c8`

## callees

- `0x18000c614`
- `0x18000cd54`
- `0x18000d688`
- `0x1800217ac`
- `0x18004ff84`
- `0x18009372c`
- `0x1800974a8`
- `0x1800a1558`
- `0x1800a5328`
- `0x1800aa650`
- `0x1800ab180`
- `0x1800b9928`
- `0x1800b9a04`
- `0x1800b9e8c`
- `0x1800ba1ec`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ba3ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ba3ec`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800ba433`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800ba433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba474`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ba474`

## pseudocode

```c
void __fastcall AlpcServer::ProcessFileCacheBeginDownloadMessage(
        AlpcServer *this,
        struct AlpcServer::MessageContext *a2)
{
  __int64 v4; // r12
  CommunicationPortContext *CommunicationPortContext; // rax
  CommunicationPortContext *v6; // r13
  struct IFontCacheClientState *ClientContext; // rsi
  unsigned int v8; // eax
  HANDLE CurrentProcess; // rbx
  HANDLE v10; // r12
  void *v11; // rax
  struct IExceptionHandler *v12; // rcx
  HANDLE TargetHandle; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+50h] [rbp-A8h] BYREF
  HANDLE hTargetProcessHandle; // [rsp+58h] [rbp-A0h] BYREF
  _QWORD v17[4]; // [rsp+60h] [rbp-98h] BYREF
  struct _PORT_MESSAGE v18; // [rsp+80h] [rbp-78h] BYREF
  int v19; // [rsp+A8h] [rbp-50h]
  HANDLE v20; // [rsp+B0h] [rbp-48h]
  int v21; // [rsp+B8h] [rbp-40h]

  v17[2] = this;
  v17[1] = a2;
  *((_QWORD *)this + 3) = *(_QWORD *)EventTag::EventTag((EventTag *)v17, (const char (*)[9])"download");
  EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(this, g_stateTag);
  v4 = CastAlpcMessage<AlpcRequest<19>>(*(_QWORD *)a2, *((_QWORD *)a2 + 1));
  memset_0(&v18, 0, 0x40u);
  v18 = *(struct _PORT_MESSAGE *)v4;
  v18.u1.Length = 4194328;
  v19 = 19;
  v17[0] = (char *)a2 + 16;
  CommunicationPortContext = AlpcServer::GetCommunicationPortContext(
                               this,
                               *((struct _ALPC_MESSAGE_ATTRIBUTES **)a2 + 2),
                               *(struct _PORT_MESSAGE **)a2);
  try
  {
    v6 = CommunicationPortContext;
    ClientContext = CommunicationPortContext::GetClientContext(
                      CommunicationPortContext,
                      *((struct IFontCacheServerInternal **)this + 5));
    (*(void (__fastcall **)(struct IFontCacheClientState *, __int64 *, _QWORD))(*(_QWORD *)ClientContext + 48LL))(
      ClientContext,
      &v15,
      *(unsigned int *)(v4 + 64));
    if ( !v15 )
    {
      Exception::Exception((Exception *)&TargetHandle, -2147024809, 0);
      EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<ArgumentException>(
        this,
        &TargetHandle,
        1668312161,
        1100);
    }
    v14 = 0;
    TargetHandle = 0;
    (*(void (__fastcall **)(_QWORD, HANDLE *))(**((_QWORD **)this + 5) + 56LL))(*((_QWORD *)this + 5), &TargetHandle);
    v8 = (*(__int64 (__fastcall **)(HANDLE, CommunicationPortContext *, __int64, __int64, __int64, _DWORD, __int64 *))(*(_QWORD *)TargetHandle + 88LL))(
           TargetHandle,
           v6,
           v4 + 48,
           v15,
           v4 + 72,
           *(_DWORD *)(v4 + 68),
           &v14);
    EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrowIfFailed(this, v8, 0x444263706C61LL, 1119);
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&TargetHandle);
    if ( v14 )
    {
      (*(void (__fastcall **)(struct IFontCacheClientState *))(*(_QWORD *)ClientContext + 56LL))(ClientContext);
      ImpersonateAndOpenClientProcessHandle(&hTargetProcessHandle, v6);
      CurrentProcess = GetCurrentProcess();
      TargetHandle = 0;
      v10 = hTargetProcessHandle;
      v11 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 24LL))(v14);
      if ( !DuplicateHandle(CurrentProcess, v11, v10, &TargetHandle, 0, 0, 2u) )
        OSException::ThrowLastError();
      v20 = TargetHandle;
      v21 = (*(__int64 (__fastcall **)(struct IFontCacheClientState *, __int64))(*(_QWORD *)ClientContext + 64LL))(
              ClientContext,
              v14);
      if ( hTargetProcessHandle )
        CloseHandle(hTargetProcessHandle);
    }
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&v14);
    ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(&v15);
  }
  catch ( ... )
  {
    MapExceptionToHresult(v12);
  }
  AlpcServer::SendReply(this, a2, &v18, *((struct _ALPC_MESSAGE_ATTRIBUTES **)a2 + 2));
}

```

## disassembly

```asm
0x1800ba1ec  mov     [rsp+arg_10], rbx
0x1800ba1f1  mov     [rsp+arg_18], rsi
0x1800ba1f6  push    rdi
0x1800ba1f7  push    r12
0x1800ba1f9  push    r13
0x1800ba1fb  push    r14
0x1800ba1fd  push    r15
0x1800ba1ff  sub     rsp, 0D0h
0x1800ba206  mov     rax, cs:__security_cookie
0x1800ba20d  xor     rax, rsp
0x1800ba210  mov     [rsp+0F8h+var_38], rax
0x1800ba218  mov     r15, rdx
0x1800ba21b  mov     rdi, rcx
0x1800ba21e  mov     [rsp+0F8h+var_88], rcx
0x1800ba223  mov     [rsp+0F8h+var_90], rdx
0x1800ba228  lea     rdx, aDownload; "download"
0x1800ba22f  lea     rcx, [rsp+0F8h+var_98]; this
0x1800ba234  call    ??0EventTag@@QEAA@AEAY08$$CBD@Z; EventTag::EventTag(char const (&)[9])
0x1800ba239  mov     r8, [rax]
0x1800ba23c  mov     [rdi+18h], r8
0x1800ba240  mov     rdx, cs:?g_stateTag@@3VEventTag@@B; EventTag const g_stateTag
0x1800ba247  mov     rcx, rdi
0x1800ba24a  call    ??$LogEvent@VEventTag@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXVEventTag@@0@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogEvent<EventTag>(EventTag,EventTag)
0x1800ba24f  mov     rdx, [r15+8]
0x1800ba253  mov     rcx, [r15]
0x1800ba256  call    ??$CastAlpcMessage@U?$AlpcRequest@$0BD@@@@@YAPEAU?$AlpcRequest@$0BD@@@PEAU_PORT_MESSAGE@@_K@Z; CastAlpcMessage<AlpcRequest<19>>(_PORT_MESSAGE *,unsigned __int64)
0x1800ba25b  mov     r12, rax
0x1800ba25e  xor     edx, edx; Val
0x1800ba260  lea     r8d, [rdx+40h]; Size
0x1800ba264  lea     rcx, [rsp+0F8h+var_78]; void *
0x1800ba26c  call    memset_0
0x1800ba271  movzx   ecx, word ptr [r12]
0x1800ba276  mov     word ptr [rsp+0F8h+var_78.u1], cx
0x1800ba27e  movzx   ecx, word ptr [r12+2]
0x1800ba284  mov     word ptr [rsp+0F8h+var_78.u1+2], cx
0x1800ba28c  movups  xmm0, xmmword ptr [r12+4]
0x1800ba292  movups  xmmword ptr [rsp+0F8h+var_78.u2], xmm0
0x1800ba29a  movups  xmm1, xmmword ptr [r12+14h]
0x1800ba2a0  movups  xmmword ptr [rsp+0F8h+var_78.8+0Ch], xmm1
0x1800ba2a8  mov     eax, [r12+24h]
0x1800ba2ad  mov     dword ptr [rsp+0F8h+var_78.20h+4], eax
0x1800ba2b4  mov     dword ptr [rsp+0F8h+var_78.u1], 400018h
0x1800ba2bf  mov     rbx, 444263706C61h
0x1800ba2c9  mov     [rsp+0F8h+var_50], 13h
0x1800ba2d4  lea     r14, [r15+10h]
0x1800ba2d8  mov     [rsp+0F8h+var_98], r14
0x1800ba2dd  mov     r8, [r15]; struct _PORT_MESSAGE *
0x1800ba2e0  mov     rdx, [r14]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800ba2e3  mov     rcx, rdi; this
0x1800ba2e6  call    ?GetCommunicationPortContext@AlpcServer@@AEAAAEAVCommunicationPortContext@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@PEAU_PORT_MESSAGE@@@Z; AlpcServer::GetCommunicationPortContext(_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *)
0x1800ba2eb  mov     r13, rax
0x1800ba2ee  mov     rdx, [rdi+28h]; struct IFontCacheServerInternal *
0x1800ba2f2  mov     rcx, rax; this
0x1800ba2f5  call    ?GetClientContext@CommunicationPortContext@@QEAAAEAUIFontCacheClientState@@PEAUIFontCacheServerInternal@@@Z; CommunicationPortContext::GetClientContext(IFontCacheServerInternal *)
0x1800ba2fa  mov     rsi, rax
0x1800ba2fd  mov     rcx, [rax]
0x1800ba300  mov     rax, [rcx+30h]
0x1800ba304  mov     r8d, [r12+40h]
0x1800ba309  lea     rdx, [rsp+0F8h+var_A8]
0x1800ba30e  mov     rcx, rsi
0x1800ba311  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba316  nop
0x1800ba317  xor     eax, eax
0x1800ba319  cmp     [rsp+0F8h+var_A8], rax
0x1800ba31e  jnz     short loc_1800BA34B
0x1800ba320  xor     r8d, r8d; unsigned int
0x1800ba323  mov     edx, 80070057h; int
0x1800ba328  lea     rcx, [rsp+0F8h+TargetHandle]; this
0x1800ba32d  call    ??0Exception@@IEAA@HI@Z; Exception::Exception(int,uint)
0x1800ba332  mov     r9d, 44Ch
0x1800ba338  mov     r8d, 63706C61h
0x1800ba33e  lea     rdx, [rsp+0F8h+TargetHandle]
0x1800ba343  mov     rcx, rdi
0x1800ba346  call    ??$LogAndThrow@VArgumentException@@@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXAEBVArgumentException@@VEventTag@@I@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrow<ArgumentException>(ArgumentException const &,EventTag,uint)
0x1800ba34b  mov     [rsp+0F8h+var_B0], rax
0x1800ba350  mov     [rsp+0F8h+TargetHandle], rax
0x1800ba355  mov     rcx, [rdi+28h]
0x1800ba359  mov     rax, [rcx]
0x1800ba35c  lea     rdx, [rsp+0F8h+TargetHandle]
0x1800ba361  mov     rax, [rax+38h]
0x1800ba365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba36a  mov     rcx, [rsp+0F8h+TargetHandle]
0x1800ba36f  mov     rax, [rcx]
0x1800ba372  lea     r9, [r12+48h]
0x1800ba377  lea     r8, [r12+30h]
0x1800ba37c  lea     rdx, [rsp+0F8h+var_B0]
0x1800ba381  mov     qword ptr [rsp+0F8h+dwOptions], rdx
0x1800ba386  mov     edx, [r12+44h]
0x1800ba38b  mov     [rsp+0F8h+bInheritHandle], edx
0x1800ba38f  mov     qword ptr [rsp+0F8h+dwDesiredAccess], r9
0x1800ba394  mov     r9, [rsp+0F8h+var_A8]
0x1800ba399  mov     rdx, r13
0x1800ba39c  mov     rax, [rax+58h]
0x1800ba3a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3a5  mov     r9d, 45Fh
0x1800ba3ab  mov     r8, rbx
0x1800ba3ae  mov     edx, eax
0x1800ba3b0  mov     rcx, rdi
0x1800ba3b3  call    ?LogAndThrowIfFailed@?$EventSource@V?$ComInterfaceList@VAlpcServer@@UIUnknown@@@@UIUnknown@@@@QEBAXJVEventTag@@I@Z; EventSource<ComInterfaceList<AlpcServer,IUnknown>,IUnknown>::LogAndThrowIfFailed(long,EventTag,uint)
0x1800ba3b8  nop
0x1800ba3b9  lea     rcx, [rsp+0F8h+TargetHandle]
0x1800ba3be  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800ba3c3  cmp     [rsp+0F8h+var_B0], 0
0x1800ba3c9  jz      loc_1800BA47B
0x1800ba3cf  mov     rax, [rsi]
0x1800ba3d2  mov     rcx, rsi
0x1800ba3d5  mov     rax, [rax+38h]
0x1800ba3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3de  mov     rdx, r13
0x1800ba3e1  lea     rcx, [rsp+0F8h+hTargetProcessHandle]
0x1800ba3e6  call    ?ImpersonateAndOpenClientProcessHandle@@YA?AVWin32Handle@@AEAVCommunicationPortContext@@@Z; ImpersonateAndOpenClientProcessHandle(CommunicationPortContext &)
0x1800ba3eb  nop
0x1800ba3ec  call    cs:__imp_GetCurrentProcess
0x1800ba3f2  mov     rbx, rax
0x1800ba3f5  xor     r13d, r13d
0x1800ba3f8  mov     [rsp+0F8h+TargetHandle], r13
0x1800ba3fd  mov     r12, [rsp+0F8h+hTargetProcessHandle]
0x1800ba402  mov     rcx, [rsp+0F8h+var_B0]
0x1800ba407  mov     rdx, [rcx]
0x1800ba40a  mov     rax, [rdx+18h]
0x1800ba40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba413  mov     [rsp+0F8h+dwOptions], 2; dwOptions
0x1800ba41b  mov     [rsp+0F8h+bInheritHandle], r13d; bInheritHandle
0x1800ba420  mov     [rsp+0F8h+dwDesiredAccess], r13d; dwDesiredAccess
0x1800ba425  lea     r9, [rsp+0F8h+TargetHandle]; lpTargetHandle
0x1800ba42a  mov     r8, r12; hTargetProcessHandle
0x1800ba42d  mov     rdx, rax; hSourceHandle
0x1800ba430  mov     rcx, rbx; hSourceProcessHandle
0x1800ba433  call    cs:__imp_DuplicateHandle
0x1800ba439  test    eax, eax
0x1800ba43b  jnz     short loc_1800BA442
0x1800ba43d  call    ?ThrowLastError@OSException@@SAXXZ; OSException::ThrowLastError(void)
0x1800ba442  mov     rax, [rsp+0F8h+TargetHandle]
0x1800ba447  mov     [rsp+0F8h+var_48], rax
0x1800ba44f  mov     rax, [rsi]
0x1800ba452  mov     rdx, [rsp+0F8h+var_B0]
0x1800ba457  mov     rcx, rsi
0x1800ba45a  mov     rax, [rax+40h]
0x1800ba45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba463  mov     [rsp+0F8h+var_40], eax
0x1800ba46a  mov     rcx, [rsp+0F8h+hTargetProcessHandle]; hObject
0x1800ba46f  test    rcx, rcx
0x1800ba472  jz      short loc_1800BA47B
0x1800ba474  call    cs:__imp_CloseHandle
0x1800ba47a  nop
0x1800ba47b  lea     rcx, [rsp+0F8h+var_B0]
0x1800ba480  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800ba485  nop
0x1800ba486  lea     rcx, [rsp+0F8h+var_A8]
0x1800ba48b  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800ba490  nop
0x1800ba491  jmp     short loc_1800BA4A2
0x1800ba493  mov     r14, [rsp+0F8h+var_98]
0x1800ba498  mov     r15, [rsp+0F8h+var_90]
0x1800ba49d  mov     rdi, [rsp+0F8h+var_88]
0x1800ba4a2  mov     r9, [r14]; struct _ALPC_MESSAGE_ATTRIBUTES *
0x1800ba4a5  lea     r8, [rsp+0F8h+var_78]; struct _PORT_MESSAGE *
0x1800ba4ad  mov     rdx, r15; struct AlpcServer::MessageContext *
0x1800ba4b0  mov     rcx, rdi; this
0x1800ba4b3  call    ?SendReply@AlpcServer@@AEAAXAEAUMessageContext@1@PEAU_PORT_MESSAGE@@PEAU_ALPC_MESSAGE_ATTRIBUTES@@@Z; AlpcServer::SendReply(AlpcServer::MessageContext &,_PORT_MESSAGE *,_ALPC_MESSAGE_ATTRIBUTES *)
0x1800ba4b8  mov     rcx, [rsp+0F8h+var_38]
0x1800ba4c0  xor     rcx, rsp; StackCookie
0x1800ba4c3  call    __security_check_cookie
0x1800ba4c8  lea     r11, [rsp+0F8h+var_28]
0x1800ba4d0  mov     rbx, [r11+40h]
0x1800ba4d4  mov     rsi, [r11+48h]
0x1800ba4d8  mov     rsp, r11
0x1800ba4db  pop     r15
0x1800ba4dd  pop     r14
0x1800ba4df  pop     r13
0x1800ba4e1  pop     r12
0x1800ba4e3  pop     rdi
0x1800ba4e4  retn
```
