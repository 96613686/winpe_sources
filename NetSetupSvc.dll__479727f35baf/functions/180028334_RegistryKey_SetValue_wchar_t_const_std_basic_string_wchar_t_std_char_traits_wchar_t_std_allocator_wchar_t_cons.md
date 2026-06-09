# RegistryKey::SetValue(wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180028334`
- end: `0x1800283f4`
- name: `?SetValue@RegistryKey@@QEBAXPEB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `192`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001ea44`
- `0x18001f2e4`

## callees

- `0x1800032e4`
- `0x180008c78`
- `0x18000d954`
- `0x180028334`
- `0x1800289c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028379`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180028379`

## pseudocode

```c
LSTATUS __fastcall RegistryKey::SetValue(__int64 a1, int a2)
{
  const BYTE *lpData; // rax
  __int64 v4; // r8
  HKEY *v5; // r10
  LPCWSTR v6; // rdx
  LSTATUS result; // eax
  signed int v8; // ebx
  __int64 v9; // rax
  __int64 v10; // r8
  _BYTE pExceptionObject[208]; // [rsp+30h] [rbp-D8h] BYREF

  lpData = (const BYTE *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
  result = RegSetValueExW(*v5, v6, 0, 1u, lpData, 2 * *(_DWORD *)(v4 + 16) + 2);
  v8 = result;
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v9 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
      WPP_SF_SSD(*(_QWORD *)(v10 + 16), 43, v10, a2, v9, v8);
    }
    Win32Exception::Win32Exception((Win32Exception *)pExceptionObject, v8);
    throw (Win32Exception *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180028334  mov     [rsp+arg_0], rbx
0x180028339  mov     [rsp+arg_8], rsi
0x18002833e  push    rdi
0x18002833f  sub     rsp, 100h
0x180028346  mov     r10, rcx
0x180028349  mov     rdi, r8
0x18002834c  mov     rcx, r8
0x18002834f  mov     rsi, rdx
0x180028352  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180028357  mov     r9d, [r8+10h]
0x18002835b  xor     r8d, r8d; Reserved
0x18002835e  mov     rcx, [r10]; hKey
0x180028361  lea     r9d, ds:2[r9*2]
0x180028369  mov     [rsp+108h+cbData], r9d; cbData
0x18002836e  mov     r9d, 1; dwType
0x180028374  mov     [rsp+108h+lpData], rax; lpData
0x180028379  call    cs:__imp_RegSetValueExW
0x18002837f  mov     ebx, eax
0x180028381  test    eax, eax
0x180028383  jz      short loc_1800283DF
0x180028385  mov     r8, cs:WPP_GLOBAL_Control
0x18002838c  lea     rax, WPP_GLOBAL_Control
0x180028393  cmp     r8, rax
0x180028396  jz      short loc_1800283C1
0x180028398  cmp     byte ptr [r8+19h], 2
0x18002839d  jb      short loc_1800283C1
0x18002839f  mov     rcx, rdi
0x1800283a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x1800283a7  mov     rcx, [r8+10h]
0x1800283ab  mov     edx, 2Bh ; '+'
0x1800283b0  mov     [rsp+108h+cbData], ebx
0x1800283b4  mov     r9, rsi
0x1800283b7  mov     [rsp+108h+lpData], rax
0x1800283bc  call    WPP_SF_SSD
0x1800283c1  mov     edx, ebx; int
0x1800283c3  lea     rcx, [rsp+108h+pExceptionObject]; this
0x1800283c8  call    ??0Win32Exception@@QEAA@J@Z; Win32Exception::Win32Exception(long)
0x1800283cd  lea     rdx, _TI4?AVWin32Exception@@; pThrowInfo
0x1800283d4  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x1800283d9  call    _CxxThrowException_0
0x1800283df  lea     r11, [rsp+108h+var_8]
0x1800283e7  mov     rbx, [r11+10h]
0x1800283eb  mov     rsi, [r11+18h]
0x1800283ef  mov     rsp, r11
0x1800283f2  pop     rdi
0x1800283f3  retn
```
