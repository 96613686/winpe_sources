# NgcUtils::ClearScenarioInProgressStatus

- ea: `0x18002afa8`
- end: `0x18002b0d5`
- name: `NgcUtils::ClearScenarioInProgressStatus`
- size: `301`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050070`

## callees

- `0x18000a8e0`
- `0x18000b180`
- `0x1800199d8`
- `0x180023278`
- `0x180029980`
- `0x18002afa8`
- `0x18002b0dc`
- `0x18002c640`
- `0x18005b308`
- `0x18005c788`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002b06c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002b06c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b035`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002b035`

## string_xrefs

- `0x18002afe6`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`
- `0x18002b04d`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`
- `0x18002b098`: `onecore\ds\security\ngc\utils\common\lib\logoncredsregutils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 NgcUtils::ClearScenarioInProgressStatus()
{
  unsigned __int16 *v0; // r8
  int v1; // eax
  unsigned int v2; // ebx
  HKEY *v3; // rax
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  int v6; // eax
  bool v7; // dl
  int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  std::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>::basic_string<unsigned short,std::char_traits<unsigned short>,wil::secure_allocator<unsigned short>>((__int64)lpSubKey);
  v1 = NgcUtils::BuildFullRegKeyPath_0(v0);
  v2 = v1;
  if ( v1 >= 0 )
  {
    hKey = 0;
    v3 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    v4 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v4 = lpSubKey[0];
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 2u, v3);
    if ( v5 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x27B,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
        (const char *)v5,
        phkResulta);
    }
    else
    {
      v6 = RegDeleteValueW(hKey, L"DestructiveResetInProgress");
      v7 = (v6 & 0xFFFFFFFD) != 0;
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( v7 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x280,
          (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
          (const char *)(unsigned int)v6,
          phkResulta);
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x273,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\logoncredsregutils.cpp",
      (const char *)(unsigned int)v1,
      phkResult);
  }
  std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(lpSubKey);
  return v2;
}

```

## disassembly

```asm
0x18002afa8  push    rbx
0x18002afaa  sub     rsp, 60h
0x18002afae  mov     rax, cs:__security_cookie
0x18002afb5  xor     rax, rsp
0x18002afb8  mov     [rsp+68h+var_10], rax
0x18002afbd  mov     r8, rcx
0x18002afc0  lea     rcx, [rsp+68h+lpSubKey]
0x18002afc5  call    ??0?$basic_string@GU?$char_traits@G@std@@U?$secure_allocator@G@wil@@@std@@QEAA@XZ; std::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,wil::secure_allocator<ushort>>(void)
0x18002afca  nop
0x18002afcb  lea     rdx, [rsp+68h+lpSubKey]
0x18002afd0  mov     rcx, r8; unsigned __int16 *
0x18002afd3  call    NgcUtils__BuildFullRegKeyPath_0
0x18002afd8  mov     ebx, eax
0x18002afda  test    eax, eax
0x18002afdc  jns     short loc_18002AFFC
0x18002afde  mov     rcx, [rsp+68h]; this
0x18002afe3  mov     r9d, eax; char *
0x18002afe6  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002afed  mov     edx, 273h; void *
0x18002aff2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002aff7  jmp     loc_18002B0B5
0x18002affc  mov     [rsp+68h+hKey], 0
0x18002b005  lea     rcx, [rsp+68h+hKey]
0x18002b00a  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18002b00f  lea     rdx, [rsp+68h+lpSubKey]
0x18002b014  cmp     [rsp+68h+var_18], 7
0x18002b01a  cmova   rdx, [rsp+68h+lpSubKey]; lpSubKey
0x18002b020  mov     qword ptr [rsp+68h+phkResult], rax; int
0x18002b025  mov     r9d, 2; samDesired
0x18002b02b  xor     r8d, r8d; ulOptions
0x18002b02e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b035  call    cs:__imp_RegOpenKeyExW
0x18002b03c  nop     dword ptr [rax+rax+00h]
0x18002b041  mov     rcx, [rsp+68h]; this
0x18002b046  test    eax, eax
0x18002b048  jz      short loc_18002B060
0x18002b04a  mov     r9d, eax; char *
0x18002b04d  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002b054  mov     edx, 27Bh; void *
0x18002b059  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18002b05e  jmp     short loc_18002B0A9
0x18002b060  lea     rdx, aDestructiveres; "DestructiveResetInProgress"
0x18002b067  mov     rcx, [rsp+68h+hKey]; hKey
0x18002b06c  call    cs:__imp_RegDeleteValueW
0x18002b073  nop     dword ptr [rax+rax+00h]
0x18002b078  test    eax, 0FFFFFFFDh
0x18002b07d  setnz   dl
0x18002b080  test    eax, eax
0x18002b082  jle     short loc_18002B08C
0x18002b084  movzx   eax, ax
0x18002b087  or      eax, 80070000h
0x18002b08c  mov     rcx, [rsp+68h]; this
0x18002b091  test    dl, dl
0x18002b093  jz      short loc_18002B0A9
0x18002b095  mov     r9d, eax; char *
0x18002b098  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18002b09f  mov     edx, 280h; void *
0x18002b0a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002b0a9  lea     rcx, [rsp+68h+hKey]
0x18002b0ae  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002b0b3  xor     ebx, ebx
0x18002b0b5  lea     rcx, [rsp+68h+lpSubKey]
0x18002b0ba  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_FILETIME@@@std@@QEAA@XZ; std::pair<std::wstring,_FILETIME>::~pair<std::wstring,_FILETIME>(void)
0x18002b0bf  mov     eax, ebx
0x18002b0c1  mov     rcx, [rsp+68h+var_10]
0x18002b0c6  xor     rcx, rsp; StackCookie
0x18002b0c9  call    __security_check_cookie
0x18002b0ce  add     rsp, 60h
0x18002b0d2  pop     rbx
0x18002b0d3  retn
```
