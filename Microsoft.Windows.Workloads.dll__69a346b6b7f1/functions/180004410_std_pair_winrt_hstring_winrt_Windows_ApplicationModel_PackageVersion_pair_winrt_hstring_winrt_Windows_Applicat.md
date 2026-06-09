# std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(void)

- ea: `0x180004410`
- end: `0x180004463`
- name: `??1?$pair@Uhstring@winrt@@UPackageVersion@ApplicationModel@Windows@2@@std@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `106`
- callee_count: `3`
- tags: ``

## callers

- `0x18001eb00`
- `0x18003cad4`
- `0x18003cae0`
- `0x18003caf8`
- `0x18003cb08`
- `0x18003cb18`
- `0x18003cbcc`
- `0x18003cbd8`
- `0x18003cc81`
- `0x18003ccf7`
- `0x18003cd03`
- `0x18003cd0f`
- `0x18003cd27`
- `0x18003cd33`
- `0x18003cd9d`
- `0x18003cda9`
- `0x18003ce40`
- `0x18003ce7e`
- `0x18003ce8a`
- `0x18003cea2`
- `0x18003cf21`
- `0x18003cf2d`
- `0x18003cf39`
- `0x18003cfeb`
- `0x18003d003`
- `0x18003d0e8`
- `0x18003d0f4`
- `0x18003d10c`
- `0x18003d148`
- `0x18003d1ad`
- `0x18003d2ae`
- `0x18003d2ba`
- `0x18003d2c6`
- `0x18003d4c6`
- `0x18003d4d2`
- `0x18003d4ea`
- `0x18003d502`
- `0x18003d50e`
- `0x18003d526`
- `0x18003d9cc`
- `0x18003d9d8`
- `0x18003da54`
- `0x18003db7a`
- `0x18003dca0`
- `0x18003e000`
- `0x18003e018`
- `0x18003e04c`
- `0x18003e07c`
- `0x18003e0ce`
- `0x18003e0f8`

## callees

- `0x180004410`
- `0x180030ae5`
- `0x180030aeb`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000445c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000445c`

## pseudocode

```c
void __fastcall std::pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>::~pair<winrt::hstring,winrt::Windows::ApplicationModel::PackageVersion>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rbx
  int v3; // eax
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    v3 = _InterlockedDecrement(v1 + 6);
    if ( v3 )
    {
      if ( v3 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180004410  mov     [rsp+arg_8], rbx
0x180004415  push    rdi
0x180004416  sub     rsp, 20h
0x18000441a  mov     rbx, [rcx]
0x18000441d  mov     rdi, rcx
0x180004420  test    rbx, rbx
0x180004423  jz      short loc_18000444D
0x180004425  mov     eax, 0FFFFFFFFh
0x18000442a  lock xadd [rbx+18h], eax
0x18000442f  sub     eax, 1
0x180004432  jnz     short loc_180004458
0x180004434  call    WINRT_IMPL_GetProcessHeap
0x180004439  mov     rcx, rax; hHeap
0x18000443c  mov     r8, rbx; lpMem
0x18000443f  xor     edx, edx; dwFlags
0x180004441  call    WINRT_IMPL_HeapFree
0x180004446  mov     qword ptr [rdi], 0
0x18000444d  mov     rbx, [rsp+28h+arg_8]
0x180004452  add     rsp, 20h
0x180004456  pop     rdi
0x180004457  retn
0x180004458  test    eax, eax
0x18000445a  jns     short loc_180004446
0x18000445c  call    cs:__imp_abort
```
