# std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(unsigned __int64,std::_Tree_nod<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node *)

- ea: `0x18000e2c0`
- end: `0x18000e319`
- name: `??$_Allocate@U_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@std@@@std@@YAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@@2@$00@std@@@0@_KPEAU120@@Z`
- size: `89`
- prototype: `void *__fastcall(__int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004304`
- `0x18000e250`

## callees

- `0x18000e2c0`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000e2f0`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x18000e2f0`

## pseudocode

```c
void *__fastcall std::_Allocate<std::_Tree_nod<std::_Tmap_traits<std::wstring,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>,1>>::_Node>(
        __int64 a1,
        const char *a2)
{
  void *result; // rax
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v4; // [rsp+58h] [rbp+10h] BYREF

  v4 = a2;
  result = operator new(0x50u);
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
0x18000e2c0  mov     [rsp+arg_8], rdx
0x18000e2c5  sub     rsp, 48h
0x18000e2c9  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x18000e2d2  mov     ecx, 50h ; 'P'; Size
0x18000e2d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e2dc  test    rax, rax
0x18000e2df  jnz     short loc_18000E314
0x18000e2e1  mov     [rsp+48h+arg_8], rax
0x18000e2e6  lea     rdx, [rsp+48h+arg_8]
0x18000e2eb  lea     rcx, [rsp+48h+pExceptionObject]
0x18000e2f0  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000e2f6  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18000e2fd  mov     [rsp+48h+pExceptionObject], rax
0x18000e302  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000e309  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e30e  call    _CxxThrowException_0
0x18000e314  add     rsp, 48h
0x18000e318  retn
```
