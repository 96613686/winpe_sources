# ChannelBasedClientConnectionManager::CreateLowBoxChannelBasedClientConnection(ProcessIdentity const &,ushort const *,UiaClientState *,PipeReadyEventInfo const &,UIA_TIMEOUTDATA,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ChannelBasedClientConnection * *)

- ea: `0x18005ca40`
- end: `0x18005d250`
- name: `?CreateLowBoxChannelBasedClientConnection@ChannelBasedClientConnectionManager@@AEAAJAEBUProcessIdentity@@PEBGPEAVUiaClientState@@AEBVPipeReadyEventInfo@@UUIA_TIMEOUTDATA@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAVChannelBasedClientConnection@@@Z`
- size: `2064`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18005c908`

## callees

- `0x18002f580`
- `0x180034360`
- `0x18005b32c`
- `0x18005c684`
- `0x18005ca40`
- `0x18005d258`
- `0x18005d7c4`
- `0x18005d8d4`
- `0x18005dbf8`
- `0x18005ebf0`
- `0x180092df4`
- `0x180092e10`
- `0x1800948b8`
- `0x1801334b8`
- `0x1801cbe1c`
- `0x1801e887c`
- `0x1801fd9f8`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cb66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005cb66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cb7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cbc9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d1e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d22f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d1e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005d22f`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18005cbc3`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18005cbc3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cc24`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cc2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cdda`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cde3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ce66`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ce6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf27`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf80`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf89`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cff0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d060`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d069`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d0c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d0d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d148`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d151`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cc24`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cc2d`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cdda`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cde3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ce66`
- `OLEAUT32!__imp_SysFreeString` at `0x18005ce6f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf1e`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf27`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf80`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf89`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cff0`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cff9`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d060`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d069`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d0c8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d0d1`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d148`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d151`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1b7`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d1c0`

## string_xrefs

- `0x18005cbf1`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005ce25`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005cf4d`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005cfaf`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d01f`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d0f7`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d177`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ChannelBasedClientConnectionManager::CreateLowBoxChannelBasedClientConnection(
        std::_Ref_count_base *a1,
        const struct ProcessIdentity *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        HANDLE hNamedPipe)
{
  _QWORD *v10; // r12
  __m128i v11; // xmm6
  volatile signed __int32 *v12; // rdi
  int v13; // ebx
  __int64 v14; // rcx
  int v15; // eax
  unsigned int v16; // esi
  std::_Ref_count_base *EventW; // rbx
  signed int LastError; // eax
  unsigned int v19; // esi
  std::_Ref_count_base **v20; // r14
  DWORD v21; // eax
  __int64 v22; // rcx
  const char *v23; // r9
  __int64 result; // rax
  unsigned int v25; // edx
  int v26; // eax
  void *v27; // rbx
  ProcessIdentity *v28; // r8
  __int64 v29; // rdx
  _QWORD *v30; // rbx
  int v31; // eax
  unsigned __int8 v32; // si
  int v33; // r15d
  _QWORD *ClientVersionExchangePayload; // rax
  struct ChannelInfo *v35; // rcx
  int v36; // eax
  unsigned int v37; // esi
  __int64 v38; // rcx
  __int64 *CrossMachineCommunicationServices; // rax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  std::_Ref_count_base **v43; // [rsp+20h] [rbp-188h]
  int v44; // [rsp+20h] [rbp-188h]
  std::_Ref_count_base **v45; // [rsp+50h] [rbp-158h] BYREF
  struct ChannelInfo *v46; // [rsp+58h] [rbp-150h] BYREF
  int v47[2]; // [rsp+60h] [rbp-148h] BYREF
  __m128i v48; // [rsp+70h] [rbp-138h] BYREF
  __m128i v49; // [rsp+80h] [rbp-128h] BYREF
  __m128i v50; // [rsp+A0h] [rbp-108h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-F8h]
  __int64 v52; // [rsp+B8h] [rbp-F0h]
  struct _OVERLAPPED Overlapped; // [rsp+C0h] [rbp-E8h] BYREF
  char v54[160]; // [rsp+E0h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]
  std::_Ref_count_base *v56; // [rsp+1B0h] [rbp+8h] BYREF
  struct ChannelInfo *v57; // [rsp+1B8h] [rbp+10h] BYREF

  v56 = a1;
  try
  {
    v10 = hNamedPipe;
    *(_QWORD *)hNamedPipe = 0;
    hNamedPipe = 0;
    v51 = 0;
    v52 = 0;
    v57 = 0;
    v11 = 0;
    v50 = 0;
    if ( *((_BYTE *)a2 + 20) )
    {
      CrossMachineCommunicationServices = (__int64 *)BasicUtils::GetCrossMachineCommunicationServices(
                                                       &v49,
                                                       (char *)a2 + 4);
      v40 = *CrossMachineCommunicationServices;
      v12 = (volatile signed __int32 *)CrossMachineCommunicationServices[1];
      *CrossMachineCommunicationServices = 0;
      CrossMachineCommunicationServices[1] = 0;
      v50.m128i_i64[0] = v40;
      v50.m128i_i64[1] = (__int64)v12;
      a1 = (std::_Ref_count_base *)v49.m128i_i64[1];
      if ( v49.m128i_i64[1] )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v49.m128i_i64[1]);
      v11 = _mm_load_si128(&v50);
    }
    else
    {
      v12 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
    }
    hNamedPipe = 0;
    v48 = 0;
    if ( v12 )
      _InterlockedIncrement(v12 + 2);
    v48 = v11;
    v13 = ChannelBasedClientConnectionManager::CreatePipeToProvider(
            (__int64)a1,
            a3,
            a2,
            &v48,
            (__int64)&a6,
            &hNamedPipe,
            a7,
            (__int64 *)&v57);
    LOBYTE(v56) = 0;
    v15 = ChannelBasedClientConnectionManager::SignalPipeReady(v14, a5, (char *)a2 + 4, &v56);
    v16 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x493,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)v15,
        (int)v43);
      if ( v12 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
      if ( v57 )
        std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v22, v57);
      SysFreeString(0);
      SysFreeString(0);
      if ( (char *)hNamedPipe - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(hNamedPipe);
      return v16;
    }
    if ( (_BYTE)v56 )
    {
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x499,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
          (const char *)(unsigned int)v13,
          (int)v43);
        if ( v12 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
        if ( !v57 )
          goto LABEL_68;
      }
      else
      {
        EventW = (std::_Ref_count_base *)CreateEventW(0, 1, 1, 0);
        v56 = EventW;
        if ( !EventW )
        {
          LastError = GetLastError();
          v19 = LastError;
          if ( LastError > 0 )
            v19 = (unsigned __int16)LastError | 0x80070000;
          if ( (v19 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x49D,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
              (const char *)v19,
              (int)v43);
            AutoCleanupInfo<void *>::SafeRelease(&v56);
            if ( v12 )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
            if ( !v57 )
              goto LABEL_59;
            goto LABEL_58;
          }
        }
        memset(&Overlapped, 0, 24);
        Overlapped.hEvent = EventW;
        v20 = (std::_Ref_count_base **)hNamedPipe;
        ConnectNamedPipe(hNamedPipe, &Overlapped);
        v21 = GetLastError();
        if ( v21 != 997 )
        {
          if ( v21 != 535 )
          {
            v13 = Error::Win32Error(L"ConnectNamedPipe", L"Connecting to server");
            AutoCleanupInfo<void *>::SafeRelease(&v56);
            if ( v12 )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
            if ( !v57 )
              goto LABEL_68;
            goto LABEL_67;
          }
          goto LABEL_26;
        }
        v25 = 3000;
        if ( (_BYTE)a6 )
          v25 = HIDWORD(a6);
        v26 = HrWaitForSingleObject(EventW, v25);
        v13 = v26;
        if ( v26 >= 0 )
        {
LABEL_26:
          v48.m128i_i64[0] = 0;
          v27 = operator new(0x2C0u, (const struct std::nothrow_t *)std::nothrow);
          *(_QWORD *)v47 = v27;
          if ( v27 )
          {
            v45 = (std::_Ref_count_base **)&v49;
            v49 = 0;
            if ( v12 )
              _InterlockedIncrement(v12 + 2);
            v49 = v11;
            v43 = (std::_Ref_count_base **)&v49;
            v28 = ProcessIdentity::ProcessIdentity((ProcessIdentity *)v54, a2);
            v30 = (_QWORD *)ChannelBasedClientConnection::ChannelBasedClientConnection(v27, v29, v28);
          }
          else
          {
            v30 = 0;
          }
          v48.m128i_i64[0] = (__int64)v30;
          if ( v30 )
          {
            v31 = ObjectReferenceManager::Init((ObjectReferenceManager *)(v30 + 53));
            v19 = v31;
            if ( v31 >= 0 )
            {
              *(_QWORD *)v47 = 0;
              v32 = *((_BYTE *)a2 + 20);
              v33 = *(_DWORD *)a2;
              ClientVersionExchangePayload = (_QWORD *)anonymous_namespace_::MakeClientVersionExchangePayload(&v49);
              v35 = v57;
              v57 = 0;
              v46 = v35;
              v45 = v20;
              hNamedPipe = 0;
              v36 = OverlappedIOManager::AddReadWriteChannel(
                      (OverlappedIOManager *)&g_TheChannelBasedClientConnectionManager,
                      (__int64 *)&v45,
                      &v46,
                      (__int64)(v30 + 4),
                      (struct ChannelInfo **)v47,
                      ClientVersionExchangePayload,
                      1,
                      v33,
                      v32);
              v37 = v36;
              if ( v36 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x4CE,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
                  (const char *)(unsigned int)v36,
                  v44);
                (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
                AutoCleanupInfo<void *>::SafeRelease(&v56);
                if ( v12 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
                SysFreeString(0);
                SysFreeString(0);
                wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hNamedPipe);
                return v37;
              }
              else
              {
                v30[64] = *(_QWORD *)v47;
                *v10 = v30;
                AutoCleanupInfo<void *>::SafeRelease(&v56);
                if ( v12 )
                  std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
                SysFreeString(0);
                SysFreeString(0);
                return 0;
              }
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4C3,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
              (const char *)(unsigned int)v31,
              (int)v43);
            (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
            AutoCleanupInfo<void *>::SafeRelease(&v56);
            if ( v12 )
              std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
            if ( !v57 )
            {
LABEL_59:
              SysFreeString(0);
              SysFreeString(0);
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hNamedPipe);
              return v19;
            }
LABEL_58:
            std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v41, v57);
            goto LABEL_59;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4C1,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
            (const char *)0x8007000ELL,
            (int)v43);
          AutoCleanupInfo<void *>::SafeRelease(&v56);
          if ( v12 )
            std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
          if ( v57 )
            std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v38, v57);
          SysFreeString(0);
          SysFreeString(0);
          if ( (unsigned __int64)v20 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
            CloseHandle(v20);
          return 2147942414LL;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4AC,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
          (const char *)(unsigned int)v26,
          (int)v43);
        AutoCleanupInfo<void *>::SafeRelease(&v56);
        if ( v12 )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
        if ( !v57 )
          goto LABEL_68;
      }
    }
    else
    {
      v13 = Error::Win32Error(L"SetEvent", L"Creating client pipe");
      if ( v12 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v12);
      if ( !v57 )
        goto LABEL_68;
    }
LABEL_67:
    std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(v42, v57);
LABEL_68:
    SysFreeString(0);
    SysFreeString(0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hNamedPipe);
    result = (unsigned int)v13;
  }
  catch ( ... )
  {
    LODWORD(v56) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x4D4,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
                     v23);
    return (unsigned int)v56;
  }
  return result;
}

```

## disassembly

```asm
0x18005ca40  mov     rax, rsp
0x18005ca43  mov     [rax+18h], rbx
0x18005ca47  mov     [rax+20h], rsi
0x18005ca4b  mov     [rax+8], rcx
0x18005ca4f  push    rdi
0x18005ca50  push    r12
0x18005ca52  push    r13
0x18005ca54  push    r14
0x18005ca56  push    r15
0x18005ca58  sub     rsp, 180h
0x18005ca5f  movaps  xmmword ptr [rax-38h], xmm6
0x18005ca63  mov     r13, r9
0x18005ca66  mov     rbx, r8
0x18005ca69  mov     r15, rdx
0x18005ca6c  xor     r14d, r14d
0x18005ca6f  mov     r12, [rsp+1A8h+hNamedPipe]
0x18005ca77  mov     [r12], r14
0x18005ca7b  mov     [rax+40h], r14
0x18005ca7f  mov     [rax-0F8h], r14
0x18005ca86  mov     [rax-0F0h], r14
0x18005ca8d  mov     [rax+10h], r14
0x18005ca91  xorps   xmm6, xmm6
0x18005ca94  movdqa  xmmword ptr [rax-108h], xmm6
0x18005ca9c  cmp     [rdx+14h], r14b
0x18005caa0  jnz     loc_18005CE99
0x18005caa6  xorps   xmm0, xmm0
0x18005caa9  psrldq  xmm0, 8
0x18005caae  movq    rdi, xmm0
0x18005cab3  mov     [rsp+1A8h+hNamedPipe], r14
0x18005cabb  xorps   xmm0, xmm0
0x18005cabe  movdqa  [rsp+1A8h+var_138], xmm0
0x18005cac4  test    rdi, rdi
0x18005cac7  jz      short loc_18005CACD
0x18005cac9  lock inc dword ptr [rdi+8]
0x18005cacd  movdqa  [rsp+1A8h+var_138], xmm6
0x18005cad3  lea     rax, [rsp+1A8h+arg_8]
0x18005cadb  mov     [rsp+1A8h+var_170], rax
0x18005cae0  mov     rax, [rsp+1A8h+arg_30]
0x18005cae8  mov     [rsp+1A8h+var_178], rax
0x18005caed  lea     rax, [rsp+1A8h+hNamedPipe]
0x18005caf5  mov     [rsp+1A8h+var_180], rax
0x18005cafa  lea     rax, [rsp+1A8h+arg_28]
0x18005cb02  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x18005cb07  lea     r9, [rsp+1A8h+var_138]
0x18005cb0c  mov     r8, r15
0x18005cb0f  mov     rdx, rbx
0x18005cb12  call    ?CreatePipeToProvider@ChannelBasedClientConnectionManager@@AEAAJPEBGAEBUProcessIdentity@@V?$shared_ptr@VICrossMachineCommunicationServices@@@std@@AEAUUIA_TIMEOUTDATA@@PEAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAV?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@4@@Z; ChannelBasedClientConnectionManager::CreatePipeToProvider(ushort const *,ProcessIdentity const &,std::shared_ptr<ICrossMachineCommunicationServices>,UIA_TIMEOUTDATA &,void * *,std::wstring const &,std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard> *)
0x18005cb17  mov     ebx, eax
0x18005cb19  mov     byte ptr [rsp+1A8h+arg_0], r14b
0x18005cb21  lea     r9, [rsp+1A8h+arg_0]
0x18005cb29  lea     r8, [r15+4]
0x18005cb2d  mov     rdx, [rsp+1A8h+arg_20]
0x18005cb35  call    ?SignalPipeReady@ChannelBasedClientConnectionManager@@AEAAJAEBVPipeReadyEventInfo@@AEBV?$optional@U_GUID@@@std@@PEA_N@Z; ChannelBasedClientConnectionManager::SignalPipeReady(PipeReadyEventInfo const &,std::optional<_GUID> const &,bool *)
0x18005cb3a  mov     esi, eax
0x18005cb3c  test    eax, eax
0x18005cb3e  js      loc_18005CBE6
0x18005cb44  cmp     byte ptr [rsp+1A8h+arg_0], r14b
0x18005cb4c  jz      loc_18005CEE8
0x18005cb52  test    ebx, ebx
0x18005cb54  js      loc_18005CF42
0x18005cb5a  xor     r9d, r9d; lpName
0x18005cb5d  lea     edx, [r9+1]; bManualReset
0x18005cb61  xor     ecx, ecx; lpEventAttributes
0x18005cb63  mov     r8d, edx; bInitialState
0x18005cb66  call    cs:__imp_CreateEventW
0x18005cb6c  mov     rbx, rax
0x18005cb6f  mov     [rsp+1A8h+arg_0], rax
0x18005cb77  test    rax, rax
0x18005cb7a  jnz     short loc_18005CB94
0x18005cb7c  call    cs:__imp_GetLastError
0x18005cb82  mov     esi, eax
0x18005cb84  test    eax, eax
0x18005cb86  jg      loc_18005CE8B
0x18005cb8c  test    esi, esi
0x18005cb8e  js      loc_18005CFA4
0x18005cb94  mov     [rsp+1A8h+Overlapped.Internal], r14
0x18005cb9c  xorps   xmm0, xmm0
0x18005cb9f  movdqu  xmmword ptr [rsp+1A8h+Overlapped.InternalHigh], xmm0
0x18005cba8  mov     [rsp+1A8h+Overlapped.hEvent], rbx
0x18005cbb0  lea     rdx, [rsp+1A8h+Overlapped]; lpOverlapped
0x18005cbb8  mov     r14, [rsp+1A8h+hNamedPipe]
0x18005cbc0  mov     rcx, r14; hNamedPipe
0x18005cbc3  call    cs:__imp_ConnectNamedPipe
0x18005cbc9  call    cs:__imp_GetLastError
0x18005cbcf  cmp     eax, 3E5h
0x18005cbd4  jz      short loc_18005CC51
0x18005cbd6  cmp     eax, 217h
0x18005cbdb  jz      loc_18005CC78
0x18005cbe1  jmp     loc_18005D084
0x18005cbe6  mov     rcx, [rsp+1A8h]; this
0x18005cbee  mov     r9d, esi; char *
0x18005cbf1  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005cbf8  mov     edx, 493h; void *
0x18005cbfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cc02  nop
0x18005cc03  test    rdi, rdi
0x18005cc06  jz      short loc_18005CC11
0x18005cc08  mov     rcx, rdi; this
0x18005cc0b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005cc10  nop
0x18005cc11  mov     rdx, [rsp+1A8h+arg_8]
0x18005cc19  test    rdx, rdx
0x18005cc1c  jnz     loc_18005D1DB
0x18005cc22  xor     ecx, ecx; bstrString
0x18005cc24  call    cs:__imp_SysFreeString
0x18005cc2a  nop
0x18005cc2b  xor     ecx, ecx; bstrString
0x18005cc2d  call    cs:__imp_SysFreeString
0x18005cc33  nop
0x18005cc34  mov     rcx, [rsp+1A8h+hNamedPipe]; hObject
0x18005cc3c  lea     rax, [rcx-1]
0x18005cc40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005cc44  jbe     loc_18005D1E5
0x18005cc4a  mov     eax, esi
0x18005cc4c  jmp     loc_18005CDEC
0x18005cc51  mov     edx, 0BB8h
0x18005cc56  cmp     byte ptr [rsp+1A8h+arg_28], 0
0x18005cc5e  cmovnz  edx, [rsp+1A8h+arg_2C]; unsigned int
0x18005cc66  mov     rcx, rbx; void *
0x18005cc69  call    ?HrWaitForSingleObject@@YAJPEAXK@Z; HrWaitForSingleObject(void *,ulong)
0x18005cc6e  mov     ebx, eax
0x18005cc70  test    eax, eax
0x18005cc72  js      loc_18005D014
0x18005cc78  mov     qword ptr [rsp+1A8h+var_138], 0
0x18005cc81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18005cc88  mov     ecx, 2C0h; unsigned __int64
0x18005cc8d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18005cc92  mov     rbx, rax
0x18005cc95  mov     qword ptr [rsp+1A8h+var_148], rax
0x18005cc9a  test    rax, rax
0x18005cc9d  jz      loc_18005CE0E
0x18005cca3  lea     rax, [rsp+1A8h+var_128]
0x18005ccab  mov     [rsp+1A8h+var_158], rax
0x18005ccb0  xorps   xmm0, xmm0
0x18005ccb3  movdqa  [rsp+1A8h+var_128], xmm0
0x18005ccbc  test    rdi, rdi
0x18005ccbf  jz      short loc_18005CCC5
0x18005ccc1  lock inc dword ptr [rdi+8]
0x18005ccc5  movdqa  [rsp+1A8h+var_128], xmm6
0x18005ccce  mov     rdx, r15; struct ProcessIdentity *
0x18005ccd1  lea     rcx, [rsp+1A8h+var_C8]; this
0x18005ccd9  call    ??0ProcessIdentity@@QEAA@AEBU0@@Z; ProcessIdentity::ProcessIdentity(ProcessIdentity const &)
0x18005ccde  nop
0x18005ccdf  mov     [rsp+1A8h+var_180], r13
0x18005cce4  lea     rcx, [rsp+1A8h+var_128]
0x18005ccec  mov     qword ptr [rsp+1A8h+var_188], rcx; int
0x18005ccf1  mov     r8, rax
0x18005ccf4  mov     rcx, rbx
0x18005ccf7  call    ??0ChannelBasedClientConnection@@QEAA@PEAVChannelBasedClientConnectionManager@@UProcessIdentity@@PEAUHWND__@@V?$shared_ptr@VICrossMachineCommunicationServices@@@std@@PEAVUiaClientState@@@Z; ChannelBasedClientConnection::ChannelBasedClientConnection(ChannelBasedClientConnectionManager *,ProcessIdentity,HWND__ *,std::shared_ptr<ICrossMachineCommunicationServices>,UiaClientState *)
0x18005ccfc  mov     rbx, rax
0x18005ccff  mov     qword ptr [rsp+1A8h+var_138], rbx
0x18005cd04  test    rbx, rbx
0x18005cd07  jz      loc_18005CE15
0x18005cd0d  lea     rcx, [rbx+1A8h]; this
0x18005cd14  call    ?Init@ObjectReferenceManager@@QEAAJXZ; ObjectReferenceManager::Init(void)
0x18005cd19  mov     esi, eax
0x18005cd1b  test    eax, eax
0x18005cd1d  js      loc_18005D0EC
0x18005cd23  mov     qword ptr [rsp+1A8h+var_148], 0
0x18005cd2c  mov     sil, [r15+14h]
0x18005cd30  mov     r15d, [r15]
0x18005cd33  lea     rcx, [rsp+1A8h+var_128]
0x18005cd3b  call    _anonymous_namespace___MakeClientVersionExchangePayload
0x18005cd40  mov     rcx, [rsp+1A8h+arg_8]
0x18005cd48  mov     [rsp+1A8h+arg_8], 0
0x18005cd54  mov     [rsp+1A8h+var_150], rcx
0x18005cd59  mov     [rsp+1A8h+var_158], r14
0x18005cd5e  mov     [rsp+1A8h+hNamedPipe], 0
0x18005cd6a  lea     r9, [rbx+20h]
0x18005cd6e  mov     [rsp+1A8h+var_168], sil
0x18005cd73  mov     dword ptr [rsp+1A8h+var_170], r15d
0x18005cd78  mov     byte ptr [rsp+1A8h+var_178], 1
0x18005cd7d  mov     [rsp+1A8h+var_180], rax
0x18005cd82  lea     rax, [rsp+1A8h+var_148]
0x18005cd87  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x18005cd8c  lea     r8, [rsp+1A8h+var_150]
0x18005cd91  lea     rdx, [rsp+1A8h+var_158]
0x18005cd96  lea     rcx, ?g_TheChannelBasedClientConnectionManager@@3VChannelBasedClientConnectionManager@@A; ChannelBasedClientConnectionManager g_TheChannelBasedClientConnectionManager
0x18005cd9d  call    ?AddReadWriteChannel@OverlappedIOManager@@QEAAJV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@std@@PEAUIReadWriteChannelCallback@@PEAPEAUIReadWriteChannel@@V?$vector@EV?$allocator@E@std@@@5@_NI5@Z; OverlappedIOManager::AddReadWriteChannel(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>,IReadWriteChannelCallback *,IReadWriteChannel * *,std::vector<uchar>,bool,uint,bool)
0x18005cda2  mov     esi, eax
0x18005cda4  test    eax, eax
0x18005cda6  js      loc_18005D16C
0x18005cdac  mov     rax, qword ptr [rsp+1A8h+var_148]
0x18005cdb1  mov     [rbx+200h], rax
0x18005cdb8  mov     [r12], rbx
0x18005cdbc  lea     rcx, [rsp+1A8h+arg_0]
0x18005cdc4  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18005cdc9  nop
0x18005cdca  test    rdi, rdi
0x18005cdcd  jz      short loc_18005CDD8
0x18005cdcf  mov     rcx, rdi; this
0x18005cdd2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005cdd7  nop
0x18005cdd8  xor     ecx, ecx; bstrString
0x18005cdda  call    cs:__imp_SysFreeString
0x18005cde0  nop
0x18005cde1  xor     ecx, ecx; bstrString
0x18005cde3  call    cs:__imp_SysFreeString
0x18005cde9  nop
0x18005cdea  xor     eax, eax
0x18005cdec  lea     r11, [rsp+1A8h+var_28]
0x18005cdf4  mov     rbx, [r11+40h]
0x18005cdf8  mov     rsi, [r11+48h]
0x18005cdfc  movaps  xmm6, xmmword ptr [r11-10h]
0x18005ce01  mov     rsp, r11
0x18005ce04  pop     r15
0x18005ce06  pop     r14
0x18005ce08  pop     r13
0x18005ce0a  pop     r12
0x18005ce0c  pop     rdi
0x18005ce0d  retn
0x18005ce0e  xor     ebx, ebx
0x18005ce10  jmp     loc_18005CCFF
0x18005ce15  mov     rcx, [rsp+1A8h]; this
0x18005ce1d  mov     ebx, 8007000Eh
0x18005ce22  mov     r9d, ebx; char *
0x18005ce25  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005ce2c  mov     edx, 4C1h; void *
0x18005ce31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ce36  nop
0x18005ce37  lea     rcx, [rsp+1A8h+arg_0]
0x18005ce3f  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18005ce44  nop
0x18005ce45  test    rdi, rdi
0x18005ce48  jz      short loc_18005CE53
0x18005ce4a  mov     rcx, rdi; this
0x18005ce4d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ce52  nop
0x18005ce53  mov     rdx, [rsp+1A8h+arg_8]
0x18005ce5b  test    rdx, rdx
0x18005ce5e  jnz     loc_18005D222
0x18005ce64  xor     ecx, ecx; bstrString
0x18005ce66  call    cs:__imp_SysFreeString
0x18005ce6c  nop
0x18005ce6d  xor     ecx, ecx; bstrString
0x18005ce6f  call    cs:__imp_SysFreeString
0x18005ce75  nop
0x18005ce76  lea     rdx, [r14-1]
0x18005ce7a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18005ce7e  jbe     loc_18005D22C
0x18005ce84  mov     eax, ebx
0x18005ce86  jmp     loc_18005CDEC
0x18005ce8b  movzx   esi, ax
0x18005ce8e  or      esi, 80070000h
0x18005ce94  jmp     loc_18005CB8C
0x18005ce99  add     rdx, 4
0x18005ce9d  lea     rcx, [rsp+1A8h+var_128]
0x18005cea5  call    ?GetCrossMachineCommunicationServices@BasicUtils@@SA?AV?$shared_ptr@VICrossMachineCommunicationServices@@@std@@AEBU_GUID@@@Z; BasicUtils::GetCrossMachineCommunicationServices(_GUID const &)
0x18005ceaa  mov     rcx, [rax]
0x18005cead  mov     rdi, [rax+8]
0x18005ceb1  mov     [rax], r14
0x18005ceb4  mov     [rax+8], r14
0x18005ceb8  mov     qword ptr [rsp+1A8h+var_108], rcx
0x18005cec0  mov     qword ptr [rsp+1A8h+var_108+8], rdi
0x18005cec8  mov     rcx, qword ptr [rsp+1A8h+var_128+8]; this
0x18005ced0  test    rcx, rcx
0x18005ced3  jz      short loc_18005CEDA
0x18005ced5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005ceda  movdqa  xmm6, [rsp+1A8h+var_108]
0x18005cee3  jmp     loc_18005CAB3
0x18005cee8  lea     rdx, aCreatingClient; "Creating client pipe"
0x18005ceef  lea     rcx, aSetevent; "SetEvent"
0x18005cef6  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x18005cefb  mov     ebx, eax
0x18005cefd  test    rdi, rdi
0x18005cf00  jz      short loc_18005CF0B
0x18005cf02  mov     rcx, rdi; this
0x18005cf05  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005cf0a  nop
0x18005cf0b  mov     rdx, [rsp+1A8h+arg_8]
0x18005cf13  test    rdx, rdx
0x18005cf16  jnz     loc_18005D1F0
0x18005cf1c  xor     ecx, ecx; bstrString
0x18005cf1e  call    cs:__imp_SysFreeString
0x18005cf24  nop
0x18005cf25  xor     ecx, ecx; bstrString
0x18005cf27  call    cs:__imp_SysFreeString
0x18005cf2d  nop
0x18005cf2e  lea     rcx, [rsp+1A8h+hNamedPipe]
0x18005cf36  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005cf3b  mov     eax, ebx
0x18005cf3d  jmp     loc_18005CDEC
0x18005cf42  mov     rcx, [rsp+1A8h]; this
0x18005cf4a  mov     r9d, ebx; char *
0x18005cf4d  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005cf54  mov     edx, 499h; void *
0x18005cf59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cf5e  nop
0x18005cf5f  test    rdi, rdi
0x18005cf62  jz      short loc_18005CF6D
0x18005cf64  mov     rcx, rdi; this
0x18005cf67  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005cf6c  nop
0x18005cf6d  mov     rdx, [rsp+1A8h+arg_8]
0x18005cf75  test    rdx, rdx
0x18005cf78  jnz     loc_18005D1FA
0x18005cf7e  xor     ecx, ecx; bstrString
0x18005cf80  call    cs:__imp_SysFreeString
0x18005cf86  nop
0x18005cf87  xor     ecx, ecx; bstrString
  ... truncated ...
```
