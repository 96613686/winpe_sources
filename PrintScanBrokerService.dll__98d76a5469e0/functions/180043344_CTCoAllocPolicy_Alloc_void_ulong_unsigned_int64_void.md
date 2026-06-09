# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180043344`
- end: `0x180043392`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180043290`
- `0x180043f5c`
- `0x180044088`

## callees

- `0x180003a0c`
- `0x180043344`
- `0x180043cc8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043356`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043356`

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
0x180043344  mov     [rsp+arg_0], rbx
0x180043349  push    rdi
0x18004334a  sub     rsp, 20h
0x18004334e  mov     rcx, r8; cb
0x180043351  mov     rdi, r9
0x180043354  mov     ebx, edx
0x180043356  call    cs:__imp_CoTaskMemAlloc
0x18004335c  mov     [rdi], rax
0x18004335f  test    rax, rax
0x180043362  jz      short loc_180043382
0x180043364  test    bl, 1
0x180043367  jz      short loc_18004337E
0x180043369  mov     rcx, rax; void *
0x18004336c  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180043371  mov     rcx, [rdi]; void *
0x180043374  mov     r8, rax; Size
0x180043377  xor     edx, edx; Val
0x180043379  call    memset_0
0x18004337e  xor     eax, eax
0x180043380  jmp     short loc_180043387
0x180043382  mov     eax, 8007000Eh
0x180043387  mov     rbx, [rsp+28h+arg_0]
0x18004338c  add     rsp, 20h
0x180043390  pop     rdi
0x180043391  retn
```
