# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x18001508c`
- end: `0x1800150fb`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `111`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014ea0`
- `0x180014ec0`
- `0x180014ee0`

## callees

- `0x180008bf4`
- `0x180008c0c`
- `0x18001508c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800150ed`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800150ed`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  void *v5; // rbx
  int v6; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  int v9; // [rsp+30h] [rbp+8h] BYREF
  LPVOID lpMem; // [rsp+40h] [rbp+18h]

  try
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v4 = *v3;
    *v3 = 0;
    *a2 = v4;
    v5 = lpMem;
    if ( lpMem )
    {
      v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v6 )
      {
        if ( v6 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v5);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x18001508c  push    rbx
0x18001508e  sub     rsp, 20h
0x180015092  mov     rbx, rdx
0x180015095  mov     rax, [rcx]
0x180015098  lea     rdx, [rsp+28h+lpMem]
0x18001509d  mov     rax, [rax+28h]
0x1800150a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150a6  mov     rcx, [rax]
0x1800150a9  and     qword ptr [rax], 0
0x1800150ad  mov     [rbx], rcx
0x1800150b0  mov     rbx, [rsp+28h+lpMem]
0x1800150b5  test    rbx, rbx
0x1800150b8  jz      short loc_1800150DA
0x1800150ba  or      eax, 0FFFFFFFFh
0x1800150bd  lock xadd [rbx+18h], eax
0x1800150c2  sub     eax, 1
0x1800150c5  jnz     short loc_1800150E9
0x1800150c7  nop
0x1800150c8  call    WINRT_IMPL_GetProcessHeap
0x1800150cd  mov     rcx, rax; hHeap
0x1800150d0  mov     r8, rbx; lpMem
0x1800150d3  xor     edx, edx; dwFlags
0x1800150d5  call    WINRT_IMPL_HeapFree
0x1800150da  xor     eax, eax
0x1800150dc  jmp     short loc_1800150E2
0x1800150de  mov     eax, [rsp+28h+arg_0]
0x1800150e2  add     rsp, 20h
0x1800150e6  pop     rbx
0x1800150e7  retn
0x1800150e9  test    eax, eax
0x1800150eb  jns     short loc_1800150DA
0x1800150ed  call    cs:__imp_abort
```
