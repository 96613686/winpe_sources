# ReadSSPAppMapFromRegistry(ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,bool>>> &)

- ea: `0x18007ab40`
- end: `0x18007adaa`
- name: `?ReadSSPAppMapFromRegistry@@YAJPEBGAEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a064`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000ec54`
- `0x18000ec94`
- `0x18001e610`
- `0x180028b64`
- `0x18003af88`
- `0x18007ab40`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18007ad7e`
- `ADVAPI32!RegCloseKey` at `0x18007ad7e`
- `ADVAPI32!RegEnumKeyExW` at `0x18007acbb`
- `ADVAPI32!RegEnumKeyExW` at `0x18007acbb`
- `ADVAPI32!RegOpenKeyExW` at `0x18007abec`
- `ADVAPI32!RegOpenKeyExW` at `0x18007abec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall ReadSSPAppMapFromRegistry(LPCWSTR lpSubKey, __int64 a2)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // ebx
  unsigned int v6; // edi
  unsigned int v7; // eax
  DWORD i; // edi
  LSTATUS v9; // eax
  unsigned int v10; // edi
  unsigned int v11; // eax
  DWORD cchName; // [rsp+44h] [rbp-264h] BYREF
  DWORD v14; // [rsp+48h] [rbp-260h]
  HKEY hKey[2]; // [rsp+50h] [rbp-258h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp-248h] BYREF
  WCHAR Name[260]; // [rsp+80h] [rbp-228h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  cchName = 256;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      WPP_9a9b29d69df23d7c330004de722d1721_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>,0>>::clear(a2);
  v5 = RegOpenKeyExW(HKEY_CURRENT_USER, lpSubKey, 0, 0x20019u, hKey);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      else
        v6 = v5;
      v7 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v7, v6);
    }
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    goto LABEL_32;
  }
  v14 = 0;
  v5 = 0;
  for ( i = 0; ; ++i )
  {
    v14 = i;
    if ( v5 == 259 )
    {
      v5 = 0;
      goto LABEL_32;
    }
    cchName = 256;
    v9 = RegEnumKeyExW(hKey[0], i, Name, &cchName, 0, 0, 0, 0);
    v5 = v9;
    if ( v9 )
      break;
    std::wstring::wstring(v16, Name);
    *(_BYTE *)std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::operator[](
                a2,
                v16) = 1;
    std::wstring::~wstring(v16);
LABEL_31:
    ;
  }
  if ( v9 == 259 )
    goto LABEL_31;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids, v11, v10);
  }
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_32:
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18007ab40  mov     rax, rsp
0x18007ab43  push    rsi
0x18007ab44  push    rdi
0x18007ab45  push    r14
0x18007ab47  sub     rsp, 290h
0x18007ab4e  mov     [rsp+2A8h+var_250], 0FFFFFFFFFFFFFFFEh
0x18007ab57  mov     [rax+18h], rbx
0x18007ab5b  mov     rax, cs:__security_cookie
0x18007ab62  xor     rax, rsp
0x18007ab65  mov     [rsp+2A8h+var_20], rax
0x18007ab6d  mov     rsi, rdx
0x18007ab70  mov     rbx, rcx
0x18007ab73  mov     [rsp+2A8h+hKey], 0
0x18007ab7c  mov     [rsp+2A8h+cchName], 100h
0x18007ab84  lea     r14, WPP_GLOBAL_Control
0x18007ab8b  mov     rax, cs:WPP_GLOBAL_Control
0x18007ab92  cmp     rax, r14
0x18007ab95  jz      short loc_18007ABC7
0x18007ab97  test    byte ptr [rax+1Ch], 1
0x18007ab9b  jz      short loc_18007ABC7
0x18007ab9d  cmp     byte ptr [rax+19h], 4
0x18007aba1  jb      short loc_18007ABC7
0x18007aba3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007aba8  mov     edx, 19h
0x18007abad  mov     r9d, eax
0x18007abb0  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007abb7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007abbe  mov     rcx, [rcx+10h]
0x18007abc2  call    WPP_SF_D
0x18007abc7  mov     rcx, rsi
0x18007abca  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>,0>>::clear(void)
0x18007abcf  lea     rax, [rsp+2A8h+hKey]
0x18007abd4  mov     [rsp+2A8h+phkResult], rax; phkResult
0x18007abd9  mov     r9d, 20019h; samDesired
0x18007abdf  xor     r8d, r8d; ulOptions
0x18007abe2  mov     rdx, rbx; lpSubKey
0x18007abe5  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007abec  call    cs:__imp_RegOpenKeyExW
0x18007abf2  mov     ebx, eax
0x18007abf4  test    eax, eax
0x18007abf6  jz      short loc_18007AC5F
0x18007abf8  mov     rax, cs:WPP_GLOBAL_Control
0x18007abff  cmp     rax, r14
0x18007ac02  jz      short loc_18007AC49
0x18007ac04  test    byte ptr [rax+1Ch], 8
0x18007ac08  jz      short loc_18007AC49
0x18007ac0a  cmp     byte ptr [rax+19h], 2
0x18007ac0e  jb      short loc_18007AC49
0x18007ac10  test    ebx, ebx
0x18007ac12  jg      short loc_18007AC18
0x18007ac14  mov     edi, ebx
0x18007ac16  jmp     short loc_18007AC21
0x18007ac18  movzx   edi, bx
0x18007ac1b  or      edi, 80070000h
0x18007ac21  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ac26  mov     edx, 1Ah
0x18007ac2b  mov     dword ptr [rsp+2A8h+phkResult], edi
0x18007ac2f  mov     r9d, eax
0x18007ac32  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007ac39  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ac40  mov     rcx, [rcx+10h]
0x18007ac44  call    WPP_SF_Dd
0x18007ac49  test    ebx, ebx
0x18007ac4b  jle     short loc_18007AC56
0x18007ac4d  movzx   ebx, bx
0x18007ac50  or      ebx, 80070000h
0x18007ac56  mov     [rsp+2A8h+var_268], ebx
0x18007ac5a  jmp     loc_18007AD74
0x18007ac5f  mov     [rsp+2A8h+var_260], 0
0x18007ac67  xor     ebx, ebx
0x18007ac69  xor     edi, edi
0x18007ac6b  mov     [rsp+2A8h+var_260], edi
0x18007ac6f  cmp     ebx, 103h
0x18007ac75  jz      loc_18007AD6A
0x18007ac7b  mov     [rsp+2A8h+cchName], 100h
0x18007ac83  mov     [rsp+2A8h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18007ac8c  mov     [rsp+2A8h+lpcchClass], 0; lpcchClass
0x18007ac95  mov     [rsp+2A8h+lpClass], 0; lpClass
0x18007ac9e  mov     [rsp+2A8h+phkResult], 0; lpReserved
0x18007aca7  lea     r9, [rsp+2A8h+cchName]; lpcchName
0x18007acac  lea     r8, [rsp+2A8h+Name]; lpName
0x18007acb4  mov     edx, edi; dwIndex
0x18007acb6  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18007acbb  call    cs:__imp_RegEnumKeyExW
0x18007acc1  mov     ebx, eax
0x18007acc3  test    eax, eax
0x18007acc5  jz      short loc_18007AD36
0x18007acc7  cmp     eax, 103h
0x18007accc  jz      loc_18007AD63
0x18007acd2  mov     rax, cs:WPP_GLOBAL_Control
0x18007acd9  cmp     rax, r14
0x18007acdc  jz      short loc_18007AD23
0x18007acde  test    byte ptr [rax+1Ch], 8
0x18007ace2  jz      short loc_18007AD23
0x18007ace4  cmp     byte ptr [rax+19h], 2
0x18007ace8  jb      short loc_18007AD23
0x18007acea  test    ebx, ebx
0x18007acec  jg      short loc_18007ACF2
0x18007acee  mov     edi, ebx
0x18007acf0  jmp     short loc_18007ACFB
0x18007acf2  movzx   edi, bx
0x18007acf5  or      edi, 80070000h
0x18007acfb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18007ad00  mov     edx, 1Bh
0x18007ad05  mov     dword ptr [rsp+2A8h+phkResult], edi
0x18007ad09  mov     r9d, eax
0x18007ad0c  lea     r8, WPP_9a9b29d69df23d7c330004de722d1721_Traceguids
0x18007ad13  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ad1a  mov     rcx, [rcx+10h]
0x18007ad1e  call    WPP_SF_Dd
0x18007ad23  test    ebx, ebx
0x18007ad25  jle     short loc_18007AD30
0x18007ad27  movzx   ebx, bx
0x18007ad2a  or      ebx, 80070000h
0x18007ad30  mov     [rsp+2A8h+var_268], ebx
0x18007ad34  jmp     short loc_18007AD74
0x18007ad36  lea     rdx, [rsp+2A8h+Name]
0x18007ad3e  lea     rcx, [rsp+2A8h+var_248]
0x18007ad43  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18007ad48  nop
0x18007ad49  lea     rdx, [rsp+2A8h+var_248]
0x18007ad4e  mov     rcx, rsi
0x18007ad51  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NUKeyCompareLessIgnoreCase@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@2@@std@@QEAAAEA_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,bool,KeyCompareLessIgnoreCase,std::allocator<std::pair<std::wstring const,bool>>>::operator[](std::wstring &&)
0x18007ad56  mov     byte ptr [rax], 1
0x18007ad59  lea     rcx, [rsp+2A8h+var_248]; void *
0x18007ad5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007ad63  inc     edi
0x18007ad65  jmp     loc_18007AC6B
0x18007ad6a  xor     ebx, ebx
0x18007ad6c  jmp     short loc_18007AD74
0x18007ad6e  jmp     short $+2
0x18007ad70  mov     ebx, [rsp+2A8h+var_268]
0x18007ad74  mov     rcx, [rsp+2A8h+hKey]; hKey
0x18007ad79  test    rcx, rcx
0x18007ad7c  jz      short loc_18007AD84
0x18007ad7e  call    cs:__imp_RegCloseKey
0x18007ad84  mov     eax, ebx
0x18007ad86  mov     rcx, [rsp+2A8h+var_20]
0x18007ad8e  xor     rcx, rsp; StackCookie
0x18007ad91  call    __security_check_cookie
0x18007ad96  mov     rbx, [rsp+2A8h+arg_10]
0x18007ad9e  add     rsp, 290h
0x18007ada5  pop     r14
0x18007ada7  pop     rdi
0x18007ada8  pop     rsi
0x18007ada9  retn
```
