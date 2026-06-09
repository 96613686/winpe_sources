# ConnectedStorage::UserManager::UpdateAuthHeaderCache(ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18002da8c`
- end: `0x18002dc32`
- name: `?UpdateAuthHeaderCache@UserManager@ConnectedStorage@@AEBAXAEBVSimpleHStringWrapper@2@0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `422`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x18002b0b0`
- `0x18002ca10`

## callees

- `0x18000cb9c`
- `0x180012ed8`
- `0x180012fc0`
- `0x18001b9c8`
- `0x18001c63c`
- `0x180020898`
- `0x180029420`
- `0x1800294dc`
- `0x180029538`
- `0x180029824`
- `0x180029e38`
- `0x18002a1c0`
- `0x18002da8c`
- `0x18002e394`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002dc2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dc0d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002dc0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ConnectedStorage::UserManager::UpdateAuthHeaderCache(__int64 a1, __int64 a2, char *a3, __int64 a4)
{
  __int64 v8; // rcx
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rax
  __int64 v15; // r8
  __int64 v16; // rax
  int v17; // ecx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // r8
  __int64 v21; // rax
  _QWORD v22[2]; // [rsp+20h] [rbp-40h] BYREF
  LPCRITICAL_SECTION v23[2]; // [rsp+30h] [rbp-30h] BYREF
  HSTRING v24[4]; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string; // [rsp+90h] [rbp+30h] BYREF
  __int64 v26; // [rsp+98h] [rbp+38h] BYREF
  char v27; // [rsp+A0h] [rbp+40h] BYREF

  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)v23,
    (struct _RTL_CRITICAL_SECTION *)(a1 + 168),
    a3);
  std::vector<ConnectedStorage::BlobRecord>::end(a1 + 216, &v26);
  v9 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v8, &v27);
  v22[0] = a2;
  v22[1] = a3;
  std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___(
    &string,
    *v9,
    v10,
    v22);
  v11 = std::vector<ConnectedStorage::BlobRecord>::end(a1 + 216, &v26);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &string,
                          v11) )
  {
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    std::wstring::operator=(string + 10, v12);
  }
  std::vector<ConnectedStorage::BlobRecord>::end(a1 + 264, &v26);
  v14 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v13, &v27);
  std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::LocalUserInfo_______lambda_679a8a7ad808e55186f7c2039afe97cc___(
    &string,
    *v14,
    v15,
    a3);
  v16 = std::vector<ConnectedStorage::BlobRecord>::end(a1 + 264, &v26);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &string,
                          v16) )
    v17 = *(_DWORD *)string;
  else
    v17 = 0;
  if ( !v17 )
  {
    string = 0;
    std::vector<ConnectedStorage::BlobRecord>::end(a1 + 216, &v27);
    v19 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v18, v22);
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_ea61ac226ace22b93d4c478c88a8d14e___(
      &v26,
      *v19,
      v20,
      a3);
    v21 = std::vector<ConnectedStorage::BlobRecord>::end(a1 + 216, &v27);
    if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                            &v26,
                            v21) )
      ConnectedStorage::SimpleHStringWrapper::operator=(&string, (HSTRING *)(v26 + 16));
    ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(
      v24,
      0,
      (const struct ConnectedStorage::SimpleHStringWrapper *)&string,
      (const struct ConnectedStorage::SimpleHStringWrapper *)a3);
    std::vector<ConnectedStorage::UserManager::LocalUserInfo>::push_back(a1 + 264, v24);
    ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(v24);
    WindowsDeleteString(string);
  }
  LeaveCriticalSection(v23[0]);
}

```

## disassembly

```asm
0x18002da8c  mov     [rsp-28h+arg_18], rbx
0x18002da91  push    rbp
0x18002da92  push    rsi
0x18002da93  push    rdi
0x18002da94  push    r14
0x18002da96  push    r15
0x18002da98  mov     rbp, rsp
0x18002da9b  sub     rsp, 60h
0x18002da9f  mov     r14, r9
0x18002daa2  mov     rdi, r8
0x18002daa5  mov     rbx, rdx
0x18002daa8  mov     r15, rcx
0x18002daab  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x18002dab2  lea     rcx, [rbp+var_30]; this
0x18002dab6  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002dabb  nop
0x18002dabc  lea     rsi, [r15+0D8h]
0x18002dac3  lea     rdx, [rbp+arg_8]
0x18002dac7  mov     rcx, rsi
0x18002daca  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002dacf  mov     r8, [rax]
0x18002dad2  lea     rdx, [rbp+arg_10]
0x18002dad6  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002dadb  mov     [rbp+var_40], rbx
0x18002dadf  mov     [rbp+var_38], rdi
0x18002dae3  lea     r9, [rbp+var_40]
0x18002dae7  mov     rdx, [rax]
0x18002daea  lea     rcx, [rbp+string]
0x18002daee  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_a717a87f1fe21e15a1e5700b403a2f5e___
0x18002daf3  lea     rdx, [rbp+arg_8]
0x18002daf7  mov     rcx, rsi
0x18002dafa  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002daff  mov     rdx, rax
0x18002db02  lea     rcx, [rbp+string]
0x18002db06  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002db0b  test    al, al
0x18002db0d  jz      short loc_18002DB27
0x18002db0f  mov     rcx, r14
0x18002db12  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002db17  mov     rcx, [rbp+string]
0x18002db1b  add     rcx, 28h ; '('
0x18002db1f  mov     rdx, rax
0x18002db22  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x18002db27  lea     rbx, [r15+108h]
0x18002db2e  lea     rdx, [rbp+arg_8]
0x18002db32  mov     rcx, rbx
0x18002db35  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002db3a  mov     r8, [rax]
0x18002db3d  lea     rdx, [rbp+arg_10]
0x18002db41  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002db46  mov     r9, rdi
0x18002db49  mov     rdx, [rax]
0x18002db4c  lea     rcx, [rbp+string]
0x18002db50  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__LocalUserInfo_______lambda_679a8a7ad808e55186f7c2039afe97cc___
0x18002db55  lea     rdx, [rbp+arg_8]
0x18002db59  mov     rcx, rbx
0x18002db5c  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002db61  mov     rdx, rax
0x18002db64  lea     rcx, [rbp+string]
0x18002db68  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002db6d  test    al, al
0x18002db6f  jz      short loc_18002DB79
0x18002db71  mov     rax, [rbp+string]
0x18002db75  mov     ecx, [rax]
0x18002db77  jmp     short loc_18002DB7B
0x18002db79  xor     ecx, ecx
0x18002db7b  test    ecx, ecx
0x18002db7d  jnz     loc_18002DC14
0x18002db83  mov     [rbp+string], 0
0x18002db8b  lea     rdx, [rbp+arg_10]
0x18002db8f  mov     rcx, rsi
0x18002db92  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002db97  mov     r8, [rax]
0x18002db9a  lea     rdx, [rbp+var_40]
0x18002db9e  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002dba3  mov     r9, rdi
0x18002dba6  mov     rdx, [rax]
0x18002dba9  lea     rcx, [rbp+arg_8]
0x18002dbad  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_ea61ac226ace22b93d4c478c88a8d14e___
0x18002dbb2  lea     rdx, [rbp+arg_10]
0x18002dbb6  mov     rcx, rsi
0x18002dbb9  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002dbbe  mov     rdx, rax
0x18002dbc1  lea     rcx, [rbp+arg_8]
0x18002dbc5  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002dbca  test    al, al
0x18002dbcc  jz      short loc_18002DBDF
0x18002dbce  mov     rdx, [rbp+arg_8]
0x18002dbd2  add     rdx, 10h
0x18002dbd6  lea     rcx, [rbp+string]; newString
0x18002dbda  call    ??4SimpleHStringWrapper@ConnectedStorage@@QEAAAEAV01@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::operator=(ConnectedStorage::SimpleHStringWrapper const &)
0x18002dbdf  mov     r9, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x18002dbe2  lea     r8, [rbp+string]; struct ConnectedStorage::SimpleHStringWrapper *
0x18002dbe6  xor     edx, edx; unsigned int
0x18002dbe8  lea     rcx, [rbp+var_20]; this
0x18002dbec  call    ??0LocalUserInfo@UserManager@ConnectedStorage@@QEAA@IAEBVSimpleHStringWrapper@2@0@Z; ConnectedStorage::UserManager::LocalUserInfo::LocalUserInfo(uint,ConnectedStorage::SimpleHStringWrapper const &,ConnectedStorage::SimpleHStringWrapper const &)
0x18002dbf1  nop
0x18002dbf2  lea     rdx, [rbp+var_20]
0x18002dbf6  mov     rcx, rbx
0x18002dbf9  call    ?push_back@?$vector@ULocalUserInfo@UserManager@ConnectedStorage@@V?$allocator@ULocalUserInfo@UserManager@ConnectedStorage@@@std@@@std@@QEAAX$$QEAULocalUserInfo@UserManager@ConnectedStorage@@@Z; std::vector<ConnectedStorage::UserManager::LocalUserInfo>::push_back(ConnectedStorage::UserManager::LocalUserInfo &&)
0x18002dbfe  nop
0x18002dbff  lea     rcx, [rbp+var_20]; this
0x18002dc03  call    ??1LocalUserInfo@UserManager@ConnectedStorage@@QEAA@XZ; ConnectedStorage::UserManager::LocalUserInfo::~LocalUserInfo(void)
0x18002dc08  nop
0x18002dc09  mov     rcx, [rbp+string]; string
0x18002dc0d  call    cs:__imp_WindowsDeleteString
0x18002dc13  nop
0x18002dc14  mov     rcx, [rbp+var_30]
0x18002dc18  mov     rbx, [rsp+60h+arg_18]
0x18002dc20  add     rsp, 60h
0x18002dc24  pop     r15
0x18002dc26  pop     r14
0x18002dc28  pop     rdi
0x18002dc29  pop     rsi
0x18002dc2a  pop     rbp
0x18002dc2b  jmp     cs:__imp_LeaveCriticalSection
```
