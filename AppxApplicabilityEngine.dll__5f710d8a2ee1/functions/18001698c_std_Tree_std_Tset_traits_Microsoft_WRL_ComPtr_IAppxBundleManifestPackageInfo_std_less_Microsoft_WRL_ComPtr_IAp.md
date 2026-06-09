# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Linsert(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,bool)

- ea: `0x18001698c`
- end: `0x180016a8b`
- name: `?_Linsert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@std@@_N@2@PEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@_N@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001318`

## callees

- `0x180001250`
- `0x180001c08`
- `0x18001698c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180016a6b`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016a6b`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Linsert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  void *v5; // rsi
  __int64 *v6; // rcx
  __int64 ***v7; // rdx
  __int64 *v8; // rax
  unsigned __int64 v9; // r10
  __int64 **v10; // r9
  __int64 *v11; // rbx
  __int64 **v12; // rax
  __int64 j; // rax
  __int64 *i; // rax
  __int64 *v16; // [rsp+40h] [rbp+8h] BYREF

  v5 = (void *)a3;
  v6 = (__int64 *)(a3 + 24);
  v7 = *(__int64 ****)(a1 + 8);
  v8 = (__int64 *)v7[1];
  if ( *((_BYTE *)v8 + 33) )
  {
    LOBYTE(a3) = 1;
    v10 = *(__int64 ***)(a1 + 8);
  }
  else
  {
    v9 = *v6;
    do
    {
      v10 = (__int64 **)v8;
      LOBYTE(a3) = v9 < v8[3];
      if ( v9 >= v8[3] )
        v8 = (__int64 *)v8[2];
      else
        v8 = (__int64 *)*v8;
    }
    while ( !*((_BYTE *)v8 + 33) );
  }
  v11 = (__int64 *)v10;
  if ( (_BYTE)a3 )
  {
    if ( v10 == *v7 )
    {
      LOBYTE(a3) = 1;
      goto LABEL_12;
    }
    if ( *((_BYTE *)v10 + 33) )
    {
      v11 = v10[2];
    }
    else if ( *((_BYTE *)*v10 + 33) )
    {
      for ( i = v10[1]; !*((_BYTE *)i + 33) && v11 == (__int64 *)*i; i = (__int64 *)i[1] )
        v11 = i;
      if ( !*((_BYTE *)v11 + 33) )
        v11 = i;
    }
    else
    {
      v11 = *v10;
      for ( j = (*v10)[2]; !*(_BYTE *)(j + 33); j = v11[2] )
        v11 = (__int64 *)v11[2];
    }
  }
  if ( v11[3] >= (unsigned __int64)*v6 )
  {
    Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(v6);
    operator delete(v5);
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 0;
    return a2;
  }
LABEL_12:
  v12 = std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(
          a1,
          &v16,
          a3,
          v10,
          (__int64 *)v5);
  *(_BYTE *)(a2 + 8) = 1;
  *(_QWORD *)a2 = *v12;
  return a2;
}

```

## disassembly

```asm
0x18001698c  mov     [rsp+arg_8], rbx
0x180016991  mov     [rsp+arg_10], rsi
0x180016996  push    rdi
0x180016997  sub     rsp, 30h
0x18001699b  mov     r11, rcx
0x18001699e  mov     rdi, rdx
0x1800169a1  mov     rsi, r8
0x1800169a4  lea     rcx, [r8+18h]
0x1800169a8  mov     rdx, [r11+8]
0x1800169ac  mov     rax, [rdx+8]
0x1800169b0  cmp     byte ptr [rax+21h], 0
0x1800169b4  jnz     short loc_1800169D7
0x1800169b6  mov     r10, [rcx]
0x1800169b9  cmp     r10, [rax+18h]
0x1800169bd  mov     r9, rax
0x1800169c0  setb    r8b
0x1800169c4  jnb     short loc_1800169CB
0x1800169c6  mov     rax, [rax]
0x1800169c9  jmp     short loc_1800169CF
0x1800169cb  mov     rax, [rax+10h]
0x1800169cf  cmp     byte ptr [rax+21h], 0
0x1800169d3  jz      short loc_1800169B9
0x1800169d5  jmp     short loc_1800169DD
0x1800169d7  mov     r8b, 1
0x1800169da  mov     r9, rdx
0x1800169dd  mov     rbx, r9
0x1800169e0  test    r8b, r8b
0x1800169e3  jz      short loc_180016A5A
0x1800169e5  cmp     r9, [rdx]
0x1800169e8  jnz     short loc_180016A0B
0x1800169ea  mov     r8b, 1
0x1800169ed  lea     rdx, [rsp+38h+arg_0]
0x1800169f2  mov     [rsp+38h+var_18], rsi
0x1800169f7  mov     rcx, r11
0x1800169fa  call    ?_Insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@1@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x1800169ff  mov     byte ptr [rdi+8], 1
0x180016a03  mov     rcx, [rax]
0x180016a06  mov     [rdi], rcx
0x180016a09  jmp     short loc_180016A78
0x180016a0b  cmp     byte ptr [r9+21h], 0
0x180016a10  jz      short loc_180016A18
0x180016a12  mov     rbx, [r9+10h]
0x180016a16  jmp     short loc_180016A5A
0x180016a18  mov     rax, [r9]
0x180016a1b  cmp     byte ptr [rax+21h], 0
0x180016a1f  jnz     short loc_180016A3A
0x180016a21  mov     rbx, rax
0x180016a24  mov     rax, [rax+10h]
0x180016a28  jmp     short loc_180016A32
0x180016a2a  mov     rbx, [rbx+10h]
0x180016a2e  mov     rax, [rbx+10h]
0x180016a32  cmp     byte ptr [rax+21h], 0
0x180016a36  jz      short loc_180016A2A
0x180016a38  jmp     short loc_180016A5A
0x180016a3a  mov     rax, [r9+8]
0x180016a3e  jmp     short loc_180016A4C
0x180016a40  cmp     rbx, [rax]
0x180016a43  jnz     short loc_180016A52
0x180016a45  mov     rbx, rax
0x180016a48  mov     rax, [rax+8]
0x180016a4c  cmp     byte ptr [rax+21h], 0
0x180016a50  jz      short loc_180016A40
0x180016a52  cmp     byte ptr [rbx+21h], 0
0x180016a56  cmovz   rbx, rax
0x180016a5a  mov     rax, [rcx]
0x180016a5d  cmp     [rbx+18h], rax
0x180016a61  jb      short loc_1800169ED
0x180016a63  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180016a68  mov     rcx, rsi
0x180016a6b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016a71  mov     [rdi], rbx
0x180016a74  mov     byte ptr [rdi+8], 0
0x180016a78  mov     rbx, [rsp+38h+arg_8]
0x180016a7d  mov     rax, rdi
0x180016a80  mov     rsi, [rsp+38h+arg_10]
0x180016a85  add     rsp, 30h
0x180016a89  pop     rdi
0x180016a8a  retn
```
