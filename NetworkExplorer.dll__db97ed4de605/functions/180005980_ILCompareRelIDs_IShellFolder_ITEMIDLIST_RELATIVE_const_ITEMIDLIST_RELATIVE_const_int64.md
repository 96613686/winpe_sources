# ILCompareRelIDs(IShellFolder *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,__int64)

- ea: `0x180005980`
- end: `0x180005b0a`
- name: `?ILCompareRelIDs@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@1_J@Z`
- size: `394`
- prototype: `int(struct IShellFolder *, const struct _ITEMIDLIST_RELATIVE *, const struct _ITEMIDLIST_RELATIVE *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004db4`

## callees

- `0x180005980`
- `0x180010010`

## import_xrefs

- `SHELL32!__imp_ILCloneFirst` at `0x1800059cb`
- `SHELL32!__imp_ILCloneFirst` at `0x1800059cb`
- `SHELL32!__imp_ILFree` at `0x180005a87`
- `SHELL32!__imp_ILFree` at `0x180005a87`

## pseudocode

```c
__int64 __fastcall ILCompareRelIDs(
        struct IShellFolder *a1,
        const ITEMIDLIST *a2,
        const struct _ITEMIDLIST_RELATIVE *a3,
        __int64 a4)
{
  _WORD *v5; // rdi
  _WORD *v7; // rsi
  ITEMIDLIST *v8; // rbx
  struct IShellFolderVtbl *lpVtbl; // rax
  int v10; // ebp
  unsigned int v12; // r15d
  __int64 v14; // [rsp+68h] [rbp+10h] BYREF
  __int64 v15; // [rsp+70h] [rbp+18h] BYREF

  v5 = (_WORD *)((char *)a3 + *(unsigned __int16 *)a3);
  v7 = (USHORT *)((char *)&a2->mkid.cb + a2->mkid.cb);
  if ( v7 && *v7 )
  {
    if ( v5 && *v5 )
    {
      v8 = ILCloneFirst(a2);
      if ( v8 )
      {
        lpVtbl = a1->lpVtbl;
        v14 = 0;
        v10 = ((__int64 (__fastcall *)(struct IShellFolder *, ITEMIDLIST *, _QWORD, GUID *, __int64 *))lpVtbl->BindToObject)(
                a1,
                v8,
                0,
                &GUID_000214e6_0000_0000_c000_000000000046,
                &v14);
        if ( v10 >= 0 )
        {
          v15 = 0;
          if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v14)(
                 v14,
                 &GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1,
                 &v15) < 0 )
            a4 = 0;
          else
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          v10 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _WORD *, _WORD *))(*(_QWORD *)v14 + 56LL))(
                  v14,
                  a4 & 0xFFFFFFFFFFFF0000uLL,
                  v7,
                  v5);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
        ILFree(v8);
        return (unsigned int)v10;
      }
      else
      {
        return 2147942414LL;
      }
    }
    else
    {
      return 1;
    }
  }
  else
  {
    v12 = 0;
    if ( v5 && *v5 )
      return 0xFFFF;
    return v12;
  }
}

```

## disassembly

```asm
0x180005980  push    rsi
0x180005982  push    rdi
0x180005983  push    r12
0x180005985  push    r14
0x180005987  push    r15
0x180005989  sub     rsp, 30h
0x18000598d  movzx   edi, word ptr [r8]
0x180005991  mov     r12, r9
0x180005994  movzx   esi, word ptr [rdx]
0x180005997  add     rdi, r8
0x18000599a  mov     r14, rcx
0x18000599d  add     rsi, rdx
0x1800059a0  jz      loc_180005ABD
0x1800059a6  cmp     word ptr [rsi], 0
0x1800059aa  jz      loc_180005ABD
0x1800059b0  test    rdi, rdi
0x1800059b3  jz      loc_180005AE9
0x1800059b9  cmp     word ptr [rdi], 0
0x1800059bd  jz      loc_180005AE9
0x1800059c3  mov     rcx, rdx; pidl
0x1800059c6  mov     [rsp+58h+arg_0], rbx
0x1800059cb  call    cs:__imp_ILCloneFirst
0x1800059d1  mov     rbx, rax
0x1800059d4  test    rax, rax
0x1800059d7  jz      loc_180005AA6
0x1800059dd  mov     rax, [r14]
0x1800059e0  lea     rcx, [rsp+58h+arg_8]
0x1800059e5  mov     [rsp+58h+var_38], rcx
0x1800059ea  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046
0x1800059f1  xor     r15d, r15d
0x1800059f4  mov     [rsp+58h+arg_18], rbp
0x1800059f9  xor     r8d, r8d
0x1800059fc  mov     [rsp+58h+arg_8], r15
0x180005a01  mov     rax, [rax+28h]
0x180005a05  mov     rdx, rbx
0x180005a08  mov     rcx, r14
0x180005a0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a10  mov     ebp, eax
0x180005a12  test    eax, eax
0x180005a14  js      short loc_180005A84
0x180005a16  mov     rcx, [rsp+58h+arg_8]
0x180005a1b  lea     r8, [rsp+58h+arg_10]
0x180005a20  mov     [rsp+58h+arg_10], r15
0x180005a25  lea     rdx, _GUID_93f2f68c_1d1b_11d3_a30e_00c04f79abd1
0x180005a2c  mov     rax, [rcx]
0x180005a2f  mov     rax, [rax]
0x180005a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a37  test    eax, eax
0x180005a39  js      loc_180005AFB
0x180005a3f  mov     rcx, [rsp+58h+arg_10]
0x180005a44  mov     rax, [rcx]
0x180005a47  mov     rax, [rax+10h]
0x180005a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a50  mov     rcx, [rsp+58h+arg_8]
0x180005a55  and     r12, 0FFFFFFFFFFFF0000h
0x180005a5c  mov     r9, rdi
0x180005a5f  mov     r8, rsi
0x180005a62  mov     rdx, r12
0x180005a65  mov     rax, [rcx]
0x180005a68  mov     rax, [rax+38h]
0x180005a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a71  mov     rcx, [rsp+58h+arg_8]
0x180005a76  mov     ebp, eax
0x180005a78  mov     rax, [rcx]
0x180005a7b  mov     rax, [rax+10h]
0x180005a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a84  mov     rcx, rbx; pidl
0x180005a87  call    cs:__imp_ILFree
0x180005a8d  mov     rbx, [rsp+58h+arg_0]
0x180005a92  mov     eax, ebp
0x180005a94  mov     rbp, [rsp+58h+arg_18]
0x180005a99  add     rsp, 30h
0x180005a9d  pop     r15
0x180005a9f  pop     r14
0x180005aa1  pop     r12
0x180005aa3  pop     rdi
0x180005aa4  pop     rsi
0x180005aa5  retn
0x180005aa6  mov     rbx, [rsp+58h+arg_0]
0x180005aab  mov     eax, 8007000Eh
0x180005ab0  add     rsp, 30h
0x180005ab4  pop     r15
0x180005ab6  pop     r14
0x180005ab8  pop     r12
0x180005aba  pop     rdi
0x180005abb  pop     rsi
0x180005abc  retn
0x180005abd  xor     r15d, r15d
0x180005ac0  test    rdi, rdi
0x180005ac3  jz      short loc_180005B03
0x180005ac5  cmp     [rdi], r15w
0x180005ac9  jz      short loc_180005B03
0x180005acb  mov     eax, r15d
0x180005ace  test    eax, eax
0x180005ad0  mov     ecx, 0FFFFh
0x180005ad5  cmovz   r15d, ecx
0x180005ad9  mov     eax, r15d
0x180005adc  add     rsp, 30h
0x180005ae0  pop     r15
0x180005ae2  pop     r14
0x180005ae4  pop     r12
0x180005ae6  pop     rdi
0x180005ae7  pop     rsi
0x180005ae8  retn
0x180005ae9  mov     eax, 1
0x180005aee  add     rsp, 30h
0x180005af2  pop     r15
0x180005af4  pop     r14
0x180005af6  pop     r12
0x180005af8  pop     rdi
0x180005af9  pop     rsi
0x180005afa  retn
0x180005afb  mov     r12, r15
0x180005afe  jmp     loc_180005A50
0x180005b03  mov     eax, 1
0x180005b08  jmp     short loc_180005ACE
```
