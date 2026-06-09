# GetClsIDInfo(_GUID *,ulong,ulong *)

- ea: `0x1800e6c90`
- end: `0x1800e6e66`
- name: `?GetClsIDInfo@@YAJPEAU_GUID@@KPEAK@Z`
- size: `470`
- prototype: `__int64 __fastcall(struct _GUID *, unsigned int, unsigned int *)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009683c`
- `0x180096f60`
- `0x1800a61cc`

## callees

- `0x180030880`
- `0x180058738`
- `0x18005cc10`
- `0x180073e8c`
- `0x1800e6c90`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e6d43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e6d75`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e6d43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800e6d75`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800e6dbf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800e6e07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800e6dbf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueA` at `0x1800e6e07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6d87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6e1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6d87`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6e1f`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e6cc3`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800e6cc3`

## string_xrefs

- `0x1800e6d02`: `CLSID\`

## pseudocode

```c
__int64 __fastcall GetClsIDInfo(struct _GUID *a1, __int64 a2, unsigned int *a3)
{
  char *v4; // rdx
  int v5; // r8d
  char *v6; // rsi
  unsigned int v7; // edi
  unsigned int v8; // r10d
  int v9; // r15d
  LSTATUS ValueA; // eax
  int v11; // ebx
  int v12; // r15d
  DWORD pcbData; // [rsp+40h] [rbp-69h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-61h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-59h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-51h] BYREF
  CHAR SubKey[48]; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pvData[64]; // [rsp+90h] [rbp-19h] BYREF

  lpsz = 0;
  StringFromCLSID(a1, &lpsz);
  if ( lpsz && (v6 = SzW2ADynamic(lpsz, v4, v5, 1), operator delete(lpsz), v6) )
  {
    hKey = 0;
    pcbData = 0;
    v7 = -2147467259;
    StringCchCopyA(SubKey, 0x2Fu, "CLSID\\");
    StringCchCatA(SubKey, v8, v6);
    if ( !RegOpenKeyExA(HKEY_CLASSES_ROOT, SubKey, 0, 0x2000000u, &hKey) )
    {
      phkResult = 0;
      v9 = 0;
      if ( !RegOpenKeyExA(hKey, "InprocServer32", 0, 0x2000000u, &phkResult) )
      {
        v9 = 3;
        RegCloseKey(phkResult);
      }
      pcbData = 64;
      ValueA = RegGetValueA(hKey, "LocalServer32", 0, 0x10000006u, 0, pvData, &pcbData);
      pcbData = 64;
      v11 = v9 | 4;
      if ( ValueA )
        v11 = v9;
      v12 = v11 | 0x100;
      if ( RegGetValueA(hKey, "DocObject", 0, 0x10000006u, 0, pvData, &pcbData) )
        v12 = v11;
      RegCloseKey(hKey);
      if ( v12 )
      {
        v7 = 0;
        *a3 = v12;
      }
    }
    operator delete(v6);
  }
  else
  {
    v7 = -2147024882;
    *a3 = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x1800e6c90  mov     [rsp-8+arg_8], rbx
0x1800e6c95  push    rbp
0x1800e6c96  push    rsi
0x1800e6c97  push    rdi
0x1800e6c98  push    r14
0x1800e6c9a  push    r15
0x1800e6c9c  lea     rbp, [rsp-37h]
0x1800e6ca1  sub     rsp, 0E0h
0x1800e6ca8  mov     rax, cs:__security_cookie
0x1800e6caf  xor     rax, rsp
0x1800e6cb2  mov     [rbp+57h+var_30], rax
0x1800e6cb6  xor     ebx, ebx
0x1800e6cb8  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800e6cbc  mov     [rbp+57h+lpsz], rbx
0x1800e6cc0  mov     r14, r8
0x1800e6cc3  call    cs:__imp_StringFromCLSID
0x1800e6cc9  mov     rcx, [rbp+57h+lpsz]; lpWideCharStr
0x1800e6ccd  test    rcx, rcx
0x1800e6cd0  jz      loc_1800E6E39
0x1800e6cd6  lea     r9d, [rbx+1]; int
0x1800e6cda  call    ?SzW2ADynamic@@YAPEADPEBGPEADHH@Z; SzW2ADynamic(ushort const *,char *,int,int)
0x1800e6cdf  mov     rcx, [rbp+57h+lpsz]; void *
0x1800e6ce3  mov     rsi, rax
0x1800e6ce6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e6ceb  test    rsi, rsi
0x1800e6cee  jz      loc_1800E6E39
0x1800e6cf4  lea     r10d, [rbx+2Fh]
0x1800e6cf8  mov     [rbp+57h+hKey], rbx
0x1800e6cfc  mov     edx, r10d; unsigned __int64
0x1800e6cff  mov     [rbp+57h+var_C0], ebx
0x1800e6d02  lea     r8, aClsid_4; "CLSID\\"
0x1800e6d09  mov     edi, 80004005h
0x1800e6d0e  lea     rcx, [rbp+57h+SubKey]; char *
0x1800e6d12  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800e6d17  mov     r8, rsi; char *
0x1800e6d1a  lea     rcx, [rbp+57h+SubKey]; char *
0x1800e6d1e  mov     edx, r10d; unsigned __int64
0x1800e6d21  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800e6d26  lea     rax, [rbp+57h+hKey]
0x1800e6d2a  mov     r9d, 2000000h; samDesired
0x1800e6d30  xor     r8d, r8d; ulOptions
0x1800e6d33  mov     [rsp+100h+phkResult], rax; phkResult
0x1800e6d38  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x1800e6d3c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800e6d43  call    cs:__imp_RegOpenKeyExA
0x1800e6d49  test    eax, eax
0x1800e6d4b  jnz     loc_1800E6E2F
0x1800e6d51  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e6d55  lea     rax, [rbp+57h+var_A8]
0x1800e6d59  mov     r9d, 2000000h; samDesired
0x1800e6d5f  mov     [rsp+100h+phkResult], rax; phkResult
0x1800e6d64  xor     r8d, r8d; ulOptions
0x1800e6d67  mov     [rbp+57h+var_A8], rbx
0x1800e6d6b  lea     rdx, aInprocserver32_1; "InprocServer32"
0x1800e6d72  mov     r15d, ebx
0x1800e6d75  call    cs:__imp_RegOpenKeyExA
0x1800e6d7b  test    eax, eax
0x1800e6d7d  jnz     short loc_1800E6D8D
0x1800e6d7f  mov     rcx, [rbp+57h+var_A8]; hKey
0x1800e6d83  lea     r15d, [rbx+3]
0x1800e6d87  call    cs:__imp_RegCloseKey
0x1800e6d8d  mov     rcx, [rbp+57h+hKey]; hkey
0x1800e6d91  lea     rax, [rbp+57h+var_C0]
0x1800e6d95  mov     [rsp+100h+pcbData], rax; pcbData
0x1800e6d9a  lea     rdx, aLocalserver32_0; "LocalServer32"
0x1800e6da1  lea     rax, [rbp+57h+var_70]
0x1800e6da5  mov     [rbp+57h+var_C0], 40h ; '@'
0x1800e6dac  mov     [rsp+100h+pvData], rax; pvData
0x1800e6db1  mov     r9d, 10000006h; dwFlags
0x1800e6db7  xor     r8d, r8d; lpValue
0x1800e6dba  mov     [rsp+100h+phkResult], rbx; pdwType
0x1800e6dbf  call    cs:__imp_RegGetValueA
0x1800e6dc5  mov     rcx, [rbp+57h+hKey]; hkey
0x1800e6dc9  lea     rdx, aDocobject; "DocObject"
0x1800e6dd0  mov     ebx, r15d
0x1800e6dd3  mov     [rbp+57h+var_C0], 40h ; '@'
0x1800e6dda  or      ebx, 4
0x1800e6ddd  mov     r9d, 10000006h; dwFlags
0x1800e6de3  test    eax, eax
0x1800e6de5  lea     rax, [rbp+57h+var_C0]
0x1800e6de9  mov     [rsp+100h+pcbData], rax; pcbData
0x1800e6dee  lea     rax, [rbp+57h+var_70]
0x1800e6df2  cmovnz  ebx, r15d
0x1800e6df6  mov     [rsp+100h+pvData], rax; pvData
0x1800e6dfb  xor     r8d, r8d; lpValue
0x1800e6dfe  mov     [rsp+100h+phkResult], 0; pdwType
0x1800e6e07  call    cs:__imp_RegGetValueA
0x1800e6e0d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800e6e11  mov     r15d, ebx
0x1800e6e14  bts     r15d, 8
0x1800e6e19  test    eax, eax
0x1800e6e1b  cmovnz  r15d, ebx
0x1800e6e1f  call    cs:__imp_RegCloseKey
0x1800e6e25  test    r15d, r15d
0x1800e6e28  jz      short loc_1800E6E2F
0x1800e6e2a  xor     edi, edi
0x1800e6e2c  mov     [r14], r15d
0x1800e6e2f  mov     rcx, rsi; void *
0x1800e6e32  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e6e37  jmp     short loc_1800E6E41
0x1800e6e39  mov     edi, 8007000Eh
0x1800e6e3e  mov     [r14], ebx
0x1800e6e41  mov     eax, edi
0x1800e6e43  mov     rcx, [rbp+57h+var_30]
0x1800e6e47  xor     rcx, rsp; StackCookie
0x1800e6e4a  call    __security_check_cookie
0x1800e6e4f  mov     rbx, [rsp+100h+arg_8]
0x1800e6e57  add     rsp, 0E0h
0x1800e6e5e  pop     r15
0x1800e6e60  pop     r14
0x1800e6e62  pop     rdi
0x1800e6e63  pop     rsi
0x1800e6e64  pop     rbp
0x1800e6e65  retn
```
