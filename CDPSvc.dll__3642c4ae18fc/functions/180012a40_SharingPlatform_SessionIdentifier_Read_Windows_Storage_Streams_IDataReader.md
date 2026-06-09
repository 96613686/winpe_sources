# SharingPlatform::SessionIdentifier::Read(Windows::Storage::Streams::IDataReader *)

- ea: `0x180012a40`
- end: `0x180012c25`
- name: `?Read@SessionIdentifier@SharingPlatform@@UEAAJPEAUIDataReader@Streams@Storage@Windows@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(SharingPlatform::SessionIdentifier *this, struct Windows::Storage::Streams::IDataReader *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x180012a40`
- `0x1800130ec`
- `0x180019bb0`
- `0x180022acc`
- `0x180023148`
- `0x180047508`
- `0x180048d10`
- `0x180056334`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012a5f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180012a5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012bb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c0a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012aa2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012bb9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012c0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ab6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012ab6`

## pseudocode

```c
__int64 __fastcall SharingPlatform::SessionIdentifier::Read(
        SharingPlatform::SessionIdentifier *this,
        struct Windows::Storage::Streams::IDataReader *a2)
{
  RTL_SRWLOCK *v4; // rbp
  int ShortStringAndLength; // ebx
  __int64 v6; // rdx
  HSTRING *v8; // r8
  __int64 (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rbx
  SharingPlatform::DeviceIdentifier *v10; // rax
  SharingPlatform::DeviceIdentifier *v11; // rdi
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, GUID *, char *); // rbx
  __int64 v14; // rdx
  int v15; // eax
  unsigned int v16; // edi
  __int64 (__fastcall *v17)(_QWORD, GUID *, char *); // rdi
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // [rsp+40h] [rbp+8h] BYREF
  SharingPlatform::DeviceIdentifier *v21; // [rsp+48h] [rbp+10h] BYREF

  v4 = (RTL_SRWLOCK *)((char *)this + 56);
  AcquireSRWLockExclusive((PSRWLOCK)this + 7);
  ShortStringAndLength = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IDataReader *, char *))(*(_QWORD *)a2 + 136LL))(
                           a2,
                           (char *)this + 24);
  if ( ShortStringAndLength < 0 )
  {
    v6 = 67;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)".\\sessionidentifier.cpp",
      (const char *)(unsigned int)ShortStringAndLength,
      v18);
LABEL_4:
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return (unsigned int)ShortStringAndLength;
  }
  WindowsDeleteString(*((HSTRING *)this + 5));
  *((_QWORD *)this + 5) = 0;
  ShortStringAndLength = SharingPlatform::Internal::ReadShortStringAndLength(
                           a2,
                           (SharingPlatform::SessionIdentifier *)((char *)this + 40),
                           v8);
  if ( ShortStringAndLength < 0 )
  {
    v6 = 70;
    goto LABEL_3;
  }
  v9 = 0;
  v20 = 0;
  v10 = (SharingPlatform::DeviceIdentifier *)operator new(0x50u, (const struct std::nothrow_t *)std::nothrow);
  v11 = v10;
  v21 = v10;
  if ( v10 )
  {
    memset_0(v10, 0, 0x50u);
    v12 = SharingPlatform::DeviceIdentifier::DeviceIdentifier(v11);
    Microsoft::WRL::ComPtr<SharingPlatform::DeviceIdentifier>::Attach(&v20, v12);
    v21 = 0;
    v9 = v20;
  }
  Microsoft::WRL::Details::MakeAllocator<SharingPlatform::SharingSessionMessageReceivedEventArgs>::~MakeAllocator<SharingPlatform::SharingSessionMessageReceivedEventArgs>(&v21);
  v13 = (__int64 (__fastcall ***)(_QWORD, GUID *, char *))((unsigned __int64)(v9 + 3) & -(__int64)(v9 != 0));
  v20 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v13;
  if ( !v13 )
  {
    ShortStringAndLength = -2147024882;
    v14 = 74;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)".\\sessionidentifier.cpp",
      (const char *)(unsigned int)ShortStringAndLength,
      v18);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
    goto LABEL_4;
  }
  v15 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, char *), struct Windows::Storage::Streams::IDataReader *))(*v13)[7])(
          v13,
          a2);
  v16 = v15;
  if ( v15 >= 0 )
  {
    v17 = **v13;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 48);
    ShortStringAndLength = v17(v13, &GUID_11b48e3f_e93f_4960_8998_f755b4d9c64d, (char *)this + 48);
    if ( ShortStringAndLength < 0 )
    {
      v14 = 76;
      goto LABEL_13;
    }
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)".\\sessionidentifier.cpp",
      (const char *)(unsigned int)v15,
      v18);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v20);
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
    return v16;
  }
}

```

## disassembly

```asm
0x180012a40  mov     [rsp+arg_10], rbx
0x180012a45  mov     [rsp+arg_18], rbp
0x180012a4a  push    rsi
0x180012a4b  push    rdi
0x180012a4c  push    r14; int
0x180012a4e  sub     rsp, 20h
0x180012a52  mov     rsi, rdx
0x180012a55  mov     r14, rcx
0x180012a58  lea     rbp, [rcx+38h]
0x180012a5c  mov     rcx, rbp; SRWLock
0x180012a5f  call    cs:__imp_AcquireSRWLockExclusive
0x180012a65  mov     rax, [rsi]
0x180012a68  lea     rdx, [r14+18h]
0x180012a6c  mov     rcx, rsi
0x180012a6f  mov     rax, [rax+88h]
0x180012a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a7b  mov     ebx, eax
0x180012a7d  test    eax, eax
0x180012a7f  jns     short loc_180012AAF
0x180012a81  mov     edx, 43h ; 'C'; void *
0x180012a86  lea     r8, aSessionidentif; ".\\sessionidentifier.cpp"
0x180012a8d  mov     r9d, ebx; char *
0x180012a90  mov     rcx, [rsp+38h]; this
0x180012a95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012a9a  test    rbp, rbp
0x180012a9d  jz      short loc_180012AA8
0x180012a9f  mov     rcx, rbp; SRWLock
0x180012aa2  call    cs:__imp_ReleaseSRWLockExclusive
0x180012aa8  mov     eax, ebx
0x180012aaa  jmp     loc_180012C12
0x180012aaf  lea     rbx, [r14+28h]
0x180012ab3  mov     rcx, [rbx]; string
0x180012ab6  call    cs:__imp_WindowsDeleteString
0x180012abc  mov     qword ptr [rbx], 0
0x180012ac3  mov     rdx, rbx; struct Windows::Storage::Streams::IDataReader *
0x180012ac6  mov     rcx, rsi; this
0x180012ac9  call    ?ReadShortStringAndLength@Internal@SharingPlatform@@YAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ReadShortStringAndLength(Windows::Storage::Streams::IDataReader *,HSTRING__ * *)
0x180012ace  mov     ebx, eax
0x180012ad0  test    eax, eax
0x180012ad2  jns     short loc_180012ADB
0x180012ad4  mov     edx, 46h ; 'F'
0x180012ad9  jmp     short loc_180012A86
0x180012adb  xor     ebx, ebx
0x180012add  mov     [rsp+38h+arg_0], rbx
0x180012ae2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180012ae9  lea     ecx, [rbx+50h]; unsigned __int64
0x180012aec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180012af1  mov     rdi, rax
0x180012af4  mov     [rsp+38h+arg_8], rax
0x180012af9  test    rax, rax
0x180012afc  jz      short loc_180012B2B
0x180012afe  xor     edx, edx; Val
0x180012b00  lea     r8d, [rbx+50h]; Size
0x180012b04  mov     rcx, rax; void *
0x180012b07  call    memset_0
0x180012b0c  mov     rcx, rdi; this
0x180012b0f  call    ??0DeviceIdentifier@SharingPlatform@@QEAA@XZ; SharingPlatform::DeviceIdentifier::DeviceIdentifier(void)
0x180012b14  mov     rdx, rax
0x180012b17  lea     rcx, [rsp+38h+arg_0]
0x180012b1c  call    ?Attach@?$ComPtr@VDeviceIdentifier@SharingPlatform@@@WRL@Microsoft@@QEAAXPEAVDeviceIdentifier@SharingPlatform@@@Z; Microsoft::WRL::ComPtr<SharingPlatform::DeviceIdentifier>::Attach(SharingPlatform::DeviceIdentifier *)
0x180012b21  mov     [rsp+38h+arg_8], rbx
0x180012b26  mov     rbx, [rsp+38h+arg_0]
0x180012b2b  lea     rcx, [rsp+38h+arg_8]
0x180012b30  call    ??1?$MakeAllocator@VSharingSessionMessageReceivedEventArgs@SharingPlatform@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SharingPlatform::SharingSessionMessageReceivedEventArgs>::~MakeAllocator<SharingPlatform::SharingSessionMessageReceivedEventArgs>(void)
0x180012b35  lea     rax, [rbx+18h]
0x180012b39  neg     rbx
0x180012b3c  sbb     rbx, rbx
0x180012b3f  and     rbx, rax
0x180012b42  mov     [rsp+38h+arg_0], rbx
0x180012b47  jnz     short loc_180012B76
0x180012b49  mov     ebx, 8007000Eh
0x180012b4e  mov     edx, 4Ah ; 'J'; void *
0x180012b53  lea     r8, aSessionidentif; ".\\sessionidentifier.cpp"
0x180012b5a  mov     r9d, ebx; char *
0x180012b5d  mov     rcx, [rsp+38h]; this
0x180012b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012b67  lea     rcx, [rsp+38h+arg_0]
0x180012b6c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180012b71  jmp     loc_180012A9A
0x180012b76  mov     rax, [rbx]
0x180012b79  mov     rdx, rsi
0x180012b7c  mov     rcx, rbx
0x180012b7f  mov     rax, [rax+38h]
0x180012b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012b88  mov     edi, eax
0x180012b8a  test    eax, eax
0x180012b8c  jns     short loc_180012BC3
0x180012b8e  mov     rcx, [rsp+38h]; this
0x180012b93  mov     r9d, eax; char *
0x180012b96  lea     r8, aSessionidentif; ".\\sessionidentifier.cpp"
0x180012b9d  mov     edx, 4Bh ; 'K'; void *
0x180012ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012ba7  lea     rcx, [rsp+38h+arg_0]
0x180012bac  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180012bb1  test    rbp, rbp
0x180012bb4  jz      short loc_180012BBF
0x180012bb6  mov     rcx, rbp; SRWLock
0x180012bb9  call    cs:__imp_ReleaseSRWLockExclusive
0x180012bbf  mov     eax, edi
0x180012bc1  jmp     short loc_180012C12
0x180012bc3  mov     rax, [rbx]
0x180012bc6  mov     rdi, [rax]
0x180012bc9  lea     rcx, [r14+30h]
0x180012bcd  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180012bd2  lea     r8, [r14+30h]
0x180012bd6  lea     rdx, _GUID_11b48e3f_e93f_4960_8998_f755b4d9c64d
0x180012bdd  mov     rcx, rbx
0x180012be0  mov     rax, rdi
0x180012be3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012be8  mov     ebx, eax
0x180012bea  test    eax, eax
0x180012bec  jns     short loc_180012BF8
0x180012bee  mov     edx, 4Ch ; 'L'
0x180012bf3  jmp     loc_180012B53
0x180012bf8  lea     rcx, [rsp+38h+arg_0]
0x180012bfd  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180012c02  test    rbp, rbp
0x180012c05  jz      short loc_180012C10
0x180012c07  mov     rcx, rbp; SRWLock
0x180012c0a  call    cs:__imp_ReleaseSRWLockExclusive
0x180012c10  xor     eax, eax
0x180012c12  mov     rbx, [rsp+38h+arg_10]
0x180012c17  mov     rbp, [rsp+38h+arg_18]
0x180012c1c  add     rsp, 20h
0x180012c20  pop     r14
0x180012c22  pop     rdi
0x180012c23  pop     rsi
0x180012c24  retn
```
