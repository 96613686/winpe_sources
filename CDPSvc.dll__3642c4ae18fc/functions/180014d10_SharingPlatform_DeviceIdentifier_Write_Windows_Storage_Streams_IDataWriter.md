# SharingPlatform::DeviceIdentifier::Write(Windows::Storage::Streams::IDataWriter *)

- ea: `0x180014d10`
- end: `0x180014e40`
- name: `?Write@DeviceIdentifier@SharingPlatform@@UEBAJPEAUIDataWriter@Streams@Storage@Windows@@@Z`
- size: `304`
- prototype: `int(SharingPlatform::DeviceIdentifier *__hidden this, struct Windows::Storage::Streams::IDataWriter *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x1800130ec`
- `0x180014d10`
- `0x1800563b0`
- `0x1800564f4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014d3a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014d3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014da0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014d8d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014db0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ded`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e12`

## pseudocode

```c
__int64 __fastcall SharingPlatform::DeviceIdentifier::Write(
        RTL_SRWLOCK *this,
        struct Windows::Storage::Streams::IDataWriter *a2)
{
  RTL_SRWLOCK *v2; // rsi
  PVOID Ptr; // rdi
  __int64 (__fastcall *v6)(PVOID, SharingPlatform::Internal **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  HSTRING *v9; // r8
  int v10; // eax
  HSTRING v11; // r8
  __int64 v12; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF
  SharingPlatform::Internal *v17; // [rsp+50h] [rbp+30h] BYREF

  v2 = this + 6;
  v17 = 0;
  AcquireSRWLockShared(this + 6);
  Ptr = this[5].Ptr;
  v6 = *(__int64 (__fastcall **)(PVOID, SharingPlatform::Internal **))(*(_QWORD *)Ptr + 32LL);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
  v7 = v6(Ptr, &v17);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( v2 )
      ReleaseSRWLockShared(v2);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v10 = SharingPlatform::Internal::SerializeICDPDeviceInfo(v17, (struct ICDPDeviceInfo *)&string, v9);
    v8 = v10;
    if ( v10 >= 0 )
    {
      v10 = SharingPlatform::Internal::WriteHString(a2, (struct Windows::Storage::Streams::IDataWriter *)string, v11);
      v8 = v10;
      if ( v10 >= 0 )
      {
        WindowsDeleteString(string);
        v8 = 0;
        goto LABEL_12;
      }
      v12 = 113;
    }
    else
    {
      v12 = 111;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v10,
      savedregs);
    WindowsDeleteString(string);
LABEL_12:
    string = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6B,
    (unsigned int)".\\deviceidentifier.cpp",
    (const char *)(unsigned int)v7,
    savedregs);
  if ( v2 )
    ReleaseSRWLockShared(v2);
LABEL_13:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v17);
  return v8;
}

```

## disassembly

```asm
0x180014d10  mov     [rsp-18h+arg_8], rbx
0x180014d15  mov     [rsp-18h+arg_18], rsi
0x180014d1a  push    rbp
0x180014d1b  push    rdi
0x180014d1c  push    r14; int
0x180014d1e  mov     rbp, rsp
0x180014d21  sub     rsp, 20h
0x180014d25  lea     rsi, [rcx+30h]
0x180014d29  mov     [rbp+arg_10], 0
0x180014d31  mov     rbx, rcx
0x180014d34  mov     r14, rdx
0x180014d37  mov     rcx, rsi; SRWLock
0x180014d3a  call    cs:__imp_AcquireSRWLockShared
0x180014d40  mov     rdi, [rbx+28h]
0x180014d44  lea     rcx, [rbp+arg_10]
0x180014d48  mov     rax, [rdi]
0x180014d4b  mov     rbx, [rax+20h]
0x180014d4f  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180014d54  lea     rdx, [rbp+arg_10]
0x180014d58  mov     rcx, rdi
0x180014d5b  mov     rax, rbx
0x180014d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d63  mov     ebx, eax
0x180014d65  test    eax, eax
0x180014d67  jns     short loc_180014D98
0x180014d69  mov     rcx, [rbp+18h]; this
0x180014d6d  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180014d74  mov     r9d, eax; char *
0x180014d77  mov     edx, 6Bh ; 'k'; void *
0x180014d7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d81  test    rsi, rsi
0x180014d84  jz      loc_180014E22
0x180014d8a  mov     rcx, rsi; SRWLock
0x180014d8d  call    cs:__imp_ReleaseSRWLockShared
0x180014d93  jmp     loc_180014E22
0x180014d98  test    rsi, rsi
0x180014d9b  jz      short loc_180014DA6
0x180014d9d  mov     rcx, rsi; SRWLock
0x180014da0  call    cs:__imp_ReleaseSRWLockShared
0x180014da6  xor     ecx, ecx; string
0x180014da8  mov     [rbp+string], 0
0x180014db0  call    cs:__imp_WindowsDeleteString
0x180014db6  mov     rcx, [rbp+arg_10]; this
0x180014dba  lea     rdx, [rbp+string]; struct ICDPDeviceInfo *
0x180014dbe  mov     [rbp+string], 0
0x180014dc6  call    ?SerializeICDPDeviceInfo@Internal@SharingPlatform@@YAJPEAVICDPDeviceInfo@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::SerializeICDPDeviceInfo(ICDPDeviceInfo *,HSTRING__ * *)
0x180014dcb  mov     ebx, eax
0x180014dcd  test    eax, eax
0x180014dcf  jns     short loc_180014DF5
0x180014dd1  mov     edx, 6Fh ; 'o'; void *
0x180014dd6  mov     rcx, [rbp+18h]; this
0x180014dda  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x180014de1  mov     r9d, eax; char *
0x180014de4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014de9  mov     rcx, [rbp+string]; string
0x180014ded  call    cs:__imp_WindowsDeleteString
0x180014df3  jmp     short loc_180014E1A
0x180014df5  mov     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataWriter *
0x180014df9  mov     rcx, r14; this
0x180014dfc  call    ?WriteHString@Internal@SharingPlatform@@YAJPEAUIDataWriter@Streams@Storage@Windows@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::WriteHString(Windows::Storage::Streams::IDataWriter *,HSTRING__ *)
0x180014e01  mov     ebx, eax
0x180014e03  test    eax, eax
0x180014e05  jns     short loc_180014E0E
0x180014e07  mov     edx, 71h ; 'q'
0x180014e0c  jmp     short loc_180014DD6
0x180014e0e  mov     rcx, [rbp+string]; string
0x180014e12  call    cs:__imp_WindowsDeleteString
0x180014e18  xor     ebx, ebx
0x180014e1a  mov     [rbp+string], 0
0x180014e22  lea     rcx, [rbp+arg_10]
0x180014e26  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180014e2b  mov     rsi, [rsp+20h+arg_18]
0x180014e30  mov     eax, ebx
0x180014e32  mov     rbx, [rsp+20h+arg_8]
0x180014e37  add     rsp, 20h
0x180014e3b  pop     r14
0x180014e3d  pop     rdi
0x180014e3e  pop     rbp
0x180014e3f  retn
```
