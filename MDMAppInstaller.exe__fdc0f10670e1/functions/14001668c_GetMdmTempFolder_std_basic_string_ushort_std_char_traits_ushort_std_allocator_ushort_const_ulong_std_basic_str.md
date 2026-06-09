# GetMdmTempFolder(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14001668c`
- end: `0x1400167f8`
- name: `?GetMdmTempFolder@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEAV12@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, ULONG, const WCHAR *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a5e0`
- `0x140018e48`

## callees

- `0x140003674`
- `0x1400055f8`
- `0x140006604`
- `0x1400068c8`
- `0x14000740c`
- `0x140011d58`
- `0x14001668c`
- `0x140017610`
- `0x140018668`
- `0x14001a8d0`

## import_xrefs

- `ADVAPI32!RevertToSelf` at `0x1400167cd`
- `ADVAPI32!RevertToSelf` at `0x1400167cd`
- `SHELL32!SHCreateDirectoryExW` at `0x140016779`
- `SHELL32!SHCreateDirectoryExW` at `0x140016779`
- `SHELL32!SHGetSpecialFolderPathW` at `0x140016726`
- `SHELL32!SHGetSpecialFolderPathW` at `0x140016726`

## string_xrefs

- `0x140016704`: `Failed to impersonate before get mdm temp folder. Error 0x%1!x!`
- `0x1400167b0`: `Failed to create folder %1. Error 0x%2!x!`

## pseudocode

```c
__int64 __fastcall GetMdmTempFolder(__int64 a1, ULONG a2, const WCHAR *a3)
{
  unsigned int v3; // edi
  const WCHAR *v4; // rbx
  const WCHAR *v7; // rcx
  wchar_t *v8; // rax
  int v9; // eax
  __int64 v10; // rax
  const WCHAR *v11; // rdx
  int v12; // eax
  int v13; // esi
  __int64 v14; // r8
  _BYTE v16[32]; // [rsp+30h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-238h] BYREF

  v3 = 0;
  v4 = a3;
  if ( *((_QWORD *)a3 + 3) < 8u )
    v7 = a3;
  else
    v7 = *(const WCHAR **)a3;
  *((_QWORD *)a3 + 2) = 0;
  *v7 = 0;
  if ( (unsigned int)std::wstring::compare(a1)
    && (v8 = (wchar_t *)std::wstring::wstring(v16, a1), v9 = ImpersonateUser(v8, a2), v3 = v9, v9 < 0) )
  {
    LogError(L"Failed to impersonate before get mdm temp folder. Error 0x%1!x!", (unsigned int)v9);
  }
  else if ( SHGetSpecialFolderPathW(0, pszPath, 28, 1) )
  {
    v10 = std::char_traits<unsigned short>::length(pszPath);
    std::wstring::assign(v4, pszPath, v10);
    std::wstring::append(v4, L"\\mdm");
    if ( *((_QWORD *)v4 + 3) < 8u )
      v11 = v4;
    else
      v11 = *(const WCHAR **)v4;
    v12 = SHCreateDirectoryExW(0, v11, 0);
    v13 = v12;
    if ( v12 && v12 != 183 )
    {
      if ( v12 > 0 )
        v14 = (unsigned __int16)v12 | 0x80070000;
      else
        v14 = (unsigned int)v12;
      if ( *((_QWORD *)v4 + 3) >= 8u )
        v4 = *(const WCHAR **)v4;
      LogError(L"Failed to create folder %1. Error 0x%2!x!", v4, v14);
      if ( v13 > 0 )
        return (unsigned __int16)v13 | 0x80070000;
      else
        return (unsigned int)v13;
    }
  }
  else
  {
    return (unsigned int)ResultFromLastError();
  }
  return v3;
}

```

## disassembly

```asm
0x14001668c  mov     [rsp+arg_18], rbx
0x140016691  push    rbp
0x140016692  push    rsi
0x140016693  push    rdi
0x140016694  sub     rsp, 270h
0x14001669b  mov     rax, cs:__security_cookie
0x1400166a2  xor     rax, rsp
0x1400166a5  mov     [rsp+288h+var_28], rax
0x1400166ad  xor     edi, edi
0x1400166af  mov     [rsp+288h+var_268], 0
0x1400166b4  cmp     qword ptr [r8+18h], 8
0x1400166b9  mov     rbx, r8
0x1400166bc  mov     ebp, edx
0x1400166be  mov     rsi, rcx
0x1400166c1  jb      short loc_1400166C8
0x1400166c3  mov     rcx, [r8]
0x1400166c6  jmp     short loc_1400166CB
0x1400166c8  mov     rcx, rbx
0x1400166cb  xor     eax, eax
0x1400166cd  mov     [r8+10h], rdi
0x1400166d1  mov     [rcx], ax
0x1400166d4  mov     rcx, rsi
0x1400166d7  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHPEBG@Z; std::wstring::compare(ushort const *)
0x1400166dc  test    eax, eax
0x1400166de  jz      short loc_140016715
0x1400166e0  mov     rdx, rsi
0x1400166e3  lea     rcx, [rsp+288h+var_258]
0x1400166e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400166ed  lea     r8, [rsp+288h+var_268]
0x1400166f2  mov     edx, ebp; SessionId
0x1400166f4  mov     rcx, rax; String2
0x1400166f7  call    ?ImpersonateUser@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KAEA_N@Z; ImpersonateUser(std::wstring,ulong,bool &)
0x1400166fc  mov     edi, eax
0x1400166fe  test    eax, eax
0x140016700  jns     short loc_140016715
0x140016702  mov     edx, eax
0x140016704  lea     rcx, aFailedToImpers; "Failed to impersonate before get mdm te"...
0x14001670b  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x140016710  jmp     loc_1400167C6
0x140016715  mov     r9d, 1; fCreate
0x14001671b  lea     rdx, [rsp+288h+pszPath]; pszPath
0x140016720  xor     ecx, ecx; hwnd
0x140016722  lea     r8d, [r9+1Bh]; csidl
0x140016726  call    cs:__imp_SHGetSpecialFolderPathW
0x14001672c  test    eax, eax
0x14001672e  jnz     short loc_14001673C
0x140016730  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140016735  mov     edi, eax
0x140016737  jmp     loc_1400167C6
0x14001673c  lea     rcx, [rsp+288h+pszPath]
0x140016741  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x140016746  mov     r8, rax
0x140016749  lea     rdx, [rsp+288h+pszPath]
0x14001674e  mov     rcx, rbx
0x140016751  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x140016756  lea     rdx, aMdm; "\\mdm"
0x14001675d  mov     rcx, rbx
0x140016760  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x140016765  cmp     qword ptr [rbx+18h], 8
0x14001676a  jb      short loc_140016771
0x14001676c  mov     rdx, [rbx]
0x14001676f  jmp     short loc_140016774
0x140016771  mov     rdx, rbx; pszPath
0x140016774  xor     r8d, r8d; psa
0x140016777  xor     ecx, ecx; hwnd
0x140016779  call    cs:__imp_SHCreateDirectoryExW
0x14001677f  mov     esi, eax
0x140016781  test    eax, eax
0x140016783  jz      short loc_1400167C6
0x140016785  cmp     eax, 0B7h
0x14001678a  jz      short loc_1400167C6
0x14001678c  movzx   edi, si
0x14001678f  mov     ebp, 80070000h
0x140016794  test    eax, eax
0x140016796  jg      short loc_14001679D
0x140016798  mov     r8d, eax
0x14001679b  jmp     short loc_1400167A3
0x14001679d  mov     r8d, edi
0x1400167a0  or      r8d, ebp
0x1400167a3  cmp     qword ptr [rbx+18h], 8
0x1400167a8  jb      short loc_1400167AD
0x1400167aa  mov     rbx, [rbx]
0x1400167ad  mov     rdx, rbx
0x1400167b0  lea     rcx, aFailedToCreate_1; "Failed to create folder %1. Error 0x%2!"...
0x1400167b7  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x1400167bc  test    esi, esi
0x1400167be  jg      short loc_1400167C4
0x1400167c0  mov     edi, esi
0x1400167c2  jmp     short loc_1400167C6
0x1400167c4  or      edi, ebp
0x1400167c6  cmp     [rsp+288h+var_268], 0
0x1400167cb  jz      short loc_1400167D3
0x1400167cd  call    cs:__imp_RevertToSelf
0x1400167d3  mov     eax, edi
0x1400167d5  mov     rcx, [rsp+288h+var_28]
0x1400167dd  xor     rcx, rsp; StackCookie
0x1400167e0  call    __security_check_cookie
0x1400167e5  mov     rbx, [rsp+288h+arg_18]
0x1400167ed  add     rsp, 270h
0x1400167f4  pop     rdi
0x1400167f5  pop     rsi
0x1400167f6  pop     rbp
0x1400167f7  retn
```
