# winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x180006ae0`
- end: `0x180006b4d`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@UImageBufferResource@implementation@PrivateCommon@Windows@Microsoft@winrt@@U13456@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005fa0`
- `0x180006260`

## callees

- `0x180006ae0`
- `0x180007250`
- `0x180007262`
- `0x18000b930`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006b45`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006b45`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Microsoft::Windows::PrivateCommon::implementation::ImageBufferResource,winrt::Microsoft::Windows::PrivateCommon::ImageBufferResource>::NonDelegatingGetRuntimeClassName(
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
0x180006ae0  push    rbx
0x180006ae2  sub     rsp, 30h
0x180006ae6  mov     rbx, rdx
0x180006ae9  mov     rax, [rcx]
0x180006aec  lea     rdx, [rsp+38h+lpMem]
0x180006af1  mov     rax, [rax+28h]
0x180006af5  call    cs:__guard_dispatch_icall_fptr
0x180006afb  mov     rcx, [rax]
0x180006afe  mov     qword ptr [rax], 0
0x180006b05  mov     [rbx], rcx
0x180006b08  mov     rbx, [rsp+38h+lpMem]
0x180006b0d  test    rbx, rbx
0x180006b10  jz      short loc_180006B33
0x180006b12  mov     eax, 0FFFFFFFFh
0x180006b17  lock xadd [rbx+18h], eax
0x180006b1c  sub     eax, 1
0x180006b1f  jnz     short loc_180006B41
0x180006b21  call    WINRT_IMPL_GetProcessHeap
0x180006b26  mov     rcx, rax; hHeap
0x180006b29  mov     r8, rbx; lpMem
0x180006b2c  xor     edx, edx; dwFlags
0x180006b2e  call    WINRT_IMPL_HeapFree
0x180006b33  xor     eax, eax
0x180006b35  jmp     short loc_180006B3B
0x180006b37  mov     eax, dword ptr [rsp+38h+lpMem]
0x180006b3b  add     rsp, 30h
0x180006b3f  pop     rbx
0x180006b40  retn
0x180006b41  test    eax, eax
0x180006b43  jns     short loc_180006B33
0x180006b45  call    cs:__imp_abort
```
