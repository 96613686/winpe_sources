# VerifyFileIsInApprovedSystemList

- ea: `0x18008d4a4`
- end: `0x18008d784`
- name: `VerifyFileIsInApprovedSystemList`
- size: `736`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180050450`

## callees

- `0x1800263e4`
- `0x180045f74`
- `0x18004670c`
- `0x180058cdc`
- `0x18005ae90`
- `0x18005b31c`
- `0x18005ba40`
- `0x18005d02c`
- `0x18005d094`
- `0x18007638c`
- `0x18008d46c`
- `0x18008d4a4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008d724`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18008d724`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008d677`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18008d677`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18008d5e5`
- `api-ms-win-core-sysinfo-l1-2-0!GetNativeSystemInfo` at `0x18008d5e5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18008d666`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x18008d666`

## string_xrefs

- `0x18008d5a0`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008d61c`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008d688`: `onecoreuap\base\appmodel\execmodel\modern\activationmanager\extensionlib\activationextensions.cpp`
- `0x18008d524`: `backgroundtaskhost.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall VerifyFileIsInApprovedSystemList(LPCWCH lpString1, int a2)
{
  int v4; // edi
  int v5; // ebx
  int v6; // ebx
  int v7; // ebx
  int v8; // ebx
  UINT SystemDirectoryW; // eax
  const char *v10; // r9
  _QWORD *v11; // rcx
  int i; // ebx
  _SYSTEM_INFO *p_SystemInfo; // r8
  const char *v15; // [rsp+28h] [rbp-D8h]
  _QWORD v16[4]; // [rsp+38h] [rbp-C8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  if ( dword_1800D2808 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1800D2808);
    if ( dword_1800D2808 == -1 )
    {
      std::wstring::wstring(qword_1800D2810, L"wwahost.exe");
      std::wstring::wstring(qword_1800D2830, L"backgroundtaskhost.exe");
      std::wstring::wstring(qword_1800D2850, L"backgroundtransferhost.exe");
      atexit(VerifyFileIsInApprovedSystemList_::_2_::_dynamic_atexit_destructor_for__allowedExecutables__);
      Init_thread_footer(&dword_1800D2808);
    }
  }
  v4 = 43620;
  if ( a2 )
  {
    v5 = a2 - 5;
    if ( v5 )
    {
      v6 = v5 - 4;
      if ( v6 )
      {
        v7 = v6 - 2;
        if ( v7 )
        {
          if ( v7 != 1 )
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x69,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
              (const char *)0x8000FFFFLL,
              (int)"Unsupported package architecture",
              v15);
          v8 = 43620;
        }
        else
        {
          v8 = 1;
        }
      }
      else
      {
        v8 = 34404;
      }
    }
    else
    {
      v8 = 452;
    }
  }
  else
  {
    v8 = 332;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetNativeSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture )
  {
    switch ( SystemInfo.wProcessorArchitecture )
    {
      case 5u:
        v4 = 452;
        break;
      case 9u:
        v4 = 34404;
        break;
      case 0xCu:
        break;
      default:
        wil::details::in1diag3::Throw_HrMsg(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
          (const char *)0x8000FFFFLL,
          (int)"Unsupported package architecture",
          v15);
    }
  }
  else
  {
    v4 = 332;
  }
  memset_0(Buffer, 0, 0x20Au);
  if ( v4 == v8 || v8 == 1 )
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x105u);
  else
    SystemDirectoryW = GetSystemWow64Directory2W(Buffer, 261, (unsigned __int16)v8);
  if ( !SystemDirectoryW )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\extensionlib\\activationextensions.cpp",
      v10);
  std::wstring::wstring(v16, Buffer);
  v11 = v16;
  if ( v16[3] > 7u )
    v11 = (_QWORD *)v16[0];
  if ( *((_WORD *)v11 + v16[2] - 1) != 92 )
    std::wstring::append(v16, L"\\");
  for ( i = 0; (unsigned __int64)i < 3; ++i )
  {
    std::operator+<unsigned short>(&SystemInfo, v16, &qword_1800D2810[4 * i]);
    p_SystemInfo = &SystemInfo;
    if ( SystemInfo.dwActiveProcessorMask > 7 )
      p_SystemInfo = *(_SYSTEM_INFO **)&SystemInfo.dwOemId;
    if ( CompareStringOrdinal(lpString1, -1, (LPCWCH)p_SystemInfo, -1, 1) == 2 )
    {
      std::wstring::_Tidy_deallocate(&SystemInfo);
      std::wstring::_Tidy_deallocate(v16);
      return 1;
    }
    std::wstring::_Tidy_deallocate(&SystemInfo);
  }
  std::wstring::_Tidy_deallocate(v16);
  return 0;
}

```

## disassembly

```asm
0x18008d4a4  mov     [rsp-8+arg_8], rbx
0x18008d4a9  mov     [rsp-8+arg_10], rsi
0x18008d4ae  push    rbp
0x18008d4af  push    rdi
0x18008d4b0  push    r15
0x18008d4b2  lea     rbp, [rsp-1B0h]
0x18008d4ba  sub     rsp, 2B0h
0x18008d4c1  mov     rax, cs:__security_cookie
0x18008d4c8  xor     rax, rsp
0x18008d4cb  mov     [rbp+1C0h+var_20], rax
0x18008d4d2  mov     ebx, edx
0x18008d4d4  mov     rsi, rcx
0x18008d4d7  mov     r8d, cs:_tls_index
0x18008d4de  mov     rax, gs:58h
0x18008d4e7  mov     ecx, 4
0x18008d4ec  mov     rax, [rax+r8*8]
0x18008d4f0  mov     eax, [rcx+rax]
0x18008d4f3  cmp     cs:dword_1800D2808, eax
0x18008d4f9  jle     short loc_18008D564
0x18008d4fb  lea     rcx, dword_1800D2808
0x18008d502  call    _Init_thread_header
0x18008d507  cmp     cs:dword_1800D2808, 0FFFFFFFFh
0x18008d50e  jnz     short loc_18008D564
0x18008d510  lea     rdx, aWwahostExe; "wwahost.exe"
0x18008d517  lea     rcx, qword_1800D2810
0x18008d51e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d523  nop
0x18008d524  lea     rdx, aBackgroundtask; "backgroundtaskhost.exe"
0x18008d52b  lea     rcx, qword_1800D2830
0x18008d532  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d537  nop
0x18008d538  lea     rdx, aBackgroundtran; "backgroundtransferhost.exe"
0x18008d53f  lea     rcx, qword_1800D2850
0x18008d546  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d54b  nop
0x18008d54c  lea     rcx, _VerifyFileIsInApprovedSystemList____2____dynamic_atexit_destructor_for__allowedExecutables__; void (__cdecl *)()
0x18008d553  call    atexit
0x18008d558  lea     rcx, dword_1800D2808
0x18008d55f  call    _Init_thread_footer
0x18008d564  mov     edi, 0AA64h
0x18008d569  mov     r15d, 14Ch
0x18008d56f  test    ebx, ebx
0x18008d571  jz      short loc_18008D5CB
0x18008d573  sub     ebx, 5
0x18008d576  jz      short loc_18008D5C4
0x18008d578  sub     ebx, 4
0x18008d57b  jz      short loc_18008D5BD
0x18008d57d  sub     ebx, 2
0x18008d580  jz      short loc_18008D5B6
0x18008d582  cmp     ebx, 1
0x18008d585  jz      short loc_18008D5B2
0x18008d587  mov     rcx, [rbp+1C8h]; this
0x18008d58e  lea     rax, aUnsupportedPac; "Unsupported package architecture"
0x18008d595  mov     qword ptr [rsp+2C0h+bIgnoreCase], rax; int
0x18008d59a  mov     r9d, 8000FFFFh; char *
0x18008d5a0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008d5a7  mov     edx, 69h ; 'i'; void *
0x18008d5ac  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008d5b2  mov     ebx, edi
0x18008d5b4  jmp     short loc_18008D5CE
0x18008d5b6  mov     ebx, 1
0x18008d5bb  jmp     short loc_18008D5CE
0x18008d5bd  mov     ebx, 8664h
0x18008d5c2  jmp     short loc_18008D5CE
0x18008d5c4  mov     ebx, 1C4h
0x18008d5c9  jmp     short loc_18008D5CE
0x18008d5cb  mov     ebx, r15d
0x18008d5ce  xorps   xmm0, xmm0
0x18008d5d1  movups  xmmword ptr [rsp+2C0h+SystemInfo], xmm0
0x18008d5d6  movups  xmmword ptr [rsp+2C0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18008d5db  movups  xmmword ptr [rsp+2C0h+SystemInfo.dwNumberOfProcessors], xmm0
0x18008d5e0  lea     rcx, [rsp+2C0h+SystemInfo]; lpSystemInfo
0x18008d5e5  call    cs:__imp_GetNativeSystemInfo
0x18008d5eb  movzx   eax, word ptr [rsp+2C0h+SystemInfo]
0x18008d5f0  test    eax, eax
0x18008d5f2  jz      short loc_18008D63C
0x18008d5f4  cmp     eax, 5
0x18008d5f7  jz      short loc_18008D635
0x18008d5f9  cmp     eax, 9
0x18008d5fc  jz      short loc_18008D62E
0x18008d5fe  cmp     eax, 0Ch
0x18008d601  jz      short loc_18008D63F
0x18008d603  mov     rcx, [rbp+1C8h]; this
0x18008d60a  lea     rax, aUnsupportedPac; "Unsupported package architecture"
0x18008d611  mov     qword ptr [rsp+2C0h+bIgnoreCase], rax; int
0x18008d616  mov     r9d, 8000FFFFh; char *
0x18008d61c  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008d623  mov     edx, 7Dh ; '}'; void *
0x18008d628  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008d62e  mov     edi, 8664h
0x18008d633  jmp     short loc_18008D63F
0x18008d635  mov     edi, 1C4h
0x18008d63a  jmp     short loc_18008D63F
0x18008d63c  mov     edi, r15d
0x18008d63f  xor     edx, edx; Val
0x18008d641  mov     r8d, 20Ah; Size
0x18008d647  lea     rcx, [rbp+1C0h+Buffer]; void *
0x18008d64b  call    memset_0
0x18008d650  cmp     edi, ebx
0x18008d652  jz      short loc_18008D66E
0x18008d654  cmp     ebx, 1
0x18008d657  jz      short loc_18008D66E
0x18008d659  movzx   r8d, bx
0x18008d65d  mov     edx, 105h
0x18008d662  lea     rcx, [rbp+1C0h+Buffer]
0x18008d666  call    cs:__imp_GetSystemWow64Directory2W
0x18008d66c  jmp     short loc_18008D67D
0x18008d66e  mov     edx, 105h; uSize
0x18008d673  lea     rcx, [rbp+1C0h+Buffer]; lpBuffer
0x18008d677  call    cs:__imp_GetSystemDirectoryW
0x18008d67d  mov     rcx, [rbp+1C8h]; this
0x18008d684  test    eax, eax
0x18008d686  jnz     short loc_18008D69A
0x18008d688  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008d68f  mov     edx, 93h; void *
0x18008d694  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008d69a  lea     rdx, [rbp+1C0h+Buffer]
0x18008d69e  lea     rcx, [rsp+2C0h+var_288]
0x18008d6a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008d6a8  nop
0x18008d6a9  lea     rcx, [rsp+2C0h+var_288]
0x18008d6ae  cmp     [rsp+2C0h+var_270], 7
0x18008d6b4  cmova   rcx, [rsp+2C0h+var_288]
0x18008d6ba  mov     rax, [rsp+2C0h+var_278]
0x18008d6bf  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x18008d6c5  jz      short loc_18008D6D8
0x18008d6c7  lea     rdx, asc_1800AC0E4; "\\"
0x18008d6ce  lea     rcx, [rsp+2C0h+var_288]
0x18008d6d3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18008d6d8  xor     ebx, ebx
0x18008d6da  or      edi, 0FFFFFFFFh
0x18008d6dd  lea     r15, qword_1800D2810
0x18008d6e4  movsxd  r8, ebx
0x18008d6e7  cmp     r8, 3
0x18008d6eb  jnb     short loc_18008D751
0x18008d6ed  shl     r8, 5
0x18008d6f1  add     r8, r15
0x18008d6f4  lea     rdx, [rsp+2C0h+var_288]
0x18008d6f9  lea     rcx, [rsp+2C0h+SystemInfo]
0x18008d6fe  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x18008d703  lea     r8, [rsp+2C0h+SystemInfo]
0x18008d708  cmp     [rsp+2C0h+SystemInfo.dwActiveProcessorMask], 7
0x18008d70e  cmova   r8, qword ptr [rsp+2C0h+SystemInfo]; lpString2
0x18008d714  mov     [rsp+2C0h+bIgnoreCase], 1; bIgnoreCase
0x18008d71c  mov     r9d, edi; cchCount2
0x18008d71f  mov     edx, edi; cchCount1
0x18008d721  mov     rcx, rsi; lpString1
0x18008d724  call    cs:__imp_CompareStringOrdinal
0x18008d72a  lea     rcx, [rsp+2C0h+SystemInfo]
0x18008d72f  cmp     eax, 2
0x18008d732  jz      short loc_18008D73D
0x18008d734  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d739  inc     ebx
0x18008d73b  jmp     short loc_18008D6E4
0x18008d73d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d742  nop
0x18008d743  lea     rcx, [rsp+2C0h+var_288]
0x18008d748  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d74d  mov     al, 1
0x18008d74f  jmp     short loc_18008D75D
0x18008d751  lea     rcx, [rsp+2C0h+var_288]
0x18008d756  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008d75b  xor     al, al
0x18008d75d  mov     rcx, [rbp+1C0h+var_20]
0x18008d764  xor     rcx, rsp; StackCookie
0x18008d767  call    __security_check_cookie
0x18008d76c  lea     r11, [rsp+2C0h+var_10]
0x18008d774  mov     rbx, [r11+28h]
0x18008d778  mov     rsi, [r11+30h]
0x18008d77c  mov     rsp, r11
0x18008d77f  pop     r15
0x18008d781  pop     rdi
0x18008d782  pop     rbp
0x18008d783  retn
```
