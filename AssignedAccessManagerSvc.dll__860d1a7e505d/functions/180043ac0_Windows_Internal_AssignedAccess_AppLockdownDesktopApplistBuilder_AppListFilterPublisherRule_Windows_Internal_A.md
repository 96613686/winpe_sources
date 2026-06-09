# Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterPublisherRule_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_008f66b91adc0c3b9cddf5b173ecb0ff___

- ea: `0x180043ac0`
- end: `0x180043c89`
- name: `Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterPublisherRule_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_008f66b91adc0c3b9cddf5b173ecb0ff___`
- size: `457`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180044aa8`

## callees

- `0x180006640`
- `0x180010c98`
- `0x180014a5c`
- `0x18002001c`
- `0x1800377b0`
- `0x180043ac0`
- `0x18004489c`
- `0x180045614`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b8c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b43`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180043b8c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b0e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043b77`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180043b2e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180043b2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::AssignedAccess::AppLockdownDesktopApplistBuilder::AppListFilterPublisherRule_Windows::Internal::AssignedAccess::WstringAppData_Windows::Internal::AssignedAccess::HstringAppData__lambda_008f66b91adc0c3b9cddf5b173ecb0ff___(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 v6; // rbx
  __int64 v7; // r12
  __int64 v8; // rdi
  __int64 v9; // r14
  PCWSTR StringRawBuffer; // rax
  const WCHAR *v11; // rax
  __int64 v12; // rax
  PCWSTR v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _BYTE v20[32]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v25[40]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[144]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = *a2;
  v7 = a2[1];
  while ( v6 != v7 )
  {
    v8 = *a3;
    v9 = a3[1];
    while ( 1 )
    {
      if ( v8 == v9 )
      {
        v21 = 3;
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 8);
        std::wstring::wstring(v22, v15);
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 40);
        std::wstring::wstring(v23, v16);
        v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 72);
        std::wstring::wstring(v24, v17);
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 104);
        std::wstring::wstring(v25, v18);
        Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppData>::AppData<Windows::Internal::AssignedAccess::WstringAppData>(
          v26,
          &v21);
        std::vector<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppData>>::push_back(
          a4,
          v26);
        Windows::Internal::AssignedAccess::WstringAppData::~WstringAppData((Windows::Internal::AssignedAccess::WstringAppData *)v26);
        Windows::Internal::AssignedAccess::WstringAppData::~WstringAppData((Windows::Internal::AssignedAccess::WstringAppData *)&v21);
        goto LABEL_9;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 8), 0);
      std::wstring::wstring(v20, StringRawBuffer);
      v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
      PathFindFileNameW(v11);
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 8);
      if ( !(unsigned int)_o__wcsicmp(v12) )
      {
        v13 = WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 16), 0);
        if ( !(unsigned int)_o__wcsicmp(v13) )
          break;
        WindowsGetStringRawBuffer(*(HSTRING *)(v8 + 16), 0);
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6 + 40);
        if ( !(unsigned int)_o__wcsicmp(v14) )
          break;
      }
      std::wstring::_Tidy_deallocate(v20);
      v8 += 64;
    }
    std::wstring::_Tidy_deallocate(v20);
LABEL_9:
    v6 += 136;
  }
  return 0;
}

```

## disassembly

```asm
0x180043ac0  mov     [rsp-8+arg_0], rbx
0x180043ac5  push    rbp
0x180043ac6  push    rsi
0x180043ac7  push    rdi
0x180043ac8  push    r12
0x180043aca  push    r13
0x180043acc  push    r14
0x180043ace  push    r15
0x180043ad0  lea     rbp, [rsp-70h]
0x180043ad5  sub     rsp, 170h
0x180043adc  mov     rax, cs:__security_cookie
0x180043ae3  xor     rax, rsp
0x180043ae6  mov     [rbp+0A0h+var_40], rax
0x180043aea  mov     r13, r9
0x180043aed  mov     r15, r8
0x180043af0  mov     rbx, [rdx]
0x180043af3  mov     r12, [rdx+8]
0x180043af7  jmp     loc_180043C4B
0x180043afc  mov     rdi, [r15]
0x180043aff  mov     r14, [r15+8]
0x180043b03  jmp     loc_180043BA8
0x180043b08  xor     edx, edx; length
0x180043b0a  mov     rcx, [rdi+8]; string
0x180043b0e  call    cs:__imp_WindowsGetStringRawBuffer
0x180043b14  mov     rdx, rax
0x180043b17  lea     rcx, [rsp+1A0h+var_180]
0x180043b1c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043b21  lea     rcx, [rsp+1A0h+var_180]
0x180043b26  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b2b  mov     rcx, rax; pszPath
0x180043b2e  call    cs:__imp_PathFindFileNameW
0x180043b34  mov     rdx, rax
0x180043b37  lea     rcx, [rbx+8]
0x180043b3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b40  mov     rcx, rax
0x180043b43  call    cs:__imp__o__wcsicmp
0x180043b49  test    eax, eax
0x180043b4b  jnz     short loc_180043B9A
0x180043b4d  xor     edx, edx; length
0x180043b4f  mov     rcx, [rdi+10h]; string
0x180043b53  call    cs:__imp_WindowsGetStringRawBuffer
0x180043b59  lea     rdx, asc_1800A7204; "*"
0x180043b60  mov     rcx, rax
0x180043b63  call    cs:__imp__o__wcsicmp
0x180043b69  test    eax, eax
0x180043b6b  jz      loc_180043C7D
0x180043b71  xor     edx, edx; length
0x180043b73  mov     rcx, [rdi+10h]; string
0x180043b77  call    cs:__imp_WindowsGetStringRawBuffer
0x180043b7d  mov     rdx, rax
0x180043b80  lea     rcx, [rbx+28h]
0x180043b84  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043b89  mov     rcx, rax
0x180043b8c  call    cs:__imp__o__wcsicmp
0x180043b92  test    eax, eax
0x180043b94  jz      loc_180043C7D
0x180043b9a  lea     rcx, [rsp+1A0h+var_180]
0x180043b9f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043ba4  add     rdi, 40h ; '@'
0x180043ba8  cmp     rdi, r14
0x180043bab  jnz     loc_180043B08
0x180043bb1  mov     [rsp+1A0h+var_160], 3
0x180043bba  lea     rcx, [rbx+8]
0x180043bbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043bc3  mov     rdx, rax
0x180043bc6  lea     rcx, [rsp+1A0h+var_158]
0x180043bcb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043bd0  nop
0x180043bd1  lea     rcx, [rbx+28h]
0x180043bd5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043bda  mov     rdx, rax
0x180043bdd  lea     rcx, [rsp+1A0h+var_138]
0x180043be2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043be7  nop
0x180043be8  lea     rcx, [rbx+48h]
0x180043bec  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043bf1  mov     rdx, rax
0x180043bf4  lea     rcx, [rbp+0A0h+var_118]
0x180043bf8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043bfd  nop
0x180043bfe  lea     rcx, [rbx+68h]
0x180043c02  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180043c07  mov     rdx, rax
0x180043c0a  lea     rcx, [rbp+0A0h+var_F8]
0x180043c0e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043c13  nop
0x180043c14  lea     rdx, [rsp+1A0h+var_160]
0x180043c19  lea     rcx, [rbp+0A0h+var_D0]
0x180043c1d  call    ??0?$AppData@UWstringAppData@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@QEAA@$$QEAUWstringAppData@123@@Z; Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppData>::AppData<Windows::Internal::AssignedAccess::WstringAppData>(Windows::Internal::AssignedAccess::WstringAppData &&)
0x180043c22  nop
0x180043c23  lea     rdx, [rbp+0A0h+var_D0]
0x180043c27  mov     rcx, r13
0x180043c2a  call    ?push_back@?$vector@V?$AppData@UWstringAppData@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@V?$allocator@V?$AppData@UWstringAppData@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@@std@@@std@@QEAAX$$QEAV?$AppData@UWstringAppData@AssignedAccess@Internal@Windows@@@AssignedAccess@Internal@Windows@@@Z; std::vector<Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppData>>::push_back(Windows::Internal::AssignedAccess::AppData<Windows::Internal::AssignedAccess::WstringAppData> &&)
0x180043c2f  nop
0x180043c30  lea     rcx, [rbp+0A0h+var_D0]; this
0x180043c34  call    ??1WstringAppData@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::WstringAppData::~WstringAppData(void)
0x180043c39  nop
0x180043c3a  lea     rcx, [rsp+1A0h+var_160]; this
0x180043c3f  call    ??1WstringAppData@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::WstringAppData::~WstringAppData(void)
0x180043c44  add     rbx, 88h
0x180043c4b  cmp     rbx, r12
0x180043c4e  jnz     loc_180043AFC
0x180043c54  xor     eax, eax
0x180043c56  mov     rcx, [rbp+0A0h+var_40]
0x180043c5a  xor     rcx, rsp; StackCookie
0x180043c5d  call    __security_check_cookie
0x180043c62  mov     rbx, [rsp+1A0h+arg_0]
0x180043c6a  add     rsp, 170h
0x180043c71  pop     r15
0x180043c73  pop     r14
0x180043c75  pop     r13
0x180043c77  pop     r12
0x180043c79  pop     rdi
0x180043c7a  pop     rsi
0x180043c7b  pop     rbp
0x180043c7c  retn
0x180043c7d  lea     rcx, [rsp+1A0h+var_180]
0x180043c82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043c87  jmp     short loc_180043C44
```
