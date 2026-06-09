# winrt::handle_type<winrt::impl::hstring_traits>::close(void)

- ea: `0x180007118`
- end: `0x18000715e`
- name: `?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ`
- size: `70`
- prototype: `void __fastcall(volatile signed __int32 **)`
- caller_count: `22`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180006ae0`
- `0x180006d68`
- `0x18000803c`
- `0x1800095d0`
- `0x180009f40`
- `0x18000c534`
- `0x18000cc58`
- `0x18000d424`
- `0x18000ddd8`
- `0x18000ef84`
- `0x18000f358`
- `0x18000f660`
- `0x180011954`
- `0x180011a10`
- `0x180011ea8`
- `0x180012918`
- `0x180012a58`
- `0x180015400`
- `0x180015a9c`
- `0x180016f22`
- `0x180016fc3`
- `0x180017067`

## callees

- `0x180002be4`
- `0x180002c38`
- `0x180006aec`
- `0x180007118`

## pseudocode

```c
void __fastcall winrt::handle_type<winrt::impl::hstring_traits>::close(volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    if ( !(unsigned int)winrt::impl::atomic_ref_count::operator--(v1 + 6) )
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
0x180007118  mov     [rsp+arg_0], rbx
0x18000711d  push    rdi
0x18000711e  sub     rsp, 20h
0x180007122  mov     rbx, [rcx]
0x180007125  mov     rdi, rcx
0x180007128  test    rbx, rbx
0x18000712b  jz      short loc_180007153
0x18000712d  lea     rcx, [rbx+18h]
0x180007131  call    ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
0x180007136  test    eax, eax
0x180007138  jnz     short loc_18000714C
0x18000713a  call    WINRT_IMPL_GetProcessHeap
0x18000713f  mov     rcx, rax; hHeap
0x180007142  mov     r8, rbx; lpMem
0x180007145  xor     edx, edx; dwFlags
0x180007147  call    WINRT_IMPL_HeapFree
0x18000714c  mov     qword ptr [rdi], 0
0x180007153  mov     rbx, [rsp+28h+arg_0]
0x180007158  add     rsp, 20h
0x18000715c  pop     rdi
0x18000715d  retn
```
