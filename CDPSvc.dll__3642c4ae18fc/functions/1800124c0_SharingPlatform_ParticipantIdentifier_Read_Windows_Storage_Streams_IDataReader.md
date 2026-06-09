# SharingPlatform::ParticipantIdentifier::Read(Windows::Storage::Streams::IDataReader *)

- ea: `0x1800124c0`
- end: `0x1800125f5`
- name: `?Read@ParticipantIdentifier@SharingPlatform@@UEAAJPEAUIDataReader@Streams@Storage@Windows@@@Z`
- size: `309`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, struct Windows::Storage::Streams::IDataReader *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004928`
- `0x1800124c0`
- `0x1800130ec`
- `0x180055b28`
- `0x180056290`
- `0x180062488`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800124e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012524`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800125da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012524`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800125da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001253b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001253b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012577`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SharingPlatform::ParticipantIdentifier::Read(
        RTL_SRWLOCK *this,
        struct Windows::Storage::Streams::IDataReader *a2)
{
  RTL_SRWLOCK *v2; // rdi
  int v5; // eax
  int HString; // ebx
  HSTRING *v8; // r8
  __int64 v9; // rdx
  struct ICDPDeviceInfo **v10; // r8
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HSTRING string; // [rsp+40h] [rbp+20h] BYREF

  v2 = this + 10;
  AcquireSRWLockExclusive(this + 10);
  v5 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IDataReader *, RTL_SRWLOCK *))(*(_QWORD *)a2 + 136LL))(
         a2,
         this + 3);
  HString = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)".\\participantidentifier.cpp",
      (const char *)(unsigned int)v5,
      savedregs);
LABEL_3:
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return (unsigned int)HString;
  }
  string = 0;
  WindowsDeleteString(0);
  string = 0;
  HString = SharingPlatform::Internal::ReadHString(a2, (struct Windows::Storage::Streams::IDataReader *)&string, v8);
  if ( HString < 0 )
  {
    v9 = 87;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)".\\participantidentifier.cpp",
      (const char *)(unsigned int)HString,
      savedregs);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_3;
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&this[9]);
  HString = SharingPlatform::Internal::DeserializeICDPDeviceInfo(
              (SharingPlatform::Internal *)string,
              (HSTRING)&this[9],
              v10);
  if ( HString < 0 )
  {
    v9 = 88;
    goto LABEL_8;
  }
  HString = SharingPlatform::ParticipantIdentifier::InitializeFromCDPDeviceInfo((SharingPlatform::ParticipantIdentifier *)&this[-2]);
  if ( HString < 0 )
  {
    v9 = 91;
    goto LABEL_8;
  }
  WindowsDeleteString(string);
  string = 0;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 0;
}

```

## disassembly

```asm
0x1800124c0  mov     [rsp-18h+arg_8], rbx
0x1800124c5  mov     [rsp-18h+arg_10], rsi
0x1800124ca  push    rbp
0x1800124cb  push    rdi
0x1800124cc  push    r14; int
0x1800124ce  mov     rbp, rsp
0x1800124d1  sub     rsp, 20h
0x1800124d5  lea     rdi, [rcx+50h]
0x1800124d9  mov     rsi, rcx
0x1800124dc  mov     rcx, rdi; SRWLock
0x1800124df  mov     r14, rdx
0x1800124e2  call    cs:__imp_AcquireSRWLockExclusive
0x1800124e8  mov     rax, [r14]
0x1800124eb  lea     rdx, [rsi+18h]
0x1800124ef  mov     rcx, r14
0x1800124f2  mov     rax, [rax+88h]
0x1800124f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800124fe  mov     ebx, eax
0x180012500  test    eax, eax
0x180012502  jns     short loc_180012531
0x180012504  mov     rcx, [rbp+18h]; this
0x180012508  lea     r8, aParticipantide; ".\\participantidentifier.cpp"
0x18001250f  mov     r9d, eax; char *
0x180012512  mov     edx, 53h ; 'S'; void *
0x180012517  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001251c  test    rdi, rdi
0x18001251f  jz      short loc_18001252A
0x180012521  mov     rcx, rdi; SRWLock
0x180012524  call    cs:__imp_ReleaseSRWLockExclusive
0x18001252a  mov     eax, ebx
0x18001252c  jmp     loc_1800125E2
0x180012531  xor     ecx, ecx; string
0x180012533  mov     [rbp+string], 0
0x18001253b  call    cs:__imp_WindowsDeleteString
0x180012541  lea     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataReader *
0x180012545  mov     [rbp+string], 0
0x18001254d  mov     rcx, r14; this
0x180012550  call    ?ReadHString@Internal@SharingPlatform@@YAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ReadHString(Windows::Storage::Streams::IDataReader *,HSTRING__ * *)
0x180012555  mov     ebx, eax
0x180012557  test    eax, eax
0x180012559  jns     short loc_180012587
0x18001255b  mov     edx, 57h ; 'W'; void *
0x180012560  mov     rcx, [rbp+18h]; this
0x180012564  lea     r8, aParticipantide; ".\\participantidentifier.cpp"
0x18001256b  mov     r9d, ebx; char *
0x18001256e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012573  mov     rcx, [rbp+string]; string
0x180012577  call    cs:__imp_WindowsDeleteString
0x18001257d  mov     [rbp+string], 0
0x180012585  jmp     short loc_18001251C
0x180012587  lea     rcx, [rsi+48h]
0x18001258b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180012590  mov     rcx, [rbp+string]; this
0x180012594  lea     rdx, [rsi+48h]; HSTRING
0x180012598  call    ?DeserializeICDPDeviceInfo@Internal@SharingPlatform@@YAJPEAUHSTRING__@@PEAPEAVICDPDeviceInfo@@@Z; SharingPlatform::Internal::DeserializeICDPDeviceInfo(HSTRING__ *,ICDPDeviceInfo * *)
0x18001259d  mov     ebx, eax
0x18001259f  test    eax, eax
0x1800125a1  jns     short loc_1800125AA
0x1800125a3  mov     edx, 58h ; 'X'
0x1800125a8  jmp     short loc_180012560
0x1800125aa  lea     rcx, [rsi-10h]; this
0x1800125ae  call    ?InitializeFromCDPDeviceInfo@ParticipantIdentifier@SharingPlatform@@AEAAJXZ; SharingPlatform::ParticipantIdentifier::InitializeFromCDPDeviceInfo(void)
0x1800125b3  mov     ebx, eax
0x1800125b5  test    eax, eax
0x1800125b7  jns     short loc_1800125C0
0x1800125b9  mov     edx, 5Bh ; '['
0x1800125be  jmp     short loc_180012560
0x1800125c0  mov     rcx, [rbp+string]; string
0x1800125c4  call    cs:__imp_WindowsDeleteString
0x1800125ca  mov     [rbp+string], 0
0x1800125d2  test    rdi, rdi
0x1800125d5  jz      short loc_1800125E0
0x1800125d7  mov     rcx, rdi; SRWLock
0x1800125da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800125e0  xor     eax, eax
0x1800125e2  mov     rbx, [rsp+20h+arg_8]
0x1800125e7  mov     rsi, [rsp+20h+arg_10]
0x1800125ec  add     rsp, 20h
0x1800125f0  pop     r14
0x1800125f2  pop     rdi
0x1800125f3  pop     rbp
0x1800125f4  retn
```
