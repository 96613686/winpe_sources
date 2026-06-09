# std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode(void)

- ea: `0x180001d88`
- end: `0x180001e05`
- name: `?_Buynode@?$_Tree_val@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@std@@QEAAPEAU_Node@?$_Tree_nod@V?$_Tset_traits@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@$0A@@std@@@2@XZ`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001bb4`

## callees

- `0x180001d88`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180001de1`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180001de1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree_val<std::_Tset_traits<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,0>>::_Buynode(
        __int64 a1)
{
  _QWORD *result; // rax
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v4; // [rsp+50h] [rbp+8h] BYREF

  result = operator new(0x28u);
  if ( !result )
  {
    v4 = 0;
    exception::exception((exception *)pExceptionObject, &v4);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *result = *(_QWORD *)(a1 + 8);
  result[1] = *(_QWORD *)(a1 + 8);
  result[2] = *(_QWORD *)(a1 + 8);
  *((_WORD *)result + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180001d88  push    rbx
0x180001d8a  sub     rsp, 40h
0x180001d8e  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x180001d97  mov     rbx, rcx
0x180001d9a  mov     ecx, 28h ; '('; Size
0x180001d9f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001da4  mov     rdx, rax
0x180001da7  xor     ecx, ecx
0x180001da9  test    rax, rax
0x180001dac  jz      short loc_180001DD2
0x180001dae  mov     rax, [rbx+8]
0x180001db2  mov     [rdx], rax
0x180001db5  mov     rax, [rbx+8]
0x180001db9  mov     [rdx+8], rax
0x180001dbd  mov     rax, [rbx+8]
0x180001dc1  mov     [rdx+10h], rax
0x180001dc5  mov     [rdx+20h], cx
0x180001dc9  mov     rax, rdx
0x180001dcc  add     rsp, 40h
0x180001dd0  pop     rbx
0x180001dd1  retn
0x180001dd2  mov     [rsp+48h+arg_0], rcx
0x180001dd7  lea     rdx, [rsp+48h+arg_0]
0x180001ddc  lea     rcx, [rsp+48h+pExceptionObject]
0x180001de1  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x180001de7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180001dee  mov     [rsp+48h+pExceptionObject], rax
0x180001df3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001dfa  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001dff  call    _CxxThrowException_0
```
