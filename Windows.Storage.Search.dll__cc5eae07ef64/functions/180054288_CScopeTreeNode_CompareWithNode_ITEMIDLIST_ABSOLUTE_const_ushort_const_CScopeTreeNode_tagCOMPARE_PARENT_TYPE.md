# CScopeTreeNode::CompareWithNode(_ITEMIDLIST_ABSOLUTE const *,ushort const *,CScopeTreeNode::tagCOMPARE_PARENT_TYPE *)

- ea: `0x180054288`
- end: `0x18005444a`
- name: `?CompareWithNode@CScopeTreeNode@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEBGPEAW4tagCOMPARE_PARENT_TYPE@1@@Z`
- size: `450`
- prototype: `int(CScopeTreeNode *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, const unsigned __int16 *, enum CScopeTreeNode::tagCOMPARE_PARENT_TYPE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b8b70`

## callees

- `0x1800127e0`
- `0x180054288`
- `0x1800b9608`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILIsParent` at `0x18005432c`
- `Windows.Storage!ILIsParent` at `0x180054431`
- `Windows.Storage!ILIsParent` at `0x18005432c`
- `Windows.Storage!ILIsParent` at `0x180054431`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18005439d`
- `Windows.Storage!SHCreateItemFromParsingName` at `0x18005439d`
- `Windows.Storage!ILIsEqual` at `0x180054314`
- `Windows.Storage!ILIsEqual` at `0x180054314`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800542c5`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800542de`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800542c5`
- `Windows.Storage!__imp_PathComparePaths` at `0x1800542de`

## pseudocode

```c
__int64 __fastcall CScopeTreeNode::CompareWithNode(
        CScopeTreeNode *this,
        const ITEMIDLIST *a2,
        const unsigned __int16 *a3,
        enum CScopeTreeNode::tagCOMPARE_PARENT_TYPE *a4)
{
  char *v4; // rdi
  int v9; // eax
  HRESULT v10; // edi
  __int64 v12; // [rsp+60h] [rbp+8h] BYREF
  void *ppv; // [rsp+78h] [rbp+20h] BYREF

  v4 = (char *)this + 32;
  *(_DWORD *)a4 = 3;
  if ( *((_WORD *)this + 16) && *a3 )
  {
    v9 = PathComparePaths((char *)this + 32, a3);
    if ( v9 == 2 )
    {
      *(_DWORD *)a4 = 0;
    }
    else if ( (v9 & 8) != 0 )
    {
      *(_DWORD *)a4 = 1;
    }
    else if ( (PathComparePaths(a3, v4) & 8) != 0 )
    {
      *(_DWORD *)a4 = 2;
    }
    return 0;
  }
  else
  {
    v10 = 0;
    if ( !*((_QWORD *)this + 1) || !*a3 )
      goto LABEL_30;
    if ( !CScopeTreeNode::_IsPathInCSC(this, a3) )
      goto LABEL_15;
    ppv = 0;
    v10 = SHCreateItemFromParsingName(
            L"shell:::{BD7A2E7B-21CB-41b2-A086-B309680C6B7E}\\*",
            0,
            &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
            &ppv);
    if ( v10 >= 0 )
    {
      v12 = 0;
      v10 = SHCreateScopeItemFromShellItem((IUnknown *)ppv, (__int64)&GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0, &v12);
      if ( v10 >= 0 )
      {
        if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 1) + 104LL))(
                *((_QWORD *)this + 1),
                v12,
                0) )
          *(_DWORD *)a4 = 1;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      if ( v10 >= 0 )
      {
LABEL_15:
        if ( *(_DWORD *)a4 == 3 )
        {
LABEL_30:
          if ( ILIsEqual(*((LPCITEMIDLIST *)this + 2), a2) )
          {
            *(_DWORD *)a4 = 0;
          }
          else if ( ILIsParent(*((LPCITEMIDLIST *)this + 2), a2, 0) )
          {
            *(_DWORD *)a4 = 1;
          }
          else if ( ILIsParent(a2, *((LPCITEMIDLIST *)this + 2), 0) )
          {
            *(_DWORD *)a4 = 2;
          }
        }
      }
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180054288  mov     [rsp+arg_8], rbx
0x18005428d  push    rbp
0x18005428e  push    rdi
0x18005428f  push    r12
0x180054291  push    r14
0x180054293  push    r15
0x180054295  sub     rsp, 30h
0x180054299  lea     rdi, [rcx+20h]
0x18005429d  mov     dword ptr [r9], 3
0x1800542a4  xor     r12d, r12d
0x1800542a7  mov     rbx, r9
0x1800542aa  mov     rbp, r8
0x1800542ad  mov     r15, rdx
0x1800542b0  mov     r14, rcx
0x1800542b3  cmp     [rdi], r12w
0x1800542b7  jz      short loc_180054304
0x1800542b9  cmp     [r8], r12w
0x1800542bd  jz      short loc_180054304
0x1800542bf  mov     rdx, r8
0x1800542c2  mov     rcx, rdi
0x1800542c5  call    cs:__imp_PathComparePaths
0x1800542cb  cmp     eax, 2
0x1800542ce  jz      short loc_1800542FF
0x1800542d0  test    al, 8
0x1800542d2  jnz     loc_18005435E
0x1800542d8  mov     rdx, rdi
0x1800542db  mov     rcx, rbp
0x1800542de  call    cs:__imp_PathComparePaths
0x1800542e4  test    al, 8
0x1800542e6  jnz     short loc_180054366
0x1800542e8  mov     edi, r12d
0x1800542eb  mov     rbx, [rsp+58h+arg_8]
0x1800542f0  mov     eax, edi
0x1800542f2  add     rsp, 30h
0x1800542f6  pop     r15
0x1800542f8  pop     r14
0x1800542fa  pop     r12
0x1800542fc  pop     rdi
0x1800542fd  pop     rbp
0x1800542fe  retn
0x1800542ff  mov     [rbx], r12d
0x180054302  jmp     short loc_1800542E8
0x180054304  mov     edi, r12d
0x180054307  cmp     [rcx+8], r12
0x18005430b  jnz     short loc_180054371
0x18005430d  mov     rcx, [r14+10h]; pidl1
0x180054311  mov     rdx, r15; pidl2
0x180054314  call    cs:__imp_ILIsEqual
0x18005431a  test    eax, eax
0x18005431c  jnz     loc_18005441F
0x180054322  mov     rcx, [r14+10h]; pidl1
0x180054326  xor     r8d, r8d; fImmediate
0x180054329  mov     rdx, r15; pidl2
0x18005432c  call    cs:__imp_ILIsParent
0x180054332  test    eax, eax
0x180054334  jz      loc_180054427
0x18005433a  mov     dword ptr [rbx], 1
0x180054340  jmp     short loc_1800542EB
0x180054342  mov     rcx, [rsp+58h+ppv]
0x180054347  mov     rax, [rcx]
0x18005434a  mov     rax, [rax+10h]
0x18005434e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054353  test    edi, edi
0x180054355  js      short loc_1800542EB
0x180054357  cmp     dword ptr [rbx], 3
0x18005435a  jnz     short loc_1800542EB
0x18005435c  jmp     short loc_18005430D
0x18005435e  mov     dword ptr [rbx], 1
0x180054364  jmp     short loc_1800542E8
0x180054366  mov     dword ptr [rbx], 2
0x18005436c  jmp     loc_1800542E8
0x180054371  cmp     [r8], r12w
0x180054375  jz      short loc_18005430D
0x180054377  mov     rdx, rbp; unsigned __int16 *
0x18005437a  call    ?_IsPathInCSC@CScopeTreeNode@@AEAAHPEBG@Z; CScopeTreeNode::_IsPathInCSC(ushort const *)
0x18005437f  test    eax, eax
0x180054381  jz      short loc_180054357
0x180054383  lea     r9, [rsp+58h+ppv]; ppv
0x180054388  mov     [rsp+58h+ppv], r12
0x18005438d  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180054394  xor     edx, edx; pbc
0x180054396  lea     rcx, pszPath; "shell:::{BD7A2E7B-21CB-41b2-A086-B30968"...
0x18005439d  call    cs:__imp_SHCreateItemFromParsingName
0x1800543a3  mov     edi, eax
0x1800543a5  test    eax, eax
0x1800543a7  js      loc_1800542EB
0x1800543ad  mov     rcx, [rsp+58h+ppv]; punk
0x1800543b2  lea     rax, [rsp+58h+arg_0]
0x1800543b7  xor     r9d, r9d
0x1800543ba  mov     [rsp+58h+var_30], rax; void *
0x1800543bf  lea     rax, _GUID_dd400ff4_a119_405f_970e_a9a5e7e828c0
0x1800543c6  mov     [rsp+58h+arg_0], r12
0x1800543cb  mov     [rsp+58h+var_38], rax; __int64
0x1800543d0  lea     edx, [r9+1]
0x1800543d4  lea     r8d, [r9+2]
0x1800543d8  call    SHCreateScopeItemFromShellItem
0x1800543dd  mov     edi, eax
0x1800543df  test    eax, eax
0x1800543e1  js      loc_180054342
0x1800543e7  mov     rcx, [r14+8]
0x1800543eb  xor     r8d, r8d
0x1800543ee  mov     rdx, [rsp+58h+arg_0]
0x1800543f3  mov     rax, [rcx]
0x1800543f6  mov     rax, [rax+68h]
0x1800543fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800543ff  test    eax, eax
0x180054401  jnz     short loc_180054409
0x180054403  mov     dword ptr [rbx], 1
0x180054409  mov     rcx, [rsp+58h+arg_0]
0x18005440e  mov     rax, [rcx]
0x180054411  mov     rax, [rax+10h]
0x180054415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005441a  jmp     loc_180054342
0x18005441f  mov     [rbx], r12d
0x180054422  jmp     loc_1800542EB
0x180054427  mov     rdx, [r14+10h]; pidl2
0x18005442b  xor     r8d, r8d; fImmediate
0x18005442e  mov     rcx, r15; pidl1
0x180054431  call    cs:__imp_ILIsParent
0x180054437  test    eax, eax
0x180054439  jz      loc_1800542EB
0x18005443f  mov     dword ptr [rbx], 2
0x180054445  jmp     loc_1800542EB
```
