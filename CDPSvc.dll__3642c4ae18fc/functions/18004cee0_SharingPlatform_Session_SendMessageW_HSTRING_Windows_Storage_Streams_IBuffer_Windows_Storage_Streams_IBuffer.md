# SharingPlatform::Session::SendMessageW(HSTRING__ *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *)

- ea: `0x18004cee0`
- end: `0x18004d018`
- name: `?SendMessageW@Session@SharingPlatform@@UEAAJPEAUHSTRING__@@PEAUIBuffer@Streams@Storage@Windows@@1@Z`
- size: `312`
- prototype: `int(SharingPlatform::Session *__hidden this, HSTRING, struct Windows::Storage::Streams::IBuffer *, struct Windows::Storage::Streams::IBuffer *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x1800130ec`
- `0x18004cee0`
- `0x180054fb8`
- `0x180055f04`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cff9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cfc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004cff9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SharingPlatform::Session::SendMessageW(
        SharingPlatform::Session *this,
        HSTRING a2,
        struct Windows::Storage::Streams::IBuffer *a3,
        struct Windows::Storage::Streams::IBuffer *a4)
{
  int v5; // ebx
  __int64 result; // rax
  int v8; // r9d
  HSTRING v9; // rbx
  int StreamMessage; // eax
  unsigned int v11; // edi
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-28h]
  int v14; // [rsp+20h] [rbp-28h]
  HSTRING string; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v17; // [rsp+58h] [rbp+10h] BYREF

  v5 = (int)a3;
  if ( a2 )
  {
    if ( a3 )
    {
      SharingPlatform::Internal::MakeChannelLocator(&string, (const GUID *)((char *)this + 24), a2);
      v17 = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
      v8 = v5;
      v9 = string;
      try
      {
        StreamMessage = SharingPlatform::Internal::MessageBuilder::CreateStreamMessage(
                          (int)this + 56,
                          0,
                          (_DWORD)string,
                          v8,
                          (__int64)a4,
                          (__int64)&v17);
        v11 = StreamMessage;
        if ( StreamMessage >= 0 )
          v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, __int64))(**((_QWORD **)this + 21) + 72LL))(
                  *((_QWORD *)this + 21),
                  v9,
                  v17);
        else
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x178,
            (unsigned int)".\\session.cpp",
            (const char *)(unsigned int)StreamMessage,
            v14);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
        WindowsDeleteString(v9);
        result = v11;
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x17C,
                               (unsigned int)".\\session.cpp",
                               v12);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)".\\session.cpp",
        (const char *)0x80070057LL,
        v13);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)".\\session.cpp",
      (const char *)0x80070057LL,
      v13);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x18004cee0  mov     [rsp+arg_0], rbx
0x18004cee5  mov     [rsp+arg_10], rsi
0x18004ceea  push    rdi
0x18004ceeb  sub     rsp, 40h
0x18004ceef  mov     rdi, r9
0x18004cef2  mov     rbx, r8
0x18004cef5  mov     r8, rdx
0x18004cef8  mov     rsi, rcx
0x18004cefb  test    rdx, rdx
0x18004cefe  jnz     short loc_18004CF25
0x18004cf00  mov     rcx, [rsp+48h]; this
0x18004cf05  mov     ebx, 80070057h
0x18004cf0a  mov     r9d, ebx; char *
0x18004cf0d  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004cf14  mov     edx, 171h; void *
0x18004cf19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf1e  mov     eax, ebx
0x18004cf20  jmp     loc_18004D007
0x18004cf25  test    rbx, rbx
0x18004cf28  jnz     short loc_18004CF4F
0x18004cf2a  mov     rcx, [rsp+48h]; this
0x18004cf2f  mov     ebx, 80070057h
0x18004cf34  mov     r9d, ebx; char *
0x18004cf37  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004cf3e  mov     edx, 172h; void *
0x18004cf43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cf48  mov     eax, ebx
0x18004cf4a  jmp     loc_18004D007
0x18004cf4f  lea     rdx, [rcx+18h]
0x18004cf53  lea     rcx, [rsp+48h+string]
0x18004cf58  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x18004cf5d  nop
0x18004cf5e  mov     [rsp+48h+arg_8], 0
0x18004cf67  lea     rcx, [rsp+48h+arg_8]
0x18004cf6c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004cf71  lea     rcx, [rsi+38h]
0x18004cf75  lea     rax, [rsp+48h+arg_8]
0x18004cf7a  mov     [rsp+48h+var_20], rax
0x18004cf7f  mov     qword ptr [rsp+48h+var_28], rdi; int
0x18004cf84  mov     r9, rbx
0x18004cf87  mov     rbx, [rsp+48h+string]
0x18004cf8c  mov     r8, rbx
0x18004cf8f  xor     edx, edx
0x18004cf91  call    ?CreateStreamMessage@MessageBuilder@Internal@SharingPlatform@@SAJPEAU_GUID@@PEAU?$IVectorView@U_GUID@@@Collections@Foundation@Windows@@PEAUHSTRING__@@PEAUIBuffer@Streams@Storage@8@3PEAPEAUIBuffer@Streams@Storage@8@@Z; SharingPlatform::Internal::MessageBuilder::CreateStreamMessage(_GUID *,Windows::Foundation::Collections::IVectorView<_GUID> *,HSTRING__ *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer *,Windows::Storage::Streams::IBuffer * *)
0x18004cf96  mov     edi, eax
0x18004cf98  test    eax, eax
0x18004cf9a  jns     short loc_18004CFCE
0x18004cf9c  mov     rcx, [rsp+48h]; this
0x18004cfa1  mov     r9d, eax; char *
0x18004cfa4  lea     r8, aSessionCpp; ".\\session.cpp"
0x18004cfab  mov     edx, 178h; void *
0x18004cfb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004cfb5  nop
0x18004cfb6  lea     rcx, [rsp+48h+arg_8]
0x18004cfbb  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004cfc0  nop
0x18004cfc1  mov     rcx, rbx; string
0x18004cfc4  call    cs:__imp_WindowsDeleteString
0x18004cfca  mov     eax, edi
0x18004cfcc  jmp     short loc_18004D007
0x18004cfce  mov     rcx, [rsi+0A8h]
0x18004cfd5  mov     rax, [rcx]
0x18004cfd8  mov     r8, [rsp+48h+arg_8]
0x18004cfdd  mov     rdx, rbx
0x18004cfe0  mov     rax, [rax+48h]
0x18004cfe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfe9  mov     edi, eax
0x18004cfeb  lea     rcx, [rsp+48h+arg_8]
0x18004cff0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004cff5  nop
0x18004cff6  mov     rcx, rbx; string
0x18004cff9  call    cs:__imp_WindowsDeleteString
0x18004cfff  mov     eax, edi
0x18004d001  jmp     short loc_18004D007
0x18004d003  mov     eax, dword ptr [rsp+48h+arg_8]
0x18004d007  mov     rbx, [rsp+48h+arg_0]
0x18004d00c  mov     rsi, [rsp+48h+arg_10]
0x18004d011  add     rsp, 40h
0x18004d015  pop     rdi
0x18004d016  retn
```
