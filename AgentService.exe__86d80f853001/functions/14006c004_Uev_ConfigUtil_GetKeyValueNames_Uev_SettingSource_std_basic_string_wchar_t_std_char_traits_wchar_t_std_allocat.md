# Uev::ConfigUtil::GetKeyValueNames(Uev::SettingSource,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,std::list<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> &)

- ea: `0x14006c004`
- end: `0x14006c215`
- name: `?GetKeyValueNames@ConfigUtil@Uev@@AEAAJW4SettingSource@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@5@@Z`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x14006dc80`

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
- `0x14006c004`
- `0x14009b010`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14006c0a9`
- `ADVAPI32!RegOpenKeyExW` at `0x14006c0a9`
- `ADVAPI32!RegEnumValueW` at `0x14006c0f5`
- `ADVAPI32!RegEnumValueW` at `0x14006c0f5`

## string_xrefs

- `0x14006c1b7`: `Attempting to assign an already-valid handle.`
- `0x14006c1e6`: `Attempting to use an invalid handle.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::ConfigUtil::GetKeyValueNames(__int64 *a1, int a2, const WCHAR *a3, __int64 a4, __int64 a5)
{
  WCHAR *v8; // rsi
  __int64 v9; // rax
  HKEY *v10; // rax
  unsigned int v11; // ebx
  DWORD v12; // edi
  LSTATUS v13; // eax
  unsigned __int64 v14; // r8
  DWORD Type; // [rsp+40h] [rbp-61h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-59h] BYREF
  DWORD cchValueName; // [rsp+50h] [rbp-51h] BYREF
  WCHAR *v19; // [rsp+58h] [rbp-49h]
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-41h] BYREF
  __int128 v21; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v22; // [rsp+B0h] [rbp+Fh]
  __int64 v23; // [rsp+B8h] [rbp+17h]

  hKey = 0;
  std::list<std::wstring>::clear(a5);
  v8 = (WCHAR *)operator new[](0x8000u);
  v19 = v8;
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
      cchValueName = 0x4000;
      Type = 0;
      if ( !hKey )
      {
        std::wstring::wstring(&v21, L"Attempting to use an invalid handle.");
        Uev::SmartHandleException::SmartHandleException(pExceptionObject, &v21);
        throw (Uev::SmartHandleException *)pExceptionObject;
      }
      v13 = RegEnumValueW(hKey, v12, v8, &cchValueName, 0, &Type, 0, 0);
      v11 = v13;
      if ( v13 )
        break;
      if ( Type == 1 )
      {
        v21 = 0;
        v22 = 0;
        v23 = 0;
        v14 = -1;
        do
          ++v14;
        while ( v8[v14] );
        std::wstring::_Construct<1,wchar_t *>(&v21, v8, v14);
        std::list<std::wstring>::push_back(a5, &v21);
        std::wstring::_Tidy_deallocate(&v21);
      }
      if ( ++v12 >= 0x1000 )
        goto LABEL_15;
    }
    if ( v13 == 259 )
    {
      v11 = 0;
      if ( !*(_QWORD *)(a5 + 8) )
        v11 = 2;
    }
    else
    {
      std::list<std::wstring>::clear(a5);
    }
  }
LABEL_15:
  operator delete(v8);
  Uev::SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&void Uev::RegCloseKeyWrapper(HKEY__ *),0>(&hKey);
  return v11;
}

```

## disassembly

```asm
0x14006c004  mov     [rsp-8+arg_8], rbx
0x14006c009  mov     [rsp-8+arg_18], rsi
0x14006c00e  push    rbp
0x14006c00f  push    rdi
0x14006c010  push    r12
0x14006c012  push    r14
0x14006c014  push    r15
0x14006c016  lea     rbp, [rsp-2Fh]
0x14006c01b  sub     rsp, 0D0h
0x14006c022  mov     rax, cs:__security_cookie
0x14006c029  xor     rax, rsp
0x14006c02c  mov     [rbp+4Fh+var_30], rax
0x14006c030  mov     rbx, r8
0x14006c033  mov     r15d, edx
0x14006c036  mov     rdi, rcx
0x14006c039  mov     r14, [rbp+4Fh+arg_20]
0x14006c03d  xor     r12d, r12d
0x14006c040  mov     [rbp+4Fh+hKey], r12
0x14006c044  mov     rcx, r14
0x14006c047  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x14006c04c  mov     ecx, 8000h; unsigned __int64
0x14006c051  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14006c056  mov     rsi, rax
0x14006c059  mov     [rbp+4Fh+var_98], rax
0x14006c05d  cmp     [rbp+4Fh+hKey], r12
0x14006c061  jnz     loc_14006C1B7
0x14006c067  cmp     qword ptr [rbx+18h], 7
0x14006c06c  jbe     short loc_14006C071
0x14006c06e  mov     rbx, [rbx]
0x14006c071  lea     eax, [r15-1]
0x14006c075  mov     rcx, rdi
0x14006c078  test    eax, 0FFFFFFFDh
0x14006c07d  mov     rax, [rdi]
0x14006c080  jz      short loc_14006C088
0x14006c082  mov     rax, [rax+28h]
0x14006c086  jmp     short loc_14006C08C
0x14006c088  mov     rax, [rax+20h]
0x14006c08c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c091  lea     rcx, [rbp+4Fh+hKey]
0x14006c095  mov     [rsp+0F0h+phkResult], rcx; phkResult
0x14006c09a  mov     r9d, 20119h; samDesired
0x14006c0a0  xor     r8d, r8d; ulOptions
0x14006c0a3  mov     rdx, rbx; lpSubKey
0x14006c0a6  mov     rcx, [rax]; hKey
0x14006c0a9  call    cs:__imp_RegOpenKeyExW
0x14006c0af  mov     ebx, eax
0x14006c0b1  test    eax, eax
0x14006c0b3  jnz     loc_14006C159
0x14006c0b9  mov     edi, r12d
0x14006c0bc  mov     [rbp+4Fh+cchValueName], 4000h
0x14006c0c3  mov     [rbp+4Fh+Type], r12d
0x14006c0c7  mov     rcx, [rbp+4Fh+hKey]; hKey
0x14006c0cb  test    rcx, rcx
0x14006c0ce  jz      loc_14006C1E6
0x14006c0d4  mov     [rsp+0F0h+lpcbData], r12; lpcbData
0x14006c0d9  mov     [rsp+0F0h+lpData], r12; lpData
0x14006c0de  lea     rax, [rbp+4Fh+Type]
0x14006c0e2  mov     [rsp+0F0h+lpType], rax; lpType
0x14006c0e7  mov     [rsp+0F0h+phkResult], r12; lpReserved
0x14006c0ec  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x14006c0f0  mov     r8, rsi; lpValueName
0x14006c0f3  mov     edx, edi; dwIndex
0x14006c0f5  call    cs:__imp_RegEnumValueW
0x14006c0fb  mov     ebx, eax
0x14006c0fd  test    eax, eax
0x14006c0ff  jnz     loc_14006C195
0x14006c105  cmp     [rbp+4Fh+Type], 1
0x14006c109  jnz     short loc_14006C14B
0x14006c10b  xorps   xmm0, xmm0
0x14006c10e  movups  [rbp+4Fh+var_50], xmm0
0x14006c112  mov     [rbp+4Fh+var_40], r12
0x14006c116  mov     [rbp+4Fh+var_38], r12
0x14006c11a  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006c11e  inc     r8
0x14006c121  cmp     [rsi+r8*2], r12w
0x14006c126  jnz     short loc_14006C11E
0x14006c128  mov     rdx, rsi
0x14006c12b  lea     rcx, [rbp+4Fh+var_50]
0x14006c12f  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x14006c134  nop
0x14006c135  lea     rdx, [rbp+4Fh+var_50]
0x14006c139  mov     rcx, r14
0x14006c13c  call    ?push_back@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@@Z; std::list<std::wstring>::push_back(std::wstring &&)
0x14006c141  nop
0x14006c142  lea     rcx, [rbp+4Fh+var_50]
0x14006c146  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x14006c14b  inc     edi
0x14006c14d  cmp     edi, 1000h
0x14006c153  jb      loc_14006C0BC
0x14006c159  mov     rcx, rsi; Block
0x14006c15c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14006c161  nop
0x14006c162  lea     rcx, [rbp+4Fh+hKey]
0x14006c166  call    ??1?$SmartHandle@PEAUHKEY__@@$1?RegCloseKeyWrapper@Uev@@YAXPEAU1@@Z$0A@@Uev@@QEAA@XZ; Uev::SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>::~SmartHandle<HKEY__ *,&Uev::RegCloseKeyWrapper(HKEY__ *),0>(void)
0x14006c16b  mov     eax, ebx
0x14006c16d  mov     rcx, [rbp+4Fh+var_30]
0x14006c171  xor     rcx, rsp; StackCookie
0x14006c174  call    __security_check_cookie
0x14006c179  lea     r11, [rsp+0F0h+var_20]
0x14006c181  mov     rbx, [r11+38h]
0x14006c185  mov     rsi, [r11+48h]
0x14006c189  mov     rsp, r11
0x14006c18c  pop     r15
0x14006c18e  pop     r14
0x14006c190  pop     r12
0x14006c192  pop     rdi
0x14006c193  pop     rbp
0x14006c194  retn
0x14006c195  cmp     eax, 103h
0x14006c19a  jnz     short loc_14006C1AD
0x14006c19c  mov     ebx, r12d
0x14006c19f  mov     eax, 2
0x14006c1a4  cmp     [r14+8], r12
0x14006c1a8  cmovbe  ebx, eax
0x14006c1ab  jmp     short loc_14006C159
0x14006c1ad  mov     rcx, r14
0x14006c1b0  call    ?clear@?$list@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAXXZ; std::list<std::wstring>::clear(void)
0x14006c1b5  jmp     short loc_14006C159
0x14006c1b7  lea     rdx, aAttemptingToAs; "Attempting to assign an already-valid h"...
0x14006c1be  lea     rcx, [rbp+4Fh+var_50]
0x14006c1c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006c1c7  nop
0x14006c1c8  lea     rdx, [rbp+4Fh+var_50]
0x14006c1cc  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14006c1d0  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006c1d5  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006c1dc  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14006c1e0  call    _CxxThrowException_0
0x14006c1e6  lea     rdx, aAttemptingToUs; "Attempting to use an invalid handle."
0x14006c1ed  lea     rcx, [rbp+4Fh+var_50]
0x14006c1f1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x14006c1f6  nop
0x14006c1f7  lea     rdx, [rbp+4Fh+var_50]
0x14006c1fb  lea     rcx, [rbp+4Fh+pExceptionObject]
0x14006c1ff  call    ??0SmartHandleException@Uev@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Uev::SmartHandleException::SmartHandleException(std::wstring const &)
0x14006c204  lea     rdx, _TI3?AVSmartHandleException@Uev@@; pThrowInfo
0x14006c20b  lea     rcx, [rbp+4Fh+pExceptionObject]; pExceptionObject
0x14006c20f  call    _CxxThrowException_0
```
