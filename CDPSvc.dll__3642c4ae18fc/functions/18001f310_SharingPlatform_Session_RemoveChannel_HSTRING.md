# SharingPlatform::Session::RemoveChannel(HSTRING__ *)

- ea: `0x18001f310`
- end: `0x18001f468`
- name: `?RemoveChannel@Session@SharingPlatform@@UEAAJPEAUHSTRING__@@@Z`
- size: `344`
- prototype: `int(SharingPlatform::Session *__hidden this, HSTRING)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800130ec`
- `0x18001f310`
- `0x18001f470`
- `0x18001f5ec`
- `0x1800225a0`
- `0x18004729c`
- `0x18004d94c`
- `0x18004fa38`
- `0x180055f04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f40a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f41a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f40a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f41a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3c4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001f369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f433`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001f433`

## string_xrefs

- `0x18001f372`: `SessionRemoveChannel`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::Session::RemoveChannel(SharingPlatform::Session *this, HSTRING a2)
{
  const unsigned __int16 *StringRawBuffer; // rbx
  unsigned int v6; // edi
  HSTRING string[2]; // [rsp+20h] [rbp-188h] BYREF
  _QWORD v8[42]; // [rsp+30h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( a2 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
      v8,
      "SessionRemoveChannel");
    v8[0] = &RemoteSessionTraceProvider::SessionRemoveChannel::`vftable';
    *(_OWORD *)string = *(_OWORD *)((char *)this + 24);
    RemoteSessionTraceProvider::SessionRemoveChannel::StartActivity(
      (RemoteSessionTraceProvider::SessionRemoveChannel *)v8,
      (struct _GUID *)string,
      StringRawBuffer);
    SharingPlatform::Internal::MakeChannelLocator(string, (const GUID *)((char *)this + 24), a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    if ( std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::erase(
           (char *)this + 152,
           string) == 1 )
    {
      if ( this != (SharingPlatform::Session *)-72LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
      wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v8,
        0);
      v6 = 0;
    }
    else
    {
      v6 = -2147023728;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x161,
        (unsigned int)".\\session.cpp",
        (const char *)0x80070490LL,
        (int)string[0]);
      if ( this != (SharingPlatform::Session *)-72LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
    }
    WindowsDeleteString(string[0]);
    RemoteSessionTraceProvider::SessionRemoveChannel::~SessionRemoveChannel((RemoteSessionTraceProvider::SessionRemoveChannel *)v8);
    return v6;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)".\\session.cpp",
      (const char *)0x80070057LL,
      (int)string[0]);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18001f310  mov     [rsp+arg_10], rbx
0x18001f315  push    rbp
0x18001f316  push    rsi
0x18001f317  push    rdi
0x18001f318  sub     rsp, 190h
0x18001f31f  mov     rax, cs:__security_cookie
0x18001f326  xor     rax, rsp
0x18001f329  mov     [rsp+1A8h+var_28], rax
0x18001f331  mov     rsi, rdx
0x18001f334  mov     rbp, rcx
0x18001f337  test    rdx, rdx
0x18001f33a  jnz     short loc_18001F364
0x18001f33c  mov     rcx, [rsp+1A8h]; this
0x18001f344  mov     ebx, 80070057h
0x18001f349  mov     r9d, ebx; char *
0x18001f34c  lea     r8, aSessionCpp; ".\\session.cpp"
0x18001f353  mov     edx, 157h; void *
0x18001f358  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f35d  mov     eax, ebx
0x18001f35f  jmp     loc_18001F445
0x18001f364  xor     edx, edx; length
0x18001f366  mov     rcx, rsi; string
0x18001f369  call    cs:__imp_WindowsGetStringRawBuffer
0x18001f36f  mov     rbx, rax
0x18001f372  lea     rdx, aSessionremovec; "SessionRemoveChannel"
0x18001f379  lea     rcx, [rsp+1A8h+var_178]
0x18001f37e  call    ??0?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001f383  lea     rax, ??_7SessionRemoveChannel@RemoteSessionTraceProvider@@6B@; const RemoteSessionTraceProvider::SessionRemoveChannel::`vftable'
0x18001f38a  mov     [rsp+1A8h+var_178], rax
0x18001f38f  movups  xmm0, xmmword ptr [rbp+18h]
0x18001f393  movdqu  xmmword ptr [rsp+1A8h+string], xmm0; int
0x18001f399  mov     r8, rbx; unsigned __int16 *
0x18001f39c  lea     rdx, [rsp+1A8h+string]; struct _GUID
0x18001f3a1  lea     rcx, [rsp+1A8h+var_178]; this
0x18001f3a6  call    ?StartActivity@SessionRemoveChannel@RemoteSessionTraceProvider@@QEAAXU_GUID@@PEBG@Z; RemoteSessionTraceProvider::SessionRemoveChannel::StartActivity(_GUID,ushort const *)
0x18001f3ab  nop
0x18001f3ac  mov     r8, rsi
0x18001f3af  lea     rdx, [rbp+18h]
0x18001f3b3  lea     rcx, [rsp+1A8h+string]
0x18001f3b8  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x18001f3bd  lea     rbx, [rbp+48h]
0x18001f3c1  mov     rcx, rbx; lpCriticalSection
0x18001f3c4  call    cs:__imp_EnterCriticalSection
0x18001f3ca  lea     rcx, [rbp+98h]
0x18001f3d1  lea     rdx, [rsp+1A8h+string]
0x18001f3d6  call    ?erase@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::erase(Microsoft::WRL::Wrappers::HString const &)
0x18001f3db  cmp     rax, 1
0x18001f3df  jz      short loc_18001F412
0x18001f3e1  mov     rcx, [rsp+1A8h]; this
0x18001f3e9  mov     edi, 80070490h
0x18001f3ee  mov     r9d, edi; char *
0x18001f3f1  lea     r8, aSessionCpp; ".\\session.cpp"
0x18001f3f8  mov     edx, 161h; void *
0x18001f3fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f402  test    rbx, rbx
0x18001f405  jz      short loc_18001F42E
0x18001f407  mov     rcx, rbx; lpCriticalSection
0x18001f40a  call    cs:__imp_LeaveCriticalSection
0x18001f410  jmp     short loc_18001F42E
0x18001f412  test    rbx, rbx
0x18001f415  jz      short loc_18001F420
0x18001f417  mov     rcx, rbx; lpCriticalSection
0x18001f41a  call    cs:__imp_LeaveCriticalSection
0x18001f420  xor     edx, edx
0x18001f422  lea     rcx, [rsp+1A8h+var_178]
0x18001f427  call    ?Stop@?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18001f42c  xor     edi, edi
0x18001f42e  mov     rcx, [rsp+1A8h+string]; string
0x18001f433  call    cs:__imp_WindowsDeleteString
0x18001f439  lea     rcx, [rsp+1A8h+var_178]; this
0x18001f43e  call    ??1SessionRemoveChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionRemoveChannel::~SessionRemoveChannel(void)
0x18001f443  mov     eax, edi
0x18001f445  mov     rcx, [rsp+1A8h+var_28]
0x18001f44d  xor     rcx, rsp; StackCookie
0x18001f450  call    __security_check_cookie
0x18001f455  mov     rbx, [rsp+1A8h+arg_10]
0x18001f45d  add     rsp, 190h
0x18001f464  pop     rdi
0x18001f465  pop     rsi
0x18001f466  pop     rbp
0x18001f467  retn
```
