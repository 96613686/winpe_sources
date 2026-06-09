# DataStoreCache::MRTTransformerData::ResolveSuiteSortName(HSTRING__ *,HSTRING__ *)

- ea: `0x18036b4a0`
- end: `0x18036b70d`
- name: `?ResolveSuiteSortName@MRTTransformerData@DataStoreCache@@UEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@0@Z`
- size: `621`
- prototype: `struct Microsoft::WRL::Wrappers::HString __high(HSTRING, HSTRING)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000ce94`
- `0x18000f898`
- `0x18000fba8`
- `0x18001dac0`
- `0x1800385d0`
- `0x18003b500`
- `0x1800c5b3c`
- `0x1800dd908`
- `0x18017eee4`
- `0x18036b4a0`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18036b692`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18036b692`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036b53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036b54f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036b53b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18036b54f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b6a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b6cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b61f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b6a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18036b6cd`

## string_xrefs

- `0x18036b51c`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18036b59d`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18036b631`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18036b677`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`
- `0x18036b6fb`: `shellcommon\shell\datastorecache\transformers\mrttransformer\lib\mrttransformer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HSTRING *DataStoreCache::MRTTransformerData::ResolveSuiteSortName(
        __int64 a1,
        HSTRING *a2,
        ShellMRTHelper::Common *a3,
        ...)
{
  HSTRING v3; // r12
  __int64 v7; // r14
  int v8; // eax
  HSTRING v9; // rdx
  bool IsResolvableStringReference; // r15
  int v11; // eax
  __int64 v12; // rax
  HSTRING v13; // r8
  HSTRING *v14; // rbx
  int v15; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-40h]
  int v19; // [rsp+20h] [rbp-40h]
  PSRWLOCK *v20; // [rsp+20h] [rbp-40h]
  HSTRING v21; // [rsp+30h] [rbp-30h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-28h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string[2]; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  HSTRING v26; // [rsp+B8h] [rbp+58h] BYREF
  va_list va; // [rsp+B8h] [rbp+58h]
  va_list va1; // [rsp+C0h] [rbp+60h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v26 = va_arg(va1, HSTRING);
  v3 = v26;
  v7 = a1 + 152;
  Microsoft::WRL::Wrappers::SRWLock::LockShared(SRWLock, a1 + 152);
  if ( *(_QWORD *)(a1 + 136) )
  {
    *a2 = 0;
    string[0] = *(HSTRING *)(a1 + 136);
    v8 = Microsoft::WRL::Wrappers::HString::Set(a2, string);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)(unsigned int)v8,
        v18);
    if ( SRWLock[0] )
      ReleaseSRWLockShared(SRWLock[0]);
  }
  else
  {
    if ( SRWLock[0] )
      ReleaseSRWLockShared(SRWLock[0]);
    DataStoreCache::MRTTransformerData::ResolveText(a1 - 48, &v21, a3, 4, 0);
    IsResolvableStringReference = ShellMRTHelper::Common::IsResolvableStringReference((ShellMRTHelper::Common *)v21, v9);
    v22 = 0;
    v11 = Microsoft::WRL::WeakRef::As<DataStoreCache::IMRTTransformerInternal>(a1 + 56, &v22);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11C,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)(unsigned int)v11,
        v19);
    *a2 = 0;
    if ( v22 )
    {
      v12 = *v22;
      v13 = v21;
      if ( IsResolvableStringReference )
        v13 = 0;
      *(GUID *)SRWLock = GUID_NULL;
      v20 = SRWLock;
      v14 = (HSTRING *)(*(__int64 (__fastcall **)(__int64 *, HSTRING *, HSTRING, HSTRING))(v12 + 56))(
                         v22,
                         string,
                         v13,
                         v3);
      WindowsDeleteString(*a2);
      *a2 = 0;
      *a2 = *v14;
      *v14 = 0;
      WindowsDeleteString(string[0]);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
        (const char *)0x8007139FLL,
        v19);
    }
    if ( *a2 )
    {
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, v7);
      string[0] = *a2;
      v15 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a1 + 136), string);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12F,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
          (const char *)(unsigned int)v15,
          (int)v20);
      if ( SRWLock[0] )
        ReleaseSRWLockExclusive(SRWLock[0]);
    }
    else if ( !v21 || IsResolvableStringReference )
    {
      v17 = Microsoft::WRL::Wrappers::HString::Set(a2, (HSTRING *)va);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x13C,
          (unsigned int)"shellcommon\\shell\\datastorecache\\transformers\\mrttransformer\\lib\\mrttransformer.cpp",
          (const char *)(unsigned int)v17,
          (int)v20);
    }
    else
    {
      WindowsDeleteString(0);
      *a2 = v21;
      v21 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    WindowsDeleteString(v21);
  }
  return a2;
}

```

## disassembly

```asm
0x18036b4a0  mov     [rsp-38h+arg_18], r9
0x18036b4a5  mov     [rsp-38h+arg_8], rdx
0x18036b4aa  push    rbp
0x18036b4ab  push    rbx
0x18036b4ac  push    rsi
0x18036b4ad  push    rdi
0x18036b4ae  push    r12
0x18036b4b0  push    r14
0x18036b4b2  push    r15
0x18036b4b4  mov     rbp, rsp
0x18036b4b7  sub     rsp, 60h
0x18036b4bb  mov     r12, r9
0x18036b4be  mov     r15, r8
0x18036b4c1  mov     rdi, rdx
0x18036b4c4  mov     rsi, rcx
0x18036b4c7  mov     [rbp+arg_0], 1
0x18036b4ce  lea     r14, [rcx+98h]
0x18036b4d5  mov     rdx, r14
0x18036b4d8  lea     rcx, [rbp+SRWLock]
0x18036b4dc  call    ?LockShared@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockShared@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockShared(_RTL_SRWLOCK *)
0x18036b4e1  nop
0x18036b4e2  cmp     qword ptr [rsi+88h], 0
0x18036b4ea  jz      short loc_18036B546
0x18036b4ec  mov     qword ptr [rdi], 0
0x18036b4f3  mov     [rbp+arg_0], 1
0x18036b4fa  mov     rax, [rsi+88h]
0x18036b501  mov     [rbp+string], rax
0x18036b505  lea     rdx, [rbp+string]; HSTRING *
0x18036b509  mov     rcx, rdi; newString
0x18036b50c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18036b511  mov     rcx, [rbp+38h]; this
0x18036b515  test    eax, eax
0x18036b517  jns     short loc_18036B52E
0x18036b519  mov     r9d, eax; char *
0x18036b51c  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18036b523  mov     edx, 111h; void *
0x18036b528  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18036b52e  mov     rcx, [rbp+SRWLock]; SRWLock
0x18036b532  test    rcx, rcx
0x18036b535  jz      loc_18036B6AD
0x18036b53b  call    cs:__imp_ReleaseSRWLockShared
0x18036b541  jmp     loc_18036B6AD
0x18036b546  mov     rcx, [rbp+SRWLock]; SRWLock
0x18036b54a  test    rcx, rcx
0x18036b54d  jz      short loc_18036B555
0x18036b54f  call    cs:__imp_ReleaseSRWLockShared
0x18036b555  mov     byte ptr [rsp+60h+var_40], 0; int
0x18036b55a  mov     r9d, 4
0x18036b560  mov     r8, r15
0x18036b563  lea     rdx, [rbp+var_30]
0x18036b567  lea     rcx, [rsi-30h]
0x18036b56b  call    ?ResolveText@MRTTransformerData@DataStoreCache@@AEAA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@W4TextType@12@_N@Z; DataStoreCache::MRTTransformerData::ResolveText(HSTRING__ *,DataStoreCache::MRTTransformerData::TextType,bool)
0x18036b570  nop
0x18036b571  mov     rcx, [rbp+var_30]; this
0x18036b575  call    ?IsResolvableStringReference@Common@ShellMRTHelper@@YA_NPEAUHSTRING__@@@Z; ShellMRTHelper::Common::IsResolvableStringReference(HSTRING__ *)
0x18036b57a  mov     r15b, al
0x18036b57d  mov     [rbp+var_28], 0
0x18036b585  lea     rcx, [rsi+38h]
0x18036b589  lea     rdx, [rbp+var_28]
0x18036b58d  call    ??$As@UIMRTTransformerInternal@DataStoreCache@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIMRTTransformerInternal@DataStoreCache@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<DataStoreCache::IMRTTransformerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<DataStoreCache::IMRTTransformerInternal>>)
0x18036b592  mov     rcx, [rbp+38h]; this
0x18036b596  test    eax, eax
0x18036b598  jns     short loc_18036B5AF
0x18036b59a  mov     r9d, eax; char *
0x18036b59d  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18036b5a4  mov     edx, 11Ch; void *
0x18036b5a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18036b5af  mov     qword ptr [rdi], 0
0x18036b5b6  mov     [rbp+arg_0], 3
0x18036b5bd  mov     rcx, [rbp+var_28]
0x18036b5c1  test    rcx, rcx
0x18036b5c4  jz      short loc_18036B627
0x18036b5c6  mov     rax, [rcx]
0x18036b5c9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18036b5d0  mov     r8, [rbp+var_30]
0x18036b5d4  xor     edx, edx
0x18036b5d6  test    r15b, r15b
0x18036b5d9  cmovnz  r8, rdx
0x18036b5dd  movdqu  xmmword ptr [rbp+SRWLock], xmm0
0x18036b5e2  lea     rdx, [rbp+SRWLock]
0x18036b5e6  mov     qword ptr [rsp+60h+var_40], rdx
0x18036b5eb  mov     r9, r12
0x18036b5ee  lea     rdx, [rbp+string]
0x18036b5f2  mov     rax, [rax+38h]
0x18036b5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18036b5fb  mov     rbx, rax
0x18036b5fe  mov     rcx, [rdi]; string
0x18036b601  call    cs:__imp_WindowsDeleteString
0x18036b607  mov     qword ptr [rdi], 0
0x18036b60e  mov     rcx, [rbx]
0x18036b611  mov     [rdi], rcx
0x18036b614  mov     qword ptr [rbx], 0
0x18036b61b  mov     rcx, [rbp+string]; string
0x18036b61f  call    cs:__imp_WindowsDeleteString
0x18036b625  jmp     short loc_18036B642
0x18036b627  mov     rcx, [rbp+38h]; this
0x18036b62b  mov     r9d, 8007139Fh; char *
0x18036b631  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18036b638  mov     edx, 129h; void *
0x18036b63d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18036b642  cmp     qword ptr [rdi], 0
0x18036b646  jz      short loc_18036B6BF
0x18036b648  mov     rdx, r14
0x18036b64b  lea     rcx, [rbp+SRWLock]
0x18036b64f  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18036b654  nop
0x18036b655  mov     rax, [rdi]
0x18036b658  mov     [rbp+string], rax
0x18036b65c  lea     rcx, [rsi+88h]; newString
0x18036b663  lea     rdx, [rbp+string]; HSTRING *
0x18036b667  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18036b66c  mov     rcx, [rbp+38h]; this
0x18036b670  test    eax, eax
0x18036b672  jns     short loc_18036B689
0x18036b674  mov     r9d, eax; char *
0x18036b677  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18036b67e  mov     edx, 12Fh; void *
0x18036b683  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18036b689  mov     rcx, [rbp+SRWLock]; SRWLock
0x18036b68d  test    rcx, rcx
0x18036b690  jz      short loc_18036B699
0x18036b692  call    cs:__imp_ReleaseSRWLockExclusive
0x18036b698  nop
0x18036b699  lea     rcx, [rbp+var_28]
0x18036b69d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18036b6a2  nop
0x18036b6a3  mov     rcx, [rbp+var_30]; string
0x18036b6a7  call    cs:__imp_WindowsDeleteString
0x18036b6ad  mov     rax, rdi
0x18036b6b0  add     rsp, 60h
0x18036b6b4  pop     r15
0x18036b6b6  pop     r14
0x18036b6b8  pop     r12
0x18036b6ba  pop     rdi
0x18036b6bb  pop     rsi
0x18036b6bc  pop     rbx
0x18036b6bd  pop     rbp
0x18036b6be  retn
0x18036b6bf  cmp     [rbp+var_30], 0
0x18036b6c4  jz      short loc_18036B6E4
0x18036b6c6  test    r15b, r15b
0x18036b6c9  jnz     short loc_18036B6E4
0x18036b6cb  xor     ecx, ecx; string
0x18036b6cd  call    cs:__imp_WindowsDeleteString
0x18036b6d3  mov     rax, [rbp+var_30]
0x18036b6d7  mov     [rdi], rax
0x18036b6da  mov     [rbp+var_30], 0
0x18036b6e2  jmp     short loc_18036B699
0x18036b6e4  lea     rdx, [rbp+arg_18]; HSTRING *
0x18036b6e8  mov     rcx, rdi; newString
0x18036b6eb  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18036b6f0  mov     rcx, [rbp+38h]; this
0x18036b6f4  test    eax, eax
0x18036b6f6  jns     short loc_18036B699
0x18036b6f8  mov     r9d, eax; char *
0x18036b6fb  lea     r8, aShellcommonShe_14; "shellcommon\\shell\\datastorecache\\tra"...
0x18036b702  mov     edx, 13Ch; void *
0x18036b707  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
