# ResourcePackResolver::AddSetToApplicablePackages(std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>> const &)

- ea: `0x18000193c`
- end: `0x1800019cb`
- name: `?AddSetToApplicablePackages@ResourcePackResolver@@IEAAXAEBV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001318`
- `0x18000181c`

## callees

- `0x180001714`
- `0x18000193c`

## pseudocode

```c
void __fastcall ResourcePackResolver::AddSetToApplicablePackages(__int64 a1, __int64 a2)
{
  __int64 *v4; // rbx
  __int64 *i; // rax
  __int64 *v6; // rcx
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF

  v4 = **(__int64 ***)(a2 + 8);
  while ( v4 != *(__int64 **)(a2 + 8) )
  {
    std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(
      a1 + 328,
      (__int64)v7,
      (unsigned __int64 *)v4 + 3);
    if ( !*((_BYTE *)v4 + 33) )
    {
      i = (__int64 *)v4[2];
      if ( *((_BYTE *)i + 33) )
      {
        for ( i = (__int64 *)v4[1]; !*((_BYTE *)i + 33) && v4 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v4 = i;
LABEL_7:
        v4 = i;
      }
      else
      {
        v6 = (__int64 *)*i;
        if ( *(_BYTE *)(*i + 33) )
          goto LABEL_7;
        do
        {
          v4 = v6;
          v6 = (__int64 *)*v6;
        }
        while ( !*((_BYTE *)v6 + 33) );
      }
    }
  }
}

```

## disassembly

```asm
0x18000193c  mov     [rsp+arg_0], rbx
0x180001941  mov     [rsp+arg_8], rsi
0x180001946  push    rdi
0x180001947  sub     rsp, 30h
0x18000194b  mov     rbx, [rdx+8]
0x18000194f  mov     rdi, rdx
0x180001952  mov     rsi, rcx
0x180001955  mov     rbx, [rbx]
0x180001958  cmp     rbx, [rdi+8]
0x18000195c  jz      short loc_180001992
0x18000195e  lea     r8, [rbx+18h]
0x180001962  lea     rcx, [rsi+148h]
0x180001969  lea     rdx, [rsp+38h+var_18]
0x18000196e  call    ?insert@?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@@std@@_N@2@AEBV?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@_N@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::insert(Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo> const &,bool)
0x180001973  cmp     byte ptr [rbx+21h], 0
0x180001977  jnz     short loc_180001958
0x180001979  mov     rax, [rbx+10h]
0x18000197d  cmp     byte ptr [rax+21h], 0
0x180001981  jz      short loc_1800019B1
0x180001983  mov     rax, [rbx+8]
0x180001987  cmp     byte ptr [rax+21h], 0
0x18000198b  jz      short loc_1800019A2
0x18000198d  mov     rbx, rax
0x180001990  jmp     short loc_180001958
0x180001992  mov     rbx, [rsp+38h+arg_0]
0x180001997  mov     rsi, [rsp+38h+arg_8]
0x18000199c  add     rsp, 30h
0x1800019a0  pop     rdi
0x1800019a1  retn
0x1800019a2  cmp     rbx, [rax+10h]
0x1800019a6  jnz     short loc_18000198D
0x1800019a8  mov     rbx, rax
0x1800019ab  mov     rax, [rax+8]
0x1800019af  jmp     short loc_180001987
0x1800019b1  mov     rcx, [rax]
0x1800019b4  cmp     byte ptr [rcx+21h], 0
0x1800019b8  jnz     short loc_18000198D
0x1800019ba  mov     rax, [rcx]
0x1800019bd  mov     rbx, rcx
0x1800019c0  mov     rcx, rax
0x1800019c3  cmp     byte ptr [rax+21h], 0
0x1800019c7  jz      short loc_1800019BA
0x1800019c9  jmp     short loc_180001958
```
