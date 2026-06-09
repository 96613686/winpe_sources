# ConnectedStorage::ProviderEnumerator::~ProviderEnumerator(void)

- ea: `0x18001fe1c`
- end: `0x18001fecb`
- name: `??1ProviderEnumerator@ConnectedStorage@@UEAA@XZ`
- size: `175`
- prototype: `void __fastcall(ConnectedStorage::ProviderEnumerator *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001ff50`

## callees

- `0x18000d2f4`
- `0x180012378`
- `0x180012fc0`
- `0x18001c63c`
- `0x18001fe1c`
- `0x18001ff38`
- `0x180020898`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001feb6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001feb6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001fe77`

## pseudocode

```c
void __fastcall ConnectedStorage::ProviderEnumerator::~ProviderEnumerator(ConnectedStorage::ProviderEnumerator *this)
{
  char *v2; // rsi
  char *v3; // rcx
  HSTRING *v4; // rbx
  __int64 v5; // rax
  HSTRING *v6; // [rsp+40h] [rbp+8h] BYREF
  char v7; // [rsp+48h] [rbp+10h] BYREF
  char v8; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)this = &ConnectedStorage::ProviderEnumerator::`vftable';
  v2 = (char *)this + 72;
  std::vector<ConnectedStorage::ContextDesc>::begin((char *)this + 72, &v6);
  while ( 1 )
  {
    v5 = std::vector<ConnectedStorage::BlobRecord>::end(v3, &v7);
    if ( !(unsigned __int8)std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(
                             &v6,
                             v5) )
      break;
    WindowsDeleteString(*v6);
    v4 = (HSTRING *)std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(&v6);
    WindowsDeleteString(v4[1]);
    WindowsDeleteString(v4[2]);
    WindowsDeleteString(v4[3]);
    std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<XblGameSaveProviderInfo>>>::operator++(&v6, &v8);
    v3 = v2;
  }
  std::vector<XblGameSaveProviderInfo>::~vector<XblGameSaveProviderInfo>(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x18001fe1c  push    rbx
0x18001fe1e  push    rsi
0x18001fe1f  push    rdi
0x18001fe20  sub     rsp, 20h
0x18001fe24  lea     rax, ??_7ProviderEnumerator@ConnectedStorage@@6B@; const ConnectedStorage::ProviderEnumerator::`vftable'
0x18001fe2b  mov     rdi, rcx
0x18001fe2e  mov     [rcx], rax
0x18001fe31  lea     rsi, [rcx+48h]
0x18001fe35  mov     rcx, rsi
0x18001fe38  lea     rdx, [rsp+38h+arg_0]
0x18001fe3d  call    ?begin@?$vector@VContextDesc@ConnectedStorage@@V?$allocator@VContextDesc@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VContextDesc@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::ContextDesc>::begin(void)
0x18001fe42  jmp     short loc_18001FE8F
0x18001fe44  mov     rcx, [rsp+38h+arg_0]
0x18001fe49  mov     rcx, [rcx]; string
0x18001fe4c  call    cs:__imp_WindowsDeleteString
0x18001fe52  lea     rcx, [rsp+38h+arg_0]
0x18001fe57  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18001fe5c  mov     rbx, rax
0x18001fe5f  mov     rcx, [rax+8]; string
0x18001fe63  call    cs:__imp_WindowsDeleteString
0x18001fe69  mov     rcx, [rbx+10h]; string
0x18001fe6d  call    cs:__imp_WindowsDeleteString
0x18001fe73  mov     rcx, [rbx+18h]; string
0x18001fe77  call    cs:__imp_WindowsDeleteString
0x18001fe7d  lea     rdx, [rsp+38h+arg_10]
0x18001fe82  lea     rcx, [rsp+38h+arg_0]
0x18001fe87  call    ??E?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UXblGameSaveProviderInfo@@@std@@@std@@@std@@QEAA?AV01@H@Z; std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<XblGameSaveProviderInfo>>>::operator++(int)
0x18001fe8c  mov     rcx, rsi
0x18001fe8f  lea     rdx, [rsp+38h+arg_8]
0x18001fe94  call    ?end@?$vector@UBlobRecord@ConnectedStorage@@V?$allocator@UBlobRecord@ConnectedStorage@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UBlobRecord@ConnectedStorage@@@std@@@std@@@2@XZ; std::vector<ConnectedStorage::BlobRecord>::end(void)
0x18001fe99  mov     rdx, rax
0x18001fe9c  lea     rcx, [rsp+38h+arg_0]
0x18001fea1  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@VNtmTransferWrapper@ConnectedStorage@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<ConnectedStorage::NtmTransferWrapper>>> const &)
0x18001fea6  test    al, al
0x18001fea8  jnz     short loc_18001FE44
0x18001feaa  mov     rcx, rsi
0x18001fead  call    ??1?$vector@UXblGameSaveProviderInfo@@V?$allocator@UXblGameSaveProviderInfo@@@std@@@std@@QEAA@XZ; std::vector<XblGameSaveProviderInfo>::~vector<XblGameSaveProviderInfo>(void)
0x18001feb2  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001feb6  call    cs:__imp_DeleteCriticalSection
0x18001febc  mov     dword ptr [rdi+0Ch], 0C0000001h
0x18001fec3  add     rsp, 20h
0x18001fec7  pop     rdi
0x18001fec8  pop     rsi
0x18001fec9  pop     rbx
0x18001feca  retn
```
