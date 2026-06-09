# CoTaskMemAllocWithInit(unsigned __int64,void * *)

- ea: `0x1800096a0`
- end: `0x1800096e6`
- name: `?CoTaskMemAllocWithInit@@YAJ_KPEAPEAX@Z`
- size: `70`
- prototype: `__int64 __fastcall(size_t Size, void **)`
- caller_count: `24`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005ec8`
- `0x180006fc0`
- `0x180008c28`
- `0x180009020`
- `0x180009140`
- `0x18000bbe8`
- `0x180011d08`
- `0x1800121c0`
- `0x1800127e4`
- `0x1800139f0`
- `0x180013bf8`
- `0x180014244`
- `0x180014390`
- `0x180017dc0`
- `0x180017ec4`
- `0x180017f30`
- `0x18001f51c`
- `0x18001f764`
- `0x18001f970`
- `0x18001faf0`
- `0x18001fc4c`
- `0x18001fe04`
- `0x18002000c`
- `0x180020674`

## callees

- `0x1800096a0`
- `0x180017408`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800096b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800096b0`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocWithInit(size_t Size, void **a2)
{
  void *v4; // rax

  v4 = CoTaskMemAlloc(Size);
  *a2 = v4;
  if ( !v4 )
    return 2147942414LL;
  memset_0(v4, 0, Size);
  return 0;
}

```

## disassembly

```asm
0x1800096a0  mov     [rsp+arg_0], rbx
0x1800096a5  push    rdi
0x1800096a6  sub     rsp, 20h
0x1800096aa  mov     rbx, rdx
0x1800096ad  mov     rdi, rcx
0x1800096b0  call    cs:__imp_CoTaskMemAlloc
0x1800096b7  nop     dword ptr [rax+rax+00h]
0x1800096bc  mov     [rbx], rax
0x1800096bf  test    rax, rax
0x1800096c2  jz      short loc_1800096DF
0x1800096c4  mov     r8, rdi; Size
0x1800096c7  xor     edx, edx; Val
0x1800096c9  mov     rcx, rax; void *
0x1800096cc  call    memset_0
0x1800096d1  xor     eax, eax
0x1800096d3  mov     rbx, [rsp+28h+arg_0]
0x1800096d8  add     rsp, 20h
0x1800096dc  pop     rdi
0x1800096dd  retn
0x1800096df  mov     eax, 8007000Eh
0x1800096e4  jmp     short loc_1800096D3
```
