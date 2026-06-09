# SecUtil::CACL::Reset(void)

- ea: `0x140027c90`
- end: `0x140027ced`
- name: `?Reset@CACL@SecUtil@@QEAAXXZ`
- size: `93`
- prototype: `void __fastcall(SecUtil::CACL *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14000d5c4`
- `0x14003a8e8`

## callees

- `0x140005264`
- `0x140005918`
- `0x140027c90`
- `0x14003178c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140027cc6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140027cc6`

## string_xrefs

- `0x140027cd5`: `onecoreuap\base\appmodel\Search\common\include\secutil_common.hxx`

## pseudocode

```c
void __fastcall SecUtil::CACL::Reset(void **this)
{
  void *v2; // rcx
  struct _ACL *v3; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *this;
  if ( v2 )
  {
    operator delete(v2);
    *this = 0;
  }
  v3 = (struct _ACL *)operator new[](8u);
  *this = v3;
  if ( !InitializeAcl(v3, 8u, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\secutil_common.hxx",
      v4);
}

```

## disassembly

```asm
0x140027c90  push    rbx
0x140027c92  sub     rsp, 20h
0x140027c96  mov     rbx, rcx
0x140027c99  mov     rcx, [rcx]; Block
0x140027c9c  test    rcx, rcx
0x140027c9f  jz      short loc_140027CAD
0x140027ca1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140027ca6  mov     qword ptr [rbx], 0
0x140027cad  mov     ecx, 8; unsigned __int64
0x140027cb2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140027cb7  mov     edx, 8; nAclLength
0x140027cbc  mov     [rbx], rax
0x140027cbf  mov     rcx, rax; pAcl
0x140027cc2  lea     r8d, [rdx-6]; dwAclRevision
0x140027cc6  call    cs:__imp_InitializeAcl
0x140027ccc  test    eax, eax
0x140027cce  jnz     short loc_140027CE7
0x140027cd0  mov     rcx, [rsp+28h]; this
0x140027cd5  lea     r8, aOnecoreuapBase_21; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140027cdc  mov     edx, 16Ah; void *
0x140027ce1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140027ce7  add     rsp, 20h
0x140027ceb  pop     rbx
0x140027cec  retn
```
