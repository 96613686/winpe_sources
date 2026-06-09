# CServerObject_ComRegistration::ValidRegistration(ushort const *,ProviderBitness,int &)

- ea: `0x1400145d8`
- end: `0x14001484f`
- name: `?ValidRegistration@CServerObject_ComRegistration@@QEAAJPEBGW4ProviderBitness@@AEAH@Z`
- size: `631`
- prototype: `__int64 __fastcall(__int64, __int64, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014fa4`

## callees

- `0x1400145d8`
- `0x140014860`
- `0x140046430`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400147cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140014705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001482b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140014705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14001482b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400146bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014744`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400146bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140014744`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001471d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014844`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001471d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140014844`
- `OLEAUT32!__imp_SysFreeString` at `0x14001475e`
- `OLEAUT32!__imp_SysFreeString` at `0x140014769`
- `OLEAUT32!__imp_SysFreeString` at `0x1400147ea`
- `OLEAUT32!__imp_SysFreeString` at `0x14001475e`
- `OLEAUT32!__imp_SysFreeString` at `0x140014769`
- `OLEAUT32!__imp_SysFreeString` at `0x1400147ea`

## pseudocode

```c
__int64 __fastcall CServerObject_ComRegistration::ValidRegistration(__int64 a1, __int64 a2, int a3, int *a4)
{
  int v7; // r15d
  signed int v8; // ebx
  REGSAM v9; // r15d
  int v10; // r14d
  BOOL v11; // edi
  LSTATUS v12; // eax
  LSTATUS v13; // eax
  __int64 result; // rax
  signed int LastError; // eax
  signed int v16; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v21; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[528]; // [rsp+50h] [rbp-B0h] BYREF

  lpSubKey = 0;
  WmiHelper::ConcatenateStrings(3u, (BSTR *)&lpSubKey, a2, L"\\", L"InProcServer32");
  if ( lpSubKey )
  {
    v21 = 0;
    WmiHelper::ConcatenateStrings(3u, (BSTR *)&v21, a2, L"\\", L"LocalServer32");
    if ( v21 )
    {
      hKey = 0;
      v7 = 512;
      if ( a3 != 32 )
        v7 = 256;
      v8 = 0;
      v9 = v7 | 0x20019;
      v10 = 0;
      v11 = 0;
      v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, v9, &hKey);
      if ( v12 )
      {
        if ( (unsigned int)(v12 - 2) > 1 )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError > 0 )
            v8 = (unsigned __int16)LastError | 0x80070000;
          if ( v8 < 0 )
            goto LABEL_11;
        }
      }
      else
      {
        Type = 1;
        cbData = 520;
        if ( !RegQueryValueExW(hKey, CServerObject_ComRegistration::s_Strings_Reg_Null, 0, &Type, Data, &cbData) )
          v11 = *(_WORD *)Data != 0;
        RegCloseKey(hKey);
      }
      hKey = 0;
      v13 = RegOpenKeyExW(HKEY_CLASSES_ROOT, v21, 0, v9, &hKey);
      if ( v13 )
      {
        if ( (unsigned int)(v13 - 2) > 1 )
        {
          v16 = GetLastError();
          v8 = v16;
          if ( v16 > 0 )
            v8 = (unsigned __int16)v16 | 0x80070000;
        }
      }
      else
      {
        cbData = 1;
        Type = 520;
        if ( !RegQueryValueExW(hKey, CServerObject_ComRegistration::s_Strings_Reg_Null, 0, &cbData, Data, &Type)
          && *(_WORD *)Data )
        {
          v10 = 1;
        }
        RegCloseKey(hKey);
      }
LABEL_11:
      SysFreeString((BSTR)lpSubKey);
      SysFreeString((BSTR)v21);
      result = (unsigned int)v8;
      *a4 = v10 | v11;
      return result;
    }
    SysFreeString((BSTR)lpSubKey);
  }
  return 2147749894LL;
}

```

## disassembly

```asm
0x1400145d8  mov     [rsp-8+arg_0], rbx
0x1400145dd  push    rbp
0x1400145de  push    rsi
0x1400145df  push    rdi
0x1400145e0  push    r12
0x1400145e2  push    r13
0x1400145e4  push    r14
0x1400145e6  push    r15
0x1400145e8  lea     rbp, [rsp-170h]
0x1400145f0  sub     rsp, 270h
0x1400145f7  mov     rax, cs:__security_cookie
0x1400145fe  xor     rax, rsp
0x140014601  mov     [rbp+1A0h+var_40], rax
0x140014608  xor     r13d, r13d
0x14001460b  lea     rax, aInprocserver32; "InProcServer32"
0x140014612  mov     esi, r8d
0x140014615  mov     [rsp+2A0h+lpSubKey], r13
0x14001461a  mov     r12, r9
0x14001461d  mov     [rsp+2A0h+phkResult], rax
0x140014622  mov     rbx, rdx
0x140014625  lea     r9, asc_14004DB1C; "\\"
0x14001462c  mov     r8, rdx
0x14001462f  lea     edi, [r13+3]
0x140014633  mov     ecx, edi
0x140014635  lea     rdx, [rsp+2A0h+lpSubKey]
0x14001463a  call    ?ConcatenateStrings@WmiHelper@@SA?AW4WmiStatusCode@@KPEAPEAGZZ; WmiHelper::ConcatenateStrings(ulong,ushort * *,...)
0x14001463f  cmp     [rsp+2A0h+lpSubKey], r13
0x140014644  jz      loc_1400147F0
0x14001464a  lea     rax, aLocalserver32; "LocalServer32"
0x140014651  mov     [rsp+2A0h+var_258], r13
0x140014656  lea     r9, asc_14004DB1C; "\\"
0x14001465d  mov     [rsp+2A0h+phkResult], rax
0x140014662  mov     r8, rbx
0x140014665  lea     rdx, [rsp+2A0h+var_258]
0x14001466a  mov     ecx, edi
0x14001466c  call    ?ConcatenateStrings@WmiHelper@@SA?AW4WmiStatusCode@@KPEAPEAGZZ; WmiHelper::ConcatenateStrings(ulong,ushort * *,...)
0x140014671  cmp     [rsp+2A0h+var_258], r13
0x140014676  jz      loc_1400147E5
0x14001467c  mov     rdx, [rsp+2A0h+lpSubKey]; lpSubKey
0x140014681  mov     eax, 100h
0x140014686  cmp     esi, 20h ; ' '
0x140014689  mov     [rsp+2A0h+hKey], r13
0x14001468e  mov     r15d, 200h
0x140014694  mov     rcx, 0FFFFFFFF80000000h; hKey
0x14001469b  cmovnz  r15d, eax
0x14001469f  mov     ebx, r13d
0x1400146a2  lea     rax, [rsp+2A0h+hKey]
0x1400146a7  or      r15d, 20019h
0x1400146ae  mov     r9d, r15d; samDesired
0x1400146b1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1400146b6  xor     r8d, r8d; ulOptions
0x1400146b9  mov     r14d, r13d
0x1400146bc  mov     edi, r13d
0x1400146bf  call    cs:__imp_RegOpenKeyExW
0x1400146c5  lea     esi, [r13+1]
0x1400146c9  test    eax, eax
0x1400146cb  jnz     loc_1400147A2
0x1400146d1  mov     rdx, cs:?s_Strings_Reg_Null@CServerObject_ComRegistration@@1PEBGEB; lpValueName
0x1400146d8  lea     rax, [rsp+2A0h+cbData]
0x1400146dd  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1400146e2  lea     r9, [rsp+2A0h+Type]; lpType
0x1400146e7  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x1400146ec  xor     r8d, r8d; lpReserved
0x1400146ef  lea     rax, [rsp+2A0h+Data]
0x1400146f4  mov     [rsp+2A0h+Type], esi
0x1400146f8  mov     [rsp+2A0h+phkResult], rax; lpData
0x1400146fd  mov     [rsp+2A0h+cbData], 208h
0x140014705  call    cs:__imp_RegQueryValueExW
0x14001470b  test    eax, eax
0x14001470d  jnz     short loc_140014718
0x14001470f  cmp     word ptr [rsp+2A0h+Data], r13w
0x140014715  cmovnz  edi, esi
0x140014718  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14001471d  call    cs:__imp_RegCloseKey
0x140014723  mov     rdx, [rsp+2A0h+var_258]; lpSubKey
0x140014728  lea     rax, [rsp+2A0h+hKey]
0x14001472d  mov     r9d, r15d; samDesired
0x140014730  mov     [rsp+2A0h+phkResult], rax; phkResult
0x140014735  xor     r8d, r8d; ulOptions
0x140014738  mov     [rsp+2A0h+hKey], r13
0x14001473d  mov     rcx, 0FFFFFFFF80000000h; hKey
0x140014744  call    cs:__imp_RegOpenKeyExW
0x14001474a  test    eax, eax
0x14001474c  jz      loc_1400147F7
0x140014752  add     eax, 0FFFFFFFEh
0x140014755  cmp     eax, esi
0x140014757  ja      short loc_1400147CB
0x140014759  mov     rcx, [rsp+2A0h+lpSubKey]; bstrString
0x14001475e  call    cs:__imp_SysFreeString
0x140014764  mov     rcx, [rsp+2A0h+var_258]; bstrString
0x140014769  call    cs:__imp_SysFreeString
0x14001476f  or      edi, r14d
0x140014772  mov     eax, ebx
0x140014774  mov     [r12], edi
0x140014778  mov     rcx, [rbp+1A0h+var_40]
0x14001477f  xor     rcx, rsp; StackCookie
0x140014782  call    __security_check_cookie
0x140014787  mov     rbx, [rsp+2A0h+arg_0]
0x14001478f  add     rsp, 270h
0x140014796  pop     r15
0x140014798  pop     r14
0x14001479a  pop     r13
0x14001479c  pop     r12
0x14001479e  pop     rdi
0x14001479f  pop     rsi
0x1400147a0  pop     rbp
0x1400147a1  retn
0x1400147a2  add     eax, 0FFFFFFFEh
0x1400147a5  cmp     eax, esi
0x1400147a7  jbe     loc_140014723
0x1400147ad  call    cs:__imp_GetLastError
0x1400147b3  mov     ebx, eax
0x1400147b5  test    eax, eax
0x1400147b7  jle     short loc_1400147C2
0x1400147b9  movzx   ebx, ax
0x1400147bc  or      ebx, 80070000h
0x1400147c2  test    ebx, ebx
0x1400147c4  js      short loc_140014759
0x1400147c6  jmp     loc_140014723
0x1400147cb  call    cs:__imp_GetLastError
0x1400147d1  mov     ebx, eax
0x1400147d3  test    eax, eax
0x1400147d5  jle     short loc_140014759
0x1400147d7  movzx   ebx, ax
0x1400147da  or      ebx, 80070000h
0x1400147e0  jmp     loc_140014759
0x1400147e5  mov     rcx, [rsp+2A0h+lpSubKey]; bstrString
0x1400147ea  call    cs:__imp_SysFreeString
0x1400147f0  mov     eax, 80041006h
0x1400147f5  jmp     short loc_140014778
0x1400147f7  mov     rdx, cs:?s_Strings_Reg_Null@CServerObject_ComRegistration@@1PEBGEB; lpValueName
0x1400147fe  lea     rax, [rsp+2A0h+Type]
0x140014803  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140014808  lea     r9, [rsp+2A0h+cbData]; lpType
0x14001480d  mov     [rsp+2A0h+lpcbData], rax; lpcbData
0x140014812  xor     r8d, r8d; lpReserved
0x140014815  lea     rax, [rsp+2A0h+Data]
0x14001481a  mov     [rsp+2A0h+cbData], esi
0x14001481e  mov     [rsp+2A0h+phkResult], rax; lpData
0x140014823  mov     [rsp+2A0h+Type], 208h
0x14001482b  call    cs:__imp_RegQueryValueExW
0x140014831  test    eax, eax
0x140014833  jnz     short loc_14001483F
0x140014835  cmp     word ptr [rsp+2A0h+Data], r13w
0x14001483b  cmovnz  r14d, esi
0x14001483f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140014844  call    cs:__imp_RegCloseKey
0x14001484a  jmp     loc_140014759
```
