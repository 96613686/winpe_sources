# CtapHybridInternal::Noise::PerformHandshake(CtapHybridInternal::CtapHybridEvent &,_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *,CtapHybridInternal::CtapOperationHint)

- ea: `0x18012a8e4`
- end: `0x18012ae7a`
- name: `?PerformHandshake@Noise@CtapHybridInternal@@QEAAXAEAUCtapHybridEvent@2@PEAU_CTAPCBOR_HYBRID_STORAGE_LINKED_DATA@@W4CtapOperationHint@2@@Z`
- size: `1430`
- prototype: `void __high(struct CtapHybridInternal::CtapHybridEvent *, struct _CTAPCBOR_HYBRID_STORAGE_LINKED_DATA *, enum CtapHybridInternal::CtapOperationHint)`
- caller_count: `1`
- callee_count: `31`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180107340`

## callees

- `0x18000a210`
- `0x180017724`
- `0x18001cd78`
- `0x18001df88`
- `0x180023264`
- `0x1800241a4`
- `0x18003164c`
- `0x1800350b4`
- `0x180037f6c`
- `0x18003ac98`
- `0x18003acb8`
- `0x180046f30`
- `0x18004aa68`
- `0x18005176c`
- `0x180062fcc`
- `0x180067630`
- `0x18006b260`
- `0x18006c82c`
- `0x18007e064`
- `0x1800d5c1c`
- `0x1801048ec`
- `0x180106c0c`
- `0x180108ff8`
- `0x18012a404`
- `0x18012a8e4`
- `0x18012b260`
- `0x18012bff8`
- `0x18012d048`
- `0x18012d32c`
- `0x18012d7f0`
- `0x18013c090`

## import_xrefs

- `noise!NoiseCloseHandle` at `0x18012acd8`
- `noise!NoiseCloseHandle` at `0x18012acd8`
- `noise!NoiseOpenHandle` at `0x18012acf2`
- `noise!NoiseOpenHandle` at `0x18012acf2`
- `noise!NoiseHandshakeInitialize` at `0x18012ada3`
- `noise!NoiseHandshakeInitialize` at `0x18012ada3`
- `bcrypt!BCryptGenRandom` at `0x18012a947`
- `bcrypt!BCryptGenRandom` at `0x18012a947`

## string_xrefs

- `0x18012a95b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012a98f`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012aa3b`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012ac64`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012ad06`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`
- `0x18012adb7`: `onecore\ds\security\fido\ctap\transports_modern\ctaphybridnoise.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CtapHybridInternal::Noise::PerformHandshake(__int64 a1, int a2, __int64 a3, int a4)
{
  NTSTATUS v8; // eax
  const wchar_t *v9; // rdx
  _QWORD *v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  char *v13; // rcx
  __int64 v14; // rdx
  __int128 v15; // xmm0
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  char *v19; // rdi
  __int64 v20; // r15
  int v21; // eax
  struct CtapHybridInternal::CtapHybridEvent *v22; // r8
  struct NOISE_HANDLE__ **v23; // rdi
  struct NOISE_HANDLE__ *v24; // r14
  int v25; // eax
  int v26; // eax
  unsigned int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  int v30; // [rsp+20h] [rbp-E0h]
  int v31; // [rsp+20h] [rbp-E0h]
  char v32; // [rsp+70h] [rbp-90h] BYREF
  char v33; // [rsp+71h] [rbp-8Fh] BYREF
  char *v34; // [rsp+80h] [rbp-80h] BYREF
  __int64 v35; // [rsp+88h] [rbp-78h]
  char *v36; // [rsp+90h] [rbp-70h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h]
  PUCHAR pbBuffer; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v41; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v42)(); // [rsp+C8h] [rbp-38h] BYREF
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int128 v44; // [rsp+D8h] [rbp-28h]
  _QWORD *v45; // [rsp+E8h] [rbp-18h]
  unsigned __int8 *v46; // [rsp+F0h] [rbp-10h] BYREF
  int v47; // [rsp+F8h] [rbp-8h]
  unsigned __int8 *v48; // [rsp+108h] [rbp+8h] BYREF
  int v49; // [rsp+110h] [rbp+10h]
  __int64 (__fastcall *v50)(); // [rsp+120h] [rbp+20h] BYREF
  char v51; // [rsp+128h] [rbp+28h]
  char v52; // [rsp+129h] [rbp+29h]
  __int128 v53; // [rsp+130h] [rbp+30h]
  _QWORD v54[2]; // [rsp+140h] [rbp+40h] BYREF
  __int16 v55; // [rsp+150h] [rbp+50h]
  char *v56; // [rsp+158h] [rbp+58h]
  __int64 v57; // [rsp+160h] [rbp+60h]
  _QWORD *v58; // [rsp+178h] [rbp+78h]
  _QWORD v59[2]; // [rsp+180h] [rbp+80h] BYREF
  char v60; // [rsp+190h] [rbp+90h]
  char v61; // [rsp+191h] [rbp+91h]
  __int64 v62; // [rsp+198h] [rbp+98h]
  __int64 v63; // [rsp+1A0h] [rbp+A0h]
  _QWORD *v64; // [rsp+1B8h] [rbp+B8h]
  _BYTE v65[24]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v66[24]; // [rsp+1D8h] [rbp+D8h] BYREF
  int v67[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _QWORD v68[4]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v69[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v70[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE Src[32]; // [rsp+260h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  std::vector<unsigned char>::vector<unsigned char>(&pbBuffer, 16, &v32);
  v8 = BCryptGenRandom((BCRYPT_ALG_HANDLE)0x81, pbBuffer, v41 - (_DWORD)pbBuffer, 0);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v8,
      v28);
  std::wstring::wstring(v68);
  if ( a4 )
  {
    if ( a4 != 1 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
        (const char *)0x80070057LL,
        v28);
    v9 = L"mc";
  }
  else
  {
    v9 = L"ga";
  }
  std::wstring::_Assign<unsigned short>(v68, v9);
  v42 = (__int64 (__fastcall *)())*(unsigned int *)(a3 + 16);
  v43 = *(_QWORD *)(a3 + 24);
  *(_QWORD *)&v44 = (unsigned int)(v41 - (_DWORD)pbBuffer);
  *((_QWORD *)&v44 + 1) = pbBuffer;
  v10 = v68;
  if ( v68[3] > 7u )
    v10 = (_QWORD *)v68[0];
  v45 = v10;
  LODWORD(v38) = 0;
  v36 = 0;
  v11 = CtapCborEncodeHybridClientPayload(&v42, &v38, &v36);
  v12 = CtapCborErrorToWin32Error(v11);
  if ( v12 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)v12,
      v28);
  v34 = v36;
  v35 = (unsigned int)v38;
  CtapHybridInternal::HexEncodeBytes(Src);
  CtapHybridInternal::DecodeTunnelServerDomain(v70, *(unsigned __int16 *)(a3 + 72));
  std::vector<unsigned char>::vector<unsigned char>(
    v66,
    *(_QWORD *)(a3 + 8),
    *(_QWORD *)(a3 + 8) + *(unsigned int *)(a3 + 4));
  CtapHybridInternal::BuildWebSocketUrlToTunnelService(v69, v70, v66);
  std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(&v34, a1);
  v42 = CtapHybridInternal::SocketClosedHandler;
  v13 = v34;
  v14 = v35;
  v34 = 0;
  v35 = 0;
  v54[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs>::`vftable';
  v54[1] = CtapHybridInternal::SocketClosedHandler;
  v55 = v43;
  v56 = v13;
  v57 = v14;
  v15 = 0;
  v44 = 0;
  v58 = v54;
  *(double *)&v15 = std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(&v38, a1);
  v50 = CtapHybridInternal::MessageReceivedHandler;
  v16 = v38;
  v17 = v39;
  v38 = 0;
  v39 = 0;
  v59[0] = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs>::`vftable';
  v59[1] = CtapHybridInternal::MessageReceivedHandler;
  v60 = v51;
  v61 = v52;
  v62 = v16;
  v63 = v17;
  v53 = v15;
  v64 = v59;
  v18 = CtapHybridInternal::ConnectToTunnelServiceCancellable(
          (unsigned int)&v36,
          *(_QWORD *)(a1 + 256),
          (unsigned int)v69,
          (unsigned int)v59,
          (__int64)v54,
          (__int64)Src);
  winrt::Windows::Foundation::IUnknown::operator=(a1 + 24, v18);
  winrt::Windows::Foundation::Collections::IVector<unsigned char>::~IVector<unsigned char>(&v36);
  std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(&v50);
  std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(&v42);
  *(_BYTE *)(a1 + 16) = 0;
  *(_BYTE *)(a1 + 264) = 1;
  CtapDevicePublishWnfState(0x20u, 0x196u, 0, 0);
  *(_OWORD *)v67 = 0;
  v19 = *(char **)(a3 + 40);
  v20 = *(unsigned int *)(a3 + 32);
  v34 = (char *)pbBuffer;
  v35 = v41 - (_QWORD)pbBuffer;
  v36 = v19;
  v37 = v20;
  v21 = CtapHybridInternal::CtapHybridLookForMatchingAdvertisementsCancellable(
          *(_QWORD *)(a1 + 256),
          (unsigned int)&v36,
          (unsigned int)&v34,
          a2,
          (__int64)v67);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v21,
      v29);
  CtapHybridInternal::PopulateDeviceTypeInTelemetry((CtapHybridInternal *)*(unsigned __int16 *)(a3 + 72), a2, v22);
  v34 = (char *)v67;
  v35 = 16;
  v36 = v19;
  v37 = v20;
  CtapHybridInternal::DeriveHKDFKey(
    (unsigned int)&v48,
    32,
    (unsigned int)&v36,
    (unsigned int)&v34,
    (__int64)&CtapHybridInternal::c_keyPurposePSK);
  v23 = (struct NOISE_HANDLE__ **)(a1 + 32);
  v24 = *(struct NOISE_HANDLE__ **)(a1 + 32);
  if ( v24 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
    NoiseCloseHandle(v24);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
  }
  *v23 = 0;
  v25 = NoiseOpenHandle((struct NOISE_HANDLE__ **)(a1 + 32));
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v25,
      v30);
  v32 = 0;
  v34 = &v32;
  v35 = (__int64)&v33;
  std::vector<unsigned char>::vector<unsigned char>(&v46, &v34);
  v26 = NoiseHandshakeInitialize(
          *v23,
          L"ECDH_P256",
          (void *const)0x1E1,
          L"SHA256",
          L"NKpsk0",
          1,
          v46,
          v47 - (_DWORD)v46,
          0,
          *(unsigned __int8 *const *)(a3 + 56),
          *(_DWORD *)(a3 + 48),
          v48,
          v49 - (_DWORD)v48);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaphybridnoise.cpp",
      (const char *)(unsigned int)v26,
      v31);
  CtapHybridInternal::Noise::ProcessHandshakeMessage(a1, v65);
  CtapHybridInternal::Noise::WriteMessageInSocket(a1, v65);
  std::vector<unsigned char>::_Tidy(v65);
  std::vector<unsigned char>::_Tidy(&v46);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::_Tidy(&v48);
  std::string::_Tidy_deallocate(v69);
  std::vector<unsigned char>::_Tidy(v66);
  std::string::_Tidy_deallocate(v70);
  std::string::_Tidy_deallocate(Src);
  std::wstring::_Tidy_deallocate(v68);
  return std::vector<unsigned char>::_Tidy(&pbBuffer);
}

```

## disassembly

```asm
0x18012a8e4  mov     [rsp-8+arg_18], rbx
0x18012a8e9  push    rbp
0x18012a8ea  push    rsi
0x18012a8eb  push    rdi
0x18012a8ec  push    r14
0x18012a8ee  push    r15
0x18012a8f0  lea     rbp, [rsp-190h]
0x18012a8f8  sub     rsp, 290h
0x18012a8ff  mov     rax, cs:__security_cookie
0x18012a906  xor     rax, rsp
0x18012a909  mov     [rbp+1B0h+var_30], rax
0x18012a910  mov     edi, r9d
0x18012a913  mov     rbx, r8
0x18012a916  mov     r14, rdx
0x18012a919  mov     rsi, rcx
0x18012a91c  lea     r8, [rsp+2B0h+var_240]
0x18012a921  mov     edx, 10h
0x18012a926  lea     rcx, [rbp+1B0h+pbBuffer]
0x18012a92a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18012a92f  nop
0x18012a930  mov     rdx, [rbp+1B0h+pbBuffer]; pbBuffer
0x18012a934  mov     r8d, dword ptr [rbp+1B0h+var_1F8]
0x18012a938  sub     r8d, edx; cbBuffer
0x18012a93b  xor     r9d, r9d; dwFlags
0x18012a93e  mov     r15d, 81h
0x18012a944  mov     ecx, r15d; hAlgorithm
0x18012a947  call    cs:__imp_BCryptGenRandom
0x18012a94d  mov     rcx, [rbp+1B8h]; this
0x18012a954  test    eax, eax
0x18012a956  jns     short loc_18012A96C
0x18012a958  mov     r9d, eax; char *
0x18012a95b  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012a962  lea     edx, [r15-14h]; void *
0x18012a966  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012a96c  lea     rcx, [rbp+1B0h+var_B0]
0x18012a973  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18012a978  nop
0x18012a979  test    edi, edi
0x18012a97b  jz      short loc_18012A9AA
0x18012a97d  cmp     edi, 1
0x18012a980  jz      short loc_18012A9A1
0x18012a982  mov     rcx, [rbp+1B8h]; this
0x18012a989  mov     r9d, 80070057h; char *
0x18012a98f  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012a996  mov     edx, 79h ; 'y'; void *
0x18012a99b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012a9a1  lea     rdx, aMc; "mc"
0x18012a9a8  jmp     short loc_18012A9B1
0x18012a9aa  lea     rdx, aGa; "ga"
0x18012a9b1  mov     r8d, 2
0x18012a9b7  lea     rcx, [rbp+1B0h+var_B0]
0x18012a9be  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18012a9c3  mov     eax, [rbx+10h]
0x18012a9c6  mov     dword ptr [rbp+1B0h+var_1E8], eax
0x18012a9c9  xor     eax, eax
0x18012a9cb  mov     dword ptr [rbp+1B0h+var_1E8+4], eax
0x18012a9ce  mov     rax, [rbx+18h]
0x18012a9d2  mov     [rbp+1B0h+var_1E0], rax
0x18012a9d6  mov     eax, dword ptr [rbp+1B0h+var_1F8]
0x18012a9d9  mov     rcx, [rbp+1B0h+pbBuffer]
0x18012a9dd  sub     eax, ecx
0x18012a9df  mov     dword ptr [rbp+1B0h+var_1D8], eax
0x18012a9e2  xor     eax, eax
0x18012a9e4  mov     dword ptr [rbp+1B0h+var_1D8+4], eax
0x18012a9e7  mov     qword ptr [rbp+1B0h+var_1D8+8], rcx
0x18012a9eb  lea     rax, [rbp+1B0h+var_B0]
0x18012a9f2  cmp     [rbp+1B0h+var_98], 7
0x18012a9fa  cmova   rax, [rbp+1B0h+var_B0]
0x18012aa02  mov     [rbp+1B0h+var_1C8], rax
0x18012aa06  mov     dword ptr [rbp+1B0h+var_210], 0
0x18012aa0d  mov     [rbp+1B0h+var_220], 0
0x18012aa15  lea     r8, [rbp+1B0h+var_220]
0x18012aa19  lea     rdx, [rbp+1B0h+var_210]
0x18012aa1d  lea     rcx, [rbp+1B0h+var_1E8]
0x18012aa21  call    CtapCborEncodeHybridClientPayload
0x18012aa26  mov     ecx, eax
0x18012aa28  call    CtapCborErrorToWin32Error
0x18012aa2d  mov     rcx, [rbp+1B8h]; this
0x18012aa34  test    eax, eax
0x18012aa36  jz      short loc_18012AA4B
0x18012aa38  mov     r9d, eax; char *
0x18012aa3b  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012aa42  mov     edx, r15d; void *
0x18012aa45  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18012aa4b  mov     rax, [rbp+1B0h+var_220]
0x18012aa4f  mov     [rbp+1B0h+var_230], rax
0x18012aa53  mov     eax, dword ptr [rbp+1B0h+var_210]
0x18012aa56  mov     [rbp+1B0h+var_228], rax
0x18012aa5a  lea     rdx, [rbp+1B0h+var_230]
0x18012aa5e  lea     rcx, [rbp+1B0h+Src]; Src
0x18012aa65  call    ?HexEncodeBytes@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$span@$$CBE$0?0@3@@Z; CtapHybridInternal::HexEncodeBytes(std::span<uchar const,-1>)
0x18012aa6a  nop
0x18012aa6b  movzx   edx, word ptr [rbx+48h]
0x18012aa6f  lea     rcx, [rbp+1B0h+var_70]
0x18012aa76  call    ?DecodeTunnelServerDomain@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@G@Z; CtapHybridInternal::DecodeTunnelServerDomain(ushort)
0x18012aa7b  nop
0x18012aa7c  mov     rdx, [rbx+8]
0x18012aa80  mov     r8d, [rbx+4]
0x18012aa84  add     r8, rdx
0x18012aa87  lea     rcx, [rbp+1B0h+var_D8]
0x18012aa8e  call    ??$?0PEAE$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@PEAE0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(uchar *,uchar *,std::allocator<uchar> const &)
0x18012aa93  nop
0x18012aa94  lea     r8, [rbp+1B0h+var_D8]
0x18012aa9b  lea     rdx, [rbp+1B0h+var_70]
0x18012aaa2  lea     rcx, [rbp+1B0h+var_90]
0x18012aaa9  call    ?BuildWebSocketUrlToTunnelService@CtapHybridInternal@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@AEBV?$vector@EV?$allocator@E@std@@@3@@Z; CtapHybridInternal::BuildWebSocketUrlToTunnelService(std::string const &,std::vector<uchar> const &)
0x18012aaae  nop
0x18012aaaf  mov     rdx, rsi
0x18012aab2  lea     rcx, [rbp+1B0h+var_230]
0x18012aab6  call    ??$?0UCredentialInfo@@$0A@@?$weak_ptr@UCredentialInfo@@@std@@QEAA@AEBV?$shared_ptr@UCredentialInfo@@@1@@Z; std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(std::shared_ptr<CredentialInfo> const &)
0x18012aabb  nop
0x18012aabc  lea     r8, ?SocketClosedHandler@CtapHybridInternal@@YAXV?$weak_ptr@VNoise@CtapHybridInternal@@@std@@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@Z; CtapHybridInternal::SocketClosedHandler(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs)
0x18012aac3  mov     [rbp+1B0h+var_1E8], r8
0x18012aac7  mov     rcx, [rbp+1B0h+var_230]
0x18012aacb  mov     rdx, [rbp+1B0h+var_228]
0x18012aacf  mov     [rbp+1B0h+var_230], 0
0x18012aad7  mov     [rbp+1B0h+var_228], 0
0x18012aadf  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@XUIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@4567@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs>::`vftable'
0x18012aae6  mov     [rbp+1B0h+var_170], rax
0x18012aaea  mov     [rbp+1B0h+var_168], r8
0x18012aaee  mov     al, byte ptr [rbp+1B0h+var_1E0]
0x18012aaf1  mov     byte ptr [rbp+1B0h+var_160], al
0x18012aaf4  mov     al, byte ptr [rbp+1B0h+var_1E0+1]
0x18012aaf7  mov     byte ptr [rbp+1B0h+var_160+1], al
0x18012aafa  mov     [rbp+1B0h+var_158], rcx
0x18012aafe  mov     [rbp+1B0h+var_150], rdx
0x18012ab02  xorps   xmm0, xmm0
0x18012ab05  movdqu  [rbp+1B0h+var_1D8], xmm0
0x18012ab0a  lea     rax, [rbp+1B0h+var_170]
0x18012ab0e  mov     [rbp+1B0h+var_138], rax
0x18012ab12  mov     rdx, rsi
0x18012ab15  lea     rcx, [rbp+1B0h+var_210]
0x18012ab19  call    ??$?0UCredentialInfo@@$0A@@?$weak_ptr@UCredentialInfo@@@std@@QEAA@AEBV?$shared_ptr@UCredentialInfo@@@1@@Z; std::weak_ptr<CredentialInfo>::weak_ptr<CredentialInfo>(std::shared_ptr<CredentialInfo> const &)
0x18012ab1e  nop
0x18012ab1f  lea     r8, ?MessageReceivedHandler@CtapHybridInternal@@YAXV?$weak_ptr@VNoise@CtapHybridInternal@@@std@@UMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@5678@@Z; CtapHybridInternal::MessageReceivedHandler(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs)
0x18012ab26  mov     [rbp+1B0h+var_190], r8
0x18012ab2a  mov     rcx, [rbp+1B0h+var_210]
0x18012ab2e  mov     rdx, [rbp+1B0h+var_208]
0x18012ab32  mov     [rbp+1B0h+var_210], 0
0x18012ab3a  mov     [rbp+1B0h+var_208], 0
0x18012ab42  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@XUMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@4567@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>,void,winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs>::`vftable'
0x18012ab49  mov     [rbp+1B0h+var_130], rax
0x18012ab50  mov     [rbp+1B0h+var_128], r8
0x18012ab57  mov     al, [rbp+1B0h+var_188]
0x18012ab5a  mov     [rbp+1B0h+var_120], al
0x18012ab60  mov     al, [rbp+1B0h+var_187]
0x18012ab63  mov     [rbp+1B0h+var_11F], al
0x18012ab69  mov     [rbp+1B0h+var_118], rcx
0x18012ab70  mov     [rbp+1B0h+var_110], rdx
0x18012ab77  movdqu  [rbp+1B0h+var_180], xmm0
0x18012ab7c  lea     rax, [rbp+1B0h+var_130]
0x18012ab83  mov     [rbp+1B0h+var_F8], rax
0x18012ab8a  lea     rax, [rbp+1B0h+Src]
0x18012ab91  mov     [rsp+2B0h+var_288], rax
0x18012ab96  lea     rax, [rbp+1B0h+var_170]
0x18012ab9a  mov     qword ptr [rsp+2B0h+var_290], rax
0x18012ab9f  lea     r9, [rbp+1B0h+var_130]
0x18012aba6  lea     r8, [rbp+1B0h+var_90]
0x18012abad  mov     rdx, [rsi+100h]
0x18012abb4  lea     rcx, [rbp+1B0h+var_220]
0x18012abb8  call    ?ConnectToTunnelServiceCancellable@CtapHybridInternal@@YA?AUMessageWebSocket@Sockets@Networking@Windows@winrt@@PEAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6AXUMessageWebSocket@Sockets@Networking@Windows@winrt@@UMessageWebSocketMessageReceivedEventArgs@2345@@Z@8@V?$function@$$A6AXUIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@2345@@Z@8@1@Z; CtapHybridInternal::ConnectToTunnelServiceCancellable(void *,std::string const &,std::function<void (winrt::Windows::Networking::Sockets::MessageWebSocket,winrt::Windows::Networking::Sockets::MessageWebSocketMessageReceivedEventArgs)>,std::function<void (winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs)>,std::string const &)
0x18012abbd  lea     rcx, [rsi+18h]
0x18012abc1  mov     rdx, rax
0x18012abc4  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x18012abc9  lea     rcx, [rbp+1B0h+var_220]
0x18012abcd  call    ??1?$IVector@E@Collections@Foundation@Windows@winrt@@QEAA@XZ; winrt::Windows::Foundation::Collections::IVector<uchar>::~IVector<uchar>(void)
0x18012abd2  nop
0x18012abd3  lea     rcx, [rbp+1B0h+var_190]
0x18012abd7  call    ??1?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@QEAA@XZ; std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(void)
0x18012abdc  nop
0x18012abdd  lea     rcx, [rbp+1B0h+var_1E8]
0x18012abe1  call    ??1?$_Binder@U_Unforced@std@@A6AXV?$weak_ptr@VNoise@CtapHybridInternal@@@2@UIWebSocket@Sockets@Networking@Windows@winrt@@UWebSocketClosedEventArgs@5678@@ZV32@AEBU?$_Ph@$00@2@AEBU?$_Ph@$01@2@@std@@QEAA@XZ; std::_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>::~_Binder<std::_Unforced,void (&)(std::weak_ptr<CtapHybridInternal::Noise>,winrt::Windows::Networking::Sockets::IWebSocket,winrt::Windows::Networking::Sockets::WebSocketClosedEventArgs),std::weak_ptr<CtapHybridInternal::Noise>,std::_Ph<1> const &,std::_Ph<2> const &>(void)
0x18012abe6  nop
0x18012abe7  mov     byte ptr [rsi+10h], 0
0x18012abeb  mov     byte ptr [rsi+108h], 1
0x18012abf2  xor     r9d, r9d
0x18012abf5  xor     r8d, r8d
0x18012abf8  mov     edx, 196h
0x18012abfd  lea     ecx, [r9+20h]
0x18012ac01  call    _CtapDevicePublishWnfState
0x18012ac06  xorps   xmm0, xmm0
0x18012ac09  movups  xmmword ptr [rbp+1B0h+var_C0], xmm0
0x18012ac10  mov     rdi, [rbx+28h]
0x18012ac14  mov     r15d, [rbx+20h]
0x18012ac18  mov     rcx, [rbp+1B0h+pbBuffer]
0x18012ac1c  mov     [rbp+1B0h+var_230], rcx
0x18012ac20  mov     rax, [rbp+1B0h+var_1F8]
0x18012ac24  sub     rax, rcx
0x18012ac27  mov     [rbp+1B0h+var_228], rax
0x18012ac2b  mov     [rbp+1B0h+var_220], rdi
0x18012ac2f  mov     [rbp+1B0h+var_218], r15
0x18012ac33  lea     rax, [rbp+1B0h+var_C0]
0x18012ac3a  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18012ac3f  mov     r9, r14
0x18012ac42  lea     r8, [rbp+1B0h+var_230]
0x18012ac46  lea     rdx, [rbp+1B0h+var_220]
0x18012ac4a  mov     rcx, [rsi+100h]
0x18012ac51  call    ?CtapHybridLookForMatchingAdvertisementsCancellable@CtapHybridInternal@@YAJPEAXV?$span@$$CBE$0?0@std@@1AEAUCtapHybridEvent@1@AEAUUnpackedAdvertisementData@1@@Z; CtapHybridInternal::CtapHybridLookForMatchingAdvertisementsCancellable(void *,std::span<uchar const,-1>,std::span<uchar const,-1>,CtapHybridInternal::CtapHybridEvent &,CtapHybridInternal::UnpackedAdvertisementData &)
0x18012ac56  mov     rcx, [rbp+1B8h]; this
0x18012ac5d  test    eax, eax
0x18012ac5f  jns     short loc_18012AC76
0x18012ac61  mov     r9d, eax; char *
0x18012ac64  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012ac6b  mov     edx, 97h; void *
0x18012ac70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012ac76  mov     rdx, r14; unsigned __int16
0x18012ac79  movzx   ecx, word ptr [rbx+48h]; this
0x18012ac7d  call    ?PopulateDeviceTypeInTelemetry@CtapHybridInternal@@YAXGAEAUCtapHybridEvent@1@@Z; CtapHybridInternal::PopulateDeviceTypeInTelemetry(ushort,CtapHybridInternal::CtapHybridEvent &)
0x18012ac82  lea     rax, [rbp+1B0h+var_C0]
0x18012ac89  mov     [rbp+1B0h+var_230], rax
0x18012ac8d  mov     [rbp+1B0h+var_228], 10h
0x18012ac95  mov     [rbp+1B0h+var_220], rdi
0x18012ac99  mov     [rbp+1B0h+var_218], r15
0x18012ac9d  lea     rax, ?c_keyPurposePSK@CtapHybridInternal@@3V?$array@E$03@std@@B; std::array<uchar,4> const CtapHybridInternal::c_keyPurposePSK
0x18012aca4  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18012aca9  lea     r9, [rbp+1B0h+var_230]
0x18012acad  lea     r8, [rbp+1B0h+var_220]
0x18012acb1  mov     edx, 20h ; ' '
0x18012acb6  lea     rcx, [rbp+1B0h+var_1A8]
0x18012acba  call    ?DeriveHKDFKey@CtapHybridInternal@@YA?AUHKDFKey@1@IV?$span@$$CBE$0?0@std@@V34@V?$span@$$CBE$03@4@@Z; CtapHybridInternal::DeriveHKDFKey(uint,std::span<uchar const,-1>,std::span<uchar const,-1>,std::span<uchar const,4>)
0x18012acbf  nop
0x18012acc0  lea     rdi, [rsi+20h]
0x18012acc4  mov     r14, [rdi]
0x18012acc7  test    r14, r14
0x18012acca  jz      short loc_18012ACE8
0x18012accc  lea     rcx, [rbp+1B0h+var_220]; this
0x18012acd0  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18012acd5  mov     rcx, r14
0x18012acd8  call    cs:__imp_?NoiseCloseHandle@@YAJPEAUNOISE_HANDLE__@@@Z; NoiseCloseHandle(NOISE_HANDLE__ *)
0x18012acde  lea     rcx, [rbp+1B0h+var_220]; this
0x18012ace2  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18012ace7  nop
0x18012ace8  mov     qword ptr [rdi], 0
0x18012acef  mov     rcx, rdi
0x18012acf2  call    cs:__imp_?NoiseOpenHandle@@YAJPEAPEAUNOISE_HANDLE__@@@Z; NoiseOpenHandle(NOISE_HANDLE__ * *)
0x18012acf8  mov     rcx, [rbp+1B8h]; this
0x18012acff  test    eax, eax
0x18012ad01  jns     short loc_18012AD18
0x18012ad03  mov     r9d, eax; char *
0x18012ad06  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012ad0d  mov     edx, 0AFh; void *
0x18012ad12  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012ad18  mov     [rsp+2B0h+var_240], 0
0x18012ad1d  lea     rax, [rsp+2B0h+var_240]
0x18012ad22  mov     [rbp+1B0h+var_230], rax
0x18012ad26  lea     rax, [rsp+2B0h+var_23F]
0x18012ad2b  mov     [rbp+1B0h+var_228], rax
0x18012ad2f  lea     rdx, [rbp+1B0h+var_230]
0x18012ad33  lea     rcx, [rbp+1B0h+var_1C0]
0x18012ad37  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$initializer_list@E@1@AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::initializer_list<uchar>,std::allocator<uchar> const &)
0x18012ad3c  nop
0x18012ad3d  mov     rcx, [rbp+1B0h+var_1A8]
0x18012ad41  mov     r8, [rbp+1B0h+var_1C0]
0x18012ad45  mov     eax, [rbp+1B0h+var_1A0]
0x18012ad48  sub     eax, ecx
0x18012ad4a  mov     edx, [rbp+1B0h+var_1B8]
0x18012ad4d  sub     edx, r8d
0x18012ad50  mov     [rsp+2B0h+var_250], eax
0x18012ad54  mov     [rsp+2B0h+var_258], rcx
0x18012ad59  mov     eax, [rbx+30h]
0x18012ad5c  mov     [rsp+2B0h+var_260], eax
0x18012ad60  mov     rax, [rbx+38h]
0x18012ad64  mov     [rsp+2B0h+var_268], rax
0x18012ad69  mov     [rsp+2B0h+var_270], 0
0x18012ad72  mov     [rsp+2B0h+var_278], edx
0x18012ad76  mov     [rsp+2B0h+var_280], r8
0x18012ad7b  mov     byte ptr [rsp+2B0h+var_288], 1
0x18012ad80  lea     rax, aNkpsk0; "NKpsk0"
0x18012ad87  mov     qword ptr [rsp+2B0h+var_290], rax; int
0x18012ad8c  lea     r9, pwszCNGHashAlgid; "SHA256"
0x18012ad93  mov     r8d, 1E1h
0x18012ad99  lea     rdx, aEcdhP256; "ECDH_P256"
0x18012ada0  mov     rcx, [rdi]
0x18012ada3  call    cs:__imp_?NoiseHandshakeInitialize@@YAJPEAUNOISE_HANDLE__@@QEBGQEAX11_NQEAEK24K4K@Z; NoiseHandshakeInitialize(NOISE_HANDLE__ *,ushort const * const,void * const,ushort const * const,ushort const * const,bool,uchar * const,ulong,void * const,uchar * const,ulong,uchar * const,ulong)
0x18012ada9  mov     rcx, [rbp+1B8h]; this
0x18012adb0  test    eax, eax
0x18012adb2  jns     short loc_18012ADC9
0x18012adb4  mov     r9d, eax; char *
0x18012adb7  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012adbe  mov     edx, 0B4h; void *
0x18012adc3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18012adc9  lea     rdx, [rbp+1B0h+var_F0]
0x18012add0  mov     rcx, rsi
0x18012add3  call    ?ProcessHandshakeMessage@Noise@CtapHybridInternal@@AEAA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; CtapHybridInternal::Noise::ProcessHandshakeMessage(void)
0x18012add8  nop
0x18012add9  lea     rdx, [rbp+1B0h+var_F0]
0x18012ade0  mov     rcx, rsi
0x18012ade3  call    ?WriteMessageInSocket@Noise@CtapHybridInternal@@AEAAXAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; CtapHybridInternal::Noise::WriteMessageInSocket(std::vector<uchar> const &)
0x18012ade8  nop
0x18012ade9  lea     rcx, [rbp+1B0h+var_F0]
0x18012adf0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18012adf5  nop
0x18012adf6  lea     rcx, [rbp+1B0h+var_1C0]
0x18012adfa  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18012adff  nop
0x18012ae00  lea     rcx, [rbp+1B0h+var_1A8]
0x18012ae04  call    ?_Tidy@?$vector@EU?$secure_allocator@E@wil@@@std@@AEAAXXZ; std::vector<uchar,wil::secure_allocator<uchar>>::_Tidy(void)
0x18012ae09  nop
0x18012ae0a  lea     rcx, [rbp+1B0h+var_90]
0x18012ae11  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
  ... truncated ...
```
