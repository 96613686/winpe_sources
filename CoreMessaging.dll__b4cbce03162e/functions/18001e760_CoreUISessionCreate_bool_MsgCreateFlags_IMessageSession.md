# CoreUISessionCreate(bool,MsgCreateFlags,IMessageSession * *)

- ea: `0x18001e760`
- end: `0x18001eb92`
- name: `?CoreUISessionCreate@@YAJ_NW4MsgCreateFlags@@PEAPEAUIMessageSession@@@Z`
- size: `1074`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001e220`
- `0x18007e3e0`
- `0x18007f7c0`
- `0x180080cb0`
- `0x1800a23fc`

## callees

- `0x180005da0`
- `0x180007198`
- `0x180007d80`
- `0x1800089c0`
- `0x18000ec10`
- `0x18001e760`
- `0x18001eb98`
- `0x18001ebcc`
- `0x18001ee6c`
- `0x18001eeec`
- `0x18001ffcc`
- `0x180020068`
- `0x18002088c`
- `0x180021a84`
- `0x180021d8c`
- `0x180021edc`
- `0x180049d98`
- `0x180081c94`
- `0x180081d10`
- `0x18008cc78`
- `0x18009d670`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e837`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e9b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ea0d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e837`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001e9b8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001ea0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CoreUISessionCreate(char a1, char a2, __int64 *a3)
{
  void (*v5)(struct Cn::Context *); // rcx
  __int64 v6; // r8
  bool v7; // r12
  int v8; // esi
  struct Cn::Context *ThreadContextOrNullAndLock; // rax
  int v10; // r8d
  struct Cn::Context *Ptr; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // r15d
  char v17; // r14
  __int64 v18; // r8
  Microsoft::CoreUI::Dispatch::ThreadContext *v19; // r13
  Microsoft::CoreUI::Dispatch::EventLoop *v20; // rax
  __int64 v21; // rcx
  char v22; // r12
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rdx
  System::Object *v26; // rsi
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // rdx
  volatile signed __int64 *Value; // rax
  char v34; // [rsp+31h] [rbp-87h]
  char v35; // [rsp+32h] [rbp-86h]
  __int64 v36; // [rsp+38h] [rbp-80h] BYREF
  __int64 *v37; // [rsp+40h] [rbp-78h]
  System::Exception::Holder$ *v38; // [rsp+48h] [rbp-70h] BYREF
  System::Exception::Holder$ *v39; // [rsp+50h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+58h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v41; // [rsp+68h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v42; // [rsp+78h] [rbp-40h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+0h]

  v37 = a3;
  McGenEventRegister_EventRegister();
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v5, &Session_CoreUICreate_Start, v6, 1u, &v41);
  byte_180105089 = 1;
  v36 = 0;
  v35 = 0;
  v7 = a2 & 1;
  v8 = a2 & 2;
  v41.Ptr = 0;
  v34 = 0;
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)v5, &Session_CoreUICreate_InitializeCnContext_Start, v6, 1u, &v40);
  if ( v8 )
  {
    Cn::Context::NoContext_GetFreeThreadedContext(v5, (struct Cn::Context **)&v41);
    Ptr = (struct Cn::Context *)v41.Ptr;
  }
  else
  {
    ThreadContextOrNullAndLock = Cn::Context::NoContext_GetThreadContextOrNullAndLock();
    Ptr = ThreadContextOrNullAndLock;
    v41.Ptr = (ULONGLONG)ThreadContextOrNullAndLock;
    if ( ThreadContextOrNullAndLock )
    {
      _InterlockedIncrement64((volatile signed __int64 *)ThreadContextOrNullAndLock + 4);
    }
    else
    {
      Value = (volatile signed __int64 *)TlsGetValue(Cn::Context::s_tlsStorage);
      Ptr = (struct Cn::Context *)Value;
      if ( Value )
        _InterlockedIncrement64(Value + 4);
      else
        Ptr = Cn::Context::AllocAndInitializeContext(1);
      v41.Ptr = (ULONGLONG)Ptr;
      ConfigureNewContext(Ptr);
    }
  }
  v16 = CFlat::EntryExit::OnBeginCallToCFlat((const char16_t *)Ptr, retaddr, v10);
  if ( v16 )
    CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,unsigned long,void *)>>::GetHashCode(
      v13,
      v12,
      v14,
      v15);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v13, &Session_CoreUICreate_InitializeCnContext_Stop, v14, 1u, &v40);
  if ( *(_DWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 36LL) )
  {
    Microsoft::CoreUI::CoreUISession::AddRef();
    v17 = 0;
    v34 = 1;
  }
  else
  {
    *(_DWORD *)(*((_QWORD *)TlsGetValue(Cn::Context::s_tlsStorage) + 6) + 36LL) = 1;
    LOBYTE(v30) = v7;
    LOBYTE(v31) = a1;
    LOBYTE(v32) = v8 != 0;
    Microsoft::CoreUI::Dispatch::ThreadContext::InternalCreate(&v40, v32, v31, v30);
    if ( v40.Ptr )
      System::Object::ReleaseNotFrozen$((System::Object *)v40.Ptr);
    v17 = 1;
  }
  v19 = (Microsoft::CoreUI::Dispatch::ThreadContext *)CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::get_Value();
  v20 = (Microsoft::CoreUI::Dispatch::EventLoop *)*((_QWORD *)v19 + 5);
  v40.Ptr = (ULONGLONG)v20;
  v21 = *((_QWORD *)v19 + 6);
  if ( (*(_BYTE *)(v21 + 232) & 1) != 0 )
  {
    Microsoft::CoreUI::Dispatch::EventLoop::OnSessionResurrected(v20, v7);
    *((_BYTE *)Ptr + 77) = 0;
    v34 = 0;
    v22 = 1;
  }
  else
  {
    v22 = 0;
    if ( v8 )
      *((_BYTE *)Ptr + 77) = 0;
  }
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v21, &Session_CoreUICreate_ExportSession_Start, v18, 1u, &v42);
  CFlat::Marshal<IMessageSession *,CFlat::InterfacePtr<Microsoft::CoreUI::IExportMessageSession>,void>::Convert(
    *((_QWORD *)v19 + 6),
    &v36);
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v23, &Session_CoreUICreate_ExportSession_Stop, v24, 1u, &v42);
  try
  {
    if ( v17 || v22 )
      v22 = 1;
    Microsoft::CoreUI::CoreUISession::Release();
  }
  catch ( System::Exception::Holder$ *v39 )
  {
    LODWORD(v40.Ptr) = *(_DWORD *)(*(_QWORD *)v39 + 40LL);
    v35 = 1;
    try
    {
      Ptr = (struct Cn::Context *)v41.Ptr;
      Cn::Context::ShutdownAdapters((Cn::Context *)v41.Ptr);
      Microsoft::CoreUI::CoreUISession::Release();
    }
    catch ( System::Exception::Holder$ )
    {
      Ptr = (struct Cn::Context *)v41.Ptr;
    }
LABEL_51:
    v16 = v40.Ptr;
    goto LABEL_28;
  }
  if ( v17 && !v8 )
    Microsoft::CoreUI::Dispatch::ThreadContext::PrepareKeepAlive(v19, (volatile signed __int64 *)Ptr);
  v26 = *(System::Object **)(v40.Ptr + 168);
  v40.Ptr = (ULONGLONG)v26;
  if ( v26 )
    ++*((_DWORD *)v26 + 4);
  try
  {
    LOBYTE(v25) = v22;
    (*(void (__fastcall **)(System::Object *, __int64))(*(_QWORD *)v26 + 152LL))(v26, v25);
    if ( v26 )
      System::Object::ReleaseNotFrozen$(v26);
  }
  catch ( System::Exception::Holder$ *v38 )
  {
    LODWORD(v40.Ptr) = *(_DWORD *)(*(_QWORD *)v38 + 40LL);
    Ptr = (struct Cn::Context *)v41.Ptr;
    goto LABEL_51;
  }
LABEL_28:
  CFlat::EntryExit::OnEndCallToCFlat(Ptr);
  if ( v34 )
    Cn::Context::UninitializeContext(Ptr);
  v28 = v36;
  if ( v16 < 0 && v36 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v28 = 0;
    v36 = 0;
  }
  if ( v35 && v17 )
  {
    Cn::Context::UninitializeContext(Ptr);
    v28 = v36;
  }
  if ( v28 )
  {
    *v37 = v28;
    v36 = 0;
  }
  if ( (Microsoft_WindowsPhone_CoreMessagingEnableBits & 8) != 0 )
    McGenEventWrite_EventWriteTransfer(v28, &Session_CoreUICreate_Stop, v27, 1u, &v42);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18001e760  mov     [rsp+arg_8], rsi
0x18001e765  push    rdi
0x18001e766  push    r12
0x18001e768  push    r13
0x18001e76a  push    r14
0x18001e76c  push    r15
0x18001e76e  sub     rsp, 90h
0x18001e775  mov     rax, cs:__security_cookie
0x18001e77c  xor     rax, rsp
0x18001e77f  mov     [rsp+0B8h+var_30], rax
0x18001e787  mov     esi, edx
0x18001e789  mov     r13b, cl
0x18001e78c  mov     [rsp+0B8h+var_78], r8
0x18001e791  call    McGenEventRegister_EventRegister
0x18001e796  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e79d  jnz     loc_18001EA56
0x18001e7a3  mov     cs:byte_180105089, 1
0x18001e7aa  mov     [rsp+0B8h+var_80], 0
0x18001e7b3  mov     [rsp+0B8h+var_88], 0
0x18001e7b8  mov     [rsp+0B8h+var_86], 0
0x18001e7bd  mov     r12b, sil
0x18001e7c0  and     r12b, 1
0x18001e7c4  and     esi, 2
0x18001e7c7  setnz   r14b
0x18001e7cb  mov     qword ptr [rsp+0B8h+var_50], 0
0x18001e7d4  mov     [rsp+0B8h+var_87], 0
0x18001e7d9  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e7e0  jnz     loc_18001EA77
0x18001e7e6  test    esi, esi
0x18001e7e8  jnz     loc_18001E9F3
0x18001e7ee  call    ?NoContext_GetThreadContextOrNullAndLock@Context@Cn@@SAPEAV12@XZ; Cn::Context::NoContext_GetThreadContextOrNullAndLock(void)
0x18001e7f3  mov     rdi, rax
0x18001e7f6  mov     qword ptr [rsp+0B8h+var_50], rax
0x18001e7fb  test    rax, rax
0x18001e7fe  jz      loc_18001EA07
0x18001e804  lock inc qword ptr [rax+20h]
0x18001e809  mov     rdx, [rsp+0B8h]; void *
0x18001e811  mov     rcx, rdi; void *
0x18001e814  call    ?OnBeginCallToCFlat@EntryExit@CFlat@@SAJPEAX0H@Z; CFlat::EntryExit::OnBeginCallToCFlat(void *,void *,int)
0x18001e819  mov     r15d, eax
0x18001e81c  test    eax, eax
0x18001e81e  jnz     loc_18001EA98
0x18001e824  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e82b  jnz     loc_18001EA9E
0x18001e831  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e837  call    cs:__imp_TlsGetValue
0x18001e83d  mov     rcx, [rax+30h]
0x18001e841  cmp     dword ptr [rcx+24h], 0
0x18001e845  jz      loc_18001E9B2
0x18001e84b  call    ?AddRef@CoreUISession@CoreUI@Microsoft@@SAXXZ; Microsoft::CoreUI::CoreUISession::AddRef(void)
0x18001e850  xor     r14b, r14b
0x18001e853  mov     [rsp+0B8h+var_87], 1
0x18001e858  mov     [rsp+0B8h+var_88], r14b
0x18001e85d  call    ?get_Value@?$ContextLocal$1@V?$SmartPtr@VThreadContext@Dispatch@CoreUI@Microsoft@@@CFlat@@@CFlat@@QEAAPEAVThreadContext@Dispatch@CoreUI@Microsoft@@XZ; CFlat::ContextLocal$1<CFlat::SmartPtr<Microsoft::CoreUI::Dispatch::ThreadContext>>::get_Value(void)
0x18001e862  mov     r13, rax
0x18001e865  mov     rax, [rax+28h]
0x18001e869  mov     qword ptr [rsp+0B8h+var_60], rax
0x18001e86e  mov     rcx, [r13+30h]
0x18001e872  test    byte ptr [rcx+0E8h], 1
0x18001e879  jnz     loc_18001E996
0x18001e87f  xor     r12b, r12b
0x18001e882  test    esi, esi
0x18001e884  jnz     loc_18001EABF
0x18001e88a  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e891  jnz     loc_18001EAC8
0x18001e897  lea     rdx, [rsp+0B8h+var_80]
0x18001e89c  mov     rcx, [r13+30h]
0x18001e8a0  call    ?Convert@?$Marshal@PEAUIMessageSession@@U?$InterfacePtr@VIExportMessageSession@CoreUI@Microsoft@@@CFlat@@X@CFlat@@SAXU?$FastInterfacePtr@VIExportMessageSession@CoreUI@Microsoft@@@2@U?$Ref@PEAUIMessageSession@@@2@@Z; CFlat::Marshal<IMessageSession *,CFlat::InterfacePtr<Microsoft::CoreUI::IExportMessageSession>,void>::Convert(CFlat::FastInterfacePtr<Microsoft::CoreUI::IExportMessageSession>,CFlat::Ref<IMessageSession *>)
0x18001e8a5  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e8ac  jnz     loc_18001EAE9
0x18001e8b2  test    r14b, r14b
0x18001e8b5  jnz     loc_18001E98E
0x18001e8bb  test    r12b, r12b
0x18001e8be  jnz     loc_18001E98E
0x18001e8c4  call    ?Release@CoreUISession@CoreUI@Microsoft@@SAXXZ; Microsoft::CoreUI::CoreUISession::Release(void)
0x18001e8c9  test    r14b, r14b
0x18001e8cc  jnz     loc_18001EA37
0x18001e8d2  mov     rsi, qword ptr [rsp+0B8h+var_60]
0x18001e8d7  mov     rsi, [rsi+0A8h]
0x18001e8de  mov     qword ptr [rsp+0B8h+var_60], rsi
0x18001e8e3  test    rsi, rsi
0x18001e8e6  jz      short loc_18001E8EB
0x18001e8e8  inc     dword ptr [rsi+10h]
0x18001e8eb  mov     rax, [rsi]
0x18001e8ee  mov     dl, r12b
0x18001e8f1  mov     rcx, rsi
0x18001e8f4  mov     rax, [rax+98h]
0x18001e8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e900  nop
0x18001e901  test    rsi, rsi
0x18001e904  jz      short loc_18001E90F
0x18001e906  mov     rcx, rsi; this
0x18001e909  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001e90e  nop
0x18001e90f  mov     rcx, rdi; void *
0x18001e912  call    ?OnEndCallToCFlat@EntryExit@CFlat@@SAXPEAX@Z; CFlat::EntryExit::OnEndCallToCFlat(void *)
0x18001e917  cmp     [rsp+0B8h+var_87], 0
0x18001e91c  jz      short loc_18001E926
0x18001e91e  mov     rcx, rdi; struct Cn::Context *
0x18001e921  call    ?UninitializeContext@Context@Cn@@SAXPEAV12@@Z; Cn::Context::UninitializeContext(Cn::Context *)
0x18001e926  mov     rcx, [rsp+0B8h+var_80]
0x18001e92b  test    r15d, r15d
0x18001e92e  js      loc_18001EB35
0x18001e934  cmp     [rsp+0B8h+var_86], 0
0x18001e939  jnz     loc_18001EB56
0x18001e93f  test    rcx, rcx
0x18001e942  jz      short loc_18001E955
0x18001e944  mov     rax, [rsp+0B8h+var_78]
0x18001e949  mov     [rax], rcx
0x18001e94c  mov     [rsp+0B8h+var_80], 0
0x18001e955  test    byte ptr cs:Microsoft_WindowsPhone_CoreMessagingEnableBits, 8
0x18001e95c  jnz     loc_18001EB71
0x18001e962  mov     eax, r15d
0x18001e965  mov     rcx, [rsp+0B8h+var_30]
0x18001e96d  xor     rcx, rsp; StackCookie
0x18001e970  call    __security_check_cookie
0x18001e975  mov     rsi, [rsp+0B8h+arg_8]
0x18001e97d  add     rsp, 90h
0x18001e984  pop     r15
0x18001e986  pop     r14
0x18001e988  pop     r13
0x18001e98a  pop     r12
0x18001e98c  pop     rdi
0x18001e98d  retn
0x18001e98e  mov     r12b, 1
0x18001e991  jmp     loc_18001E8C4
0x18001e996  mov     dl, r12b; bool
0x18001e999  mov     rcx, rax; this
0x18001e99c  call    ?OnSessionResurrected@EventLoop@Dispatch@CoreUI@Microsoft@@QEAAX_N@Z; Microsoft::CoreUI::Dispatch::EventLoop::OnSessionResurrected(bool)
0x18001e9a1  mov     byte ptr [rdi+4Dh], 0
0x18001e9a5  mov     [rsp+0B8h+var_87], 0
0x18001e9aa  mov     r12b, 1
0x18001e9ad  jmp     loc_18001E88A
0x18001e9b2  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001e9b8  call    cs:__imp_TlsGetValue
0x18001e9be  mov     rcx, [rax+30h]
0x18001e9c2  mov     dword ptr [rcx+24h], 1
0x18001e9c9  mov     r9b, r12b
0x18001e9cc  mov     r8b, r13b
0x18001e9cf  mov     dl, r14b
0x18001e9d2  lea     rcx, [rsp+0B8h+var_60]
0x18001e9d7  call    ?InternalCreate@ThreadContext@Dispatch@CoreUI@Microsoft@@SA?AV?$SmartPtr@VThreadContext@Dispatch@CoreUI@Microsoft@@@CFlat@@_N00@Z; Microsoft::CoreUI::Dispatch::ThreadContext::InternalCreate(bool,bool,bool)
0x18001e9dc  mov     rcx, qword ptr [rsp+0B8h+var_60]; this
0x18001e9e1  test    rcx, rcx
0x18001e9e4  jz      short loc_18001E9EB
0x18001e9e6  call    ?ReleaseNotFrozen$@Object@System@@AEAAXXZ; System::Object::ReleaseNotFrozen$(void)
0x18001e9eb  mov     r14b, 1
0x18001e9ee  jmp     loc_18001E858
0x18001e9f3  lea     rdx, [rsp+0B8h+var_50]; struct Cn::Context **
0x18001e9f8  call    ?NoContext_GetFreeThreadedContext@Context@Cn@@SAXP6AXPEAV12@@ZPEAPEAV12@@Z; Cn::Context::NoContext_GetFreeThreadedContext(void (*)(Cn::Context *),Cn::Context * *)
0x18001e9fd  mov     rdi, qword ptr [rsp+0B8h+var_50]
0x18001ea02  jmp     loc_18001E809
0x18001ea07  mov     ecx, cs:?s_tlsStorage@Context@Cn@@0IA; dwTlsIndex
0x18001ea0d  call    cs:__imp_TlsGetValue
0x18001ea13  mov     rdi, rax
0x18001ea16  test    rax, rax
0x18001ea19  jnz     short loc_18001EA4F
0x18001ea1b  mov     cl, 1; bool
0x18001ea1d  call    ?AllocAndInitializeContext@Context@Cn@@CAPEAV12@_N@Z; Cn::Context::AllocAndInitializeContext(bool)
0x18001ea22  mov     rdi, rax
0x18001ea25  mov     qword ptr [rsp+0B8h+var_50], rdi
0x18001ea2a  mov     rcx, rdi; struct Cn::Context *
0x18001ea2d  call    ?ConfigureNewContext@@YAXPEAVContext@Cn@@@Z; ConfigureNewContext(Cn::Context *)
0x18001ea32  jmp     loc_18001E809
0x18001ea37  test    esi, esi
0x18001ea39  jnz     loc_18001E8D2
0x18001ea3f  mov     rdx, rdi; void *
0x18001ea42  mov     rcx, r13; this
0x18001ea45  call    ?PrepareKeepAlive@ThreadContext@Dispatch@CoreUI@Microsoft@@AEAAXPEAX@Z; Microsoft::CoreUI::Dispatch::ThreadContext::PrepareKeepAlive(void *)
0x18001ea4a  jmp     loc_18001E8D2
0x18001ea4f  lock inc qword ptr [rax+20h]
0x18001ea54  jmp     short loc_18001EA25
0x18001ea56  lea     rax, [rsp+0B8h+var_50]
0x18001ea5b  mov     [rsp+0B8h+var_98], rax
0x18001ea60  mov     r9d, 1
0x18001ea66  lea     rdx, Session_CoreUICreate_Start
0x18001ea6d  call    McGenEventWrite_EventWriteTransfer
0x18001ea72  jmp     loc_18001E7A3
0x18001ea77  lea     rax, [rsp+0B8h+var_60]
0x18001ea7c  mov     [rsp+0B8h+var_98], rax
0x18001ea81  mov     r9d, 1
0x18001ea87  lea     rdx, Session_CoreUICreate_InitializeCnContext_Start
0x18001ea8e  call    McGenEventWrite_EventWriteTransfer
0x18001ea93  jmp     loc_18001E7E6
0x18001ea98  call    ?GetHashCode@?$Box$1@U?$FunctionPointerAndUserData$1@P6AJPEAXK0@Z@CFlat@@@CFlat@@UEAAHXZ; CFlat::Box$1<CFlat::FunctionPointerAndUserData$1<long (*)(void *,ulong,void *)>>::GetHashCode(void)
0x18001ea9e  lea     rax, [rsp+0B8h+var_60]
0x18001eaa3  mov     [rsp+0B8h+var_98], rax
0x18001eaa8  mov     r9d, 1
0x18001eaae  lea     rdx, Session_CoreUICreate_InitializeCnContext_Stop
0x18001eab5  call    McGenEventWrite_EventWriteTransfer
0x18001eaba  jmp     loc_18001E831
0x18001eabf  mov     [rdi+4Dh], r12b
0x18001eac3  jmp     loc_18001E88A
0x18001eac8  lea     rax, [rsp+0B8h+var_40]
0x18001eacd  mov     [rsp+0B8h+var_98], rax
0x18001ead2  mov     r9d, 1
0x18001ead8  lea     rdx, Session_CoreUICreate_ExportSession_Start
0x18001eadf  call    McGenEventWrite_EventWriteTransfer
0x18001eae4  jmp     loc_18001E897
0x18001eae9  lea     rax, [rsp+0B8h+var_40]
0x18001eaee  mov     [rsp+0B8h+var_98], rax
0x18001eaf3  mov     r9d, 1
0x18001eaf9  lea     rdx, Session_CoreUICreate_ExportSession_Stop
0x18001eb00  call    McGenEventWrite_EventWriteTransfer
0x18001eb05  jmp     loc_18001E8B2
0x18001eb0a  jmp     short loc_18001EB21
0x18001eb0c  mov     rdi, qword ptr [rsp+0B8h+var_50]
0x18001eb11  mov     rcx, rdi; this
0x18001eb14  call    ?ShutdownAdapters@Context@Cn@@QEAAXXZ; Cn::Context::ShutdownAdapters(void)
0x18001eb19  call    ?Release@CoreUISession@CoreUI@Microsoft@@SAXXZ; Microsoft::CoreUI::CoreUISession::Release(void)
0x18001eb1e  nop
0x18001eb1f  jmp     short loc_18001EB26
0x18001eb21  mov     rdi, qword ptr [rsp+0B8h+var_50]
0x18001eb26  mov     r15d, dword ptr [rsp+0B8h+var_60]
0x18001eb2b  mov     r14b, [rsp+0B8h+var_88]
0x18001eb30  jmp     loc_18001E90F
0x18001eb35  test    rcx, rcx
0x18001eb38  jz      loc_18001E934
0x18001eb3e  mov     rax, [rcx]
0x18001eb41  mov     rax, [rax+10h]
0x18001eb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb4a  xor     ecx, ecx
0x18001eb4c  mov     [rsp+0B8h+var_80], rcx
0x18001eb51  jmp     loc_18001E934
0x18001eb56  test    r14b, r14b
0x18001eb59  jz      loc_18001E93F
0x18001eb5f  mov     rcx, rdi; struct Cn::Context *
0x18001eb62  call    ?UninitializeContext@Context@Cn@@SAXPEAV12@@Z; Cn::Context::UninitializeContext(Cn::Context *)
0x18001eb67  mov     rcx, [rsp+0B8h+var_80]
0x18001eb6c  jmp     loc_18001E93F
0x18001eb71  lea     rax, [rsp+0B8h+var_40]
0x18001eb76  mov     [rsp+0B8h+var_98], rax
0x18001eb7b  mov     r9d, 1
0x18001eb81  lea     rdx, Session_CoreUICreate_Stop
0x18001eb88  call    McGenEventWrite_EventWriteTransfer
0x18001eb8d  jmp     loc_18001E962
```
