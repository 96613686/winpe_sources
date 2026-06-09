# ResourcePackResolver::GetApplicablePackages(void)

- ea: `0x18000181c`
- end: `0x180001936`
- name: `?GetApplicablePackages@ResourcePackResolver@@QEAA?AV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@XZ`
- size: `282`
- prototype: `__int64 __fastcall(ResourcePackResolver *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cef0`

## callees

- `0x180001318`
- `0x180001498`
- `0x18000181c`
- `0x18000193c`
- `0x1800019d4`
- `0x180001fd0`
- `0x1800052a0`
- `0x180025010`

## pseudocode

```c
__int64 __fastcall ResourcePackResolver::GetApplicablePackages(ResourcePackResolver *this, __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 *v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // r14
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int *v12; // rbx
  unsigned int *v13; // rdi

  ResourcePackResolver::CategorizePackages(this);
  v4 = *((_QWORD *)this + 43);
  v5 = (***((__int64 (__fastcall ****)(_QWORD))this + 50))(*((_QWORD *)this + 50));
  v6 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
  v7 = *v6;
  v8 = v6[1];
  while ( v7 != v8 )
  {
    ResourcePackResolver::ChooseLanguagePackagesForLanguage(this, v7);
    v7 += 40;
  }
  if ( *((_QWORD *)this + 43) == v4 )
    ResourcePackResolver::AddSetToApplicablePackages(this, (char *)this + 168);
  v9 = *((_QWORD *)this + 43);
  v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 50) + 8LL))(*((_QWORD *)this + 50));
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  v12 = *(unsigned int **)v11;
  v13 = *(unsigned int **)(v11 + 8);
  while ( v12 != v13 )
    ResourcePackResolver::ChooseScalePackagesForScale(this, *v12++);
  if ( *((_QWORD *)this + 43) == v9 )
    ResourcePackResolver::AddSetToApplicablePackages(this, (char *)this + 168);
  ResourcePackResolver::ChooseDxflPackages(this);
  ResourcePackResolver::AddSetToApplicablePackages(this, (char *)this + 104);
  ResourcePackResolver::AddSetToApplicablePackages(this, (char *)this + 136);
  std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(
    a2,
    (char *)this + 328);
  return a2;
}

```

## disassembly

```asm
0x18000181c  push    rbx
0x18000181e  push    rbp
0x18000181f  push    rsi
0x180001820  push    rdi
0x180001821  push    r14
0x180001823  push    r15
0x180001825  sub     rsp, 38h
0x180001829  mov     rbp, rdx
0x18000182c  mov     rsi, rcx
0x18000182f  call    ?CategorizePackages@ResourcePackResolver@@IEAAXXZ; ResourcePackResolver::CategorizePackages(void)
0x180001834  mov     rcx, [rsi+190h]
0x18000183b  lea     r15, [rsi+148h]
0x180001842  mov     r14, [r15+10h]
0x180001846  mov     rax, [rcx]
0x180001849  mov     rax, [rax]
0x18000184c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001851  mov     rdx, rax
0x180001854  mov     rcx, [rax]
0x180001857  mov     rax, [rcx+8]
0x18000185b  mov     rcx, rdx
0x18000185e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001863  mov     rbx, [rax]
0x180001866  mov     rdi, [rax+8]
0x18000186a  cmp     rbx, rdi
0x18000186d  jnz     short loc_1800018CF
0x18000186f  cmp     [rsi+158h], r14
0x180001876  jnz     short loc_180001887
0x180001878  lea     rdx, [rsi+0A8h]
0x18000187f  mov     rcx, rsi
0x180001882  call    ?AddSetToApplicablePackages@ResourcePackResolver@@IEAAXAEBV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@@Z; ResourcePackResolver::AddSetToApplicablePackages(std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &)
0x180001887  mov     rcx, [rsi+190h]
0x18000188e  mov     r14, [rsi+158h]
0x180001895  mov     rax, [rcx]
0x180001898  mov     rax, [rax+8]
0x18000189c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a1  mov     rdx, rax
0x1800018a4  mov     rcx, [rax]
0x1800018a7  mov     rax, [rcx+8]
0x1800018ab  mov     rcx, rdx
0x1800018ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018b3  mov     rbx, [rax]
0x1800018b6  mov     rdi, [rax+8]
0x1800018ba  cmp     rbx, rdi
0x1800018bd  jz      short loc_1800018E0
0x1800018bf  mov     edx, [rbx]; unsigned int
0x1800018c1  mov     rcx, rsi; this
0x1800018c4  call    ?ChooseScalePackagesForScale@ResourcePackResolver@@IEAAXI@Z; ResourcePackResolver::ChooseScalePackagesForScale(uint)
0x1800018c9  add     rbx, 4
0x1800018cd  jmp     short loc_1800018BA
0x1800018cf  mov     rdx, rbx
0x1800018d2  mov     rcx, rsi
0x1800018d5  call    ?ChooseLanguagePackagesForLanguage@ResourcePackResolver@@IEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ResourcePackResolver::ChooseLanguagePackagesForLanguage(std::wstring const &)
0x1800018da  add     rbx, 28h ; '('
0x1800018de  jmp     short loc_18000186A
0x1800018e0  cmp     [rsi+158h], r14
0x1800018e7  jnz     short loc_1800018F8
0x1800018e9  lea     rdx, [rsi+0A8h]
0x1800018f0  mov     rcx, rsi
0x1800018f3  call    ?AddSetToApplicablePackages@ResourcePackResolver@@IEAAXAEBV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@@Z; ResourcePackResolver::AddSetToApplicablePackages(std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &)
0x1800018f8  mov     rcx, rsi; this
0x1800018fb  call    ?ChooseDxflPackages@ResourcePackResolver@@IEAAXXZ; ResourcePackResolver::ChooseDxflPackages(void)
0x180001900  lea     rdx, [rsi+68h]
0x180001904  mov     rcx, rsi
0x180001907  call    ?AddSetToApplicablePackages@ResourcePackResolver@@IEAAXAEBV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@@Z; ResourcePackResolver::AddSetToApplicablePackages(std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &)
0x18000190c  lea     rdx, [rsi+88h]
0x180001913  mov     rcx, rsi
0x180001916  call    ?AddSetToApplicablePackages@ResourcePackResolver@@IEAAXAEBV?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@@Z; ResourcePackResolver::AddSetToApplicablePackages(std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &)
0x18000191b  mov     rdx, r15
0x18000191e  mov     rcx, rbp
0x180001921  call    ??0?$_Tree@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@AEBV01@@Z; std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(std::_Tree<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>> const &)
0x180001926  mov     rax, rbp
0x180001929  add     rsp, 38h
0x18000192d  pop     r15
0x18000192f  pop     r14
0x180001931  pop     rdi
0x180001932  pop     rsi
0x180001933  pop     rbp
0x180001934  pop     rbx
0x180001935  retn
```
