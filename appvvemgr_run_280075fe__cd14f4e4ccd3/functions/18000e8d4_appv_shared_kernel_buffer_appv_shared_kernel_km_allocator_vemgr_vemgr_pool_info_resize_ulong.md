# appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(ulong)

- ea: `0x18000e8d4`
- end: `0x18000e958`
- name: `?resize@?$buffer@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJK@Z`
- size: `132`
- prototype: ``
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x1800040dc`
- `0x180009434`
- `0x18000a864`
- `0x18000a9e4`
- `0x18000ab2c`
- `0x18000acbc`
- `0x18000bfb8`
- `0x18000c31c`
- `0x18000ce9c`
- `0x18000d054`
- `0x180014d1c`
- `0x18001ad74`

## callees

- `0x18000e8d4`
- `0x18001bc00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x18000e903`
- `ntoskrnl!ExAllocatePool2` at `0x18000e903`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e940`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000e940`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::buffer<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::resize(
        unsigned int *a1,
        unsigned int a2)
{
  unsigned int v2; // esi
  size_t v4; // rbp
  void *v5; // rdi
  void *Pool2; // rax
  __int64 result; // rax

  v2 = a1[1];
  if ( a2 > v2 )
  {
    v4 = *a1;
    v5 = (void *)*((_QWORD *)a1 + 1);
    *a1 = a2;
    a1[1] = a2;
    Pool2 = (void *)ExAllocatePool2(256, a2, 1733125462);
    *((_QWORD *)a1 + 1) = Pool2;
    if ( !Pool2 )
    {
      *a1 = v4;
      result = 3221225626LL;
      a1[1] = v2;
      *((_QWORD *)a1 + 1) = v5;
      return result;
    }
    if ( v5 )
    {
      memmove(Pool2, v5, v4);
      ExFreePoolWithTag(v5, 0);
    }
  }
  else
  {
    *a1 = a2;
  }
  return 0;
}

```

## disassembly

```asm
0x18000e8d4  push    rbx
0x18000e8d6  push    rbp
0x18000e8d7  push    rsi
0x18000e8d8  push    rdi
0x18000e8d9  sub     rsp, 28h
0x18000e8dd  mov     esi, [rcx+4]
0x18000e8e0  mov     rbx, rcx
0x18000e8e3  cmp     edx, esi
0x18000e8e5  ja      short loc_18000E8EB
0x18000e8e7  mov     [rcx], edx
0x18000e8e9  jmp     short loc_18000E94C
0x18000e8eb  mov     ebp, [rcx]
0x18000e8ed  mov     r8d, 674D6556h
0x18000e8f3  mov     rdi, [rcx+8]
0x18000e8f7  mov     [rcx], edx
0x18000e8f9  mov     [rcx+4], edx
0x18000e8fc  mov     ecx, 100h
0x18000e901  mov     edx, edx
0x18000e903  call    cs:__imp_ExAllocatePool2
0x18000e90a  nop     dword ptr [rax+rax+00h]
0x18000e90f  mov     [rbx+8], rax
0x18000e913  test    rax, rax
0x18000e916  jnz     short loc_18000E928
0x18000e918  mov     [rbx], ebp
0x18000e91a  mov     eax, 0C000009Ah
0x18000e91f  mov     [rbx+4], esi
0x18000e922  mov     [rbx+8], rdi
0x18000e926  jmp     short loc_18000E94E
0x18000e928  test    rdi, rdi
0x18000e92b  jz      short loc_18000E94C
0x18000e92d  mov     r8, rbp; Size
0x18000e930  mov     rdx, rdi; Src
0x18000e933  mov     rcx, rax; void *
0x18000e936  call    memmove
0x18000e93b  xor     edx, edx; Tag
0x18000e93d  mov     rcx, rdi; P
0x18000e940  call    cs:__imp_ExFreePoolWithTag
0x18000e947  nop     dword ptr [rax+rax+00h]
0x18000e94c  xor     eax, eax
0x18000e94e  add     rsp, 28h
0x18000e952  pop     rdi
0x18000e953  pop     rsi
0x18000e954  pop     rbp
0x18000e955  pop     rbx
0x18000e956  retn
```
