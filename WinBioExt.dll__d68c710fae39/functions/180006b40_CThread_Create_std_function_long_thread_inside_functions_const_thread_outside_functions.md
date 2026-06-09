# CThread::Create(std::function<long (thread_inside_functions &)> const &,thread_outside_functions * *)

- ea: `0x180006b40`
- end: `0x180006b86`
- name: `?Create@CThread@@CAJAEBV?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@PEAPEAVthread_outside_functions@@@Z`
- size: `70`
- prototype: `__int64 __fastcall(__int64, volatile signed __int32 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180006b8c`

## callees

- `0x180001ec8`
- `0x180006700`
- `0x180006b40`

## pseudocode

```c
__int64 __fastcall CThread::Create(__int64 a1, volatile signed __int32 **a2)
{
  void *v3; // rcx
  volatile signed __int32 *v4; // rax
  __int64 result; // rax

  try
  {
    v3 = operator new(0x80u);
    v4 = (volatile signed __int32 *)CThread::CThread(v3);
    *a2 = v4;
    _InterlockedIncrement(v4);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  v3 = operator new(0x80u);
}

```

## disassembly

```asm
0x180006b40  mov     [rsp+arg_0], rbx
0x180006b45  push    rdi
0x180006b46  sub     rsp, 20h
0x180006b4a  mov     rbx, rdx
0x180006b4d  mov     rdi, rcx
0x180006b50  mov     ecx, 80h; Size
0x180006b55  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b5a  mov     [rsp+28h+arg_10], rax
0x180006b5f  mov     rdx, rdi
0x180006b62  mov     rcx, rax; lpParameter
0x180006b65  call    ??0CThread@@AEAA@AEBV?$function@$$A6AJAEAVthread_inside_functions@@@Z@std@@@Z; CThread::CThread(std::function<long (thread_inside_functions &)> const &)
0x180006b6a  nop
0x180006b6b  mov     [rbx], rax
0x180006b6e  lock inc dword ptr [rax]
0x180006b71  xor     eax, eax
0x180006b73  jmp     short loc_180006B7A
0x180006b75  mov     eax, 8007000Eh
0x180006b7a  mov     rbx, [rsp+28h+arg_0]
0x180006b7f  add     rsp, 20h
0x180006b83  pop     rdi
0x180006b84  retn
```
