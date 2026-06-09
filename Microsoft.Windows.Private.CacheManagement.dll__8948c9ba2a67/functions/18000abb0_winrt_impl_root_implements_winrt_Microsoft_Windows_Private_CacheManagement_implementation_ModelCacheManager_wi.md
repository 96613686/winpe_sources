# winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x18000abb0`
- end: `0x18000ac1d`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@UModelCacheManager@implementation@CacheManagement@Private@Windows@Microsoft@winrt@@U134567@UIModelCacheManager2@34567@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180008f30`
- `0x180009030`

## callees

- `0x18000abb0`
- `0x180016298`
- `0x18001629e`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000ac15`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000ac15`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::Private::CacheManagement::implementation::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::ModelCacheManager,winrt::Microsoft::Windows::Private::CacheManagement::IModelCacheManager2>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem[3]; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v4 = *v3;
    *v3 = 0;
    *a2 = v4;
    if ( lpMem[0] )
    {
      v5 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v5 )
      {
        if ( v5 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem[0]);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000abb0  push    rbx
0x18000abb2  sub     rsp, 30h
0x18000abb6  mov     rbx, rdx
0x18000abb9  mov     rax, [rcx]
0x18000abbc  lea     rdx, [rsp+38h+lpMem]
0x18000abc1  mov     rax, [rax+28h]
0x18000abc5  call    cs:__guard_dispatch_icall_fptr
0x18000abcb  mov     rcx, [rax]
0x18000abce  mov     qword ptr [rax], 0
0x18000abd5  mov     [rbx], rcx
0x18000abd8  mov     rbx, [rsp+38h+lpMem]
0x18000abdd  test    rbx, rbx
0x18000abe0  jz      short loc_18000AC03
0x18000abe2  mov     eax, 0FFFFFFFFh
0x18000abe7  lock xadd [rbx+18h], eax
0x18000abec  sub     eax, 1
0x18000abef  jnz     short loc_18000AC11
0x18000abf1  call    WINRT_IMPL_GetProcessHeap
0x18000abf6  mov     rcx, rax; hHeap
0x18000abf9  mov     r8, rbx; lpMem
0x18000abfc  xor     edx, edx; dwFlags
0x18000abfe  call    WINRT_IMPL_HeapFree
0x18000ac03  xor     eax, eax
0x18000ac05  jmp     short loc_18000AC0B
0x18000ac07  mov     eax, dword ptr [rsp+38h+lpMem]
0x18000ac0b  add     rsp, 30h
0x18000ac0f  pop     rbx
0x18000ac10  retn
0x18000ac11  test    eax, eax
0x18000ac13  jns     short loc_18000AC03
0x18000ac15  call    cs:__imp_abort
```
