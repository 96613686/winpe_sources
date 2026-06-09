# ConnectedStorage::Context::GetProviderInfo(XblGameSaveProviderInfo *)

- ea: `0x18005cab4`
- end: `0x18005cbc2`
- name: `?GetProviderInfo@Context@ConnectedStorage@@QEBA_NPEAUXblGameSaveProviderInfo@@@Z`
- size: `270`
- prototype: `bool(ConnectedStorage::Context *__hidden this, struct XblGameSaveProviderInfo *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003373c`

## callees

- `0x18000cb9c`
- `0x18002a714`
- `0x1800313e4`
- `0x1800335fc`
- `0x180033a4c`
- `0x18005cab4`
- `0x180064ba4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cbb1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cae8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005cbb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cb95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005cb95`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall ConnectedStorage::Context::GetProviderInfo(ConnectedStorage::Context *this, HSTRING *a2, char *a3)
{
  HSTRING v5; // rsi
  char *v6; // r8
  char result; // al
  HSTRING v8; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v9[8]; // [rsp+28h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+30h] [rbp-38h] BYREF
  HSTRING v11[2]; // [rsp+40h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-18h]

  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 384),
    a3);
  v5 = (HSTRING)(*((_QWORD *)this + 54) + *((_QWORD *)this + 55));
  LeaveCriticalSection(lpCriticalSection[0]);
  if ( v5 )
  {
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 328),
      v6);
    ConnectedStorage::ContainerIndex::GetMetaData(*((_QWORD *)this + 38), &v8);
    ConnectedStorage::ContainerIndex::GetSyncMetaData(*((_QWORD *)this + 38), v11);
    ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::Context *)((char *)this + 104), a2);
    ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::Context *)((char *)this + 112), a2 + 1);
    ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)&v8, a2 + 2);
    ConnectedStorage::SimpleHStringWrapper::DuplicateTo((ConnectedStorage::SimpleHStringWrapper *)v9, a2 + 3);
    a2[4] = v11[0];
    a2[5] = v5;
    *((_BYTE *)a2 + 48) = ConnectedStorage::ContainerIndex::IsFullyUploaded(*((ConnectedStorage::ContainerIndex **)this
                                                                            + 38));
    *((_BYTE *)a2 + 49) = 1;
    WindowsDeleteString(string);
    string = 0;
    ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(&v8);
    LeaveCriticalSection(lpCriticalSection[0]);
    return 1;
  }
  else
  {
    result = 0;
    *(_OWORD *)a2 = 0;
    *((_OWORD *)a2 + 1) = 0;
    *((_OWORD *)a2 + 2) = 0;
    a2[6] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18005cab4  push    rbp
0x18005cab6  push    rbx
0x18005cab7  push    rsi
0x18005cab8  push    rdi
0x18005cab9  mov     rbp, rsp
0x18005cabc  sub     rsp, 68h
0x18005cac0  mov     rbx, rdx
0x18005cac3  mov     rdi, rcx
0x18005cac6  lea     rdx, [rcx+180h]; struct ConnectedStorage::Mutex *
0x18005cacd  lea     rcx, [rbp+lpCriticalSection]; this
0x18005cad1  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005cad6  mov     rsi, [rdi+1B8h]
0x18005cadd  add     rsi, [rdi+1B0h]
0x18005cae4  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005cae8  call    cs:__imp_LeaveCriticalSection
0x18005caee  test    rsi, rsi
0x18005caf1  jnz     short loc_18005CB0C
0x18005caf3  xorps   xmm0, xmm0
0x18005caf6  xor     eax, eax
0x18005caf8  movups  xmmword ptr [rbx], xmm0
0x18005cafb  movups  xmmword ptr [rbx+10h], xmm0
0x18005caff  movups  xmmword ptr [rbx+20h], xmm0
0x18005cb03  mov     [rbx+30h], rax
0x18005cb07  jmp     loc_18005CBB9
0x18005cb0c  lea     rdx, [rdi+148h]; struct ConnectedStorage::Mutex *
0x18005cb13  lea     rcx, [rbp+lpCriticalSection]; this
0x18005cb17  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005cb1c  nop
0x18005cb1d  lea     rdx, [rbp+var_48]
0x18005cb21  mov     rcx, [rdi+130h]
0x18005cb28  call    ?GetMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetMetaData(void)
0x18005cb2d  nop
0x18005cb2e  lea     rdx, [rbp+var_28]
0x18005cb32  mov     rcx, [rdi+130h]
0x18005cb39  call    ?GetSyncMetaData@ContainerIndex@ConnectedStorage@@QEBA?AUContainerIndexSyncMetaData@2@XZ; ConnectedStorage::ContainerIndex::GetSyncMetaData(void)
0x18005cb3e  nop
0x18005cb3f  lea     rcx, [rdi+68h]; this
0x18005cb43  mov     rdx, rbx; HSTRING *
0x18005cb46  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005cb4b  lea     rdx, [rbx+8]; HSTRING *
0x18005cb4f  lea     rcx, [rdi+70h]; this
0x18005cb53  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005cb58  lea     rdx, [rbx+10h]; HSTRING *
0x18005cb5c  lea     rcx, [rbp+var_48]; this
0x18005cb60  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005cb65  lea     rdx, [rbx+18h]; HSTRING *
0x18005cb69  lea     rcx, [rbp+var_40]; this
0x18005cb6d  call    ?DuplicateTo@SimpleHStringWrapper@ConnectedStorage@@QEBAXPEAPEAUHSTRING__@@@Z; ConnectedStorage::SimpleHStringWrapper::DuplicateTo(HSTRING__ * *)
0x18005cb72  mov     rax, [rbp+var_28]
0x18005cb76  mov     [rbx+20h], rax
0x18005cb7a  mov     [rbx+28h], rsi
0x18005cb7e  mov     rcx, [rdi+130h]; this
0x18005cb85  call    ?IsFullyUploaded@ContainerIndex@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::ContainerIndex::IsFullyUploaded(void)
0x18005cb8a  mov     [rbx+30h], al
0x18005cb8d  mov     byte ptr [rbx+31h], 1
0x18005cb91  mov     rcx, [rbp+string]; string
0x18005cb95  call    cs:__imp_WindowsDeleteString
0x18005cb9b  mov     [rbp+string], 0
0x18005cba3  lea     rcx, [rbp+var_48]; this
0x18005cba7  call    ??1ContainerIndexMetaData@ConnectedStorage@@QEAA@XZ; ConnectedStorage::ContainerIndexMetaData::~ContainerIndexMetaData(void)
0x18005cbac  nop
0x18005cbad  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18005cbb1  call    cs:__imp_LeaveCriticalSection
0x18005cbb7  mov     al, 1
0x18005cbb9  add     rsp, 68h
0x18005cbbd  pop     rdi
0x18005cbbe  pop     rsi
0x18005cbbf  pop     rbx
0x18005cbc0  pop     rbp
0x18005cbc1  retn
```
