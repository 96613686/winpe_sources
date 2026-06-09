# std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180003d44`
- end: `0x180003eb4`
- name: `?_Insert@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@1@Z`
- size: `368`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002230`
- `0x180016888`

## callees

- `0x180001250`
- `0x180003d44`
- `0x18000b3c4`
- `0x18000b414`
- `0x180011b84`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003d74`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d74`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(
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
  _QWORD *v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // r9
  __int64 v14; // rdx
  __int64 *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  _QWORD *result; // rax

  v5 = *(_QWORD *)(a1 + 16);
  v6 = a1;
  if ( v5 >= 0xFFFFFFFFFFFFFFELL )
  {
    Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(a5 + 4);
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
LABEL_9:
    *(_QWORD *)(v10 + 16) = a5;
    goto LABEL_10;
  }
  if ( (_BYTE)a3 )
  {
    *a4 = a5;
    v11 = *(_QWORD **)(a1 + 8);
    if ( a4 == (_QWORD *)*v11 )
      *v11 = a5;
    goto LABEL_10;
  }
  a4[2] = a5;
  v10 = *(_QWORD *)(a1 + 8);
  if ( a4 == *(_QWORD **)(v10 + 16) )
    goto LABEL_9;
LABEL_10:
  v12 = a5[1];
  v13 = a5;
  while ( !*(_BYTE *)(v12 + 40) )
  {
    v14 = v13[1];
    v15 = *(__int64 **)(v14 + 8);
    v16 = *v15;
    if ( v14 == *v15 )
    {
      v16 = v15[2];
      if ( !*(_BYTE *)(v16 + 40) )
        goto LABEL_17;
      if ( v13 == *(_QWORD **)(v14 + 16) )
        std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
          v6,
          v14);
      *(_BYTE *)(v13[1] + 40LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 40LL) = 0;
      std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
        v6,
        *(_QWORD *)(v13[1] + 8LL),
        a3,
        v13);
    }
    else
    {
      if ( !*(_BYTE *)(v16 + 40) )
      {
LABEL_17:
        *(_BYTE *)(v14 + 40) = 1;
        *(_BYTE *)(v16 + 40) = 1;
        *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 40LL) = 0;
        v13 = *(_QWORD **)(v13[1] + 8LL);
        goto LABEL_21;
      }
      if ( v13 == *(_QWORD **)v14 )
        std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
          v6,
          v14,
          a3,
          v13[1]);
      *(_BYTE *)(v13[1] + 40LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 40LL) = 0;
      std::_Tree<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
        v6,
        *(_QWORD *)(v13[1] + 8LL));
    }
LABEL_21:
    v12 = v13[1];
  }
  v17 = *(_QWORD *)(v6 + 8);
  *a2 = v8;
  v18 = *(_QWORD *)(v17 + 8);
  result = a2;
  *(_BYTE *)(v18 + 40) = 1;
  return result;
}

```

## disassembly

```asm
0x180003d44  push    rbx
0x180003d46  sub     rsp, 20h
0x180003d4a  mov     rax, [rcx+10h]
0x180003d4e  mov     r11, rcx
0x180003d51  mov     rcx, 0FFFFFFFFFFFFFFEh
0x180003d5b  mov     rbx, rdx
0x180003d5e  cmp     rax, rcx
0x180003d61  jb      short loc_180003D87
0x180003d63  mov     rbx, [rsp+28h+arg_20]
0x180003d68  lea     rcx, [rbx+20h]
0x180003d6c  call    ?InternalRelease@?$ComPtr@UIAppxBundleManifestPackageInfo2@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo2>::InternalRelease(void)
0x180003d71  mov     rcx, rbx
0x180003d74  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d7a  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180003d81  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003d87  mov     r10, [rsp+28h+arg_20]
0x180003d8c  inc     rax
0x180003d8f  mov     [r11+10h], rax
0x180003d93  mov     [r10+8], r9
0x180003d97  mov     rax, [r11+8]
0x180003d9b  cmp     r9, rax
0x180003d9e  jnz     short loc_180003DB1
0x180003da0  mov     [rax+8], r10
0x180003da4  mov     rax, [r11+8]
0x180003da8  mov     [rax], r10
0x180003dab  mov     rax, [r11+8]
0x180003daf  jmp     short loc_180003DD5
0x180003db1  test    r8b, r8b
0x180003db4  jz      short loc_180003DC7
0x180003db6  mov     [r9], r10
0x180003db9  mov     rax, [r11+8]
0x180003dbd  cmp     r9, [rax]
0x180003dc0  jnz     short loc_180003DD9
0x180003dc2  mov     [rax], r10
0x180003dc5  jmp     short loc_180003DD9
0x180003dc7  mov     [r9+10h], r10
0x180003dcb  mov     rax, [r11+8]
0x180003dcf  cmp     r9, [rax+10h]
0x180003dd3  jnz     short loc_180003DD9
0x180003dd5  mov     [rax+10h], r10
0x180003dd9  mov     rax, [r10+8]
0x180003ddd  mov     r9, r10
0x180003de0  jmp     loc_180003E92
0x180003de5  mov     rdx, [r9+8]
0x180003de9  mov     rcx, [rdx+8]
0x180003ded  mov     rax, [rcx]
0x180003df0  cmp     rdx, rax
0x180003df3  jnz     short loc_180003E36
0x180003df5  mov     rax, [rcx+10h]
0x180003df9  cmp     byte ptr [rax+28h], 0
0x180003dfd  jz      short loc_180003E3C
0x180003dff  cmp     r9, [rdx+10h]
0x180003e03  jnz     short loc_180003E10
0x180003e05  mov     rcx, r11
0x180003e08  mov     r9, rdx
0x180003e0b  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180003e10  mov     rax, [r9+8]
0x180003e14  mov     byte ptr [rax+28h], 1
0x180003e18  mov     rax, [r9+8]
0x180003e1c  mov     rcx, [rax+8]
0x180003e20  mov     byte ptr [rcx+28h], 0
0x180003e24  mov     rcx, r11
0x180003e27  mov     rdx, [r9+8]
0x180003e2b  mov     rdx, [rdx+8]
0x180003e2f  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180003e34  jmp     short loc_180003E8E
0x180003e36  cmp     byte ptr [rax+28h], 0
0x180003e3a  jnz     short loc_180003E5A
0x180003e3c  mov     byte ptr [rdx+28h], 1
0x180003e40  mov     byte ptr [rax+28h], 1
0x180003e44  mov     rax, [r9+8]
0x180003e48  mov     rcx, [rax+8]
0x180003e4c  mov     byte ptr [rcx+28h], 0
0x180003e50  mov     rax, [r9+8]
0x180003e54  mov     r9, [rax+8]
0x180003e58  jmp     short loc_180003E8E
0x180003e5a  cmp     r9, [rdx]
0x180003e5d  jnz     short loc_180003E6A
0x180003e5f  mov     rcx, r11
0x180003e62  mov     r9, rdx
0x180003e65  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180003e6a  mov     rax, [r9+8]
0x180003e6e  mov     byte ptr [rax+28h], 1
0x180003e72  mov     rax, [r9+8]
0x180003e76  mov     rcx, [rax+8]
0x180003e7a  mov     byte ptr [rcx+28h], 0
0x180003e7e  mov     rcx, r11
0x180003e81  mov     rdx, [r9+8]
0x180003e85  mov     rdx, [rdx+8]
0x180003e89  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180003e8e  mov     rax, [r9+8]
0x180003e92  cmp     byte ptr [rax+28h], 0
0x180003e96  jz      loc_180003DE5
0x180003e9c  mov     rax, [r11+8]
0x180003ea0  mov     [rbx], r10
0x180003ea3  mov     rcx, [rax+8]
0x180003ea7  mov     rax, rbx
0x180003eaa  mov     byte ptr [rcx+28h], 1
0x180003eae  add     rsp, 20h
0x180003eb2  pop     rbx
0x180003eb3  retn
```
