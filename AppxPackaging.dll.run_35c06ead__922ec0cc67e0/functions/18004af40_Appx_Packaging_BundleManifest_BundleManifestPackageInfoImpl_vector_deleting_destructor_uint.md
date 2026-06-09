# Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vector deleting destructor'(uint)

- ea: `0x18004af40`
- end: `0x18004afd5`
- name: `??_EBundleManifestPackageInfoImpl@BundleManifest@Packaging@Appx@@UEAAPEAXI@Z`
- size: `149`
- prototype: `void *__fastcall(Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x18004af40`
- `0x1800992c4`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004af63`
- `OLEAUT32!__imp_SysFreeString` at `0x18004af73`
- `OLEAUT32!__imp_SysFreeString` at `0x18004af83`
- `OLEAUT32!__imp_SysFreeString` at `0x18004af73`
- `OLEAUT32!__imp_SysFreeString` at `0x18004af83`

## pseudocode

```c
Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *__fastcall Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl::`vector deleting destructor'(
        Appx::Packaging::BundleManifest::BundleManifestPackageInfoImpl *this,
        char a2)
{
  __int64 v4; // rcx

  CoTaskMemFree(*((LPVOID *)this + 14));
  CoTaskMemFree(*((LPVOID *)this + 13));
  SysFreeString(*((BSTR *)this + 12));
  SysFreeString(*((BSTR *)this + 11));
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
  {
    *((_QWORD *)this + 5) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)this + 9) = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x78u);
  return this;
}

```

## disassembly

```asm
0x18004af40  mov     [rsp+arg_0], rbx
0x18004af45  push    rdi
0x18004af46  sub     rsp, 20h
0x18004af4a  mov     rbx, rcx
0x18004af4d  mov     edi, edx
0x18004af4f  mov     rcx, [rcx+70h]; pv
0x18004af53  call    cs:__imp_CoTaskMemFree
0x18004af5a  nop     dword ptr [rax+rax+00h]
0x18004af5f  mov     rcx, [rbx+68h]; pv
0x18004af63  call    cs:__imp_CoTaskMemFree
0x18004af6a  nop     dword ptr [rax+rax+00h]
0x18004af6f  mov     rcx, [rbx+60h]; bstrString
0x18004af73  call    cs:__imp_SysFreeString
0x18004af7a  nop     dword ptr [rax+rax+00h]
0x18004af7f  mov     rcx, [rbx+58h]; bstrString
0x18004af83  call    cs:__imp_SysFreeString
0x18004af8a  nop     dword ptr [rax+rax+00h]
0x18004af8f  mov     rcx, [rbx+28h]
0x18004af93  test    rcx, rcx
0x18004af96  jz      short loc_18004AFAC
0x18004af98  mov     qword ptr [rbx+28h], 0
0x18004afa0  mov     rax, [rcx]
0x18004afa3  mov     rax, [rax+10h]
0x18004afa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004afac  mov     dword ptr [rbx+24h], 0C0000001h
0x18004afb3  test    dil, 1
0x18004afb7  jz      short loc_18004AFC6
0x18004afb9  mov     edx, 78h ; 'x'; unsigned __int64
0x18004afbe  mov     rcx, rbx; void *
0x18004afc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18004afc6  mov     rax, rbx
0x18004afc9  mov     rbx, [rsp+28h+arg_0]
0x18004afce  add     rsp, 20h
0x18004afd2  pop     rdi
0x18004afd3  retn
```
