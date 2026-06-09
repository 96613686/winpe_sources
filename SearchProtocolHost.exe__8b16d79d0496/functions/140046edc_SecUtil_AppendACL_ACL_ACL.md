# SecUtil::AppendACL(_ACL *,_ACL *)

- ea: `0x140046edc`
- end: `0x140046ff2`
- name: `?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z`
- size: `278`
- prototype: `void __fastcall(PACL pAcl, PACL, struct _ACL *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140046d08`

## callees

- `0x140005240`
- `0x1400317c8`
- `0x140046edc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140046f87`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x140046f87`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140046f27`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x140046f27`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140046f63`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x140046f63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046fb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140046fb5`

## string_xrefs

- `0x140046f3c`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x140046fa0`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`
- `0x140046fc0`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
void __fastcall SecUtil::AppendACL(PACL pAcl, PACL a2, struct _ACL *a3)
{
  DWORD LastError; // eax
  DWORD i; // ebx
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD nAceListLength; // [rsp+20h] [rbp-38h]
  LPVOID pAce; // [rsp+30h] [rbp-28h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h] BYREF
  int v12; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a2 )
  {
    v11 = 0;
    v12 = 0;
    pAce = 0;
    if ( !GetAclInformation(a2, &v11, 0xCu, AclSizeInformation) )
    {
      LastError = GetLastError();
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x304,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        (const char *)LastError,
        nAceListLength);
    }
    for ( i = 0; i < (unsigned int)v11; ++i )
    {
      if ( !GetAce(a2, i, &pAce) )
      {
        v8 = GetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x30A,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
          (const char *)v8,
          nAceListLength);
      }
      if ( !AddAce(pAcl, 2u, 0xFFFFFFFF, pAce, *((unsigned __int16 *)pAce + 1)) )
      {
        v7 = GetLastError();
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x30F,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
          (const char *)v7,
          nAceListLength);
      }
    }
  }
}

```

## disassembly

```asm
0x140046edc  test    rdx, rdx
0x140046edf  jz      locret_140046FF1
0x140046ee5  mov     r11, rsp
0x140046ee8  mov     [r11+18h], rbx
0x140046eec  mov     [r11+20h], rsi
0x140046ef0  push    rdi
0x140046ef1  sub     rsp, 50h
0x140046ef5  mov     rax, cs:__security_cookie
0x140046efc  xor     rax, rsp
0x140046eff  mov     [rsp+58h+var_10], rax
0x140046f04  xor     eax, eax
0x140046f06  mov     rdi, rdx
0x140046f09  mov     rsi, rcx
0x140046f0c  mov     [r11-20h], rax
0x140046f10  lea     rdx, [r11-20h]; pAclInformation
0x140046f14  mov     [rsp+58h+var_18], eax
0x140046f18  mov     rcx, rdi; pAcl
0x140046f1b  mov     [r11-28h], rax
0x140046f1f  lea     r9d, [rax+2]; dwAclInformationClass
0x140046f23  lea     r8d, [rax+0Ch]; nAclInformationLength
0x140046f27  call    cs:__imp_GetAclInformation
0x140046f2d  test    eax, eax
0x140046f2f  jnz     short loc_140046F51
0x140046f31  call    cs:__imp_GetLastError
0x140046f37  mov     rcx, [rsp+58h]; this
0x140046f3c  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046f43  mov     r9d, eax; char *
0x140046f46  mov     edx, 304h; void *
0x140046f4b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140046f51  xor     ebx, ebx
0x140046f53  cmp     ebx, dword ptr [rsp+58h+var_20]
0x140046f57  jnb     short loc_140046FD5
0x140046f59  lea     r8, [rsp+58h+pAce]; pAce
0x140046f5e  mov     edx, ebx; dwAceIndex
0x140046f60  mov     rcx, rdi; pAcl
0x140046f63  call    cs:__imp_GetAce
0x140046f69  test    eax, eax
0x140046f6b  jz      short loc_140046FB5
0x140046f6d  mov     r9, [rsp+58h+pAce]; pAceList
0x140046f72  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x140046f76  mov     edx, 2; dwAceRevision
0x140046f7b  mov     rcx, rsi; pAcl
0x140046f7e  movzx   eax, word ptr [r9+2]
0x140046f83  mov     [rsp+58h+nAceListLength], eax; unsigned int
0x140046f87  call    cs:__imp_AddAce
0x140046f8d  test    eax, eax
0x140046f8f  jz      short loc_140046F95
0x140046f91  inc     ebx
0x140046f93  jmp     short loc_140046F53
0x140046f95  call    cs:__imp_GetLastError
0x140046f9b  mov     rcx, [rsp+58h]; this
0x140046fa0  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046fa7  mov     r9d, eax; char *
0x140046faa  mov     edx, 30Fh; void *
0x140046faf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140046fb5  call    cs:__imp_GetLastError
0x140046fbb  mov     rcx, [rsp+58h]; this
0x140046fc0  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x140046fc7  mov     r9d, eax; char *
0x140046fca  mov     edx, 30Ah; void *
0x140046fcf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140046fd5  mov     rcx, [rsp+58h+var_10]
0x140046fda  xor     rcx, rsp; StackCookie
0x140046fdd  call    __security_check_cookie
0x140046fe2  mov     rbx, [rsp+58h+arg_10]
0x140046fe7  mov     rsi, [rsp+58h+arg_18]
0x140046fec  add     rsp, 50h
0x140046ff0  pop     rdi
0x140046ff1  retn
```
