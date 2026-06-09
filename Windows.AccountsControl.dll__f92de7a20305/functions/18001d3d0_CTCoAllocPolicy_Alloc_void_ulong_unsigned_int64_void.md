# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18001d3d0`
- end: `0x18001d41e`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001c3e8`
- `0x18002a400`
- `0x18002a680`
- `0x18002a8b0`
- `0x18002aa70`
- `0x18003073c`
- `0x1800308a4`
- `0x180030a0c`
- `0x180030b74`
- `0x18006851c`

## callees

- `0x18001d3d0`
- `0x1800212c0`
- `0x1800696f2`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d3e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d3e2`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, char a2, SIZE_T a3, void **a4)
{
  void *v6; // rax
  size_t v7; // rax

  v6 = CoTaskMemAlloc(a3);
  *a4 = v6;
  if ( !v6 )
    return 2147942414LL;
  if ( (a2 & 1) != 0 )
  {
    v7 = CTCoAllocPolicy::_CoTaskMemSize(v6);
    memset_0(*a4, 0, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d3d0  mov     [rsp+arg_0], rbx
0x18001d3d5  push    rdi
0x18001d3d6  sub     rsp, 20h
0x18001d3da  mov     rcx, r8; cb
0x18001d3dd  mov     rdi, r9
0x18001d3e0  mov     ebx, edx
0x18001d3e2  call    cs:__imp_CoTaskMemAlloc
0x18001d3e8  mov     [rdi], rax
0x18001d3eb  test    rax, rax
0x18001d3ee  jz      short loc_18001D40E
0x18001d3f0  test    bl, 1
0x18001d3f3  jz      short loc_18001D40A
0x18001d3f5  mov     rcx, rax; void *
0x18001d3f8  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001d3fd  mov     rcx, [rdi]; void *
0x18001d400  mov     r8, rax; Size
0x18001d403  xor     edx, edx; Val
0x18001d405  call    memset_0
0x18001d40a  xor     eax, eax
0x18001d40c  jmp     short loc_18001D413
0x18001d40e  mov     eax, 8007000Eh
0x18001d413  mov     rbx, [rsp+28h+arg_0]
0x18001d418  add     rsp, 20h
0x18001d41c  pop     rdi
0x18001d41d  retn
```
