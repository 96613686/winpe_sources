# ConnectedStorage::ActivatingContext::LoadLocalContainerIndex(void)

- ea: `0x1800558c0`
- end: `0x180055a26`
- name: `?LoadLocalContainerIndex@ActivatingContext@ConnectedStorage@@AEAAXXZ`
- size: `358`
- prototype: `void __fastcall(ConnectedStorage::ActivatingContext *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180056fd0`
- `0x180057130`

## callees

- `0x180003c70`
- `0x18000cb9c`
- `0x180011b94`
- `0x180012ed8`
- `0x180014f34`
- `0x18001c090`
- `0x18002ee50`
- `0x180031360`
- `0x180051540`
- `0x1800558c0`
- `0x180064c00`
- `0x180065cdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055984`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180055984`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559c6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800559f2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800559a0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800559a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ConnectedStorage::ActivatingContext::LoadLocalContainerIndex(ConnectedStorage::ActivatingContext *this)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  char *v4; // r8
  __int64 v5; // rbx
  char *v6; // r8
  __int64 v7; // rbx
  char *v8; // r8
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[4]; // [rsp+28h] [rbp-30h] BYREF

  *((_QWORD *)this + 98) = "ConnectedStorage::ActivatingContext::LoadLocalContainerIndex";
  ConnectedStorage::GetStorageServiceTestFlags(this);
  std::operator+<unsigned short>(lpCriticalSection, (char *)this + 560, L"\\containers.index");
  v2 = (__int64 *)ConnectedStorage::ContainerIndex::Load((_lambda_249230bd792972bce8c42ec595a35649_ *)&string);
  std::unique_ptr<ConnectedStorage::ContainerIndex>::operator=<std::default_delete<ConnectedStorage::ContainerIndex>,0>(
    (__int64 *)this + 74,
    v2);
  std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(&string);
  std::wstring::_Tidy_deallocate(lpCriticalSection);
  v3 = *((_QWORD *)this + 74);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(v3 + 64),
    v4);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, (HSTRING *)(v3 + 144));
  LeaveCriticalSection(lpCriticalSection[0]);
  ConnectedStorage::SimpleHStringWrapper::operator=((HSTRING *)this + 37, &string);
  WindowsDeleteString(string);
  v5 = *((_QWORD *)this + 74);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(v5 + 64),
    v6);
  LOBYTE(v5) = (*(_DWORD *)(v5 + 136) & 4) != 0;
  LeaveCriticalSection(lpCriticalSection[0]);
  *((_BYTE *)this + 724) = v5;
  v7 = *((_QWORD *)this + 74);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(v7 + 64),
    v8);
  LOBYTE(v7) = (*(_DWORD *)(v7 + 136) & 8) != 0;
  LeaveCriticalSection(lpCriticalSection[0]);
  *((_BYTE *)this + 725) = v7;
  if ( *((_BYTE *)this + 723) )
    ConnectedStorage::ContainerIndex::SetHasUnresolvedConflicts(*((ConnectedStorage::ContainerIndex **)this + 74), 0);
}

```

## disassembly

```asm
0x1800558c0  push    rbp
0x1800558c2  push    rbx
0x1800558c3  push    rsi
0x1800558c4  push    rdi
0x1800558c5  mov     rbp, rsp
0x1800558c8  sub     rsp, 58h
0x1800558cc  mov     rax, cs:__security_cookie
0x1800558d3  xor     rax, rsp
0x1800558d6  mov     [rbp+var_10], rax
0x1800558da  mov     rdi, rcx
0x1800558dd  lea     rax, aConnectedstora_10; "ConnectedStorage::ActivatingContext::Lo"...
0x1800558e4  mov     [rcx+310h], rax
0x1800558eb  call    ?GetStorageServiceTestFlags@ConnectedStorage@@YAKXZ; ConnectedStorage::GetStorageServiceTestFlags(void)
0x1800558f0  cmp     byte ptr [rdi+208h], 0
0x1800558f7  jnz     short loc_180055900
0x1800558f9  mov     ebx, 1
0x1800558fe  jmp     short loc_18005590A
0x180055900  xor     ebx, ebx
0x180055902  lea     ecx, [rbx+2]
0x180055905  test    cl, al
0x180055907  cmovnz  ebx, ecx
0x18005590a  lea     rdx, [rdi+230h]
0x180055911  lea     r8, aContainersInde; "\\containers.index"
0x180055918  lea     rcx, [rbp+lpCriticalSection]
0x18005591c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180055921  nop
0x180055922  lea     rdx, [rdi+210h]
0x180055929  mov     r9d, ebx
0x18005592c  lea     r8, [rbp+lpCriticalSection]
0x180055930  lea     rcx, [rbp+string]; this
0x180055934  call    ?Load@ContainerIndex@ConnectedStorage@@SA?AV?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@0W4ContainerSyncTrackingFlag@2@@Z; ConnectedStorage::ContainerIndex::Load(std::wstring const &,std::wstring const &,ConnectedStorage::ContainerSyncTrackingFlag)
0x180055939  lea     rsi, [rdi+250h]
0x180055940  mov     rdx, rax
0x180055943  mov     rcx, rsi
0x180055946  call    ??$?4U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@$0A@@?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<ConnectedStorage::ContainerIndex>::operator=<std::default_delete<ConnectedStorage::ContainerIndex>,0>(std::unique_ptr<ConnectedStorage::ContainerIndex> &&)
0x18005594b  lea     rcx, [rbp+string]
0x18005594f  call    ??1?$unique_ptr@VContainerIndex@ConnectedStorage@@U?$default_delete@VContainerIndex@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndex>::~unique_ptr<ConnectedStorage::ContainerIndex>(void)
0x180055954  nop
0x180055955  lea     rcx, [rbp+lpCriticalSection]
0x180055959  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005595e  mov     rbx, [rsi]
0x180055961  lea     rdx, [rbx+40h]; struct ConnectedStorage::Mutex *
0x180055965  lea     rcx, [rbp+lpCriticalSection]; this
0x180055969  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005596e  nop
0x18005596f  lea     rdx, [rbx+90h]; struct ConnectedStorage::SimpleHStringWrapper *
0x180055976  lea     rcx, [rbp+string]; newString
0x18005597a  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x18005597f  nop
0x180055980  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180055984  call    cs:__imp_LeaveCriticalSection
0x18005598a  nop
0x18005598b  lea     rcx, [rdi+128h]; newString
0x180055992  lea     rdx, [rbp+string]
0x180055996  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18005599b  nop
0x18005599c  mov     rcx, [rbp+string]; string
0x1800559a0  call    cs:__imp_WindowsDeleteString
0x1800559a6  mov     rbx, [rsi]
0x1800559a9  lea     rdx, [rbx+40h]; struct ConnectedStorage::Mutex *
0x1800559ad  lea     rcx, [rbp+lpCriticalSection]; this
0x1800559b1  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800559b6  mov     ebx, [rbx+88h]
0x1800559bc  shr     ebx, 2
0x1800559bf  and     bl, 1
0x1800559c2  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800559c6  call    cs:__imp_LeaveCriticalSection
0x1800559cc  mov     [rdi+2D4h], bl
0x1800559d2  mov     rbx, [rsi]
0x1800559d5  lea     rdx, [rbx+40h]; struct ConnectedStorage::Mutex *
0x1800559d9  lea     rcx, [rbp+lpCriticalSection]; this
0x1800559dd  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x1800559e2  mov     ebx, [rbx+88h]
0x1800559e8  shr     ebx, 3
0x1800559eb  and     bl, 1
0x1800559ee  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x1800559f2  call    cs:__imp_LeaveCriticalSection
0x1800559f8  mov     [rdi+2D5h], bl
0x1800559fe  cmp     byte ptr [rdi+2D3h], 0
0x180055a05  jz      short loc_180055A11
0x180055a07  xor     edx, edx; bool
0x180055a09  mov     rcx, [rsi]; this
0x180055a0c  call    ?SetHasUnresolvedConflicts@ContainerIndex@ConnectedStorage@@QEBAX_N@Z; ConnectedStorage::ContainerIndex::SetHasUnresolvedConflicts(bool)
0x180055a11  mov     rcx, [rbp+var_10]
0x180055a15  xor     rcx, rsp; StackCookie
0x180055a18  call    __security_check_cookie
0x180055a1d  add     rsp, 58h
0x180055a21  pop     rdi
0x180055a22  pop     rsi
0x180055a23  pop     rbx
0x180055a24  pop     rbp
0x180055a25  retn
```
