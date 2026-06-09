# SharingPlatform::Internal::CDPListener::OnParticipantJoined(ICDPParticipant *)

- ea: `0x180011160`
- end: `0x1800112d1`
- name: `?OnParticipantJoined@CDPListener@Internal@SharingPlatform@@UEAAJPEAVICDPParticipant@@@Z`
- size: `369`
- prototype: `__int64 __fastcall(SharingPlatform::Internal::CDPListener *__hidden this, struct ICDPParticipant *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x18000a580`
- `0x180011160`
- `0x1800130ec`
- `0x180018490`
- `0x18004a640`
- `0x18005e510`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112be`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011214`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800112be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800111b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800111b8`
- `cdp!CDPCreateDeviceInternal` at `0x18001123c`
- `cdp!CDPCreateDeviceInternal` at `0x18001123c`

## pseudocode

```c
__int64 __fastcall SharingPlatform::Internal::CDPListener::OnParticipantJoined(
        SharingPlatform::Internal::CDPListener *this,
        struct ICDPParticipant *a2)
{
  __int64 v4; // rbx
  unsigned __int64 v5; // rdx
  unsigned __int8 v6; // cl
  __int64 v7; // rcx
  RemoteSessionTraceProvider *v8; // rax
  __int64 v9; // rax
  __int64 (__fastcall *v10)(struct ICDPParticipant *, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  int v14; // eax
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  RemoteSessionTraceProvider *v18; // rax
  int v19[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF
  __int64 v22; // [rsp+68h] [rbp+38h] BYREF
  __int64 v23; // [rsp+70h] [rbp+40h] BYREF

  v4 = (*(__int64 (__fastcall **)(struct ICDPParticipant *))(*(_QWORD *)a2 + 24LL))(a2);
  v23 = v4;
  if ( RemoteSessionTraceProvider::IsEnabled(v6, v5) )
  {
    v8 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                         v7,
                                         _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
    RemoteSessionTraceProvider::LogVerbose_(v8, L"CDPListener::OnParticipantJoined sessionId:%llx", v4);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v9 = *(_QWORD *)a2;
  v21 = 0;
  v10 = *(__int64 (__fastcall **)(struct ICDPParticipant *, __int64 *))(v9 + 56);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
  v11 = v10(a2, &v21);
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)".\\cdplistener.cpp",
      (const char *)(unsigned int)v11,
      v19[0]);
LABEL_5:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
    if ( this != (SharingPlatform::Internal::CDPListener *)-32LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    return v12;
  }
  v22 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v22);
  v14 = CDPCreateDeviceInternal(v21, 0, &v22);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE3,
      (unsigned int)".\\cdplistener.cpp",
      (const char *)(unsigned int)v14,
      v19[0]);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v22);
    goto LABEL_5;
  }
  std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<ICDPDevice>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>,0>>::_Emplace<unsigned __int64 &,Microsoft::WRL::ComPtr<ICDPDevice>>(
    (__int64 *)this + 11,
    (__int64)v19,
    (__int64)&v23);
  if ( RemoteSessionTraceProvider::IsEnabled(v16, v15) )
  {
    v18 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                          v17,
                                          _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
    RemoteSessionTraceProvider::LogVerbose_(v18, L"CDPListener::OnParticipantJoined");
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
  if ( this != (SharingPlatform::Internal::CDPListener *)-32LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return 0;
}

```

## disassembly

```asm
0x180011160  push    rbp
0x180011162  push    rbx
0x180011163  push    rsi
0x180011164  push    rdi
0x180011165  push    r14
0x180011167  mov     rbp, rsp
0x18001116a  sub     rsp, 30h
0x18001116e  mov     rax, [rdx]
0x180011171  mov     r14, rcx
0x180011174  mov     rcx, rdx
0x180011177  mov     rsi, rdx
0x18001117a  mov     rax, [rax+18h]
0x18001117e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011183  mov     rbx, rax
0x180011186  mov     [rbp+arg_10], rax
0x18001118a  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18001118f  test    al, al
0x180011191  jz      short loc_1800111B1
0x180011193  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18001119a  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x18001119f  mov     r8, rbx
0x1800111a2  lea     rdx, aCdplistenerOnp; "CDPListener::OnParticipantJoined sessio"...
0x1800111a9  mov     rcx, rax; this
0x1800111ac  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x1800111b1  lea     rdi, [r14+20h]
0x1800111b5  mov     rcx, rdi; lpCriticalSection
0x1800111b8  call    cs:__imp_EnterCriticalSection
0x1800111be  mov     rax, [rsi]
0x1800111c1  lea     rcx, [rbp+arg_0]
0x1800111c5  mov     [rbp+arg_0], 0
0x1800111cd  mov     rbx, [rax+38h]
0x1800111d1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800111d6  lea     rdx, [rbp+arg_0]
0x1800111da  mov     rcx, rsi
0x1800111dd  mov     rax, rbx
0x1800111e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111e5  mov     ebx, eax
0x1800111e7  test    eax, eax
0x1800111e9  jns     short loc_180011221
0x1800111eb  mov     rcx, [rbp+28h]; this
0x1800111ef  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800111f6  mov     r9d, eax; char *
0x1800111f9  mov     edx, 0D7h; void *
0x1800111fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011203  lea     rcx, [rbp+arg_0]
0x180011207  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001120c  test    rdi, rdi
0x18001120f  jz      short loc_18001121A
0x180011211  mov     rcx, rdi; lpCriticalSection
0x180011214  call    cs:__imp_LeaveCriticalSection
0x18001121a  mov     eax, ebx
0x18001121c  jmp     loc_1800112C6
0x180011221  lea     rcx, [rbp+arg_8]
0x180011225  mov     [rbp+arg_8], 0
0x18001122d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180011232  mov     rcx, [rbp+arg_0]
0x180011236  lea     r8, [rbp+arg_8]
0x18001123a  xor     edx, edx
0x18001123c  call    cs:__imp_CDPCreateDeviceInternal
0x180011242  mov     ebx, eax
0x180011244  test    eax, eax
0x180011246  jns     short loc_18001126B
0x180011248  mov     rcx, [rbp+28h]; this
0x18001124c  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180011253  mov     r9d, eax; char *
0x180011256  mov     edx, 0E3h; void *
0x18001125b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011260  lea     rcx, [rbp+arg_8]
0x180011264  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180011269  jmp     short loc_180011203
0x18001126b  lea     rcx, [r14+58h]
0x18001126f  lea     r9, [rbp+arg_8]
0x180011273  lea     r8, [rbp+arg_10]
0x180011277  lea     rdx, [rbp+var_10]
0x18001127b  call    ??$_Emplace@AEA_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@AEA_K$$QEAV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<ICDPDevice>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>,0>>::_Emplace<unsigned __int64 &,Microsoft::WRL::ComPtr<ICDPDevice>>(unsigned __int64 &,Microsoft::WRL::ComPtr<ICDPDevice> &&)
0x180011280  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180011285  test    al, al
0x180011287  jz      short loc_1800112A4
0x180011289  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180011290  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180011295  lea     rdx, aCdplistenerOnp_0; "CDPListener::OnParticipantJoined"
0x18001129c  mov     rcx, rax; this
0x18001129f  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x1800112a4  lea     rcx, [rbp+arg_8]
0x1800112a8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800112ad  lea     rcx, [rbp+arg_0]
0x1800112b1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800112b6  test    rdi, rdi
0x1800112b9  jz      short loc_1800112C4
0x1800112bb  mov     rcx, rdi; lpCriticalSection
0x1800112be  call    cs:__imp_LeaveCriticalSection
0x1800112c4  xor     eax, eax
0x1800112c6  add     rsp, 30h
0x1800112ca  pop     r14
0x1800112cc  pop     rdi
0x1800112cd  pop     rsi
0x1800112ce  pop     rbx
0x1800112cf  pop     rbp
0x1800112d0  retn
```
