# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180023940`
- end: `0x180023967`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `__int64 __fastcall(void *, __int64, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180023ba0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394c`

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
0x180023940  push    rbx
0x180023942  sub     rsp, 20h
0x180023946  mov     rcx, r8; cb
0x180023949  mov     rbx, r9
0x18002394c  call    cs:__imp_CoTaskMemAlloc
0x180023952  mov     [rbx], rax
0x180023955  neg     rax
0x180023958  sbb     eax, eax
0x18002395a  not     eax
0x18002395c  and     eax, 8007000Eh
0x180023961  add     rsp, 20h
0x180023965  pop     rbx
0x180023966  retn
```
