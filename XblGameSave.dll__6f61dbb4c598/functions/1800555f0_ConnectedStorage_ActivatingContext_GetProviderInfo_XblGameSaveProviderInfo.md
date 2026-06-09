# ConnectedStorage::ActivatingContext::GetProviderInfo(XblGameSaveProviderInfo *)

- ea: `0x1800555f0`
- end: `0x180055715`
- name: `?GetProviderInfo@ActivatingContext@ConnectedStorage@@QEBA_NPEAUXblGameSaveProviderInfo@@@Z`
- size: `293`
- prototype: `bool(ConnectedStorage::ActivatingContext *__hidden this, struct XblGameSaveProviderInfo *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18003373c`

## callees

- `0x18000cb9c`
- `0x180012ff8`
- `0x18002a714`
- `0x1800313e4`
- `0x1800335fc`
- `0x180033a4c`
- `0x1800555f0`
- `0x1800647c0`
- `0x180064ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800556fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800556fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800556c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800556c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ConnectedStorage::ActivatingContext::GetProviderInfo(
        struct _RTL_CRITICAL_SECTION *this,
        struct XblGameSaveProviderInfo *a2,
        char *a3)
{
  ConnectedStorage::ContainerIndex **p_SpinCount; // rdi
  char v6; // di
  HSTRING v8; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v11; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h]

  ConnectedStorage::Mutex::Lock::Lock((ConnectedStorage::Mutex::Lock *)lpCriticalSection, this + 15, a3);
  p_SpinCount = (ConnectedStorage::ContainerIndex **)&this[14].SpinCount;
  if ( !(unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(&this[14].SpinCount) )
  {
    v6 = 0;
    goto LABEL_6;
  }
  if ( !ConnectedStorage::ContainerIndex::GetTotalBytes(*p_SpinCount) )
  {
    v6 = 0;
LABEL_6:
    *(_OWORD *)a2 = 0;
    *((_OWORD *)a2 + 1) = 0;
    *((_OWORD *)a2 + 2) = 0;
    *((_QWORD *)a2 + 6) = 0;
    goto LABEL_7;
  }
  ConnectedStorage::ContainerIndex::GetMetaData(*p_SpinCount, &v8);
  ConnectedStorage::ContainerIndex::GetSyncMetaData(*p_SpinCount, &v11);
  ConnectedStorage::SimpleHStringWrapper::DuplicateTo(
    (ConnectedStorage::SimpleHStringWrapper *)&this[3].LockCount,
    (HSTRING *)a2);
  ConnectedStorage::SimpleHStringWrapper::DuplicateTo(
    (ConnectedStorage::SimpleHStringWrapper *)&this[3].OwningThread,
    (HSTRING *)a2 + 1);
  ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)&v8, (HSTRING *)a2 + 2);
  ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)v9, (HSTRING *)a2 + 3);
  *((_QWORD *)a2 + 4) = v11;
  *((_QWORD *)a2 + 5) = ConnectedStorage::ContainerIndex::GetTotalBytes(*p_SpinCount);
  *((_BYTE *)a2 + 48) = ConnectedStorage::ContainerIndex::IsFullyUploaded(*p_SpinCount);
  v6 = 1;
  *((_BYTE *)a2 + 49) = 1;
  WindowsDeleteString(string);
  string = 0;
  ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(&v8);
LABEL_7:
  LeaveCriticalSection(lpCriticalSection[0]);
  return v6;
}

```

## disassembly

```asm
0x1800555f0  mov     [rsp+arg_0], rbx
0x1800555f5  mov     [rsp+arg_8], rsi
0x1800555fa  push    rdi
0x1800555fb  sub     rsp, 60h
0x1800555ff  mov     rbx, rdx
0x180055602  mov     rsi, rcx
0x180055605  lea     rdx, [rcx+258h]; struct ConnectedStorage::Mutex *
0x18005560c  lea     rcx, [rsp+68h+lpCriticalSection]; this
0x180055611  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180055616  nop
0x180055617  lea     rdi, [rsi+250h]
0x18005561e  mov     rcx, rdi
0x180055621  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x180055626  test    al, al
0x180055628  jz      loc_1800556E0
0x18005562e  mov     rcx, [rdi]; this
0x180055631  call    ?GetTotalBytes@ContainerIndex@ConnectedStorage@@QEBA_KXZ; ConnectedStorage::ContainerIndex::GetTotalBytes(void)
0x180055636  test    rax, rax
0x180055639  jnz     short loc_180055642
0x18005563b  xor     edi, edi
0x18005563d  jmp     loc_1800556E3
0x180055642  lea     rdx, [rsp+68h+var_48]
0x180055647  mov     rcx, [rdi]
0x18005564a  call    ?GetMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetMetaData(void)
0x18005564f  nop
0x180055650  lea     rdx, [rsp+68h+var_28]
0x180055655  mov     rcx, [rdi]
0x180055658  call    ?GetSyncMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexSyncMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetSyncMetaData(void)
0x18005565d  nop
0x18005565e  lea     rcx, [rsi+80h]; this
0x180055665  mov     rdx, rbx; HSTRING *
0x180055668  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005566d  lea     rdx, [rbx+8]; HSTRING *
0x180055671  lea     rcx, [rsi+88h]; this
0x180055678  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005567d  lea     rdx, [rbx+10h]; HSTRING *
0x180055681  lea     rcx, [rsp+68h+var_48]; this
0x180055686  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005568b  lea     rdx, [rbx+18h]; HSTRING *
0x18005568f  lea     rcx, [rsp+68h+var_40]; this
0x180055694  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x180055699  mov     rax, [rsp+68h+var_28]
0x18005569e  mov     [rbx+20h], rax
0x1800556a2  mov     rcx, [rdi]; this
0x1800556a5  call    ?GetTotalBytes@ContainerIndex@ConnectedStorage@@QEBA_KXZ; ConnectedStorage::ContainerIndex::GetTotalBytes(void)
0x1800556aa  mov     [rbx+28h], rax
0x1800556ae  mov     rcx, [rdi]; this
0x1800556b1  call    ?IsFullyUploaded@ContainerIndex@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::ContainerIndex::IsFullyUploaded(void)
0x1800556b6  mov     [rbx+30h], al
0x1800556b9  mov     dil, 1
0x1800556bc  mov     [rbx+31h], dil
0x1800556c0  mov     rcx, [rsp+68h+string]; string
0x1800556c5  call    cs:__imp_WindowsDeleteString
0x1800556cb  mov     [rsp+68h+string], 0
0x1800556d4  lea     rcx, [rsp+68h+var_48]; this
0x1800556d9  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x1800556de  jmp     short loc_1800556F7
0x1800556e0  xor     dil, dil
0x1800556e3  xorps   xmm0, xmm0
0x1800556e6  xor     eax, eax
0x1800556e8  movups  xmmword ptr [rbx], xmm0
0x1800556eb  movups  xmmword ptr [rbx+10h], xmm0
0x1800556ef  movups  xmmword ptr [rbx+20h], xmm0
0x1800556f3  mov     [rbx+30h], rax
0x1800556f7  mov     rcx, [rsp+68h+lpCriticalSection]; lpCriticalSection
0x1800556fc  call    cs:__imp_LeaveCriticalSection
0x180055702  mov     al, dil
0x180055705  mov     rbx, [rsp+68h+arg_0]
0x18005570a  mov     rsi, [rsp+68h+arg_8]
0x18005570f  add     rsp, 60h
0x180055713  pop     rdi
0x180055714  retn
```
