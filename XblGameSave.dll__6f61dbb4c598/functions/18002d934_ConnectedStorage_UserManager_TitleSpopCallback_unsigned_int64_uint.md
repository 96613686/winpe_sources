# ConnectedStorage::UserManager::TitleSpopCallback(unsigned __int64,uint)

- ea: `0x18002d934`
- end: `0x18002da4e`
- name: `?TitleSpopCallback@UserManager@ConnectedStorage@@AEAAX_KI@Z`
- size: `282`
- prototype: `void __fastcall(ConnectedStorage::UserManager *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18002dc40`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000b67c`
- `0x18000cb9c`
- `0x180011c0c`
- `0x180012fc0`
- `0x18001c63c`
- `0x180020898`
- `0x180029538`
- `0x18002ad94`
- `0x18002d934`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002da1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002da1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002da27`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ConnectedStorage::UserManager::TitleSpopCallback(ConnectedStorage::UserManager *this, __int64 a2)
{
  int v3; // eax
  const unsigned __int16 *v4; // r8
  char *v5; // r8
  __int64 v6; // rcx
  _QWORD *v7; // rax
  __int64 v8; // r8
  __int64 v9; // rax
  HSTRING string; // [rsp+20h] [rbp-19h] BYREF
  unsigned __int64 *v11; // [rsp+28h] [rbp-11h] BYREF
  _BYTE v12[8]; // [rsp+30h] [rbp-9h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-1h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+40h] [rbp+7h] BYREF
  WCHAR sourceString[24]; // [rsp+50h] [rbp+17h] BYREF

  v3 = StringCchPrintfW(sourceString, 0x15u, L"%I64u", a2);
  if ( v3 < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)v3,
      (int)L"StringCchPrintf(xuidInDec, _countof(xuidInDec), L\"%I64u\", xuid)",
      v4);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, sourceString);
  if ( (*(unsigned __int8 (__fastcall **)(ConnectedStorage::UserManager *, HSTRING *))(*(_QWORD *)this + 24LL))(
         this,
         &string) )
  {
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
      v5);
    std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 216, v13);
    v7 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v6, v12);
    std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_ea61ac226ace22b93d4c478c88a8d14e___(
      &v11,
      *v7,
      v8,
      &string);
    v9 = std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 216, v12);
    if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                            &v11,
                            v9) )
      ConnectedStorage::UserManager::FireUserSignOut(this, *v11);
    LeaveCriticalSection(lpCriticalSection[0]);
  }
  WindowsDeleteString(string);
}

```

## disassembly

```asm
0x18002d934  mov     [rsp-8+arg_10], rbx
0x18002d939  mov     [rsp-8+arg_18], rdi
0x18002d93e  push    rbp
0x18002d93f  lea     rbp, [rsp-57h]
0x18002d944  sub     rsp, 90h
0x18002d94b  mov     rax, cs:__security_cookie
0x18002d952  xor     rax, rsp
0x18002d955  mov     [rbp+57h+var_10], rax
0x18002d959  mov     rdi, rcx
0x18002d95c  mov     r9, rdx
0x18002d95f  lea     r8, aI64u; "%I64u"
0x18002d966  mov     edx, 15h; unsigned __int64
0x18002d96b  lea     rcx, [rbp+57h+sourceString]; unsigned __int16 *
0x18002d96f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d974  test    eax, eax
0x18002d976  jns     short loc_18002D987
0x18002d978  lea     rdx, aStringcchprint_2; "StringCchPrintf(xuidInDec, _countof(xui"...
0x18002d97f  mov     ecx, eax; this
0x18002d981  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002d987  lea     rdx, [rbp+57h+sourceString]; sourceString
0x18002d98b  lea     rcx, [rbp+57h+string]; string
0x18002d98f  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x18002d994  nop
0x18002d995  mov     rax, [rdi]
0x18002d998  lea     rdx, [rbp+57h+string]
0x18002d99c  mov     rcx, rdi
0x18002d99f  mov     rax, [rax+18h]
0x18002d9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9a8  test    al, al
0x18002d9aa  jz      short loc_18002DA23
0x18002d9ac  lea     rdx, [rdi+0A8h]; struct ConnectedStorage::Mutex *
0x18002d9b3  lea     rcx, [rbp+57h+lpCriticalSection]; this
0x18002d9b7  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002d9bc  nop
0x18002d9bd  lea     rbx, [rdi+0D8h]
0x18002d9c4  lea     rdx, [rbp+57h+var_58]
0x18002d9c8  mov     rcx, rbx
0x18002d9cb  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002d9d0  mov     r8, [rax]
0x18002d9d3  lea     rdx, [rbp+57h+var_60]
0x18002d9d7  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002d9dc  lea     r9, [rbp+57h+string]
0x18002d9e0  mov     rdx, [rax]
0x18002d9e3  lea     rcx, [rbp+57h+var_68]
0x18002d9e7  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_ea61ac226ace22b93d4c478c88a8d14e___
0x18002d9ec  lea     rdx, [rbp+57h+var_60]
0x18002d9f0  mov     rcx, rbx
0x18002d9f3  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002d9f8  mov     rdx, rax
0x18002d9fb  lea     rcx, [rbp+57h+var_68]
0x18002d9ff  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002da04  test    al, al
0x18002da06  jz      short loc_18002DA18
0x18002da08  mov     rdx, [rbp+57h+var_68]
0x18002da0c  mov     rdx, [rdx]; unsigned __int64
0x18002da0f  mov     rcx, rdi; this
0x18002da12  call    ?FireUserSignOut@UserManager@ConnectedStorage@@AEBAX_K@Z; ConnectedStorage::UserManager::FireUserSignOut(unsigned __int64)
0x18002da17  nop
0x18002da18  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x18002da1c  call    cs:__imp_LeaveCriticalSection
0x18002da22  nop
0x18002da23  mov     rcx, [rbp+57h+string]; string
0x18002da27  call    cs:__imp_WindowsDeleteString
0x18002da2d  mov     rcx, [rbp+57h+var_10]
0x18002da31  xor     rcx, rsp; StackCookie
0x18002da34  call    __security_check_cookie
0x18002da39  lea     r11, [rsp+90h+var_s0]
0x18002da41  mov     rbx, [r11+20h]
0x18002da45  mov     rdi, [r11+28h]
0x18002da49  mov     rsp, r11
0x18002da4c  pop     rbp
0x18002da4d  retn
```
