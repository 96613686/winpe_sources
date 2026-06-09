# std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>> const &,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>)

- ea: `0x180001a78`
- end: `0x180001b10`
- name: `??0?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAA@AEBU?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@1@@Z`
- size: `152`
- prototype: `__int64 __fastcall(__int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800019d4`

## callees

- `0x180001a78`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180001aec`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180001aec`

## pseudocode

```c
__int64 __fastcall std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>(
        __int64 a1,
        __int64 a2,
        const char *a3)
{
  _QWORD *v4; // rax
  __int64 i; // rcx
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+60h] [rbp+18h] BYREF

  v8 = a3;
  *(_QWORD *)(a1 + 16) = 0;
  v4 = operator new(0x28u);
  if ( !v4 )
  {
    v8 = 0;
    exception::exception((exception *)pExceptionObject, &v8);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 8) = v4;
  *v4 = v4;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*(_QWORD *)(a1 + 8) + i + 32) = 1;
  return a1;
}

```

## disassembly

```asm
0x180001a78  mov     [rsp+arg_10], r8
0x180001a7d  push    rbx
0x180001a7e  sub     rsp, 40h
0x180001a82  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180001a8b  mov     rbx, rcx
0x180001a8e  mov     qword ptr [rcx+10h], 0
0x180001a96  mov     ecx, 28h ; '('; Size
0x180001a9b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001aa0  test    rax, rax
0x180001aa3  jz      short loc_180001AD9
0x180001aa5  mov     [rbx+8], rax
0x180001aa9  mov     [rax], rax
0x180001aac  mov     rax, [rbx+8]
0x180001ab0  mov     [rax+8], rax
0x180001ab4  mov     rax, [rbx+8]
0x180001ab8  mov     [rax+10h], rax
0x180001abc  xor     ecx, ecx
0x180001abe  mov     rax, [rbx+8]
0x180001ac2  mov     byte ptr [rax+rcx+20h], 1
0x180001ac7  inc     rcx
0x180001aca  cmp     rcx, 2
0x180001ace  jnz     short loc_180001ABE
0x180001ad0  mov     rax, rbx
0x180001ad3  add     rsp, 40h
0x180001ad7  pop     rbx
0x180001ad8  retn
0x180001ad9  mov     [rsp+48h+arg_10], 0
0x180001ae2  lea     rdx, [rsp+48h+arg_10]
0x180001ae7  lea     rcx, [rsp+48h+pExceptionObject]
0x180001aec  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180001af2  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001af9  mov     [rsp+48h+pExceptionObject], rax
0x180001afe  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001b05  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001b0a  call    _CxxThrowException_0
```
