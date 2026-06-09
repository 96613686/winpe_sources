# winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageUri(winrt::Windows::Foundation::Uri const &)

- ea: `0x1800067e0`
- end: `0x18000680b`
- name: `?PackageUri@?$consume_Microsoft_Windows_Management_Deployment_IPackageSetItem@UIPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@QEBA@AEBUUri@Foundation@Windows@3@@Z`
- size: `43`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001eb00`

## callees

- `0x180004810`
- `0x1800067e0`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Microsoft_Windows_Management_Deployment_IPackageSetItem<winrt::Microsoft::Windows::Management::Deployment::IPackageSetItem>::PackageUri(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 result; // rax

  result = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a1 + 120LL))(*a1, *a2);
  if ( (int)result < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)result);
  }
  return result;
}

```

## disassembly

```asm
0x1800067e0  sub     rsp, 28h
0x1800067e4  mov     rcx, [rcx]
0x1800067e7  mov     rdx, [rdx]
0x1800067ea  mov     rax, [rcx]
0x1800067ed  mov     rax, [rax+78h]
0x1800067f1  call    cs:__guard_dispatch_icall_fptr
0x1800067f7  test    eax, eax
0x1800067f9  js      short loc_180006800
0x1800067fb  add     rsp, 28h
0x1800067ff  retn
0x180006800  lfence
0x180006803  mov     ecx, eax
0x180006805  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
