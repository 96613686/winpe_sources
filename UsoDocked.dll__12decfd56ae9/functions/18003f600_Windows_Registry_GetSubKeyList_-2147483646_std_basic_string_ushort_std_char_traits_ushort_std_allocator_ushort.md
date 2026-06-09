# Windows::Registry::GetSubKeyList<-2147483646>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003f600`
- end: `0x18003f858`
- name: `??$GetSubKeyList@$0?HPPPPPPO@@Registry@Windows@@QEAA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@0@Z`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180033110`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x180025cd0`
- `0x180027f2c`
- `0x18003f600`
- `0x180040128`
- `0x1800409bc`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f685`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003f685`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f6d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003f6d7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f753`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003f753`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7f8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f7f8`

## string_xrefs

- `0x18003f831`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`
- `0x18003f846`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Windows::Registry::GetSubKeyList<-2147483646>(__int64 a1, _QWORD *a2)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  DWORD v5; // edi
  WCHAR *v6; // rsi
  __m128i si128; // xmm6
  unsigned int v8; // eax
  __int64 v9; // r8
  _OWORD *v10; // rdx
  unsigned int phkResult; // [rsp+28h] [rbp-99h]
  unsigned int phkResulta; // [rsp+28h] [rbp-99h]
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-59h] BYREF
  DWORD cSubKeys; // [rsp+6Ch] [rbp-55h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-51h] BYREF
  int v17; // [rsp+78h] [rbp-49h]
  DWORD cchName; // [rsp+7Ch] [rbp-45h] BYREF
  LPWSTR lpName[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v20; // [rsp+90h] [rbp-31h]
  _QWORD *v21; // [rsp+98h] [rbp-29h]
  __int128 v22; // [rsp+A0h] [rbp-21h] BYREF
  __m128i v23; // [rsp+B0h] [rbp-11h]
  LPCWSTR lpSubKey[4]; // [rsp+C0h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  v21 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v17 = 1;
  (*(void (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)a1 + 88LL))(a1, lpSubKey);
  hKey = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v3 = lpSubKey[0];
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey) )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v4 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1FB,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
        (const char *)v4,
        phkResult);
    if ( cSubKeys )
    {
      ++cbMaxSubKeyLen;
      *(_OWORD *)lpName = 0;
      v20 = 0;
      std::vector<unsigned short>::_Construct_n<>(lpName, cbMaxSubKeyLen);
      v5 = 0;
      if ( cSubKeys )
      {
        v6 = lpName[0];
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        do
        {
          cchName = cbMaxSubKeyLen;
          v8 = RegEnumKeyExW(hKey, v5, v6, &cchName, 0, 0, 0, 0);
          if ( v8 == 259 )
            break;
          if ( v8 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x20C,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\registry.cpp",
              (const char *)v8,
              phkResulta);
          v22 = 0;
          v23 = 0;
          v9 = -1;
          do
            ++v9;
          while ( v6[v9] );
          std::wstring::_Construct<1,unsigned short const *>(&v22, v6, v9);
          v10 = (_OWORD *)a2[1];
          if ( v10 == (_OWORD *)a2[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(a2, v10, &v22);
          }
          else
          {
            *v10 = v22;
            v10[1] = v23;
            v23 = si128;
            LOWORD(v22) = 0;
            a2[1] += 32LL;
          }
          std::wstring::_Tidy_deallocate(&v22);
          ++v5;
        }
        while ( v5 < cSubKeys );
      }
      std::vector<unsigned short>::_Tidy(lpName);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::_Tidy_deallocate(lpSubKey);
  return a2;
}

```

## disassembly

```asm
0x18003f600  mov     rax, rsp
0x18003f603  push    rbp
0x18003f604  push    rbx
0x18003f605  push    rsi
0x18003f606  push    rdi
0x18003f607  push    r14
0x18003f609  lea     rbp, [rax-5Fh]
0x18003f60d  sub     rsp, 0F0h
0x18003f614  movaps  xmmword ptr [rax-38h], xmm6
0x18003f618  mov     rax, cs:__security_cookie
0x18003f61f  xor     rax, rsp
0x18003f622  mov     qword ptr [rbp+57h+var_38], rax
0x18003f626  mov     rbx, rdx
0x18003f629  mov     [rbp+57h+var_80], rdx
0x18003f62d  mov     [rbp+57h+var_A0], 1
0x18003f634  xor     r14d, r14d
0x18003f637  mov     [rdx], r14
0x18003f63a  mov     [rdx+8], r14
0x18003f63e  mov     [rdx+10h], r14
0x18003f642  mov     [rbp+57h+var_A0], 1
0x18003f649  mov     rax, [rcx]
0x18003f64c  lea     rdx, [rbp+57h+lpSubKey]
0x18003f650  mov     rax, [rax+58h]
0x18003f654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f659  nop
0x18003f65a  mov     [rbp+57h+hKey], r14
0x18003f65e  lea     rdx, [rbp+57h+lpSubKey]
0x18003f662  cmp     [rbp+57h+var_40], 7
0x18003f667  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003f66c  lea     rax, [rbp+57h+hKey]
0x18003f670  mov     [rsp+110h+phkResult], rax; phkResult
0x18003f675  mov     r9d, 20019h; samDesired
0x18003f67b  xor     r8d, r8d; ulOptions
0x18003f67e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003f685  call    cs:__imp_RegOpenKeyExW
0x18003f68b  test    eax, eax
0x18003f68d  jnz     loc_18003F7EF
0x18003f693  mov     [rbp+57h+cSubKeys], r14d
0x18003f697  mov     [rbp+57h+cbMaxSubKeyLen], r14d
0x18003f69b  mov     [rsp+58h], r14; lpftLastWriteTime
0x18003f6a0  mov     [rsp+110h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18003f6a5  mov     [rsp+110h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18003f6aa  mov     [rsp+110h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18003f6af  mov     [rsp+110h+lpcValues], r14; lpcValues
0x18003f6b4  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18003f6b9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18003f6bd  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18003f6c2  lea     rax, [rbp+57h+cSubKeys]
0x18003f6c6  mov     [rsp+110h+phkResult], rax; unsigned int
0x18003f6cb  xor     r9d, r9d; lpReserved
0x18003f6ce  xor     r8d, r8d; lpcchClass
0x18003f6d1  xor     edx, edx; lpClass
0x18003f6d3  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f6d7  call    cs:__imp_RegQueryInfoKeyW
0x18003f6dd  mov     rcx, [rbp+5Fh]; this
0x18003f6e1  test    eax, eax
0x18003f6e3  jnz     loc_18003F82E
0x18003f6e9  cmp     [rbp+57h+cSubKeys], r14d
0x18003f6ed  jbe     loc_18003F7EF
0x18003f6f3  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003f6f6  inc     eax
0x18003f6f8  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x18003f6fb  mov     edx, eax
0x18003f6fd  xorps   xmm0, xmm0
0x18003f700  movdqu  xmmword ptr [rbp+57h+lpName], xmm0
0x18003f705  mov     [rbp+57h+var_88], r14
0x18003f709  lea     rcx, [rbp+57h+lpName]
0x18003f70d  call    ??$_Construct_n@$$V@?$vector@GV?$allocator@G@std@@@std@@AEAAX_K@Z; std::vector<ushort>::_Construct_n<>(unsigned __int64)
0x18003f712  nop
0x18003f713  mov     edi, r14d
0x18003f716  cmp     [rbp+57h+cSubKeys], r14d
0x18003f71a  jbe     loc_18003F7E5
0x18003f720  mov     rsi, [rbp+57h+lpName]
0x18003f724  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18003f72c  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18003f72f  mov     [rbp+57h+cchName], eax
0x18003f732  mov     [rsp+110h+lpcValues], r14; lpftLastWriteTime
0x18003f737  mov     [rsp+110h+lpcbMaxClassLen], r14; lpcchClass
0x18003f73c  mov     [rsp+110h+lpcbMaxSubKeyLen], r14; lpClass
0x18003f741  mov     [rsp+110h+phkResult], r14; unsigned int
0x18003f746  lea     r9, [rbp+57h+cchName]; lpcchName
0x18003f74a  mov     r8, rsi; lpName
0x18003f74d  mov     edx, edi; dwIndex
0x18003f74f  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f753  call    cs:__imp_RegEnumKeyExW
0x18003f759  cmp     eax, 103h
0x18003f75e  jz      loc_18003F7E5
0x18003f764  mov     rcx, [rbp+5Fh]; this
0x18003f768  test    eax, eax
0x18003f76a  jnz     loc_18003F843
0x18003f770  xorps   xmm0, xmm0
0x18003f773  movups  [rbp+57h+var_78], xmm0
0x18003f777  xorps   xmm1, xmm1
0x18003f77a  movdqu  [rbp+57h+var_68], xmm1
0x18003f77f  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003f783  inc     r8
0x18003f786  cmp     [rsi+r8*2], r14w
0x18003f78b  jnz     short loc_18003F783
0x18003f78d  mov     rdx, rsi
0x18003f790  lea     rcx, [rbp+57h+var_78]
0x18003f794  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18003f799  nop
0x18003f79a  mov     rdx, [rbx+8]
0x18003f79e  cmp     rdx, [rbx+10h]
0x18003f7a2  jz      short loc_18003F7C4
0x18003f7a4  movups  xmm0, [rbp+57h+var_78]
0x18003f7a8  movups  xmmword ptr [rdx], xmm0
0x18003f7ab  movups  xmm1, [rbp+57h+var_68]
0x18003f7af  movups  xmmword ptr [rdx+10h], xmm1
0x18003f7b3  movdqu  [rbp+57h+var_68], xmm6
0x18003f7b8  mov     word ptr [rbp+57h+var_78], r14w
0x18003f7bd  add     qword ptr [rbx+8], 20h ; ' '
0x18003f7c2  jmp     short loc_18003F7D1
0x18003f7c4  lea     r8, [rbp+57h+var_78]
0x18003f7c8  mov     rcx, rbx
0x18003f7cb  call    ??$_Emplace_reallocate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18003f7d0  nop
0x18003f7d1  lea     rcx, [rbp+57h+var_78]
0x18003f7d5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f7da  inc     edi
0x18003f7dc  cmp     edi, [rbp+57h+cSubKeys]
0x18003f7df  jb      loc_18003F72C
0x18003f7e5  lea     rcx, [rbp+57h+lpName]
0x18003f7e9  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x18003f7ee  nop
0x18003f7ef  mov     rcx, [rbp+57h+hKey]; hKey
0x18003f7f3  test    rcx, rcx
0x18003f7f6  jz      short loc_18003F7FF
0x18003f7f8  call    cs:__imp_RegCloseKey
0x18003f7fe  nop
0x18003f7ff  lea     rcx, [rbp+57h+lpSubKey]
0x18003f803  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f808  nop
0x18003f809  mov     rax, rbx
0x18003f80c  mov     rcx, qword ptr [rbp+57h+var_38]
0x18003f810  xor     rcx, rsp; StackCookie
0x18003f813  call    __security_check_cookie
0x18003f818  movaps  xmm6, [rsp+110h+var_38+8]
0x18003f820  add     rsp, 0F0h
0x18003f827  pop     r14
0x18003f829  pop     rdi
0x18003f82a  pop     rsi
0x18003f82b  pop     rbx
0x18003f82c  pop     rbp
0x18003f82d  retn
0x18003f82e  mov     r9d, eax; char *
0x18003f831  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f838  mov     edx, 1FBh; void *
0x18003f83d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18003f843  mov     r9d, eax; char *
0x18003f846  lea     r8, aOnecoreEnduser_0; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f84d  mov     edx, 20Ch; void *
0x18003f852  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
