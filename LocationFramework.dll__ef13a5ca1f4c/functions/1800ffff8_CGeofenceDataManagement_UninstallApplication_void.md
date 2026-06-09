# CGeofenceDataManagement::UninstallApplication(void)

- ea: `0x1800ffff8`
- end: `0x1801000f1`
- name: `?UninstallApplication@CGeofenceDataManagement@@QEAAJXZ`
- size: `249`
- prototype: `__int64 __fastcall(CGeofenceDataManagement *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a19c0`

## callees

- `0x180012194`
- `0x1800123c0`
- `0x180016e30`
- `0x18002085c`
- `0x180020994`
- `0x180020c64`
- `0x18004a528`
- `0x1800a98c0`
- `0x1800ffff8`
- `0x1801004ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180100077`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801000bb`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1801000bb`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010006d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18010006d`

## string_xrefs

- `0x180100098`: `DeleteFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CGeofenceDataManagement::UninstallApplication(CGeofenceDataManagement *this)
{
  unsigned int v2; // edi
  __int64 v3; // rdx
  const WCHAR *v4; // rax
  __int64 v5; // rdx
  signed int LastError; // eax
  __int64 v7; // rcx
  const WCHAR *v8; // rax
  _BYTE v10[16]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v11[32]; // [rsp+30h] [rbp-38h] BYREF

  v2 = 0;
  ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(v10, this);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 72,
    0);
  std::wstring::wstring(v11, (char *)this + 40);
  std::wstring::append(v11, L"\\");
  std::wstring::append(v11, L"Geofence.dat");
  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v11, v3);
  if ( DeleteFileW(v4) )
    goto LABEL_7;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( (byte_1801E39C4 & 0x10) != 0 )
    McTemplateU0zq_EventWriteTransfer(v7, GeofenceStoreInternalError, L"DeleteFile failed", v2);
  if ( (v2 & 0x80000000) == 0 )
  {
LABEL_7:
    v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 40, v5);
    RemoveDirectoryW(v8);
  }
  std::wstring::_Tidy_deallocate(v11);
  ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(v10);
  return v2;
}

```

## disassembly

```asm
0x1800ffff8  mov     [rsp+arg_8], rbx
0x1800ffffd  push    rdi
0x1800ffffe  sub     rsp, 60h
0x180100002  mov     rax, cs:__security_cookie
0x180100009  xor     rax, rsp
0x18010000c  mov     [rsp+68h+var_18], rax
0x180100011  mov     rbx, rcx
0x180100014  xor     edi, edi
0x180100016  mov     rdx, rcx
0x180100019  lea     rcx, [rsp+68h+var_48]
0x18010001e  call    ??0?$CComCritSecLock@VCComAutoCriticalSection@ATL@@@ATL@@QEAA@AEAVCComAutoCriticalSection@1@_N@Z; ATL::CComCritSecLock<ATL::CComAutoCriticalSection>::CComCritSecLock<ATL::CComAutoCriticalSection>(ATL::CComAutoCriticalSection &,bool)
0x180100023  nop
0x180100024  lea     rcx, [rbx+48h]
0x180100028  xor     edx, edx
0x18010002a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18010002f  lea     rdx, [rbx+28h]
0x180100033  lea     rcx, [rsp+68h+var_38]
0x180100038  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18010003d  nop
0x18010003e  lea     rdx, asc_18016EDDC; "\\"
0x180100045  lea     rcx, [rsp+68h+var_38]
0x18010004a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18010004f  lea     rdx, aGeofenceDat; "Geofence.dat"
0x180100056  lea     rcx, [rsp+68h+var_38]
0x18010005b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180100060  lea     rcx, [rsp+68h+var_38]
0x180100065  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18010006a  mov     rcx, rax; lpFileName
0x18010006d  call    cs:__imp_DeleteFileW
0x180100073  test    eax, eax
0x180100075  jnz     short loc_1801000AF
0x180100077  call    cs:__imp_GetLastError
0x18010007d  mov     edi, eax
0x18010007f  test    eax, eax
0x180100081  jle     short loc_18010008C
0x180100083  movzx   edi, ax
0x180100086  or      edi, 80070000h
0x18010008c  test    cs:byte_1801E39C4, 10h
0x180100093  jz      short loc_1801000AB
0x180100095  mov     r9d, edi
0x180100098  lea     r8, aDeletefileFail; "DeleteFile failed"
0x18010009f  lea     rdx, GeofenceStoreInternalError
0x1801000a6  call    McTemplateU0zq_EventWriteTransfer
0x1801000ab  test    edi, edi
0x1801000ad  js      short loc_1801000C2
0x1801000af  lea     rcx, [rbx+28h]
0x1801000b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801000b8  mov     rcx, rax; lpPathName
0x1801000bb  call    cs:__imp_RemoveDirectoryW
0x1801000c1  nop
0x1801000c2  lea     rcx, [rsp+68h+var_38]
0x1801000c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801000cc  nop
0x1801000cd  lea     rcx, [rsp+68h+var_48]
0x1801000d2  call    ??1?$CComCritSecLock@VCComCriticalSection@ATL@@@ATL@@QEAA@XZ; ATL::CComCritSecLock<ATL::CComCriticalSection>::~CComCritSecLock<ATL::CComCriticalSection>(void)
0x1801000d7  mov     eax, edi
0x1801000d9  mov     rcx, [rsp+68h+var_18]
0x1801000de  xor     rcx, rsp; StackCookie
0x1801000e1  call    __security_check_cookie
0x1801000e6  mov     rbx, [rsp+68h+arg_8]
0x1801000eb  add     rsp, 60h
0x1801000ef  pop     rdi
0x1801000f0  retn
```
