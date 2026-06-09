# std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>,std::less<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>,std::allocator<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>>(void)

- ea: `0x180004494`
- end: `0x18000452c`
- name: `??0?$set@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@U?$less@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@std@@V?$allocator@V?$ComPtr@UIAppxBundleManifestPackageInfo@@@WRL@Microsoft@@@5@@std@@QEAA@XZ`
- size: `152`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004304`
- `0x1800052a0`
- `0x18000cef0`

## callees

- `0x180004494`
- `0x180011a64`
- `0x180013294`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180004508`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180004508`

## pseudocode

```c
__int64 __fastcall std::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>::set<Microsoft::WRL::ComPtr<IAppxBundleManifestPackageInfo>>(
        __int64 a1)
{
  _QWORD *v2; // rax
  __int64 i; // rcx
  _QWORD pExceptionObject[4]; // [rsp+28h] [rbp-20h] BYREF
  const char *v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = (const char *)a1;
  *(_QWORD *)(a1 + 16) = 0;
  v2 = operator new(0x28u);
  if ( !v2 )
  {
    v6 = 0;
    exception::exception((exception *)pExceptionObject, &v6);
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (std::bad_alloc *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 8) = v2;
  *v2 = v2;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
  for ( i = 0; i != 2; ++i )
    *(_BYTE *)(*(_QWORD *)(a1 + 8) + i + 32) = 1;
  return a1;
}

```

## disassembly

```asm
0x180004494  mov     [rsp+arg_0], rcx
0x180004499  push    rbx
0x18000449a  sub     rsp, 40h
0x18000449e  mov     [rsp+48h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800044a7  mov     rbx, rcx
0x1800044aa  mov     qword ptr [rcx+10h], 0
0x1800044b2  mov     ecx, 28h ; '('; Size
0x1800044b7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800044bc  test    rax, rax
0x1800044bf  jz      short loc_1800044F5
0x1800044c1  mov     [rbx+8], rax
0x1800044c5  mov     [rax], rax
0x1800044c8  mov     rax, [rbx+8]
0x1800044cc  mov     [rax+8], rax
0x1800044d0  mov     rax, [rbx+8]
0x1800044d4  mov     [rax+10h], rax
0x1800044d8  xor     ecx, ecx
0x1800044da  mov     rax, [rbx+8]
0x1800044de  mov     byte ptr [rax+rcx+20h], 1
0x1800044e3  inc     rcx
0x1800044e6  cmp     rcx, 2
0x1800044ea  jnz     short loc_1800044DA
0x1800044ec  mov     rax, rbx
0x1800044ef  add     rsp, 40h
0x1800044f3  pop     rbx
0x1800044f4  retn
0x1800044f5  mov     [rsp+48h+arg_0], 0
0x1800044fe  lea     rdx, [rsp+48h+arg_0]
0x180004503  lea     rcx, [rsp+48h+pExceptionObject]
0x180004508  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18000450e  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180004515  mov     [rsp+48h+pExceptionObject], rax
0x18000451a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180004521  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180004526  call    _CxxThrowException_0
```
