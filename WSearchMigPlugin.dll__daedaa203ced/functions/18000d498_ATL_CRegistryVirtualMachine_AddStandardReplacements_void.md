# ATL::CRegistryVirtualMachine::AddStandardReplacements(void)

- ea: `0x18000d498`
- end: `0x18000d705`
- name: `?AddStandardReplacements@CRegistryVirtualMachine@ATL@@QEAAJXZ`
- size: `621`
- prototype: `HRESULT __fastcall(ATL::CRegistryVirtualMachine *this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800129f0`

## callees

- `0x1800026f0`
- `0x180002bf0`
- `0x18000329c`
- `0x18000ab88`
- `0x18000b410`
- `0x18000d498`
- `0x180018010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d558`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000d558`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d522`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000d522`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000d4e0`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleFileNameW` at `0x18000d4e0`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000d61b`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000d61b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d64b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d64b`
- `SHELL32!SHGetFileInfoW` at `0x18000d689`
- `SHELL32!SHGetFileInfoW` at `0x18000d689`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall ATL::CRegistryVirtualMachine::AddStandardReplacements(ATL::CRegistryVirtualMachine *this)
{
  HMODULE v2; // rdi
  DWORD ModuleFileNameW; // eax
  HRESULT result; // eax
  WCHAR *v5; // r8
  int v6; // eax
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  int v9; // edi
  DWORD_PTR v10; // rax
  const wchar_t *v11; // r8
  LPOLESTR lpsz[2]; // [rsp+30h] [rbp-D0h] BYREF
  SHFILEINFOW psfi; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v14; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v15[526]; // [rsp+302h] [rbp+202h] BYREF
  WCHAR Filename[264]; // [rsp+510h] [rbp+410h] BYREF

  lpsz[1] = (LPOLESTR)-2LL;
  v2 = hModule;
  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return -2147024774;
  if ( !v2 || v2 == GetModuleHandleW(0) )
  {
    v14 = 34;
    v6 = _o_wcscpy_s(v15, 261, Filename);
    if ( v6 )
    {
      if ( v6 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v6 == 22 || v6 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v6 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&v15[2 * v7 - 2] );
    *(_WORD *)&v15[2 * (int)v7 - 2] = 34;
    v8 = 2LL * (int)v7 + 2;
    if ( v8 >= 0x20C )
      _report_rangecheckfailure();
    *(_WORD *)&v15[v8 - 2] = 0;
    v5 = (WCHAR *)&v14;
  }
  else
  {
    v5 = Filename;
  }
  result = (*(__int64 (__fastcall **)(ATL::CRegistryVirtualMachine *, const wchar_t *, WCHAR *))(*(_QWORD *)this + 24LL))(
             this,
             L"Module",
             v5);
  if ( result >= 0 )
  {
    result = (*(__int64 (__fastcall **)(ATL::CRegistryVirtualMachine *, const wchar_t *, WCHAR *))(*(_QWORD *)this + 24LL))(
               this,
               L"Module_Raw",
               Filename);
    if ( result >= 0 )
    {
      lpsz[0] = 0;
      result = StringFromCLSID(&ATL::CAtlModule::m_libid, lpsz);
      if ( result >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(ATL::CRegistryVirtualMachine *, const wchar_t *, LPOLESTR))(*(_QWORD *)this
                                                                                                  + 24LL))(
               this,
               L"MODULEGUID",
               lpsz[0]);
        CoTaskMemFree(lpsz[0]);
        if ( v9 >= 0 )
        {
          memset_0(&psfi, 0, sizeof(psfi));
          v10 = SHGetFileInfoW(Filename, 0, &psfi, 0x2B8u, 0x2000u);
          v11 = L"InprocServer32";
          if ( v10 )
            v11 = L"LocalServer32";
          result = (*(__int64 (__fastcall **)(ATL::CRegistryVirtualMachine *, const wchar_t *, const wchar_t *))(*(_QWORD *)this + 24LL))(
                     this,
                     L"MODULETYPE",
                     v11);
          if ( result >= 0 )
            return (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, ATL::CRegistryVirtualMachine *))(*(_QWORD *)ATL::_pAtlModule + 40LL))(
                     ATL::_pAtlModule,
                     this);
        }
        else
        {
          return v9;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d498  push    rbp
0x18000d49a  push    rbx
0x18000d49b  push    rsi
0x18000d49c  push    rdi
0x18000d49d  lea     rbp, [rsp-638h]
0x18000d4a5  sub     rsp, 738h
0x18000d4ac  mov     [rsp+750h+var_718], 0FFFFFFFFFFFFFFFEh
0x18000d4b5  mov     rax, cs:__security_cookie
0x18000d4bc  xor     rax, rsp
0x18000d4bf  mov     [rbp+650h+var_30], rax
0x18000d4c6  mov     rbx, rcx
0x18000d4c9  mov     rdi, cs:hModule
0x18000d4d0  mov     r8d, 104h; nSize
0x18000d4d6  lea     rdx, [rbp+650h+Filename]; lpFilename
0x18000d4dd  mov     rcx, rdi; hModule
0x18000d4e0  call    cs:__imp_GetModuleFileNameW
0x18000d4e6  xor     esi, esi
0x18000d4e8  test    eax, eax
0x18000d4ea  jnz     short loc_18000D50D
0x18000d4ec  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000d4f1  nop
0x18000d4f2  mov     rcx, [rbp+650h+var_30]
0x18000d4f9  xor     rcx, rsp; StackCookie
0x18000d4fc  call    __security_check_cookie
0x18000d501  add     rsp, 738h
0x18000d508  pop     rdi
0x18000d509  pop     rsi
0x18000d50a  pop     rbx
0x18000d50b  pop     rbp
0x18000d50c  retn
0x18000d50d  cmp     eax, 104h
0x18000d512  jnz     short loc_18000D51B
0x18000d514  mov     eax, 8007007Ah
0x18000d519  jmp     short loc_18000D4F2
0x18000d51b  test    rdi, rdi
0x18000d51e  jz      short loc_18000D539
0x18000d520  xor     ecx, ecx; lpModuleName
0x18000d522  call    cs:__imp_GetModuleHandleW
0x18000d528  cmp     rdi, rax
0x18000d52b  jz      short loc_18000D539
0x18000d52d  lea     r8, [rbp+650h+Filename]
0x18000d534  jmp     loc_18000D5C7
0x18000d539  mov     edi, 22h ; '"'
0x18000d53e  mov     [rbp+650h+var_450], di
0x18000d545  lea     r8, [rbp+650h+Filename]
0x18000d54c  mov     edx, 105h
0x18000d551  lea     rcx, [rbp+650h+var_44E]
0x18000d558  call    cs:__imp__o_wcscpy_s
0x18000d55e  test    eax, eax
0x18000d560  jz      short loc_18000D585
0x18000d562  cmp     eax, 0Ch
0x18000d565  jz      loc_18000D6DE
0x18000d56b  cmp     eax, 16h
0x18000d56e  jz      loc_18000D6FA
0x18000d574  cmp     eax, edi
0x18000d576  jz      loc_18000D6FA
0x18000d57c  cmp     eax, 50h ; 'P'
0x18000d57f  jnz     loc_18000D6EF
0x18000d585  lea     rcx, [rbp+650h+var_450]
0x18000d58c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d590  inc     rax
0x18000d593  cmp     [rcx+rax*2], si
0x18000d597  jnz     short loc_18000D590
0x18000d599  cdqe
0x18000d59b  mov     [rbp+rax*2+650h+var_450], di
0x18000d5a3  lea     rcx, ds:2[rax*2]
0x18000d5ab  cmp     rcx, 20Ch
0x18000d5b2  jnb     loc_18000D6E9
0x18000d5b8  mov     [rbp+rcx+650h+var_450], si
0x18000d5c0  lea     r8, [rbp+650h+var_450]
0x18000d5c7  mov     rax, [rbx]
0x18000d5ca  lea     rdx, aModule_0; "Module"
0x18000d5d1  mov     rcx, rbx
0x18000d5d4  mov     rax, [rax+18h]
0x18000d5d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5dd  test    eax, eax
0x18000d5df  js      loc_18000D4F2
0x18000d5e5  mov     rax, [rbx]
0x18000d5e8  lea     r8, [rbp+650h+Filename]
0x18000d5ef  lea     rdx, aModuleRaw; "Module_Raw"
0x18000d5f6  mov     rcx, rbx
0x18000d5f9  mov     rax, [rax+18h]
0x18000d5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d602  test    eax, eax
0x18000d604  js      loc_18000D4F2
0x18000d60a  mov     [rsp+750h+lpsz], rsi
0x18000d60f  lea     rdx, [rsp+750h+lpsz]; lplpsz
0x18000d614  lea     rcx, ?m_libid@CAtlModule@ATL@@2U_GUID@@A; rclsid
0x18000d61b  call    cs:__imp_StringFromCLSID
0x18000d621  test    eax, eax
0x18000d623  js      loc_18000D4F2
0x18000d629  mov     rax, [rbx]
0x18000d62c  mov     r8, [rsp+750h+lpsz]
0x18000d631  lea     rdx, aModuleguid_0; "MODULEGUID"
0x18000d638  mov     rcx, rbx
0x18000d63b  mov     rax, [rax+18h]
0x18000d63f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d644  mov     edi, eax
0x18000d646  mov     rcx, [rsp+750h+lpsz]; pv
0x18000d64b  call    cs:__imp_CoTaskMemFree
0x18000d651  test    edi, edi
0x18000d653  jns     short loc_18000D65C
0x18000d655  mov     eax, edi
0x18000d657  jmp     loc_18000D4F2
0x18000d65c  mov     edi, 2B8h
0x18000d661  mov     r8d, edi; Size
0x18000d664  xor     edx, edx; Val
0x18000d666  lea     rcx, [rsp+750h+psfi]; void *
0x18000d66b  call    memset_0
0x18000d670  mov     [rsp+750h+uFlags], 2000h; uFlags
0x18000d678  mov     r9d, edi; cbFileInfo
0x18000d67b  lea     r8, [rsp+750h+psfi]; psfi
0x18000d680  xor     edx, edx; dwFileAttributes
0x18000d682  lea     rcx, [rbp+650h+Filename]; pszPath
0x18000d689  call    cs:__imp_SHGetFileInfoW
0x18000d68f  mov     rcx, [rbx]
0x18000d692  mov     r9, [rcx+18h]
0x18000d696  lea     rdx, aModuletype_0; "MODULETYPE"
0x18000d69d  mov     rcx, rbx
0x18000d6a0  test    rax, rax
0x18000d6a3  mov     rax, r9
0x18000d6a6  lea     r8, aInprocserver32; "InprocServer32"
0x18000d6ad  jz      short loc_18000D6B6
0x18000d6af  lea     r8, aLocalserver32; "LocalServer32"
0x18000d6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6bb  test    eax, eax
0x18000d6bd  js      loc_18000D4F2
0x18000d6c3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000d6ca  mov     rax, [rcx]
0x18000d6cd  mov     rdx, rbx
0x18000d6d0  mov     rax, [rax+28h]
0x18000d6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d9  jmp     loc_18000D4F2
0x18000d6de  mov     ecx, 8007000Eh; int
0x18000d6e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d6e9  call    __report_rangecheckfailure
0x18000d6ef  mov     ecx, 80004005h; int
0x18000d6f4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000d6fa  mov     ecx, 80070057h; int
0x18000d6ff  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
