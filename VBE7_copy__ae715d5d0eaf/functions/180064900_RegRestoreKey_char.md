# _RegRestoreKey(char *)

- ea: `0x180064900`
- end: `0x180064ce7`
- name: `?_RegRestoreKey@@YAHPEAD@Z`
- size: `999`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180063868`
- `0x180063f8c`

## callees

- `0x180060ed4`
- `0x1800646cc`
- `0x180064900`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `ADVAPI32!RegEnumKeyA` at `0x1800649ff`
- `ADVAPI32!RegEnumKeyA` at `0x180064a8c`
- `ADVAPI32!RegEnumKeyA` at `0x180064b19`
- `ADVAPI32!RegEnumKeyA` at `0x180064b84`
- `ADVAPI32!RegEnumKeyA` at `0x180064c06`
- `ADVAPI32!RegEnumKeyA` at `0x180064c87`
- `ADVAPI32!RegEnumKeyA` at `0x1800649ff`
- `ADVAPI32!RegEnumKeyA` at `0x180064a8c`
- `ADVAPI32!RegEnumKeyA` at `0x180064b19`
- `ADVAPI32!RegEnumKeyA` at `0x180064b84`
- `ADVAPI32!RegEnumKeyA` at `0x180064c06`
- `ADVAPI32!RegEnumKeyA` at `0x180064c87`
- `ADVAPI32!RegDeleteKeyA` at `0x180064cb7`
- `ADVAPI32!RegDeleteKeyA` at `0x180064cb7`
- `ADVAPI32!RegOpenKeyA` at `0x18006494b`
- `ADVAPI32!RegOpenKeyA` at `0x180064970`
- `ADVAPI32!RegOpenKeyA` at `0x1800649a2`
- `ADVAPI32!RegOpenKeyA` at `0x1800649cf`
- `ADVAPI32!RegOpenKeyA` at `0x180064a35`
- `ADVAPI32!RegOpenKeyA` at `0x180064a5c`
- `ADVAPI32!RegOpenKeyA` at `0x180064ac2`
- `ADVAPI32!RegOpenKeyA` at `0x180064ae9`
- `ADVAPI32!RegOpenKeyA` at `0x180064b4f`
- `ADVAPI32!RegOpenKeyA` at `0x180064baf`
- `ADVAPI32!RegOpenKeyA` at `0x180064bd6`
- `ADVAPI32!RegOpenKeyA` at `0x180064c3c`
- `ADVAPI32!RegOpenKeyA` at `0x18006494b`
- `ADVAPI32!RegOpenKeyA` at `0x180064970`
- `ADVAPI32!RegOpenKeyA` at `0x1800649a2`
- `ADVAPI32!RegOpenKeyA` at `0x1800649cf`
- `ADVAPI32!RegOpenKeyA` at `0x180064a35`
- `ADVAPI32!RegOpenKeyA` at `0x180064a5c`
- `ADVAPI32!RegOpenKeyA` at `0x180064ac2`
- `ADVAPI32!RegOpenKeyA` at `0x180064ae9`
- `ADVAPI32!RegOpenKeyA` at `0x180064b4f`
- `ADVAPI32!RegOpenKeyA` at `0x180064baf`
- `ADVAPI32!RegOpenKeyA` at `0x180064bd6`
- `ADVAPI32!RegOpenKeyA` at `0x180064c3c`
- `ADVAPI32!RegCloseKey` at `0x180064984`
- `ADVAPI32!RegCloseKey` at `0x180064a0e`
- `ADVAPI32!RegCloseKey` at `0x180064a19`
- `ADVAPI32!RegCloseKey` at `0x180064a9b`
- `ADVAPI32!RegCloseKey` at `0x180064aa6`
- `ADVAPI32!RegCloseKey` at `0x180064b28`
- `ADVAPI32!RegCloseKey` at `0x180064b33`
- `ADVAPI32!RegCloseKey` at `0x180064b93`
- `ADVAPI32!RegCloseKey` at `0x180064c15`
- `ADVAPI32!RegCloseKey` at `0x180064c20`
- `ADVAPI32!RegCloseKey` at `0x180064c5f`
- `ADVAPI32!RegCloseKey` at `0x180064c94`
- `ADVAPI32!RegCloseKey` at `0x180064c9f`
- `ADVAPI32!RegCloseKey` at `0x180064984`
- `ADVAPI32!RegCloseKey` at `0x180064a0e`
- `ADVAPI32!RegCloseKey` at `0x180064a19`
- `ADVAPI32!RegCloseKey` at `0x180064a9b`
- `ADVAPI32!RegCloseKey` at `0x180064aa6`
- `ADVAPI32!RegCloseKey` at `0x180064b28`
- `ADVAPI32!RegCloseKey` at `0x180064b33`
- `ADVAPI32!RegCloseKey` at `0x180064b93`
- `ADVAPI32!RegCloseKey` at `0x180064c15`
- `ADVAPI32!RegCloseKey` at `0x180064c20`
- `ADVAPI32!RegCloseKey` at `0x180064c5f`
- `ADVAPI32!RegCloseKey` at `0x180064c94`
- `ADVAPI32!RegCloseKey` at `0x180064c9f`

## string_xrefs

- `0x180064add`: `Clsid`
- `0x180064c35`: `Replace`
- `0x18006499b`: `DeleteAP`
- `0x180064abb`: `DeleteCL`
- `0x180064a2e`: `DeleteIF`
- `0x180064b48`: `DeletePI`
- `0x180064ba8`: `DeleteTI`

## pseudocode

```c
__int64 __fastcall _RegRestoreKey(char *a1)
{
  unsigned int v2; // edi
  HKEY v4; // rbx
  HKEY v5; // rbx
  HKEY v6; // rsi
  DWORD v7; // ebx
  DWORD i; // edx
  HKEY v9; // rsi
  DWORD v10; // ebx
  DWORD j; // edx
  HKEY v12; // rsi
  DWORD v13; // ebx
  DWORD k; // edx
  DWORD v15; // ebx
  DWORD m; // edx
  HKEY v17; // rsi
  DWORD v18; // ebx
  DWORD n; // edx
  LSTATUS v20; // ebx
  HKEY v21; // [rsp+20h] [rbp-E0h] BYREF
  HKEY v22; // [rsp+28h] [rbp-D8h] BYREF
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  CHAR Name[256]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = 0;
  if ( RegOpenKeyA(HKEY_CLASSES_ROOT, aVbkeysave5, &phkResult) )
    return 0;
  v4 = hKey;
  if ( RegOpenKeyA(phkResult, a1, &hKey) )
  {
    hKey = v4;
    RegCloseKey(phkResult);
    return 0;
  }
  v5 = v21;
  if ( RegOpenKeyA(hKey, aDeleteap, &v21) )
  {
    v21 = v5;
  }
  else
  {
    v6 = v22;
    v7 = 0;
    if ( RegOpenKeyA(HKEY_CLASSES_ROOT, "AppID", &v22) )
    {
      v22 = v6;
    }
    else
    {
      for ( i = 0; !RegEnumKeyA(v21, i, Name, 0x100u); i = v7 )
      {
        ++v7;
        RegDeleteSubKeys(v22, Name);
      }
      RegCloseKey(v22);
    }
    RegCloseKey(v21);
    v5 = v21;
  }
  if ( RegOpenKeyA(hKey, aDeleteif, &v21) )
  {
    v21 = v5;
  }
  else
  {
    v9 = v22;
    v10 = 0;
    if ( RegOpenKeyA(HKEY_CLASSES_ROOT, szInterface, &v22) )
    {
      v22 = v9;
    }
    else
    {
      for ( j = 0; !RegEnumKeyA(v21, j, Name, 0x100u); j = v10 )
      {
        ++v10;
        RegDeleteSubKeys(v22, Name);
      }
      RegCloseKey(v22);
    }
    RegCloseKey(v21);
    v5 = v21;
  }
  if ( RegOpenKeyA(hKey, aDeletecl, &v21) )
  {
    v21 = v5;
  }
  else
  {
    v12 = v22;
    v13 = 0;
    if ( RegOpenKeyA(HKEY_CLASSES_ROOT, szCLSID, &v22) )
    {
      v22 = v12;
    }
    else
    {
      for ( k = 0; !RegEnumKeyA(v21, k, Name, 0x100u); k = v13 )
      {
        ++v13;
        RegDeleteSubKeys(v22, Name);
      }
      RegCloseKey(v22);
    }
    RegCloseKey(v21);
    v5 = v21;
  }
  if ( RegOpenKeyA(hKey, aDeletepi, &v21) )
  {
    v21 = v5;
  }
  else
  {
    v15 = 0;
    for ( m = 0; !RegEnumKeyA(v21, m, Name, 0x100u); m = v15 )
    {
      ++v15;
      RegDeleteSubKeys(HKEY_CLASSES_ROOT, Name);
    }
    RegCloseKey(v21);
    v5 = v21;
  }
  if ( RegOpenKeyA(hKey, aDeleteti, &v21) )
  {
    v21 = v5;
  }
  else
  {
    v17 = v22;
    v18 = 0;
    if ( RegOpenKeyA(HKEY_CLASSES_ROOT, szTypeLib, &v22) )
    {
      v22 = v17;
    }
    else
    {
      for ( n = 0; !RegEnumKeyA(v21, n, Name, 0x100u); n = v18 )
      {
        ++v18;
        RegDeleteSubKeys(v22, Name);
      }
      RegCloseKey(v22);
    }
    RegCloseKey(v21);
    v5 = v21;
  }
  if ( RegOpenKeyA(hKey, aReplace, &v21) )
  {
    v21 = v5;
  }
  else
  {
    _ErrRegCopyTree(v21, HKEY_CLASSES_ROOT);
    RegCloseKey(v21);
  }
  LOBYTE(v2) = RegDeleteSubKeys(phkResult, a1) == 0;
  v20 = RegEnumKeyA(phkResult, 0, Name, 0x100u);
  RegCloseKey(hKey);
  RegCloseKey(phkResult);
  if ( v20 == 259 )
    RegDeleteKeyA(HKEY_CLASSES_ROOT, aVbkeysave5);
  return v2;
}

```

## disassembly

```asm
0x180064900  mov     [rsp-8+arg_8], rbx
0x180064905  mov     [rsp-8+arg_10], rsi
0x18006490a  push    rbp
0x18006490b  push    rdi
0x18006490c  push    r12
0x18006490e  push    r14
0x180064910  push    r15
0x180064912  lea     rbp, [rsp-50h]
0x180064917  mov     eax, 150h
0x18006491c  call    _alloca_probe
0x180064921  sub     rsp, rax
0x180064924  mov     rax, cs:__security_cookie
0x18006492b  xor     rax, rsp
0x18006492e  mov     [rbp+70h+var_30], rax
0x180064932  mov     r14, rcx
0x180064935  mov     r12, 0FFFFFFFF80000000h
0x18006493c  lea     r8, [rsp+170h+phkResult]; phkResult
0x180064941  lea     rdx, aVbkeysave5; "VBKeySave5"
0x180064948  mov     rcx, r12; hKey
0x18006494b  call    cs:__imp_RegOpenKeyA
0x180064951  xor     edi, edi
0x180064953  test    eax, eax
0x180064955  jz      short loc_18006495E
0x180064957  xor     eax, eax
0x180064959  jmp     loc_180064CBF
0x18006495e  mov     rcx, [rsp+170h+phkResult]; hKey
0x180064963  mov     rbx, [rsp+170h+hKey]
0x180064968  lea     r8, [rsp+170h+hKey]; phkResult
0x18006496d  mov     rdx, r14; lpSubKey
0x180064970  call    cs:__imp_RegOpenKeyA
0x180064976  test    eax, eax
0x180064978  jz      short loc_18006498C
0x18006497a  mov     rcx, [rsp+170h+phkResult]; hKey
0x18006497f  mov     [rsp+170h+hKey], rbx
0x180064984  call    cs:__imp_RegCloseKey
0x18006498a  jmp     short loc_180064957
0x18006498c  mov     rcx, [rsp+170h+hKey]; hKey
0x180064991  mov     rbx, [rsp+170h+var_150]
0x180064996  lea     r8, [rsp+170h+var_150]; phkResult
0x18006499b  lea     rdx, aDeleteap; "DeleteAP"
0x1800649a2  call    cs:__imp_RegOpenKeyA
0x1800649a8  mov     r15d, 100h
0x1800649ae  test    eax, eax
0x1800649b0  jz      short loc_1800649B9
0x1800649b2  mov     [rsp+170h+var_150], rbx
0x1800649b7  jmp     short loc_180064A24
0x1800649b9  mov     rsi, [rsp+170h+var_148]
0x1800649be  lea     r8, [rsp+170h+var_148]; phkResult
0x1800649c3  lea     rdx, aAppid; "AppID"
0x1800649ca  mov     rcx, r12; hKey
0x1800649cd  mov     ebx, edi
0x1800649cf  call    cs:__imp_RegOpenKeyA
0x1800649d5  test    eax, eax
0x1800649d7  jz      short loc_1800649E0
0x1800649d9  mov     [rsp+170h+var_148], rsi
0x1800649de  jmp     short loc_180064A14
0x1800649e0  xor     edx, edx
0x1800649e2  jmp     short loc_1800649F2
0x1800649e4  lea     rdx, [rsp+170h+Name]; char *
0x1800649e9  inc     ebx
0x1800649eb  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x1800649f0  mov     edx, ebx; dwIndex
0x1800649f2  mov     rcx, [rsp+170h+var_150]; hKey
0x1800649f7  lea     r8, [rsp+170h+Name]; lpName
0x1800649fc  mov     r9d, r15d; cchName
0x1800649ff  call    cs:__imp_RegEnumKeyA
0x180064a05  mov     rcx, [rsp+170h+var_148]; HKEY
0x180064a0a  test    eax, eax
0x180064a0c  jz      short loc_1800649E4
0x180064a0e  call    cs:__imp_RegCloseKey
0x180064a14  mov     rcx, [rsp+170h+var_150]; hKey
0x180064a19  call    cs:__imp_RegCloseKey
0x180064a1f  mov     rbx, [rsp+170h+var_150]
0x180064a24  mov     rcx, [rsp+170h+hKey]; hKey
0x180064a29  lea     r8, [rsp+170h+var_150]; phkResult
0x180064a2e  lea     rdx, aDeleteif; "DeleteIF"
0x180064a35  call    cs:__imp_RegOpenKeyA
0x180064a3b  test    eax, eax
0x180064a3d  jz      short loc_180064A46
0x180064a3f  mov     [rsp+170h+var_150], rbx
0x180064a44  jmp     short loc_180064AB1
0x180064a46  mov     rsi, [rsp+170h+var_148]
0x180064a4b  lea     r8, [rsp+170h+var_148]; phkResult
0x180064a50  lea     rdx, ?szInterface@@3PADA; "Interface"
0x180064a57  mov     rcx, r12; hKey
0x180064a5a  mov     ebx, edi
0x180064a5c  call    cs:__imp_RegOpenKeyA
0x180064a62  test    eax, eax
0x180064a64  jz      short loc_180064A6D
0x180064a66  mov     [rsp+170h+var_148], rsi
0x180064a6b  jmp     short loc_180064AA1
0x180064a6d  xor     edx, edx
0x180064a6f  jmp     short loc_180064A7F
0x180064a71  lea     rdx, [rsp+170h+Name]; char *
0x180064a76  inc     ebx
0x180064a78  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180064a7d  mov     edx, ebx; dwIndex
0x180064a7f  mov     rcx, [rsp+170h+var_150]; hKey
0x180064a84  lea     r8, [rsp+170h+Name]; lpName
0x180064a89  mov     r9d, r15d; cchName
0x180064a8c  call    cs:__imp_RegEnumKeyA
0x180064a92  mov     rcx, [rsp+170h+var_148]; HKEY
0x180064a97  test    eax, eax
0x180064a99  jz      short loc_180064A71
0x180064a9b  call    cs:__imp_RegCloseKey
0x180064aa1  mov     rcx, [rsp+170h+var_150]; hKey
0x180064aa6  call    cs:__imp_RegCloseKey
0x180064aac  mov     rbx, [rsp+170h+var_150]
0x180064ab1  mov     rcx, [rsp+170h+hKey]; hKey
0x180064ab6  lea     r8, [rsp+170h+var_150]; phkResult
0x180064abb  lea     rdx, aDeletecl; "DeleteCL"
0x180064ac2  call    cs:__imp_RegOpenKeyA
0x180064ac8  test    eax, eax
0x180064aca  jz      short loc_180064AD3
0x180064acc  mov     [rsp+170h+var_150], rbx
0x180064ad1  jmp     short loc_180064B3E
0x180064ad3  mov     rsi, [rsp+170h+var_148]
0x180064ad8  lea     r8, [rsp+170h+var_148]; phkResult
0x180064add  lea     rdx, ?szCLSID@@3PADA; "Clsid"
0x180064ae4  mov     rcx, r12; hKey
0x180064ae7  mov     ebx, edi
0x180064ae9  call    cs:__imp_RegOpenKeyA
0x180064aef  test    eax, eax
0x180064af1  jz      short loc_180064AFA
0x180064af3  mov     [rsp+170h+var_148], rsi
0x180064af8  jmp     short loc_180064B2E
0x180064afa  xor     edx, edx
0x180064afc  jmp     short loc_180064B0C
0x180064afe  lea     rdx, [rsp+170h+Name]; char *
0x180064b03  inc     ebx
0x180064b05  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180064b0a  mov     edx, ebx; dwIndex
0x180064b0c  mov     rcx, [rsp+170h+var_150]; hKey
0x180064b11  lea     r8, [rsp+170h+Name]; lpName
0x180064b16  mov     r9d, r15d; cchName
0x180064b19  call    cs:__imp_RegEnumKeyA
0x180064b1f  mov     rcx, [rsp+170h+var_148]; HKEY
0x180064b24  test    eax, eax
0x180064b26  jz      short loc_180064AFE
0x180064b28  call    cs:__imp_RegCloseKey
0x180064b2e  mov     rcx, [rsp+170h+var_150]; hKey
0x180064b33  call    cs:__imp_RegCloseKey
0x180064b39  mov     rbx, [rsp+170h+var_150]
0x180064b3e  mov     rcx, [rsp+170h+hKey]; hKey
0x180064b43  lea     r8, [rsp+170h+var_150]; phkResult
0x180064b48  lea     rdx, aDeletepi; "DeletePI"
0x180064b4f  call    cs:__imp_RegOpenKeyA
0x180064b55  test    eax, eax
0x180064b57  jz      short loc_180064B60
0x180064b59  mov     [rsp+170h+var_150], rbx
0x180064b5e  jmp     short loc_180064B9E
0x180064b60  mov     ebx, edi
0x180064b62  xor     edx, edx
0x180064b64  jmp     short loc_180064B77
0x180064b66  lea     rdx, [rsp+170h+Name]; char *
0x180064b6b  mov     rcx, r12; HKEY
0x180064b6e  inc     ebx
0x180064b70  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180064b75  mov     edx, ebx; dwIndex
0x180064b77  mov     rcx, [rsp+170h+var_150]; hKey
0x180064b7c  lea     r8, [rsp+170h+Name]; lpName
0x180064b81  mov     r9d, r15d; cchName
0x180064b84  call    cs:__imp_RegEnumKeyA
0x180064b8a  test    eax, eax
0x180064b8c  jz      short loc_180064B66
0x180064b8e  mov     rcx, [rsp+170h+var_150]; hKey
0x180064b93  call    cs:__imp_RegCloseKey
0x180064b99  mov     rbx, [rsp+170h+var_150]
0x180064b9e  mov     rcx, [rsp+170h+hKey]; hKey
0x180064ba3  lea     r8, [rsp+170h+var_150]; phkResult
0x180064ba8  lea     rdx, aDeleteti; "DeleteTI"
0x180064baf  call    cs:__imp_RegOpenKeyA
0x180064bb5  test    eax, eax
0x180064bb7  jz      short loc_180064BC0
0x180064bb9  mov     [rsp+170h+var_150], rbx
0x180064bbe  jmp     short loc_180064C2B
0x180064bc0  mov     rsi, [rsp+170h+var_148]
0x180064bc5  lea     r8, [rsp+170h+var_148]; phkResult
0x180064bca  lea     rdx, ?szTypeLib@@3PADA; "TypeLib"
0x180064bd1  mov     rcx, r12; hKey
0x180064bd4  mov     ebx, edi
0x180064bd6  call    cs:__imp_RegOpenKeyA
0x180064bdc  test    eax, eax
0x180064bde  jz      short loc_180064BE7
0x180064be0  mov     [rsp+170h+var_148], rsi
0x180064be5  jmp     short loc_180064C1B
0x180064be7  xor     edx, edx
0x180064be9  jmp     short loc_180064BF9
0x180064beb  lea     rdx, [rsp+170h+Name]; char *
0x180064bf0  inc     ebx
0x180064bf2  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180064bf7  mov     edx, ebx; dwIndex
0x180064bf9  mov     rcx, [rsp+170h+var_150]; hKey
0x180064bfe  lea     r8, [rsp+170h+Name]; lpName
0x180064c03  mov     r9d, r15d; cchName
0x180064c06  call    cs:__imp_RegEnumKeyA
0x180064c0c  mov     rcx, [rsp+170h+var_148]; HKEY
0x180064c11  test    eax, eax
0x180064c13  jz      short loc_180064BEB
0x180064c15  call    cs:__imp_RegCloseKey
0x180064c1b  mov     rcx, [rsp+170h+var_150]; hKey
0x180064c20  call    cs:__imp_RegCloseKey
0x180064c26  mov     rbx, [rsp+170h+var_150]
0x180064c2b  mov     rcx, [rsp+170h+hKey]; hKey
0x180064c30  lea     r8, [rsp+170h+var_150]; phkResult
0x180064c35  lea     rdx, aReplace; "Replace"
0x180064c3c  call    cs:__imp_RegOpenKeyA
0x180064c42  test    eax, eax
0x180064c44  jz      short loc_180064C4D
0x180064c46  mov     [rsp+170h+var_150], rbx
0x180064c4b  jmp     short loc_180064C65
0x180064c4d  mov     rcx, [rsp+170h+var_150]; HKEY
0x180064c52  mov     rdx, r12; HKEY
0x180064c55  call    ?_ErrRegCopyTree@@YAIPEAUHKEY__@@0@Z; _ErrRegCopyTree(HKEY__ *,HKEY__ *)
0x180064c5a  mov     rcx, [rsp+170h+var_150]; hKey
0x180064c5f  call    cs:__imp_RegCloseKey
0x180064c65  mov     rcx, [rsp+170h+phkResult]; HKEY
0x180064c6a  mov     rdx, r14; char *
0x180064c6d  call    ?RegDeleteSubKeys@@YAIPEAUHKEY__@@PEAD@Z; RegDeleteSubKeys(HKEY__ *,char *)
0x180064c72  mov     rcx, [rsp+170h+phkResult]; hKey
0x180064c77  lea     r8, [rsp+170h+Name]; lpName
0x180064c7c  test    eax, eax
0x180064c7e  mov     r9d, r15d; cchName
0x180064c81  setz    dil
0x180064c85  xor     edx, edx; dwIndex
0x180064c87  call    cs:__imp_RegEnumKeyA
0x180064c8d  mov     rcx, [rsp+170h+hKey]; hKey
0x180064c92  mov     ebx, eax
0x180064c94  call    cs:__imp_RegCloseKey
0x180064c9a  mov     rcx, [rsp+170h+phkResult]; hKey
0x180064c9f  call    cs:__imp_RegCloseKey
0x180064ca5  cmp     ebx, 103h
0x180064cab  jnz     short loc_180064CBD
0x180064cad  lea     rdx, aVbkeysave5; "VBKeySave5"
0x180064cb4  mov     rcx, r12; hKey
0x180064cb7  call    cs:__imp_RegDeleteKeyA
0x180064cbd  mov     eax, edi
0x180064cbf  mov     rcx, [rbp+70h+var_30]
0x180064cc3  xor     rcx, rsp; StackCookie
0x180064cc6  call    __security_check_cookie
0x180064ccb  lea     r11, [rsp+170h+var_20]
0x180064cd3  mov     rbx, [r11+38h]
0x180064cd7  mov     rsi, [r11+40h]
0x180064cdb  mov     rsp, r11
0x180064cde  pop     r15
0x180064ce0  pop     r14
0x180064ce2  pop     r12
0x180064ce4  pop     rdi
0x180064ce5  pop     rbp
0x180064ce6  retn
```
