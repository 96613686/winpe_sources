# std::_Allocate<std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<DX_FEATURE_LEVEL>,std::allocator<std::pair<DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x18000d7ec`
- end: `0x18000d845`
- name: `??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@W4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@W4DX_FEATURE_LEVEL@@@std@@V?$allocator@U?$pair@$$CBW4DX_FEATURE_LEVEL@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@6@$00@std@@@0@_KPEAU120@@Z`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004304`
- `0x18000d770`

## callees

- `0x18000d7ec`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d81c`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000d81c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall std::_Allocate<std::_Tree_nod<std::_Tmap_traits<enum DX_FEATURE_LEVEL,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<enum DX_FEATURE_LEVEL>,std::allocator<std::pair<enum DX_FEATURE_LEVEL const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(
        __int64 a1,
        const char *a2)
{
  void *result; // rax
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v4; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  result = operator new(0x30u);
  if ( !result )
  {
    v4 = 0;
    exception::exception((exception *)pExceptionObject, &v4);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x18000d7ec  mov     [rsp+arg_8], rdx
0x18000d7f1  sub     rsp, 48h
0x18000d7f5  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18000d7fe  mov     ecx, 30h ; '0'; Size
0x18000d803  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d808  test    rax, rax
0x18000d80b  jnz     short loc_18000D840
0x18000d80d  mov     [rsp+48h+arg_8], rax
0x18000d812  lea     rdx, [rsp+48h+arg_8]
0x18000d817  lea     rcx, [rsp+48h+pExceptionObject]
0x18000d81c  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000d822  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000d829  mov     [rsp+48h+pExceptionObject], rax
0x18000d82e  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000d835  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d83a  call    _CxxThrowException_0
0x18000d840  add     rsp, 48h
0x18000d844  retn
```
