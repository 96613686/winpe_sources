# ATL::CAcl::GetLength(void)

- ea: `0x18000f744`
- end: `0x18000f7ae`
- name: `?GetLength@CAcl@ATL@@QEBAIXZ`
- size: `106`
- prototype: `unsigned int __fastcall(ATL::CAcl *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001039c`

## callees

- `0x18000f744`
- `0x180010e30`
- `0x18002bd78`
- `0x180031960`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000f787`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000f787`

## pseudocode

```c
__int64 __fastcall ATL::CAcl::GetLength(ATL::CAcl *this)
{
  struct _ACL *PACL; // rax
  __int64 pAclInformation; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+28h] [rbp-20h]

  PACL = (struct _ACL *)ATL::CAcl::GetPACL(this);
  pAclInformation = 0;
  v5 = 0;
  if ( *((_BYTE *)this + 16) )
    return 0;
  if ( !GetAclInformation(PACL, &pAclInformation, 0xCu, AclSizeInformation) )
    ATL::AtlThrowLastWin32();
  return HIDWORD(pAclInformation);
}

```

## disassembly

```asm
0x18000f744  push    rbx
0x18000f746  sub     rsp, 40h
0x18000f74a  mov     rax, cs:__security_cookie
0x18000f751  xor     rax, rsp
0x18000f754  mov     [rsp+48h+var_18], rax
0x18000f759  mov     rbx, rcx
0x18000f75c  call    ?GetPACL@CAcl@ATL@@QEBAPEBU_ACL@@XZ; ATL::CAcl::GetPACL(void)
0x18000f761  xor     ecx, ecx
0x18000f763  mov     [rsp+48h+pAclInformation], rcx
0x18000f768  mov     [rsp+48h+var_20], ecx
0x18000f76c  cmp     [rbx+10h], cl
0x18000f76f  jz      short loc_18000F775
0x18000f771  xor     eax, eax
0x18000f773  jmp     short loc_18000F79B
0x18000f775  mov     r9d, 2; dwAclInformationClass
0x18000f77b  lea     rdx, [rsp+48h+pAclInformation]; pAclInformation
0x18000f780  mov     rcx, rax; pAcl
0x18000f783  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18000f787  call    cs:__imp_GetAclInformation
0x18000f78d  test    eax, eax
0x18000f78f  jnz     short loc_18000F797
0x18000f791  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x18000f797  mov     eax, dword ptr [rsp+48h+pAclInformation+4]
0x18000f79b  mov     rcx, [rsp+48h+var_18]
0x18000f7a0  xor     rcx, rsp; StackCookie
0x18000f7a3  call    __security_check_cookie
0x18000f7a8  add     rsp, 40h
0x18000f7ac  pop     rbx
0x18000f7ad  retn
```
