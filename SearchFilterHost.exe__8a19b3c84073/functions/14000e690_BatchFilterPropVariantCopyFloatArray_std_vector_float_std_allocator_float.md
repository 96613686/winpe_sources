# BatchFilterPropVariantCopyFloatArray(std::vector<float,std::allocator<float>> &)

- ea: `0x14000e690`
- end: `0x14000e6e8`
- name: `?BatchFilterPropVariantCopyFloatArray@@YAPEAMAEAV?$vector@MV?$allocator@M@std@@@std@@@Z`
- size: `88`
- prototype: `void *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000e7ec`

## callees

- `0x140005205`
- `0x14000e690`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e6b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000e6b9`

## pseudocode

```c
void *__fastcall BatchFilterPropVariantCopyFloatArray(__int64 a1)
{
  __int64 v1; // rax
  SIZE_T v4; // rsi
  void *v5; // rax
  void *v6; // rdi

  v1 = *(_QWORD *)(a1 + 8);
  if ( *(_QWORD *)a1 == v1 )
    return 0;
  v4 = ((_DWORD)v1 - *(_DWORD *)a1) & 0xFFFFFFFC;
  v5 = CoTaskMemAlloc(v4);
  v6 = v5;
  if ( v5 )
    memcpy_0(v5, *(const void **)a1, (unsigned int)v4);
  return v6;
}

```

## disassembly

```asm
0x14000e690  mov     [rsp+arg_0], rbx
0x14000e695  mov     [rsp+arg_8], rsi
0x14000e69a  push    rdi
0x14000e69b  sub     rsp, 20h
0x14000e69f  mov     rax, [rcx+8]
0x14000e6a3  mov     rbx, rcx
0x14000e6a6  cmp     [rcx], rax
0x14000e6a9  jnz     short loc_14000E6AF
0x14000e6ab  xor     eax, eax
0x14000e6ad  jmp     short loc_14000E6D8
0x14000e6af  sub     rax, [rcx]
0x14000e6b2  and     eax, 0FFFFFFFCh
0x14000e6b5  mov     ecx, eax; cb
0x14000e6b7  mov     esi, eax
0x14000e6b9  call    cs:__imp_CoTaskMemAlloc
0x14000e6bf  mov     rdi, rax
0x14000e6c2  test    rax, rax
0x14000e6c5  jz      short loc_14000E6D5
0x14000e6c7  mov     rdx, [rbx]; Src
0x14000e6ca  mov     r8d, esi; Size
0x14000e6cd  mov     rcx, rax; void *
0x14000e6d0  call    memcpy_0
0x14000e6d5  mov     rax, rdi
0x14000e6d8  mov     rbx, [rsp+28h+arg_0]
0x14000e6dd  mov     rsi, [rsp+28h+arg_8]
0x14000e6e2  add     rsp, 20h
0x14000e6e6  pop     rdi
0x14000e6e7  retn
```
