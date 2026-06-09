# CSha1Hash::HashBytes(uchar const *,unsigned __int64)

- ea: `0x1800d7c88`
- end: `0x1800d7db7`
- name: `?HashBytes@CSha1Hash@@QEAAJPEBE_K@Z`
- size: `303`
- prototype: `__int64 __fastcall(CSha1Hash *__hidden this, BYTE *pbData, DWORD dwDataLen)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x1800d4870`
- `0x1800d4c40`
- `0x1800d5f50`
- `0x1800d8800`
- `0x1800db974`
- `0x1800dba5c`
- `0x1800dc200`
- `0x1800e2c10`
- `0x1800e2e30`
- `0x1800e30e0`
- `0x1800e68e0`
- `0x1800f0690`
- `0x1800f0d30`

## callees

- `0x180002ab0`
- `0x1800d7c88`
- `0x1800d7e60`
- `0x1800d8278`

## import_xrefs

- `ADVAPI32!CryptDestroyHash` at `0x1800d7d8b`
- `ADVAPI32!CryptDestroyHash` at `0x1800d7d8b`
- `ADVAPI32!CryptGetHashParam` at `0x1800d7d66`
- `ADVAPI32!CryptGetHashParam` at `0x1800d7d66`
- `ADVAPI32!CryptHashData` at `0x1800d7d2f`
- `ADVAPI32!CryptHashData` at `0x1800d7d2f`
- `ADVAPI32!CryptCreateHash` at `0x1800d7d0e`
- `ADVAPI32!CryptCreateHash` at `0x1800d7d0e`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d7cd2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800d7cd2`

## pseudocode

```c
__int64 __fastcall CSha1Hash::HashBytes(CSha1Hash *this, BYTE *pbData, unsigned __int64 dwDataLen)
{
  DWORD v3; // esi
  BOOL inited; // eax
  int v7; // ebx
  BOOL v8; // eax
  BOOL v9; // eax
  BOOL HashParam; // eax
  HCRYPTHASH hHash; // [rsp+30h] [rbp-48h] BYREF
  DWORD pdwDataLen; // [rsp+38h] [rbp-40h] BYREF
  BYTE pbDataa[24]; // [rsp+40h] [rbp-38h] BYREF

  *((_BYTE *)this + 20) = 0;
  v3 = dwDataLen;
  if ( dwDataLen > 0xFFFFFFFF )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    inited = InitOnceExecuteOnce(&CSha1Hash::s_initOnce, CSha1Hash::s_InitializeOnce, 0, 0);
    v7 = ResultFromWin32Bool(inited);
    if ( v7 >= 0 )
    {
      hHash = 0;
      v8 = CryptCreateHash(phProv, 0x8004u, 0, 0, &hHash);
      v7 = ResultFromWin32Bool(v8);
      if ( v7 >= 0 )
      {
        v9 = CryptHashData(hHash, pbData, v3, 0);
        v7 = ResultFromWin32Bool(v9);
        if ( v7 >= 0 )
        {
          pdwDataLen = 20;
          HashParam = CryptGetHashParam(hHash, 2u, pbDataa, &pdwDataLen, 0);
          v7 = ResultFromWin32Bool(HashParam);
          if ( v7 >= 0 )
            CSha1Hash::_SetHash(this, pbDataa);
        }
        CryptDestroyHash(hHash);
      }
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800d7c88  mov     [rsp+arg_18], rbx
0x1800d7c8d  push    rbp
0x1800d7c8e  push    rsi
0x1800d7c8f  push    rdi
0x1800d7c90  sub     rsp, 60h
0x1800d7c94  mov     rax, cs:__security_cookie
0x1800d7c9b  xor     rax, rsp
0x1800d7c9e  mov     [rsp+78h+var_20], rax
0x1800d7ca3  mov     eax, 0FFFFFFFFh
0x1800d7ca8  mov     byte ptr [rcx+14h], 0
0x1800d7cac  mov     rsi, r8
0x1800d7caf  mov     rbp, rdx
0x1800d7cb2  mov     rdi, rcx
0x1800d7cb5  cmp     r8, rax
0x1800d7cb8  ja      loc_1800D7D93
0x1800d7cbe  xor     r9d, r9d; Context
0x1800d7cc1  lea     rdx, ?s_InitializeOnce@CSha1Hash@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800d7cc8  xor     r8d, r8d; Parameter
0x1800d7ccb  lea     rcx, ?s_initOnce@CSha1Hash@@0T_RTL_RUN_ONCE@@A; InitOnce
0x1800d7cd2  call    cs:__imp_InitOnceExecuteOnce
0x1800d7cd8  mov     ecx, eax; int
0x1800d7cda  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800d7cdf  mov     ebx, eax
0x1800d7ce1  test    eax, eax
0x1800d7ce3  js      loc_1800D7D98
0x1800d7ce9  mov     rcx, cs:phProv; hProv
0x1800d7cf0  lea     rax, [rsp+78h+hHash]
0x1800d7cf5  xor     r9d, r9d; dwFlags
0x1800d7cf8  mov     [rsp+78h+phHash], rax; phHash
0x1800d7cfd  xor     r8d, r8d; hKey
0x1800d7d00  mov     [rsp+78h+hHash], 0
0x1800d7d09  mov     edx, 8004h; Algid
0x1800d7d0e  call    cs:__imp_CryptCreateHash
0x1800d7d14  mov     ecx, eax; int
0x1800d7d16  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800d7d1b  mov     ebx, eax
0x1800d7d1d  test    eax, eax
0x1800d7d1f  js      short loc_1800D7D98
0x1800d7d21  mov     rcx, [rsp+78h+hHash]; hHash
0x1800d7d26  mov     r8d, esi; dwDataLen
0x1800d7d29  xor     r9d, r9d; dwFlags
0x1800d7d2c  mov     rdx, rbp; pbData
0x1800d7d2f  call    cs:__imp_CryptHashData
0x1800d7d35  mov     ecx, eax; int
0x1800d7d37  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800d7d3c  mov     ebx, eax
0x1800d7d3e  test    eax, eax
0x1800d7d40  js      short loc_1800D7D86
0x1800d7d42  mov     rcx, [rsp+78h+hHash]; hHash
0x1800d7d47  lea     r9, [rsp+78h+pdwDataLen]; pdwDataLen
0x1800d7d4c  lea     r8, [rsp+78h+pbData]; pbData
0x1800d7d51  mov     [rsp+78h+pdwDataLen], 14h
0x1800d7d59  mov     edx, 2; dwParam
0x1800d7d5e  mov     dword ptr [rsp+78h+phHash], 0; dwFlags
0x1800d7d66  call    cs:__imp_CryptGetHashParam
0x1800d7d6c  mov     ecx, eax; int
0x1800d7d6e  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x1800d7d73  mov     ebx, eax
0x1800d7d75  test    eax, eax
0x1800d7d77  js      short loc_1800D7D86
0x1800d7d79  lea     rdx, [rsp+78h+pbData]; unsigned __int8 *
0x1800d7d7e  mov     rcx, rdi; this
0x1800d7d81  call    ?_SetHash@CSha1Hash@@AEAAXPEBE@Z; CSha1Hash::_SetHash(uchar const *)
0x1800d7d86  mov     rcx, [rsp+78h+hHash]; hHash
0x1800d7d8b  call    cs:__imp_CryptDestroyHash
0x1800d7d91  jmp     short loc_1800D7D98
0x1800d7d93  mov     ebx, 80070216h
0x1800d7d98  mov     eax, ebx
0x1800d7d9a  mov     rcx, [rsp+78h+var_20]
0x1800d7d9f  xor     rcx, rsp; StackCookie
0x1800d7da2  call    __security_check_cookie
0x1800d7da7  mov     rbx, [rsp+78h+arg_18]
0x1800d7daf  add     rsp, 60h
0x1800d7db3  pop     rdi
0x1800d7db4  pop     rsi
0x1800d7db5  pop     rbp
0x1800d7db6  retn
```
