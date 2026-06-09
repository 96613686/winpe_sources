# ConnectedStorage::Container::UpdateContainer(std::shared_ptr<ConnectedStorage::UpdateData>,ConnectedStorage::MultiFileWrite *)

- ea: `0x180076fb4`
- end: `0x1800771ab`
- name: `?UpdateContainer@Container@ConnectedStorage@@AEAAXV?$shared_ptr@UUpdateData@ConnectedStorage@@@std@@PEAVMultiFileWrite@2@@Z`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180076e5c`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180010f28`
- `0x180011b94`
- `0x1800124d0`
- `0x1800190f0`
- `0x18003ea50`
- `0x18004a8c8`
- `0x18005a88c`
- `0x1800608e0`
- `0x180070d04`
- `0x180076fb4`
- `0x180079530`
- `0x18007aae0`
- `0x18007ad44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077160`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180077160`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180077030`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180077030`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077121`

## string_xrefs

- `0x18007719c`: `CoCreateGuid(&newGuid)`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ConnectedStorage::Container::UpdateContainer(__int64 a1, __int64 a2, char *a3)
{
  __int64 i; // rbx
  HRESULT v6; // eax
  const unsigned __int16 *v7; // r8
  _QWORD *Quota; // rax
  ConnectedStorage::AtomManager *v9; // r10
  unsigned int v10; // esi
  __int64 v11; // rdi
  HSTRING *v12; // rax
  HSTRING *j; // rbx
  HSTRING *v14; // rdi
  HSTRING *v15; // rax
  std::_Ref_count_base *v16; // rcx
  HSTRING newString; // [rsp+30h] [rbp-99h] BYREF
  _BYTE *v18; // [rsp+38h] [rbp-91h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v20[8]; // [rsp+48h] [rbp-81h] BYREF
  _BYTE *v21; // [rsp+50h] [rbp-79h]
  HSTRING *v22; // [rsp+60h] [rbp-69h]
  LPCRITICAL_SECTION v23[3]; // [rsp+68h] [rbp-61h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v25[32]; // [rsp+90h] [rbp-39h] BYREF
  GUID pguid; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v27[32]; // [rsp+C0h] [rbp-9h] BYREF

  v23[2] = (LPCRITICAL_SECTION)a2;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 56),
    a3);
  std::vector<ConnectedStorage::BlobRecord>::vector<ConnectedStorage::BlobRecord>(v20, a1 + 104);
  for ( i = *(_QWORD *)(*(_QWORD *)a2 + 176LL); i != *(_QWORD *)(*(_QWORD *)a2 + 184LL); i += 32 )
  {
    pguid = 0;
    v6 = CoCreateGuid(&pguid);
    if ( v6 < 0 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)v6, (int)L"CoCreateGuid(&newGuid)", v7);
    Quota = std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(
              v23,
              (_QWORD *)(i + 16));
    ConnectedStorage::AtomManager::WriteNewAtom(v9, (__int64)Quota);
    v10 = **(_DWORD **)(i + 16);
    v18 = v25;
    v11 = ConnectedStorage::Atom::Atom((ConnectedStorage::Atom *)v25, (const struct ConnectedStorage::Atom *)v27);
    v12 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, (HSTRING *)i);
    ConnectedStorage::BlobRecords::SetBlob(v20, v12, v11, v10);
    ConnectedStorage::Atom::~Atom((ConnectedStorage::Atom *)v27);
  }
  for ( j = *(HSTRING **)(*(_QWORD *)a2 + 200LL); j != *(HSTRING **)(*(_QWORD *)a2 + 208LL); ++j )
  {
    v14 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&newString, j);
    v22 = v14;
    v15 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&v19, v14);
    ConnectedStorage::BlobRecords::Find(v20, &v18, v15);
    if ( v18 != v21 )
      std::vector<ConnectedStorage::BlobRecord>::erase(v20, &pguid);
    WindowsDeleteString(*v14);
    *v14 = 0;
  }
  std::swap<ConnectedStorage::BlobRecords,0>(a1 + 128, a1 + 104);
  std::swap<ConnectedStorage::BlobRecords,0>(v20, a1 + 104);
  std::vector<ConnectedStorage::BlobRecord>::_Tidy(v20);
  LeaveCriticalSection(lpCriticalSection[0]);
  v16 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
}

```

## disassembly

```asm
0x180076fb4  mov     [rsp-8+arg_18], rbx
0x180076fb9  push    rbp
0x180076fba  push    rsi
0x180076fbb  push    rdi
0x180076fbc  push    r12
0x180076fbe  push    r13
0x180076fc0  push    r14
0x180076fc2  push    r15
0x180076fc4  lea     rbp, [rsp-27h]
0x180076fc9  sub     rsp, 0F0h
0x180076fd0  mov     rax, cs:__security_cookie
0x180076fd7  xor     rax, rsp
0x180076fda  mov     [rbp+57h+var_40], rax
0x180076fde  mov     r13, r8
0x180076fe1  mov     r14, rdx
0x180076fe4  mov     r15, rcx
0x180076fe7  mov     [rbp+57h+var_A8], rdx
0x180076feb  lea     rdx, [rcx+38h]; struct ConnectedStorage::Mutex *
0x180076fef  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x180076ff3  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x180076ff8  nop
0x180076ff9  lea     r12, [r15+68h]
0x180076ffd  mov     rdx, r12
0x180077000  lea     rcx, [rsp+120h+var_D8]
0x180077005  call    ??0?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<ConnectedStorage::BlobRecord>::vector<ConnectedStorage::BlobRecord>(std::vector<ConnectedStorage::BlobRecord> const &)
0x18007700a  nop
0x18007700b  mov     rbx, [r14]
0x18007700e  mov     rbx, [rbx+0B0h]
0x180077015  mov     rax, [r14]
0x180077018  cmp     rbx, [rax+0B8h]
0x18007701f  jz      loc_1800770BE
0x180077025  xorps   xmm0, xmm0
0x180077028  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18007702c  lea     rcx, [rbp+57h+pguid]; pguid
0x180077030  call    cs:__imp_CoCreateGuid
0x180077036  test    eax, eax
0x180077038  js      loc_18007719C
0x18007703e  mov     r10, [r15+98h]
0x180077045  lea     rdx, [rbx+10h]
0x180077049  lea     rcx, [rbp+57h+var_B8]
0x18007704d  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x180077052  mov     [rsp+120h+var_100], rax; __int64
0x180077057  lea     r9, [rbp+57h+pguid]
0x18007705b  mov     r8, r13
0x18007705e  lea     rdx, [rbp+57h+var_60]
0x180077062  mov     rcx, r10; this
0x180077065  call    ?WriteNewAtom@AtomManager@ConnectedStorage@@QEAA?AVAtom@2@PEAVMultiFileWrite@2@AEBU_GUID@@V?$shared_ptr@VCountedBytes@ConnectedStorage@@@std@@@Z; ConnectedStorage::AtomManager::WriteNewAtom(ConnectedStorage::MultiFileWrite *,_GUID const &,std::shared_ptr<ConnectedStorage::CountedBytes>)
0x18007706a  nop
0x18007706b  mov     rax, [rbx+10h]
0x18007706f  mov     esi, [rax]
0x180077071  lea     rax, [rbp+57h+var_90]
0x180077075  mov     [rsp+120h+var_E8], rax
0x18007707a  lea     rdx, [rbp+57h+var_60]; struct ConnectedStorage::Atom *
0x18007707e  lea     rcx, [rbp+57h+var_90]; this
0x180077082  call    ??0Atom@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::Atom::Atom(ConnectedStorage::Atom const &)
0x180077087  mov     rdi, rax
0x18007708a  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18007708d  lea     rcx, [rsp+120h+newString]; newString
0x180077092  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180077097  nop
0x180077098  mov     r9d, esi
0x18007709b  mov     r8, rdi
0x18007709e  mov     rdx, rax
0x1800770a1  lea     rcx, [rsp+120h+var_D8]
0x1800770a6  call    ?SetBlob@BlobRecords@ConnectedStorage@@QEAAXVSimpleHStringWrapper@2@VAtom@2@I@Z; ConnectedStorage::BlobRecords::SetBlob(ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::Atom,uint)
0x1800770ab  nop
0x1800770ac  lea     rcx, [rbp+57h+var_60]; this
0x1800770b0  call    ??1Atom@ConnectedStorage@@QEAA@XZ; ConnectedStorage::Atom::~Atom(void)
0x1800770b5  add     rbx, 20h ; ' '
0x1800770b9  jmp     loc_180077015
0x1800770be  mov     rbx, [rax+0C8h]
0x1800770c5  mov     rax, [r14]
0x1800770c8  cmp     rbx, [rax+0D0h]
0x1800770cf  jz      short loc_180077134
0x1800770d1  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x1800770d4  lea     rcx, [rsp+120h+newString]; newString
0x1800770d9  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x1800770de  mov     rdi, rax
0x1800770e1  mov     [rbp+57h+var_C0], rax
0x1800770e5  mov     rdx, rax; struct ConnectedStorage::SimpleHStringWrapper *
0x1800770e8  lea     rcx, [rsp+120h+var_E0]; newString
0x1800770ed  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x1800770f2  mov     r8, rax
0x1800770f5  lea     rdx, [rsp+120h+var_E8]
0x1800770fa  lea     rcx, [rsp+120h+var_D8]
0x1800770ff  call    ?Find@BlobRecords@ConnectedStorage@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@std@@VSimpleHStringWrapper@2@@Z; ConnectedStorage::BlobRecords::Find(ConnectedStorage::SimpleHStringWrapper)
0x180077104  mov     r8, [rsp+120h+var_E8]
0x180077109  cmp     r8, [rbp+57h+var_D0]
0x18007710d  jz      short loc_18007711E
0x18007710f  lea     rdx, [rbp+57h+pguid]
0x180077113  lea     rcx, [rsp+120h+var_D8]
0x180077118  call    ?erase@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@@Z; std::vector<ConnectedStorage::BlobRecord>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ConnectedStorage::BlobRecord>>>)
0x18007711d  nop
0x18007711e  mov     rcx, [rdi]; string
0x180077121  call    cs:__imp_WindowsDeleteString
0x180077127  mov     qword ptr [rdi], 0
0x18007712e  add     rbx, 8
0x180077132  jmp     short loc_1800770C5
0x180077134  lea     rcx, [r15+80h]
0x18007713b  mov     rdx, r12
0x18007713e  call    ??$swap@VBlobRecords@ConnectedStorage@@$0A@@std@@YAXAEAVBlobRecords@ConnectedStorage@@0@Z; std::swap<ConnectedStorage::BlobRecords,0>(ConnectedStorage::BlobRecords &,ConnectedStorage::BlobRecords &)
0x180077143  mov     rdx, r12
0x180077146  lea     rcx, [rsp+120h+var_D8]
0x18007714b  call    ??$swap@VBlobRecords@ConnectedStorage@@$0A@@std@@YAXAEAVBlobRecords@ConnectedStorage@@0@Z; std::swap<ConnectedStorage::BlobRecords,0>(ConnectedStorage::BlobRecords &,ConnectedStorage::BlobRecords &)
0x180077150  nop
0x180077151  lea     rcx, [rsp+120h+var_D8]
0x180077156  call    ?_Tidy@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@AEAAXXZ; std::vector<ConnectedStorage::BlobRecord>::_Tidy(void)
0x18007715b  nop
0x18007715c  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x180077160  call    cs:__imp_LeaveCriticalSection
0x180077166  nop
0x180077167  mov     rcx, [r14+8]; this
0x18007716b  test    rcx, rcx
0x18007716e  jz      short loc_180077175
0x180077170  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180077175  mov     rcx, [rbp+57h+var_40]
0x180077179  xor     rcx, rsp; StackCookie
0x18007717c  call    __security_check_cookie
0x180077181  mov     rbx, [rsp+120h+arg_18]
0x180077189  add     rsp, 0F0h
0x180077190  pop     r15
0x180077192  pop     r14
0x180077194  pop     r13
0x180077196  pop     r12
0x180077198  pop     rdi
0x180077199  pop     rsi
0x18007719a  pop     rbp
0x18007719b  retn
0x18007719c  lea     rdx, aCocreateguidNe; "CoCreateGuid(&newGuid)"
0x1800771a3  mov     ecx, eax; this
0x1800771a5  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
