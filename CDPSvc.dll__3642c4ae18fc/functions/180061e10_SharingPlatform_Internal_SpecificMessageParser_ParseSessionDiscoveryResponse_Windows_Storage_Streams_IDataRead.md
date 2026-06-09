# SharingPlatform::Internal::SpecificMessageParser::ParseSessionDiscoveryResponse(Windows::Storage::Streams::IDataReader *,ICDPDevice *,Windows::Foundation::Collections::IVector<SharingPlatform::ISessionIdentifier *> *)

- ea: `0x180061e10`
- end: `0x18006200b`
- name: `?ParseSessionDiscoveryResponse@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAVICDPDevice@@PEAU?$IVector@PEAUISessionIdentifier@SharingPlatform@@@Collections@Foundation@7@@Z`
- size: `507`
- prototype: `__int64 __fastcall(SharingPlatform::Internal *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180060aa0`

## callees

- `0x180004928`
- `0x1800130ec`
- `0x1800225a0`
- `0x1800467e8`
- `0x18004fff0`
- `0x180056334`
- `0x180061e10`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061fdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061ea3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061f5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180061fdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SharingPlatform::Internal::SpecificMessageParser::ParseSessionDiscoveryResponse(
        SharingPlatform::Internal *this,
        __int64 a2,
        __int64 a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  int i; // edi
  HSTRING *v9; // r8
  int ShortStringAndLength; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // [rsp+20h] [rbp-50h] BYREF
  __int64 v15; // [rsp+28h] [rbp-48h] BYREF
  void *v16; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  _QWORD v18[3]; // [rsp+40h] [rbp-30h] BYREF
  struct _GUID v19; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v18[0] = a2;
  v5 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, int *))(*(_QWORD *)this + 104LL))(this, &v14);
  if ( v5 >= 0 )
  {
    for ( i = 0; i < (unsigned __int8)v14; ++i )
    {
      v5 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, struct _GUID *))(*(_QWORD *)this + 136LL))(
             this,
             &v19);
      if ( v5 < 0 )
      {
        v6 = 174;
        goto LABEL_3;
      }
      string = 0;
      WindowsDeleteString(0);
      string = 0;
      ShortStringAndLength = SharingPlatform::Internal::ReadShortStringAndLength(
                               this,
                               (struct Windows::Storage::Streams::IDataReader *)&string,
                               v9);
      v5 = ShortStringAndLength;
      if ( ShortStringAndLength < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB2,
          (unsigned int)".\\specificmessageparser.cpp",
          (const char *)(unsigned int)ShortStringAndLength,
          v14);
        goto LABEL_19;
      }
      v15 = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
      v11 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceIdentifier,SharingPlatform::IDeviceIdentifier,ICDPDevice *>(
              &v15,
              v18);
      v5 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)".\\specificmessageparser.cpp",
          (const char *)(unsigned int)v11,
          v14);
        goto LABEL_17;
      }
      v16 = 0;
      v18[1] = v15;
      v18[2] = string;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
      v12 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::SessionIdentifier,SharingPlatform::ISessionIdentifier,_GUID &,HSTRING__ * &,SharingPlatform::IDeviceIdentifier * &>(
              &v16,
              &v19);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 184;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v13,
          (unsigned int)".\\specificmessageparser.cpp",
          (const char *)(unsigned int)v12,
          v14);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
LABEL_17:
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
LABEL_19:
        WindowsDeleteString(string);
        return (unsigned int)v5;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a3 + 104LL))(a3, v16);
      v5 = v12;
      if ( v12 < 0 )
      {
        v13 = 186;
        goto LABEL_15;
      }
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
      WindowsDeleteString(string);
      string = 0;
    }
    return 0;
  }
  else
  {
    v6 = 168;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)".\\specificmessageparser.cpp",
      (const char *)(unsigned int)v5,
      v14);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180061e10  push    rbp
0x180061e12  push    rbx
0x180061e13  push    rsi
0x180061e14  push    rdi
0x180061e15  push    r14
0x180061e17  mov     rbp, rsp
0x180061e1a  sub     rsp, 70h
0x180061e1e  mov     rax, cs:__security_cookie
0x180061e25  xor     rax, rsp
0x180061e28  mov     [rbp+var_8], rax
0x180061e2c  mov     r14, r8
0x180061e2f  mov     rsi, rcx
0x180061e32  mov     [rbp+var_30], rdx
0x180061e36  mov     rax, [rcx]
0x180061e39  lea     rdx, [rbp+var_50]
0x180061e3d  mov     rax, [rax+68h]
0x180061e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e46  mov     ebx, eax
0x180061e48  test    eax, eax
0x180061e4a  jns     short loc_180061E6B
0x180061e4c  mov     edx, 0A8h; void *
0x180061e51  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180061e58  mov     r9d, ebx; char *
0x180061e5b  mov     rcx, [rbp+28h]; this
0x180061e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061e64  mov     eax, ebx
0x180061e66  jmp     loc_180061FF4
0x180061e6b  xor     edi, edi
0x180061e6d  movzx   eax, byte ptr [rbp+var_50]
0x180061e71  cmp     edi, eax
0x180061e73  jge     loc_180061FF2
0x180061e79  mov     rax, [rsi]
0x180061e7c  lea     rdx, [rbp+var_18]
0x180061e80  mov     rcx, rsi
0x180061e83  mov     rax, [rax+88h]
0x180061e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061e8f  mov     ebx, eax
0x180061e91  test    eax, eax
0x180061e93  js      loc_180061FE8
0x180061e99  mov     [rbp+string], 0
0x180061ea1  xor     ecx, ecx; string
0x180061ea3  call    cs:__imp_WindowsDeleteString
0x180061ea9  mov     [rbp+string], 0
0x180061eb1  lea     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataReader *
0x180061eb5  mov     rcx, rsi; this
0x180061eb8  call    ?ReadShortStringAndLength@Internal@SharingPlatform@@YAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ReadShortStringAndLength(Windows::Storage::Streams::IDataReader *,HSTRING__ * *)
0x180061ebd  mov     ebx, eax
0x180061ebf  test    eax, eax
0x180061ec1  js      loc_180061FC0
0x180061ec7  mov     [rbp+var_48], 0
0x180061ecf  lea     rcx, [rbp+var_48]
0x180061ed3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061ed8  lea     rdx, [rbp+var_30]
0x180061edc  lea     rcx, [rbp+var_48]
0x180061ee0  call    ??$MakeAndInitialize@VDeviceIdentifier@SharingPlatform@@UIDeviceIdentifier@2@PEAVICDPDevice@@@Details@WRL@Microsoft@@YAJPEAPEAUIDeviceIdentifier@SharingPlatform@@$$QEAPEAVICDPDevice@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceIdentifier,SharingPlatform::IDeviceIdentifier,ICDPDevice *>(SharingPlatform::IDeviceIdentifier * *,ICDPDevice * &&)
0x180061ee5  mov     ebx, eax
0x180061ee7  test    eax, eax
0x180061ee9  js      loc_180061F9C
0x180061eef  mov     [rbp+var_40], 0
0x180061ef7  mov     rax, [rbp+var_48]
0x180061efb  mov     [rbp+var_28], rax
0x180061eff  mov     rax, [rbp+string]
0x180061f03  mov     [rbp+var_20], rax
0x180061f07  lea     rcx, [rbp+var_40]
0x180061f0b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061f10  lea     r9, [rbp+var_28]
0x180061f14  lea     r8, [rbp+var_20]
0x180061f18  lea     rdx, [rbp+var_18]; struct _GUID *
0x180061f1c  lea     rcx, [rbp+var_40]; void **
0x180061f20  call    ??$MakeAndInitialize@VSessionIdentifier@SharingPlatform@@UISessionIdentifier@2@AEAU_GUID@@AEAPEAUHSTRING__@@AEAPEAUIDeviceIdentifier@2@@Details@WRL@Microsoft@@YAJPEAPEAUISessionIdentifier@SharingPlatform@@AEAU_GUID@@AEAPEAUHSTRING__@@AEAPEAUIDeviceIdentifier@4@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::SessionIdentifier,SharingPlatform::ISessionIdentifier,_GUID &,HSTRING__ * &,SharingPlatform::IDeviceIdentifier * &>(SharingPlatform::ISessionIdentifier * *,_GUID &,HSTRING__ * &,SharingPlatform::IDeviceIdentifier * &)
0x180061f25  mov     ebx, eax
0x180061f27  test    eax, eax
0x180061f29  js      short loc_180061F78
0x180061f2b  mov     rax, [r14]
0x180061f2e  mov     rdx, [rbp+var_40]
0x180061f32  mov     rcx, r14
0x180061f35  mov     rax, [rax+68h]
0x180061f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f3e  mov     ebx, eax
0x180061f40  test    eax, eax
0x180061f42  js      short loc_180061F71
0x180061f44  lea     rcx, [rbp+var_40]
0x180061f48  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061f4d  nop
0x180061f4e  lea     rcx, [rbp+var_48]
0x180061f52  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061f57  nop
0x180061f58  mov     rcx, [rbp+string]; string
0x180061f5c  call    cs:__imp_WindowsDeleteString
0x180061f62  mov     [rbp+string], 0
0x180061f6a  inc     edi
0x180061f6c  jmp     loc_180061E6D
0x180061f71  mov     edx, 0BAh
0x180061f76  jmp     short loc_180061F7D
0x180061f78  mov     edx, 0B8h; void *
0x180061f7d  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180061f84  mov     r9d, eax; char *
0x180061f87  mov     rcx, [rbp+28h]; this
0x180061f8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061f90  nop
0x180061f91  lea     rcx, [rbp+var_40]
0x180061f95  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061f9a  jmp     short loc_180061FB5
0x180061f9c  mov     rcx, [rbp+28h]; this
0x180061fa0  mov     r9d, eax; char *
0x180061fa3  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180061faa  mov     edx, 0B5h; void *
0x180061faf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061fb4  nop
0x180061fb5  lea     rcx, [rbp+var_48]
0x180061fb9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180061fbe  jmp     short loc_180061FD9
0x180061fc0  mov     rcx, [rbp+28h]; this
0x180061fc4  mov     r9d, eax; char *
0x180061fc7  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180061fce  mov     edx, 0B2h; void *
0x180061fd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180061fd8  nop
0x180061fd9  mov     rcx, [rbp+string]; string
0x180061fdd  call    cs:__imp_WindowsDeleteString
0x180061fe3  jmp     loc_180061E64
0x180061fe8  mov     edx, 0AEh
0x180061fed  jmp     loc_180061E51
0x180061ff2  xor     eax, eax
0x180061ff4  mov     rcx, [rbp+var_8]
0x180061ff8  xor     rcx, rsp; StackCookie
0x180061ffb  call    __security_check_cookie
0x180062000  add     rsp, 70h
0x180062004  pop     r14
0x180062006  pop     rdi
0x180062007  pop     rsi
0x180062008  pop     rbx
0x180062009  pop     rbp
0x18006200a  retn
```
