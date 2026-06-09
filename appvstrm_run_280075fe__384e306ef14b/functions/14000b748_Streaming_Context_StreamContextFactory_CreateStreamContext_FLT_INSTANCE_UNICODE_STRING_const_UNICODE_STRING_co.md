# Streaming::Context::StreamContextFactory::CreateStreamContext(_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StrmStreamContext,Streaming::Context::ContextDelete> &)

- ea: `0x14000b748`
- end: `0x14000ba8b`
- name: `?CreateStreamContext@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@1AEAU_FILE_OBJECT@@AEAV?$auto_ptr@UStrmStreamContext@Context@Streaming@@UContextDelete@23@@kernel@shared@appv@@@Z`
- size: `835`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _UNICODE_STRING *, struct _UNICODE_STRING *, PFILE_OBJECT FileObject, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14000ba94`
- `0x14000bbd4`

## callees

- `0x140005e3c`
- `0x14000b0bc`
- `0x14000b748`
- `0x14000bd34`
- `0x1400147fc`
- `0x140014b00`
- `0x1400153c4`
- `0x140015b30`
- `0x140015f00`

## import_xrefs

- `FLTMGR!FltSetStreamContext` at `0x14000b958`
- `FLTMGR!FltSetStreamContext` at `0x14000b958`
- `FLTMGR!FltReleaseContext` at `0x14000b792`
- `FLTMGR!FltReleaseContext` at `0x14000b7ab`
- `FLTMGR!FltReleaseContext` at `0x14000b7c4`
- `FLTMGR!FltReleaseContext` at `0x14000b873`
- `FLTMGR!FltReleaseContext` at `0x14000b88c`
- `FLTMGR!FltReleaseContext` at `0x14000b8a5`
- `FLTMGR!FltReleaseContext` at `0x14000ba39`
- `FLTMGR!FltReleaseContext` at `0x14000ba52`
- `FLTMGR!FltReleaseContext` at `0x14000ba6b`
- `FLTMGR!FltReleaseContext` at `0x14000b792`
- `FLTMGR!FltReleaseContext` at `0x14000b7ab`
- `FLTMGR!FltReleaseContext` at `0x14000b7c4`
- `FLTMGR!FltReleaseContext` at `0x14000b873`
- `FLTMGR!FltReleaseContext` at `0x14000b88c`
- `FLTMGR!FltReleaseContext` at `0x14000b8a5`
- `FLTMGR!FltReleaseContext` at `0x14000ba39`
- `FLTMGR!FltReleaseContext` at `0x14000ba52`
- `FLTMGR!FltReleaseContext` at `0x14000ba6b`
- `FLTMGR!FltAllocateContext` at `0x14000b7fa`
- `FLTMGR!FltAllocateContext` at `0x14000b7fa`

## string_xrefs

- `0x14000b819`: `StreamContextFactory::CreateStreamContext() - Low memory error.`
- `0x14000b8f7`: `StreamContextFactory::CreateStreamContext() - Streaming filter Failed in reading and creating file information. Failure status = 0x%08X.`
- `0x14000b9b5`: `StreamContextFactory::CreateStreamContext() - Streaming filter could not set the streaming information on file '%s'. Failure status = 0x%08X.`

## pseudocode

```c
__int64 __fastcall Streaming::Context::StreamContextFactory::CreateStreamContext(
        PFLT_INSTANCE Instance,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        PFILE_OBJECT FileObject,
        PFLT_CONTEXT *a5)
{
  int StreamingInformation; // edi
  NTSTATUS StreamFileInformation; // esi
  __int64 *CurrentActivityID; // rax
  volatile signed __int32 *v13; // rdi
  __int64 *v14; // rax
  PFLT_CONTEXT v15; // rdx
  PFLT_CONTEXT v16; // rcx
  __int64 v17; // rbx
  __int64 *v18; // rax
  volatile signed __int32 *v19; // rdi
  PFLT_CONTEXT v20; // rcx
  PFLT_CONTEXT NewContext; // [rsp+30h] [rbp-48h] BYREF
  PFLT_CONTEXT Context; // [rsp+38h] [rbp-40h] BYREF
  PFLT_CONTEXT v23; // [rsp+40h] [rbp-38h] BYREF
  _BYTE v24[8]; // [rsp+48h] [rbp-30h] BYREF
  volatile signed __int32 *v25; // [rsp+50h] [rbp-28h]
  _BYTE v26[8]; // [rsp+58h] [rbp-20h] BYREF
  volatile signed __int32 *v27; // [rsp+60h] [rbp-18h]

  v23 = 0;
  NewContext = 0;
  Context = 0;
  StreamingInformation = Streaming::InstanceContextFactory::GetContext(
                           Instance,
                           Instance,
                           (struct Streaming::InstanceContext *)&v23);
  if ( StreamingInformation < 0 )
    goto LABEL_2;
  StreamFileInformation = FltAllocateContext(
                            *((PFLT_FILTER *)Streaming::gStrmFltData + 1),
                            8u,
                            0x70u,
                            PagedPool,
                            &NewContext);
  if ( StreamFileInformation < 0 )
  {
    CurrentActivityID = (__int64 *)Streaming::Utils::GetCurrentActivityID(v24);
    LogWrite(1, *CurrentActivityID, L"StreamContextFactory::CreateStreamContext() - Low memory error.");
    goto LABEL_11;
  }
  memset(NewContext, 0, 0x70u);
  StreamFileInformation = Streaming::Context::StreamContextFactory::GetStreamFileInformation(
                            Instance,
                            a2,
                            a3,
                            FileObject,
                            (struct Streaming::Context::StrmFileInfo *)((char *)NewContext + 8));
  if ( StreamFileInformation < 0 )
  {
    v14 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v24);
    LogWrite(
      1,
      *v14,
      L"StreamContextFactory::CreateStreamContext() - Streaming filter Failed in reading and creating file information. Fa"
       "ilure status = 0x%08X.",
      (unsigned int)StreamFileInformation);
LABEL_11:
    v13 = v25;
    if ( !v25 )
    {
LABEL_15:
      if ( Context )
      {
        FltReleaseContext(Context);
        Context = 0;
      }
      if ( NewContext )
      {
        FltReleaseContext(NewContext);
        NewContext = 0;
      }
      if ( v23 )
        FltReleaseContext(v23);
      return (unsigned int)StreamFileInformation;
    }
LABEL_12:
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    goto LABEL_15;
  }
  StreamingInformation = Streaming::Context::StreamingBitmapBuilder::ReadStreamingInformation(Instance, FileObject);
  if ( StreamingInformation < 0 )
  {
LABEL_2:
    if ( Context )
    {
      FltReleaseContext(Context);
      Context = 0;
    }
    if ( NewContext )
    {
      FltReleaseContext(NewContext);
      NewContext = 0;
    }
    if ( v23 )
      FltReleaseContext(v23);
    return (unsigned int)StreamingInformation;
  }
  *((_QWORD *)NewContext + 13) = Instance;
  if ( v23 )
    _InterlockedIncrement((volatile signed __int32 *)v23 + 6);
  StreamFileInformation = FltSetStreamContext(
                            Instance,
                            FileObject,
                            FLT_SET_CONTEXT_KEEP_IF_EXISTS,
                            NewContext,
                            &Context);
  if ( StreamFileInformation == -1071906814 )
  {
    v15 = Context;
    Context = *a5;
    v16 = Context;
    *a5 = v15;
    if ( !v16 )
    {
LABEL_40:
      v20 = NewContext;
      goto LABEL_41;
    }
LABEL_39:
    FltReleaseContext(v16);
    Context = 0;
    goto LABEL_40;
  }
  if ( StreamFileInformation < 0 )
  {
    v17 = *(_QWORD *)Streaming::Utils::GetNullTerminated(v26, a3);
    v18 = (__int64 *)Streaming::Utils::GetCurrentActivityID(v24);
    LogWrite(
      1,
      *v18,
      L"StreamContextFactory::CreateStreamContext() - Streaming filter could not set the streaming information on file '%s"
       "'. Failure status = 0x%08X.",
      (unsigned int)StreamFileInformation,
      v17);
    v19 = v25;
    if ( v25 )
    {
      if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    v13 = v27;
    if ( !v27 )
      goto LABEL_15;
    goto LABEL_12;
  }
  v20 = *a5;
  *a5 = NewContext;
  NewContext = v20;
  if ( Context )
  {
    v16 = Context;
    goto LABEL_39;
  }
LABEL_41:
  if ( v20 )
  {
    FltReleaseContext(v20);
    NewContext = 0;
  }
  if ( v23 )
    FltReleaseContext(v23);
  return 0;
}

```

## disassembly

```asm
0x14000b748  push    rbp
0x14000b74a  push    rbx
0x14000b74b  push    rsi
0x14000b74c  push    rdi
0x14000b74d  push    r12
0x14000b74f  push    r13
0x14000b751  push    r14
0x14000b753  push    r15
0x14000b755  mov     rbp, rsp
0x14000b758  sub     rsp, 78h
0x14000b75c  xor     r13d, r13d
0x14000b75f  mov     r12, r8
0x14000b762  mov     r15, rdx
0x14000b765  mov     [rbp+var_38], r13
0x14000b769  lea     r8, [rbp+var_38]; struct Streaming::InstanceContext *
0x14000b76d  mov     [rbp+NewContext], r13
0x14000b771  mov     rdx, rcx; struct _FLT_INSTANCE *
0x14000b774  mov     [rbp+Context], r13
0x14000b778  mov     r14, r9
0x14000b77b  mov     rbx, rcx
0x14000b77e  call    ?GetContext@InstanceContextFactory@Streaming@@QEAAJPEAU_FLT_INSTANCE@@AEAVInstanceContext@2@@Z; Streaming::InstanceContextFactory::GetContext(_FLT_INSTANCE *,Streaming::InstanceContext &)
0x14000b783  mov     edi, eax
0x14000b785  test    eax, eax
0x14000b787  jns     short loc_14000B7D7
0x14000b789  mov     rcx, [rbp+Context]; Context
0x14000b78d  test    rcx, rcx
0x14000b790  jz      short loc_14000B7A2
0x14000b792  call    cs:__imp_FltReleaseContext
0x14000b799  nop     dword ptr [rax+rax+00h]
0x14000b79e  mov     [rbp+Context], r13
0x14000b7a2  mov     rcx, [rbp+NewContext]; Context
0x14000b7a6  test    rcx, rcx
0x14000b7a9  jz      short loc_14000B7BB
0x14000b7ab  call    cs:__imp_FltReleaseContext
0x14000b7b2  nop     dword ptr [rax+rax+00h]
0x14000b7b7  mov     [rbp+NewContext], r13
0x14000b7bb  mov     rcx, [rbp+var_38]; Context
0x14000b7bf  test    rcx, rcx
0x14000b7c2  jz      short loc_14000B7D0
0x14000b7c4  call    cs:__imp_FltReleaseContext
0x14000b7cb  nop     dword ptr [rax+rax+00h]
0x14000b7d0  mov     eax, edi
0x14000b7d2  jmp     loc_14000BA79
0x14000b7d7  mov     rcx, cs:?gStrmFltData@Streaming@@3PEAUStrmGlobalData@1@EA; Streaming::StrmGlobalData * Streaming::gStrmFltData
0x14000b7de  lea     rax, [rbp+NewContext]
0x14000b7e2  mov     edx, 8; ContextType
0x14000b7e7  mov     [rsp+78h+ReturnedContext], rax; ReturnedContext
0x14000b7ec  mov     rcx, [rcx+8]; Filter
0x14000b7f0  lea     edi, [rdx-7]
0x14000b7f3  mov     r9d, edi; PoolType
0x14000b7f6  lea     r8d, [rdx+68h]; ContextSize
0x14000b7fa  call    cs:__imp_FltAllocateContext
0x14000b801  nop     dword ptr [rax+rax+00h]
0x14000b806  mov     esi, eax
0x14000b808  test    eax, eax
0x14000b80a  jns     loc_14000B8B8
0x14000b810  lea     rcx, [rbp+var_30]
0x14000b814  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b819  lea     r8, aStreamcontextf_1; "StreamContextFactory::CreateStreamConte"...
0x14000b820  mov     ecx, edi
0x14000b822  mov     rdx, [rax]
0x14000b825  call    LogWrite
0x14000b82a  mov     rdi, [rbp+var_28]
0x14000b82e  test    rdi, rdi
0x14000b831  jz      short loc_14000B86A
0x14000b833  or      ebx, 0FFFFFFFFh
0x14000b836  mov     eax, ebx
0x14000b838  lock xadd [rdi+8], eax
0x14000b83d  add     eax, ebx
0x14000b83f  jnz     short loc_14000B86A
0x14000b841  mov     rax, [rdi]
0x14000b844  mov     rcx, rdi
0x14000b847  mov     rax, [rax+8]
0x14000b84b  call    _guard_dispatch_icall
0x14000b850  mov     eax, ebx
0x14000b852  lock xadd [rdi+0Ch], eax
0x14000b857  add     eax, ebx
0x14000b859  jnz     short loc_14000B86A
0x14000b85b  mov     rax, [rdi]
0x14000b85e  mov     rcx, rdi
0x14000b861  mov     rax, [rax+10h]
0x14000b865  call    _guard_dispatch_icall
0x14000b86a  mov     rcx, [rbp+Context]; Context
0x14000b86e  test    rcx, rcx
0x14000b871  jz      short loc_14000B883
0x14000b873  call    cs:__imp_FltReleaseContext
0x14000b87a  nop     dword ptr [rax+rax+00h]
0x14000b87f  mov     [rbp+Context], r13
0x14000b883  mov     rcx, [rbp+NewContext]; Context
0x14000b887  test    rcx, rcx
0x14000b88a  jz      short loc_14000B89C
0x14000b88c  call    cs:__imp_FltReleaseContext
0x14000b893  nop     dword ptr [rax+rax+00h]
0x14000b898  mov     [rbp+NewContext], r13
0x14000b89c  mov     rcx, [rbp+var_38]; Context
0x14000b8a0  test    rcx, rcx
0x14000b8a3  jz      short loc_14000B8B1
0x14000b8a5  call    cs:__imp_FltReleaseContext
0x14000b8ac  nop     dword ptr [rax+rax+00h]
0x14000b8b1  mov     eax, esi
0x14000b8b3  jmp     loc_14000BA79
0x14000b8b8  mov     rcx, [rbp+NewContext]; void *
0x14000b8bc  xor     edx, edx; Val
0x14000b8be  lea     r8d, [rdx+70h]; Size
0x14000b8c2  call    memset
0x14000b8c7  mov     rax, [rbp+NewContext]
0x14000b8cb  mov     r9, r14; struct _FILE_OBJECT *
0x14000b8ce  add     rax, 8
0x14000b8d2  mov     r8, r12; struct _UNICODE_STRING *
0x14000b8d5  mov     rdx, r15; struct _UNICODE_STRING *
0x14000b8d8  mov     [rsp+78h+ReturnedContext], rax; struct Streaming::Context::StrmFileInfo *
0x14000b8dd  mov     rcx, rbx; Instance
0x14000b8e0  call    ?GetStreamFileInformation@StreamContextFactory@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEBU_UNICODE_STRING@@1AEAU_FILE_OBJECT@@AEAUStrmFileInfo@23@@Z; Streaming::Context::StreamContextFactory::GetStreamFileInformation(_FLT_INSTANCE *,_UNICODE_STRING const &,_UNICODE_STRING const &,_FILE_OBJECT &,Streaming::Context::StrmFileInfo &)
0x14000b8e5  mov     esi, eax
0x14000b8e7  test    eax, eax
0x14000b8e9  jns     short loc_14000B90D
0x14000b8eb  lea     rcx, [rbp+var_30]
0x14000b8ef  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b8f4  mov     r9d, esi
0x14000b8f7  lea     r8, aStreamcontextf; "StreamContextFactory::CreateStreamConte"...
0x14000b8fe  mov     ecx, edi
0x14000b900  mov     rdx, [rax]
0x14000b903  call    LogWrite
0x14000b908  jmp     loc_14000B82A
0x14000b90d  mov     r8, [rbp+NewContext]
0x14000b911  mov     rdx, r14; FileObject
0x14000b914  add     r8, 58h ; 'X'
0x14000b918  mov     rcx, rbx; Instance
0x14000b91b  call    ?ReadStreamingInformation@StreamingBitmapBuilder@Context@Streaming@@SAJPEAU_FLT_INSTANCE@@AEAU_FILE_OBJECT@@AEAV?$auto_ptr@VStreamingBitMap@Context@Streaming@@U?$AllocDelete@VStreamingBitMap@Context@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@@Z; Streaming::Context::StreamingBitmapBuilder::ReadStreamingInformation(_FLT_INSTANCE *,_FILE_OBJECT &,appv::shared::kernel::auto_ptr<Streaming::Context::StreamingBitMap,appv::shared::kernel::AllocDelete<Streaming::Context::StreamingBitMap>> &)
0x14000b920  mov     edi, eax
0x14000b922  test    eax, eax
0x14000b924  js      loc_14000B789
0x14000b92a  mov     rax, [rbp+NewContext]
0x14000b92e  mov     [rax+68h], rbx
0x14000b932  mov     rax, [rbp+var_38]
0x14000b936  test    rax, rax
0x14000b939  jz      short loc_14000B93F
0x14000b93b  lock inc dword ptr [rax+18h]
0x14000b93f  mov     r9, [rbp+NewContext]; NewContext
0x14000b943  lea     rax, [rbp+Context]
0x14000b947  mov     r8d, 1; Operation
0x14000b94d  mov     [rsp+78h+ReturnedContext], rax; OldContext
0x14000b952  mov     rdx, r14; FileObject
0x14000b955  mov     rcx, rbx; Instance
0x14000b958  call    cs:__imp_FltSetStreamContext
0x14000b95f  nop     dword ptr [rax+rax+00h]
0x14000b964  mov     esi, eax
0x14000b966  cmp     eax, 0C01C0002h
0x14000b96b  jnz     short loc_14000B98D
0x14000b96d  mov     rax, [rbp+arg_20]
0x14000b971  mov     rdx, [rbp+Context]
0x14000b975  mov     rcx, [rax]
0x14000b978  mov     [rbp+Context], rcx
0x14000b97c  mov     [rax], rdx
0x14000b97f  test    rcx, rcx
0x14000b982  jz      loc_14000BA49
0x14000b988  jmp     loc_14000BA39
0x14000b98d  test    esi, esi
0x14000b98f  jns     loc_14000BA1B
0x14000b995  mov     rdx, r12
0x14000b998  lea     rcx, [rbp+var_20]
0x14000b99c  call    ?GetNullTerminated@Utils@Streaming@@YA?AV?$shared_ptr@_W@kernel_std@@PEBU_UNICODE_STRING@@@Z; Streaming::Utils::GetNullTerminated(_UNICODE_STRING const *)
0x14000b9a1  lea     rcx, [rbp+var_30]
0x14000b9a5  mov     rbx, [rax]
0x14000b9a8  call    ?GetCurrentActivityID@Utils@Streaming@@YA?AV?$shared_ptr@U_GUID@@@kernel_std@@XZ; Streaming::Utils::GetCurrentActivityID(void)
0x14000b9ad  mov     r9d, esi
0x14000b9b0  mov     [rsp+78h+ReturnedContext], rbx
0x14000b9b5  lea     r8, aStreamcontextf_0; "StreamContextFactory::CreateStreamConte"...
0x14000b9bc  mov     ecx, 1
0x14000b9c1  mov     rdx, [rax]
0x14000b9c4  call    LogWrite
0x14000b9c9  mov     rdi, [rbp+var_28]
0x14000b9cd  or      ebx, 0FFFFFFFFh
0x14000b9d0  test    rdi, rdi
0x14000b9d3  jz      short loc_14000BA09
0x14000b9d5  mov     eax, ebx
0x14000b9d7  lock xadd [rdi+8], eax
0x14000b9dc  add     eax, ebx
0x14000b9de  jnz     short loc_14000BA09
0x14000b9e0  mov     rax, [rdi]
0x14000b9e3  mov     rcx, rdi
0x14000b9e6  mov     rax, [rax+8]
0x14000b9ea  call    _guard_dispatch_icall
0x14000b9ef  mov     eax, ebx
0x14000b9f1  lock xadd [rdi+0Ch], eax
0x14000b9f6  add     eax, ebx
0x14000b9f8  jnz     short loc_14000BA09
0x14000b9fa  mov     rax, [rdi]
0x14000b9fd  mov     rcx, rdi
0x14000ba00  mov     rax, [rax+10h]
0x14000ba04  call    _guard_dispatch_icall
0x14000ba09  mov     rdi, [rbp+var_18]
0x14000ba0d  test    rdi, rdi
0x14000ba10  jz      loc_14000B86A
0x14000ba16  jmp     loc_14000B836
0x14000ba1b  mov     rax, [rbp+arg_20]
0x14000ba1f  mov     rdx, [rbp+NewContext]
0x14000ba23  mov     rcx, [rax]
0x14000ba26  mov     [rax], rdx
0x14000ba29  mov     rax, [rbp+Context]
0x14000ba2d  mov     [rbp+NewContext], rcx
0x14000ba31  test    rax, rax
0x14000ba34  jz      short loc_14000BA4D
0x14000ba36  mov     rcx, rax; Context
0x14000ba39  call    cs:__imp_FltReleaseContext
0x14000ba40  nop     dword ptr [rax+rax+00h]
0x14000ba45  mov     [rbp+Context], r13
0x14000ba49  mov     rcx, [rbp+NewContext]; Context
0x14000ba4d  test    rcx, rcx
0x14000ba50  jz      short loc_14000BA62
0x14000ba52  call    cs:__imp_FltReleaseContext
0x14000ba59  nop     dword ptr [rax+rax+00h]
0x14000ba5e  mov     [rbp+NewContext], r13
0x14000ba62  mov     rcx, [rbp+var_38]; Context
0x14000ba66  test    rcx, rcx
0x14000ba69  jz      short loc_14000BA77
0x14000ba6b  call    cs:__imp_FltReleaseContext
0x14000ba72  nop     dword ptr [rax+rax+00h]
0x14000ba77  xor     eax, eax
0x14000ba79  add     rsp, 78h
0x14000ba7d  pop     r15
0x14000ba7f  pop     r14
0x14000ba81  pop     r13
0x14000ba83  pop     r12
0x14000ba85  pop     rdi
0x14000ba86  pop     rsi
0x14000ba87  pop     rbx
0x14000ba88  pop     rbp
0x14000ba89  retn
```
