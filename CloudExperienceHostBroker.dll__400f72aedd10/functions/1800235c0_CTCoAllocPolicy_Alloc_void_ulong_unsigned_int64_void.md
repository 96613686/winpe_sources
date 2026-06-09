# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800235c0`
- end: `0x1800235e7`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180020f04`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800235cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800235cc`

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
0x1800235c0  push    rbx
0x1800235c2  sub     rsp, 20h
0x1800235c6  mov     rcx, r8; cb
0x1800235c9  mov     rbx, r9
0x1800235cc  call    cs:__imp_CoTaskMemAlloc
0x1800235d2  mov     [rbx], rax
0x1800235d5  neg     rax
0x1800235d8  sbb     eax, eax
0x1800235da  not     eax
0x1800235dc  and     eax, 8007000Eh
0x1800235e1  add     rsp, 20h
0x1800235e5  pop     rbx
0x1800235e6  retn
```
