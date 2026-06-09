# WriteResourceEntry

- ea: `0x180108d7c`
- end: `0x18010906a`
- name: `WriteResourceEntry`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801064a0`

## callees

- `0x18000b9e0`
- `0x180011fe0`
- `0x180106324`
- `0x180106d50`
- `0x180108964`
- `0x180108d7c`
- `0x180139010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180108f5f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180108f5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180109014`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010904f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180109014`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010904f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180108eaa`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180108eaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180108ecb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180108ecb`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180108e2d`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180108e2d`
- `OLEAUT32!__imp_SysFreeString` at `0x180108ed6`
- `OLEAUT32!__imp_SysFreeString` at `0x180108ed6`
- `OLEAUT32!__imp_SysStringLen` at `0x180108fe7`
- `OLEAUT32!__imp_SysStringLen` at `0x180108fe7`

## string_xrefs

- `0x180108fa0`: `Path%d`

## pseudocode

```c
__int64 __fastcall WriteResourceEntry(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // r14
  signed int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rdi
  _BOOL8 v8; // r15
  __int64 v9; // rsi
  char IsStateSeparationEnabled; // al
  const wchar_t *v11; // r9
  LSTATUS v12; // eax
  bool v13; // cc
  UINT v15; // eax
  bool v16; // cc
  BYTE Data[4]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  int v20; // [rsp+64h] [rbp-9Ch]
  BYTE v21[8]; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v23; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  __int64 v25; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  cbData = 4;
  hKey = 0;
  v2 = *(_QWORD *)(a1 + 8);
  v20 = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v21 = 0;
  dwDisposition = 0;
  bstrString = 0;
  v25 = 0;
  v23 = 0;
  v3 = EnterpriseResourceManagerStore_NormalizeURI(v2, &v25);
  v4 = v25;
  v5 = v3;
  if ( v3 >= 0 )
  {
    v5 = AddURIPrefix(v25, *(unsigned int *)(a1 + 44), &v23);
    if ( v5 >= 0 )
    {
      v6 = *(_QWORD *)(a1 + 32);
      v7 = *(_QWORD *)(a1 + 24);
      v8 = *(_DWORD *)a1 != 0;
      v9 = *(_QWORD *)(a1 + 16);
      IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
      v11 = L"OSData\\Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
      if ( !IsStateSeparationEnabled )
        v11 = L"Software\\Microsoft\\EnterpriseResourceManager\\Tracked";
      v5 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s\\%s\\%s", v11, v9, v7, v6);
      if ( v5 >= 0 )
      {
        v12 = RegCreateKeyExW((HKEY)(v8 - 0x7FFFFFFF), SubKey, 0, 0, 0, 0x2011Fu, 0, &hKey, &dwDisposition);
        v5 = v12;
        v13 = v12 <= 0;
        if ( v12 )
          goto LABEL_7;
        if ( dwDisposition != 2 )
          goto LABEL_20;
        v12 = RegQueryValueExW(hKey, L"count", 0, 0, Data, &cbData);
        v5 = v12;
        v13 = v12 <= 0;
        if ( v12 )
        {
LABEL_7:
          if ( v13 )
            goto LABEL_9;
          goto LABEL_8;
        }
        v5 = SearchForResourceByValue(hKey);
        if ( v5 >= 0 && !v20 )
        {
LABEL_20:
          v5 = StringCchPrintfW(SubKey, 0x104u, L"Path%d", *(unsigned int *)Data);
          if ( v5 >= 0 )
          {
            v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, BSTR *))(*(_QWORD *)v23 + 64LL))(
                   v23,
                   0,
                   0,
                   &bstrString);
            if ( v5 >= 0 )
            {
              v15 = SysStringLen(bstrString);
              v12 = RegSetValueExW(hKey, SubKey, 0, 1u, (const BYTE *)bstrString, 2 * v15 + 2);
              v16 = v12 <= 0;
              if ( v12
                || (*(_DWORD *)v21 = *(_DWORD *)Data + 1,
                    v12 = RegSetValueExW(hKey, L"count", 0, 4u, v21, 4u),
                    v16 = v12 <= 0,
                    v12) )
              {
                if ( !v16 )
                {
LABEL_8:
                  v5 = (unsigned __int16)v12 | 0x80070000;
                  goto LABEL_9;
                }
                v5 = v12;
              }
            }
          }
        }
      }
    }
  }
LABEL_9:
  if ( hKey )
    RegCloseKey(hKey);
  SysFreeString(bstrString);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180108d7c  mov     [rsp-8+arg_8], rbx
0x180108d81  mov     [rsp-8+arg_10], rsi
0x180108d86  push    rbp
0x180108d87  push    rdi
0x180108d88  push    r12
0x180108d8a  push    r14
0x180108d8c  push    r15
0x180108d8e  lea     rbp, [rsp-1B0h]
0x180108d96  sub     rsp, 2B0h
0x180108d9d  mov     rax, cs:__security_cookie
0x180108da4  xor     rax, rsp
0x180108da7  mov     [rbp+1D0h+var_30], rax
0x180108dae  xor     r12d, r12d
0x180108db1  mov     [rbp+1D0h+cbData], 4
0x180108db8  mov     rsi, rcx
0x180108dbb  mov     [rsp+2D0h+hKey], r12
0x180108dc0  mov     rcx, [rcx+8]
0x180108dc4  lea     rdx, [rbp+1D0h+var_248]
0x180108dc8  mov     [rsp+2D0h+var_26C], r12d
0x180108dcd  mov     dword ptr [rsp+2D0h+Data], r12d
0x180108dd2  mov     dword ptr [rsp+2D0h+var_268], r12d
0x180108dd7  mov     [rsp+2D0h+dwDisposition], r12d
0x180108ddc  mov     [rsp+2D0h+bstrString], r12
0x180108de1  mov     [rbp+1D0h+var_248], r12
0x180108de5  mov     [rsp+2D0h+var_258], r12
0x180108dea  call    EnterpriseResourceManagerStore_NormalizeURI
0x180108def  mov     r14, [rbp+1D0h+var_248]
0x180108df3  mov     ebx, eax
0x180108df5  test    eax, eax
0x180108df7  js      loc_180108EC1
0x180108dfd  mov     edx, [rsi+2Ch]
0x180108e00  lea     r8, [rsp+2D0h+var_258]
0x180108e05  mov     rcx, r14
0x180108e08  call    AddURIPrefix
0x180108e0d  mov     ebx, eax
0x180108e0f  test    eax, eax
0x180108e11  js      loc_180108EC1
0x180108e17  cmp     [rsi], r12d
0x180108e1a  mov     r15d, r12d
0x180108e1d  mov     rbx, [rsi+20h]
0x180108e21  mov     rdi, [rsi+18h]
0x180108e25  setnz   r15b
0x180108e29  mov     rsi, [rsi+10h]
0x180108e2d  call    cs:__imp_RtlIsStateSeparationEnabled
0x180108e33  mov     [rsp+2D0h+lpSecurityAttributes], rbx
0x180108e38  lea     rcx, aSoftwareMicros_22; "Software\\Microsoft\\EnterpriseResource"...
0x180108e3f  test    al, al
0x180108e41  mov     qword ptr [rsp+2D0h+samDesired], rdi
0x180108e46  lea     r9, aOsdataSoftware_61; "OSData\\Software\\Microsoft\\Enterprise"...
0x180108e4d  mov     qword ptr [rsp+2D0h+dwOptions], rsi
0x180108e52  cmovz   r9, rcx
0x180108e56  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x180108e5d  mov     edi, 104h
0x180108e62  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x180108e66  mov     edx, edi; unsigned __int64
0x180108e68  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180108e6d  mov     ebx, eax
0x180108e6f  test    eax, eax
0x180108e71  js      short loc_180108EC1
0x180108e73  lea     rax, [rsp+2D0h+dwDisposition]
0x180108e78  xor     r9d, r9d; lpClass
0x180108e7b  mov     [rsp+2D0h+lpdwDisposition], rax; lpdwDisposition
0x180108e80  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x180108e84  lea     rax, [rsp+2D0h+hKey]
0x180108e89  xor     r8d, r8d; Reserved
0x180108e8c  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180108e91  lea     rcx, [r15-7FFFFFFFh]; hKey
0x180108e98  mov     [rsp+2D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180108e9d  mov     [rsp+2D0h+samDesired], 2011Fh; samDesired
0x180108ea5  mov     [rsp+2D0h+dwOptions], r12d; dwOptions
0x180108eaa  call    cs:__imp_RegCreateKeyExW
0x180108eb0  mov     ebx, eax
0x180108eb2  test    eax, eax
0x180108eb4  jz      short loc_180108F33
0x180108eb6  jle     short loc_180108EC1
0x180108eb8  movzx   ebx, ax
0x180108ebb  or      ebx, 80070000h
0x180108ec1  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180108ec6  test    rcx, rcx
0x180108ec9  jz      short loc_180108ED1
0x180108ecb  call    cs:__imp_RegCloseKey
0x180108ed1  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x180108ed6  call    cs:__imp_SysFreeString
0x180108edc  test    r14, r14
0x180108edf  jz      short loc_180108EF0
0x180108ee1  mov     rax, [r14]
0x180108ee4  mov     rcx, r14
0x180108ee7  mov     rax, [rax+10h]
0x180108eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108ef0  mov     rcx, [rsp+2D0h+var_258]
0x180108ef5  test    rcx, rcx
0x180108ef8  jz      short loc_180108F06
0x180108efa  mov     rax, [rcx]
0x180108efd  mov     rax, [rax+10h]
0x180108f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108f06  mov     eax, ebx
0x180108f08  mov     rcx, [rbp+1D0h+var_30]
0x180108f0f  xor     rcx, rsp; StackCookie
0x180108f12  call    __security_check_cookie
0x180108f17  lea     r11, [rsp+2D0h+var_20]
0x180108f1f  mov     rbx, [r11+38h]
0x180108f23  mov     rsi, [r11+40h]
0x180108f27  mov     rsp, r11
0x180108f2a  pop     r15
0x180108f2c  pop     r14
0x180108f2e  pop     r12
0x180108f30  pop     rdi
0x180108f31  pop     rbp
0x180108f32  retn
0x180108f33  cmp     [rsp+2D0h+dwDisposition], 2
0x180108f38  jnz     short loc_180108F9B
0x180108f3a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180108f3f  lea     rax, [rbp+1D0h+cbData]
0x180108f43  mov     qword ptr [rsp+2D0h+samDesired], rax; lpcbData
0x180108f48  lea     rdx, Value; "count"
0x180108f4f  lea     rax, [rsp+2D0h+Data]
0x180108f54  xor     r9d, r9d; lpType
0x180108f57  xor     r8d, r8d; lpReserved
0x180108f5a  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x180108f5f  call    cs:__imp_RegQueryValueExW
0x180108f65  mov     ebx, eax
0x180108f67  test    eax, eax
0x180108f69  jnz     loc_180108EB6
0x180108f6f  mov     rdx, [rsp+2D0h+var_258]
0x180108f74  lea     r8, [rsp+2D0h+var_26C]
0x180108f79  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180108f7e  xor     r9d, r9d
0x180108f81  call    SearchForResourceByValue
0x180108f86  mov     ebx, eax
0x180108f88  test    eax, eax
0x180108f8a  js      loc_180108EC1
0x180108f90  cmp     [rsp+2D0h+var_26C], r12d
0x180108f95  jnz     loc_180108EC1
0x180108f9b  mov     r9d, dword ptr [rsp+2D0h+Data]
0x180108fa0  lea     r8, aPathD; "Path%d"
0x180108fa7  mov     rdx, rdi; unsigned __int64
0x180108faa  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x180108fae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180108fb3  mov     ebx, eax
0x180108fb5  test    eax, eax
0x180108fb7  js      loc_180108EC1
0x180108fbd  mov     rcx, [rsp+2D0h+var_258]
0x180108fc2  lea     r9, [rsp+2D0h+bstrString]
0x180108fc7  xor     r8d, r8d
0x180108fca  xor     edx, edx
0x180108fcc  mov     rax, [rcx]
0x180108fcf  mov     rax, [rax+40h]
0x180108fd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180108fd8  mov     ebx, eax
0x180108fda  test    eax, eax
0x180108fdc  js      loc_180108EC1
0x180108fe2  mov     rcx, [rsp+2D0h+bstrString]; pbstr
0x180108fe7  call    cs:__imp_SysStringLen
0x180108fed  mov     rdx, [rsp+2D0h+bstrString]
0x180108ff2  mov     r9d, 1; dwType
0x180108ff8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180108ffd  xor     r8d, r8d; Reserved
0x180109000  lea     eax, ds:2[rax*2]
0x180109007  mov     [rsp+2D0h+samDesired], eax; cbData
0x18010900b  mov     qword ptr [rsp+2D0h+dwOptions], rdx; lpData
0x180109010  lea     rdx, [rbp+1D0h+SubKey]; lpValueName
0x180109014  call    cs:__imp_RegSetValueExW
0x18010901a  test    eax, eax
0x18010901c  jnz     short loc_18010905D
0x18010901e  mov     eax, dword ptr [rsp+2D0h+Data]
0x180109022  lea     rdx, Value; "count"
0x180109029  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18010902e  inc     eax
0x180109030  mov     dword ptr [rsp+2D0h+var_268], eax
0x180109034  mov     r9d, 4; dwType
0x18010903a  lea     rax, [rsp+2D0h+var_268]
0x18010903f  mov     [rsp+2D0h+samDesired], 4; cbData
0x180109047  xor     r8d, r8d; Reserved
0x18010904a  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x18010904f  call    cs:__imp_RegSetValueExW
0x180109055  test    eax, eax
0x180109057  jz      loc_180108EC1
0x18010905d  jg      loc_180108EB8
0x180109063  mov     ebx, eax
0x180109065  jmp     loc_180108EC1
```
