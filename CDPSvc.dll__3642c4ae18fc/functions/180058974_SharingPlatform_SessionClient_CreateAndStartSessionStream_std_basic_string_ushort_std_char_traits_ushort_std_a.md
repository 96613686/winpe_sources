# SharingPlatform::SessionClient::CreateAndStartSessionStream(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,SharingPlatform::CDPBinaryClientContainer *)

- ea: `0x180058974`
- end: `0x180058c99`
- name: `?CreateAndStartSessionStream@SessionClient@SharingPlatform@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDPBinaryClientContainer@2@@Z`
- size: `805`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011530`
- `0x180058340`
- `0x18005885c`

## callees

- `0x180004928`
- `0x180006668`
- `0x180010c58`
- `0x1800130ec`
- `0x1800225a0`
- `0x1800571d8`
- `0x180057648`
- `0x180057824`
- `0x1800578f0`
- `0x180058974`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058c49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058b58`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180058c49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058ac6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180058ac6`
- `cdp!CDPCreateBinaryClientInternal` at `0x1800589f3`
- `cdp!CDPCreateBinaryClientInternal` at `0x1800589f3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::SessionClient::CreateAndStartSessionStream(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *v6; // r15
  int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rcx
  char *v13; // r8
  __int64 v14; // rcx
  _QWORD *v15; // r8
  int v16; // eax
  unsigned __int8 v17; // cl
  int v18; // edi
  int v20; // [rsp+20h] [rbp-69h]
  unsigned __int16 v21; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int16 v22; // [rsp+72h] [rbp-17h] BYREF
  unsigned __int16 v23; // [rsp+74h] [rbp-15h] BYREF
  unsigned __int16 v24; // [rsp+76h] [rbp-13h] BYREF
  unsigned __int16 v25; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 v26; // [rsp+7Ah] [rbp-Fh] BYREF
  unsigned __int16 v27; // [rsp+7Ch] [rbp-Dh] BYREF
  unsigned __int16 v28; // [rsp+7Eh] [rbp-Bh] BYREF
  __int64 v29; // [rsp+80h] [rbp-9h] BYREF
  __int64 v30; // [rsp+88h] [rbp-1h] BYREF
  _QWORD *v31; // [rsp+90h] [rbp+7h] BYREF
  _QWORD v32[4]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v30 = a1;
  v6 = a3 + 1;
  Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(a3 + 1);
  v7 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryClientCallback,SharingPlatform::Internal::CDPBinaryClientCallback,SharingPlatform::SessionClient *>(
         v6,
         &v30);
  if ( v7 >= 0 )
  {
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(a3);
    v7 = CDPCreateBinaryClientInternal(a3);
    if ( v7 < 0 )
    {
      v8 = 380;
      goto LABEL_3;
    }
    v30 = 0;
    v31 = (_QWORD *)a1;
    v9 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPClientAuthorizationProvider,ICDPClientAuthorizationProvider,SharingPlatform::SessionClient *>(
           &v30,
           &v31);
    v7 = v9;
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*a3 + 48LL))(*a3, v30);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v29 = 0;
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
        v11 = *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId;
        if ( *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId )
        {
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
                                         + 8LL))(*(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId);
          v11 = *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId;
        }
        v29 = v11;
        if ( a2[3] <= 7u )
          v12 = a2;
        else
          v12 = (_QWORD *)*a2;
        v13 = (char *)v12 + 2 * a2[2];
        if ( a2[3] > 7u )
          a2 = (_QWORD *)*a2;
        std::string::string(v32, a2, v13);
        EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
        if ( *(_DWORD *)(a1 + 576) && (v14 = *(_QWORD *)(a1 + 488)) != 0 )
        {
          v15 = v32;
          if ( v32[3] > 0xFu )
            v15 = (_QWORD *)v32[0];
          v16 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *, _QWORD *))(*(_QWORD *)v14 + 40LL))(
                  v14,
                  v29,
                  v15,
                  a3 + 3);
          v18 = v16;
          if ( v16 >= 0 )
          {
            if ( a1 != -56 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
            v31 = a3 + 5;
            v21 = *(unsigned __int8 *)(a1 + 111);
            v22 = *(unsigned __int8 *)(a1 + 110);
            v23 = *(unsigned __int8 *)(a1 + 109);
            v24 = *(unsigned __int8 *)(a1 + 108);
            v25 = *(unsigned __int8 *)(a1 + 107);
            v26 = *(unsigned __int8 *)(a1 + 106);
            v27 = *(unsigned __int8 *)(a1 + 105);
            v28 = *(unsigned __int8 *)(a1 + 104);
            RemoteSessionTraceProvider::LogVerbose<unsigned short const (&)[130],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,char const *>(
              v17,
              (unsigned int *)(a1 + 96),
              (unsigned __int16 *)(a1 + 100),
              (unsigned __int16 *)(a1 + 102),
              &v28,
              &v27,
              &v26,
              &v25,
              &v24,
              &v23,
              &v22,
              &v21,
              &v31);
            v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *, __int64))(*(_QWORD *)*a3 + 24LL))(
                   *a3,
                   a3 + 3,
                   (*v6 + 8LL) & -(__int64)(*v6 != 0));
            std::string::~string(v32);
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x190,
              (unsigned int)".\\sessionclient.cpp",
              (const char *)(unsigned int)v16,
              v20);
            if ( a1 != -56 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
            std::string::~string(v32);
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
            v7 = v18;
          }
        }
        else
        {
          if ( a1 != -56 )
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
          std::string::~string(v32);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
          v7 = -2147019873;
        }
        goto LABEL_32;
      }
      v10 = 385;
    }
    else
    {
      v10 = 384;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)(unsigned int)v9,
      v20);
LABEL_32:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
    return (unsigned int)v7;
  }
  v8 = 379;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)".\\sessionclient.cpp",
    (const char *)(unsigned int)v7,
    v20);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180058974  mov     [rsp-8+arg_8], rbx
0x180058979  mov     [rsp-8+arg_18], rsi
0x18005897e  push    rbp
0x18005897f  push    rdi
0x180058980  push    r13
0x180058982  push    r14
0x180058984  push    r15
0x180058986  lea     rbp, [rsp-37h]
0x18005898b  sub     rsp, 0C0h
0x180058992  mov     rax, cs:__security_cookie
0x180058999  xor     rax, rsp
0x18005899c  mov     [rbp+57h+var_28], rax
0x1800589a0  mov     r14, r8
0x1800589a3  mov     rdi, rdx
0x1800589a6  mov     rsi, rcx
0x1800589a9  mov     [rbp+57h+var_58], rcx
0x1800589ad  lea     r15, [r8+8]
0x1800589b1  mov     rcx, r15
0x1800589b4  call    ?InternalRelease@?$ComPtr@VCDPBinaryClientCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(void)
0x1800589b9  lea     rdx, [rbp+57h+var_58]
0x1800589bd  mov     rcx, r15
0x1800589c0  call    ??$MakeAndInitialize@VCDPBinaryClientCallback@Internal@SharingPlatform@@V123@PEAVSessionClient@3@@Details@WRL@Microsoft@@YAJPEAPEAVCDPBinaryClientCallback@Internal@SharingPlatform@@$$QEAPEAVSessionClient@5@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryClientCallback,SharingPlatform::Internal::CDPBinaryClientCallback,SharingPlatform::SessionClient *>(SharingPlatform::Internal::CDPBinaryClientCallback * *,SharingPlatform::SessionClient * &&)
0x1800589c5  mov     ebx, eax
0x1800589c7  test    eax, eax
0x1800589c9  jns     short loc_1800589E8
0x1800589cb  mov     edx, 17Bh; void *
0x1800589d0  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x1800589d7  mov     r9d, ebx; char *
0x1800589da  mov     rcx, [rbp+5Fh]; this
0x1800589de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800589e3  jmp     loc_180058C6F
0x1800589e8  mov     rcx, r14
0x1800589eb  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800589f0  mov     rcx, r14
0x1800589f3  call    cs:__imp_CDPCreateBinaryClientInternal
0x1800589f9  mov     ebx, eax
0x1800589fb  test    eax, eax
0x1800589fd  jns     short loc_180058A06
0x1800589ff  mov     edx, 17Ch
0x180058a04  jmp     short loc_1800589D0
0x180058a06  mov     [rbp+57h+var_58], 0
0x180058a0e  mov     [rbp+57h+var_50], rsi
0x180058a12  lea     rdx, [rbp+57h+var_50]
0x180058a16  lea     rcx, [rbp+57h+var_58]
0x180058a1a  call    ??$MakeAndInitialize@VCDPClientAuthorizationProvider@Internal@SharingPlatform@@VICDPClientAuthorizationProvider@@PEAVSessionClient@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPClientAuthorizationProvider@@$$QEAPEAVSessionClient@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPClientAuthorizationProvider,ICDPClientAuthorizationProvider,SharingPlatform::SessionClient *>(ICDPClientAuthorizationProvider * *,SharingPlatform::SessionClient * &&)
0x180058a1f  mov     ebx, eax
0x180058a21  test    eax, eax
0x180058a23  jns     short loc_180058A2C
0x180058a25  mov     edx, 180h
0x180058a2a  jmp     short loc_180058A4A
0x180058a2c  mov     rcx, [r14]
0x180058a2f  mov     rax, [rcx]
0x180058a32  mov     rdx, [rbp+57h+var_58]
0x180058a36  mov     rax, [rax+30h]
0x180058a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a3f  mov     ebx, eax
0x180058a41  test    eax, eax
0x180058a43  jns     short loc_180058A62
0x180058a45  mov     edx, 181h; void *
0x180058a4a  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180058a51  mov     r9d, eax; char *
0x180058a54  mov     rcx, [rbp+5Fh]; this
0x180058a58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058a5d  jmp     loc_180058C66
0x180058a62  mov     [rbp+57h+var_60], 0
0x180058a6a  lea     rcx, [rbp+57h+var_60]
0x180058a6e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058a73  nop
0x180058a74  mov     rcx, cs:?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x180058a7b  test    rcx, rcx
0x180058a7e  jz      short loc_180058A93
0x180058a80  mov     rax, [rcx]
0x180058a83  mov     rax, [rax+8]
0x180058a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058a8c  mov     rcx, cs:?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x180058a93  mov     [rbp+57h+var_60], rcx
0x180058a97  cmp     qword ptr [rdi+18h], 7
0x180058a9c  jbe     short loc_180058AA3
0x180058a9e  mov     rcx, [rdi]
0x180058aa1  jmp     short loc_180058AA6
0x180058aa3  mov     rcx, rdi
0x180058aa6  mov     rax, [rdi+10h]
0x180058aaa  lea     r8, [rcx+rax*2]
0x180058aae  jbe     short loc_180058AB3
0x180058ab0  mov     rdi, [rdi]
0x180058ab3  mov     rdx, rdi
0x180058ab6  lea     rcx, [rbp+57h+var_48]
0x180058aba  call    ??$?0V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@$0A@@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@1@0AEBV?$allocator@D@1@@Z; std::string::string(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::allocator<char> const &)
0x180058abf  lea     rbx, [rsi+38h]
0x180058ac3  mov     rcx, rbx; lpCriticalSection
0x180058ac6  call    cs:__imp_EnterCriticalSection
0x180058acc  cmp     dword ptr [rsi+240h], 0
0x180058ad3  jz      loc_180058C41
0x180058ad9  mov     rcx, [rsi+1E8h]
0x180058ae0  test    rcx, rcx
0x180058ae3  jz      loc_180058C41
0x180058ae9  mov     rax, [rcx]
0x180058aec  lea     r8, [rbp+57h+var_48]
0x180058af0  cmp     [rbp+57h+var_30], 0Fh
0x180058af5  cmova   r8, [rbp+57h+var_48]
0x180058afa  lea     r9, [r14+18h]
0x180058afe  mov     rdx, [rbp+57h+var_60]
0x180058b02  mov     rax, [rax+28h]
0x180058b06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b0b  mov     edi, eax
0x180058b0d  test    eax, eax
0x180058b0f  jns     short loc_180058B50
0x180058b11  mov     rcx, [rbp+5Fh]; this
0x180058b15  mov     r9d, eax; char *
0x180058b18  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180058b1f  mov     edx, 190h; void *
0x180058b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058b29  test    rbx, rbx
0x180058b2c  jz      short loc_180058B37
0x180058b2e  mov     rcx, rbx; lpCriticalSection
0x180058b31  call    cs:__imp_LeaveCriticalSection
0x180058b37  lea     rcx, [rbp+57h+var_48]
0x180058b3b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180058b40  lea     rcx, [rbp+57h+var_60]
0x180058b44  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058b49  mov     ebx, edi
0x180058b4b  jmp     loc_180058C66
0x180058b50  test    rbx, rbx
0x180058b53  jz      short loc_180058B5E
0x180058b55  mov     rcx, rbx; lpCriticalSection
0x180058b58  call    cs:__imp_LeaveCriticalSection
0x180058b5e  lea     rax, [r14+28h]
0x180058b62  mov     [rbp+57h+var_50], rax
0x180058b66  movzx   eax, byte ptr [rsi+6Fh]
0x180058b6a  mov     [rbp+57h+var_70], ax
0x180058b6e  movzx   eax, byte ptr [rsi+6Eh]
0x180058b72  mov     [rbp+57h+var_6E], ax
0x180058b76  movzx   eax, byte ptr [rsi+6Dh]
0x180058b7a  mov     [rbp+57h+var_6C], ax
0x180058b7e  movzx   eax, byte ptr [rsi+6Ch]
0x180058b82  mov     [rbp+57h+var_6A], ax
0x180058b86  movzx   eax, byte ptr [rsi+6Bh]
0x180058b8a  mov     [rbp+57h+var_68], ax
0x180058b8e  movzx   eax, byte ptr [rsi+6Ah]
0x180058b92  mov     [rbp+57h+var_66], ax
0x180058b96  movzx   eax, byte ptr [rsi+69h]
0x180058b9a  mov     [rbp+57h+var_64], ax
0x180058b9e  movzx   eax, byte ptr [rsi+68h]
0x180058ba2  mov     [rbp+57h+var_62], ax
0x180058ba6  lea     rdx, [rsi+60h]
0x180058baa  lea     r9, [rdx+6]
0x180058bae  lea     r8, [rdx+4]
0x180058bb2  lea     rax, [rbp+57h+var_50]
0x180058bb6  mov     [rsp+0E0h+var_80], rax
0x180058bbb  lea     rax, [rbp+57h+var_70]
0x180058bbf  mov     [rsp+0E0h+var_88], rax
0x180058bc4  lea     rax, [rbp+57h+var_6E]
0x180058bc8  mov     [rsp+0E0h+var_90], rax
0x180058bcd  lea     rax, [rbp+57h+var_6C]
0x180058bd1  mov     [rsp+0E0h+var_98], rax
0x180058bd6  lea     rax, [rbp+57h+var_6A]
0x180058bda  mov     [rsp+0E0h+var_A0], rax
0x180058bdf  lea     rax, [rbp+57h+var_68]
0x180058be3  mov     [rsp+0E0h+var_A8], rax
0x180058be8  lea     rax, [rbp+57h+var_66]
0x180058bec  mov     [rsp+0E0h+var_B0], rax
0x180058bf1  lea     rax, [rbp+57h+var_64]
0x180058bf5  mov     [rsp+0E0h+var_B8], rax
0x180058bfa  lea     rax, [rbp+57h+var_62]
0x180058bfe  mov     [rsp+0E0h+var_C0], rax
0x180058c03  call    ??$LogVerbose@AEAY0IC@$$CBGAEAKAEAGAEAGGGGGGGGGPEBD@RemoteSessionTraceProvider@@SAXAEAY0IC@$$CBGAEAKAEAG2$$QEAG3333333$$QEAPEBD@Z; RemoteSessionTraceProvider::LogVerbose<ushort const (&)[130],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort,char const *>(ushort const (&)[130],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,char const * &&)
0x180058c08  mov     rcx, [r14]
0x180058c0b  mov     r8, [r15]
0x180058c0e  mov     r9, [rcx]
0x180058c11  lea     rax, [r8+8]
0x180058c15  neg     r8
0x180058c18  sbb     r8, r8
0x180058c1b  and     r8, rax
0x180058c1e  lea     rdx, [r14+18h]
0x180058c22  mov     rax, [r9+18h]
0x180058c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058c2b  mov     ebx, eax
0x180058c2d  lea     rcx, [rbp+57h+var_48]
0x180058c31  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180058c36  lea     rcx, [rbp+57h+var_60]
0x180058c3a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058c3f  jmp     short loc_180058C66
0x180058c41  test    rbx, rbx
0x180058c44  jz      short loc_180058C4F
0x180058c46  mov     rcx, rbx; lpCriticalSection
0x180058c49  call    cs:__imp_LeaveCriticalSection
0x180058c4f  lea     rcx, [rbp+57h+var_48]
0x180058c53  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180058c58  lea     rcx, [rbp+57h+var_60]
0x180058c5c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058c61  mov     ebx, 8007139Fh
0x180058c66  lea     rcx, [rbp+57h+var_58]
0x180058c6a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180058c6f  mov     eax, ebx
0x180058c71  mov     rcx, [rbp+57h+var_28]
0x180058c75  xor     rcx, rsp; StackCookie
0x180058c78  call    __security_check_cookie
0x180058c7d  lea     r11, [rsp+0E0h+var_20]
0x180058c85  mov     rbx, [r11+38h]
0x180058c89  mov     rsi, [r11+48h]
0x180058c8d  mov     rsp, r11
0x180058c90  pop     r15
0x180058c92  pop     r14
0x180058c94  pop     r13
0x180058c96  pop     rdi
0x180058c97  pop     rbp
0x180058c98  retn
```
