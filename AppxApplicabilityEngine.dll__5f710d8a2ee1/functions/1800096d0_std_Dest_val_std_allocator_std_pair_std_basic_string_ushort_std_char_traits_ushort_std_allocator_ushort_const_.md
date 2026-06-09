# std::_Dest_val<std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>> &,std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> *)

- ea: `0x1800096d0`
- end: `0x18000972f`
- name: `??$_Dest_val@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@std@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@2@@std@@YAXAEAV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@0@PEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@0@@Z`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002af4`

## callees

- `0x1800096d0`
- `0x180025010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180009727`
- `msvcrt!??3@YAXPEAX@Z` at `0x180009727`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Dest_val<std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rcx

  v3 = *(_QWORD *)(a2 + 40);
  if ( v3 )
  {
    *(_QWORD *)(a2 + 40) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  if ( *(_QWORD *)(a2 + 24) >= 8u )
    operator delete(*(void **)a2);
  *(_QWORD *)(a2 + 24) = 7;
  *(_QWORD *)(a2 + 16) = 0;
  *(_WORD *)a2 = 0;
}

```

## disassembly

```asm
0x1800096d0  push    rdi
0x1800096d2  sub     rsp, 30h
0x1800096d6  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800096df  mov     [rsp+38h+arg_0], rbx
0x1800096e4  mov     rbx, rdx
0x1800096e7  mov     rcx, [rdx+28h]
0x1800096eb  xor     edi, edi
0x1800096ed  test    rcx, rcx
0x1800096f0  jz      short loc_180009703
0x1800096f2  mov     [rdx+28h], rdi
0x1800096f6  mov     rax, [rcx]
0x1800096f9  mov     rax, [rax+10h]
0x1800096fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009702  nop
0x180009703  cmp     qword ptr [rbx+18h], 8
0x180009708  jnb     short loc_180009724
0x18000970a  mov     qword ptr [rbx+18h], 7
0x180009712  mov     [rbx+10h], rdi
0x180009716  mov     [rbx], di
0x180009719  mov     rbx, [rsp+38h+arg_0]
0x18000971e  add     rsp, 30h
0x180009722  pop     rdi
0x180009723  retn
0x180009724  mov     rcx, [rbx]
0x180009727  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000972d  jmp     short loc_18000970A
```
