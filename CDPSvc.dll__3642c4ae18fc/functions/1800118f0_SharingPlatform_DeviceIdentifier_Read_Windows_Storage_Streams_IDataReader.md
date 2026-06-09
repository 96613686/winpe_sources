# SharingPlatform::DeviceIdentifier::Read(Windows::Storage::Streams::IDataReader *)

- ea: `0x1800118f0`
- end: `0x180011aa4`
- name: `?Read@DeviceIdentifier@SharingPlatform@@UEAAJPEAUIDataReader@Streams@Storage@Windows@@@Z`
- size: `436`
- prototype: `int(SharingPlatform::DeviceIdentifier *__hidden this, struct Windows::Storage::Streams::IDataReader *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004928`
- `0x180010dfc`
- `0x1800118f0`
- `0x1800130ec`
- `0x180055b28`
- `0x180056290`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800119a3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800119a3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a74`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800119ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180011a74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800119f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a34`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011a89`
- `cdp!CDPCreateDeviceInternal` at `0x1800119be`
- `cdp!CDPCreateDeviceInternal` at `0x1800119be`

## pseudocode

```c
__int64 __fastcall SharingPlatform::DeviceIdentifier::Read(
        SharingPlatform::DeviceIdentifier *this,
        struct Windows::Storage::Streams::IDataReader *a2)
{
  HSTRING *v4; // r8
  int HString; // eax
  unsigned int v6; // ebx
  struct ICDPDeviceInfo **v7; // r8
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  SharingPlatform::Internal *v11; // rax
  HSTRING *v12; // r8
  __int64 v13; // rcx
  SharingPlatform::Internal *v14; // rax
  HSTRING *v15; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v19; // [rsp+50h] [rbp+30h] BYREF
  HSTRING string; // [rsp+58h] [rbp+38h] BYREF

  string = 0;
  WindowsDeleteString(0);
  string = 0;
  HString = SharingPlatform::Internal::ReadHString(a2, (struct Windows::Storage::Streams::IDataReader *)&string, v4);
  v6 = HString;
  if ( HString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)HString,
      savedregs);
    goto LABEL_17;
  }
  v19 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
  v8 = SharingPlatform::Internal::DeserializeICDPDeviceInfo((SharingPlatform::Internal *)string, (HSTRING)&v19, v7);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v8,
      savedregs);
LABEL_5:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
    goto LABEL_17;
  }
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 40);
  v9 = CDPCreateDeviceInternal(v19, 0, (char *)this + 40);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 132;
    goto LABEL_8;
  }
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  v11 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 112LL))(*((_QWORD *)this + 5));
  v9 = SharingPlatform::Internal::ConvertCStringToHSTRING(v11, (const char *)this + 24, v12);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 134;
    goto LABEL_8;
  }
  WindowsDeleteString(*((HSTRING *)this + 4));
  v13 = v19;
  *((_QWORD *)this + 4) = 0;
  v14 = (SharingPlatform::Internal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
  v9 = SharingPlatform::Internal::ConvertCStringToHSTRING(v14, (const char *)this + 32, v15);
  v6 = v9;
  if ( v9 < 0 )
  {
    v10 = 135;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v9,
      savedregs);
    if ( this != (SharingPlatform::DeviceIdentifier *)-48LL )
      ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
    goto LABEL_5;
  }
  if ( this != (SharingPlatform::DeviceIdentifier *)-48LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v19);
  v6 = 0;
LABEL_17:
  WindowsDeleteString(string);
  return v6;
}

```

## disassembly

```asm
0x1800118f0  mov     [rsp-18h+arg_0], rbx
0x1800118f5  mov     [rsp-18h+arg_8], rsi
0x1800118fa  push    rbp
0x1800118fb  push    rdi
0x1800118fc  push    r14; int
0x1800118fe  mov     rbp, rsp
0x180011901  sub     rsp, 20h
0x180011905  mov     rsi, rcx
0x180011908  mov     [rbp+string], 0
0x180011910  xor     ecx, ecx; string
0x180011912  mov     rbx, rdx
0x180011915  call    cs:__imp_WindowsDeleteString
0x18001191b  lea     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataReader *
0x18001191f  mov     [rbp+string], 0
0x180011927  mov     rcx, rbx; this
0x18001192a  call    ?ReadHString@Internal@SharingPlatform@@YAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ReadHString(Windows::Storage::Streams::IDataReader *,HSTRING__ * *)
0x18001192f  mov     ebx, eax
0x180011931  test    eax, eax
0x180011933  jns     short loc_180011952
0x180011935  mov     rcx, [rbp+18h]; this
0x180011939  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180011940  mov     r9d, eax; char *
0x180011943  mov     edx, 7Ah ; 'z'; void *
0x180011948  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001194d  jmp     loc_180011A85
0x180011952  lea     rcx, [rbp+arg_10]
0x180011956  mov     [rbp+arg_10], 0
0x18001195e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180011963  mov     rcx, [rbp+string]; this
0x180011967  lea     rdx, [rbp+arg_10]; HSTRING
0x18001196b  call    ?DeserializeICDPDeviceInfo@Internal@SharingPlatform@@YAJPEAUHSTRING__@@PEAPEAVICDPDeviceInfo@@@Z; SharingPlatform::Internal::DeserializeICDPDeviceInfo(HSTRING__ *,ICDPDeviceInfo * *)
0x180011970  mov     ebx, eax
0x180011972  test    eax, eax
0x180011974  jns     short loc_18001199C
0x180011976  mov     rcx, [rbp+18h]; this
0x18001197a  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180011981  mov     r9d, eax; char *
0x180011984  mov     edx, 7Dh ; '}'; void *
0x180011989  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001198e  lea     rcx, [rbp+arg_10]
0x180011992  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180011997  jmp     loc_180011A85
0x18001199c  lea     rdi, [rsi+30h]
0x1800119a0  mov     rcx, rdi; SRWLock
0x1800119a3  call    cs:__imp_AcquireSRWLockExclusive
0x1800119a9  lea     r14, [rsi+28h]
0x1800119ad  mov     rcx, r14
0x1800119b0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800119b5  mov     rcx, [rbp+arg_10]
0x1800119b9  mov     r8, r14
0x1800119bc  xor     edx, edx
0x1800119be  call    cs:__imp_CDPCreateDeviceInternal
0x1800119c4  mov     ebx, eax
0x1800119c6  test    eax, eax
0x1800119c8  jns     short loc_1800119F2
0x1800119ca  mov     edx, 84h; void *
0x1800119cf  mov     rcx, [rbp+18h]; this
0x1800119d3  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x1800119da  mov     r9d, eax; char *
0x1800119dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119e2  test    rdi, rdi
0x1800119e5  jz      short loc_18001198E
0x1800119e7  mov     rcx, rdi; SRWLock
0x1800119ea  call    cs:__imp_ReleaseSRWLockExclusive
0x1800119f0  jmp     short loc_18001198E
0x1800119f2  lea     rbx, [rsi+18h]
0x1800119f6  mov     rcx, [rbx]; string
0x1800119f9  call    cs:__imp_WindowsDeleteString
0x1800119ff  mov     qword ptr [rbx], 0
0x180011a06  mov     rcx, [r14]
0x180011a09  mov     rax, [rcx]
0x180011a0c  mov     rax, [rax+70h]
0x180011a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a15  mov     rdx, rbx; char *
0x180011a18  mov     rcx, rax; this
0x180011a1b  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180011a20  mov     ebx, eax
0x180011a22  test    eax, eax
0x180011a24  jns     short loc_180011A2D
0x180011a26  mov     edx, 86h
0x180011a2b  jmp     short loc_1800119CF
0x180011a2d  lea     rbx, [rsi+20h]
0x180011a31  mov     rcx, [rbx]; string
0x180011a34  call    cs:__imp_WindowsDeleteString
0x180011a3a  mov     rcx, [rbp+arg_10]
0x180011a3e  mov     qword ptr [rbx], 0
0x180011a45  mov     rax, [rcx]
0x180011a48  mov     rax, [rax+20h]
0x180011a4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011a51  mov     rdx, rbx; char *
0x180011a54  mov     rcx, rax; this
0x180011a57  call    ?ConvertCStringToHSTRING@Internal@SharingPlatform@@YAJPEBDPEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ConvertCStringToHSTRING(char const *,HSTRING__ * *)
0x180011a5c  mov     ebx, eax
0x180011a5e  test    eax, eax
0x180011a60  jns     short loc_180011A6C
0x180011a62  mov     edx, 87h
0x180011a67  jmp     loc_1800119CF
0x180011a6c  test    rdi, rdi
0x180011a6f  jz      short loc_180011A7A
0x180011a71  mov     rcx, rdi; SRWLock
0x180011a74  call    cs:__imp_ReleaseSRWLockExclusive
0x180011a7a  lea     rcx, [rbp+arg_10]
0x180011a7e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180011a83  xor     ebx, ebx
0x180011a85  mov     rcx, [rbp+string]; string
0x180011a89  call    cs:__imp_WindowsDeleteString
0x180011a8f  mov     rsi, [rsp+20h+arg_8]
0x180011a94  mov     eax, ebx
0x180011a96  mov     rbx, [rsp+20h+arg_0]
0x180011a9b  add     rsp, 20h
0x180011a9f  pop     r14
0x180011aa1  pop     rdi
0x180011aa2  pop     rbp
0x180011aa3  retn
```
