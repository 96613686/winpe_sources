# CSharedMemBlock::CreateSids(void * *,void * *,void * *,void * *,void * *)

- ea: `0x180001ec4`
- end: `0x180002091`
- name: `?CreateSids@CSharedMemBlock@@AEAAJPEAPEAX0000@Z`
- size: `461`
- prototype: `int(CSharedMemBlock *__hidden this, void **, void **, void **, void **, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180001c90`

## callees

- `0x180001ec4`
- `0x180023dd0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x180024bc4`
- `ADVAPI32!FreeSid` at `0x180024bd6`
- `ADVAPI32!FreeSid` at `0x180024bf9`
- `ADVAPI32!FreeSid` at `0x180024c0f`
- `ADVAPI32!FreeSid` at `0x180024bc4`
- `ADVAPI32!FreeSid` at `0x180024bd6`
- `ADVAPI32!FreeSid` at `0x180024bf9`
- `ADVAPI32!FreeSid` at `0x180024c0f`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001f4b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001f85`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001fbf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001ffc`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001f4b`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001f85`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001fbf`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180001ffc`
- `ADVAPI32!CreateWellKnownSid` at `0x180002032`
- `ADVAPI32!CreateWellKnownSid` at `0x180002032`
- `KERNEL32!LocalFree` at `0x18000207d`
- `KERNEL32!LocalFree` at `0x180024be8`
- `KERNEL32!LocalFree` at `0x18000207d`
- `KERNEL32!LocalFree` at `0x180024be8`
- `KERNEL32!LocalAlloc` at `0x180002014`
- `KERNEL32!LocalAlloc` at `0x180002014`
- `KERNEL32!GetLastError` at `0x180002072`
- `KERNEL32!GetLastError` at `0x180024b82`
- `KERNEL32!GetLastError` at `0x180002072`
- `KERNEL32!GetLastError` at `0x180024b82`

## pseudocode

```c
__int64 __fastcall CSharedMemBlock::CreateSids(
        CSharedMemBlock *this,
        void **pSid,
        void **a3,
        void **a4,
        void **a5,
        void **a6)
{
  PSID *v8; // rdi
  signed int v9; // ebx
  HLOCAL v10; // rax
  void *v11; // rsi
  signed int v13; // edi
  signed int LastError; // eax
  DWORD cbSid; // [rsp+60h] [rbp-20h] BYREF
  void **v16; // [rsp+68h] [rbp-18h]
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *pSid = 0;
  v8 = pSid;
  *a3 = 0;
  *a4 = 0;
  v16 = pSid;
  *a5 = 0;
  *a6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, pSid)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x223u, 0, 0, 0, 0, 0, 0, a3)
    || !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Eu, 0, 0, 0, 0, 0, 0, a5)
    || (v9 = 0, !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x22Fu, 0, 0, 0, 0, 0, 0, a6)) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  cbSid = 68;
  v10 = LocalAlloc(0, 0x44u);
  v11 = v10;
  if ( !v10 )
  {
    LOWORD(v13) = 8;
LABEL_15:
    v9 = (unsigned __int16)v13 | 0x80070000;
    goto LABEL_11;
  }
  if ( CreateWellKnownSid(WinBuiltinIUsersSid, 0, v10, &cbSid) )
  {
    *a4 = v11;
    goto LABEL_8;
  }
  v13 = GetLastError();
  LocalFree(v11);
  if ( v13 )
  {
    if ( v13 <= 0 )
    {
      v9 = v13;
      goto LABEL_11;
    }
    goto LABEL_15;
  }
LABEL_11:
  v8 = v16;
LABEL_8:
  if ( v9 < 0 )
  {
    if ( *v8 )
    {
      FreeSid(*v8);
      *v8 = 0;
    }
    if ( *a3 )
    {
      FreeSid(*a3);
      *a3 = 0;
    }
    if ( *a4 )
    {
      LocalFree(*a4);
      *a4 = 0;
    }
    if ( *a5 )
    {
      FreeSid(*a5);
      *a5 = 0;
    }
    if ( *a6 )
    {
      FreeSid(*a6);
      *a6 = 0;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180001ec4  mov     [rsp-38h+arg_0], rbx
0x180001ec9  push    rbp
0x180001eca  push    rsi
0x180001ecb  push    rdi
0x180001ecc  push    r12
0x180001ece  push    r13
0x180001ed0  push    r14
0x180001ed2  push    r15
0x180001ed4  mov     rbp, rsp
0x180001ed7  sub     rsp, 80h
0x180001ede  mov     rax, cs:__security_cookie
0x180001ee5  xor     rax, rsp
0x180001ee8  mov     [rbp+var_8], rax
0x180001eec  mov     r15, [rbp+arg_20]
0x180001ef0  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180001ef4  mov     r12, [rbp+arg_28]
0x180001ef8  xor     esi, esi
0x180001efa  mov     [rsp+80h+pSid], rdx; pSid
0x180001eff  mov     r14, r9
0x180001f02  mov     [rdx], rsi
0x180001f05  mov     r13, r8
0x180001f08  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x180001f0c  mov     rdi, rdx
0x180001f0f  mov     [r8], rsi
0x180001f12  lea     ebx, [rsi+20h]
0x180001f15  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x180001f19  mov     r8d, ebx; nSubAuthority0
0x180001f1c  mov     [r9], rsi
0x180001f1f  mov     r9d, 220h; nSubAuthority1
0x180001f25  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x180001f29  mov     [rbp+var_18], rdx
0x180001f2d  mov     dl, 2; nSubAuthorityCount
0x180001f2f  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x180001f33  mov     [r15], rsi
0x180001f36  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x180001f3a  mov     [r12], rsi
0x180001f3e  mov     dword ptr [rbp+pIdentifierAuthority.Value], esi
0x180001f41  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x180001f47  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x180001f4b  call    cs:__imp_AllocateAndInitializeSid
0x180001f51  test    eax, eax
0x180001f53  jz      loc_180024B82
0x180001f59  mov     [rsp+80h+pSid], r13; pSid
0x180001f5e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180001f62  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x180001f66  mov     r9d, 223h; nSubAuthority1
0x180001f6c  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x180001f70  mov     r8d, ebx; nSubAuthority0
0x180001f73  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x180001f77  mov     dl, 2; nSubAuthorityCount
0x180001f79  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x180001f7d  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x180001f81  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x180001f85  call    cs:__imp_AllocateAndInitializeSid
0x180001f8b  test    eax, eax
0x180001f8d  jz      loc_180024B82
0x180001f93  mov     [rsp+80h+pSid], r15; pSid
0x180001f98  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180001f9c  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x180001fa0  mov     r9d, 22Eh; nSubAuthority1
0x180001fa6  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x180001faa  mov     r8d, ebx; nSubAuthority0
0x180001fad  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x180001fb1  mov     dl, 2; nSubAuthorityCount
0x180001fb3  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x180001fb7  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x180001fbb  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x180001fbf  call    cs:__imp_AllocateAndInitializeSid
0x180001fc5  test    eax, eax
0x180001fc7  jz      loc_180024B82
0x180001fcd  mov     [rsp+80h+pSid], r12; pSid
0x180001fd2  lea     r8d, [rsi+20h]; nSubAuthority0
0x180001fd6  mov     [rsp+80h+nSubAuthority7], esi; nSubAuthority7
0x180001fda  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x180001fde  mov     [rsp+80h+nSubAuthority6], esi; nSubAuthority6
0x180001fe2  mov     r9d, 22Fh; nSubAuthority1
0x180001fe8  mov     [rsp+80h+nSubAuthority5], esi; nSubAuthority5
0x180001fec  mov     dl, 2; nSubAuthorityCount
0x180001fee  mov     [rsp+80h+nSubAuthority4], esi; nSubAuthority4
0x180001ff2  mov     ebx, esi
0x180001ff4  mov     [rsp+80h+nSubAuthority3], esi; nSubAuthority3
0x180001ff8  mov     [rsp+80h+nSubAuthority2], esi; nSubAuthority2
0x180001ffc  call    cs:__imp_AllocateAndInitializeSid
0x180002002  test    eax, eax
0x180002004  jz      loc_180024B82
0x18000200a  mov     edx, 44h ; 'D'; uBytes
0x18000200f  xor     ecx, ecx; uFlags
0x180002011  mov     [rbp+cbSid], edx
0x180002014  call    cs:__imp_LocalAlloc
0x18000201a  mov     rsi, rax
0x18000201d  test    rax, rax
0x180002020  jz      loc_180024BA0
0x180002026  xor     edx, edx; DomainSid
0x180002028  lea     r9, [rbp+cbSid]; cbSid
0x18000202c  mov     r8, rax; pSid
0x18000202f  lea     ecx, [rdx+3Eh]; WellKnownSidType
0x180002032  call    cs:__imp_CreateWellKnownSid
0x180002038  test    eax, eax
0x18000203a  jz      short loc_180002072
0x18000203c  mov     [r14], rsi
0x18000203f  xor     esi, esi
0x180002041  test    ebx, ebx
0x180002043  js      loc_180024BBC
0x180002049  mov     eax, ebx
0x18000204b  mov     rcx, [rbp+var_8]
0x18000204f  xor     rcx, rsp; StackCookie
0x180002052  call    __security_check_cookie
0x180002057  mov     rbx, [rsp+80h+arg_0]
0x18000205f  add     rsp, 80h
0x180002066  pop     r15
0x180002068  pop     r14
0x18000206a  pop     r13
0x18000206c  pop     r12
0x18000206e  pop     rdi
0x18000206f  pop     rsi
0x180002070  pop     rbp
0x180002071  retn
0x180002072  call    cs:__imp_GetLastError
0x180002078  mov     rcx, rsi; hMem
0x18000207b  mov     edi, eax
0x18000207d  call    cs:__imp_LocalFree
0x180002083  test    edi, edi
0x180002085  jnz     loc_180024BB3
0x18000208b  mov     rdi, [rbp+var_18]
0x18000208f  jmp     short loc_18000203F
0x180024b82  call    cs:__imp_GetLastError
0x180024b88  mov     ebx, eax
0x180024b8a  test    eax, eax
0x180024b8c  jle     loc_18000200A
0x180024b92  movzx   ebx, ax
0x180024b95  or      ebx, 80070000h
0x180024b9b  jmp     loc_18000200A
0x180024ba0  mov     edi, 8
0x180024ba5  movzx   ebx, di
0x180024ba8  or      ebx, 80070000h
0x180024bae  jmp     loc_18000208B
0x180024bb3  jg      short loc_180024BA5
0x180024bb5  mov     ebx, edi
0x180024bb7  jmp     loc_18000208B
0x180024bbc  mov     rcx, [rdi]; pSid
0x180024bbf  test    rcx, rcx
0x180024bc2  jz      short loc_180024BCD
0x180024bc4  call    cs:__imp_FreeSid
0x180024bca  mov     [rdi], rsi
0x180024bcd  mov     rcx, [r13+0]; pSid
0x180024bd1  test    rcx, rcx
0x180024bd4  jz      short loc_180024BE0
0x180024bd6  call    cs:__imp_FreeSid
0x180024bdc  mov     [r13+0], rsi
0x180024be0  mov     rcx, [r14]; hMem
0x180024be3  test    rcx, rcx
0x180024be6  jz      short loc_180024BF1
0x180024be8  call    cs:__imp_LocalFree
0x180024bee  mov     [r14], rsi
0x180024bf1  mov     rcx, [r15]; pSid
0x180024bf4  test    rcx, rcx
0x180024bf7  jz      short loc_180024C02
0x180024bf9  call    cs:__imp_FreeSid
0x180024bff  mov     [r15], rsi
0x180024c02  mov     rcx, [r12]; pSid
0x180024c06  test    rcx, rcx
0x180024c09  jz      loc_180002049
0x180024c0f  call    cs:__imp_FreeSid
0x180024c15  mov     [r12], rsi
0x180024c19  jmp     loc_180002049
```
