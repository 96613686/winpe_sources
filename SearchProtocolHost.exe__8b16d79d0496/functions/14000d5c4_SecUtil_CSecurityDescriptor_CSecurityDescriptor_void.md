# SecUtil::CSecurityDescriptor::CSecurityDescriptor(void)

- ea: `0x14000d5c4`
- end: `0x14000d64a`
- name: `??0CSecurityDescriptor@SecUtil@@QEAA@XZ`
- size: `134`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140022778`
- `0x14003a8e8`

## callees

- `0x14000d5c4`
- `0x140027c90`
- `0x14003178c`
- `0x1400473a8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000d614`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x14000d614`

## string_xrefs

- `0x14000d623`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall SecUtil::CSecurityDescriptor::CSecurityDescriptor(_QWORD *pSecurityDescriptor)
{
  SecUtil::CACL *v2; // rcx
  __int64 v3; // rdx
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  pSecurityDescriptor[5] = 0;
  pSecurityDescriptor[6] = 0;
  v2 = (SecUtil::CACL *)(pSecurityDescriptor + 7);
  *(_QWORD *)v2 = 0;
  SecUtil::CACL::Reset(v2);
  pSecurityDescriptor[8] = 0;
  SecUtil::CACL::Reset((SecUtil::CACL *)(pSecurityDescriptor + 8));
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v4);
  SecUtil::CSecurityDescriptor::SetDacl((SecUtil::CSecurityDescriptor *)pSecurityDescriptor, v3, 0);
  return pSecurityDescriptor;
}

```

## disassembly

```asm
0x14000d5c4  mov     [rsp+arg_0], rcx
0x14000d5c9  push    rbx
0x14000d5ca  sub     rsp, 30h
0x14000d5ce  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000d5d7  mov     rbx, rcx
0x14000d5da  mov     qword ptr [rcx+28h], 0
0x14000d5e2  mov     qword ptr [rcx+30h], 0
0x14000d5ea  add     rcx, 38h ; '8'; this
0x14000d5ee  mov     qword ptr [rcx], 0
0x14000d5f5  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x14000d5fa  nop
0x14000d5fb  lea     rcx, [rbx+40h]; this
0x14000d5ff  mov     qword ptr [rcx], 0
0x14000d606  call    ?Reset@CACL@SecUtil@@QEAAXXZ; SecUtil::CACL::Reset(void)
0x14000d60b  nop
0x14000d60c  mov     edx, 1; dwRevision
0x14000d611  mov     rcx, rbx; pSecurityDescriptor
0x14000d614  call    cs:__imp_InitializeSecurityDescriptor
0x14000d61a  test    eax, eax
0x14000d61c  jnz     short loc_14000D635
0x14000d61e  mov     rcx, [rsp+38h]; this
0x14000d623  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14000d62a  mov     edx, 18Dh; void *
0x14000d62f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14000d635  xor     r8d, r8d; struct _ACL *
0x14000d638  mov     rcx, rbx; this
0x14000d63b  call    ?SetDacl@CSecurityDescriptor@SecUtil@@QEAAXHPEAU_ACL@@H@Z; SecUtil::CSecurityDescriptor::SetDacl(int,_ACL *,int)
0x14000d640  nop
0x14000d641  mov     rax, rbx
0x14000d644  add     rsp, 30h
0x14000d648  pop     rbx
0x14000d649  retn
```
