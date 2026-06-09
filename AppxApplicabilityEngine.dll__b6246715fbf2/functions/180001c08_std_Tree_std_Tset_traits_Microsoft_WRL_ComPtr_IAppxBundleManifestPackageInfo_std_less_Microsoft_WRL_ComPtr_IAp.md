# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *,std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)

- ea: `0x180001c08`
- end: `0x180001d81`
- name: `?_Insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAA?AV?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@1@Z`
- size: `377`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180001714`
- `0x1800052a0`
- `0x18001698c`

## callees

- `0x180001250`
- `0x18000128c`
- `0x180001c08`
- `0x18000badc`
- `0x180011b84`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180001d27`
- `msvcrt!??3@YAXPEAX@Z` at `0x180001d27`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Insert(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        _QWORD *a5)
{
  unsigned __int64 v5; // rax
  __int64 v6; // r11
  _QWORD *v8; // r10
  _QWORD *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD *result; // rax
  _QWORD *v16; // rax
  __int64 v17; // rdx
  __int64 *v18; // rcx
  __int64 v19; // rax

  v5 = *(_QWORD *)(a1 + 16);
  v6 = a1;
  if ( v5 >= 0x1FFFFFFFFFFFFFFELL )
  {
    Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(a5 + 3);
    operator delete(a5);
    std::_Xlength_error("map/set<T> too long");
  }
  v8 = a5;
  *(_QWORD *)(a1 + 16) = v5 + 1;
  a5[1] = a4;
  v9 = *(_QWORD **)(a1 + 8);
  if ( a4 == v9 )
  {
    v9[1] = a5;
    **(_QWORD **)(a1 + 8) = a5;
    v10 = *(_QWORD *)(a1 + 8);
LABEL_4:
    *(_QWORD *)(v10 + 16) = a5;
    goto LABEL_5;
  }
  if ( (_BYTE)a3 )
  {
    *a4 = a5;
    v16 = *(_QWORD **)(a1 + 8);
    if ( a4 == (_QWORD *)*v16 )
      *v16 = a5;
    goto LABEL_5;
  }
  a4[2] = a5;
  v10 = *(_QWORD *)(a1 + 8);
  if ( a4 == *(_QWORD **)(v10 + 16) )
    goto LABEL_4;
LABEL_5:
  v11 = a5[1];
  v12 = a5;
  while ( !*(_BYTE *)(v11 + 32) )
  {
    v17 = v12[1];
    v18 = *(__int64 **)(v17 + 8);
    v19 = *v18;
    if ( v17 == *v18 )
    {
      v19 = v18[2];
      if ( !*(_BYTE *)(v19 + 32) )
      {
LABEL_19:
        *(_BYTE *)(v17 + 32) = 1;
        *(_BYTE *)(v19 + 32) = 1;
        *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 32LL) = 0;
        v12 = *(_QWORD **)(v12[1] + 8LL);
        goto LABEL_20;
      }
      if ( v12 == *(_QWORD **)(v17 + 16) )
        std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(
          v6,
          v17,
          a3,
          v12[1]);
      *(_BYTE *)(v12[1] + 32LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 32LL) = 0;
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(
        v6,
        *(_QWORD *)(v12[1] + 8LL));
    }
    else
    {
      if ( !*(_BYTE *)(v19 + 32) )
        goto LABEL_19;
      if ( v12 == *(_QWORD **)v17 )
        std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(
          v6,
          v17);
      *(_BYTE *)(v12[1] + 32LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 32LL) = 0;
      std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(
        v6,
        *(_QWORD *)(v12[1] + 8LL),
        a3,
        v12);
    }
LABEL_20:
    v11 = v12[1];
  }
  v13 = *(_QWORD *)(v6 + 8);
  *a2 = v8;
  v14 = *(_QWORD *)(v13 + 8);
  result = a2;
  *(_BYTE *)(v14 + 32) = 1;
  return result;
}

```

## disassembly

```asm
0x180001c08  push    rbx
0x180001c0a  sub     rsp, 20h
0x180001c0e  mov     rax, [rcx+10h]
0x180001c12  mov     r11, rcx
0x180001c15  mov     rcx, 1FFFFFFFFFFFFFFEh
0x180001c1f  mov     rbx, rdx
0x180001c22  cmp     rax, rcx
0x180001c25  jnb     loc_180001D16
0x180001c2b  mov     r10, [rsp+28h+arg_20]
0x180001c30  inc     rax
0x180001c33  mov     [r11+10h], rax
0x180001c37  mov     [r10+8], r9
0x180001c3b  mov     rax, [r11+8]
0x180001c3f  cmp     r9, rax
0x180001c42  jnz     short loc_180001C7C
0x180001c44  mov     [rax+8], r10
0x180001c48  mov     rax, [r11+8]
0x180001c4c  mov     [rax], r10
0x180001c4f  mov     rax, [r11+8]
0x180001c53  mov     [rax+10h], r10
0x180001c57  mov     rax, [r10+8]
0x180001c5b  mov     r9, r10
0x180001c5e  cmp     byte ptr [rax+20h], 0
0x180001c62  jz      short loc_180001CA2
0x180001c64  mov     rax, [r11+8]
0x180001c68  mov     [rbx], r10
0x180001c6b  mov     rcx, [rax+8]
0x180001c6f  mov     rax, rbx
0x180001c72  mov     byte ptr [rcx+20h], 1
0x180001c76  add     rsp, 20h
0x180001c7a  pop     rbx
0x180001c7b  retn
0x180001c7c  test    r8b, r8b
0x180001c7f  jnz     short loc_180001C91
0x180001c81  mov     [r9+10h], r10
0x180001c85  mov     rax, [r11+8]
0x180001c89  cmp     r9, [rax+10h]
0x180001c8d  jz      short loc_180001C53
0x180001c8f  jmp     short loc_180001C57
0x180001c91  mov     [r9], r10
0x180001c94  mov     rax, [r11+8]
0x180001c98  cmp     r9, [rax]
0x180001c9b  jnz     short loc_180001C57
0x180001c9d  mov     [rax], r10
0x180001ca0  jmp     short loc_180001C57
0x180001ca2  mov     rdx, [r9+8]
0x180001ca6  mov     rcx, [rdx+8]
0x180001caa  mov     rax, [rcx]
0x180001cad  cmp     rdx, rax
0x180001cb0  jz      short loc_180001CE7
0x180001cb2  cmp     byte ptr [rax+20h], 0
0x180001cb6  jz      short loc_180001CF1
0x180001cb8  cmp     r9, [rdx]
0x180001cbb  jz      loc_180001D71
0x180001cc1  mov     rax, [r9+8]
0x180001cc5  mov     byte ptr [rax+20h], 1
0x180001cc9  mov     rax, [r9+8]
0x180001ccd  mov     rcx, [rax+8]
0x180001cd1  mov     byte ptr [rcx+20h], 0
0x180001cd5  mov     rcx, r11
0x180001cd8  mov     rdx, [r9+8]
0x180001cdc  mov     rdx, [rdx+8]
0x180001ce0  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001ce5  jmp     short loc_180001D0D
0x180001ce7  mov     rax, [rcx+10h]
0x180001ceb  cmp     byte ptr [rax+20h], 0
0x180001cef  jnz     short loc_180001D3A
0x180001cf1  mov     byte ptr [rdx+20h], 1
0x180001cf5  mov     byte ptr [rax+20h], 1
0x180001cf9  mov     rax, [r9+8]
0x180001cfd  mov     rcx, [rax+8]
0x180001d01  mov     byte ptr [rcx+20h], 0
0x180001d05  mov     rax, [r9+8]
0x180001d09  mov     r9, [rax+8]
0x180001d0d  mov     rax, [r9+8]
0x180001d11  jmp     loc_180001C5E
0x180001d16  mov     rbx, [rsp+28h+arg_20]
0x180001d1b  lea     rcx, [rbx+18h]
0x180001d1f  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180001d24  mov     rcx, rbx
0x180001d27  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180001d2d  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180001d34  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180001d3a  cmp     r9, [rdx+10h]
0x180001d3e  jnz     short loc_180001D4B
0x180001d40  mov     rcx, r11
0x180001d43  mov     r9, rdx
0x180001d46  call    ?_Lrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Lrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001d4b  mov     rax, [r9+8]
0x180001d4f  mov     byte ptr [rax+20h], 1
0x180001d53  mov     rax, [r9+8]
0x180001d57  mov     rcx, [rax+8]
0x180001d5b  mov     byte ptr [rcx+20h], 0
0x180001d5f  mov     rcx, r11
0x180001d62  mov     rdx, [r9+8]
0x180001d66  mov     rdx, [rdx+8]
0x180001d6a  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001d6f  jmp     short loc_180001D0D
0x180001d71  mov     rcx, r11
0x180001d74  mov     r9, rdx
0x180001d77  call    ?_Rrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)
0x180001d7c  jmp     loc_180001CC1
```
