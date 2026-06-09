# SharingPlatform::Session::OnStreamData(_GUID const &,HSTRING__ *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *)

- ea: `0x18004b760`
- end: `0x18004b8fc`
- name: `?OnStreamData@Session@SharingPlatform@@UEAAXAEBU_GUID@@PEAUHSTRING__@@PEAUIBuffer@Streams@Storage@Windows@@2@Z`
- size: `412`
- prototype: `void(SharingPlatform::Session *__hidden this, const struct _GUID *, HSTRING, struct Windows::Storage::Streams::IBuffer *, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x180042e40`
- `0x18004a4c4`
- `0x18004b760`
- `0x18004d020`
- `0x18004fa38`
- `0x18004fac8`
- `0x1800560c0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b83e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b83e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b7c6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b7c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b857`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004b8e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SharingPlatform::Session::OnStreamData(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2,
        SharingPlatform::Internal *a3,
        struct Windows::Storage::Streams::IBuffer *a4,
        struct Windows::Storage::Streams::IBuffer *a5)
{
  int v9; // eax
  HSTRING v10; // rbx
  char v11; // bl
  HSTRING *v12; // r8
  int v13; // eax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // [rsp+20h] [rbp-78h]
  struct IInspectable *v17; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  HSTRING v19[2]; // [rsp+40h] [rbp-58h] BYREF
  _OWORD v20[4]; // [rsp+50h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  SharingPlatform::Internal *v22; // [rsp+B0h] [rbp+18h] BYREF

  v22 = a3;
  v19[0] = 0;
  v9 = Microsoft::WRL::Wrappers::HString::Set(v19, (HSTRING *)&v22);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x3BB,
      (unsigned int)".\\session.cpp",
      (const char *)(unsigned int)v9,
      v16);
  v17 = 0;
  EnterCriticalSection(this + 2);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::find(
    &this[4],
    &string,
    v19);
  v10 = string;
  if ( string == (HSTRING)this[4].DebugInfo )
  {
    v11 = 0;
  }
  else
  {
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
    if ( (int)Microsoft::WRL::WeakRef::InternalResolve(
                (Microsoft::WRL::WeakRef *)(v10 + 10),
                &GUID_255b794d_a24b_457c_8107_4ef363f95da5,
                &v17) >= 0
      && v17 )
    {
      v11 = 1;
    }
    else
    {
      v11 = 0;
      std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::erase(
        &this[4],
        v19);
    }
  }
  if ( this != (struct _RTL_CRITICAL_SECTION *)-80LL )
    LeaveCriticalSection(this + 2);
  try
  {
    if ( v11 )
    {
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      v13 = SharingPlatform::Internal::ParseChannelLocator(a3, (HSTRING)&string, v12);
      if ( v13 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x3D4,
          (unsigned int)".\\session.cpp",
          (const char *)(unsigned int)v13,
          v16);
      v20[0] = *a2;
      ((void (__fastcall *)(struct IInspectable *, HSTRING, _OWORD *, struct Windows::Storage::Streams::IBuffer *, struct Windows::Storage::Streams::IBuffer *))v17->lpVtbl[1].QueryInterface)(
        v17,
        string,
        v20,
        a4,
        a5);
      WindowsDeleteString(string);
    }
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
    WindowsDeleteString(v19[0]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(retaddr, (void *)0x3D9, v14, v15);
  }
}

```

## disassembly

```asm
0x18004b760  mov     rax, rsp
0x18004b763  mov     [rax+18h], r8
0x18004b767  push    rbx
0x18004b768  push    rsi
0x18004b769  push    rdi
0x18004b76a  push    r12
0x18004b76c  push    r14
0x18004b76e  push    r15
0x18004b770  sub     rsp, 68h
0x18004b774  mov     r15, r9
0x18004b777  mov     r14, r8
0x18004b77a  mov     r12, rdx
0x18004b77d  mov     rsi, rcx
0x18004b780  mov     qword ptr [rax-58h], 0
0x18004b788  lea     rdx, [rax+18h]; HSTRING *
0x18004b78c  lea     rcx, [rax-58h]; newString
0x18004b790  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18004b795  mov     rcx, [rsp+98h]; this
0x18004b79d  test    eax, eax
0x18004b79f  jns     short loc_18004B7B6
0x18004b7a1  mov     r9d, eax; char *
0x18004b7a4  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004b7ab  mov     edx, 3BBh; void *
0x18004b7b0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18004b7b6  mov     [rsp+98h+var_68], 0
0x18004b7bf  lea     rdi, [rsi+50h]
0x18004b7c3  mov     rcx, rdi; lpCriticalSection
0x18004b7c6  call    cs:__imp_EnterCriticalSection
0x18004b7cc  lea     r8, [rsp+98h+var_58]
0x18004b7d1  lea     rdx, [rsp+98h+string]
0x18004b7d6  lea     rcx, [rsi+0A0h]
0x18004b7dd  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x18004b7e2  mov     rbx, [rsp+98h+string]
0x18004b7e7  cmp     rbx, [rsi+0A0h]
0x18004b7ee  jnz     short loc_18004B7F4
0x18004b7f0  xor     bl, bl
0x18004b7f2  jmp     short loc_18004B836
0x18004b7f4  lea     rcx, [rsp+98h+var_68]
0x18004b7f9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004b7fe  lea     rcx, [rbx+28h]; this
0x18004b802  lea     r8, [rsp+98h+var_68]; struct IInspectable **
0x18004b807  lea     rdx, _GUID_255b794d_a24b_457c_8107_4ef363f95da5; struct _GUID *
0x18004b80e  call    ?InternalResolve@WeakRef@WRL@Microsoft@@IEBAJAEBU_GUID@@PEAPEAUIInspectable@@@Z; Microsoft::WRL::WeakRef::InternalResolve(_GUID const &,IInspectable * *)
0x18004b813  test    eax, eax
0x18004b815  js      short loc_18004B823
0x18004b817  cmp     [rsp+98h+var_68], 0
0x18004b81d  jz      short loc_18004B823
0x18004b81f  mov     bl, 1
0x18004b821  jmp     short loc_18004B836
0x18004b823  xor     bl, bl
0x18004b825  lea     rdx, [rsp+98h+var_58]
0x18004b82a  lea     rcx, [rsi+0A0h]
0x18004b831  call    ?erase@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::erase(Microsoft::WRL::Wrappers::HString const &)
0x18004b836  test    rdi, rdi
0x18004b839  jz      short loc_18004B844
0x18004b83b  mov     rcx, rdi; lpCriticalSection
0x18004b83e  call    cs:__imp_LeaveCriticalSection
0x18004b844  test    bl, bl
0x18004b846  jz      loc_18004B8D7
0x18004b84c  mov     [rsp+98h+string], 0
0x18004b855  xor     ecx, ecx; string
0x18004b857  call    cs:__imp_WindowsDeleteString
0x18004b85d  mov     [rsp+98h+string], 0
0x18004b866  lea     rdx, [rsp+98h+string]; HSTRING
0x18004b86b  mov     rcx, r14; this
0x18004b86e  call    ?ParseChannelLocator@Internal@SharingPlatform@@YAJPEAUHSTRING__@@PEAPEAU3@@Z; SharingPlatform::Internal::ParseChannelLocator(HSTRING__ *,HSTRING__ * *)
0x18004b873  mov     rcx, [rsp+98h]; this
0x18004b87b  test    eax, eax
0x18004b87d  jns     short loc_18004B894
0x18004b87f  mov     r9d, eax; char *
0x18004b882  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004b889  mov     edx, 3D4h; void *
0x18004b88e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18004b894  mov     rcx, [rsp+98h+var_68]
0x18004b899  movups  xmm0, xmmword ptr [r12]
0x18004b89e  movdqu  [rsp+98h+var_48], xmm0
0x18004b8a4  mov     rax, [rcx]
0x18004b8a7  mov     rdx, [rsp+98h+arg_20]
0x18004b8af  mov     qword ptr [rsp+98h+var_78], rdx
0x18004b8b4  mov     r9, r15
0x18004b8b7  lea     r8, [rsp+98h+var_48]
0x18004b8bc  mov     rdx, [rsp+98h+string]
0x18004b8c1  mov     rax, [rax+30h]
0x18004b8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8ca  nop
0x18004b8cb  mov     rcx, [rsp+98h+string]; string
0x18004b8d0  call    cs:__imp_WindowsDeleteString
0x18004b8d6  nop
0x18004b8d7  lea     rcx, [rsp+98h+var_68]
0x18004b8dc  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004b8e1  nop
0x18004b8e2  mov     rcx, [rsp+98h+var_58]; string
0x18004b8e7  call    cs:__imp_WindowsDeleteString
0x18004b8ed  nop
0x18004b8ee  add     rsp, 68h
0x18004b8f2  pop     r15
0x18004b8f4  pop     r14
0x18004b8f6  pop     r12
0x18004b8f8  pop     rdi
0x18004b8f9  pop     rsi
0x18004b8fa  pop     rbx
0x18004b8fb  retn
```
