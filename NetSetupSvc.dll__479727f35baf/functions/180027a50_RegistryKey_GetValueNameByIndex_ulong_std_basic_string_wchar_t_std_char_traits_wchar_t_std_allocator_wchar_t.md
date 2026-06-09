# RegistryKey::GetValueNameByIndex(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180027a50`
- end: `0x180027bd8`
- name: `?GetValueNameByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `392`
- prototype: `char __fastcall(HKEY *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800269c8`

## callees

- `0x1800027c0`
- `0x1800032e4`
- `0x1800078f8`
- `0x180008c78`
- `0x18000d954`
- `0x180019c64`
- `0x180027a50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027acb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027b42`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027acb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180027b42`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall RegistryKey::GetValueNameByIndex(HKEY *a1, DWORD a2, __int64 a3)
{
  WCHAR *v6; // rax
  unsigned int v7; // edi
  WCHAR *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-F8h] BYREF
  DWORD cchValueName; // [rsp+110h] [rbp-28h] BYREF

  cchValueName = 100;
  std::wstring::resize(a3, 100, 0);
  v6 = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  v7 = RegEnumValueW(*a1, a2, v6, &cchValueName, 0, 0, 0, 0);
  if ( v7 == 259 )
    return 0;
  std::wstring::resize(a3, ++cchValueName, 0);
  if ( v7 == 234 )
  {
    v9 = (WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v7 = RegEnumValueW(*a1, a2, v9, &cchValueName, 0, 0, 0, 0);
  }
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids, v7);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v7);
    throw (Win32Exception *)pExceptionObject;
  }
  --*(_QWORD *)(a3 + 16);
  v10 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  *(_WORD *)(v10 + 2 * v11) = 0;
  return 1;
}

```

## disassembly

```asm
0x180027a50  mov     r11, rsp
0x180027a53  mov     [r11+20h], rbx
0x180027a57  push    rbp
0x180027a58  push    rsi
0x180027a59  push    rdi
0x180027a5a  sub     rsp, 120h
0x180027a61  mov     rax, cs:__security_cookie
0x180027a68  xor     rax, rsp
0x180027a6b  mov     [rsp+138h+var_20], rax
0x180027a73  mov     rbx, r8
0x180027a76  mov     ebp, edx
0x180027a78  mov     edx, 64h ; 'd'
0x180027a7d  mov     rsi, rcx
0x180027a80  mov     rcx, rbx
0x180027a83  mov     [r11-28h], edx
0x180027a87  xor     r8d, r8d
0x180027a8a  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180027a8f  mov     rcx, rbx
0x180027a92  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027a97  mov     rcx, [rsi]; hKey
0x180027a9a  lea     r9, [rsp+138h+cchValueName]; lpcchValueName
0x180027aa2  mov     [rsp+138h+lpcbData], 0; lpcbData
0x180027aab  mov     r8, rax; lpValueName
0x180027aae  mov     [rsp+138h+lpData], 0; lpData
0x180027ab7  mov     edx, ebp; dwIndex
0x180027ab9  mov     [rsp+138h+lpType], 0; lpType
0x180027ac2  mov     [rsp+138h+lpReserved], 0; lpReserved
0x180027acb  call    cs:__imp_RegEnumValueW
0x180027ad1  mov     edi, eax
0x180027ad3  cmp     eax, 103h
0x180027ad8  jnz     short loc_180027AE1
0x180027ada  xor     al, al
0x180027adc  jmp     loc_180027BB5
0x180027ae1  mov     eax, [rsp+138h+cchValueName]
0x180027ae8  xor     r8d, r8d
0x180027aeb  inc     eax
0x180027aed  mov     rcx, rbx
0x180027af0  mov     edx, eax
0x180027af2  mov     [rsp+138h+cchValueName], eax
0x180027af9  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x180027afe  cmp     edi, 0EAh
0x180027b04  jnz     short loc_180027B4A
0x180027b06  mov     rcx, rbx
0x180027b09  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027b0e  mov     rcx, [rsi]; hKey
0x180027b11  lea     r9, [rsp+138h+cchValueName]; lpcchValueName
0x180027b19  mov     [rsp+138h+lpcbData], 0; lpcbData
0x180027b22  mov     r8, rax; lpValueName
0x180027b25  mov     [rsp+138h+lpData], 0; lpData
0x180027b2e  mov     edx, ebp; dwIndex
0x180027b30  mov     [rsp+138h+lpType], 0; lpType
0x180027b39  mov     [rsp+138h+lpReserved], 0; lpReserved
0x180027b42  call    cs:__imp_RegEnumValueW
0x180027b48  mov     edi, eax
0x180027b4a  test    edi, edi
0x180027b4c  jz      short loc_180027B9D
0x180027b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b55  lea     rax, WPP_GLOBAL_Control
0x180027b5c  cmp     rcx, rax
0x180027b5f  jz      short loc_180027B7F
0x180027b61  cmp     byte ptr [rcx+19h], 2
0x180027b65  jb      short loc_180027B7F
0x180027b67  mov     rcx, [rcx+10h]
0x180027b6b  lea     r8, WPP_419802ccba213757c01acb0d7aa84d96_Traceguids
0x180027b72  mov     edx, 15h
0x180027b77  mov     r9d, edi
0x180027b7a  call    WPP_SF_d
0x180027b7f  mov     edx, edi; int
0x180027b81  lea     rcx, [rsp+138h+pExceptionObject]; this
0x180027b86  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180027b8b  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180027b92  lea     rcx, [rsp+138h+pExceptionObject]; pExceptionObject
0x180027b97  call    _CxxThrowException_0
0x180027b9d  dec     qword ptr [rbx+10h]
0x180027ba1  mov     rcx, rbx
0x180027ba4  mov     rdx, [rbx+10h]
0x180027ba8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180027bad  xor     ecx, ecx
0x180027baf  mov     [rax+rdx*2], cx
0x180027bb3  mov     al, 1
0x180027bb5  mov     rcx, [rsp+138h+var_20]
0x180027bbd  xor     rcx, rsp; StackCookie
0x180027bc0  call    __security_check_cookie
0x180027bc5  mov     rbx, [rsp+138h+arg_18]
0x180027bcd  add     rsp, 120h
0x180027bd4  pop     rdi
0x180027bd5  pop     rsi
0x180027bd6  pop     rbp
0x180027bd7  retn
```
