# SharingPlatform::SessionHost::OnData(unsigned __int64,uchar const *,unsigned __int64,unsigned __int64,unsigned __int64,char const *)

- ea: `0x18005ca70`
- end: `0x18005cfb1`
- name: `?OnData@SessionHost@SharingPlatform@@UEAAJ_KPEBE000PEBD@Z`
- size: `1345`
- prototype: `__int64 __fastcall(SharingPlatform::SessionHost *this, __int64, const unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x18000a580`
- `0x18001104c`
- `0x1800130ec`
- `0x180015298`
- `0x180015408`
- `0x18001620c`
- `0x180018490`
- `0x1800225a0`
- `0x18004a640`
- `0x180053320`
- `0x1800558a0`
- `0x1800582b0`
- `0x18005ca70`
- `0x180062014`
- `0x180062230`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cc4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf20`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cc4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005ce2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cf20`

## pseudocode

```c
__int64 __fastcall SharingPlatform::SessionHost::OnData(
        SharingPlatform::SessionHost *this,
        __int64 a2,
        const unsigned __int8 *a3,
        __int64 a4)
{
  unsigned int v7; // r12d
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  int OverCallerManagedBuffer; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, struct Windows::Storage::Streams::IDataReader **); // rbx
  int v15; // eax
  __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  unsigned int v21; // ebx
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  RemoteSessionTraceProvider *v24; // rax
  __int64 v25; // rcx
  RemoteSessionTraceProvider *v26; // rax
  int v27; // eax
  int HostBinaryStream; // eax
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, __int64 *); // rdi
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  int v36; // edi
  unsigned int i; // ebx
  __int64 v38; // rax
  struct Windows::Storage::Streams::IBuffer **v40; // [rsp+20h] [rbp-C1h]
  struct Windows::Storage::Streams::IBuffer **v41; // [rsp+20h] [rbp-C1h]
  struct Windows::Storage::Streams::IBuffer **v42; // [rsp+20h] [rbp-C1h]
  int v43; // [rsp+20h] [rbp-C1h]
  unsigned __int8 v44[8]; // [rsp+30h] [rbp-B1h] BYREF
  HSTRING string; // [rsp+38h] [rbp-A9h] BYREF
  unsigned __int8 v46[8]; // [rsp+40h] [rbp-A1h] BYREF
  struct Windows::Storage::Streams::IDataReader *v47; // [rsp+48h] [rbp-99h] BYREF
  unsigned __int8 v48[8]; // [rsp+50h] [rbp-91h] BYREF
  __int64 v49; // [rsp+58h] [rbp-89h] BYREF
  struct Windows::Storage::Streams::IBuffer *v50; // [rsp+60h] [rbp-81h] BYREF
  __int64 v51; // [rsp+68h] [rbp-79h] BYREF
  struct ICDPBinaryHost *v52; // [rsp+70h] [rbp-71h] BYREF
  struct Windows::Storage::Streams::IBuffer *v53; // [rsp+78h] [rbp-69h] BYREF
  unsigned __int16 v54; // [rsp+80h] [rbp-61h] BYREF
  struct IInspectable *v55; // [rsp+88h] [rbp-59h] BYREF
  __int64 v56; // [rsp+90h] [rbp-51h] BYREF
  struct _GUID v57; // [rsp+98h] [rbp-49h] BYREF
  __int64 v58; // [rsp+A8h] [rbp-39h] BYREF
  int v59; // [rsp+B0h] [rbp-31h] BYREF
  int *v60; // [rsp+B8h] [rbp-29h]
  int v61; // [rsp+C0h] [rbp-21h] BYREF
  __m128i v62; // [rsp+C4h] [rbp-1Dh]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+47h]

  v55 = 0;
  v7 = (unsigned int)a3;
  v8 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
         (SharingPlatform::SessionHost *)((char *)this + 128),
         &v55);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( !v55 )
    {
      v9 = -2147467260;
      v11 = 692;
      v10 = 2147500036LL;
      goto LABEL_5;
    }
    *(_QWORD *)v48 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v48);
    OverCallerManagedBuffer = Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(
                                (Windows::Storage::Streams *)(unsigned int)a4,
                                a4,
                                v7,
                                v48,
                                v40);
    v9 = OverCallerManagedBuffer;
    if ( OverCallerManagedBuffer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B8,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)(unsigned int)OverCallerManagedBuffer,
        (int)v41);
LABEL_52:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v48);
      goto LABEL_53;
    }
    v13 = *((_QWORD *)this + 10);
    v47 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Storage::Streams::IDataReader **))(*(_QWORD *)v13 + 48LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v47);
    v15 = v14(v13, *(_QWORD *)v48, &v47);
    v9 = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 700;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)v16,
        (int)v41);
      goto LABEL_51;
    }
    v18 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(v47, &v54, v46, v44);
    v9 = v18;
    if ( v18 < 0 )
    {
      v16 = (unsigned int)v18;
      v17 = 708;
      goto LABEL_50;
    }
    if ( v54 != 2 || v46[0] != 1 )
    {
      v9 = -2147483637;
      v17 = 710;
      v16 = 2147483659LL;
      goto LABEL_50;
    }
    v21 = v44[0];
    if ( RemoteSessionTraceProvider::IsEnabled(v20, v19) )
    {
      v24 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                            v23,
                                            _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
      LODWORD(v41) = v21;
      RemoteSessionTraceProvider::LogVerbose_(
        v24,
        L"SessionHost OnData sessionId:%llx dataLength:%Iu messageType:%u",
        a2,
        a4,
        v41);
    }
    if ( v44[0] != 8 )
    {
      if ( RemoteSessionTraceProvider::IsEnabled(v23, v22) )
      {
        v26 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v25,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogWarning_(
          v26,
          L"SessionHost OnData cdpSession:%llx unknown message received MessageType:%u",
          a2,
          v21);
      }
      goto LABEL_48;
    }
    v51 = 0;
    string = 0;
    v50 = 0;
    v49 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v50);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v51);
    v27 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionStreamMessage(
            (_DWORD)v47,
            (unsigned int)&v57,
            (unsigned int)&v51,
            (unsigned int)&string,
            (__int64)&v50,
            (__int64)&v49);
    v9 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D7,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)(unsigned int)v27,
        (int)v42);
LABEL_37:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v50);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v51);
LABEL_51:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v47);
      goto LABEL_52;
    }
    v52 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v52);
    HostBinaryStream = SharingPlatform::SessionHost::FindHostBinaryStream(
                         (SharingPlatform::SessionHost *)((char *)this - 24),
                         string,
                         &v52);
    v9 = HostBinaryStream;
    if ( HostBinaryStream < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2DA,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)(unsigned int)HostBinaryStream,
        (int)v42);
LABEL_36:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v52);
      goto LABEL_37;
    }
    v53 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v53);
    v29 = Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(
            (Windows::Storage::Streams *)(unsigned int)a4,
            a4,
            v7,
            (unsigned __int8 *)&v53,
            v42);
    v9 = v29;
    if ( v29 < 0 )
    {
      v30 = 735;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)".\\sessionhost.cpp",
        (const char *)(unsigned int)v29,
        v43);
LABEL_35:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v53);
      goto LABEL_36;
    }
    v31 = v51;
    if ( !v51 )
    {
      v29 = SharingPlatform::SessionHost::SendBinaryHostMessageToAll(
              (SharingPlatform::SessionHost *)((char *)this - 24),
              v52,
              v53,
              &v57);
      v9 = v29;
      if ( v29 < 0 )
      {
        v30 = 740;
        goto LABEL_25;
      }
      ((void (__fastcall *)(struct IInspectable *, struct _GUID *, HSTRING, struct Windows::Storage::Streams::IBuffer *, __int64))v55->lpVtbl[2].QueryInterface)(
        v55,
        &v57,
        string,
        v50,
        v49);
LABEL_47:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v53);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v52);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v50);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v51);
LABEL_48:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v47);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v48);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v55);
      return 0;
    }
    v56 = 0;
    v32 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 64LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v56);
    v33 = v32(v31, &v56);
    v9 = v33;
    if ( v33 >= 0 )
    {
      v33 = SharingPlatform::SessionHost::SendBinaryHostMessageToParticipants(
              (int)this - 24,
              (_DWORD)v52,
              (_DWORD)v53,
              v56,
              (__int64)&v57);
      v9 = v33;
      if ( v33 >= 0 )
      {
        v60 = &v61;
        v58 = v51;
        v61 = 0;
        v62 = 0;
        v35 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v51 + 56LL))(v51, &v59);
        *v60 = v35;
        wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<_GUID>>::get_at_current(&v58, 0);
        v36 = v59;
        for ( i = 0;
              *v60 >= 0 && i != v36;
              wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<_GUID>>::get_at_current(&v58, i) )
        {
          v38 = v62.m128i_i64[0] - *((_QWORD *)this + 13);
          if ( v62.m128i_i64[0] == *((_QWORD *)this + 13) )
            v38 = _mm_srli_si128(v62, 8).m128i_u64[0] - *((_QWORD *)this + 14);
          if ( !v38 )
          {
            ((void (__fastcall *)(struct IInspectable *, struct _GUID *, HSTRING, struct Windows::Storage::Streams::IBuffer *, __int64))v55->lpVtbl[2].QueryInterface)(
              v55,
              &v57,
              string,
              v50,
              v49);
            break;
          }
          ++i;
        }
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v56);
        goto LABEL_47;
      }
      v34 = 751;
    }
    else
    {
      v34 = 748;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)".\\sessionhost.cpp",
      (const char *)(unsigned int)v33,
      v43);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v56);
    goto LABEL_35;
  }
  v10 = (unsigned int)v8;
  v11 = 691;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)".\\sessionhost.cpp",
    (const char *)v10,
    (int)v40);
LABEL_53:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v55);
  return v9;
}

```

## disassembly

```asm
0x18005ca70  push    rbp
0x18005ca72  push    rbx
0x18005ca73  push    rsi
0x18005ca74  push    rdi
0x18005ca75  push    r12
0x18005ca77  push    r13
0x18005ca79  push    r14
0x18005ca7b  push    r15
0x18005ca7d  lea     rbp, [rsp-7]
0x18005ca82  sub     rsp, 0E8h
0x18005ca89  mov     rax, cs:__security_cookie
0x18005ca90  xor     rax, rsp
0x18005ca93  mov     [rbp+3Fh+var_48], rax
0x18005ca97  mov     r14, rdx
0x18005ca9a  mov     r15, rcx
0x18005ca9d  xor     r13d, r13d
0x18005caa0  lea     rdx, [rbp+3Fh+var_98]; struct IInspectable **
0x18005caa4  sub     rcx, 0FFFFFFFFFFFFFF80h; this
0x18005caa8  mov     [rbp+3Fh+var_98], r13
0x18005caac  mov     rsi, r9
0x18005caaf  mov     r12, r8
0x18005cab2  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x18005cab7  mov     ebx, eax
0x18005cab9  test    eax, eax
0x18005cabb  jns     short loc_18005CAC7
0x18005cabd  mov     r9d, eax
0x18005cac0  mov     edx, 2B3h
0x18005cac5  jmp     short loc_18005CADA
0x18005cac7  cmp     [rbp+3Fh+var_98], r13
0x18005cacb  jnz     short loc_18005CAEF
0x18005cacd  mov     ebx, 80004004h
0x18005cad2  mov     edx, 2B4h; void *
0x18005cad7  mov     r9d, ebx; char *
0x18005cada  mov     rcx, [rbp+47h]; this
0x18005cade  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cae5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005caea  jmp     loc_18005CF86
0x18005caef  lea     rcx, [rsp+120h+var_D0]
0x18005caf4  mov     qword ptr [rsp+120h+var_D0], r13
0x18005caf9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cafe  lea     r9, [rsp+120h+var_D0]; unsigned __int8 *
0x18005cb03  mov     r8, r12; unsigned int
0x18005cb06  mov     edx, esi; unsigned int
0x18005cb08  mov     ecx, esi; this
0x18005cb0a  call    ?CBuffer_CreateOverCallerManagedBuffer@Streams@Storage@Windows@@YAJIIPEAEPEAPEAUIBuffer@123@@Z; Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(uint,uint,uchar *,Windows::Storage::Streams::IBuffer * *)
0x18005cb0f  mov     ebx, eax
0x18005cb11  test    eax, eax
0x18005cb13  jns     short loc_18005CB32
0x18005cb15  mov     rcx, [rbp+47h]; this
0x18005cb19  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cb20  mov     r9d, eax; char *
0x18005cb23  mov     edx, 2B8h; void *
0x18005cb28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb2d  jmp     loc_18005CF7C
0x18005cb32  mov     rdi, [r15+50h]
0x18005cb36  lea     rcx, [rsp+120h+var_D8]
0x18005cb3b  mov     [rsp+120h+var_D8], r13
0x18005cb40  mov     rax, [rdi]
0x18005cb43  mov     rbx, [rax+30h]
0x18005cb47  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cb4c  mov     rdx, qword ptr [rsp+120h+var_D0]
0x18005cb51  lea     r8, [rsp+120h+var_D8]
0x18005cb56  mov     rcx, rdi
0x18005cb59  mov     rax, rbx
0x18005cb5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cb61  mov     ebx, eax
0x18005cb63  test    eax, eax
0x18005cb65  jns     short loc_18005CB74
0x18005cb67  mov     r9d, eax
0x18005cb6a  mov     edx, 2BCh
0x18005cb6f  jmp     loc_18005CF62
0x18005cb74  mov     rcx, [rsp+120h+var_D8]; struct Windows::Storage::Streams::IDataReader *
0x18005cb79  lea     r9, [rsp+120h+var_F0]; unsigned __int8 *
0x18005cb7e  lea     r8, [rsp+120h+var_E0]; unsigned __int8 *
0x18005cb83  lea     rdx, [rbp+3Fh+var_A0]; unsigned __int16 *
0x18005cb87  call    ?ParseSessionMessageHeader@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAGPEAE2@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(Windows::Storage::Streams::IDataReader *,ushort *,uchar *,uchar *)
0x18005cb8c  mov     ebx, eax
0x18005cb8e  test    eax, eax
0x18005cb90  jns     short loc_18005CB9F
0x18005cb92  mov     r9d, eax
0x18005cb95  mov     edx, 2C4h
0x18005cb9a  jmp     loc_18005CF62
0x18005cb9f  cmp     [rbp+3Fh+var_A0], 2
0x18005cba4  jnz     loc_18005CF55
0x18005cbaa  cmp     [rsp+120h+var_E0], 1
0x18005cbaf  jnz     loc_18005CF55
0x18005cbb5  movzx   ebx, [rsp+120h+var_F0]
0x18005cbba  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18005cbbf  test    al, al
0x18005cbc1  jz      short loc_18005CBE8
0x18005cbc3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18005cbca  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x18005cbcf  mov     r9, rsi
0x18005cbd2  mov     dword ptr [rsp+120h+var_100], ebx
0x18005cbd6  mov     r8, r14
0x18005cbd9  lea     rdx, aSessionhostOnd_0; "SessionHost OnData sessionId:%llx dataL"...
0x18005cbe0  mov     rcx, rax; this
0x18005cbe3  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x18005cbe8  cmp     [rsp+120h+var_F0], 8
0x18005cbed  jz      short loc_18005CC22
0x18005cbef  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x18005cbf4  test    al, al
0x18005cbf6  jz      loc_18005CF34
0x18005cbfc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18005cc03  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x18005cc08  mov     r9d, ebx
0x18005cc0b  lea     rdx, aSessionhostOnd; "SessionHost OnData cdpSession:%llx unkn"...
0x18005cc12  mov     r8, r14
0x18005cc15  mov     rcx, rax; this
0x18005cc18  call    ?LogWarning_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogWarning_(ushort const *,...)
0x18005cc1d  jmp     loc_18005CF34
0x18005cc22  lea     rcx, [rsp+120h+var_C8]
0x18005cc27  mov     [rbp+3Fh+var_B8], r13
0x18005cc2b  mov     [rsp+120h+string], r13
0x18005cc30  mov     [rsp+120h+var_C0], r13
0x18005cc35  mov     [rsp+120h+var_C8], r13
0x18005cc3a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cc3f  lea     rcx, [rsp+120h+var_C0]
0x18005cc44  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cc49  mov     rcx, [rsp+120h+string]; string
0x18005cc4e  call    cs:__imp_WindowsDeleteString
0x18005cc54  lea     rcx, [rbp+3Fh+var_B8]
0x18005cc58  mov     [rsp+120h+string], r13
0x18005cc5d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cc62  mov     rcx, [rsp+120h+var_D8]
0x18005cc67  lea     rax, [rsp+120h+var_C8]
0x18005cc6c  mov     [rsp+120h+var_F8], rax
0x18005cc71  lea     r9, [rsp+120h+string]
0x18005cc76  lea     rax, [rsp+120h+var_C0]
0x18005cc7b  lea     r8, [rbp+3Fh+var_B8]
0x18005cc7f  mov     [rsp+120h+var_100], rax; int
0x18005cc84  lea     rdx, [rbp+3Fh+var_88]
0x18005cc88  call    ?ParseSessionStreamMessage@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAU_GUID@@PEAPEAU?$IVector@U_GUID@@@Collections@Foundation@7@PEAPEAUHSTRING__@@PEAPEAUIBuffer@567@4@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionStreamMessage(Windows::Storage::Streams::IDataReader *,_GUID *,Windows::Foundation::Collections::IVector<_GUID> * *,HSTRING__ * *,Windows::Storage::Streams::IBuffer * *,Windows::Storage::Streams::IBuffer * *)
0x18005cc8d  mov     ebx, eax
0x18005cc8f  test    eax, eax
0x18005cc91  jns     short loc_18005CCB0
0x18005cc93  mov     rcx, [rbp+47h]; this
0x18005cc97  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cc9e  mov     r9d, eax; char *
0x18005cca1  mov     edx, 2D7h; void *
0x18005cca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ccab  jmp     loc_18005CE12
0x18005ccb0  lea     rcx, [rbp+3Fh+var_B0]
0x18005ccb4  mov     [rbp+3Fh+var_B0], r13
0x18005ccb8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ccbd  mov     rdx, [rsp+120h+string]; HSTRING
0x18005ccc2  lea     r14, [r15-18h]
0x18005ccc6  mov     rcx, r14; this
0x18005ccc9  lea     r8, [rbp+3Fh+var_B0]; struct ICDPBinaryHost **
0x18005cccd  call    ?FindHostBinaryStream@SessionHost@SharingPlatform@@AEAAJPEAUHSTRING__@@PEAPEAVICDPBinaryHost@@@Z; SharingPlatform::SessionHost::FindHostBinaryStream(HSTRING__ *,ICDPBinaryHost * *)
0x18005ccd2  mov     ebx, eax
0x18005ccd4  test    eax, eax
0x18005ccd6  jns     short loc_18005CCF5
0x18005ccd8  mov     rcx, [rbp+47h]; this
0x18005ccdc  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cce3  mov     r9d, eax; char *
0x18005cce6  mov     edx, 2DAh; void *
0x18005cceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ccf0  jmp     loc_18005CE09
0x18005ccf5  lea     rcx, [rbp+3Fh+var_A8]
0x18005ccf9  mov     [rbp+3Fh+var_A8], r13
0x18005ccfd  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cd02  lea     r9, [rbp+3Fh+var_A8]; unsigned __int8 *
0x18005cd06  mov     r8, r12; unsigned int
0x18005cd09  mov     edx, esi; unsigned int
0x18005cd0b  mov     ecx, esi; this
0x18005cd0d  call    ?CBuffer_CreateOverCallerManagedBuffer@Streams@Storage@Windows@@YAJIIPEAEPEAPEAUIBuffer@123@@Z; Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(uint,uint,uchar *,Windows::Storage::Streams::IBuffer * *)
0x18005cd12  mov     ebx, eax
0x18005cd14  test    eax, eax
0x18005cd16  jns     short loc_18005CD35
0x18005cd18  mov     edx, 2DFh; void *
0x18005cd1d  mov     rcx, [rbp+47h]; this
0x18005cd21  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cd28  mov     r9d, eax; char *
0x18005cd2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cd30  jmp     loc_18005CE00
0x18005cd35  mov     rbx, [rbp+3Fh+var_B8]
0x18005cd39  test    rbx, rbx
0x18005cd3c  jnz     short loc_18005CD8C
0x18005cd3e  mov     r8, [rbp+3Fh+var_A8]; struct Windows::Storage::Streams::IBuffer *
0x18005cd42  lea     r9, [rbp+3Fh+var_88]; struct _GUID *
0x18005cd46  mov     rdx, [rbp+3Fh+var_B0]; struct ICDPBinaryHost *
0x18005cd4a  mov     rcx, r14; this
0x18005cd4d  call    ?SendBinaryHostMessageToAll@SessionHost@SharingPlatform@@AEAAJPEAVICDPBinaryHost@@PEAUIBuffer@Streams@Storage@Windows@@AEBU_GUID@@@Z; SharingPlatform::SessionHost::SendBinaryHostMessageToAll(ICDPBinaryHost *,Windows::Storage::Streams::IBuffer *,_GUID const &)
0x18005cd52  mov     ebx, eax
0x18005cd54  test    eax, eax
0x18005cd56  jns     short loc_18005CD5F
0x18005cd58  mov     edx, 2E4h
0x18005cd5d  jmp     short loc_18005CD1D
0x18005cd5f  mov     rdx, [rsp+120h+var_C8]
0x18005cd64  mov     rcx, [rbp+3Fh+var_98]
0x18005cd68  mov     r9, [rsp+120h+var_C0]
0x18005cd6d  mov     r8, [rsp+120h+string]
0x18005cd72  mov     [rsp+120h+var_100], rdx
0x18005cd77  lea     rdx, [rbp+3Fh+var_88]
0x18005cd7b  mov     rax, [rcx]
0x18005cd7e  mov     rax, [rax+60h]
0x18005cd82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd87  jmp     loc_18005CEF5
0x18005cd8c  mov     [rbp+3Fh+var_90], r13
0x18005cd90  lea     rcx, [rbp+3Fh+var_90]
0x18005cd94  mov     rax, [rbx]
0x18005cd97  mov     rdi, [rax+40h]
0x18005cd9b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cda0  lea     rdx, [rbp+3Fh+var_90]
0x18005cda4  mov     rcx, rbx
0x18005cda7  mov     rax, rdi
0x18005cdaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cdaf  mov     ebx, eax
0x18005cdb1  test    eax, eax
0x18005cdb3  jns     short loc_18005CDBC
0x18005cdb5  mov     edx, 2ECh
0x18005cdba  jmp     short loc_18005CDE4
0x18005cdbc  mov     r9, [rbp+3Fh+var_90]
0x18005cdc0  lea     rax, [rbp+3Fh+var_88]
0x18005cdc4  mov     r8, [rbp+3Fh+var_A8]
0x18005cdc8  mov     rcx, r14
0x18005cdcb  mov     rdx, [rbp+3Fh+var_B0]
0x18005cdcf  mov     [rsp+120h+var_100], rax; int
0x18005cdd4  call    ?SendBinaryHostMessageToParticipants@SessionHost@SharingPlatform@@AEAAJPEAVICDPBinaryHost@@PEAUIBuffer@Streams@Storage@Windows@@PEAU?$IVectorView@U_GUID@@@Collections@Foundation@7@AEBU_GUID@@@Z; SharingPlatform::SessionHost::SendBinaryHostMessageToParticipants(ICDPBinaryHost *,Windows::Storage::Streams::IBuffer *,Windows::Foundation::Collections::IVectorView<_GUID> *,_GUID const &)
0x18005cdd9  mov     ebx, eax
0x18005cddb  test    eax, eax
0x18005cddd  jns     short loc_18005CE44
0x18005cddf  mov     edx, 2EFh; void *
0x18005cde4  mov     rcx, [rbp+47h]; this
0x18005cde8  lea     r8, aSessionhostCpp; ".\\sessionhost.cpp"
0x18005cdef  mov     r9d, eax; char *
0x18005cdf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cdf7  lea     rcx, [rbp+3Fh+var_90]
0x18005cdfb  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce00  lea     rcx, [rbp+3Fh+var_A8]
0x18005ce04  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce09  lea     rcx, [rbp+3Fh+var_B0]
0x18005ce0d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce12  lea     rcx, [rsp+120h+var_C8]
0x18005ce17  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce1c  lea     rcx, [rsp+120h+var_C0]
0x18005ce21  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce26  mov     rcx, [rsp+120h+string]; string
0x18005ce2b  call    cs:__imp_WindowsDeleteString
0x18005ce31  lea     rcx, [rbp+3Fh+var_B8]
0x18005ce35  mov     [rsp+120h+string], r13
0x18005ce3a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005ce3f  jmp     loc_18005CF72
0x18005ce44  mov     rcx, [rbp+3Fh+var_B8]
0x18005ce48  lea     rax, [rbp+3Fh+var_60]
0x18005ce4c  mov     [rbp+3Fh+var_68], rax
0x18005ce50  lea     rdx, [rbp+3Fh+var_70]
0x18005ce54  xorps   xmm0, xmm0
0x18005ce57  mov     [rbp+3Fh+var_78], rcx
0x18005ce5b  mov     [rbp+3Fh+var_60], r13d
0x18005ce5f  movups  [rbp+3Fh+var_5C], xmm0
0x18005ce63  mov     rax, [rcx]
0x18005ce66  mov     rax, [rax+38h]
0x18005ce6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce6f  mov     rcx, [rbp+3Fh+var_68]
0x18005ce73  xor     edx, edx
0x18005ce75  mov     [rcx], eax
0x18005ce77  lea     rcx, [rbp+3Fh+var_78]
0x18005ce7b  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@U_GUID@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<_GUID>>::get_at_current(uint)
0x18005ce80  mov     edi, [rbp+3Fh+var_70]
0x18005ce83  mov     ebx, r13d
0x18005ce86  mov     rax, [rbp+3Fh+var_68]
0x18005ce8a  cmp     [rax], r13d
0x18005ce8d  jl      short loc_18005CEEC
0x18005ce8f  cmp     ebx, edi
0x18005ce91  jz      short loc_18005CEEC
0x18005ce93  movups  xmm0, [rbp+3Fh+var_5C]
0x18005ce97  movq    rax, xmm0
0x18005ce9c  sub     rax, [r15+68h]
0x18005cea0  jnz     short loc_18005CEB0
0x18005cea2  psrldq  xmm0, 8
0x18005cea7  movq    rax, xmm0
0x18005ceac  sub     rax, [r15+70h]
0x18005ceb0  test    rax, rax
0x18005ceb3  jz      short loc_18005CEC4
0x18005ceb5  inc     ebx
0x18005ceb7  lea     rcx, [rbp+3Fh+var_78]
0x18005cebb  mov     edx, ebx
0x18005cebd  call    ?get_at_current@?$vector_range_nothrow@U?$IVectorView@U_GUID@@@Collections@Foundation@Windows@@@wil@@QEAAXI@Z; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<_GUID>>::get_at_current(uint)
0x18005cec2  jmp     short loc_18005CE86
0x18005cec4  mov     rdx, [rsp+120h+var_C8]
0x18005cec9  mov     rcx, [rbp+3Fh+var_98]
0x18005cecd  mov     r9, [rsp+120h+var_C0]
0x18005ced2  mov     r8, [rsp+120h+string]
0x18005ced7  mov     [rsp+120h+var_100], rdx
0x18005cedc  lea     rdx, [rbp+3Fh+var_88]
0x18005cee0  mov     rax, [rcx]
0x18005cee3  mov     rax, [rax+60h]
0x18005cee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceec  lea     rcx, [rbp+3Fh+var_90]
0x18005cef0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cef5  lea     rcx, [rbp+3Fh+var_A8]
0x18005cef9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cefe  lea     rcx, [rbp+3Fh+var_B0]
0x18005cf02  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cf07  lea     rcx, [rsp+120h+var_C8]
0x18005cf0c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005cf11  lea     rcx, [rsp+120h+var_C0]
0x18005cf16  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
  ... truncated ...
```
