# winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(void)

- ea: `0x1800052a0`
- end: `0x1800052f3`
- name: `??1?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAA@XZ`
- size: `83`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c514`
- `0x18000c63a`
- `0x18000c760`

## callees

- `0x1800052a0`
- `0x180007250`
- `0x180007262`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052ec`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800052ec`

## pseudocode

```c
void __fastcall winrt::handle_type<winrt::impl::hstring_traits>::~handle_type<winrt::impl::hstring_traits>(
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
0x1800052a0  mov     [rsp+arg_8], rbx
0x1800052a5  push    rdi
0x1800052a6  sub     rsp, 20h
0x1800052aa  mov     rbx, [rcx]
0x1800052ad  mov     rdi, rcx
0x1800052b0  test    rbx, rbx
0x1800052b3  jz      short loc_1800052DD
0x1800052b5  mov     eax, 0FFFFFFFFh
0x1800052ba  lock xadd [rbx+18h], eax
0x1800052bf  sub     eax, 1
0x1800052c2  jnz     short loc_1800052E8
0x1800052c4  call    WINRT_IMPL_GetProcessHeap
0x1800052c9  mov     rcx, rax; hHeap
0x1800052cc  mov     r8, rbx; lpMem
0x1800052cf  xor     edx, edx; dwFlags
0x1800052d1  call    WINRT_IMPL_HeapFree
0x1800052d6  mov     qword ptr [rdi], 0
0x1800052dd  mov     rbx, [rsp+28h+arg_8]
0x1800052e2  add     rsp, 20h
0x1800052e6  pop     rdi
0x1800052e7  retn
0x1800052e8  test    eax, eax
0x1800052ea  jns     short loc_1800052D6
0x1800052ec  call    cs:__imp_abort
```
