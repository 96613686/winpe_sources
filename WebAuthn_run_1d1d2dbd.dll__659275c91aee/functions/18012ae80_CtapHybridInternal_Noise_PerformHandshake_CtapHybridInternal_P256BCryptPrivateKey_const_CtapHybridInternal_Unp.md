# CtapHybridInternal::Noise::PerformHandshake(CtapHybridInternal::P256BCryptPrivateKey const &,CtapHybridInternal::UnpackedAdvertisementData const &,CtapHybridInternal::QrSymetricSecret const &)

- ea: `0x18012ae80`
- end: `0x18012b25a`
- name: `?PerformHandshake@Noise@CtapHybridInternal@@QEAAXAEBUP256BCryptPrivateKey@2@AEBUUnpackedAdvertisementData@2@AEBUQrSymetricSecret@2@@Z`
- size: `986`
- prototype: `void(CtapHybridInternal::Noise *__hidden this, const struct CtapHybridInternal::P256BCryptPrivateKey *, const struct CtapHybridInternal::UnpackedAdvertisementData *, const struct CtapHybridInternal::QrSymetricSecret *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180107524`

## callees

- `0x180017724`
- `0x180023264`
- `0x180023b2c`
- `0x1800241a4`
- `0x18003164c`
- `0x1800350b4`
- `0x18003ac98`
- `0x18003acb8`
- `0x1800472cc`
- `0x18004aa68`
- `0x18006b260`
- `0x18009359c`
- `0x180106c0c`
- `0x180108ff8`
- `0x18010efb4`
- `0x18012a1b8`
- `0x18012a390`
- `0x18012a404`
- `0x18012ae80`
- `0x18012b260`
- `0x18012bff8`
- `0x18012ce98`
- `0x18012d32c`
- `0x18013c090`

## import_xrefs

- `noise!NoiseCloseHandle` at `0x18012b0f3`
- `noise!NoiseCloseHandle` at `0x18012b0f3`
- `noise!NoiseOpenHandle` at `0x18012b10d`
- `noise!NoiseOpenHandle` at `0x18012b10d`
- `noise!NoiseHandshakeInitialize` at `0x18012b1be`
- `noise!NoiseHandshakeInitialize` at `0x18012b1be`
- `bcrypt!BCryptImportKeyPair` at `0x18012b0b5`
- `bcrypt!BCryptImportKeyPair` at `0x18012b0b5`

## string_xrefs

- `0x18012b0c9`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012b121`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012b1d2`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall CtapHybridInternal::Noise::PerformHandshake(
        CtapHybridInternal::Noise *this,
        UCHAR *a2,
        const struct CtapHybridInternal::UnpackedAdvertisementData *a3,
        const struct CtapHybridInternal::QrSymetricSecret *a4)
{
  char *v8; // rcx
  __int64 v9; // rdx
  __int128 v10; // xmm0
  const struct CtapHybridInternal::QrSymetricSecret *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rax
  NTSTATUS v14; // eax
  struct NOISE_HANDLE__ **v15; // rbx
  struct NOISE_HANDLE__ *v16; // rdi
  int v17; // eax
  int v18; // eax
  int pbInput; // [rsp+20h] [rbp-E0h]
  int pbInputa; // [rsp+20h] [rbp-E0h]
  char v21; // [rsp+70h] [rbp-90h] BYREF
  char v22; // [rsp+71h] [rbp-8Fh] BYREF
  char *v23; // [rsp+80h] [rbp-80h] BYREF
  __int64 v24; // [rsp+88h] [rbp-78h]
  const struct CtapHybridInternal::QrSymetricSecret *v25; // [rsp+90h] [rbp-70h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  char v27[8]; // [rsp+A0h] [rbp-60h] BYREF
  char v28[8]; // [rsp+A8h] [rbp-58h] BYREF
  char v29[8]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int8 *v30; // [rsp+B8h] [rbp-48h] BYREF
  int v31; // [rsp+C0h] [rbp-40h]
  unsigned __int8 *v32; // [rsp+D0h] [rbp-30h] BYREF
  int v33; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall *v34)(); // [rsp+E8h] [rbp-18h] BYREF
  char v35; // [rsp+F0h] [rbp-10h]
  char v36; // [rsp+F1h] [rbp-Fh]
  __int128 v37; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall *v38)(); // [rsp+108h] [rbp+8h] BYREF
  char v39; // [rsp+110h] [rbp+10h]
  char v40; // [rsp+111h] [rbp+11h]
  __int128 v41; // [rsp+118h] [rbp+18h]
  _QWORD v42[2]; // [rsp+128h] [rbp+28h] BYREF
  char v43; // [rsp+138h] [rbp+38h]
  char v44; // [rsp+139h] [rbp+39h]
  char *v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]
  _QWORD *v47; // [rsp+160h] [rbp+60h]
  _QWORD v48[2]; // [rsp+168h] [rbp+68h] BYREF
  char v49; // [rsp+178h] [rbp+78h]
  char v50; // [rsp+179h] [rbp+79h]
  const struct CtapHybridInternal::QrSymetricSecret *v51; // [rsp+180h] [rbp+80h]
  __int64 v52; // [rsp+188h] [rbp+88h]
  _QWORD *v53; // [rsp+1A0h] [rbp+A0h]
  _BYTE v54[24]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v55[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v56[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v57[32]; // [rsp+200h] [rbp+100h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  CtapHybridInternal::BuildWebSocketUrlToTunnelService(v56, a3, a4);
  v55[0] = *(_QWORD *)winrt::to_hstring<std::string,0>(v28, v56);
  winrt::Windows::Foundation::Uri::Uri(
    (winrt::Windows::Foundation::Uri *)v29,
    (const struct winrt::param::hstring *)v55);
  winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
  std::string::string(v57);
  std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(&v23, this);
  v38 = CtapHybridInternal::SocketClosedHandler;
  v8 = v23;
  v9 = v24;
  v23 = 0;
  v24 = 0;
  v42[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs>::`vftable';
  v42[1] = CtapHybridInternal::SocketClosedHandler;
  v43 = v39;
  v44 = v40;
  v45 = v8;
  v46 = v9;
  v10 = 0;
  v41 = 0;
  v47 = v42;
  *(double *)&v10 = std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(&v25, this);
  v34 = CtapHybridInternal::MessageReceivedHandler;
  v11 = v25;
  v12 = v26;
  v25 = 0;
  v26 = 0;
  v48[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs>::`vftable';
  v48[1] = CtapHybridInternal::MessageReceivedHandler;
  v49 = v35;
  v50 = v36;
  v51 = v11;
  v52 = v12;
  v37 = v10;
  v53 = v48;
  v13 = CtapHybridInternal::ConnectToTunnelServiceCancellable(
          (unsigned int)v27,
          *((_QWORD *)this + 32),
          (unsigned int)v56,
          (unsigned int)v48,
          (__int64)v42,
          (__int64)v57);
  winrt::Windows::Foundation::IUnknown::operator=((char *)this + 24, v13);
  winrt::Windows::Foundation::Collections::IVector<unsigned char>::~IVector<unsigned char>(v27);
  std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(&v34);
  std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(&v38);
  std::string::_Tidy_deallocate(v57);
  *((_BYTE *)this + 16) = 0;
  *((_BYTE *)this + 264) = 1;
  v23 = (char *)a3;
  v24 = 16;
  v25 = a4;
  v26 = 16;
  CtapHybridInternal::DeriveHKDFKey(
    (unsigned int)&v32,
    32,
    (unsigned int)&v25,
    (unsigned int)&v23,
    (__int64)&CtapHybridInternal::c_keyPurposePSK);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    0);
  v14 = BCryptImportKeyPair((BCRYPT_ALG_HANDLE)0x2A1, 0, L"ECCPRIVATEBLOB", (BCRYPT_KEY_HANDLE *)this + 5, a2, 0x68u, 0);
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v14,
      pbInput);
  v15 = (struct NOISE_HANDLE__ **)((char *)this + 32);
  v16 = (struct NOISE_HANDLE__ *)*((_QWORD *)this + 4);
  if ( v16 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v27);
    NoiseCloseHandle(v16);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v27);
  }
  *v15 = 0;
  v17 = NoiseOpenHandle((struct NOISE_HANDLE__ **)this + 4);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v17,
      pbInput);
  v21 = 1;
  v23 = &v21;
  v24 = (__int64)&v22;
  std::vector<unsigned char>::vector<unsigned char>(&v30, &v23);
  v18 = NoiseHandshakeInitialize(
          *v15,
          L"ECDH_P256",
          (void *const)0x1E1,
          L"SHA256",
          L"KNpsk0",
          1,
          v30,
          v31 - (_DWORD)v30,
          *((void *const *)this + 5),
          0,
          0,
          v32,
          v33 - (_DWORD)v32);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v18,
      pbInputa);
  CtapHybridInternal::Noise::ProcessHandshakeMessage(this, v54);
  CtapHybridInternal::Noise::WriteMessageInSocket(this, v54);
  std::vector<unsigned char>::_Tidy(v54);
  std::vector<unsigned char>::_Tidy(&v30);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v32);
  winrt::Windows::Foundation::Collections::IVector<unsigned char>::~IVector<unsigned char>(v29);
  std::string::_Tidy_deallocate(v56);
}

```

## disassembly

```asm
0x18012ae80  push    rbp
0x18012ae82  push    rbx
0x18012ae83  push    rsi
0x18012ae84  push    rdi
0x18012ae85  push    r14
0x18012ae87  push    r15
0x18012ae89  lea     rbp, [rsp-138h]
0x18012ae91  sub     rsp, 238h
0x18012ae98  mov     rax, cs:__security_cookie
0x18012ae9f  xor     rax, rsp
0x18012aea2  mov     [rbp+160h+var_40], rax
0x18012aea9  mov     rdi, r9
0x18012aeac  mov     rbx, r8
0x18012aeaf  mov     rsi, rdx
0x18012aeb2  mov     r14, rcx
0x18012aeb5  mov     r8, r9
0x18012aeb8  mov     rdx, rbx
0x18012aebb  lea     rcx, [rbp+160h+var_80]
0x18012aec2  call    ?BuildWebSocketUrlToTunnelService@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUUnpackedAdvertisementData@1@AEBUQrSymetricSecret@1@@Z; CtapHybridInternal::BuildWebSocketUrlToTunnelService(CtapHybridInternal::UnpackedAdvertisementData const &,CtapHybridInternal::QrSymetricSecret const &)
0x18012aec7  nop
0x18012aec8  lea     rdx, [rbp+160h+var_80]
0x18012aecf  lea     rcx, [rbp+160h+var_1B8]
0x18012aed3  call    ??$to_hstring@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$0A@@winrt@@YA?AUhstring@0@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; winrt::to_hstring<std::string,0>(std::string const &)
0x18012aed8  nop
0x18012aed9  mov     rax, [rax]
0x18012aedc  mov     [rbp+160h+var_A0], rax
0x18012aee3  lea     rdx, [rbp+160h+var_A0]; struct winrt::param::hstring *
0x18012aeea  lea     rcx, [rbp+160h+var_1B0]; this
0x18012aeee  call    ??0Uri@Foundation@Windows@winrt@@QEAA@AEBUhstring@param@3@@Z; winrt::Windows::Foundation::Uri::Uri(winrt::param::hstring const &)
0x18012aef3  nop
0x18012aef4  lea     rcx, [rbp+160h+var_1B8]
0x18012aef8  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18012aefd  lea     rcx, [rbp+160h+var_60]
0x18012af04  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18012af09  nop
0x18012af0a  mov     rdx, r14
0x18012af0d  lea     rcx, [rbp+160h+var_1E0]
0x18012af11  call    ??$?0UCredentialInfo@@$0A@@?$weak_ptr@UCredentialInfo@@@std@@QEAA@AEBV?$shared_ptr@UCredentialInfo@@@1@@Z; std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(std::shared_ptr<CredentialInfo> const &)
0x18012af16  nop
0x18012af17  lea     r8, ?SocketClosedHandler@CtapHybridInternal@@YAXV?$weak_ptr@VNoise@CtapHybridInternal@@@std@@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@Z; CtapHybridInternal::SocketClosedHandler(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs)
0x18012af1e  mov     [rbp+160h+var_158], r8
0x18012af22  mov     rcx, [rbp+160h+var_1E0]
0x18012af26  mov     rdx, [rbp+160h+var_1D8]
0x18012af2a  mov     [rbp+160h+var_1E0], 0
0x18012af32  mov     [rbp+160h+var_1D8], 0
0x18012af3a  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@XUIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@4567@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs>::`vftable'
0x18012af41  mov     [rbp+160h+var_138], rax
0x18012af45  mov     [rbp+160h+var_130], r8
0x18012af49  mov     al, [rbp+160h+var_150]
0x18012af4c  mov     [rbp+160h+var_128], al
0x18012af4f  mov     al, [rbp+160h+var_14F]
0x18012af52  mov     [rbp+160h+var_127], al
0x18012af55  mov     [rbp+160h+var_120], rcx
0x18012af59  mov     [rbp+160h+var_118], rdx
0x18012af5d  xorps   xmm0, xmm0
0x18012af60  movdqu  [rbp+160h+var_148], xmm0
0x18012af65  lea     rax, [rbp+160h+var_138]
0x18012af69  mov     [rbp+160h+var_100], rax
0x18012af6d  mov     rdx, r14
0x18012af70  lea     rcx, [rbp+160h+var_1D0]
0x18012af74  call    ??$?0UCredentialInfo@@$0A@@?$weak_ptr@UCredentialInfo@@@std@@QEAA@AEBV?$shared_ptr@UCredentialInfo@@@1@@Z; std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(std::shared_ptr<CredentialInfo> const &)
0x18012af79  nop
0x18012af7a  lea     r8, ?MessageReceivedHandler@CtapHybridInternal@@YAXV?$weak_ptr@VNoise@CtapHybridInternal@@@std@@UMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@5678@@Z; CtapHybridInternal::MessageReceivedHandler(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs)
0x18012af81  mov     [rbp+160h+var_178], r8
0x18012af85  mov     rcx, [rbp+160h+var_1D0]
0x18012af89  mov     rdx, [rbp+160h+var_1C8]
0x18012af8d  mov     [rbp+160h+var_1D0], 0
0x18012af95  mov     [rbp+160h+var_1C8], 0
0x18012af9d  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@XUMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@4567@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs>::`vftable'
0x18012afa4  mov     [rbp+160h+var_F8], rax
0x18012afa8  mov     [rbp+160h+var_F0], r8
0x18012afac  mov     al, [rbp+160h+var_170]
0x18012afaf  mov     [rbp+160h+var_E8], al
0x18012afb2  mov     al, [rbp+160h+var_16F]
0x18012afb5  mov     [rbp+160h+var_E7], al
0x18012afb8  mov     [rbp+160h+var_E0], rcx
0x18012afbf  mov     [rbp+160h+var_D8], rdx
0x18012afc6  movdqu  [rbp+160h+var_168], xmm0
0x18012afcb  lea     rax, [rbp+160h+var_F8]
0x18012afcf  mov     [rbp+160h+var_C0], rax
0x18012afd6  lea     rax, [rbp+160h+var_60]
0x18012afdd  mov     qword ptr [rsp+260h+cbInput], rax
0x18012afe2  lea     rax, [rbp+160h+var_138]
0x18012afe6  mov     [rsp+260h+pbInput], rax
0x18012afeb  lea     r9, [rbp+160h+var_F8]
0x18012afef  lea     r8, [rbp+160h+var_80]
0x18012aff6  mov     rdx, [r14+100h]
0x18012affd  lea     rcx, [rbp+160h+var_1C0]
0x18012b001  call    ?ConnectToTunnelServiceCancellable@CtapHybridInternal@@YA?AUMessageWebSocket@Sockets@Networking@Windows@winrt@@PEAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6AXUMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@2345@@Z@8@V?$function@$$A6AXUIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@2345@@Z@8@1@Z; CtapHybridInternal::ConnectToTunnelServiceCancellable(void *,std::string const &,std::function<void (winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs)>,std::function<void (winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs)>,std::string const &)
0x18012b006  lea     rcx, [r14+18h]
0x18012b00a  mov     rdx, rax
0x18012b00d  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18012b012  lea     rcx, [rbp+160h+var_1C0]
0x18012b016  call    ??1?$IVector@E@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IVector<uchar>::~IVector<uchar>(void)
0x18012b01b  nop
0x18012b01c  lea     rcx, [rbp+160h+var_178]
0x18012b020  call    ??1?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@QEAA@XZ; std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(void)
0x18012b025  nop
0x18012b026  lea     rcx, [rbp+160h+var_158]
0x18012b02a  call    ??1?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@QEAA@XZ; std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(void)
0x18012b02f  nop
0x18012b030  lea     rcx, [rbp+160h+var_60]
0x18012b037  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012b03c  mov     byte ptr [r14+10h], 0
0x18012b041  mov     byte ptr [r14+108h], 1
0x18012b049  mov     [rbp+160h+var_1E0], rbx
0x18012b04d  mov     eax, 10h
0x18012b052  mov     [rbp+160h+var_1D8], rax
0x18012b056  mov     [rbp+160h+var_1D0], rdi
0x18012b05a  mov     [rbp+160h+var_1C8], rax
0x18012b05e  lea     rax, ?c_keyPurposePSK@CtapHybridInternal@@3V?$array@E$03@std@@B; std::array<uchar,4> const CtapHybridInternal::c_keyPurposePSK
0x18012b065  mov     [rsp+260h+pbInput], rax
0x18012b06a  lea     r9, [rbp+160h+var_1E0]
0x18012b06e  lea     r8, [rbp+160h+var_1D0]
0x18012b072  mov     edx, 20h ; ' '
0x18012b077  lea     rcx, [rbp+160h+var_190]
0x18012b07b  call    ?DeriveHKDFKey@CtapHybridInternal@@YA?AUHKDFKey@1@IV?$span@$$CBE$0?0@std@@V34@V?$span@$$CBE$03@4@@Z; CtapHybridInternal::DeriveHKDFKey(uint,std::span<uchar const,-1>,std::span<uchar const,-1>,std::span<uchar const,4>)
0x18012b080  nop
0x18012b081  lea     r15, [r14+28h]
0x18012b085  xor     edx, edx
0x18012b087  mov     rcx, r15
0x18012b08a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x18012b08f  mov     [rsp+260h+dwFlags], 0; dwFlags
0x18012b097  mov     [rsp+260h+cbInput], 68h ; 'h'; cbInput
0x18012b09f  mov     [rsp+260h+pbInput], rsi; int
0x18012b0a4  mov     r9, r15; phKey
0x18012b0a7  lea     r8, aEccprivateblob; "ECCPRIVATEBLOB"
0x18012b0ae  xor     edx, edx; hImportKey
0x18012b0b0  mov     ecx, 2A1h; hAlgorithm
0x18012b0b5  call    cs:__imp_BCryptImportKeyPair
0x18012b0bb  mov     rcx, [rbp+168h]; this
0x18012b0c2  test    eax, eax
0x18012b0c4  jns     short loc_18012B0DB
0x18012b0c6  mov     r9d, eax; char *
0x18012b0c9  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012b0d0  mov     edx, 5Ch ; '\'; void *
0x18012b0d5  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18012b0db  lea     rbx, [r14+20h]
0x18012b0df  mov     rdi, [rbx]
0x18012b0e2  test    rdi, rdi
0x18012b0e5  jz      short loc_18012B103
0x18012b0e7  lea     rcx, [rbp+160h+var_1C0]; this
0x18012b0eb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012b0f0  mov     rcx, rdi
0x18012b0f3  call    cs:__imp_?NoiseCloseHandle@@YAJPEAUNOISE_HANDLE__@@@Z; NoiseCloseHandle(NOISE_HANDLE__ *)
0x18012b0f9  lea     rcx, [rbp+160h+var_1C0]; this
0x18012b0fd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012b102  nop
0x18012b103  mov     qword ptr [rbx], 0
0x18012b10a  mov     rcx, rbx
0x18012b10d  call    cs:__imp_?NoiseOpenHandle@@YAJPEAPEAUNOISE_HANDLE__@@@Z; NoiseOpenHandle(NOISE_HANDLE__ * *)
0x18012b113  mov     rcx, [rbp+168h]; this
0x18012b11a  test    eax, eax
0x18012b11c  jns     short loc_18012B133
0x18012b11e  mov     r9d, eax; char *
0x18012b121  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012b128  mov     edx, 5Eh ; '^'; void *
0x18012b12d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012b133  mov     [rsp+260h+var_1F0], 1
0x18012b138  lea     rax, [rsp+260h+var_1F0]
0x18012b13d  mov     [rbp+160h+var_1E0], rax
0x18012b141  lea     rax, [rsp+260h+var_1EF]
0x18012b146  mov     [rbp+160h+var_1D8], rax
0x18012b14a  lea     rdx, [rbp+160h+var_1E0]
0x18012b14e  lea     rcx, [rbp+160h+var_1A8]
0x18012b152  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$initializer_list@E@1@AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::initializer_list<uchar>,std::allocator<uchar> const &)
0x18012b157  nop
0x18012b158  mov     rdx, [rbp+160h+var_190]
0x18012b15c  mov     r8, [rbp+160h+var_1A8]
0x18012b160  mov     eax, [rbp+160h+var_188]
0x18012b163  sub     eax, edx
0x18012b165  mov     ecx, [rbp+160h+var_1A0]
0x18012b168  sub     ecx, r8d
0x18012b16b  mov     [rsp+260h+var_200], eax
0x18012b16f  mov     [rsp+260h+var_208], rdx
0x18012b174  mov     [rsp+260h+var_210], 0
0x18012b17c  mov     [rsp+260h+var_218], 0
0x18012b185  mov     rax, [r15]
0x18012b188  mov     [rsp+260h+var_220], rax
0x18012b18d  mov     [rsp+260h+var_228], ecx
0x18012b191  mov     qword ptr [rsp+260h+dwFlags], r8
0x18012b196  mov     byte ptr [rsp+260h+cbInput], 1
0x18012b19b  lea     rax, aKnpsk0; "KNpsk0"
0x18012b1a2  mov     [rsp+260h+pbInput], rax; int
0x18012b1a7  lea     r9, pwszCNGHashAlgid; "SHA256"
0x18012b1ae  mov     r8d, 1E1h
0x18012b1b4  lea     rdx, aEcdhP256; "ECDH_P256"
0x18012b1bb  mov     rcx, [rbx]
0x18012b1be  call    cs:__imp_?NoiseHandshakeInitialize@@YAJPEAUNOISE_HANDLE__@@QEBGQEAX11_NQEAEK24K4K@Z; NoiseHandshakeInitialize(NOISE_HANDLE__ *,ushort const * const,void * const,ushort const * const,ushort const * const,bool,uchar * const,ulong,void * const,uchar * const,ulong,uchar * const,ulong)
0x18012b1c4  mov     rcx, [rbp+168h]; this
0x18012b1cb  test    eax, eax
0x18012b1cd  jns     short loc_18012B1E4
0x18012b1cf  mov     r9d, eax; char *
0x18012b1d2  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012b1d9  mov     edx, 63h ; 'c'; void *
0x18012b1de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012b1e4  lea     rdx, [rbp+160h+var_B8]
0x18012b1eb  mov     rcx, r14
0x18012b1ee  call    ?ProcessHandshakeMessage@Noise@CtapHybridInternal@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; CtapHybridInternal::Noise::ProcessHandshakeMessage(void)
0x18012b1f3  nop
0x18012b1f4  lea     rdx, [rbp+160h+var_B8]
0x18012b1fb  mov     rcx, r14
0x18012b1fe  call    ?WriteMessageInSocket@Noise@CtapHybridInternal@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; CtapHybridInternal::Noise::WriteMessageInSocket(std::vector<uchar> const &)
0x18012b203  nop
0x18012b204  lea     rcx, [rbp+160h+var_B8]
0x18012b20b  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18012b210  nop
0x18012b211  lea     rcx, [rbp+160h+var_1A8]
0x18012b215  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18012b21a  nop
0x18012b21b  lea     rcx, [rbp+160h+var_190]
0x18012b21f  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18012b224  nop
0x18012b225  lea     rcx, [rbp+160h+var_1B0]
0x18012b229  call    ??1?$IVector@E@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IVector<uchar>::~IVector<uchar>(void)
0x18012b22e  nop
0x18012b22f  lea     rcx, [rbp+160h+var_80]
0x18012b236  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18012b23b  mov     rcx, [rbp+160h+var_40]
0x18012b242  xor     rcx, rsp; StackCookie
0x18012b245  call    __security_check_cookie
0x18012b24a  add     rsp, 238h
0x18012b251  pop     r15
0x18012b253  pop     r14
0x18012b255  pop     rdi
0x18012b256  pop     rsi
0x18012b257  pop     rbx
0x18012b258  pop     rbp
0x18012b259  retn
```
