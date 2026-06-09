# DataStoreCache::MRTTransformerData::ResolveSortName(HSTRING__ *,HSTRING__ *)

- ea: `0x18017eb50`
- end: `0x18017eede`
- name: `?ResolveSortName@MRTTransformerData@DataStoreCache@@UEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@0@Z`
- size: `910`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18000f898`
- `0x18000fba8`
- `0x18001dac0`
- `0x1800385d0`
- `0x18003b500`
- `0x1800c5b3c`
- `0x1800dd908`
- `0x1800f1040`
- `0x1800f1174`
- `0x1800f1288`
- `0x1800f2100`
- `0x1800f2278`
- `0x18011ebe0`
- `0x18017d9d0`
- `0x18017eb50`
- `0x18017eee4`
- `0x1801a6ce0`
- `0x1801bb6ec`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ed45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ed45`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee5b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18017ebee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18017ec02`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18017ebee`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18017ec02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ed81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ed99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ee70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017eea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ed81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ed99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017ee70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18017eea2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ecbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18017ecbf`

## string_xrefs

- `0x18017ebcf`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18017ec4e`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18017edad`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18017edfa`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18017eecc`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HSTRING *__fastcall DataStoreCache::MRTTransformerData::ResolveSortName(
        __int64 a1,
        HSTRING *a2,
        ShellMRTHelper::Common *a3,
        HSTRING a4)
{
  __int64 v8; // r15
  int v9; // eax
  HSTRING v10; // rdx
  bool IsResolvableStringReference; // r12
  int v12; // eax
  __int64 v13; // rsi
  __int64 v14; // rcx
  __int128 v15; // xmm6
  PCWSTR StringRawBuffer; // rbx
  __int64 v17; // rcx
  __int64 v18; // r8
  _QWORD *v19; // rax
  __int64 v20; // rax
  HSTRING v21; // r8
  HSTRING *v22; // rbx
  int v23; // eax
  int v25; // eax
  int v26; // [rsp+28h] [rbp-59h]
  int v27; // [rsp+28h] [rbp-59h]
  PSRWLOCK *v28; // [rsp+28h] [rbp-59h]
  HSTRING v29; // [rsp+38h] [rbp-49h] BYREF
  int v30; // [rsp+40h] [rbp-41h]
  HSTRING string[2]; // [rsp+48h] [rbp-39h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-29h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+68h] [rbp-19h] BYREF
  HSTRING v34[12]; // [rsp+78h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v34[1] = (HSTRING)a2;
  v34[0] = a4;
  v30 = 1;
  v8 = a1 + 152;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, a1 + 152);
  if ( *(_QWORD *)(a1 + 120) )
  {
    *a2 = 0;
    v30 = 1;
    string[0] = *(HSTRING *)(a1 + 120);
    v9 = Microsoft::WRL::Wrappers::HString::Set(a2, string);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)(unsigned int)v9,
        v26);
    if ( SRWLock[0] )
      ReleaseSRWLockShared(SRWLock[0]);
  }
  else
  {
    if ( SRWLock[0] )
      ReleaseSRWLockShared(SRWLock[0]);
    DataStoreCache::MRTTransformerData::ResolveText(a1 - 48, &v29, a3, 2, 0);
    IsResolvableStringReference = ShellMRTHelper::Common::IsResolvableStringReference(
                                    (ShellMRTHelper::Common *)v29,
                                    v10);
    v32[0] = 0;
    v12 = Microsoft::WRL::WeakRef::As<DataStoreCache::IMRTTransformerInternal>(a1 + 56, v32);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBE,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)(unsigned int)v12,
        v27);
    *a2 = 0;
    v30 = 3;
    if ( v32[0] )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, v8);
      v13 = a1 + 144;
      v14 = *(_QWORD *)(a1 + 144);
      if ( v14 && (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(v14 + 8) )
      {
        if ( *(_QWORD *)v13 )
          v15 = *(_OWORD *)(*(_QWORD *)v13 + 152LL);
        else
          v15 = 0;
      }
      else
      {
        StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1 + 80), 0);
        v17 = *(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::operator->(
                           a1 + 144,
                           string)
            + 272LL;
        v18 = -1;
        do
          ++v18;
        while ( StringRawBuffer[v18] );
        std::wstring::_Assign<unsigned short>(v17, StringRawBuffer);
        tip2::test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::~test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>(string);
        if ( *(_QWORD *)v13
          && (unsigned __int8)tip2::details::shared_data<1,0,0>::has_ever_started(*(_QWORD *)v13 + 8LL) )
        {
          wil::com_ptr_t<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>,wil::err_returncode_policy>::reset(a1 + 144);
        }
        v19 = (_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::ensure_data(a1 + 144);
        tip2::details::shared_data<1,0,0>::start(*v19 + 8LL, string);
        v15 = *(_OWORD *)string;
      }
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
      v20 = *(_QWORD *)v32[0];
      v21 = v29;
      if ( IsResolvableStringReference )
        v21 = 0;
      *(_OWORD *)SRWLock = v15;
      v28 = SRWLock;
      v22 = (HSTRING *)(*(__int64 (__fastcall **)(_QWORD, HSTRING *, HSTRING, HSTRING))(v20 + 56))(
                         v32[0],
                         string,
                         v21,
                         a4);
      WindowsDeleteString(*a2);
      *a2 = 0;
      *a2 = *v22;
      *v22 = 0;
      WindowsDeleteString(string[0]);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)0x8007139FLL,
        v27);
      v13 = a1 + 144;
    }
    if ( *a2 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, v8);
      string[0] = *a2;
      v23 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 120), string);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xDF,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
          (const char *)(unsigned int)v23,
          (int)v28);
      if ( *(_QWORD *)v13 )
      {
        if ( (unsigned __int8)tip2::details::shared_data<1,0,0>::is_running(*(_QWORD *)v13 + 8LL) )
        {
          *(_BYTE *)(*(_QWORD *)tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::operator->(
                                  v13,
                                  string)
                   + 304LL) = 1;
          tip2::test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::~test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>(string);
          if ( *(_QWORD *)v13 )
            tip2::details::shared_data<1,0,0>::complete_without_lock(*(_QWORD *)v13 + 8LL);
        }
      }
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
    }
    else if ( !v29 || IsResolvableStringReference )
    {
      v25 = Microsoft::WRL::Wrappers::HString::Set(a2, v34);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xF2,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
          (const char *)(unsigned int)v25,
          (int)v28);
    }
    else
    {
      WindowsDeleteString(0);
      *a2 = v29;
      v29 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v32);
    WindowsDeleteString(v29);
  }
  return a2;
}

```

## disassembly

```asm
0x18017eb50  mov     rax, rsp
0x18017eb53  push    rbp
0x18017eb54  push    rbx
0x18017eb55  push    rsi
0x18017eb56  push    rdi
0x18017eb57  push    r12
0x18017eb59  push    r13
0x18017eb5b  push    r14
0x18017eb5d  push    r15
0x18017eb5f  lea     rbp, [rax-5Fh]
0x18017eb63  sub     rsp, 98h
0x18017eb6a  movaps  xmmword ptr [rax-58h], xmm6
0x18017eb6e  mov     r13, r9
0x18017eb71  mov     rsi, r8
0x18017eb74  mov     rdi, rdx
0x18017eb77  mov     r14, rcx
0x18017eb7a  mov     qword ptr [rbp+57h+var_58], rdx
0x18017eb7e  mov     [rbp+57h+var_60], r9
0x18017eb82  mov     [rbp+57h+var_98], 1
0x18017eb89  lea     r15, [rcx+98h]
0x18017eb90  mov     rdx, r15
0x18017eb93  lea     rcx, [rbp+57h+SRWLock]
0x18017eb97  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18017eb9c  nop
0x18017eb9d  xor     r12d, r12d
0x18017eba0  cmp     [r14+78h], r12
0x18017eba4  jz      short loc_18017EBF9
0x18017eba6  mov     [rdi], r12
0x18017eba9  mov     [rbp+57h+var_98], 1
0x18017ebb0  mov     rax, [r14+78h]
0x18017ebb4  mov     [rbp+57h+string], rax
0x18017ebb8  lea     rdx, [rbp+57h+string]; HSTRING *
0x18017ebbc  mov     rcx, rdi; newString
0x18017ebbf  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18017ebc4  mov     rcx, [rbp+5Fh]; this
0x18017ebc8  test    eax, eax
0x18017ebca  jns     short loc_18017EBE1
0x18017ebcc  mov     r9d, eax; char *
0x18017ebcf  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18017ebd6  mov     edx, 0B3h; void *
0x18017ebdb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ebe1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18017ebe5  test    rcx, rcx
0x18017ebe8  jz      loc_18017EE76
0x18017ebee  call    cs:__imp_ReleaseSRWLockShared
0x18017ebf4  jmp     loc_18017EE76
0x18017ebf9  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18017ebfd  test    rcx, rcx
0x18017ec00  jz      short loc_18017EC08
0x18017ec02  call    cs:__imp_ReleaseSRWLockShared
0x18017ec08  mov     [rsp+20h], r12b; int
0x18017ec0d  mov     r9d, 2
0x18017ec13  mov     r8, rsi
0x18017ec16  lea     rdx, [rbp+57h+var_A0]
0x18017ec1a  lea     rcx, [r14-30h]
0x18017ec1e  call    ?ResolveText@MRTTransformerData@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@W4TextType@12@_N@Z; DataStoreCache::MRTTransformerData::ResolveText(HSTRING__ *,DataStoreCache::MRTTransformerData::TextType,bool)
0x18017ec23  nop
0x18017ec24  mov     rcx, [rbp+57h+var_A0]; this
0x18017ec28  call    ?IsResolvableStringReference@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::IsResolvableStringReference(HSTRING__ *)
0x18017ec2d  mov     r12b, al
0x18017ec30  xor     ebx, ebx
0x18017ec32  mov     [rbp+57h+var_80], rbx
0x18017ec36  lea     rcx, [r14+38h]
0x18017ec3a  lea     rdx, [rbp+57h+var_80]
0x18017ec3e  call    ??$As@UIMRTTransformerInternal@DataStoreCache@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMRTTransformerInternal@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<DataStoreCache::IMRTTransformerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::IMRTTransformerInternal>>)
0x18017ec43  mov     rcx, [rbp+5Fh]; this
0x18017ec47  test    eax, eax
0x18017ec49  jns     short loc_18017EC60
0x18017ec4b  mov     r9d, eax; char *
0x18017ec4e  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18017ec55  mov     edx, 0BEh; void *
0x18017ec5a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ec60  mov     [rdi], rbx
0x18017ec63  mov     [rbp+57h+var_98], 3
0x18017ec6a  cmp     [rbp+57h+var_80], rbx
0x18017ec6e  jz      loc_18017EDA3
0x18017ec74  mov     rdx, r15
0x18017ec77  lea     rcx, [rbp+57h+SRWLock]
0x18017ec7b  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18017ec80  nop
0x18017ec81  lea     rsi, [r14+90h]
0x18017ec88  mov     rcx, [rsi]
0x18017ec8b  test    rcx, rcx
0x18017ec8e  jz      short loc_18017ECB9
0x18017ec90  add     rcx, 8
0x18017ec94  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18017ec99  test    al, al
0x18017ec9b  jz      short loc_18017ECB9
0x18017ec9d  mov     rax, [rsi]
0x18017eca0  test    rax, rax
0x18017eca3  jz      short loc_18017ECB1
0x18017eca5  movups  xmm6, xmmword ptr [rax+98h]
0x18017ecac  jmp     loc_18017ED3C
0x18017ecb1  xorps   xmm6, xmm6
0x18017ecb4  jmp     loc_18017ED3C
0x18017ecb9  xor     edx, edx; length
0x18017ecbb  mov     rcx, [r14+50h]; string
0x18017ecbf  call    cs:__imp_WindowsGetStringRawBuffer
0x18017ecc5  mov     rbx, rax
0x18017ecc8  lea     rdx, [rbp+57h+string]
0x18017eccc  mov     rcx, rsi
0x18017eccf  call    ??C?$tip_test@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::operator->(void)
0x18017ecd4  nop
0x18017ecd5  mov     rcx, [rax]
0x18017ecd8  add     rcx, 110h
0x18017ecdf  or      r8, 0FFFFFFFFFFFFFFFFh
0x18017ece3  xor     eax, eax
0x18017ece5  inc     r8
0x18017ece8  cmp     [rbx+r8*2], ax
0x18017eced  jnz     short loc_18017ECE5
0x18017ecef  mov     rdx, rbx
0x18017ecf2  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18017ecf7  nop
0x18017ecf8  lea     rcx, [rbp+57h+string]
0x18017ecfc  call    ??1?$test_data_control@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::~test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>(void)
0x18017ed01  mov     rcx, [rsi]
0x18017ed04  xor     ebx, ebx
0x18017ed06  test    rcx, rcx
0x18017ed09  jz      short loc_18017ED20
0x18017ed0b  add     rcx, 8
0x18017ed0f  call    ?has_ever_started@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::has_ever_started(void)
0x18017ed14  test    al, al
0x18017ed16  jz      short loc_18017ED20
0x18017ed18  mov     rcx, rsi
0x18017ed1b  call    ?reset@?$com_ptr_t@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>,wil::err_returncode_policy>::reset(void)
0x18017ed20  mov     rcx, rsi
0x18017ed23  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::ensure_data(void)
0x18017ed28  mov     rcx, [rax]
0x18017ed2b  add     rcx, 8
0x18017ed2f  lea     rdx, [rbp+57h+string]
0x18017ed33  call    ?start@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<1,0,0>::start(void)
0x18017ed38  movaps  xmm6, xmmword ptr [rbp+57h+string]
0x18017ed3c  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18017ed40  test    rcx, rcx
0x18017ed43  jz      short loc_18017ED4B
0x18017ed45  call    cs:__imp_ReleaseSRWLockExclusive
0x18017ed4b  mov     rcx, [rbp+57h+var_80]
0x18017ed4f  mov     rax, [rcx]
0x18017ed52  mov     r8, [rbp+57h+var_A0]
0x18017ed56  test    r12b, r12b
0x18017ed59  cmovnz  r8, rbx
0x18017ed5d  movdqa  xmmword ptr [rbp+57h+SRWLock], xmm6
0x18017ed62  lea     rdx, [rbp+57h+SRWLock]
0x18017ed66  mov     [rsp+20h], rdx
0x18017ed6b  mov     r9, r13
0x18017ed6e  lea     rdx, [rbp+57h+string]
0x18017ed72  mov     rax, [rax+38h]
0x18017ed76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18017ed7b  mov     rbx, rax
0x18017ed7e  mov     rcx, [rdi]; string
0x18017ed81  call    cs:__imp_WindowsDeleteString
0x18017ed87  xor     eax, eax
0x18017ed89  mov     [rdi], rax
0x18017ed8c  mov     rcx, [rbx]
0x18017ed8f  mov     [rdi], rcx
0x18017ed92  mov     [rbx], rax
0x18017ed95  mov     rcx, [rbp+57h+string]; string
0x18017ed99  call    cs:__imp_WindowsDeleteString
0x18017ed9f  xor     ebx, ebx
0x18017eda1  jmp     short loc_18017EDC5
0x18017eda3  mov     rcx, [rbp+5Fh]; this
0x18017eda7  mov     r9d, 8007139Fh; char *
0x18017edad  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18017edb4  mov     edx, 0D9h; void *
0x18017edb9  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18017edbe  lea     rsi, [r14+90h]
0x18017edc5  cmp     [rdi], rbx
0x18017edc8  jz      loc_18017EE95
0x18017edce  mov     rdx, r15
0x18017edd1  lea     rcx, [rbp+57h+SRWLock]
0x18017edd5  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18017edda  nop
0x18017eddb  mov     rax, [rdi]
0x18017edde  mov     [rbp+57h+string], rax
0x18017ede2  lea     rcx, [r14+78h]; newString
0x18017ede6  lea     rdx, [rbp+57h+string]; HSTRING *
0x18017edea  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18017edef  mov     rcx, [rbp+5Fh]; this
0x18017edf3  test    eax, eax
0x18017edf5  jns     short loc_18017EE0C
0x18017edf7  mov     r9d, eax; char *
0x18017edfa  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18017ee01  mov     edx, 0DFh; void *
0x18017ee06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18017ee0c  mov     rcx, [rsi]
0x18017ee0f  test    rcx, rcx
0x18017ee12  jz      short loc_18017EE52
0x18017ee14  add     rcx, 8
0x18017ee18  call    ?is_running@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::is_running(void)
0x18017ee1d  test    al, al
0x18017ee1f  jz      short loc_18017EE52
0x18017ee21  lea     rdx, [rbp+57h+string]
0x18017ee25  mov     rcx, rsi
0x18017ee28  call    ??C?$tip_test@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@1@XZ; tip2::tip_test<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::operator->(void)
0x18017ee2d  mov     rcx, [rax]
0x18017ee30  mov     byte ptr [rcx+130h], 1
0x18017ee37  lea     rcx, [rbp+57h+string]
0x18017ee3b  call    ??1?$test_data_control@V?$merged_data@U_tip_ResolveSortNameTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>::~test_data_control<tip2::details::merged_data<_tip_ResolveSortNameTest,_tip_ResolveSortNameTest>>(void)
0x18017ee40  mov     rcx, [rsi]
0x18017ee43  test    rcx, rcx
0x18017ee46  jz      short loc_18017EE52
0x18017ee48  add     rcx, 8
0x18017ee4c  call    ?complete_without_lock@?$shared_data@$00$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<1,0,0>::complete_without_lock(void)
0x18017ee51  nop
0x18017ee52  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18017ee56  test    rcx, rcx
0x18017ee59  jz      short loc_18017EE62
0x18017ee5b  call    cs:__imp_ReleaseSRWLockExclusive
0x18017ee61  nop
0x18017ee62  lea     rcx, [rbp+57h+var_80]
0x18017ee66  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18017ee6b  nop
0x18017ee6c  mov     rcx, [rbp+57h+var_A0]; string
0x18017ee70  call    cs:__imp_WindowsDeleteString
0x18017ee76  mov     rax, rdi
0x18017ee79  movaps  xmm6, [rsp+0D0h+var_58+8]
0x18017ee81  add     rsp, 98h
0x18017ee88  pop     r15
0x18017ee8a  pop     r14
0x18017ee8c  pop     r13
0x18017ee8e  pop     r12
0x18017ee90  pop     rdi
0x18017ee91  pop     rsi
0x18017ee92  pop     rbx
0x18017ee93  pop     rbp
0x18017ee94  retn
0x18017ee95  cmp     [rbp+57h+var_A0], rbx
0x18017ee99  jz      short loc_18017EEB5
0x18017ee9b  test    r12b, r12b
0x18017ee9e  jnz     short loc_18017EEB5
0x18017eea0  xor     ecx, ecx; string
0x18017eea2  call    cs:__imp_WindowsDeleteString
0x18017eea8  mov     rax, [rbp+57h+var_A0]
0x18017eeac  mov     [rdi], rax
0x18017eeaf  mov     [rbp+57h+var_A0], rbx
0x18017eeb3  jmp     short loc_18017EE62
0x18017eeb5  lea     rdx, [rbp+57h+var_60]; HSTRING *
0x18017eeb9  mov     rcx, rdi; newString
0x18017eebc  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18017eec1  mov     rcx, [rbp+5Fh]; this
0x18017eec5  test    eax, eax
0x18017eec7  jns     short loc_18017EE62
0x18017eec9  mov     r9d, eax; char *
0x18017eecc  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18017eed3  mov     edx, 0F2h; void *
0x18017eed8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
