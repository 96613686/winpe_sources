# Uev::ConfigUtil::GetKeyNames(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x14006be0c`
- end: `0x14006bffd`
- name: `?GetKeyNames@ConfigUtil@Uev@@AEAAJW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@@Z`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14006c980`

## callees

- `0x140003e50`
- `0x140003f88`
- `0x140003fcc`
- `0x140004ab4`
- `0x14000ba60`
- `0x14000c2b8`
- `0x14000d1d8`
- `0x14000d260`
- `0x14000d5ac`
- `0x14003f454`
- `0x14003f4c8`
- `0x14006be0c`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006bea9`
- `ADVAPI32!RegOpenKeyExW` at `0x14006bea9`
- `ADVAPI32!RegEnumKeyExW` at `0x14006beed`
- `ADVAPI32!RegEnumKeyExW` at `0x14006beed`

## string_xrefs

- `0x14006bf9f`: `Attempting to assign an already-valid handle.`
- `0x14006bfce`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::ConfigUtil::GetKeyNames(__int64 *a1, int a2, const WCHAR *a3, __int64 a4)
{
  WCHAR *v8; // rsi
  __int64 v9; // rax
  HKEY *v10; // rax
  unsigned int v11; // ebx
  DWORD v12; // edi
  LSTATUS v13; // eax
  unsigned __int64 v14; // r8
  HKEY hKey; // [rsp+40h] [rbp-69h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-61h] BYREF
  WCHAR *v18; // [rsp+50h] [rbp-59h]
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-49h] BYREF
  __int128 v20; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+7h]
  __int64 v22; // [rsp+B8h] [rbp+Fh]

  hKey = 0;
  std::list<std::wstring>::clear(a4);
  v8 = (WCHAR *)operator new[](0x200u);
  v18 = v8;
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v9 = *a1;
  if ( ((a2 - 1) & 0xFFFFFFFD) != 0 )
    v10 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v9 + 40))(a1);
  else
    v10 = (HKEY *)(*(__int64 (__fastcall **)(__int64 *))(v9 + 32))(a1);
  v11 = RegOpenKeyExW(*v10, a3, 0, 0x20119u, &hKey);
  if ( !v11 )
  {
    v12 = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( !hKey )
      {
        std::wstring::wstring(&v20, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, &v20);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      v13 = RegEnumKeyExW(hKey, v12, v8, &cchName, 0, 0, 0, 0);
      v11 = v13;
      if ( v13 )
        break;
      v20 = 0;
      v21 = 0;
      v22 = 0;
      v14 = -1;
      do
        ++v14;
      while ( v8[v14] );
      std::wstring::_Construct<1,wchar_t *>(&v20, v8, v14);
      std::list<std::wstring>::push_back(a4, &v20);
      std::wstring::_Tidy_deallocate(&v20);
      if ( ++v12 >= 0x1000 )
        goto LABEL_13;
    }
    if ( v13 == 259 )
    {
      v11 = 0;
      if ( !*(_QWORD *)(a4 + 8) )
        v11 = 2;
    }
    else
    {
      std::list<std::wstring>::clear(a4);
    }
  }
LABEL_13:
  operator delete(v8);
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  return v11;
}

```

## disassembly

```asm
0x14006be0c  push    rbp
0x14006be0e  push    rbx
0x14006be0f  push    rsi
0x14006be10  push    rdi
0x14006be11  push    r12
0x14006be13  push    r14
0x14006be15  push    r15
0x14006be17  lea     rbp, [rsp-27h]
0x14006be1c  sub     rsp, 0D0h
0x14006be23  mov     rax, cs:__security_cookie
0x14006be2a  xor     rax, rsp
0x14006be2d  mov     [rbp+57h+var_40], rax
0x14006be31  mov     r14, r9
0x14006be34  mov     rbx, r8
0x14006be37  mov     r15d, edx
0x14006be3a  mov     rdi, rcx
0x14006be3d  xor     r12d, r12d
0x14006be40  mov     [rbp+57h+hKey], r12
0x14006be44  mov     rcx, r9
0x14006be47  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x14006be4c  mov     ecx, 200h; unsigned __int64
0x14006be51  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006be56  mov     rsi, rax
0x14006be59  mov     [rbp+57h+var_B0], rax
0x14006be5d  cmp     [rbp+57h+hKey], r12
0x14006be61  jnz     loc_14006BF9F
0x14006be67  cmp     qword ptr [rbx+18h], 7
0x14006be6c  jbe     short loc_14006BE71
0x14006be6e  mov     rbx, [rbx]
0x14006be71  lea     eax, [r15-1]
0x14006be75  mov     rcx, rdi
0x14006be78  test    eax, 0FFFFFFFDh
0x14006be7d  mov     rax, [rdi]
0x14006be80  jz      short loc_14006BE88
0x14006be82  mov     rax, [rax+28h]
0x14006be86  jmp     short loc_14006BE8C
0x14006be88  mov     rax, [rax+20h]
0x14006be8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006be91  lea     rcx, [rbp+57h+hKey]
0x14006be95  mov     [rsp+100h+phkResult], rcx; phkResult
0x14006be9a  mov     r9d, 20119h; samDesired
0x14006bea0  xor     r8d, r8d; ulOptions
0x14006bea3  mov     rdx, rbx; lpSubKey
0x14006bea6  mov     rcx, [rax]; hKey
0x14006bea9  call    cs:__imp_RegOpenKeyExW
0x14006beaf  mov     ebx, eax
0x14006beb1  test    eax, eax
0x14006beb3  jnz     loc_14006BF4B
0x14006beb9  mov     edi, r12d
0x14006bebc  mov     [rbp+57h+cchName], 100h
0x14006bec3  mov     rcx, [rbp+57h+hKey]; hKey
0x14006bec7  test    rcx, rcx
0x14006beca  jz      loc_14006BFCE
0x14006bed0  mov     [rsp+100h+lpftLastWriteTime], r12; lpftLastWriteTime
0x14006bed5  mov     [rsp+100h+lpcchClass], r12; lpcchClass
0x14006beda  mov     [rsp+100h+lpClass], r12; lpClass
0x14006bedf  mov     [rsp+100h+phkResult], r12; lpReserved
0x14006bee4  lea     r9, [rbp+57h+cchName]; lpcchName
0x14006bee8  mov     r8, rsi; lpName
0x14006beeb  mov     edx, edi; dwIndex
0x14006beed  call    cs:__imp_RegEnumKeyExW
0x14006bef3  mov     ebx, eax
0x14006bef5  test    eax, eax
0x14006bef7  jnz     loc_14006BF7D
0x14006befd  xorps   xmm0, xmm0
0x14006bf00  movups  [rbp+57h+var_60], xmm0
0x14006bf04  mov     [rbp+57h+var_50], r12
0x14006bf08  mov     [rbp+57h+var_48], r12
0x14006bf0c  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006bf10  inc     r8
0x14006bf13  cmp     [rsi+r8*2], r12w
0x14006bf18  jnz     short loc_14006BF10
0x14006bf1a  mov     rdx, rsi
0x14006bf1d  lea     rcx, [rbp+57h+var_60]
0x14006bf21  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14006bf26  nop
0x14006bf27  lea     rdx, [rbp+57h+var_60]
0x14006bf2b  mov     rcx, r14
0x14006bf2e  call    ?push_back@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x14006bf33  nop
0x14006bf34  lea     rcx, [rbp+57h+var_60]
0x14006bf38  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006bf3d  inc     edi
0x14006bf3f  cmp     edi, 1000h
0x14006bf45  jb      loc_14006BEBC
0x14006bf4b  mov     rcx, rsi; Block
0x14006bf4e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006bf53  nop
0x14006bf54  lea     rcx, [rbp+57h+hKey]
0x14006bf58  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006bf5d  mov     eax, ebx
0x14006bf5f  mov     rcx, [rbp+57h+var_40]
0x14006bf63  xor     rcx, rsp; StackCookie
0x14006bf66  call    __security_check_cookie
0x14006bf6b  add     rsp, 0D0h
0x14006bf72  pop     r15
0x14006bf74  pop     r14
0x14006bf76  pop     r12
0x14006bf78  pop     rdi
0x14006bf79  pop     rsi
0x14006bf7a  pop     rbx
0x14006bf7b  pop     rbp
0x14006bf7c  retn
0x14006bf7d  cmp     eax, 103h
0x14006bf82  jnz     short loc_14006BF95
0x14006bf84  mov     ebx, r12d
0x14006bf87  mov     eax, 2
0x14006bf8c  cmp     [r14+8], r12
0x14006bf90  cmovbe  ebx, eax
0x14006bf93  jmp     short loc_14006BF4B
0x14006bf95  mov     rcx, r14
0x14006bf98  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x14006bf9d  jmp     short loc_14006BF4B
0x14006bf9f  lea     rdx, aAttemptingToAs; "Attempting to assign an already-valid h"...
0x14006bfa6  lea     rcx, [rbp+57h+var_60]
0x14006bfaa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006bfaf  nop
0x14006bfb0  lea     rdx, [rbp+57h+var_60]
0x14006bfb4  lea     rcx, [rbp+57h+pExceptionObject]
0x14006bfb8  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006bfbd  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006bfc4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14006bfc8  call    _CxxThrowException_0
0x14006bfce  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006bfd5  lea     rcx, [rbp+57h+var_60]
0x14006bfd9  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006bfde  nop
0x14006bfdf  lea     rdx, [rbp+57h+var_60]
0x14006bfe3  lea     rcx, [rbp+57h+pExceptionObject]
0x14006bfe7  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006bfec  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006bff3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14006bff7  call    _CxxThrowException_0
```
