# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180055fa8`
- end: `0x180055fcf`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180055f08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055fb4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180055fb4`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Alloc(void *a1, __int64 a2, SIZE_T a3, void **a4)
{
  void *v5; // rax

  v5 = CoTaskMemAlloc(a3);
  *a4 = v5;
  return v5 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180055fa8  push    rbx
0x180055faa  sub     rsp, 20h
0x180055fae  mov     rcx, r8; cb
0x180055fb1  mov     rbx, r9
0x180055fb4  call    cs:__imp_CoTaskMemAlloc
0x180055fba  mov     [rbx], rax
0x180055fbd  neg     rax
0x180055fc0  sbb     eax, eax
0x180055fc2  not     eax
0x180055fc4  and     eax, 8007000Eh
0x180055fc9  add     rsp, 20h
0x180055fcd  pop     rbx
0x180055fce  retn
```
