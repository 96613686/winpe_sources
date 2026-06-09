# winrt::impl::root_implements<winrt::Windows::Management::Update::implementation::WindowsSoftwareUpdateVersion,winrt::Windows::Management::Update::WindowsSoftwareUpdateVersion>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x1800144f4`
- end: `0x18001455f`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@UWindowsSoftwareUpdateVersion@implementation@Update@Management@Windows@winrt@@U13456@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180014310`
- `0x180014330`
- `0x180014350`

## callees

- `0x180008653`
- `0x18000866b`
- `0x1800144f4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014557`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180014557`

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
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

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
    return *(unsigned int *)winrt::to_hresult(&lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x1800144f4  push    rbx
0x1800144f6  sub     rsp, 20h
0x1800144fa  mov     rbx, rdx
0x1800144fd  mov     rax, [rcx]
0x180014500  lea     rdx, [rsp+28h+lpMem]
0x180014505  mov     rax, [rax+28h]
0x180014509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001450e  mov     rcx, [rax]
0x180014511  mov     qword ptr [rax], 0
0x180014518  mov     [rbx], rcx
0x18001451b  mov     rbx, [rsp+28h+lpMem]
0x180014520  test    rbx, rbx
0x180014523  jz      short loc_180014545
0x180014525  or      eax, 0FFFFFFFFh
0x180014528  lock xadd [rbx+18h], eax
0x18001452d  sub     eax, 1
0x180014530  jnz     short loc_180014553
0x180014532  nop
0x180014533  call    WINRT_IMPL_GetProcessHeap
0x180014538  mov     rcx, rax; hHeap
0x18001453b  mov     r8, rbx; lpMem
0x18001453e  xor     edx, edx; dwFlags
0x180014540  call    WINRT_IMPL_HeapFree
0x180014545  xor     eax, eax
0x180014547  jmp     short loc_18001454D
0x180014549  mov     eax, dword ptr [rsp+28h+lpMem]
0x18001454d  add     rsp, 20h
0x180014551  pop     rbx
0x180014552  retn
0x180014553  test    eax, eax
0x180014555  jns     short loc_180014545
0x180014557  call    cs:__imp_abort
```
