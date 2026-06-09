# BatchFilterPropVariantCopyByteArray(std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x14000e634`
- end: `0x14000e689`
- name: `?BatchFilterPropVariantCopyByteArray@@YAPEAEAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `85`
- prototype: `void *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e7ec`

## callees

- `0x140005205`
- `0x14000e634`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e65a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e65a`

## pseudocode

```c
void *__fastcall BatchFilterPropVariantCopyByteArray(__int64 a1)
{
  __int64 v1; // rax
  SIZE_T v4; // rsi
  void *v5; // rax
  void *v6; // rdi

  v1 = *(_QWORD *)(a1 + 8);
  if ( *(_QWORD *)a1 == v1 )
    return 0;
  v4 = (unsigned int)(v1 - *(_DWORD *)a1);
  v5 = CoTaskMemAlloc(v4);
  v6 = v5;
  if ( v5 )
    memcpy_0(v5, *(const void **)a1, (unsigned int)v4);
  return v6;
}

```

## disassembly

```asm
0x14000e634  mov     [rsp+arg_0], rbx
0x14000e639  mov     [rsp+arg_8], rsi
0x14000e63e  push    rdi
0x14000e63f  sub     rsp, 20h
0x14000e643  mov     rax, [rcx+8]
0x14000e647  mov     rbx, rcx
0x14000e64a  cmp     [rcx], rax
0x14000e64d  jnz     short loc_14000E653
0x14000e64f  xor     eax, eax
0x14000e651  jmp     short loc_14000E679
0x14000e653  sub     rax, [rcx]
0x14000e656  mov     ecx, eax; cb
0x14000e658  mov     esi, eax
0x14000e65a  call    cs:__imp_CoTaskMemAlloc
0x14000e660  mov     rdi, rax
0x14000e663  test    rax, rax
0x14000e666  jz      short loc_14000E676
0x14000e668  mov     rdx, [rbx]; Src
0x14000e66b  mov     r8d, esi; Size
0x14000e66e  mov     rcx, rax; void *
0x14000e671  call    memcpy_0
0x14000e676  mov     rax, rdi
0x14000e679  mov     rbx, [rsp+28h+arg_0]
0x14000e67e  mov     rsi, [rsp+28h+arg_8]
0x14000e683  add     rsp, 20h
0x14000e687  pop     rdi
0x14000e688  retn
```
