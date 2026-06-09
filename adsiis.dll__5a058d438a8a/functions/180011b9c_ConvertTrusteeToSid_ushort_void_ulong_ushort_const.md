# ConvertTrusteeToSid(ushort *,void * *,ulong *,ushort const *)

- ea: `0x180011b9c`
- end: `0x180011ca1`
- name: `?ConvertTrusteeToSid@@YAJPEAGPEAPEAXPEAKPEBG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName, void **, unsigned int *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800112e4`
- `0x180011d98`
- `0x180011e64`

## callees

- `0x180011b9c`
- `0x18001201c`
- `0x18001d652`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180011bfe`
- `msvcrt!_wcsicmp` at `0x180011bfe`
- `ADVAPI32!LookupAccountNameW` at `0x180011c36`
- `ADVAPI32!LookupAccountNameW` at `0x180011c36`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011c4f`
- `ACTIVEDS!__imp_AllocADsMem` at `0x180011c4f`

## pseudocode

```c
__int64 __fastcall ConvertTrusteeToSid(LPCWSTR lpAccountName, void **a2, unsigned int *a3, const unsigned __int16 *a4)
{
  int LastError; // ebx
  bool v5; // zf
  const WCHAR *v9; // rdi
  int v10; // eax
  void *v11; // rax
  void *v12; // rdi
  DWORD cbSid; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Sid[272]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+160h] [rbp+60h] BYREF

  LastError = 0;
  v5 = *lpAccountName == 92;
  cchReferencedDomainName = 260;
  peUse = 0;
  v9 = lpAccountName;
  cbSid = 260;
  if ( v5 || *lpAccountName == 47 )
    v9 = lpAccountName + 1;
  v10 = _wcsicmp(a4, L"localhost");
  if ( LookupAccountNameW(
         (LPCWSTR)((unsigned __int64)a4 & -(__int64)(v10 != 0)),
         v9,
         Sid,
         &cbSid,
         ReferencedDomainName,
         &cchReferencedDomainName,
         &peUse)
    || (LastError = HResultGetLastError(), LastError >= 0) )
  {
    v11 = AllocADsMem(cbSid);
    v12 = v11;
    if ( v11 )
    {
      memcpy_0(v11, Sid, cbSid);
      *a3 = cbSid;
      *a2 = v12;
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180011b9c  push    rbp
0x180011b9e  push    rbx
0x180011b9f  push    rsi
0x180011ba0  push    rdi
0x180011ba1  push    r14
0x180011ba3  push    r15
0x180011ba5  lea     rbp, [rsp-288h]
0x180011bad  sub     rsp, 388h
0x180011bb4  mov     rax, cs:__security_cookie
0x180011bbb  xor     rax, rsp
0x180011bbe  mov     [rbp+2B0h+var_40], rax
0x180011bc5  xor     ebx, ebx
0x180011bc7  mov     eax, 104h
0x180011bcc  cmp     word ptr [rcx], 5Ch ; '\'
0x180011bd0  mov     r15, r9
0x180011bd3  mov     r14, r8
0x180011bd6  mov     [rsp+3B0h+var_368], eax
0x180011bda  mov     rsi, rdx
0x180011bdd  mov     [rsp+3B0h+var_36C], ebx
0x180011be1  mov     rdi, rcx
0x180011be4  mov     [rsp+3B0h+cbSid], eax
0x180011be8  jz      short loc_180011BF0
0x180011bea  cmp     word ptr [rcx], 2Fh ; '/'
0x180011bee  jnz     short loc_180011BF4
0x180011bf0  add     rdi, 2
0x180011bf4  lea     rdx, aLocalhost_0; "localhost"
0x180011bfb  mov     rcx, r15; String1
0x180011bfe  call    cs:__imp__wcsicmp
0x180011c04  lea     r9, [rsp+3B0h+cbSid]; cbSid
0x180011c09  mov     rdx, rdi; lpAccountName
0x180011c0c  neg     eax
0x180011c0e  lea     r8, [rsp+3B0h+Sid]; Sid
0x180011c13  lea     rax, [rsp+3B0h+var_36C]
0x180011c18  mov     [rsp+3B0h+peUse], rax; peUse
0x180011c1d  sbb     rcx, rcx
0x180011c20  lea     rax, [rsp+3B0h+var_368]
0x180011c25  and     rcx, r15; lpSystemName
0x180011c28  mov     [rsp+3B0h+cchReferencedDomainName], rax; cchReferencedDomainName
0x180011c2d  lea     rax, [rbp+2B0h+var_250]
0x180011c31  mov     [rsp+3B0h+ReferencedDomainName], rax; ReferencedDomainName
0x180011c36  call    cs:__imp_LookupAccountNameW
0x180011c3c  test    eax, eax
0x180011c3e  jnz     short loc_180011C4B
0x180011c40  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x180011c45  mov     ebx, eax
0x180011c47  test    eax, eax
0x180011c49  js      short loc_180011C80
0x180011c4b  mov     ecx, [rsp+3B0h+cbSid]; cb
0x180011c4f  call    cs:__imp_AllocADsMem
0x180011c55  mov     rdi, rax
0x180011c58  test    rax, rax
0x180011c5b  jnz     short loc_180011C64
0x180011c5d  mov     ebx, 8007000Eh
0x180011c62  jmp     short loc_180011C80
0x180011c64  mov     r8d, [rsp+3B0h+cbSid]; Size
0x180011c69  lea     rdx, [rsp+3B0h+Sid]; Src
0x180011c6e  mov     rcx, rdi; void *
0x180011c71  call    memcpy_0
0x180011c76  mov     eax, [rsp+3B0h+cbSid]
0x180011c7a  mov     [r14], eax
0x180011c7d  mov     [rsi], rdi
0x180011c80  mov     eax, ebx
0x180011c82  mov     rcx, [rbp+2B0h+var_40]
0x180011c89  xor     rcx, rsp; StackCookie
0x180011c8c  call    __security_check_cookie
0x180011c91  add     rsp, 388h
0x180011c98  pop     r15
0x180011c9a  pop     r14
0x180011c9c  pop     rdi
0x180011c9d  pop     rsi
0x180011c9e  pop     rbx
0x180011c9f  pop     rbp
0x180011ca0  retn
```
