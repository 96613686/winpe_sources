# CProviderRegistrationCache::CallADVAPILookupSids(void *,ushort * *,ushort * *)

- ea: `0x180013ec8`
- end: `0x18001407f`
- name: `?CallADVAPILookupSids@CProviderRegistrationCache@@AEAAKPEAXPEAPEAG1@Z`
- size: `439`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, void *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015518`
- `0x1800157d4`

## callees

- `0x180003dc0`
- `0x180007ea0`
- `0x18000e8d6`
- `0x180013ec8`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f6c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013fa6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013fff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013fa6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180013fff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014041`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180013f62`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x180013f62`

## string_xrefs

- `0x180013f24`: `CProviderRegistrationCache::CallADVAPILookupSids`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::CallADVAPILookupSids(
        CProviderRegistrationCache *this,
        void *a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  unsigned int LastError; // ebx
  unsigned __int64 v8; // rax
  HLOCAL v9; // rdi
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rbx
  unsigned int v13; // ebx
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cchName; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+38h] [rbp-C8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+3Ch] [rbp-C4h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+270h] [rbp+170h] BYREF

  v15 = 0;
  cchName = 260;
  cchReferencedDomainName = 260;
  peUse = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v19,
    "CProviderRegistrationCache::CallADVAPILookupSids",
    (int *)a3,
    0,
    &v15);
  *a3 = 0;
  if ( LookupAccountSidLocalW(a2, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
  {
    if ( cchName + 1 < cchName || (v8 = 2LL * (cchName + 1), v8 > 0xFFFFFFFF) )
    {
      LastError = 534;
      goto LABEL_21;
    }
    v9 = LocalAlloc(0x40u, (unsigned int)v8);
    if ( !v9 )
    {
      LastError = 14;
LABEL_21:
      v15 = LastError;
      goto LABEL_22;
    }
    if ( cchName )
      memcpy_0(v9, Name, 2LL * cchName);
    if ( !a4 )
    {
LABEL_10:
      *a3 = (unsigned __int16 *)v9;
      LastError = 0;
      goto LABEL_21;
    }
    if ( cchReferencedDomainName + 1 < cchReferencedDomainName
      || (v10 = 2LL * (cchReferencedDomainName + 1), v10 > 0xFFFFFFFF) )
    {
      v13 = 534;
    }
    else
    {
      v11 = (unsigned __int16 *)LocalAlloc(0x40u, (unsigned int)v10);
      v12 = v11;
      if ( v11 )
      {
        if ( cchName )
          memcpy_0(v11, ReferencedDomainName, 2LL * cchReferencedDomainName);
        *a4 = v12;
        goto LABEL_10;
      }
      v13 = 14;
    }
    v15 = v13;
    LocalFree(v9);
    LastError = v15;
    goto LABEL_22;
  }
  LastError = GetLastError();
  v15 = LastError;
LABEL_22:
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v19);
  return LastError;
}

```

## disassembly

```asm
0x180013ec8  push    rbp
0x180013eca  push    rbx
0x180013ecb  push    rsi
0x180013ecc  push    rdi
0x180013ecd  push    r14
0x180013ecf  lea     rbp, [rsp-390h]
0x180013ed7  sub     rsp, 490h
0x180013ede  mov     rax, cs:__security_cookie
0x180013ee5  xor     rax, rsp
0x180013ee8  mov     [rbp+3B0h+var_30], rax
0x180013eef  mov     eax, 104h
0x180013ef4  mov     [rsp+4B0h+var_480], 0
0x180013efc  mov     [rsp+4B0h+cchName], eax
0x180013f00  lea     rcx, [rsp+4B0h+var_470]; this
0x180013f05  mov     [rsp+4B0h+var_478], eax
0x180013f09  mov     r14, r9
0x180013f0c  lea     rax, [rsp+4B0h+var_480]
0x180013f11  mov     [rsp+4B0h+var_474], 0
0x180013f19  mov     rbx, rdx
0x180013f1c  mov     [rsp+4B0h+cchReferencedDomainName], rax; unsigned int *
0x180013f21  xor     r9d, r9d; int *
0x180013f24  lea     rdx, aCproviderregis_1; "CProviderRegistrationCache::CallADVAPIL"...
0x180013f2b  mov     rsi, r8
0x180013f2e  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180013f33  lea     rax, [rsp+4B0h+var_474]
0x180013f38  mov     qword ptr [rsi], 0
0x180013f3f  mov     [rsp+4B0h+peUse], rax; peUse
0x180013f44  lea     r9, [rbp+3B0h+ReferencedDomainName]; ReferencedDomainName
0x180013f4b  lea     rax, [rsp+4B0h+var_478]
0x180013f50  mov     rcx, rbx; Sid
0x180013f53  lea     r8, [rsp+4B0h+cchName]; cchName
0x180013f58  mov     [rsp+4B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180013f5d  lea     rdx, [rsp+4B0h+Name]; Name
0x180013f62  call    cs:__imp_LookupAccountSidLocalW
0x180013f68  test    eax, eax
0x180013f6a  jnz     short loc_180013F7D
0x180013f6c  call    cs:__imp_GetLastError
0x180013f72  mov     ebx, eax
0x180013f74  mov     [rsp+4B0h+var_480], eax
0x180013f78  jmp     loc_180014056
0x180013f7d  mov     eax, [rsp+4B0h+cchName]
0x180013f81  lea     ecx, [rax+1]
0x180013f84  cmp     ecx, eax
0x180013f86  jb      loc_18001404D
0x180013f8c  mov     eax, ecx
0x180013f8e  mov     ebx, 0FFFFFFFFh
0x180013f93  add     rax, rax
0x180013f96  cmp     rax, rbx
0x180013f99  ja      loc_18001404D
0x180013f9f  mov     edx, eax; uBytes
0x180013fa1  mov     ecx, 40h ; '@'; uFlags
0x180013fa6  call    cs:__imp_LocalAlloc
0x180013fac  mov     rdi, rax
0x180013faf  test    rax, rax
0x180013fb2  jnz     short loc_180013FBC
0x180013fb4  lea     ebx, [rax+0Eh]
0x180013fb7  jmp     loc_180014052
0x180013fbc  mov     eax, [rsp+4B0h+cchName]
0x180013fc0  test    eax, eax
0x180013fc2  jz      short loc_180013FD7
0x180013fc4  mov     r8d, eax
0x180013fc7  lea     rdx, [rsp+4B0h+Name]; Src
0x180013fcc  add     r8, r8; Size
0x180013fcf  mov     rcx, rdi; void *
0x180013fd2  call    memcpy_0
0x180013fd7  test    r14, r14
0x180013fda  jnz     short loc_180013FE3
0x180013fdc  mov     [rsi], rdi
0x180013fdf  xor     ebx, ebx
0x180013fe1  jmp     short loc_180014052
0x180013fe3  mov     eax, [rsp+4B0h+var_478]
0x180013fe7  lea     ecx, [rax+1]
0x180013fea  cmp     ecx, eax
0x180013fec  jb      short loc_180014035
0x180013fee  mov     eax, ecx
0x180013ff0  add     rax, rax
0x180013ff3  cmp     rax, rbx
0x180013ff6  ja      short loc_180014035
0x180013ff8  mov     edx, eax; uBytes
0x180013ffa  mov     ecx, 40h ; '@'; uFlags
0x180013fff  call    cs:__imp_LocalAlloc
0x180014005  mov     rbx, rax
0x180014008  test    rax, rax
0x18001400b  jnz     short loc_180014012
0x18001400d  lea     ebx, [rax+0Eh]
0x180014010  jmp     short loc_18001403A
0x180014012  cmp     [rsp+4B0h+cchName], 0
0x180014017  jz      short loc_180014030
0x180014019  mov     r8d, [rsp+4B0h+var_478]
0x18001401e  lea     rdx, [rbp+3B0h+ReferencedDomainName]; Src
0x180014025  add     r8, r8; Size
0x180014028  mov     rcx, rbx; void *
0x18001402b  call    memcpy_0
0x180014030  mov     [r14], rbx
0x180014033  jmp     short loc_180013FDC
0x180014035  mov     ebx, 216h
0x18001403a  mov     rcx, rdi; hMem
0x18001403d  mov     [rsp+4B0h+var_480], ebx
0x180014041  call    cs:__imp_LocalFree
0x180014047  mov     ebx, [rsp+4B0h+var_480]
0x18001404b  jmp     short loc_180014056
0x18001404d  mov     ebx, 216h
0x180014052  mov     [rsp+4B0h+var_480], ebx
0x180014056  lea     rcx, [rsp+4B0h+var_470]; this
0x18001405b  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180014060  mov     eax, ebx
0x180014062  mov     rcx, [rbp+3B0h+var_30]
0x180014069  xor     rcx, rsp; StackCookie
0x18001406c  call    __security_check_cookie
0x180014071  add     rsp, 490h
0x180014078  pop     r14
0x18001407a  pop     rdi
0x18001407b  pop     rsi
0x18001407c  pop     rbx
0x18001407d  pop     rbp
0x18001407e  retn
```
