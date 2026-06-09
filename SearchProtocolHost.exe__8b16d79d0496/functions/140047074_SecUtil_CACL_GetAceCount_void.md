# SecUtil::CACL::GetAceCount(void)

- ea: `0x140047074`
- end: `0x1400470de`
- name: `?GetAceCount@CACL@SecUtil@@QEBAKXZ`
- size: `106`
- prototype: `unsigned int __fastcall(SecUtil::CACL *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022778`
- `0x140047318`

## callees

- `0x140005240`
- `0x14003178c`
- `0x140047074`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400470a7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1400470a7`

## string_xrefs

- `0x1400470b6`: `onecoreuap\base\appmodel\search\common\secutil\secutil.cxx`

## pseudocode

```c
__int64 __fastcall SecUtil::CACL::GetAceCount(struct _ACL **this)
{
  struct _ACL *v1; // rcx
  __int64 result; // rax
  const char *v3; // r9
  __int64 pAclInformation; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *this;
  result = 0;
  pAclInformation = 0;
  v5 = 0;
  if ( v1 )
  {
    if ( !GetAclInformation(v1, &pAclInformation, 0xCu, AclSizeInformation) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x3B4,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\secutil\\secutil.cxx",
        v3);
    return (unsigned int)pAclInformation;
  }
  return result;
}

```

## disassembly

```asm
0x140047074  sub     rsp, 48h
0x140047078  mov     rax, cs:__security_cookie
0x14004707f  xor     rax, rsp
0x140047082  mov     [rsp+48h+var_18], rax
0x140047087  mov     rcx, [rcx]; pAcl
0x14004708a  xor     eax, eax
0x14004708c  mov     [rsp+48h+pAclInformation], rax
0x140047091  mov     [rsp+48h+var_20], eax
0x140047095  test    rcx, rcx
0x140047098  jz      short loc_1400470CC
0x14004709a  lea     r9d, [rax+2]; dwAclInformationClass
0x14004709e  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1400470a2  lea     rdx, [rsp+48h+pAclInformation]; pAclInformation
0x1400470a7  call    cs:__imp_GetAclInformation
0x1400470ad  test    eax, eax
0x1400470af  jnz     short loc_1400470C8
0x1400470b1  mov     rcx, [rsp+48h]; this
0x1400470b6  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400470bd  mov     edx, 3B4h; void *
0x1400470c2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400470c8  mov     eax, dword ptr [rsp+48h+pAclInformation]
0x1400470cc  mov     rcx, [rsp+48h+var_18]
0x1400470d1  xor     rcx, rsp; StackCookie
0x1400470d4  call    __security_check_cookie
0x1400470d9  add     rsp, 48h
0x1400470dd  retn
```
