# ConnectedStorage::ContainerIndex::GetMatchingEntries(ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x180064598`
- end: `0x1800647b7`
- name: `?GetMatchingEntries@ContainerIndex@ConnectedStorage@@QEBA?AV?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@AEBVSimpleHStringWrapper@2@@Z`
- size: `543`
- prototype: `__int64 __fastcall(ConnectedStorage::ContainerIndex *this)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005d9e8`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180011b94`
- `0x18005b004`
- `0x1800640ac`
- `0x1800644ec`
- `0x180064598`
- `0x180065d34`
- `0x180065ffc`
- `0x1800663a0`
- `0x180077d60`
- `0x180077e08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006476f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006476f`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800646e3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800646e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800645ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringLen` at `0x1800645ff`

## string_xrefs

- `0x1800647a8`: `CoCreateGuid(&guid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HSTRING __fastcall ConnectedStorage::ContainerIndex::GetMatchingEntries(
        ConnectedStorage::ContainerIndex *this,
        HSTRING a2,
        char *a3)
{
  const unsigned __int16 *v6; // r8
  _QWORD *v7; // rbx
  _QWORD *v8; // rdi
  __int64 v9; // r15
  HSTRING *v10; // rax
  __int64 v11; // rax
  __int64 *v12; // rax
  __int64 v13; // rdi
  __int64 v14; // r15
  HSTRING *v15; // rax
  HRESULT v16; // eax
  const unsigned __int16 *v17; // r8
  HSTRING newString; // [rsp+30h] [rbp-50h] BYREF
  int v20; // [rsp+38h] [rbp-48h]
  HSTRING v21[2]; // [rsp+40h] [rbp-40h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+50h] [rbp-30h] BYREF
  GUID pguid; // [rsp+60h] [rbp-20h] BYREF

  v21[1] = a2;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 64),
    a3);
  *(_QWORD *)a2 = 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  v20 = 1;
  if ( WindowsGetStringLen(*(HSTRING *)a3) > 0xFF )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x80070057LL,
      (int)L"ContainerIndex::GetMatchingEntries: Invalid prefix string",
      v6);
  v7 = (_QWORD *)*((_QWORD *)this + 20);
  v8 = (_QWORD *)*((_QWORD *)this + 21);
  while ( v7 != v8 )
  {
    v9 = *v7;
    if ( (unsigned int)(*(_DWORD *)(*v7 + 28LL) - 3) > 1 )
    {
      v10 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, (HSTRING *)a3);
      if ( (unsigned __int8)ConnectedStorage::ContainerIndexEntry::MatchesPrefix(v9, v10) )
      {
        v11 = ConnectedStorage::ContainerIndexEntry::Clone(*v7, v21);
        std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::push_back(a2, v11);
        std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(v21);
      }
    }
    ++v7;
  }
  v12 = (__int64 *)*((_QWORD *)this + 23);
  if ( v12 )
  {
    v13 = *v12;
    v14 = v12[1];
    while ( v13 != v14 )
    {
      if ( ((*(_DWORD *)(v13 + 32) - 2) & 0xFFFFFFFD) == 0 )
      {
        v15 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(v21, (HSTRING *)a3);
        if ( (unsigned __int8)ConnectedStorage::SimpleHStringWrapper::StartsWith(v13, v15) )
        {
          if ( !ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(
                  this,
                  (const struct ConnectedStorage::SimpleHStringWrapper *)v13,
                  0) )
          {
            pguid = 0;
            v16 = CoCreateGuid(&pguid);
            if ( v16 < 0 )
              ConnectedStorage::ReportErrorAndThrow(
                (ConnectedStorage *)(unsigned int)v16,
                (int)L"CoCreateGuid(&guid)",
                v17);
            ConnectedStorage::ContainerIndexEntry::Create(
              (_lambda_249230bd792972bce8c42ec595a35649_ *)&newString,
              (__int64)&pguid);
            ConnectedStorage::ContainerIndexEntry::UpdateAfterSuccessfulDownload(
              (ConnectedStorage::ContainerIndexEntry *)newString,
              *((_BYTE *)newString + 24) + 1 + ((unsigned int)*((unsigned __int8 *)newString + 24) + 1) / 0xFF,
              *(_QWORD *)(v13 + 40),
              (const struct ConnectedStorage::SimpleHStringWrapper *)(v13 + 24),
              (struct _FILETIME *)(v13 + 16));
            std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::push_back(a2, &newString);
            std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(&newString);
          }
        }
      }
      v13 += 48;
    }
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  return a2;
}

```

## disassembly

```asm
0x180064598  push    rbp
0x18006459a  push    rbx
0x18006459b  push    rsi
0x18006459c  push    rdi
0x18006459d  push    r12
0x18006459f  push    r14
0x1800645a1  push    r15
0x1800645a3  mov     rbp, rsp
0x1800645a6  sub     rsp, 80h
0x1800645ad  mov     rax, cs:__security_cookie
0x1800645b4  xor     rax, rsp
0x1800645b7  mov     [rbp+var_10], rax
0x1800645bb  mov     r12, r8
0x1800645be  mov     rsi, rdx
0x1800645c1  mov     r14, rcx
0x1800645c4  mov     [rbp+var_38], rdx
0x1800645c8  mov     [rbp+var_48], 0
0x1800645cf  lea     rdx, [rcx+40h]; struct ConnectedStorage::Mutex *
0x1800645d3  lea     rcx, [rbp+lpCriticalSection]; this
0x1800645d7  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800645dc  nop
0x1800645dd  mov     qword ptr [rsi], 0
0x1800645e4  mov     qword ptr [rsi+8], 0
0x1800645ec  mov     qword ptr [rsi+10h], 0
0x1800645f4  mov     [rbp+var_48], 1
0x1800645fb  mov     rcx, [r12]; string
0x1800645ff  call    cs:__imp_WindowsGetStringLen
0x180064605  cmp     eax, 0FFh
0x18006460a  ja      loc_180064796
0x180064610  mov     rbx, [r14+0A0h]
0x180064617  mov     rdi, [r14+0A8h]
0x18006461e  cmp     rbx, rdi
0x180064621  jz      short loc_180064675
0x180064623  mov     r15, [rbx]
0x180064626  mov     eax, [r15+1Ch]
0x18006462a  sub     eax, 3
0x18006462d  cmp     eax, 1
0x180064630  jbe     short loc_18006466F
0x180064632  mov     rdx, r12; struct ConnectedStorage::SimpleHStringWrapper *
0x180064635  lea     rcx, [rbp+newString]; newString
0x180064639  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18006463e  mov     rdx, rax
0x180064641  mov     rcx, r15
0x180064644  call    ?MatchesPrefix@ContainerIndexEntry@ConnectedStorage@@QEBA_NVSimpleHStringWrapper@2@@Z; ConnectedStorage::ContainerIndexEntry::MatchesPrefix(ConnectedStorage::SimpleHStringWrapper)
0x180064649  test    al, al
0x18006464b  jz      short loc_18006466F
0x18006464d  lea     rdx, [rbp+var_40]
0x180064651  mov     rcx, [rbx]
0x180064654  call    ?Clone@ContainerIndexEntry@ConnectedStorage@@QEBA?AV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@XZ; ConnectedStorage::ContainerIndexEntry::Clone(void)
0x180064659  nop
0x18006465a  mov     rdx, rax
0x18006465d  mov     rcx, rsi
0x180064660  call    ?push_back@?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@2@@Z; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::push_back(std::unique_ptr<ConnectedStorage::ContainerIndexEntry> &&)
0x180064665  nop
0x180064666  lea     rcx, [rbp+var_40]
0x18006466a  call    ??1?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(void)
0x18006466f  add     rbx, 8
0x180064673  jmp     short loc_18006461E
0x180064675  mov     rax, [r14+0B8h]
0x18006467c  test    rax, rax
0x18006467f  jz      loc_18006476B
0x180064685  mov     rdi, [rax]
0x180064688  mov     r15, [rax+8]
0x18006468c  jmp     loc_180064762
0x180064691  mov     eax, [rdi+20h]
0x180064694  sub     eax, 2
0x180064697  test    eax, 0FFFFFFFDh
0x18006469c  jnz     loc_18006475E
0x1800646a2  mov     rdx, r12; struct ConnectedStorage::SimpleHStringWrapper *
0x1800646a5  lea     rcx, [rbp+var_40]; newString
0x1800646a9  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x1800646ae  mov     rdx, rax
0x1800646b1  mov     rcx, rdi
0x1800646b4  call    ?StartsWith@SimpleHStringWrapper@ConnectedStorage@@QEBA_NV12@@Z; ConnectedStorage::SimpleHStringWrapper::StartsWith(ConnectedStorage::SimpleHStringWrapper)
0x1800646b9  test    al, al
0x1800646bb  jz      loc_18006475E
0x1800646c1  xor     r8d, r8d; bool
0x1800646c4  mov     rdx, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x1800646c7  mov     rcx, r14; this
0x1800646ca  call    ?GetExistingContainerIndexEntry@ContainerIndex@ConnectedStorage@@QEBAPEAVContainerIndexEntry@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(ConnectedStorage::SimpleHStringWrapper const &,bool)
0x1800646cf  test    rax, rax
0x1800646d2  jnz     loc_18006475E
0x1800646d8  xorps   xmm0, xmm0
0x1800646db  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800646df  lea     rcx, [rbp+pguid]; pguid
0x1800646e3  call    cs:__imp_CoCreateGuid
0x1800646e9  test    eax, eax
0x1800646eb  js      loc_1800647A8
0x1800646f1  lea     r8, [rdi+8]
0x1800646f5  lea     rax, [rbp+pguid]
0x1800646f9  mov     [rsp+80h+var_60], rax; __int64
0x1800646fe  lea     r9, [rdi+18h]
0x180064702  mov     rdx, rdi
0x180064705  lea     rcx, [rbp+newString]; this
0x180064709  call    ?Create@ContainerIndexEntry@ConnectedStorage@@SA?AV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@AEBVSimpleHStringWrapper@2@00AEBU_GUID@@W4State@12@@Z; ConnectedStorage::ContainerIndexEntry::Create(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_GUID const &,ConnectedStorage::ContainerIndexEntry::State)
0x18006470e  nop
0x18006470f  lea     r8, [rdi+10h]
0x180064713  mov     rcx, [rbp+newString]; this
0x180064717  movzx   r10d, byte ptr [rcx+18h]
0x18006471c  inc     r10d
0x18006471f  mov     eax, 80808081h
0x180064724  mul     r10d
0x180064727  shr     edx, 7
0x18006472a  imul    eax, edx, 0FFh
0x180064730  sub     r10d, eax
0x180064733  mov     [rsp+80h+var_60], r8; struct _FILETIME *
0x180064738  lea     r9, [rdi+18h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18006473c  mov     r8, [rdi+28h]; unsigned __int64
0x180064740  mov     dl, r10b; unsigned __int8
0x180064743  call    ?UpdateAfterSuccessfulDownload@ContainerIndexEntry@ConnectedStorage@@QEAAXE_KAEBVSimpleHStringWrapper@2@AEAU_FILETIME@@@Z; ConnectedStorage::ContainerIndexEntry::UpdateAfterSuccessfulDownload(uchar,unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &,_FILETIME &)
0x180064748  lea     rdx, [rbp+newString]
0x18006474c  mov     rcx, rsi
0x18006474f  call    ?push_back@?$vector@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@V?$allocator@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@2@@Z; std::vector<std::unique_ptr<ConnectedStorage::ContainerIndexEntry>>::push_back(std::unique_ptr<ConnectedStorage::ContainerIndexEntry> &&)
0x180064754  nop
0x180064755  lea     rcx, [rbp+newString]
0x180064759  call    ??1?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(void)
0x18006475e  add     rdi, 30h ; '0'
0x180064762  cmp     rdi, r15
0x180064765  jnz     loc_180064691
0x18006476b  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x18006476f  call    cs:__imp_LeaveCriticalSection
0x180064775  mov     rax, rsi
0x180064778  mov     rcx, [rbp+var_10]
0x18006477c  xor     rcx, rsp; StackCookie
0x18006477f  call    __security_check_cookie
0x180064784  add     rsp, 80h
0x18006478b  pop     r15
0x18006478d  pop     r14
0x18006478f  pop     r12
0x180064791  pop     rdi
0x180064792  pop     rsi
0x180064793  pop     rbx
0x180064794  pop     rbp
0x180064795  retn
0x180064796  lea     rdx, aContainerindex_4; "ContainerIndex::GetMatchingEntries: Inv"...
0x18006479d  mov     ecx, 80070057h; this
0x1800647a2  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800647a8  lea     rdx, aCocreateguidGu; "CoCreateGuid(&guid)"
0x1800647af  mov     ecx, eax; this
0x1800647b1  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
