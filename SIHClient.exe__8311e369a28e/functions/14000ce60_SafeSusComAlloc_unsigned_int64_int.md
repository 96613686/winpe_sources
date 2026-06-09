# SafeSusComAlloc(unsigned __int64,int)

- ea: `0x14000ce60`
- end: `0x14000ce96`
- name: `?SafeSusComAlloc@@YAPEAX_KH@Z`
- size: `54`
- prototype: `void *__fastcall(size_t Size, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000cf80`

## callees

- `0x14000ce60`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ce6d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000ce6d`

## pseudocode

```c
void *__fastcall SafeSusComAlloc(size_t Size)
{
  void *v2; // rax
  void *v3; // rbx

  v2 = CoTaskMemAlloc(Size);
  v3 = v2;
  if ( v2 )
    memset(v2, 0, Size);
  return v3;
}

```

## disassembly

```asm
0x14000ce60  mov     [rsp+arg_0], rbx
0x14000ce65  push    rdi
0x14000ce66  sub     rsp, 20h
0x14000ce6a  mov     rdi, rcx
0x14000ce6d  call    cs:__imp_CoTaskMemAlloc
0x14000ce73  mov     rbx, rax
0x14000ce76  test    rax, rax
0x14000ce79  jz      short loc_14000CE88
0x14000ce7b  mov     r8, rdi; Size
0x14000ce7e  xor     edx, edx; Val
0x14000ce80  mov     rcx, rax; void *
0x14000ce83  call    memset
0x14000ce88  mov     rax, rbx
0x14000ce8b  mov     rbx, [rsp+28h+arg_0]
0x14000ce90  add     rsp, 20h
0x14000ce94  pop     rdi
0x14000ce95  retn
```
