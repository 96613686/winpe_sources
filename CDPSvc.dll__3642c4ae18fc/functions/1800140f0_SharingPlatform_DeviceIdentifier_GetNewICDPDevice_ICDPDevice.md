# SharingPlatform::DeviceIdentifier::GetNewICDPDevice(ICDPDevice * *)

- ea: `0x1800140f0`
- end: `0x180014241`
- name: `?GetNewICDPDevice@DeviceIdentifier@SharingPlatform@@UEAAJPEAPEAVICDPDevice@@@Z`
- size: `337`
- prototype: `int(SharingPlatform::DeviceIdentifier *__hidden this, struct ICDPDevice **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x1800130ec`
- `0x1800140f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014140`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014140`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014193`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800141a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014193`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800141a6`
- `cdp!CDPCreateDeviceQueryInternal` at `0x1800141c5`
- `cdp!CDPCreateDeviceQueryInternal` at `0x1800141c5`

## pseudocode

```c
__int64 __fastcall SharingPlatform::DeviceIdentifier::GetNewICDPDevice(RTL_SRWLOCK *this, struct ICDPDevice **a2)
{
  unsigned int v4; // ebx
  RTL_SRWLOCK *v5; // rsi
  PVOID Ptr; // rdi
  __int64 (__fastcall *v7)(PVOID, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v15; // [rsp+48h] [rbp+28h] BYREF
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF

  if ( a2 )
  {
    v5 = this + 7;
    v16 = 0;
    AcquireSRWLockShared(this + 7);
    Ptr = this[6].Ptr;
    v7 = *(__int64 (__fastcall **)(PVOID, __int64 *))(*(_QWORD *)Ptr + 32LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
    v8 = v7(Ptr, &v16);
    v4 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)".\\deviceidentifier.cpp",
        (const char *)(unsigned int)v8,
        savedregs);
      if ( v5 )
        ReleaseSRWLockShared(v5);
      goto LABEL_14;
    }
    if ( v5 )
      ReleaseSRWLockShared(v5);
    v15 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
    LOBYTE(v9) = 1;
    v10 = CDPCreateDeviceQueryInternal(v9, 0, &v15);
    v4 = v10;
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, struct ICDPDevice **))(*(_QWORD *)v15 + 104LL))(v15, v16, a2);
      v4 = v10;
      if ( v10 >= 0 )
      {
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
        v4 = 0;
        goto LABEL_14;
      }
      v11 = 68;
    }
    else
    {
      v11 = 67;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)".\\deviceidentifier.cpp",
      (const char *)(unsigned int)v10,
      savedregs);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v15);
LABEL_14:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v16);
    return v4;
  }
  v4 = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A,
    (unsigned int)".\\deviceidentifier.cpp",
    (const char *)0x80004003LL,
    savedregs);
  return v4;
}

```

## disassembly

```asm
0x1800140f0  mov     [rsp-18h+arg_0], rbx
0x1800140f5  mov     [rsp-18h+arg_18], rsi
0x1800140fa  push    rbp
0x1800140fb  push    rdi
0x1800140fc  push    r14; int
0x1800140fe  mov     rbp, rsp
0x180014101  sub     rsp, 20h
0x180014105  mov     r14, rdx
0x180014108  mov     rdi, rcx
0x18001410b  test    rdx, rdx
0x18001410e  jnz     short loc_180014131
0x180014110  mov     rcx, [rbp+18h]; this
0x180014114  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x18001411b  mov     ebx, 80004003h
0x180014120  lea     edx, [r14+3Ah]; void *
0x180014124  mov     r9d, ebx; char *
0x180014127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001412c  jmp     loc_18001422C
0x180014131  lea     rsi, [rcx+38h]
0x180014135  mov     [rbp+arg_10], 0
0x18001413d  mov     rcx, rsi; SRWLock
0x180014140  call    cs:__imp_AcquireSRWLockShared
0x180014146  mov     rdi, [rdi+30h]
0x18001414a  lea     rcx, [rbp+arg_10]
0x18001414e  mov     rax, [rdi]
0x180014151  mov     rbx, [rax+20h]
0x180014155  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001415a  lea     rdx, [rbp+arg_10]
0x18001415e  mov     rcx, rdi
0x180014161  mov     rax, rbx
0x180014164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014169  mov     ebx, eax
0x18001416b  test    eax, eax
0x18001416d  jns     short loc_18001419E
0x18001416f  mov     rcx, [rbp+18h]; this
0x180014173  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x18001417a  mov     r9d, eax; char *
0x18001417d  mov     edx, 3Fh ; '?'; void *
0x180014182  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014187  test    rsi, rsi
0x18001418a  jz      loc_180014223
0x180014190  mov     rcx, rsi; SRWLock
0x180014193  call    cs:__imp_ReleaseSRWLockShared
0x180014199  jmp     loc_180014223
0x18001419e  test    rsi, rsi
0x1800141a1  jz      short loc_1800141AC
0x1800141a3  mov     rcx, rsi; SRWLock
0x1800141a6  call    cs:__imp_ReleaseSRWLockShared
0x1800141ac  lea     rcx, [rbp+arg_8]
0x1800141b0  mov     [rbp+arg_8], 0
0x1800141b8  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800141bd  lea     r8, [rbp+arg_8]
0x1800141c1  xor     edx, edx
0x1800141c3  mov     cl, 1
0x1800141c5  call    cs:__imp_CDPCreateDeviceQueryInternal
0x1800141cb  mov     ebx, eax
0x1800141cd  test    eax, eax
0x1800141cf  jns     short loc_1800141F4
0x1800141d1  mov     edx, 43h ; 'C'; void *
0x1800141d6  mov     rcx, [rbp+18h]; this
0x1800141da  lea     r8, aDeviceidentifi; ".\\deviceidentifier.cpp"
0x1800141e1  mov     r9d, eax; char *
0x1800141e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141e9  lea     rcx, [rbp+arg_8]
0x1800141ed  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800141f2  jmp     short loc_180014223
0x1800141f4  mov     rcx, [rbp+arg_8]
0x1800141f8  mov     r8, r14
0x1800141fb  mov     rdx, [rbp+arg_10]
0x1800141ff  mov     rax, [rcx]
0x180014202  mov     rax, [rax+68h]
0x180014206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001420b  mov     ebx, eax
0x18001420d  test    eax, eax
0x18001420f  jns     short loc_180014218
0x180014211  mov     edx, 44h ; 'D'
0x180014216  jmp     short loc_1800141D6
0x180014218  lea     rcx, [rbp+arg_8]
0x18001421c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180014221  xor     ebx, ebx
0x180014223  lea     rcx, [rbp+arg_10]
0x180014227  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001422c  mov     rsi, [rsp+20h+arg_18]
0x180014231  mov     eax, ebx
0x180014233  mov     rbx, [rsp+20h+arg_0]
0x180014238  add     rsp, 20h
0x18001423c  pop     r14
0x18001423e  pop     rdi
0x18001423f  pop     rbp
0x180014240  retn
```
