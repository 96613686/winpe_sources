# JDictsDictionaryManifest::GetChunkDescriptors(_ChunkDescriptorType *,uint *)

- ea: `0x180016980`
- end: `0x180016a6b`
- name: `?GetChunkDescriptors@JDictsDictionaryManifest@@UEAAJPEAU_ChunkDescriptorType@@PEAI@Z`
- size: `235`
- prototype: `__int64 __fastcall(JDictsDictionaryManifest *__hidden this, struct _ChunkDescriptorType *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callees

- `0x180005ca4`
- `0x1800167a4`
- `0x180016980`
- `0x180016f64`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016a54`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016a54`

## string_xrefs

- `0x180016a3a`: `mincore\textinput\dev\mtf\datasources\filterds\filterdictionary\lib\jdictsdictionarymanifest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall JDictsDictionaryManifest::GetChunkDescriptors(
        JDictsDictionaryManifest *this,
        struct _ChunkDescriptorType *a2,
        unsigned int *a3)
{
  unsigned int v7; // r12d
  char *v8; // rbx
  int v9; // edi
  __int64 v10; // rdx
  unsigned int v11; // esi
  int v12[4]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v13; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( !a2 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 48LL))(*((_QWORD *)this + 2));
  v7 = *a3;
  *(_OWORD *)v12 = 0;
  v13 = 0;
  std::vector<__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001>::resize(v12, v7);
  v8 = *(char **)v12;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned int *))(**((_QWORD **)this + 2) + 48LL))(
         *((_QWORD *)this + 2),
         *(_QWORD *)v12,
         a3);
  if ( v9 >= 0 )
  {
    v11 = 0;
    if ( *a3 )
    {
      while ( v11 < v7 )
      {
        v9 = JDictsDictionaryManifest::DecodeChunkDescriptor(
               this,
               (const struct __MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 *)&v8[28 * v11],
               (struct _ChunkDescriptorType *)((char *)a2 + 540 * v11));
        if ( v9 < 0 )
        {
          v10 = 134;
          goto LABEL_11;
        }
        if ( ++v11 >= *a3 )
          break;
      }
    }
  }
  else
  {
    v10 = 127;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\datasources\\filterds\\filterdictionary\\lib\\jdictsdictionarymanifest.cpp",
      (const char *)(unsigned int)v9,
      v12[0]);
  }
  if ( v8 )
    operator delete(v8);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180016980  push    rbx
0x180016982  push    rbp
0x180016983  push    rsi
0x180016984  push    rdi
0x180016985  push    r12
0x180016987  push    r14
0x180016989  push    r15
0x18001698b  sub     rsp, 40h
0x18001698f  mov     r14, r8
0x180016992  mov     r15, rdx
0x180016995  mov     rbp, rcx
0x180016998  test    rdx, rdx
0x18001699b  jnz     short loc_1800169B2
0x18001699d  mov     rcx, [rcx+10h]
0x1800169a1  mov     rax, [rcx]
0x1800169a4  mov     rax, [rax+30h]
0x1800169a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ad  jmp     loc_180016A5C
0x1800169b2  mov     r12d, [r8]
0x1800169b5  xorps   xmm0, xmm0
0x1800169b8  movdqu  xmmword ptr [rsp+78h+var_58], xmm0; int
0x1800169be  mov     [rsp+78h+var_48], 0
0x1800169c7  mov     edx, r12d
0x1800169ca  lea     rcx, [rsp+78h+var_58]
0x1800169cf  call    ?resize@?$vector@U__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001@@@std@@@std@@QEAAX_K@Z; std::vector<__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001>::resize(unsigned __int64)
0x1800169d4  mov     rcx, [rbp+10h]
0x1800169d8  mov     rax, [rcx]
0x1800169db  mov     r8, r14
0x1800169de  mov     rbx, qword ptr [rsp+78h+var_58]
0x1800169e3  mov     rdx, rbx
0x1800169e6  mov     rax, [rax+30h]
0x1800169ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ef  mov     edi, eax
0x1800169f1  test    eax, eax
0x1800169f3  jns     short loc_1800169FC
0x1800169f5  mov     edx, 7Fh
0x1800169fa  jmp     short loc_180016A37
0x1800169fc  xor     esi, esi
0x1800169fe  cmp     [r14], esi
0x180016a01  jbe     short loc_180016A4C
0x180016a03  cmp     esi, r12d
0x180016a06  jnb     short loc_180016A4C
0x180016a08  mov     eax, esi
0x180016a0a  imul    r8, rax, 21Ch
0x180016a11  add     r8, r15; struct _ChunkDescriptorType *
0x180016a14  imul    rdx, rax, 1Ch
0x180016a18  add     rdx, rbx; struct __MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 *
0x180016a1b  mov     rcx, rbp; this
0x180016a1e  call    ?DecodeChunkDescriptor@JDictsDictionaryManifest@@AEAAJAEBU__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001@@AEAU_ChunkDescriptorType@@@Z; JDictsDictionaryManifest::DecodeChunkDescriptor(__MIDL___MIDL_itf_ifilterdictionary_0000_0000_0001 const &,_ChunkDescriptorType &)
0x180016a23  mov     edi, eax
0x180016a25  test    eax, eax
0x180016a27  js      short loc_180016A32
0x180016a29  inc     esi
0x180016a2b  cmp     esi, [r14]
0x180016a2e  jb      short loc_180016A03
0x180016a30  jmp     short loc_180016A4C
0x180016a32  mov     edx, 86h; void *
0x180016a37  mov     r9d, edi; char *
0x180016a3a  lea     r8, aMincoreTextinp_9; "mincore\\textinput\\dev\\mtf\\datasourc"...
0x180016a41  mov     rcx, [rsp+78h]; this
0x180016a46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016a4b  nop
0x180016a4c  test    rbx, rbx
0x180016a4f  jz      short loc_180016A5A
0x180016a51  mov     rcx, rbx
0x180016a54  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016a5a  mov     eax, edi
0x180016a5c  add     rsp, 40h
0x180016a60  pop     r15
0x180016a62  pop     r14
0x180016a64  pop     r12
0x180016a66  pop     rdi
0x180016a67  pop     rsi
0x180016a68  pop     rbp
0x180016a69  pop     rbx
0x180016a6a  retn
```
