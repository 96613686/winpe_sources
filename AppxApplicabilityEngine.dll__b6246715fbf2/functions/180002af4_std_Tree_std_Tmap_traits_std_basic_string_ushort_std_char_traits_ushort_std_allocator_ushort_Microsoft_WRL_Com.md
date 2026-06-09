# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *,std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x180002af4`
- end: `0x180002c64`
- name: `?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@@2@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@1@Z`
- size: `368`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002230`

## callees

- `0x180002af4`
- `0x1800096d0`
- `0x180011b84`
- `0x180016a94`
- `0x180016ae4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002b24`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002b24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Insert(
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
  if ( v5 >= 0x555555555555554LL )
  {
    std::_Dest_val<std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
      0x555555555555554LL,
      (__int64)(a5 + 3));
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
  while ( !*(_BYTE *)(v12 + 72) )
  {
    v14 = v13[1];
    v15 = *(__int64 **)(v14 + 8);
    v16 = *v15;
    if ( v14 == *v15 )
    {
      v16 = v15[2];
      if ( !*(_BYTE *)(v16 + 72) )
        goto LABEL_17;
      if ( v13 == *(_QWORD **)(v14 + 16) )
        std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
          v6,
          v14);
      *(_BYTE *)(v13[1] + 72LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 72LL) = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
        v6,
        *(_QWORD *)(v13[1] + 8LL),
        a3,
        v13);
    }
    else
    {
      if ( !*(_BYTE *)(v16 + 72) )
      {
LABEL_17:
        *(_BYTE *)(v14 + 72) = 1;
        *(_BYTE *)(v16 + 72) = 1;
        *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 72LL) = 0;
        v13 = *(_QWORD **)(v13[1] + 8LL);
        goto LABEL_21;
      }
      if ( v13 == *(_QWORD **)v14 )
        std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(
          v6,
          v14,
          a3,
          v13[1]);
      *(_BYTE *)(v13[1] + 72LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v13[1] + 8LL) + 72LL) = 0;
      std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(
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
  *(_BYTE *)(v18 + 72) = 1;
  return result;
}

```

## disassembly

```asm
0x180002af4  push    rbx
0x180002af6  sub     rsp, 20h
0x180002afa  mov     rax, [rcx+10h]
0x180002afe  mov     r11, rcx
0x180002b01  mov     rcx, 555555555555554h
0x180002b0b  mov     rbx, rdx
0x180002b0e  cmp     rax, rcx
0x180002b11  jb      short loc_180002B37
0x180002b13  mov     rbx, [rsp+28h+arg_20]
0x180002b18  lea     rdx, [rbx+18h]
0x180002b1c  call    ??$_Dest_val@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@std@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@2@@std@@YAXAEAV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@0@PEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@0@@Z; std::_Dest_val<std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>> &,std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> *)
0x180002b21  mov     rcx, rbx
0x180002b24  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002b2a  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x180002b31  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180002b37  mov     r10, [rsp+28h+arg_20]
0x180002b3c  inc     rax
0x180002b3f  mov     [r11+10h], rax
0x180002b43  mov     [r10+8], r9
0x180002b47  mov     rax, [r11+8]
0x180002b4b  cmp     r9, rax
0x180002b4e  jnz     short loc_180002B61
0x180002b50  mov     [rax+8], r10
0x180002b54  mov     rax, [r11+8]
0x180002b58  mov     [rax], r10
0x180002b5b  mov     rax, [r11+8]
0x180002b5f  jmp     short loc_180002B85
0x180002b61  test    r8b, r8b
0x180002b64  jz      short loc_180002B77
0x180002b66  mov     [r9], r10
0x180002b69  mov     rax, [r11+8]
0x180002b6d  cmp     r9, [rax]
0x180002b70  jnz     short loc_180002B89
0x180002b72  mov     [rax], r10
0x180002b75  jmp     short loc_180002B89
0x180002b77  mov     [r9+10h], r10
0x180002b7b  mov     rax, [r11+8]
0x180002b7f  cmp     r9, [rax+10h]
0x180002b83  jnz     short loc_180002B89
0x180002b85  mov     [rax+10h], r10
0x180002b89  mov     rax, [r10+8]
0x180002b8d  mov     r9, r10
0x180002b90  jmp     loc_180002C42
0x180002b95  mov     rdx, [r9+8]
0x180002b99  mov     rcx, [rdx+8]
0x180002b9d  mov     rax, [rcx]
0x180002ba0  cmp     rdx, rax
0x180002ba3  jnz     short loc_180002BE6
0x180002ba5  mov     rax, [rcx+10h]
0x180002ba9  cmp     byte ptr [rax+48h], 0
0x180002bad  jz      short loc_180002BEC
0x180002baf  cmp     r9, [rdx+10h]
0x180002bb3  jnz     short loc_180002BC0
0x180002bb5  mov     rcx, r11
0x180002bb8  mov     r9, rdx
0x180002bbb  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180002bc0  mov     rax, [r9+8]
0x180002bc4  mov     byte ptr [rax+48h], 1
0x180002bc8  mov     rax, [r9+8]
0x180002bcc  mov     rcx, [rax+8]
0x180002bd0  mov     byte ptr [rcx+48h], 0
0x180002bd4  mov     rcx, r11
0x180002bd7  mov     rdx, [r9+8]
0x180002bdb  mov     rdx, [rdx+8]
0x180002bdf  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180002be4  jmp     short loc_180002C3E
0x180002be6  cmp     byte ptr [rax+48h], 0
0x180002bea  jnz     short loc_180002C0A
0x180002bec  mov     byte ptr [rdx+48h], 1
0x180002bf0  mov     byte ptr [rax+48h], 1
0x180002bf4  mov     rax, [r9+8]
0x180002bf8  mov     rcx, [rax+8]
0x180002bfc  mov     byte ptr [rcx+48h], 0
0x180002c00  mov     rax, [r9+8]
0x180002c04  mov     r9, [rax+8]
0x180002c08  jmp     short loc_180002C3E
0x180002c0a  cmp     r9, [rdx]
0x180002c0d  jnz     short loc_180002C1A
0x180002c0f  mov     rcx, r11
0x180002c12  mov     r9, rdx
0x180002c15  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180002c1a  mov     rax, [r9+8]
0x180002c1e  mov     byte ptr [rax+48h], 1
0x180002c22  mov     rax, [r9+8]
0x180002c26  mov     rcx, [rax+8]
0x180002c2a  mov     byte ptr [rcx+48h], 0
0x180002c2e  mov     rcx, r11
0x180002c31  mov     rdx, [r9+8]
0x180002c35  mov     rdx, [rdx+8]
0x180002c39  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)
0x180002c3e  mov     rax, [r9+8]
0x180002c42  cmp     byte ptr [rax+48h], 0
0x180002c46  jz      loc_180002B95
0x180002c4c  mov     rax, [r11+8]
0x180002c50  mov     [rbx], r10
0x180002c53  mov     rcx, [rax+8]
0x180002c57  mov     rax, rbx
0x180002c5a  mov     byte ptr [rcx+48h], 1
0x180002c5e  add     rsp, 20h
0x180002c62  pop     rbx
0x180002c63  retn
```
