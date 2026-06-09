# ConnectedStorage::ContainerIndex::CreateContainerIndexEntry(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x180064134`
- end: `0x180064248`
- name: `?CreateContainerIndexEntry@ContainerIndex@ConnectedStorage@@QEBAPEAVContainerIndexEntry@2@AEBVSimpleHStringWrapper@2@0@Z`
- size: `276`
- prototype: `HSTRING *__fastcall(ConnectedStorage::ContainerIndex *this, const struct ConnectedStorage::SimpleHStringWrapper *, const struct ConnectedStorage::SimpleHStringWrapper *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18005ed78`
- `0x180070e48`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180012ed8`
- `0x180012fc0`
- `0x180020898`
- `0x18002cf5c`
- `0x18005b004`
- `0x1800640ac`
- `0x180064134`
- `0x180064ab8`
- `0x1800662b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064228`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180064228`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800641c2`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800641c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006421d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006421d`

## string_xrefs

- `0x1800641cc`: `CoCreateGuid(&guid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
HSTRING *__fastcall ConnectedStorage::ContainerIndex::CreateContainerIndexEntry(
        ConnectedStorage::ContainerIndex *this,
        const struct ConnectedStorage::SimpleHStringWrapper *a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3)
{
  char *v5; // rsi
  __int64 v6; // rax
  HSTRING *v7; // rbx
  HRESULT v8; // eax
  const unsigned __int16 *v9; // r8
  HSTRING **v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+38h] [rbp-38h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+40h] [rbp-30h] BYREF
  GUID pguid; // [rsp+50h] [rbp-20h] BYREF

  v5 = (char *)this + 160;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (ConnectedStorage::ContainerIndex *)((char *)this + 64),
    (char *)a3);
  ConnectedStorage::ContainerIndexEntries::find(v5, &v11, a2);
  v6 = std::vector<ConnectedStorage::BlobRecord>::end(v5, &v12);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &v11,
                          v6) )
  {
    v7 = *v11;
    if ( !ConnectedStorage::SimpleHStringWrapper::IsEmpty(a3) )
      ConnectedStorage::SimpleHStringWrapper::operator=(v7 + 1);
  }
  else
  {
    pguid = 0;
    v8 = CoCreateGuid(&pguid);
    if ( v8 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v8, (int)L"CoCreateGuid(&guid)", v9);
    v12 = 0;
    ConnectedStorage::ContainerIndexEntry::Create((_lambda_249230bd792972bce8c42ec595a35649_ *)&v11, (__int64)&pguid);
    v7 = (HSTRING *)v11;
    ConnectedStorage::ContainerIndexEntries::InsertUniqueEntry((__int64)v5, (HSTRING **)&v11);
    std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(&v11);
    WindowsDeleteString(0);
  }
  LeaveCriticalSection(lpCriticalSection[0]);
  return v7;
}

```

## disassembly

```asm
0x180064134  push    rbp
0x180064136  push    rbx
0x180064137  push    rsi
0x180064138  push    rdi
0x180064139  push    r14
0x18006413b  mov     rbp, rsp
0x18006413e  sub     rsp, 70h
0x180064142  mov     rax, cs:__security_cookie
0x180064149  xor     rax, rsp
0x18006414c  mov     [rbp+var_10], rax
0x180064150  mov     rdi, r8
0x180064153  mov     r14, rdx
0x180064156  lea     rsi, [rcx+0A0h]
0x18006415d  lea     rdx, [rcx+40h]; struct ConnectedStorage::Mutex *
0x180064161  lea     rcx, [rbp+lpCriticalSection]; this
0x180064165  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18006416a  nop
0x18006416b  mov     r8, r14
0x18006416e  lea     rdx, [rbp+var_40]
0x180064172  mov     rcx, rsi
0x180064175  call    ?find@ContainerIndexEntries@ConnectedStorage@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@std@@@std@@@std@@AEBVSimpleHStringWrapper@2@@Z; ConnectedStorage::ContainerIndexEntries::find(ConnectedStorage::SimpleHStringWrapper const &)
0x18006417a  lea     rdx, [rbp+var_38]
0x18006417e  mov     rcx, rsi
0x180064181  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x180064186  mov     rdx, rax
0x180064189  lea     rcx, [rbp+var_40]
0x18006418d  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x180064192  test    al, al
0x180064194  jz      short loc_1800641B7
0x180064196  mov     rax, [rbp+var_40]
0x18006419a  mov     rbx, [rax]
0x18006419d  mov     rcx, rdi; this
0x1800641a0  call    ?IsEmpty@SimpleHStringWrapper@ConnectedStorage@@QEBA_NXZ; ConnectedStorage::SimpleHStringWrapper::IsEmpty(void)
0x1800641a5  test    al, al
0x1800641a7  jnz     short loc_180064224
0x1800641a9  lea     rcx, [rbx+8]; newString
0x1800641ad  mov     rdx, rdi
0x1800641b0  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x1800641b5  jmp     short loc_180064224
0x1800641b7  xorps   xmm0, xmm0
0x1800641ba  movups  xmmword ptr [rbp+pguid.Data1], xmm0
0x1800641be  lea     rcx, [rbp+pguid]; pguid
0x1800641c2  call    cs:__imp_CoCreateGuid
0x1800641c8  test    eax, eax
0x1800641ca  jns     short loc_1800641DB
0x1800641cc  lea     rdx, aCocreateguidGu; "CoCreateGuid(&guid)"
0x1800641d3  mov     ecx, eax; this
0x1800641d5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x1800641db  mov     [rbp+var_38], 0
0x1800641e3  lea     rax, [rbp+pguid]
0x1800641e7  mov     [rsp+70h+var_50], rax; __int64
0x1800641ec  lea     r9, [rbp+var_38]
0x1800641f0  mov     r8, rdi
0x1800641f3  mov     rdx, r14
0x1800641f6  lea     rcx, [rbp+var_40]; this
0x1800641fa  call    ?Create@ContainerIndexEntry@ConnectedStorage@@SA?AV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@AEBVSimpleHStringWrapper@2@00AEBU_GUID@@W4State@12@@Z; ConnectedStorage::ContainerIndexEntry::Create(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,_GUID const &,ConnectedStorage::ContainerIndexEntry::State)
0x1800641ff  nop
0x180064200  mov     rbx, [rbp+var_40]
0x180064204  lea     rdx, [rbp+var_40]
0x180064208  mov     rcx, rsi
0x18006420b  call    ?InsertUniqueEntry@ContainerIndexEntries@ConnectedStorage@@QEAAX$$QEAV?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@@Z; ConnectedStorage::ContainerIndexEntries::InsertUniqueEntry(std::unique_ptr<ConnectedStorage::ContainerIndexEntry> &&)
0x180064210  nop
0x180064211  lea     rcx, [rbp+var_40]
0x180064215  call    ??1?$unique_ptr@VContainerIndexEntry@ConnectedStorage@@U?$default_delete@VContainerIndexEntry@ConnectedStorage@@@std@@@std@@QEAA@XZ; std::unique_ptr<ConnectedStorage::ContainerIndexEntry>::~unique_ptr<ConnectedStorage::ContainerIndexEntry>(void)
0x18006421a  nop
0x18006421b  xor     ecx, ecx; string
0x18006421d  call    cs:__imp_WindowsDeleteString
0x180064223  nop
0x180064224  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
0x180064228  call    cs:__imp_LeaveCriticalSection
0x18006422e  mov     rax, rbx
0x180064231  mov     rcx, [rbp+var_10]
0x180064235  xor     rcx, rsp; StackCookie
0x180064238  call    __security_check_cookie
0x18006423d  add     rsp, 70h
0x180064241  pop     r14
0x180064243  pop     rdi
0x180064244  pop     rsi
0x180064245  pop     rbx
0x180064246  pop     rbp
0x180064247  retn
```
