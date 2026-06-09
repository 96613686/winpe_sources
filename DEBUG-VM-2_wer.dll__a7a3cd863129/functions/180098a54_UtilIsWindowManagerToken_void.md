# UtilIsWindowManagerToken(void *)

- ea: `0x180098a54`
- end: `0x180098b30`
- name: `?UtilIsWindowManagerToken@@YAJPEAX@Z`
- size: `220`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002f34c`

## callees

- `0x18000716c`
- `0x18002db8c`
- `0x180048d44`
- `0x18004ac6c`
- `0x180050db0`
- `0x180098a54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180098af5`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098ac2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180098ac2`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098ae1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180098ae1`

## pseudocode

```c
__int64 __fastcall UtilIsWindowManagerToken(void *a1)
{
  PSID *pSid; // rax
  BOOL v2; // ebx
  unsigned int v3; // ebx
  DWORD LastError; // eax
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  _BYTE v8[24]; // [rsp+70h] [rbp+27h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+88h] [rbp+3Fh] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  pSid = (PSID *)utl::out_ptr<void,tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,>(
                   v8,
                   &SidToCheck);
  v2 = AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x5Au, 0, 0, 0, 0, 0, 0, 0, pSid);
  utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,void *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>,void *,>(v8);
  if ( v2 && CheckTokenMembership(0, SidToCheck, &IsMember) )
  {
    v3 = IsMember == 0;
  }
  else
  {
    LastError = GetLastError();
    v3 = ERROR_HR_FROM_WIN32(LastError);
  }
  tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&void * FreeSid(void *),0>>(&SidToCheck);
  return v3;
}

```

## disassembly

```asm
0x180098a54  mov     [rsp-8+arg_0], rbx
0x180098a59  mov     [rsp-8+arg_8], rdi
0x180098a5e  push    rbp
0x180098a5f  lea     rbp, [rsp-57h]
0x180098a64  sub     rsp, 0A0h
0x180098a6b  mov     rax, cs:__security_cookie
0x180098a72  xor     rax, rsp
0x180098a75  mov     [rbp+57h+var_10], rax
0x180098a79  xor     edi, edi
0x180098a7b  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180098a81  lea     rdx, [rbp+57h+SidToCheck]
0x180098a85  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], edi
0x180098a88  lea     rcx, [rbp+57h+var_30]
0x180098a8c  mov     [rbp+57h+SidToCheck], rdi
0x180098a90  mov     [rbp+57h+IsMember], edi
0x180098a93  call    ??$out_ptr@XV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@$$V@utl@@YA?A_PAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@@Z
0x180098a98  mov     [rsp+0A0h+pSid], rax; pSid
0x180098a9d  lea     r8d, [rdi+5Ah]; nSubAuthority0
0x180098aa1  mov     [rsp+0A0h+nSubAuthority7], edi; nSubAuthority7
0x180098aa5  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180098aa9  mov     [rsp+0A0h+nSubAuthority6], edi; nSubAuthority6
0x180098aad  xor     r9d, r9d; nSubAuthority1
0x180098ab0  mov     [rsp+0A0h+nSubAuthority5], edi; nSubAuthority5
0x180098ab4  mov     dl, 2; nSubAuthorityCount
0x180098ab6  mov     [rsp+0A0h+nSubAuthority4], edi; nSubAuthority4
0x180098aba  mov     [rsp+0A0h+nSubAuthority3], edi; nSubAuthority3
0x180098abe  mov     [rsp+0A0h+nSubAuthority2], edi; nSubAuthority2
0x180098ac2  call    cs:__imp_AllocateAndInitializeSid
0x180098ac8  lea     rcx, [rbp+57h+var_30]
0x180098acc  mov     ebx, eax
0x180098ace  call    ??1?$out_ptr_t@V?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@PEAX$$V@utl@@QEAA@XZ; utl::out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>::~out_ptr_t<tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>,void *,>(void)
0x180098ad3  test    ebx, ebx
0x180098ad5  jz      short loc_180098AF5
0x180098ad7  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180098adb  lea     r8, [rbp+57h+IsMember]; IsMember
0x180098adf  xor     ecx, ecx; TokenHandle
0x180098ae1  call    cs:__imp_CheckTokenMembership
0x180098ae7  test    eax, eax
0x180098ae9  jz      short loc_180098AF5
0x180098aeb  cmp     [rbp+57h+IsMember], edi
0x180098aee  mov     ebx, edi
0x180098af0  setz    bl
0x180098af3  jmp     short loc_180098B04
0x180098af5  call    cs:__imp_GetLastError
0x180098afb  mov     ecx, eax; unsigned int
0x180098afd  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180098b02  mov     ebx, eax
0x180098b04  lea     rcx, [rbp+57h+SidToCheck]
0x180098b08  call    ??1?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (*)(void *),&FreeSid(void *),0>>(void)
0x180098b0d  mov     eax, ebx
0x180098b0f  mov     rcx, [rbp+57h+var_10]
0x180098b13  xor     rcx, rsp; StackCookie
0x180098b16  call    __security_check_cookie
0x180098b1b  lea     r11, [rsp+0A0h+var_s0]
0x180098b23  mov     rbx, [r11+10h]
0x180098b27  mov     rdi, [r11+18h]
0x180098b2b  mov     rsp, r11
0x180098b2e  pop     rbp
0x180098b2f  retn
```
