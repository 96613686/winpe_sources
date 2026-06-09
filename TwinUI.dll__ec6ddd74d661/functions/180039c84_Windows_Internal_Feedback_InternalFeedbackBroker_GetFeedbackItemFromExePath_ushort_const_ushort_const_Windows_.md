# Windows::Internal::Feedback::InternalFeedbackBroker::GetFeedbackItemFromExePath(ushort const *,ushort const *,Windows::Internal::Feedback::IFeedbackItem * *)

- ea: `0x180039c84`
- end: `0x18003a019`
- name: `?GetFeedbackItemFromExePath@InternalFeedbackBroker@Feedback@Internal@Windows@@AEAAJPEBG0PEAPEAUIFeedbackItem@234@@Z`
- size: `917`
- prototype: `int(Windows::Internal::Feedback::InternalFeedbackBroker *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Windows::Internal::Feedback::IFeedbackItem **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180234cc0`

## callees

- `0x180009dfc`
- `0x1800378dc`
- `0x180037958`
- `0x1800390a0`
- `0x1800398dc`
- `0x180039c84`
- `0x1800eefa4`
- `0x180142e34`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039e86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180039eca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ee2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039e54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180039ee2`
- `AEPIC!PicFreeFileInfo` at `0x180039f25`
- `AEPIC!PicFreeFileInfo` at `0x180039f25`
- `AEPIC!PicRetrieveFileInfo` at `0x180039ce9`
- `AEPIC!PicRetrieveFileInfo` at `0x180039ce9`

## string_xrefs

- `0x180039fed`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Feedback::InternalFeedbackBroker::GetFeedbackItemFromExePath(
        Windows::Internal::Feedback::InternalFeedbackBroker *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct Windows::Internal::Feedback::IFeedbackItem **a4)
{
  int HasPackageQueryCapability; // ebx
  PCNZWCH *v8; // rsi
  struct Windows::Internal::Feedback::IFeedbackItem *v9; // rcx
  char *v10; // rax
  char *v11; // rdi
  _QWORD *v12; // rbx
  HSTRING *v13; // r13
  HSTRING *v14; // r12
  const WCHAR *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rbx
  HRESULT String; // eax
  __int64 v19; // rbx
  __int64 v20; // rbx
  __int64 v21; // rdx
  struct Windows::Internal::Feedback::IFeedbackItem *v22; // rcx
  struct Windows::Internal::Feedback::IFeedbackItem *v24; // rcx
  __int64 v25; // rdx
  PCNZWCH *v26; // [rsp+20h] [rbp-38h] BYREF
  PCNZWCH v27; // [rsp+28h] [rbp-30h]
  PCNZWCH v28; // [rsp+30h] [rbp-28h]
  PCNZWCH sourceString; // [rsp+38h] [rbp-20h]
  __int64 v30[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  struct Windows::Internal::Feedback::IFeedbackItem *v32; // [rsp+A0h] [rbp+48h] BYREF

  v26 = 0;
  v32 = 0;
  HasPackageQueryCapability = Windows::Internal::Feedback::HasPackageQueryCapability(this);
  if ( HasPackageQueryCapability >= 0 )
  {
    if ( a2 )
    {
      if ( a3 )
      {
        if ( a4 )
        {
          *a4 = 0;
          HasPackageQueryCapability = PicRetrieveFileInfo(a2, 16400, &v26);
          if ( HasPackageQueryCapability < 0 )
            goto LABEL_41;
          v8 = v26;
          v9 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v9 + 16LL))(v9);
          }
          v32 = 0;
          v10 = (char *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
          v11 = v10;
          if ( v10 )
          {
            v12 = v10 + 16;
            Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v10 + 16));
            *((_QWORD *)v11 + 7) = 1;
            *(_QWORD *)v11 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable';
            *((_QWORD *)v11 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'};
            *v12 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            if ( Microsoft::WRL::Details::ModuleBase::module_ )
              (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                   + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
            *(_QWORD *)v11 = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable';
            *((_QWORD *)v11 + 1) = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `IWeakReferenceSource'};
            *v12 = &Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
            *((_QWORD *)v11 + 8) = 0;
            v13 = (HSTRING *)(v11 + 72);
            *((_QWORD *)v11 + 9) = 0;
            *((_QWORD *)v11 + 10) = 0;
            v14 = (HSTRING *)(v11 + 88);
            *((_QWORD *)v11 + 11) = 0;
            v30[0] = 0;
            v28 = *v8;
            v27 = v8[1];
            v15 = v8[2];
            sourceString = v15;
            v16 = -1;
            v17 = -1;
            do
              ++v17;
            while ( v15[v17] );
            WindowsDeleteString(0);
            *((_QWORD *)v11 + 8) = 0;
            String = WindowsCreateString(sourceString, v17, (HSTRING *)v11 + 8);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 24;
              goto LABEL_23;
            }
            v19 = -1;
            do
              ++v19;
            while ( v27[v19] );
            WindowsDeleteString(*v13);
            *v13 = 0;
            String = WindowsCreateString(v27, v19, (HSTRING *)v11 + 9);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 25;
              goto LABEL_23;
            }
            v20 = -1;
            do
              ++v20;
            while ( v28[v20] );
            WindowsDeleteString(*((HSTRING *)v11 + 10));
            *((_QWORD *)v11 + 10) = 0;
            String = WindowsCreateString(v28, v20, (HSTRING *)v11 + 10);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 26;
              goto LABEL_23;
            }
            do
              ++v16;
            while ( a3[v16] );
            WindowsDeleteString(*v14);
            *v14 = 0;
            String = WindowsCreateString(a3, v16, (HSTRING *)v11 + 11);
            HasPackageQueryCapability = String;
            if ( String < 0 )
            {
              v21 = 27;
LABEL_23:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v21,
                (unsigned int)"shell\\twinui\\feedback\\lib\\internalfeedbackhubapp.cpp",
                (const char *)(unsigned int)String,
                (int)v26);
              Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v11);
              Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(v30);
              goto LABEL_24;
            }
            v32 = (struct Windows::Internal::Feedback::IFeedbackItem *)v11;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v11 + 8LL))(v11);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(v11);
            HasPackageQueryCapability = 0;
          }
          else
          {
            HasPackageQueryCapability = -2147024882;
          }
LABEL_24:
          PicFreeFileInfo(v26);
          if ( HasPackageQueryCapability >= 0 )
          {
            v22 = 0;
            *a4 = v32;
            goto LABEL_26;
          }
LABEL_41:
          v22 = v32;
LABEL_26:
          if ( v22 )
          {
            v32 = 0;
            (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v22 + 16LL))(v22);
          }
          return (unsigned int)HasPackageQueryCapability;
        }
        v25 = 238;
      }
      else
      {
        v25 = 237;
      }
    }
    else
    {
      v25 = 236;
    }
    HasPackageQueryCapability = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"shell\\twinui\\feedback\\lib\\feedbackbroker.cpp",
      (const char *)0x80070057LL,
      (int)v26);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    return (unsigned int)HasPackageQueryCapability;
  }
  v24 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Feedback::IFeedbackItem *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return (unsigned int)HasPackageQueryCapability;
}

```

## disassembly

```asm
0x180039c84  mov     [rsp-40h+arg_0], rcx
0x180039c89  push    rbp
0x180039c8a  push    rbx
0x180039c8b  push    rsi
0x180039c8c  push    rdi
0x180039c8d  push    r12
0x180039c8f  push    r13
0x180039c91  push    r14
0x180039c93  push    r15
0x180039c95  mov     rbp, rsp
0x180039c98  sub     rsp, 58h
0x180039c9c  mov     r15, r9
0x180039c9f  mov     r14, r8
0x180039ca2  mov     rdi, rdx
0x180039ca5  xor     r13d, r13d
0x180039ca8  mov     [rbp+var_38], r13
0x180039cac  mov     [rbp+arg_0], r13
0x180039cb0  call    ?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ; Windows::Internal::Feedback::HasPackageQueryCapability(void)
0x180039cb5  mov     ebx, eax
0x180039cb7  test    eax, eax
0x180039cb9  js      loc_180039F8B
0x180039cbf  test    rdi, rdi
0x180039cc2  jz      loc_180039FD5
0x180039cc8  test    r14, r14
0x180039ccb  jz      loc_18003A008
0x180039cd1  test    r15, r15
0x180039cd4  jz      loc_180039FDC
0x180039cda  mov     [r15], r13
0x180039cdd  lea     r8, [rbp+var_38]
0x180039ce1  mov     edx, 4010h
0x180039ce6  mov     rcx, rdi
0x180039ce9  call    cs:__imp_PicRetrieveFileInfo
0x180039cf0  nop     dword ptr [rax+rax+00h]
0x180039cf5  mov     ebx, eax
0x180039cf7  test    eax, eax
0x180039cf9  js      loc_18003A00F
0x180039cff  mov     rsi, [rbp+var_38]
0x180039d03  mov     rcx, [rbp+arg_0]
0x180039d07  test    rcx, rcx
0x180039d0a  jz      short loc_180039D1D
0x180039d0c  mov     [rbp+arg_0], r13
0x180039d10  mov     rax, [rcx]
0x180039d13  mov     rax, [rax+10h]
0x180039d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d1c  nop
0x180039d1d  mov     [rbp+arg_0], r13
0x180039d21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039d28  mov     ecx, 60h ; '`'; unsigned __int64
0x180039d2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039d32  mov     rdi, rax
0x180039d35  test    rax, rax
0x180039d38  jz      loc_180039FCB
0x180039d3e  lea     rbx, [rax+10h]
0x180039d42  mov     rcx, rbx; this
0x180039d45  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180039d4a  mov     qword ptr [rdi+38h], 1
0x180039d52  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'
0x180039d59  mov     [rdi], rax
0x180039d5c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `IWeakReferenceSource'}
0x180039d63  mov     [rdi+8], rax
0x180039d67  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$00@WRL@Microsoft@@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<1>,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180039d6e  mov     [rbx], rax
0x180039d71  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180039d78  test    rcx, rcx
0x180039d7b  jz      short loc_180039D8A
0x180039d7d  mov     rax, [rcx]
0x180039d80  mov     rax, [rax+8]
0x180039d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d89  nop
0x180039d8a  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6B@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'
0x180039d91  mov     [rdi], rax
0x180039d94  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `IWeakReferenceSource'}
0x180039d9b  mov     [rdi+8], rax
0x180039d9f  lea     rax, ??_7InternalFeedbackItem@Feedback@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Feedback::InternalFeedbackItem::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180039da6  mov     [rbx], rax
0x180039da9  mov     [rdi+40h], r13
0x180039dad  lea     r13, [rdi+48h]
0x180039db1  xor     ecx, ecx; string
0x180039db3  mov     [r13+0], rcx
0x180039db7  mov     [rdi+50h], rcx
0x180039dbb  lea     r12, [rdi+58h]
0x180039dbf  mov     [r12], rcx
0x180039dc3  mov     [rbp+var_18], rcx
0x180039dc7  mov     rax, [rsi]
0x180039dca  mov     [rbp+var_28], rax
0x180039dce  mov     rax, [rsi+8]
0x180039dd2  mov     [rbp+var_30], rax
0x180039dd6  mov     rax, [rsi+10h]
0x180039dda  mov     [rbp+sourceString], rax
0x180039dde  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180039de2  mov     rbx, rsi
0x180039de5  inc     rbx
0x180039de8  cmp     [rax+rbx*2], cx
0x180039dec  jnz     short loc_180039DE5
0x180039dee  call    cs:__imp_WindowsDeleteString
0x180039df5  nop     dword ptr [rax+rax+00h]
0x180039dfa  lea     r8, [rdi+40h]; string
0x180039dfe  mov     qword ptr [r8], 0
0x180039e05  mov     edx, ebx; length
0x180039e07  mov     rcx, [rbp+sourceString]; sourceString
0x180039e0b  call    cs:__imp_WindowsCreateString
0x180039e12  nop     dword ptr [rax+rax+00h]
0x180039e17  mov     ebx, eax
0x180039e19  xor     ecx, ecx
0x180039e1b  test    eax, eax
0x180039e1d  js      loc_180039F74
0x180039e23  mov     rbx, rsi
0x180039e26  mov     rax, [rbp+var_30]
0x180039e2a  inc     rbx
0x180039e2d  cmp     [rax+rbx*2], cx
0x180039e31  jnz     short loc_180039E2A
0x180039e33  mov     rcx, [r13+0]; string
0x180039e37  call    cs:__imp_WindowsDeleteString
0x180039e3e  nop     dword ptr [rax+rax+00h]
0x180039e43  mov     qword ptr [r13+0], 0
0x180039e4b  mov     r8, r13; string
0x180039e4e  mov     edx, ebx; length
0x180039e50  mov     rcx, [rbp+var_30]; sourceString
0x180039e54  call    cs:__imp_WindowsCreateString
0x180039e5b  nop     dword ptr [rax+rax+00h]
0x180039e60  mov     ebx, eax
0x180039e62  xor     r13d, r13d
0x180039e65  test    eax, eax
0x180039e67  js      loc_180039F6D
0x180039e6d  mov     rbx, rsi
0x180039e70  mov     rax, [rbp+var_28]
0x180039e74  inc     rbx
0x180039e77  cmp     [rax+rbx*2], r13w
0x180039e7c  jnz     short loc_180039E74
0x180039e7e  lea     r13, [rdi+50h]
0x180039e82  mov     rcx, [r13+0]; string
0x180039e86  call    cs:__imp_WindowsDeleteString
0x180039e8d  nop     dword ptr [rax+rax+00h]
0x180039e92  mov     qword ptr [r13+0], 0
0x180039e9a  mov     r8, r13; string
0x180039e9d  mov     edx, ebx; length
0x180039e9f  mov     rcx, [rbp+var_28]; sourceString
0x180039ea3  call    cs:__imp_WindowsCreateString
0x180039eaa  nop     dword ptr [rax+rax+00h]
0x180039eaf  mov     ebx, eax
0x180039eb1  xor     r13d, r13d
0x180039eb4  test    eax, eax
0x180039eb6  js      loc_180039F81
0x180039ebc  inc     rsi
0x180039ebf  cmp     [r14+rsi*2], r13w
0x180039ec4  jnz     short loc_180039EBC
0x180039ec6  mov     rcx, [r12]; string
0x180039eca  call    cs:__imp_WindowsDeleteString
0x180039ed1  nop     dword ptr [rax+rax+00h]
0x180039ed6  mov     [r12], r13
0x180039eda  mov     r8, r12; string
0x180039edd  mov     edx, esi; length
0x180039edf  mov     rcx, r14; sourceString
0x180039ee2  call    cs:__imp_WindowsCreateString
0x180039ee9  nop     dword ptr [rax+rax+00h]
0x180039eee  mov     ebx, eax
0x180039ef0  test    eax, eax
0x180039ef2  jns     loc_180039FA7
0x180039ef8  mov     edx, 1Bh; void *
0x180039efd  mov     r9d, eax; char *
0x180039f00  lea     r8, aShellTwinuiFee_0; "shell\\twinui\\feedback\\lib\\internalf"...
0x180039f07  mov     rcx, [rbp+40h]; this
0x180039f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f10  mov     rcx, rdi
0x180039f13  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(void)
0x180039f18  lea     rcx, [rbp+var_18]
0x180039f1c  call    ??1?$MakeAllocator@VSttExperienceManagerFactory@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SttExperienceManagerFactory>::~MakeAllocator<SttExperienceManagerFactory>(void)
0x180039f21  mov     rcx, [rbp+var_38]
0x180039f25  call    cs:__imp_PicFreeFileInfo
0x180039f2c  nop     dword ptr [rax+rax+00h]
0x180039f31  test    ebx, ebx
0x180039f33  js      loc_18003A00F
0x180039f39  mov     rax, [rbp+arg_0]
0x180039f3d  mov     rcx, r13
0x180039f40  mov     [r15], rax
0x180039f43  test    rcx, rcx
0x180039f46  jz      short loc_180039F59
0x180039f48  mov     [rbp+arg_0], r13
0x180039f4c  mov     rax, [rcx]
0x180039f4f  mov     rax, [rax+10h]
0x180039f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039f58  nop
0x180039f59  mov     eax, ebx
0x180039f5b  add     rsp, 58h
0x180039f5f  pop     r15
0x180039f61  pop     r14
0x180039f63  pop     r13
0x180039f65  pop     r12
0x180039f67  pop     rdi
0x180039f68  pop     rsi
0x180039f69  pop     rbx
0x180039f6a  pop     rbp
0x180039f6b  retn
0x180039f6d  mov     edx, 19h
0x180039f72  jmp     short loc_180039EFD
0x180039f74  mov     edx, 18h
0x180039f79  xor     r13d, r13d
0x180039f7c  jmp     loc_180039EFD
0x180039f81  mov     edx, 1Ah
0x180039f86  jmp     loc_180039EFD
0x180039f8b  mov     rcx, [rbp+arg_0]
0x180039f8f  test    rcx, rcx
0x180039f92  jz      short loc_180039FA5
0x180039f94  mov     [rbp+arg_0], r13
0x180039f98  mov     rdx, [rcx]
0x180039f9b  mov     rax, [rdx+10h]
0x180039f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fa4  nop
0x180039fa5  jmp     short loc_180039F59
0x180039fa7  mov     [rbp+arg_0], rdi
0x180039fab  mov     rax, [rdi]
0x180039fae  mov     rcx, rdi
0x180039fb1  mov     rax, [rax+8]
0x180039fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039fba  nop
0x180039fbb  mov     rcx, rdi
0x180039fbe  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIFeedbackItem@Feedback@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Feedback::IFeedbackItem,Microsoft::WRL::FtmBase>::Release(void)
0x180039fc3  mov     ebx, r13d
0x180039fc6  jmp     loc_180039F21
0x180039fcb  mov     ebx, 8007000Eh
0x180039fd0  jmp     loc_180039F21
0x180039fd5  mov     edx, 0ECh
0x180039fda  jmp     short loc_180039FE1
0x180039fdc  mov     edx, 0EEh; void *
0x180039fe1  mov     ebx, 80070057h
0x180039fe6  mov     rcx, [rbp+40h]; this
0x180039fea  mov     r9d, ebx; char *
0x180039fed  lea     r8, aShellTwinuiFee; "shell\\twinui\\feedback\\lib\\feedbackb"...
0x180039ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039ff9  nop
0x180039ffa  lea     rcx, [rbp+arg_0]
0x180039ffe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a003  jmp     loc_180039F59
0x18003a008  mov     edx, 0EDh
0x18003a00d  jmp     short loc_180039FE1
0x18003a00f  mov     rcx, [rbp+arg_0]
0x18003a013  jmp     loc_180039F43
```
