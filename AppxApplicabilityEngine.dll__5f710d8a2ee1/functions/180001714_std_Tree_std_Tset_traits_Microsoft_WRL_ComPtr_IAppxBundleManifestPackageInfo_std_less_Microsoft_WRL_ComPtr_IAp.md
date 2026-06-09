# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &,bool)

- ea: `0x180001714`
- end: `0x180001814`
- name: `?insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@std@@_N@2@AEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@_N@Z`
- size: `256`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001498`
- `0x18000193c`
- `0x180002230`
- `0x1800052a0`

## callees

- `0x180001714`
- `0x180001bb4`
- `0x180001c08`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
        __int64 a1,
        __int64 a2,
        unsigned __int64 *a3)
{
  __int64 **v4; // rdx
  __int64 *v6; // rax
  bool v7; // si
  __int64 *v8; // rbx
  __int64 *v9; // rax
  unsigned __int64 v10; // r9
  __int64 *v11; // rax
  __int64 v12; // r8
  __int64 i; // rcx
  __int64 j; // rcx
  __int64 *v16; // [rsp+60h] [rbp+8h] BYREF

  v4 = *(__int64 ***)(a1 + 8);
  v6 = v4[1];
  if ( *((_BYTE *)v6 + 33) )
  {
    v7 = 1;
    v8 = *(__int64 **)(a1 + 8);
  }
  else
  {
    v10 = *a3;
    do
    {
      v8 = v6;
      v7 = v10 < v6[3];
      if ( v10 >= v6[3] )
        v6 = (__int64 *)v6[2];
      else
        v6 = (__int64 *)*v6;
    }
    while ( !*((_BYTE *)v6 + 33) );
  }
  v9 = v8;
  if ( v7 )
  {
    if ( v8 == *v4 )
    {
      v11 = (__int64 *)std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(
                         a1,
                         a3);
      LOBYTE(v12) = 1;
LABEL_15:
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(
        a1,
        &v16,
        v12,
        (__int64 **)v8,
        v11);
      v9 = v16;
      *(_BYTE *)(a2 + 8) = 1;
      goto LABEL_16;
    }
    if ( *((_BYTE *)v8 + 33) )
    {
      v9 = (__int64 *)v8[2];
    }
    else if ( *(_BYTE *)(*v8 + 33) )
    {
      for ( i = v8[1]; !*(_BYTE *)(i + 33) && v9 == *(__int64 **)i; i = *(_QWORD *)(i + 8) )
        v9 = (__int64 *)i;
      if ( !*((_BYTE *)v9 + 33) )
        v9 = (__int64 *)i;
    }
    else
    {
      v9 = (__int64 *)*v8;
      for ( j = *(_QWORD *)(*v8 + 16); !*(_BYTE *)(j + 33); j = v9[2] )
        v9 = (__int64 *)v9[2];
    }
  }
  if ( v9[3] < *a3 )
  {
    v11 = (__int64 *)std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(
                       a1,
                       a3);
    LOBYTE(v12) = v7;
    goto LABEL_15;
  }
  *(_BYTE *)(a2 + 8) = 0;
LABEL_16:
  *(_QWORD *)a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x180001714  push    rbx
0x180001716  push    rbp
0x180001717  push    rsi
0x180001718  push    rdi
0x180001719  sub     rsp, 38h
0x18000171d  mov     rdi, rdx
0x180001720  xor     r10d, r10d
0x180001723  mov     rdx, [rcx+8]
0x180001727  mov     rbp, rcx
0x18000172a  mov     rax, [rdx+8]
0x18000172e  cmp     [rax+21h], r10b
0x180001732  jz      short loc_180001760
0x180001734  mov     sil, 1
0x180001737  mov     rbx, rdx
0x18000173a  mov     rax, rbx
0x18000173d  test    sil, sil
0x180001740  jz      short loc_180001751
0x180001742  cmp     rbx, [rdx]
0x180001745  jz      short loc_18000177B
0x180001747  cmp     [rbx+21h], r10b
0x18000174b  jz      short loc_1800017C9
0x18000174d  mov     rax, [rbx+10h]
0x180001751  mov     rcx, [r8]
0x180001754  cmp     [rax+18h], rcx
0x180001758  jb      short loc_1800017B9
0x18000175a  mov     [rdi+8], r10b
0x18000175e  jmp     short loc_1800017A4
0x180001760  mov     r9, [r8]
0x180001763  cmp     r9, [rax+18h]
0x180001767  mov     rbx, rax
0x18000176a  setb    sil
0x18000176e  jnb     short loc_1800017B3
0x180001770  mov     rax, [rax]
0x180001773  cmp     [rax+21h], r10b
0x180001777  jnz     short loc_18000173A
0x180001779  jmp     short loc_180001763
0x18000177b  mov     rdx, r8
0x18000177e  call    ??$_Buynode@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@1@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &)
0x180001783  mov     r8b, 1
0x180001786  mov     r9, rbx
0x180001789  mov     [rsp+58h+var_38], rax
0x18000178e  lea     rdx, [rsp+58h+arg_0]
0x180001793  mov     rcx, rbp
0x180001796  call    ?_Insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@1@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x18000179b  mov     rax, [rsp+58h+arg_0]
0x1800017a0  mov     byte ptr [rdi+8], 1
0x1800017a4  mov     [rdi], rax
0x1800017a7  mov     rax, rdi
0x1800017aa  add     rsp, 38h
0x1800017ae  pop     rdi
0x1800017af  pop     rsi
0x1800017b0  pop     rbp
0x1800017b1  pop     rbx
0x1800017b2  retn
0x1800017b3  mov     rax, [rax+10h]
0x1800017b7  jmp     short loc_180001773
0x1800017b9  mov     rdx, r8
0x1800017bc  mov     rcx, rbp
0x1800017bf  call    ??$_Buynode@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@1@AEAV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@Z; std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &>(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> &)
0x1800017c4  mov     r8b, sil
0x1800017c7  jmp     short loc_180001786
0x1800017c9  mov     rcx, [rbx]
0x1800017cc  cmp     [rcx+21h], r10b
0x1800017d0  jz      short loc_1800017FD
0x1800017d2  mov     rcx, [rbx+8]
0x1800017d6  cmp     [rcx+21h], r10b
0x1800017da  jz      short loc_180001806
0x1800017dc  cmp     [rax+21h], r10b
0x1800017e0  cmovz   rax, rcx
0x1800017e4  jmp     loc_180001751
0x1800017e9  mov     rax, [rax+10h]
0x1800017ed  mov     rcx, [rax+10h]
0x1800017f1  cmp     [rcx+21h], r10b
0x1800017f5  jnz     loc_180001751
0x1800017fb  jmp     short loc_1800017E9
0x1800017fd  mov     rax, rcx
0x180001800  mov     rcx, [rcx+10h]
0x180001804  jmp     short loc_1800017F1
0x180001806  cmp     rax, [rcx]
0x180001809  jnz     short loc_1800017DC
0x18000180b  mov     rax, rcx
0x18000180e  mov     rcx, [rcx+8]
0x180001812  jmp     short loc_1800017D6
```
