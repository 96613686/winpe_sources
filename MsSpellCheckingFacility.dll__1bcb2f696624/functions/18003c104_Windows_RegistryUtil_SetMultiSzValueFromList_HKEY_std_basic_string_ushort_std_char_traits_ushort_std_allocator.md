# Windows::RegistryUtil::SetMultiSzValueFromList(HKEY__ *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x18003c104`
- end: `0x18003c297`
- name: `?SetMultiSzValueFromList@RegistryUtil@Windows@@SAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@5@@Z`
- size: `403`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001d888`
- `0x18005dca0`
- `0x18005e068`

## callees

- `0x1800202e4`
- `0x18003c104`
- `0x180061320`
- `0x180062344`
- `0x18006f8c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c268`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c202`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c268`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c25c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c25c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c172`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003c172`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c1f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003c1f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
LSTATUS __fastcall Windows::RegistryUtil::SetMultiSzValueFromList(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        _QWORD *a4)
{
  int v6; // eax
  const BYTE *v7; // rcx
  int v8; // ebx
  LSTATUS result; // eax
  int v10; // ebx
  int pExceptionObject; // [rsp+50h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+Fh] BYREF
  BYTE *lpData[2]; // [rsp+60h] [rbp+17h] BYREF
  int v14; // [rsp+70h] [rbp+27h]
  unsigned __int64 v15; // [rsp+78h] [rbp+2Fh]

  hKey = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  v6 = RegCreateKeyExW(HKEY_CURRENT_USER, a2, 0, 0, 0, 2u, 0, &hKey, 0);
  if ( v6 )
  {
    if ( v6 > 0 )
      v6 = (unsigned __int16)v6 | 0x80070000;
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  if ( (__int64)(a4[1] - *a4) >> 5 )
  {
    Windows::RegistryUtil::MultiSzFromVectorOfWstring(lpData);
    v7 = (const BYTE *)lpData;
    if ( v15 > 7 )
      v7 = lpData[0];
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    v8 = RegSetValueExW(hKey, a3, 0, 7u, v7, 2 * v14 + 2);
    RegCloseKey(hKey);
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    return std::wstring::_Tidy_deallocate(lpData);
  }
  else
  {
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    v10 = RegDeleteValueW(hKey, a3);
    result = RegCloseKey(hKey);
    if ( (v10 & 0xFFFFFFFD) != 0 )
    {
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      pExceptionObject = v10;
      throw (long *)&pExceptionObject;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18003c104  push    rbp
0x18003c106  push    rbx
0x18003c107  push    rdi
0x18003c108  lea     rbp, [rsp-47h]
0x18003c10d  sub     rsp, 90h
0x18003c114  mov     rax, cs:__security_cookie
0x18003c11b  xor     rax, rsp
0x18003c11e  mov     [rbp+57h+var_20], rax
0x18003c122  mov     rdi, r9
0x18003c125  mov     rbx, r8
0x18003c128  mov     [rbp+57h+hKey], 0
0x18003c130  cmp     qword ptr [rdx+18h], 7
0x18003c135  jbe     short loc_18003C13A
0x18003c137  mov     rdx, [rdx]; lpSubKey
0x18003c13a  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x18003c143  lea     rax, [rbp+57h+hKey]
0x18003c147  mov     [rsp+0A0h+phkResult], rax; phkResult
0x18003c14c  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003c155  mov     [rsp+0A0h+samDesired], 2; samDesired
0x18003c15d  mov     [rsp+0A0h+dwOptions], 0; dwOptions
0x18003c165  xor     r9d, r9d; lpClass
0x18003c168  xor     r8d, r8d; Reserved
0x18003c16b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18003c172  call    cs:__imp_RegCreateKeyExW
0x18003c178  test    eax, eax
0x18003c17a  jz      short loc_18003C19A
0x18003c17c  jle     short loc_18003C186
0x18003c17e  movzx   eax, ax
0x18003c181  or      eax, 80070000h
0x18003c186  mov     [rbp+57h+pExceptionObject], eax
0x18003c189  lea     rdx, _TI1J; pThrowInfo
0x18003c190  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003c194  call    _CxxThrowException_0
0x18003c19a  mov     rax, [rdi+8]
0x18003c19e  sub     rax, [rdi]
0x18003c1a1  sar     rax, 5
0x18003c1a5  test    rax, rax
0x18003c1a8  jz      loc_18003C24B
0x18003c1ae  mov     rdx, rdi
0x18003c1b1  lea     rcx, [rbp+57h+lpData]; Src
0x18003c1b5  call    ?MultiSzFromVectorOfWstring@RegistryUtil@Windows@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; Windows::RegistryUtil::MultiSzFromVectorOfWstring(std::vector<std::wstring> const &)
0x18003c1ba  nop
0x18003c1bb  mov     eax, [rbp+57h+var_30]
0x18003c1be  lea     rcx, [rbp+57h+lpData]
0x18003c1c2  cmp     [rbp+57h+var_28], 7
0x18003c1c7  cmova   rcx, [rbp+57h+lpData]
0x18003c1cc  cmp     qword ptr [rbx+18h], 7
0x18003c1d1  jbe     short loc_18003C1D6
0x18003c1d3  mov     rbx, [rbx]
0x18003c1d6  lea     eax, ds:2[rax*2]
0x18003c1dd  mov     [rsp+0A0h+samDesired], eax; cbData
0x18003c1e1  mov     qword ptr [rsp+0A0h+dwOptions], rcx; lpData
0x18003c1e6  mov     r9d, 7; dwType
0x18003c1ec  xor     r8d, r8d; Reserved
0x18003c1ef  mov     rdx, rbx; lpValueName
0x18003c1f2  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c1f6  call    cs:__imp_RegSetValueExW
0x18003c1fc  mov     ebx, eax
0x18003c1fe  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c202  call    cs:__imp_RegCloseKey
0x18003c208  test    ebx, ebx
0x18003c20a  jz      short loc_18003C22B
0x18003c20c  jle     short loc_18003C217
0x18003c20e  movzx   ebx, bx
0x18003c211  or      ebx, 80070000h
0x18003c217  mov     [rbp+57h+pExceptionObject], ebx
0x18003c21a  lea     rdx, _TI1J; pThrowInfo
0x18003c221  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003c225  call    _CxxThrowException_0
0x18003c22b  lea     rcx, [rbp+57h+lpData]
0x18003c22f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c234  mov     rcx, [rbp+57h+var_20]
0x18003c238  xor     rcx, rsp; StackCookie
0x18003c23b  call    __security_check_cookie
0x18003c240  add     rsp, 90h
0x18003c247  pop     rdi
0x18003c248  pop     rbx
0x18003c249  pop     rbp
0x18003c24a  retn
0x18003c24b  cmp     qword ptr [rbx+18h], 7
0x18003c250  jbe     short loc_18003C255
0x18003c252  mov     rbx, [rbx]
0x18003c255  mov     rdx, rbx; lpValueName
0x18003c258  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c25c  call    cs:__imp_RegDeleteValueW
0x18003c262  mov     ebx, eax
0x18003c264  mov     rcx, [rbp+57h+hKey]; hKey
0x18003c268  call    cs:__imp_RegCloseKey
0x18003c26e  test    ebx, 0FFFFFFFDh
0x18003c274  jz      short loc_18003C234
0x18003c276  test    ebx, ebx
0x18003c278  jle     short loc_18003C283
0x18003c27a  movzx   ebx, bx
0x18003c27d  or      ebx, 80070000h
0x18003c283  mov     [rbp+57h+pExceptionObject], ebx
0x18003c286  lea     rdx, _TI1J; pThrowInfo
0x18003c28d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003c291  call    _CxxThrowException_0
```
