# std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(std::_Tree_nod<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Node *)

- ea: `0x18000badc`
- end: `0x18000bb28`
- name: `?_Rrotate@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@@Z`
- size: `76`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001c08`

## callees

- `0x18000badc`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 33) )
    *(_QWORD *)(v3 + 8) = a2;
  *(_QWORD *)(v2 + 8) = a2[1];
  result = *(_QWORD **)(a1 + 8);
  if ( a2 == (_QWORD *)result[1] )
  {
    result[1] = v2;
  }
  else
  {
    result = (_QWORD *)a2[1];
    if ( a2 == (_QWORD *)result[2] )
      result[2] = v2;
    else
      *result = v2;
  }
  *(_QWORD *)(v2 + 16) = a2;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x18000badc  mov     r8, [rdx]
0x18000badf  mov     rax, [r8+10h]
0x18000bae3  mov     [rdx], rax
0x18000bae6  mov     rax, [r8+10h]
0x18000baea  cmp     byte ptr [rax+21h], 0
0x18000baee  jnz     short loc_18000BAF4
0x18000baf0  mov     [rax+8], rdx
0x18000baf4  mov     rax, [rdx+8]
0x18000baf8  mov     [r8+8], rax
0x18000bafc  mov     rax, [rcx+8]
0x18000bb00  cmp     rdx, [rax+8]
0x18000bb04  jnz     short loc_18000BB0C
0x18000bb06  mov     [rax+8], r8
0x18000bb0a  jmp     short loc_18000BB1F
0x18000bb0c  mov     rax, [rdx+8]
0x18000bb10  cmp     rdx, [rax+10h]
0x18000bb14  jnz     short loc_18000BB1C
0x18000bb16  mov     [rax+10h], r8
0x18000bb1a  jmp     short loc_18000BB1F
0x18000bb1c  mov     [rax], r8
0x18000bb1f  mov     [r8+10h], rdx
0x18000bb23  mov     [rdx+8], r8
0x18000bb27  retn
```
