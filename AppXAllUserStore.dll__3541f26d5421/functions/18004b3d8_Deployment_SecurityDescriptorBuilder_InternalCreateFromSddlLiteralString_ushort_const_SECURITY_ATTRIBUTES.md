# Deployment::SecurityDescriptorBuilder::InternalCreateFromSddlLiteralString(ushort const *,_SECURITY_ATTRIBUTES * *)

- ea: `0x18004b3d8`
- end: `0x18004b450`
- name: `?InternalCreateFromSddlLiteralString@SecurityDescriptorBuilder@Deployment@@AEAAJPEBGPEAPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `120`
- prototype: `int(Deployment::SecurityDescriptorBuilder *__hidden this, const unsigned __int16 *, struct _SECURITY_ATTRIBUTES **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004b3bc`

## callees

- `0x180018248`
- `0x18001a324`
- `0x18004b3d8`
- `0x18004b458`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b420`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004b420`

## string_xrefs

- `0x18004b3fa`: `onecore\admin\appmodel\common\securitydescriptorbuilder.cpp`
- `0x18004b42f`: `onecore\admin\appmodel\common\securitydescriptorbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Deployment::SecurityDescriptorBuilder::InternalCreateFromSddlLiteralString(
        PSECURITY_DESCRIPTOR *this,
        const unsigned __int16 *a2,
        PSECURITY_DESCRIPTOR **a3)
{
  int v6; // eax
  unsigned int v7; // edi
  const char *v9; // r9
  int v10; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v6 = Deployment::SecurityDescriptorBuilder::InternalReleaseAndInitializeSecurityDescriptor((Deployment::SecurityDescriptorBuilder *)this);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(a2, 1u, this + 1, 0) )
    {
      *a3 = this;
      return 0;
    }
    else
    {
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x81,
               (unsigned int)"onecore\\admin\\appmodel\\common\\securitydescriptorbuilder.cpp",
               v9);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\admin\\appmodel\\common\\securitydescriptorbuilder.cpp",
      (const char *)(unsigned int)v6,
      v10);
    return v7;
  }
}

```

## disassembly

```asm
0x18004b3d8  push    rbx
0x18004b3da  push    rbp
0x18004b3db  push    rsi
0x18004b3dc  push    rdi
0x18004b3dd  sub     rsp, 28h
0x18004b3e1  mov     rsi, r8
0x18004b3e4  mov     rbp, rdx
0x18004b3e7  mov     rbx, rcx
0x18004b3ea  call    ?InternalReleaseAndInitializeSecurityDescriptor@SecurityDescriptorBuilder@Deployment@@AEAAJXZ; Deployment::SecurityDescriptorBuilder::InternalReleaseAndInitializeSecurityDescriptor(void)
0x18004b3ef  mov     edi, eax
0x18004b3f1  test    eax, eax
0x18004b3f3  jns     short loc_18004B412
0x18004b3f5  mov     rcx, [rsp+48h]; this
0x18004b3fa  lea     r8, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\common\\secur"...
0x18004b401  mov     r9d, eax; char *
0x18004b404  mov     edx, 7Ch ; '|'; void *
0x18004b409  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b40e  mov     eax, edi
0x18004b410  jmp     short loc_18004B447
0x18004b412  xor     r9d, r9d; SecurityDescriptorSize
0x18004b415  lea     r8, [rbx+8]; SecurityDescriptor
0x18004b419  mov     rcx, rbp; StringSecurityDescriptor
0x18004b41c  lea     edx, [r9+1]; StringSDRevision
0x18004b420  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004b426  test    eax, eax
0x18004b428  jnz     short loc_18004B442
0x18004b42a  mov     rcx, [rsp+48h]; this
0x18004b42f  lea     r8, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\common\\secur"...
0x18004b436  mov     edx, 81h; void *
0x18004b43b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b440  jmp     short loc_18004B447
0x18004b442  mov     [rsi], rbx
0x18004b445  xor     eax, eax
0x18004b447  add     rsp, 28h
0x18004b44b  pop     rdi
0x18004b44c  pop     rsi
0x18004b44d  pop     rbp
0x18004b44e  pop     rbx
0x18004b44f  retn
```
