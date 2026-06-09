# ConnectedStorage::UserManager::GamerAccountChangedCallback(uint)

- ea: `0x18002ae60`
- end: `0x18002afd5`
- name: `?GamerAccountChangedCallback@UserManager@ConnectedStorage@@AEAAXI@Z`
- size: `373`
- prototype: `void __fastcall(ConnectedStorage::UserManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18002dc40`

## callees

- `0x180003c70`
- `0x18000cb9c`
- `0x180012fc0`
- `0x18001c63c`
- `0x180020898`
- `0x180022dec`
- `0x1800294b8`
- `0x18002ae60`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002afab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af99`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002af99`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall ConnectedStorage::UserManager::GamerAccountChangedCallback(
        ConnectedStorage::UserManager *this,
        int a2,
        char *a3)
{
  __int64 v4; // rcx
  _QWORD *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r10
  __int64 v8; // rax
  void (__fastcall *v9)(ConnectedStorage::UserManager *, _QWORD, _QWORD, HSTRING *, HSTRING *, HSTRING *, _BYTE *); // r14
  HSTRING *AddressOf; // rsi
  HSTRING *v11; // rdi
  HSTRING *v12; // rax
  _BYTE v13[8]; // [rsp+40h] [rbp-A8h] BYREF
  HSTRING v14; // [rsp+48h] [rbp-A0h] BYREF
  HSTRING v15; // [rsp+50h] [rbp-98h] BYREF
  HSTRING string; // [rsp+58h] [rbp-90h] BYREF
  _QWORD *v17; // [rsp+60h] [rbp-88h] BYREF
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+68h] [rbp-80h] BYREF
  _BYTE v19[64]; // [rsp+80h] [rbp-68h] BYREF
  int v20; // [rsp+F8h] [rbp+10h] BYREF

  v20 = a2;
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)this + 168),
    a3);
  std::vector<ConnectedStorage::BlobRecord>::end((char *)this + 216, &v15);
  v5 = (_QWORD *)std::vector<ConnectedStorage::ContextDesc>::begin(v4, &v14);
  std::find_if_std::_Vector_const_iterator_std::_Vector_val_std::_Simple_types_ConnectedStorage::UserManager::UserInfo_______lambda_2765afd47ed6cd70bb4fb18b76aa9bf7___(
    &v17,
    *v5,
    v6,
    &v20);
  v8 = std::vector<ConnectedStorage::BlobRecord>::end(v7, &v15);
  if ( (unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                          &v17,
                          v8) )
  {
    try
    {
      v13[0] = 0;
      v15 = 0;
      v14 = 0;
      string = 0;
      v9 = *(void (__fastcall **)(ConnectedStorage::UserManager *, _QWORD, _QWORD, HSTRING *, HSTRING *, HSTRING *, _BYTE *))(*(_QWORD *)this + 8LL);
      AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
      v11 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v14);
      v12 = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&v15);
      v9(this, *v17, 0, v12, v11, AddressOf, v13);
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v14);
      v14 = 0;
      WindowsDeleteString(v15);
    }
    catch ( ConnectedStorage::ComError v19 )
    {
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v19);
    }
    catch ( std::bad_alloc )
    {
    }
    catch ( ... )
    {
    }
  }
  LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x18002ae60  mov     [rsp+arg_10], rbx
0x18002ae65  mov     [rsp+arg_8], edx
0x18002ae69  push    rsi
0x18002ae6a  push    rdi
0x18002ae6b  push    r14
0x18002ae6d  sub     rsp, 0D0h
0x18002ae74  mov     rax, cs:__security_cookie
0x18002ae7b  xor     rax, rsp
0x18002ae7e  mov     [rsp+0E8h+var_28], rax
0x18002ae86  mov     rbx, rcx
0x18002ae89  lea     rdx, [rcx+0A8h]; struct ConnectedStorage::Mutex *
0x18002ae90  lea     rcx, [rsp+0E8h+lpCriticalSection]; this
0x18002ae95  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18002ae9a  nop
0x18002ae9b  lea     r10, [rbx+0D8h]
0x18002aea2  lea     rdx, [rsp+0E8h+var_98]
0x18002aea7  mov     rcx, r10
0x18002aeaa  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002aeaf  mov     r8, [rax]
0x18002aeb2  lea     rdx, [rsp+0E8h+var_A0]
0x18002aeb7  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18002aebc  lea     r9, [rsp+0E8h+arg_8]
0x18002aec4  mov     rdx, [rax]
0x18002aec7  lea     rcx, [rsp+0E8h+var_88]
0x18002aecc  call    std__find_if_std___Vector_const_iterator_std___Vector_val_std___Simple_types_ConnectedStorage__UserManager__UserInfo_______lambda_2765afd47ed6cd70bb4fb18b76aa9bf7___
0x18002aed1  lea     rdx, [rsp+0E8h+var_98]
0x18002aed6  mov     rcx, r10
0x18002aed9  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18002aede  mov     rdx, rax
0x18002aee1  lea     rcx, [rsp+0E8h+var_88]
0x18002aee6  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18002aeeb  test    al, al
0x18002aeed  jz      loc_18002AFA6
0x18002aef3  mov     [rsp+0E8h+var_A8], 0
0x18002aef8  mov     [rsp+0E8h+var_98], 0
0x18002af01  mov     [rsp+0E8h+var_A0], 0
0x18002af0a  mov     [rsp+0E8h+string], 0
0x18002af13  mov     rax, [rbx]
0x18002af16  mov     r14, [rax+8]
0x18002af1a  lea     rcx, [rsp+0E8h+string]; this
0x18002af1f  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002af24  mov     rsi, rax
0x18002af27  lea     rcx, [rsp+0E8h+var_A0]; this
0x18002af2c  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002af31  mov     rdi, rax
0x18002af34  lea     rcx, [rsp+0E8h+var_98]; this
0x18002af39  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002af3e  lea     rcx, [rsp+0E8h+var_A8]
0x18002af43  mov     [rsp+0E8h+var_B8], rcx
0x18002af48  mov     [rsp+0E8h+var_C0], rsi
0x18002af4d  mov     [rsp+0E8h+var_C8], rdi
0x18002af52  mov     r9, rax
0x18002af55  xor     r8d, r8d
0x18002af58  mov     rdx, [rsp+0E8h+var_88]
0x18002af5d  mov     rdx, [rdx]
0x18002af60  mov     rcx, rbx
0x18002af63  mov     rax, r14
0x18002af66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af6b  nop
0x18002af6c  mov     rcx, [rsp+0E8h+string]; string
0x18002af71  call    cs:__imp_WindowsDeleteString
0x18002af77  mov     [rsp+0E8h+string], 0
0x18002af80  mov     rcx, [rsp+0E8h+var_A0]; string
0x18002af85  call    cs:__imp_WindowsDeleteString
0x18002af8b  mov     [rsp+0E8h+var_A0], 0
0x18002af94  mov     rcx, [rsp+0E8h+var_98]; string
0x18002af99  call    cs:__imp_WindowsDeleteString
0x18002af9f  nop
0x18002afa0  jmp     short loc_18002AFA6
0x18002afa2  jmp     short loc_18002AFA6
0x18002afa4  jmp     short $+2
0x18002afa6  mov     rcx, [rsp+0E8h+lpCriticalSection]; lpCriticalSection
0x18002afab  call    cs:__imp_LeaveCriticalSection
0x18002afb1  mov     rcx, [rsp+0E8h+var_28]
0x18002afb9  xor     rcx, rsp; StackCookie
0x18002afbc  call    __security_check_cookie
0x18002afc1  mov     rbx, [rsp+0E8h+arg_10]
0x18002afc9  add     rsp, 0D0h
0x18002afd0  pop     r14
0x18002afd2  pop     rdi
0x18002afd3  pop     rsi
0x18002afd4  retn
```
