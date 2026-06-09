# CMapiSupport::GetDllDetails(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x180030cc8`
- end: `0x180030f1f`
- name: `?GetDllDetails@CMapiSupport@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAV23@1@Z`
- size: `599`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x180030f28`

## callees

- `0x180002300`
- `0x18000b9f0`
- `0x18000e0d0`
- `0x18000e6e0`
- `0x18000ee48`
- `0x18000ee70`
- `0x1800115d0`
- `0x180011884`
- `0x1800122a0`
- `0x1800122d8`
- `0x180030cc8`
- `0x18003101c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030d38`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180030d5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180030d5e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180030db2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180030e67`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180030db2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x180030e67`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiSupport::GetDllDetails(WCHAR *a1, __int64 a2, __int64 a3)
{
  HMODULE ModuleHandleW; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  WCHAR *v8; // rdi
  WCHAR *pszPath; // rbx
  HRESULT v10; // edi
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int DllDetailsFromPath; // edi
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  LPWSTR v25[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF

  v25[1] = a1;
  ATL::CSimpleStringT<wchar_t,0>::SetString(a2, &dword_1800444C4, 0);
  ATL::CSimpleStringT<wchar_t,0>::SetString(a3, &dword_1800444C4, 0);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>((__int64)v25);
  ModuleHandleW = GetModuleHandleW(*(LPCWSTR *)a1);
  if ( ModuleHandleW )
  {
    v8 = Filename;
    if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) || !(unsigned int)ResultFromLastError() )
    {
      pszPath = v25[0];
      goto LABEL_11;
    }
  }
  pszPath = v25[0];
  if ( ((*((_DWORD *)v25[0] - 3) - 260) | (1 - *((_DWORD *)v25[0] - 2))) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v25, 260, v6, v7);
    pszPath = v25[0];
  }
  v10 = SHGetFolderPathW(0, 43, 0, 0, pszPath);
  v11 = ocslen(pszPath);
  ATL::CSimpleStringT<wchar_t,0>::SetLength(v25, v11, v12, v13);
  if ( !v10 )
  {
    ATL::CSimpleStringT<wchar_t,0>::Append(v25, L"\\System\\MSMAPI\\1033\\");
    ATL::CSimpleStringT<wchar_t,0>::Append((__int64 *)v25, *(const void **)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
    pszPath = v25[0];
    if ( ((*((_DWORD *)v25[0] - 3) - 260) | (1 - *((_DWORD *)v25[0] - 2))) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v25, 260, v16, v17);
      pszPath = v25[0];
    }
    v8 = pszPath;
LABEL_11:
    DllDetailsFromPath = CMapiSupport::GetDllDetailsFromPath(v8);
    if ( !DllDetailsFromPath )
      goto LABEL_18;
  }
  if ( ((*((_DWORD *)pszPath - 3) - 260) | (1 - *((_DWORD *)pszPath - 2))) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v25, 260, v14, v15);
    pszPath = v25[0];
  }
  DllDetailsFromPath = SHGetFolderPathW(0, 37, 0, 0, pszPath);
  v19 = ocslen(pszPath);
  ATL::CSimpleStringT<wchar_t,0>::SetLength(v25, v19, v20, v21);
  ATL::CSimpleStringT<wchar_t,0>::Append(v25, L"\\");
  ATL::CSimpleStringT<wchar_t,0>::Append((__int64 *)v25, *(const void **)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
  pszPath = v25[0];
  if ( !DllDetailsFromPath )
  {
    if ( ((*((_DWORD *)v25[0] - 3) - 260) | (1 - *((_DWORD *)v25[0] - 2))) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v25, 260, v22, v23);
      pszPath = v25[0];
    }
    DllDetailsFromPath = CMapiSupport::GetDllDetailsFromPath(pszPath);
  }
LABEL_18:
  ATL::CStringData::Release((ATL::CStringData *)(pszPath - 12));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)a1 - 24LL));
  return DllDetailsFromPath;
}

```

## disassembly

```asm
0x180030cc8  mov     [rsp-8+arg_18], rbx
0x180030ccd  push    rbp
0x180030cce  push    rsi
0x180030ccf  push    rdi
0x180030cd0  push    r12
0x180030cd2  push    r13
0x180030cd4  push    r14
0x180030cd6  push    r15
0x180030cd8  lea     rbp, [rsp-160h]
0x180030ce0  sub     rsp, 260h
0x180030ce7  mov     rax, cs:__security_cookie
0x180030cee  xor     rax, rsp
0x180030cf1  mov     [rbp+190h+var_40], rax
0x180030cf8  mov     r12, r8
0x180030cfb  mov     r15, rdx
0x180030cfe  mov     r14, rcx
0x180030d01  mov     [rsp+290h+var_258], rcx
0x180030d06  xor     r8d, r8d
0x180030d09  lea     rdx, dword_1800444C4
0x180030d10  mov     rcx, r15
0x180030d13  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180030d18  xor     r8d, r8d
0x180030d1b  lea     rdx, dword_1800444C4
0x180030d22  mov     rcx, r12
0x180030d25  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x180030d2a  lea     rcx, [rsp+290h+var_260]
0x180030d2f  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x180030d34  nop
0x180030d35  mov     rcx, [r14]; lpModuleName
0x180030d38  call    cs:__imp_GetModuleHandleW
0x180030d3e  mov     esi, 1
0x180030d43  mov     r13d, 104h
0x180030d49  test    rax, rax
0x180030d4c  jz      short loc_180030D7B
0x180030d4e  lea     rdi, [rsp+290h+Filename]
0x180030d53  mov     r8d, r13d; nSize
0x180030d56  lea     rdx, [rsp+290h+Filename]; lpFilename
0x180030d5b  mov     rcx, rax; hModule
0x180030d5e  call    cs:__imp_GetModuleFileNameW
0x180030d64  test    eax, eax
0x180030d66  jnz     short loc_180030D71
0x180030d68  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180030d6d  test    eax, eax
0x180030d6f  jnz     short loc_180030D7B
0x180030d71  mov     rbx, [rsp+290h+var_260]
0x180030d76  jmp     loc_180030E1D
0x180030d7b  mov     rbx, [rsp+290h+var_260]
0x180030d80  mov     ecx, esi
0x180030d82  sub     ecx, [rbx-8]
0x180030d85  mov     eax, [rbx-0Ch]
0x180030d88  sub     eax, r13d
0x180030d8b  or      ecx, eax
0x180030d8d  jge     short loc_180030DA1
0x180030d8f  mov     edx, r13d
0x180030d92  lea     rcx, [rsp+290h+var_260]
0x180030d97  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x180030d9c  mov     rbx, [rsp+290h+var_260]
0x180030da1  mov     [rsp+290h+pszPath], rbx; pszPath
0x180030da6  xor     r9d, r9d; dwFlags
0x180030da9  xor     r8d, r8d; hToken
0x180030dac  lea     edx, [r9+2Bh]; csidl
0x180030db0  xor     ecx, ecx; hwnd
0x180030db2  call    cs:__imp_SHGetFolderPathW
0x180030db8  mov     edi, eax
0x180030dba  mov     rcx, rbx; wchar_t *
0x180030dbd  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x180030dc2  mov     edx, eax
0x180030dc4  lea     rcx, [rsp+290h+var_260]
0x180030dc9  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x180030dce  test    edi, edi
0x180030dd0  jnz     short loc_180030E35
0x180030dd2  lea     rdx, aSystemMsmapi10; "\\System\\MSMAPI\\1033\\"
0x180030dd9  lea     rcx, [rsp+290h+var_260]
0x180030dde  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180030de3  mov     rdx, [r14]
0x180030de6  mov     r8d, [rdx-10h]
0x180030dea  lea     rcx, [rsp+290h+var_260]
0x180030def  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180030df4  mov     rbx, [rsp+290h+var_260]
0x180030df9  mov     ecx, esi
0x180030dfb  sub     ecx, [rbx-8]
0x180030dfe  mov     eax, [rbx-0Ch]
0x180030e01  sub     eax, r13d
0x180030e04  or      ecx, eax
0x180030e06  jge     short loc_180030E1A
0x180030e08  mov     edx, r13d
0x180030e0b  lea     rcx, [rsp+290h+var_260]
0x180030e10  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x180030e15  mov     rbx, [rsp+290h+var_260]
0x180030e1a  mov     rdi, rbx
0x180030e1d  mov     r8, r12
0x180030e20  mov     rdx, r15
0x180030e23  mov     rcx, rdi; lpwstrFilename
0x180030e26  call    ?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z; CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180030e2b  mov     edi, eax
0x180030e2d  test    eax, eax
0x180030e2f  jz      loc_180030EDD
0x180030e35  mov     ecx, esi
0x180030e37  sub     ecx, [rbx-8]
0x180030e3a  mov     eax, [rbx-0Ch]
0x180030e3d  sub     eax, r13d
0x180030e40  or      ecx, eax
0x180030e42  jge     short loc_180030E56
0x180030e44  mov     edx, r13d
0x180030e47  lea     rcx, [rsp+290h+var_260]
0x180030e4c  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x180030e51  mov     rbx, [rsp+290h+var_260]
0x180030e56  mov     [rsp+290h+pszPath], rbx; pszPath
0x180030e5b  xor     r9d, r9d; dwFlags
0x180030e5e  xor     r8d, r8d; hToken
0x180030e61  lea     edx, [r9+25h]; csidl
0x180030e65  xor     ecx, ecx; hwnd
0x180030e67  call    cs:__imp_SHGetFolderPathW
0x180030e6d  mov     edi, eax
0x180030e6f  mov     rcx, rbx; wchar_t *
0x180030e72  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x180030e77  mov     edx, eax
0x180030e79  lea     rcx, [rsp+290h+var_260]
0x180030e7e  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x180030e83  lea     rdx, asc_1800444B8; "\\"
0x180030e8a  lea     rcx, [rsp+290h+var_260]
0x180030e8f  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x180030e94  mov     rdx, [r14]
0x180030e97  mov     r8d, [rdx-10h]
0x180030e9b  lea     rcx, [rsp+290h+var_260]
0x180030ea0  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x180030ea5  mov     rbx, [rsp+290h+var_260]
0x180030eaa  test    edi, edi
0x180030eac  jnz     short loc_180030EDD
0x180030eae  sub     esi, [rbx-8]
0x180030eb1  mov     eax, [rbx-0Ch]
0x180030eb4  sub     eax, r13d
0x180030eb7  or      esi, eax
0x180030eb9  jge     short loc_180030ECD
0x180030ebb  mov     edx, r13d
0x180030ebe  lea     rcx, [rsp+290h+var_260]
0x180030ec3  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x180030ec8  mov     rbx, [rsp+290h+var_260]
0x180030ecd  mov     r8, r12
0x180030ed0  mov     rdx, r15
0x180030ed3  mov     rcx, rbx; lpwstrFilename
0x180030ed6  call    ?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z; CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x180030edb  mov     edi, eax
0x180030edd  lea     rcx, [rbx-18h]; this
0x180030ee1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ee6  nop
0x180030ee7  mov     rcx, [r14]
0x180030eea  sub     rcx, 18h; this
0x180030eee  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180030ef3  mov     eax, edi
0x180030ef5  mov     rcx, [rbp+190h+var_40]
0x180030efc  xor     rcx, rsp; StackCookie
0x180030eff  call    __security_check_cookie
0x180030f04  mov     rbx, [rsp+290h+arg_18]
0x180030f0c  add     rsp, 260h
0x180030f13  pop     r15
0x180030f15  pop     r14
0x180030f17  pop     r13
0x180030f19  pop     r12
0x180030f1b  pop     rdi
0x180030f1c  pop     rsi
0x180030f1d  pop     rbp
0x180030f1e  retn
```
