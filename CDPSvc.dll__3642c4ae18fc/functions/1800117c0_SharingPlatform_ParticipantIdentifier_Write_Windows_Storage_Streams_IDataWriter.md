# SharingPlatform::ParticipantIdentifier::Write(Windows::Storage::Streams::IDataWriter *)

- ea: `0x1800117c0`
- end: `0x1800118e0`
- name: `?Write@ParticipantIdentifier@SharingPlatform@@UEBAJPEAUIDataWriter@Streams@Storage@Windows@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(SharingPlatform::ParticipantIdentifier *this, struct Windows::Storage::Streams::IDataWriter *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800117c0`
- `0x1800130ec`
- `0x1800563b0`
- `0x1800564f4`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800117e2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800117e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001182e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001182e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800118c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011845`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011882`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800118af`

## pseudocode

```c
__int64 __fastcall SharingPlatform::ParticipantIdentifier::Write(
        SharingPlatform::ParticipantIdentifier *this,
        struct Windows::Storage::Streams::IDataWriter *a2)
{
  RTL_SRWLOCK *v2; // rbx
  __int64 (__fastcall *v5)(struct Windows::Storage::Streams::IDataWriter *, __int128 *); // rax
  int v6; // eax
  int v7; // edi
  SharingPlatform::Internal *v9; // rcx
  HSTRING *v10; // r8
  HSTRING v11; // r8
  __int64 v12; // rdx
  __int128 v13; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HSTRING string; // [rsp+50h] [rbp+20h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 80);
  AcquireSRWLockShared((PSRWLOCK)this + 10);
  v5 = *(__int64 (__fastcall **)(struct Windows::Storage::Streams::IDataWriter *, __int128 *))(*(_QWORD *)a2 + 128LL);
  v13 = *(_OWORD *)((char *)this + 24);
  v6 = v5(a2, &v13);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)".\\participantidentifier.cpp",
      (const char *)(unsigned int)v6,
      v13);
LABEL_3:
    if ( v2 )
      ReleaseSRWLockShared(v2);
    return (unsigned int)v7;
  }
  string = 0;
  WindowsDeleteString(0);
  v9 = (SharingPlatform::Internal *)*((_QWORD *)this + 9);
  string = 0;
  v7 = SharingPlatform::Internal::SerializeICDPDeviceInfo(v9, (struct ICDPDeviceInfo *)&string, v10);
  if ( v7 < 0 )
  {
    v12 = 72;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)".\\participantidentifier.cpp",
      (const char *)(unsigned int)v7,
      v13);
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_3;
  }
  v7 = SharingPlatform::Internal::WriteHString(a2, (struct Windows::Storage::Streams::IDataWriter *)string, v11);
  if ( v7 < 0 )
  {
    v12 = 73;
    goto LABEL_8;
  }
  WindowsDeleteString(string);
  string = 0;
  if ( v2 )
    ReleaseSRWLockShared(v2);
  return 0;
}

```

## disassembly

```asm
0x1800117c0  mov     [rsp-18h+arg_8], rbx
0x1800117c5  mov     [rsp-18h+arg_10], rsi
0x1800117ca  push    rbp
0x1800117cb  push    rdi
0x1800117cc  push    r14
0x1800117ce  mov     rbp, rsp
0x1800117d1  sub     rsp, 30h
0x1800117d5  lea     rbx, [rcx+50h]
0x1800117d9  mov     r14, rcx
0x1800117dc  mov     rcx, rbx; SRWLock
0x1800117df  mov     rsi, rdx
0x1800117e2  call    cs:__imp_AcquireSRWLockShared
0x1800117e8  mov     rax, [rsi]
0x1800117eb  lea     rdx, [rbp+var_10]
0x1800117ef  movups  xmm0, xmmword ptr [r14+18h]
0x1800117f4  mov     rcx, rsi
0x1800117f7  mov     rax, [rax+80h]
0x1800117fe  movdqu  [rbp+var_10], xmm0
0x180011803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011808  mov     edi, eax
0x18001180a  test    eax, eax
0x18001180c  jns     short loc_18001183B
0x18001180e  mov     rcx, [rbp+18h]; this
0x180011812  lea     r8, aParticipantide; ".\\participantidentifier.cpp"
0x180011819  mov     r9d, eax; char *
0x18001181c  mov     edx, 44h ; 'D'; void *
0x180011821  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011826  test    rbx, rbx
0x180011829  jz      short loc_180011834
0x18001182b  mov     rcx, rbx; SRWLock
0x18001182e  call    cs:__imp_ReleaseSRWLockShared
0x180011834  mov     eax, edi
0x180011836  jmp     loc_1800118CD
0x18001183b  xor     ecx, ecx; string
0x18001183d  mov     [rbp+string], 0
0x180011845  call    cs:__imp_WindowsDeleteString
0x18001184b  mov     rcx, [r14+48h]; this
0x18001184f  lea     rdx, [rbp+string]; struct ICDPDeviceInfo *
0x180011853  mov     [rbp+string], 0
0x18001185b  call    ?SerializeICDPDeviceInfo@Internal@SharingPlatform@@YAJPEAVICDPDeviceInfo@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::SerializeICDPDeviceInfo(ICDPDeviceInfo *,HSTRING__ * *)
0x180011860  mov     edi, eax
0x180011862  test    eax, eax
0x180011864  jns     short loc_180011892
0x180011866  mov     edx, 48h ; 'H'; void *
0x18001186b  mov     rcx, [rbp+18h]; this
0x18001186f  lea     r8, aParticipantide; ".\\participantidentifier.cpp"
0x180011876  mov     r9d, edi; char *
0x180011879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001187e  mov     rcx, [rbp+string]; string
0x180011882  call    cs:__imp_WindowsDeleteString
0x180011888  mov     [rbp+string], 0
0x180011890  jmp     short loc_180011826
0x180011892  mov     rdx, [rbp+string]; struct Windows::Storage::Streams::IDataWriter *
0x180011896  mov     rcx, rsi; this
0x180011899  call    ?WriteHString@Internal@SharingPlatform@@YAJPEAUIDataWriter@Streams@Storage@Windows@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::WriteHString(Windows::Storage::Streams::IDataWriter *,HSTRING__ *)
0x18001189e  mov     edi, eax
0x1800118a0  test    eax, eax
0x1800118a2  jns     short loc_1800118AB
0x1800118a4  mov     edx, 49h ; 'I'
0x1800118a9  jmp     short loc_18001186B
0x1800118ab  mov     rcx, [rbp+string]; string
0x1800118af  call    cs:__imp_WindowsDeleteString
0x1800118b5  mov     [rbp+string], 0
0x1800118bd  test    rbx, rbx
0x1800118c0  jz      short loc_1800118CB
0x1800118c2  mov     rcx, rbx; SRWLock
0x1800118c5  call    cs:__imp_ReleaseSRWLockShared
0x1800118cb  xor     eax, eax
0x1800118cd  mov     rbx, [rsp+30h+arg_8]
0x1800118d2  mov     rsi, [rsp+30h+arg_10]
0x1800118d7  add     rsp, 30h
0x1800118db  pop     r14
0x1800118dd  pop     rdi
0x1800118de  pop     rbp
0x1800118df  retn
```
