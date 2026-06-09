# RegistryKey::GetSubKeyByIndex(ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x1800079b4`
- end: `0x180007aed`
- name: `?GetSubKeyByIndex@RegistryKey@@QEBA_NKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `313`
- prototype: `char __fastcall(HKEY *, DWORD, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010294`

## callees

- `0x1800065d4`
- `0x1800079b4`
- `0x180007af4`
- `0x18000895c`
- `0x18000d18c`
- `0x1800119f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007a18`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180007a18`

## pseudocode

```c
char __fastcall RegistryKey::GetSubKeyByIndex(HKEY *a1, DWORD a2, __int64 *a3)
{
  HKEY v3; // rcx
  unsigned int v5; // edi
  __int64 v7; // rcx
  __int64 v8; // rdx
  _BYTE pExceptionObject[208]; // [rsp+40h] [rbp-2F8h] BYREF
  DWORD cchName[4]; // [rsp+110h] [rbp-228h] BYREF
  WCHAR Name[256]; // [rsp+120h] [rbp-218h] BYREF

  v3 = *a1;
  cchName[0] = 256;
  v5 = RegEnumKeyExW(v3, a2, Name, cchName, 0, 0, 0, 0);
  if ( v5 == 259 )
    return 0;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids, v5);
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v5);
    throw (Win32Exception *)pExceptionObject;
  }
  if ( (unsigned __int64)a3[3] < 8 )
    LODWORD(v7) = (_DWORD)a3;
  else
    v7 = *a3;
  if ( (unsigned __int64)a3[3] < 8 )
    LODWORD(v8) = (_DWORD)a3;
  else
    v8 = *a3;
  std::wstring::replace((_DWORD)a3, v8, v7 + 2 * *((_DWORD *)a3 + 4), (unsigned int)Name, (__int64)&Name[cchName[0]]);
  return 1;
}

```

## disassembly

```asm
0x1800079b4  mov     [rsp+arg_18], rbx
0x1800079b9  push    rdi
0x1800079ba  sub     rsp, 330h
0x1800079c1  mov     rax, cs:__security_cookie
0x1800079c8  xor     rax, rsp
0x1800079cb  mov     [rsp+338h+var_18], rax
0x1800079d3  mov     rcx, [rcx]; hKey
0x1800079d6  lea     r9, [rsp+338h+cchName]; lpcchName
0x1800079de  mov     [rsp+338h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800079e7  mov     rbx, r8
0x1800079ea  mov     [rsp+338h+lpcchClass], 0; lpcchClass
0x1800079f3  lea     r8, [rsp+338h+Name]; lpName
0x1800079fb  mov     [rsp+338h+lpClass], 0; lpClass
0x180007a04  mov     [rsp+338h+lpReserved], 0; lpReserved
0x180007a0d  mov     [rsp+338h+cchName], 100h
0x180007a18  call    cs:__imp_RegEnumKeyExW
0x180007a1e  mov     edi, eax
0x180007a20  cmp     eax, 103h
0x180007a25  jnz     short loc_180007A2E
0x180007a27  xor     al, al
0x180007a29  jmp     loc_180007ACC
0x180007a2e  test    edi, edi
0x180007a30  jz      short loc_180007A81
0x180007a32  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a39  lea     rax, WPP_GLOBAL_Control
0x180007a40  cmp     rcx, rax
0x180007a43  jz      short loc_180007A63
0x180007a45  cmp     byte ptr [rcx+19h], 2
0x180007a49  jb      short loc_180007A63
0x180007a4b  mov     rcx, [rcx+10h]
0x180007a4f  lea     r8, WPP_609cb88717ad37ec6501c656e8b7eb9b_Traceguids
0x180007a56  mov     edx, 0Bh
0x180007a5b  mov     r9d, edi
0x180007a5e  call    WPP_SF_d
0x180007a63  mov     edx, edi; int
0x180007a65  lea     rcx, [rsp+338h+pExceptionObject]; this
0x180007a6a  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x180007a6f  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x180007a76  lea     rcx, [rsp+338h+pExceptionObject]; pExceptionObject
0x180007a7b  call    _CxxThrowException_0
0x180007a81  cmp     qword ptr [rbx+18h], 8
0x180007a86  lea     r9, [rsp+338h+Name]
0x180007a8e  mov     eax, [rsp+338h+cchName]
0x180007a95  lea     r9, [r9+rax*2]
0x180007a99  jb      short loc_180007AA0
0x180007a9b  mov     rcx, [rbx]
0x180007a9e  jmp     short loc_180007AA3
0x180007aa0  mov     rcx, rbx
0x180007aa3  mov     rax, [rbx+10h]
0x180007aa7  lea     r8, [rcx+rax*2]
0x180007aab  jb      short loc_180007AB2
0x180007aad  mov     rdx, [rbx]
0x180007ab0  jmp     short loc_180007AB5
0x180007ab2  mov     rdx, rbx
0x180007ab5  mov     [rsp+338h+lpReserved], r9
0x180007aba  mov     rcx, rbx
0x180007abd  lea     r9, [rsp+338h+Name]
0x180007ac5  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@_W@std@@@std@@@2@0PEA_W1@Z; std::wstring::replace(std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,wchar_t *,wchar_t *)
0x180007aca  mov     al, 1
0x180007acc  mov     rcx, [rsp+338h+var_18]
0x180007ad4  xor     rcx, rsp; StackCookie
0x180007ad7  call    __security_check_cookie
0x180007adc  mov     rbx, [rsp+338h+arg_18]
0x180007ae4  add     rsp, 330h
0x180007aeb  pop     rdi
0x180007aec  retn
```
