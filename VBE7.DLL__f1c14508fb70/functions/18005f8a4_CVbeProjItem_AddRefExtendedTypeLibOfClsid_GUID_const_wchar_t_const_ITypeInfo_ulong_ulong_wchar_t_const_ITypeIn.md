# CVbeProjItem::AddRefExtendedTypeLibOfClsid(_GUID const &,wchar_t const *,ITypeInfo *,ulong,ulong,wchar_t const *,ITypeInfo * *)

- ea: `0x18005f8a4`
- end: `0x18005fb4d`
- name: `?AddRefExtendedTypeLibOfClsid@CVbeProjItem@@UEAAJAEBU_GUID@@PEB_WPEAUITypeInfo@@KK1PEAPEAU3@@Z`
- size: `681`
- prototype: `__int64 __fastcall(CVbeProjItem *__hidden this, const struct _GUID *, const wchar_t *, struct ITypeInfo *, unsigned int, unsigned int, const wchar_t *, struct ITypeInfo **)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18005ab18`
- `0x18005b0d4`
- `0x18005f8a4`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `MSVCR100!atoi` at `0x18005fa5e`
- `MSVCR100!atoi` at `0x18005fa70`
- `MSVCR100!atoi` at `0x18005fa5e`
- `MSVCR100!atoi` at `0x18005fa70`
- `ADVAPI32!RegOpenKeyA` at `0x18005f913`
- `ADVAPI32!RegOpenKeyA` at `0x18005f93f`
- `ADVAPI32!RegOpenKeyA` at `0x18005f95c`
- `ADVAPI32!RegOpenKeyA` at `0x18005fa04`
- `ADVAPI32!RegOpenKeyA` at `0x18005f913`
- `ADVAPI32!RegOpenKeyA` at `0x18005f93f`
- `ADVAPI32!RegOpenKeyA` at `0x18005f95c`
- `ADVAPI32!RegOpenKeyA` at `0x18005fa04`
- `ADVAPI32!RegCloseKey` at `0x18005fb04`
- `ADVAPI32!RegCloseKey` at `0x18005fb0e`
- `ADVAPI32!RegCloseKey` at `0x18005fb18`
- `ADVAPI32!RegCloseKey` at `0x18005fb22`
- `ADVAPI32!RegCloseKey` at `0x18005fb04`
- `ADVAPI32!RegCloseKey` at `0x18005fb0e`
- `ADVAPI32!RegCloseKey` at `0x18005fb18`
- `ADVAPI32!RegCloseKey` at `0x18005fb22`
- `ADVAPI32!RegQueryValueA` at `0x18005f97f`
- `ADVAPI32!RegQueryValueA` at `0x18005fa2a`
- `ADVAPI32!RegQueryValueA` at `0x18005f97f`
- `ADVAPI32!RegQueryValueA` at `0x18005fa2a`
- `ole32!CLSIDFromString` at `0x18005f9ef`
- `ole32!CLSIDFromString` at `0x18005f9ef`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fada`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fada`
- `OLEAUT32!__imp_QueryPathOfRegTypeLib` at `0x18005fa90`
- `OLEAUT32!__imp_QueryPathOfRegTypeLib` at `0x18005fa90`

## string_xrefs

- `0x18005f8f9`: `CLSID`

## pseudocode

```c
__int64 __fastcall CVbeProjItem::AddRefExtendedTypeLibOfClsid(
        CVbeProjItem *this,
        const struct _GUID *a2,
        const wchar_t *a3,
        struct ITypeInfo *a4,
        unsigned int a5,
        unsigned int a6,
        const wchar_t *a7,
        struct ITypeInfo **a8)
{
  HRESULT v12; // ebx
  USHORT v13; // di
  __int64 v14; // rax
  unsigned __int64 v15; // rax
  __int64 v16; // rcx
  unsigned __int64 v17; // rcx
  void *v18; // rsp
  void *v19; // rsp
  const OLECHAR *v20; // rax
  CHAR *v21; // rbx
  USHORT v22; // ax
  LONG cbData; // [rsp+40h] [rbp+0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+8h] BYREF
  HKEY v26; // [rsp+50h] [rbp+10h] BYREF
  HKEY v27; // [rsp+58h] [rbp+18h] BYREF
  BSTR bstrPathName; // [rsp+60h] [rbp+20h] BYREF
  __int64 v29; // [rsp+68h] [rbp+28h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+30h] BYREF
  const wchar_t *v31; // [rsp+78h] [rbp+38h]
  __int64 v32; // [rsp+80h] [rbp+40h]
  CLSID pclsid; // [rsp+88h] [rbp+48h] BYREF
  CHAR SubKey[40]; // [rsp+98h] [rbp+58h] BYREF
  CHAR Data[128]; // [rsp+C0h] [rbp+80h] BYREF

  v31 = a7;
  v32 = a5;
  v12 = -2147221168;
  v13 = 0;
  if ( !RegOpenKeyA(HKEY_CLASSES_ROOT, "CLSID", &phkResult) )
  {
    StringFromGUID2Ansi(a2, SubKey, 39);
    if ( !RegOpenKeyA(phkResult, SubKey, &hKey) )
    {
      if ( !RegOpenKeyA(hKey, "TypeLib", &v26) )
      {
        cbData = 39;
        if ( !RegQueryValueA(v26, 0, SubKey, &cbData) )
        {
          if ( ((unsigned __int64)SubKey & 0xFFFFFFFFFFFF0000uLL) != 0 )
          {
            v14 = -1;
            do
              ++v14;
            while ( SubKey[v14] );
            v15 = 2 * v14 + 2;
            v16 = v15 + 15;
            if ( v15 + 15 < v15 )
              v16 = 0xFFFFFFFFFFFFFF0LL;
            v17 = v16 & 0xFFFFFFFFFFFFFFF0uLL;
            v18 = alloca(v17);
            v19 = alloca(v17);
            v20 = strcpyWfromA((wchar_t *)&cbData, SubKey);
          }
          else
          {
            v20 = (const OLECHAR *)SubKey;
          }
          CLSIDFromString(v20, &pclsid);
          if ( !RegOpenKeyA(hKey, "Version", &v27) )
          {
            cbData = 128;
            if ( !RegQueryValueA(v27, 0, Data, &cbData) )
            {
              v21 = Data;
              if ( Data[0] == 46 )
              {
LABEL_17:
                if ( *v21 )
                  v13 = atoi(v21 + 1);
              }
              else
              {
                while ( *v21 )
                {
                  if ( *++v21 == 46 )
                    goto LABEL_17;
                }
              }
              *v21 = 0;
              v22 = atoi(Data);
              v12 = QueryPathOfRegTypeLib(&pclsid, v22, v13, 0x409u, &bstrPathName);
              if ( !v12 )
              {
                v12 = (*(__int64 (__fastcall **)(CVbeProjItem *, BSTR, const wchar_t *, struct ITypeInfo *, _DWORD, unsigned int, const wchar_t *, __int64 *))(*(_QWORD *)this + 32LL))(
                        this,
                        bstrPathName,
                        a3,
                        a4,
                        v32,
                        a6,
                        v31,
                        &v29);
                SysFreeString(bstrPathName);
                if ( v12 >= 0 )
                {
                  v12 = (*(__int64 (__fastcall **)(__int64, const struct _GUID *, struct ITypeInfo **))(*(_QWORD *)v29 + 48LL))(
                          v29,
                          a2,
                          a8);
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
                }
              }
            }
            RegCloseKey(v27);
          }
        }
        RegCloseKey(v26);
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005f8a4  push    rbp
0x18005f8a6  push    rbx
0x18005f8a7  push    rsi
0x18005f8a8  push    rdi
0x18005f8a9  push    r12
0x18005f8ab  push    r13
0x18005f8ad  push    r14
0x18005f8af  push    r15
0x18005f8b1  mov     eax, 158h
0x18005f8b6  call    _alloca_probe
0x18005f8bb  sub     rsp, rax
0x18005f8be  lea     rbp, [rsp+40h]
0x18005f8c3  mov     rax, cs:__security_cookie
0x18005f8ca  xor     rax, rbp
0x18005f8cd  mov     [rbp+150h+var_50], rax
0x18005f8d4  mov     eax, [rbp+150h+arg_20]
0x18005f8da  mov     r15, [rbp+150h+arg_38]
0x18005f8e1  mov     r14, rcx
0x18005f8e4  mov     rcx, [rbp+150h+arg_30]
0x18005f8eb  mov     r12, r8
0x18005f8ee  mov     rsi, rdx
0x18005f8f1  mov     [rbp+150h+var_118], rcx
0x18005f8f5  lea     r8, [rbp+150h+phkResult]; phkResult
0x18005f8f9  lea     rdx, aClsid_1; "CLSID"
0x18005f900  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005f907  mov     r13, r9
0x18005f90a  mov     [rbp+150h+var_110], rax
0x18005f90e  mov     ebx, 80040150h
0x18005f913  call    cs:__imp_RegOpenKeyA
0x18005f919  xor     edi, edi
0x18005f91b  test    eax, eax
0x18005f91d  jnz     loc_18005FB28
0x18005f923  lea     r8d, [rdi+27h]; int
0x18005f927  lea     rdx, [rbp+150h+SubKey]; char *
0x18005f92b  mov     rcx, rsi; struct _GUID *
0x18005f92e  call    ?StringFromGUID2Ansi@@YAHAEBU_GUID@@PEADH@Z; StringFromGUID2Ansi(_GUID const &,char *,int)
0x18005f933  mov     rcx, [rbp+150h+phkResult]; hKey
0x18005f937  lea     r8, [rbp+150h+hKey]; phkResult
0x18005f93b  lea     rdx, [rbp+150h+SubKey]; lpSubKey
0x18005f93f  call    cs:__imp_RegOpenKeyA
0x18005f945  test    eax, eax
0x18005f947  jnz     loc_18005FB1E
0x18005f94d  mov     rcx, [rbp+150h+hKey]; hKey
0x18005f951  lea     r8, [rbp+150h+var_140]; phkResult
0x18005f955  lea     rdx, aTypelib_0; "TypeLib"
0x18005f95c  call    cs:__imp_RegOpenKeyA
0x18005f962  test    eax, eax
0x18005f964  jnz     loc_18005FB14
0x18005f96a  mov     rcx, [rbp+150h+var_140]; hKey
0x18005f96e  lea     r9, [rbp+150h+cbData]; lpcbData
0x18005f972  lea     r8, [rbp+150h+SubKey]; lpData
0x18005f976  xor     edx, edx; lpSubKey
0x18005f978  mov     [rbp+150h+cbData], 27h ; '''
0x18005f97f  call    cs:__imp_RegQueryValueA
0x18005f985  test    eax, eax
0x18005f987  jnz     loc_18005FB0A
0x18005f98d  lea     rax, [rbp+150h+SubKey]
0x18005f991  test    rax, 0FFFFFFFFFFFF0000h
0x18005f997  jz      short loc_18005F9E4
0x18005f999  lea     rcx, [rbp+150h+SubKey]
0x18005f99d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005f9a1  inc     rax
0x18005f9a4  cmp     [rcx+rax], dil
0x18005f9a8  jnz     short loc_18005F9A1
0x18005f9aa  lea     rax, ds:2[rax*2]
0x18005f9b2  lea     rcx, [rax+0Fh]
0x18005f9b6  cmp     rcx, rax
0x18005f9b9  ja      short loc_18005F9C5
0x18005f9bb  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18005f9c5  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18005f9c9  mov     rax, rcx
0x18005f9cc  call    _alloca_probe
0x18005f9d1  sub     rsp, rcx
0x18005f9d4  lea     rdx, [rbp+150h+SubKey]; char *
0x18005f9d8  lea     rcx, [rsp+190h+cbData]; wchar_t *
0x18005f9dd  call    ?strcpyWfromA@@YAPEA_WPEA_WPEBD@Z; strcpyWfromA(wchar_t *,char const *)
0x18005f9e2  jmp     short loc_18005F9E8
0x18005f9e4  lea     rax, [rbp+150h+SubKey]
0x18005f9e8  lea     rdx, [rbp+150h+pclsid]; pclsid
0x18005f9ec  mov     rcx, rax; lpsz
0x18005f9ef  call    cs:__imp_CLSIDFromString
0x18005f9f5  mov     rcx, [rbp+150h+hKey]; hKey
0x18005f9f9  lea     r8, [rbp+150h+var_138]; phkResult
0x18005f9fd  lea     rdx, aVersion; "Version"
0x18005fa04  call    cs:__imp_RegOpenKeyA
0x18005fa0a  test    eax, eax
0x18005fa0c  jnz     loc_18005FB0A
0x18005fa12  mov     rcx, [rbp+150h+var_138]; hKey
0x18005fa16  lea     r9, [rbp+150h+cbData]; lpcbData
0x18005fa1a  lea     r8, [rbp+150h+Data]; lpData
0x18005fa21  xor     edx, edx; lpSubKey
0x18005fa23  mov     [rbp+150h+cbData], 80h
0x18005fa2a  call    cs:__imp_RegQueryValueA
0x18005fa30  test    eax, eax
0x18005fa32  jnz     loc_18005FB00
0x18005fa38  cmp     [rbp+150h+Data], 2Eh ; '.'
0x18005fa3f  lea     rbx, [rbp+150h+Data]
0x18005fa46  jz      short loc_18005FA55
0x18005fa48  cmp     [rbx], dil
0x18005fa4b  jz      short loc_18005FA66
0x18005fa4d  inc     rbx
0x18005fa50  cmp     byte ptr [rbx], 2Eh ; '.'
0x18005fa53  jnz     short loc_18005FA48
0x18005fa55  cmp     [rbx], dil
0x18005fa58  jz      short loc_18005FA66
0x18005fa5a  lea     rcx, [rbx+1]; String
0x18005fa5e  call    cs:__imp_atoi
0x18005fa64  mov     edi, eax
0x18005fa66  lea     rcx, [rbp+150h+Data]; String
0x18005fa6d  mov     byte ptr [rbx], 0
0x18005fa70  call    cs:__imp_atoi
0x18005fa76  lea     rcx, [rbp+150h+bstrPathName]
0x18005fa7a  mov     r9d, 409h; lcid
0x18005fa80  mov     [rsp+190h+lpbstrPathName], rcx; lpbstrPathName
0x18005fa85  lea     rcx, [rbp+150h+pclsid]; guid
0x18005fa89  movzx   r8d, di; wMin
0x18005fa8d  movzx   edx, ax; wMaj
0x18005fa90  call    cs:__imp_QueryPathOfRegTypeLib
0x18005fa96  mov     ebx, eax
0x18005fa98  test    eax, eax
0x18005fa9a  jnz     short loc_18005FB00
0x18005fa9c  mov     r10, [r14]
0x18005fa9f  mov     rdx, [rbp+150h+bstrPathName]
0x18005faa3  lea     rax, [rbp+150h+var_128]
0x18005faa7  mov     [rsp+190h+var_158], rax
0x18005faac  mov     rax, [rbp+150h+var_118]
0x18005fab0  mov     r9, r13
0x18005fab3  mov     [rsp+190h+var_160], rax
0x18005fab8  mov     eax, [rbp+150h+arg_28]
0x18005fabe  mov     r8, r12
0x18005fac1  mov     [rsp+190h+var_168], eax
0x18005fac5  mov     rax, [rbp+150h+var_110]
0x18005fac9  mov     rcx, r14
0x18005facc  mov     dword ptr [rsp+190h+lpbstrPathName], eax
0x18005fad0  call    qword ptr [r10+20h]
0x18005fad4  mov     rcx, [rbp+150h+bstrPathName]; bstrString
0x18005fad8  mov     ebx, eax
0x18005fada  call    cs:__imp_SysFreeString
0x18005fae0  test    ebx, ebx
0x18005fae2  js      short loc_18005FB00
0x18005fae4  mov     rcx, [rbp+150h+var_128]
0x18005fae8  mov     r8, r15
0x18005faeb  mov     rdx, rsi
0x18005faee  mov     rax, [rcx]
0x18005faf1  call    qword ptr [rax+30h]
0x18005faf4  mov     rcx, [rbp+150h+var_128]
0x18005faf8  mov     ebx, eax
0x18005fafa  mov     rax, [rcx]
0x18005fafd  call    qword ptr [rax+10h]
0x18005fb00  mov     rcx, [rbp+150h+var_138]; hKey
0x18005fb04  call    cs:__imp_RegCloseKey
0x18005fb0a  mov     rcx, [rbp+150h+var_140]; hKey
0x18005fb0e  call    cs:__imp_RegCloseKey
0x18005fb14  mov     rcx, [rbp+150h+hKey]; hKey
0x18005fb18  call    cs:__imp_RegCloseKey
0x18005fb1e  mov     rcx, [rbp+150h+phkResult]; hKey
0x18005fb22  call    cs:__imp_RegCloseKey
0x18005fb28  mov     eax, ebx
0x18005fb2a  mov     rcx, [rbp+150h+var_50]
0x18005fb31  xor     rcx, rbp; StackCookie
0x18005fb34  call    __security_check_cookie
0x18005fb39  lea     rsp, [rbp+118h]
0x18005fb40  pop     r15
0x18005fb42  pop     r14
0x18005fb44  pop     r13
0x18005fb46  pop     r12
0x18005fb48  pop     rdi
0x18005fb49  pop     rsi
0x18005fb4a  pop     rbx
0x18005fb4b  pop     rbp
0x18005fb4c  retn
```
