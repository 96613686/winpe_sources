# CIEApplicationAssociation::GetClsidFromProgID(ushort const *,_GUID *)

- ea: `0x1800e6190`
- end: `0x1800e63cc`
- name: `?GetClsidFromProgID@CIEApplicationAssociation@@SAJPEBGPEAU_GUID@@@Z`
- size: `572`
- prototype: `__int64 __fastcall(const unsigned __int16 *, LPCLSID pclsid)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18008906c`
- `0x1800e5fc0`
- `0x1800e608c`

## callees

- `0x1800150e0`
- `0x18001c470`
- `0x18001e340`
- `0x180030880`
- `0x180061440`
- `0x1800e6190`
- `0x18011baa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e637e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e637e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e635f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e6318`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e635f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e62ab`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e62ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e632a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800e632a`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800e6338`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x1800e6338`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e6371`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800e6371`

## string_xrefs

- `0x1800e625c`: `\Clsid`
- `0x1800e62c0`: `Clsid\`

## pseudocode

```c
__int64 __fastcall CIEApplicationAssociation::GetClsidFromProgID(const unsigned __int16 *a1, LPCLSID pclsid)
{
  HRESULT v4; // ebx
  char *v5; // rdi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r14
  unsigned int v8; // r10d
  HANDLE CurrentProcess; // rax
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL Wow64Process; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  OLECHAR sz[40]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[80]; // [rsp+A0h] [rbp-60h] BYREF

  pcbData = 78;
  phkResult = 0;
  if ( a1 && pclsid )
  {
    *pclsid = GUID_NULL;
    v4 = StringCchLengthW(a1, 0x7FFFFFFFu, (unsigned __int64 *)&phkResult);
    if ( v4 >= 0 )
    {
      v5 = (char *)phkResult + 7;
      if ( (HKEY)((char *)phkResult + 7) < phkResult )
      {
        return (unsigned int)-2147024362;
      }
      else
      {
        v6 = (unsigned __int16 *)operator new(saturated_mul((unsigned __int64)v5, 2u));
        v7 = v6;
        if ( v6 )
        {
          v4 = StringCchCopyW(v6, (unsigned __int64)v5, a1);
          if ( v4 >= 0 )
          {
            v4 = StringCchCatW(v7, (unsigned __int64)v5, L"\\Clsid");
            if ( v4 >= 0 )
            {
              if ( RegGetValueW(HKEY_CLASSES_ROOT, v7, 0, 0x10000006u, 0, sz, &pcbData) )
                goto LABEL_17;
              v4 = StringCchCopyW(SubKey, 0x50u, L"Clsid\\");
              if ( v4 >= 0 )
              {
                v4 = StringCchCatW(SubKey, v8, sz);
                if ( v4 >= 0 )
                {
                  if ( (phkResult = 0, RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &phkResult))
                    && ((Wow64Process = 0,
                         CurrentProcess = GetCurrentProcess(),
                         IsWow64Process(CurrentProcess, &Wow64Process),
                         Wow64Process)
                     || RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20219u, &phkResult))
                    || (v4 = CLSIDFromString(sz, pclsid), RegCloseKey(phkResult), v4 < 0) )
                  {
LABEL_17:
                    v4 = -2147221164;
                    *pclsid = GUID_NULL;
                  }
                }
              }
            }
          }
          operator delete(v7);
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800e6190  mov     [rsp-8+arg_10], rbx
0x1800e6195  push    rbp
0x1800e6196  push    rsi
0x1800e6197  push    rdi
0x1800e6198  push    r14
0x1800e619a  push    r15
0x1800e619c  lea     rbp, [rsp-50h]
0x1800e61a1  sub     rsp, 150h
0x1800e61a8  mov     rax, cs:__security_cookie
0x1800e61af  xor     rax, rsp
0x1800e61b2  mov     [rbp+70h+var_30], rax
0x1800e61b6  mov     [rsp+170h+var_124], 4Eh ; 'N'
0x1800e61be  mov     rsi, rdx
0x1800e61c1  mov     [rsp+170h+phkResult], 0
0x1800e61ca  mov     r15, rcx
0x1800e61cd  test    rcx, rcx
0x1800e61d0  jnz     short loc_1800E61DC
0x1800e61d2  mov     ebx, 80070057h
0x1800e61d7  jmp     loc_1800E63A7
0x1800e61dc  test    rsi, rsi
0x1800e61df  jz      short loc_1800E61D2
0x1800e61e1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800e61e8  lea     r8, [rsp+170h+phkResult]; unsigned __int64 *
0x1800e61ed  movdqu  xmmword ptr [rdx], xmm0
0x1800e61f1  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800e61f6  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800e61fb  mov     ebx, eax
0x1800e61fd  test    eax, eax
0x1800e61ff  js      loc_1800E63A7
0x1800e6205  mov     rax, [rsp+170h+phkResult]
0x1800e620a  lea     rdi, [rax+7]
0x1800e620e  cmp     rdi, rax
0x1800e6211  jb      loc_1800E63A2
0x1800e6217  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800e621e  mov     eax, 2
0x1800e6223  mul     rdi
0x1800e6226  cmovb   rax, rcx
0x1800e622a  mov     rcx, rax; Size
0x1800e622d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e6232  mov     r14, rax
0x1800e6235  test    rax, rax
0x1800e6238  jnz     short loc_1800E6244
0x1800e623a  mov     ebx, 8007000Eh
0x1800e623f  jmp     loc_1800E63A7
0x1800e6244  mov     r8, r15; unsigned __int16 *
0x1800e6247  mov     rdx, rdi; unsigned __int64
0x1800e624a  mov     rcx, r14; unsigned __int16 *
0x1800e624d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e6252  mov     ebx, eax
0x1800e6254  test    eax, eax
0x1800e6256  js      loc_1800E6398
0x1800e625c  lea     r8, aClsid_0; "\\Clsid"
0x1800e6263  mov     rdx, rdi; unsigned __int64
0x1800e6266  mov     rcx, r14; unsigned __int16 *
0x1800e6269  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e626e  mov     ebx, eax
0x1800e6270  test    eax, eax
0x1800e6272  js      loc_1800E6398
0x1800e6278  lea     rax, [rsp+170h+var_124]
0x1800e627d  mov     rdi, 0FFFFFFFF80000000h
0x1800e6284  mov     [rsp+170h+pcbData], rax; pcbData
0x1800e6289  mov     r9d, 10000006h; dwFlags
0x1800e628f  lea     rax, [rsp+170h+sz]
0x1800e6294  xor     r8d, r8d; lpValue
0x1800e6297  mov     [rsp+170h+pvData], rax; pvData
0x1800e629c  mov     rdx, r14; lpSubKey
0x1800e629f  mov     rcx, rdi; hkey
0x1800e62a2  mov     [rsp+170h+pdwType], 0; pdwType
0x1800e62ab  call    cs:__imp_RegGetValueW
0x1800e62b1  test    eax, eax
0x1800e62b3  jnz     loc_1800E6388
0x1800e62b9  lea     r10d, [rax+50h]
0x1800e62bd  mov     edx, r10d; unsigned __int64
0x1800e62c0  lea     r8, aClsid_6; "Clsid\\"
0x1800e62c7  lea     rcx, [rbp+70h+SubKey]; unsigned __int16 *
0x1800e62cb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e62d0  mov     ebx, eax
0x1800e62d2  test    eax, eax
0x1800e62d4  js      loc_1800E6398
0x1800e62da  lea     r8, [rsp+170h+sz]; unsigned __int16 *
0x1800e62df  mov     edx, r10d; unsigned __int64
0x1800e62e2  lea     rcx, [rbp+70h+SubKey]; unsigned __int16 *
0x1800e62e6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e62eb  mov     ebx, eax
0x1800e62ed  test    eax, eax
0x1800e62ef  js      loc_1800E6398
0x1800e62f5  lea     rax, [rsp+170h+phkResult]
0x1800e62fa  mov     [rsp+170h+phkResult], 0
0x1800e6303  mov     r9d, 20019h; samDesired
0x1800e6309  mov     [rsp+170h+pdwType], rax; phkResult
0x1800e630e  xor     r8d, r8d; ulOptions
0x1800e6311  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x1800e6315  mov     rcx, rdi; hKey
0x1800e6318  call    cs:__imp_RegOpenKeyExW
0x1800e631e  test    eax, eax
0x1800e6320  jz      short loc_1800E6369
0x1800e6322  mov     [rsp+170h+Wow64Process], 0
0x1800e632a  call    cs:__imp_GetCurrentProcess
0x1800e6330  mov     rcx, rax; hProcess
0x1800e6333  lea     rdx, [rsp+170h+Wow64Process]; Wow64Process
0x1800e6338  call    cs:__imp_IsWow64Process
0x1800e633e  cmp     [rsp+170h+Wow64Process], 0
0x1800e6343  jnz     short loc_1800E6388
0x1800e6345  lea     rax, [rsp+170h+phkResult]
0x1800e634a  mov     r9d, 20219h; samDesired
0x1800e6350  xor     r8d, r8d; ulOptions
0x1800e6353  mov     [rsp+170h+pdwType], rax; phkResult
0x1800e6358  lea     rdx, [rbp+70h+SubKey]; lpSubKey
0x1800e635c  mov     rcx, rdi; hKey
0x1800e635f  call    cs:__imp_RegOpenKeyExW
0x1800e6365  test    eax, eax
0x1800e6367  jnz     short loc_1800E6388
0x1800e6369  mov     rdx, rsi; pclsid
0x1800e636c  lea     rcx, [rsp+170h+sz]; lpsz
0x1800e6371  call    cs:__imp_CLSIDFromString
0x1800e6377  mov     rcx, [rsp+170h+phkResult]; hKey
0x1800e637c  mov     ebx, eax
0x1800e637e  call    cs:__imp_RegCloseKey
0x1800e6384  test    ebx, ebx
0x1800e6386  jns     short loc_1800E6398
0x1800e6388  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800e638f  mov     ebx, 80040154h
0x1800e6394  movdqu  xmmword ptr [rsi], xmm0
0x1800e6398  mov     rcx, r14; void *
0x1800e639b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800e63a0  jmp     short loc_1800E63A7
0x1800e63a2  mov     ebx, 80070216h
0x1800e63a7  mov     eax, ebx
0x1800e63a9  mov     rcx, [rbp+70h+var_30]
0x1800e63ad  xor     rcx, rsp; StackCookie
0x1800e63b0  call    __security_check_cookie
0x1800e63b5  mov     rbx, [rsp+170h+arg_10]
0x1800e63bd  add     rsp, 150h
0x1800e63c4  pop     r15
0x1800e63c6  pop     r14
0x1800e63c8  pop     rdi
0x1800e63c9  pop     rsi
0x1800e63ca  pop     rbp
0x1800e63cb  retn
```
