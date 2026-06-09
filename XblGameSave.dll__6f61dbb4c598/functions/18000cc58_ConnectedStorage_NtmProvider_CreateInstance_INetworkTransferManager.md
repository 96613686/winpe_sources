# ConnectedStorage::NtmProvider::CreateInstance(INetworkTransferManager * *)

- ea: `0x18000cc58`
- end: `0x18000cd16`
- name: `?CreateInstance@NtmProvider@ConnectedStorage@@QEAAXPEAPEAUINetworkTransferManager@@@Z`
- size: `190`
- prototype: `void __fastcall(ConnectedStorage::NtmProvider *__hidden this, struct INetworkTransferManager **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180066db4`

## callees

- `0x180004a88`
- `0x18000a040`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000cc58`
- `0x18000cd1c`
- `0x18000cd40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cc9f`
- `ext-ms-win-gaming-xblgamesave-l1-1-0!XblGameSave_NTMSCreateInstance` at `0x18000ccc4`
- `ext-ms-win-gaming-xblgamesave-l1-1-0!XblGameSave_NTMSCreateInstance` at `0x18000ccc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectedStorage::NtmProvider::CreateInstance(
        ConnectedStorage::NtmProvider *this,
        struct INetworkTransferManager **a2)
{
  char *v4; // r8
  bool v5; // bl
  int v6; // eax
  const unsigned __int16 *v7; // r8
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF
  struct INetworkTransferManager *v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = 0;
  if ( (unsigned __int8)IsXblGameSave_NTMSCreateInstancePresent() )
  {
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      &ConnectedStorage::NtmProvider::s_mutex,
      v4);
    v5 = ConnectedStorage::NtmProvider::s_refCount != 0;
    LeaveCriticalSection(lpCriticalSection[0]);
    if ( !v5 )
    {
      v6 = ConnectedStorage::NtmProvider::Start(this);
      if ( v6 < 0 )
LABEL_7:
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v6, (int)L"hr", v7);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
    v6 = XblGameSave_NTMSCreateInstance(&v9);
    if ( !v9 )
    {
      if ( v6 >= 0 )
        v6 = -2147024882;
      goto LABEL_7;
    }
    Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(&v9);
    *a2 = v9;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
}

```

## disassembly

```asm
0x18000cc58  mov     [rsp+arg_0], rbx
0x18000cc5d  mov     [rsp+arg_8], rsi
0x18000cc62  push    rdi
0x18000cc63  sub     rsp, 30h
0x18000cc67  mov     rdi, rdx
0x18000cc6a  mov     rsi, rcx
0x18000cc6d  mov     [rsp+38h+arg_10], 0
0x18000cc76  call    IsXblGameSave_NTMSCreateInstancePresent
0x18000cc7b  test    al, al
0x18000cc7d  jz      short loc_18000CCFC
0x18000cc7f  lea     rdx, ?s_mutex@NtmProvider@ConnectedStorage@@0VMutex@2@A; struct ConnectedStorage::Mutex *
0x18000cc86  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x18000cc8b  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18000cc90  cmp     cs:?s_refCount@NtmProvider@ConnectedStorage@@0IA, 0; uint ConnectedStorage::NtmProvider::s_refCount
0x18000cc97  setnbe  bl
0x18000cc9a  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x18000cc9f  call    cs:__imp_LeaveCriticalSection
0x18000cca5  test    bl, bl
0x18000cca7  jnz     short loc_18000CCB5
0x18000cca9  mov     rcx, rsi; this
0x18000ccac  call    ?Start@NtmProvider@ConnectedStorage@@QEAAJXZ; ConnectedStorage::NtmProvider::Start(void)
0x18000ccb1  test    eax, eax
0x18000ccb3  js      short loc_18000CCDB
0x18000ccb5  lea     rcx, [rsp+38h+arg_10]
0x18000ccba  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ccbf  lea     rcx, [rsp+38h+arg_10]
0x18000ccc4  call    cs:__imp_XblGameSave_NTMSCreateInstance
0x18000ccca  cmp     [rsp+38h+arg_10], 0
0x18000ccd0  jnz     short loc_18000CCEA
0x18000ccd2  test    eax, eax
0x18000ccd4  js      short loc_18000CCDB
0x18000ccd6  mov     eax, 8007000Eh
0x18000ccdb  lea     rdx, aHr; "hr"
0x18000cce2  mov     ecx, eax; this
0x18000cce4  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18000ccea  lea     rcx, [rsp+38h+arg_10]
0x18000ccef  call    ?InternalAddRef@?$ComPtr@VAtomDownloadStream@ConnectedStorage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ConnectedStorage::AtomDownloadStream>::InternalAddRef(void)
0x18000ccf4  mov     rax, [rsp+38h+arg_10]
0x18000ccf9  mov     [rdi], rax
0x18000ccfc  lea     rcx, [rsp+38h+arg_10]
0x18000cd01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000cd06  mov     rbx, [rsp+38h+arg_0]
0x18000cd0b  mov     rsi, [rsp+38h+arg_8]
0x18000cd10  add     rsp, 30h
0x18000cd14  pop     rdi
0x18000cd15  retn
```
