# SharingPlatform::Session::SendMessageToParticipants(Windows::Foundation::Collections::IVectorView<_GUID> *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *)

- ea: `0x18004cd80`
- end: `0x18004cecb`
- name: `?SendMessageToParticipants@Session@SharingPlatform@@UEAAJPEAU?$IVectorView@U_GUID@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAUIBuffer@Streams@Storage@6@2@Z`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x1800130ec`
- `0x18004cd80`
- `0x180054fb8`
- `0x180055f04`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ceaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ce71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ceaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SharingPlatform::Session::SendMessageToParticipants(
        __int64 a1,
        __int64 a2,
        HSTRING a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // ebx
  __int64 result; // rax
  int v9; // r9d
  HSTRING v10; // rbx
  int StreamMessage; // eax
  unsigned int v12; // edi
  const char *v13; // r9
  int v14; // [rsp+20h] [rbp-48h]
  int v15; // [rsp+20h] [rbp-48h]
  HSTRING string; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  __int64 v18; // [rsp+80h] [rbp+18h] BYREF

  v5 = a4;
  if ( a3 )
  {
    if ( a4 )
    {
      SharingPlatform::Internal::MakeChannelLocator(&string, (const GUID *)(a1 + 24), a3);
      v18 = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v18);
      v9 = v5;
      v10 = string;
      try
      {
        StreamMessage = SharingPlatform::Internal::MessageBuilder::CreateStreamMessage(
                          (int)a1 + 56,
                          a2,
                          (_DWORD)string,
                          v9,
                          a5,
                          (__int64)&v18);
        v12 = StreamMessage;
        if ( StreamMessage >= 0 )
          v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, HSTRING, __int64))(**(_QWORD **)(a1 + 168) + 64LL))(
                  *(_QWORD *)(a1 + 168),
                  a2,
                  v10,
                  v18);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x18F,
            (unsigned int)".\\session.cpp",
            (const char *)(unsigned int)StreamMessage,
            v15);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v18);
        WindowsDeleteString(v10);
        result = v12;
      }
      catch ( ... )
      {
        LODWORD(v18) = wil::details::in1diag3::Return_CaughtException(
                         retaddr,
                         (void *)0x193,
                         (unsigned int)".\\session.cpp",
                         v13);
        return (unsigned int)v18;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)".\\session.cpp",
        (const char *)0x80070057LL,
        v14);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)".\\session.cpp",
      (const char *)0x80070057LL,
      v14);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004cd80  push    rbx
0x18004cd82  push    rsi
0x18004cd83  push    rdi
0x18004cd84  push    r14
0x18004cd86  sub     rsp, 48h
0x18004cd8a  mov     rbx, r9
0x18004cd8d  mov     r14, rdx
0x18004cd90  mov     rsi, rcx
0x18004cd93  test    r8, r8
0x18004cd96  jnz     short loc_18004CDBD
0x18004cd98  mov     rcx, [rsp+68h]; this
0x18004cd9d  mov     ebx, 80070057h
0x18004cda2  mov     r9d, ebx; char *
0x18004cda5  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004cdac  mov     edx, 188h; void *
0x18004cdb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cdb6  mov     eax, ebx
0x18004cdb8  jmp     loc_18004CEC0
0x18004cdbd  test    rbx, rbx
0x18004cdc0  jnz     short loc_18004CDE7
0x18004cdc2  mov     rcx, [rsp+68h]; this
0x18004cdc7  mov     ebx, 80070057h
0x18004cdcc  mov     r9d, ebx; char *
0x18004cdcf  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004cdd6  mov     edx, 189h; void *
0x18004cddb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cde0  mov     eax, ebx
0x18004cde2  jmp     loc_18004CEC0
0x18004cde7  lea     rdx, [rcx+18h]
0x18004cdeb  lea     rcx, [rsp+68h+string]
0x18004cdf0  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x18004cdf5  nop
0x18004cdf6  mov     [rsp+68h+arg_10], 0
0x18004ce02  lea     rcx, [rsp+68h+arg_10]
0x18004ce0a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004ce0f  lea     rcx, [rsi+38h]
0x18004ce13  lea     rax, [rsp+68h+arg_10]
0x18004ce1b  mov     [rsp+68h+var_40], rax
0x18004ce20  mov     rax, [rsp+68h+arg_20]
0x18004ce28  mov     qword ptr [rsp+68h+var_48], rax; int
0x18004ce2d  mov     r9, rbx
0x18004ce30  mov     rbx, [rsp+68h+string]
0x18004ce35  mov     r8, rbx
0x18004ce38  mov     rdx, r14
0x18004ce3b  call    ?CreateStreamMessage@MessageBuilder@Internal@SharingPlatform@@SAJPEAU_GUID@@PEAU?$IVectorView@U_GUID@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAUIBuffer@Streams@Storage@8@3PEAPEAUIBuffer@Streams@Storage@8@@Z; SharingPlatform::Internal::MessageBuilder::CreateStreamMessage(_GUID *,Windows::Foundation::Collections::IVectorView<_GUID> *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer * *)
0x18004ce40  mov     edi, eax
0x18004ce42  test    eax, eax
0x18004ce44  jns     short loc_18004CE7B
0x18004ce46  mov     rcx, [rsp+68h]; this
0x18004ce4b  mov     r9d, eax; char *
0x18004ce4e  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004ce55  mov     edx, 18Fh; void *
0x18004ce5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ce5f  nop
0x18004ce60  lea     rcx, [rsp+68h+arg_10]
0x18004ce68  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004ce6d  nop
0x18004ce6e  mov     rcx, rbx; string
0x18004ce71  call    cs:__imp_WindowsDeleteString
0x18004ce77  mov     eax, edi
0x18004ce79  jmp     short loc_18004CEC0
0x18004ce7b  mov     rcx, [rsi+0A8h]
0x18004ce82  mov     rax, [rcx]
0x18004ce85  mov     r9, [rsp+68h+arg_10]
0x18004ce8d  mov     r8, rbx
0x18004ce90  mov     rdx, r14
0x18004ce93  mov     rax, [rax+40h]
0x18004ce97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce9c  mov     edi, eax
0x18004ce9e  lea     rcx, [rsp+68h+arg_10]
0x18004cea6  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004ceab  nop
0x18004ceac  mov     rcx, rbx; string
0x18004ceaf  call    cs:__imp_WindowsDeleteString
0x18004ceb5  mov     eax, edi
0x18004ceb7  jmp     short loc_18004CEC0
0x18004ceb9  mov     eax, dword ptr [rsp+68h+arg_10]
0x18004cec0  add     rsp, 48h
0x18004cec4  pop     r14
0x18004cec6  pop     rdi
0x18004cec7  pop     rsi
0x18004cec8  pop     rbx
0x18004cec9  retn
```
