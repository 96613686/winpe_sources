# COleInsertDialog::DoModal(ulong)

- ea: `0x1800899b0`
- end: `0x180089d45`
- name: `?DoModal@COleInsertDialog@@QEAA_JK@Z`
- size: `917`
- prototype: `__int64 __fastcall(COleInsertDialog *__hidden this, DWORD dwIndex)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x180019290`
- `0x18002ac00`
- `0x180038820`
- `0x180089220`
- `0x1800899b0`
- `0x18008a2e0`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `msvcrt!free` at `0x180089d0b`
- `msvcrt!free` at `0x180089d0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089cc4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089b9d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089bd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180089cc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089b1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089cb5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a56`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089a81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089aca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089af4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089b1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089b4b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089cb5`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180089b66`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180089b66`
- `OLE32!GetClassFile` at `0x180089c51`
- `OLE32!GetClassFile` at `0x180089c51`
- `ADVAPI32!RegEnumKeyW` at `0x180089aa3`
- `ADVAPI32!RegEnumKeyW` at `0x180089bb8`
- `ADVAPI32!RegEnumKeyW` at `0x180089aa3`
- `ADVAPI32!RegEnumKeyW` at `0x180089bb8`

## string_xrefs

- `0x180089a75`: `CLSID`
- `0x180089c83`: `CLSID\%s\DocObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall COleInsertDialog::DoModal(COleInsertDialog *this, DWORD dwIndex)
{
  HKEY v4; // rdi
  int v5; // esi
  int v6; // r14d
  DWORD v7; // edx
  int v8; // r12d
  __int64 v9; // r13
  __int64 v10; // rsi
  int v11; // r14d
  HKEY phkResult; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v16; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v17; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+60h] [rbp-A0h] BYREF
  CLSID pclsid; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  v4 = 0;
  v18 = 0;
  v5 = 0;
  v15 = 0;
  v19 = 0;
  if ( dwIndex == 2 )
  {
    *((_DWORD *)this + 51) |= 0x3000u;
  }
  else if ( dwIndex == 1 )
  {
    *((_DWORD *)this + 51) |= 0x500u;
    hKey = 0;
    phkResult = 0;
    v16 = 0;
    v17 = 0;
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, 0, 0, 0x20019u, &hKey) && !RegOpenKeyExW(hKey, L"CLSID", 0, 8u, &phkResult) )
    {
      v6 = 1;
      if ( !RegEnumKeyW(phkResult, 0, Name, 0x105u) )
      {
        do
        {
          if ( !RegOpenKeyExW(phkResult, Name, 0, 0x20019u, &v16)
            && (!RegOpenKeyExW(v16, L"Insertable", 0, 0x20019u, &v17)
             || !RegOpenKeyExW(v16, L"Ole1Class", 0, 0x20019u, &v17)) )
          {
            RegCloseKey(v17);
            if ( RegOpenKeyExW(v16, L"DocObject", 0, 0x20019u, &v17) )
            {
              pclsid = 0;
              CLSIDFromString(Name, &pclsid);
              COleInsertDialog::AddClassIDToList(this, (struct _GUID **)&v18, &v15, &v19, &pclsid);
              RegCloseKey(v16);
            }
            RegCloseKey(v17);
          }
          v7 = v6++;
        }
        while ( !RegEnumKeyW(phkResult, v7, Name, 0x105u) );
        v4 = v18;
        v5 = v15;
      }
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
  }
  v8 = *((_DWORD *)this + 73);
  v9 = *((_QWORD *)this + 37);
  if ( v4 )
  {
    *((_QWORD *)this + 37) = v4;
    *((_DWORD *)this + 73) = v5;
  }
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(COleInsertDialog *))(*(_QWORD *)this + 384LL))(this);
    if ( v10 != 1 || COleInsertDialog::GetSelectionType(this) != 1 || dwIndex != 1 )
      break;
    pclsid = 0;
    if ( !GetClassFile(*((LPCOLESTR *)this + 35), &pclsid) )
    {
      v11 = 0;
      hKey = (HKEY)_afxPchNil;
      AfxStringFromCLSID(&phkResult, &pclsid);
      CString::Format((CString *)&hKey, (wchar_t *)L"CLSID\\%s\\DocObject", phkResult);
      v18 = 0;
      if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, (LPCWSTR)hKey, 0, 1u, &v18) )
      {
        RegCloseKey(v18);
        v11 = 1;
      }
      CString::~CString((CString *)&phkResult);
      CString::~CString((CString *)&hKey);
      if ( v11 )
        break;
    }
    if ( (unsigned int)AfxMessageBox(0xF184u, 0x15u, 0xFFFFFFFF) != 4 )
    {
      v10 = 2;
      break;
    }
  }
  free(v4);
  *((_DWORD *)this + 73) = v8;
  *((_QWORD *)this + 37) = v9;
  return v10;
}

```

## disassembly

```asm
0x1800899b0  push    rbp
0x1800899b2  push    rbx
0x1800899b3  push    rsi
0x1800899b4  push    rdi
0x1800899b5  push    r12
0x1800899b7  push    r13
0x1800899b9  push    r14
0x1800899bb  push    r15
0x1800899bd  lea     rbp, [rsp-1A8h]
0x1800899c5  sub     rsp, 2A8h
0x1800899cc  mov     rax, cs:__security_cookie
0x1800899d3  xor     rax, rsp
0x1800899d6  mov     [rbp+1E0h+var_50], rax
0x1800899dd  mov     r15d, edx
0x1800899e0  mov     rbx, rcx
0x1800899e3  xor     r12d, r12d
0x1800899e6  mov     edi, r12d
0x1800899e9  mov     [rsp+2E0h+var_288], r12
0x1800899ee  mov     esi, r12d
0x1800899f1  mov     [rsp+2E0h+var_2A0], r12d
0x1800899f6  mov     [rsp+2E0h+var_280], r12d
0x1800899fb  cmp     edx, 2
0x1800899fe  jnz     short loc_180089A0F
0x180089a00  or      dword ptr [rcx+0CCh], 3000h
0x180089a0a  jmp     loc_180089BE5
0x180089a0f  cmp     r15d, 1
0x180089a13  jnz     loc_180089BE5
0x180089a19  or      dword ptr [rcx+0CCh], 500h
0x180089a23  mov     [rsp+2E0h+hKey], r12
0x180089a28  mov     [rsp+2E0h+var_2B0], r12
0x180089a2d  mov     [rsp+2E0h+var_298], r12
0x180089a32  mov     [rsp+2E0h+var_290], r12
0x180089a37  lea     rax, [rsp+2E0h+hKey]
0x180089a3c  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089a41  mov     r13d, 20019h
0x180089a47  mov     r9d, r13d; samDesired
0x180089a4a  xor     r8d, r8d; ulOptions
0x180089a4d  xor     edx, edx; lpSubKey
0x180089a4f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180089a56  call    cs:__imp_RegOpenKeyExW
0x180089a5c  test    eax, eax
0x180089a5e  jnz     loc_180089BDA
0x180089a64  lea     rax, [rsp+2E0h+var_2B0]
0x180089a69  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089a6e  lea     r9d, [r15+7]; samDesired
0x180089a72  xor     r8d, r8d; ulOptions
0x180089a75  lea     rdx, aClsid_1; "CLSID"
0x180089a7c  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180089a81  call    cs:__imp_RegOpenKeyExW
0x180089a87  test    eax, eax
0x180089a89  jnz     loc_180089BDA
0x180089a8f  mov     r14d, r15d
0x180089a92  mov     r9d, 105h; cchName
0x180089a98  lea     r8, [rbp+1E0h+Name]; lpName
0x180089a9c  xor     edx, edx; dwIndex
0x180089a9e  mov     rcx, [rsp+2E0h+var_2B0]; hKey
0x180089aa3  call    cs:__imp_RegEnumKeyW
0x180089aa9  test    eax, eax
0x180089aab  jnz     loc_180089BCF
0x180089ab1  lea     rax, [rsp+2E0h+var_298]
0x180089ab6  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089abb  mov     r9d, r13d; samDesired
0x180089abe  xor     r8d, r8d; ulOptions
0x180089ac1  lea     rdx, [rbp+1E0h+Name]; lpSubKey
0x180089ac5  mov     rcx, [rsp+2E0h+var_2B0]; hKey
0x180089aca  call    cs:__imp_RegOpenKeyExW
0x180089ad0  test    eax, eax
0x180089ad2  jnz     loc_180089BA3
0x180089ad8  lea     rax, [rsp+2E0h+var_290]
0x180089add  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089ae2  mov     r9d, r13d; samDesired
0x180089ae5  xor     r8d, r8d; ulOptions
0x180089ae8  lea     rdx, aInsertable; "Insertable"
0x180089aef  mov     rcx, [rsp+2E0h+var_298]; hKey
0x180089af4  call    cs:__imp_RegOpenKeyExW
0x180089afa  test    eax, eax
0x180089afc  jz      short loc_180089B24
0x180089afe  lea     rax, [rsp+2E0h+var_290]
0x180089b03  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089b08  mov     r9d, r13d; samDesired
0x180089b0b  xor     r8d, r8d; ulOptions
0x180089b0e  lea     rdx, aOle1class; "Ole1Class"
0x180089b15  mov     rcx, [rsp+2E0h+var_298]; hKey
0x180089b1a  call    cs:__imp_RegOpenKeyExW
0x180089b20  test    eax, eax
0x180089b22  jnz     short loc_180089BA3
0x180089b24  mov     rcx, [rsp+2E0h+var_290]; hKey
0x180089b29  call    cs:__imp_RegCloseKey
0x180089b2f  lea     rax, [rsp+2E0h+var_290]
0x180089b34  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089b39  mov     r9d, r13d; samDesired
0x180089b3c  xor     r8d, r8d; ulOptions
0x180089b3f  lea     rdx, aDocobject; "DocObject"
0x180089b46  mov     rcx, [rsp+2E0h+var_298]; hKey
0x180089b4b  call    cs:__imp_RegOpenKeyExW
0x180089b51  test    eax, eax
0x180089b53  jz      short loc_180089B98
0x180089b55  xorps   xmm0, xmm0
0x180089b58  movups  xmmword ptr [rsp+2E0h+pclsid.Data1], xmm0
0x180089b5d  lea     rdx, [rsp+2E0h+pclsid]; pclsid
0x180089b62  lea     rcx, [rbp+1E0h+Name]; lpsz
0x180089b66  call    cs:__imp_CLSIDFromString
0x180089b6c  lea     rax, [rsp+2E0h+pclsid]
0x180089b71  mov     [rsp+2E0h+phkResult], rax; struct _GUID *
0x180089b76  lea     r9, [rsp+2E0h+var_280]; int *
0x180089b7b  lea     r8, [rsp+2E0h+var_2A0]; int *
0x180089b80  lea     rdx, [rsp+2E0h+var_288]; struct _GUID **
0x180089b85  mov     rcx, rbx; this
0x180089b88  call    ?AddClassIDToList@COleInsertDialog@@IEAAXAEAPEAU_GUID@@AEAH1PEAU2@@Z; COleInsertDialog::AddClassIDToList(_GUID * &,int &,int &,_GUID *)
0x180089b8d  mov     rcx, [rsp+2E0h+var_298]; hKey
0x180089b92  call    cs:__imp_RegCloseKey
0x180089b98  mov     rcx, [rsp+2E0h+var_290]; hKey
0x180089b9d  call    cs:__imp_RegCloseKey
0x180089ba3  mov     edx, r14d; dwIndex
0x180089ba6  inc     r14d
0x180089ba9  mov     r9d, 105h; cchName
0x180089baf  lea     r8, [rbp+1E0h+Name]; lpName
0x180089bb3  mov     rcx, [rsp+2E0h+var_2B0]; hKey
0x180089bb8  call    cs:__imp_RegEnumKeyW
0x180089bbe  test    eax, eax
0x180089bc0  jz      loc_180089AB1
0x180089bc6  mov     rdi, [rsp+2E0h+var_288]
0x180089bcb  mov     esi, [rsp+2E0h+var_2A0]
0x180089bcf  mov     rcx, [rsp+2E0h+var_2B0]; hKey
0x180089bd4  call    cs:__imp_RegCloseKey
0x180089bda  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180089bdf  call    cs:__imp_RegCloseKey
0x180089be5  mov     r12d, [rbx+124h]
0x180089bec  mov     r13, [rbx+128h]
0x180089bf3  test    rdi, rdi
0x180089bf6  jz      short loc_180089C05
0x180089bf8  mov     [rbx+128h], rdi
0x180089bff  mov     [rbx+124h], esi
0x180089c05  mov     rax, [rbx]
0x180089c08  mov     rcx, rbx
0x180089c0b  mov     rax, [rax+180h]
0x180089c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089c17  mov     rsi, rax
0x180089c1a  cmp     rax, 1
0x180089c1e  jnz     loc_180089D08
0x180089c24  mov     rcx, rbx; this
0x180089c27  call    ?GetSelectionType@COleInsertDialog@@QEBAIXZ; COleInsertDialog::GetSelectionType(void)
0x180089c2c  cmp     eax, esi
0x180089c2e  jnz     loc_180089D08
0x180089c34  cmp     r15d, esi
0x180089c37  jnz     loc_180089D08
0x180089c3d  xorps   xmm0, xmm0
0x180089c40  movups  xmmword ptr [rsp+2E0h+pclsid.Data1], xmm0
0x180089c45  lea     rdx, [rsp+2E0h+pclsid]; pclsid
0x180089c4a  mov     rcx, [rbx+118h]; szFilename
0x180089c51  call    cs:__imp_GetClassFile
0x180089c57  test    eax, eax
0x180089c59  jnz     loc_180089CE7
0x180089c5f  xor     r14d, r14d
0x180089c62  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x180089c69  mov     [rsp+2E0h+hKey], rax
0x180089c6e  lea     rdx, [rsp+2E0h+pclsid]
0x180089c73  lea     rcx, [rsp+2E0h+var_2B0]
0x180089c78  call    ?AfxStringFromCLSID@@YA?AVCString@@AEBU_GUID@@@Z; AfxStringFromCLSID(_GUID const &)
0x180089c7d  nop
0x180089c7e  mov     r8, [rsp+2E0h+var_2B0]
0x180089c83  lea     rdx, aClsidSDocobjec; "CLSID\\%s\\DocObject"
0x180089c8a  lea     rcx, [rsp+2E0h+hKey]; this
0x180089c8f  call    ?Format@CString@@QEAAXPEBGZZ; CString::Format(ushort const *,...)
0x180089c94  mov     [rsp+2E0h+var_288], r14
0x180089c99  lea     rax, [rsp+2E0h+var_288]
0x180089c9e  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180089ca3  mov     r9d, esi; samDesired
0x180089ca6  xor     r8d, r8d; ulOptions
0x180089ca9  mov     rdx, [rsp+2E0h+hKey]; lpSubKey
0x180089cae  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180089cb5  call    cs:__imp_RegOpenKeyExW
0x180089cbb  test    eax, eax
0x180089cbd  jnz     short loc_180089CCD
0x180089cbf  mov     rcx, [rsp+2E0h+var_288]; hKey
0x180089cc4  call    cs:__imp_RegCloseKey
0x180089cca  mov     r14d, esi
0x180089ccd  lea     rcx, [rsp+2E0h+var_2B0]; this
0x180089cd2  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180089cd7  nop
0x180089cd8  lea     rcx, [rsp+2E0h+hKey]; this
0x180089cdd  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x180089ce2  test    r14d, r14d
0x180089ce5  jnz     short loc_180089D08
0x180089ce7  or      r8d, 0FFFFFFFFh; unsigned int
0x180089ceb  mov     edx, 15h; unsigned int
0x180089cf0  mov     ecx, 0F184h; uID
0x180089cf5  call    ?AfxMessageBox@@YAHIII@Z; AfxMessageBox(uint,uint,uint)
0x180089cfa  cmp     eax, 4
0x180089cfd  jz      loc_180089C05
0x180089d03  mov     esi, 2
0x180089d08  mov     rcx, rdi; Block
0x180089d0b  call    cs:__imp_free
0x180089d11  mov     [rbx+124h], r12d
0x180089d18  mov     [rbx+128h], r13
0x180089d1f  mov     rax, rsi
0x180089d22  mov     rcx, [rbp+1E0h+var_50]
0x180089d29  xor     rcx, rsp; StackCookie
0x180089d2c  call    __security_check_cookie
0x180089d31  add     rsp, 2A8h
0x180089d38  pop     r15
0x180089d3a  pop     r14
0x180089d3c  pop     r13
0x180089d3e  pop     r12
0x180089d40  pop     rdi
0x180089d41  pop     rsi
0x180089d42  pop     rbx
0x180089d43  pop     rbp
0x180089d44  retn
```
