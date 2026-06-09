# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x14000aad0`
- end: `0x14000aaf7`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `__int64 __fastcall(void *, __int64, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400071d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000aadc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000aadc`

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
0x14000aad0  push    rbx
0x14000aad2  sub     rsp, 20h
0x14000aad6  mov     rcx, r8; cb
0x14000aad9  mov     rbx, r9
0x14000aadc  call    cs:__imp_CoTaskMemAlloc
0x14000aae2  mov     [rbx], rax
0x14000aae5  neg     rax
0x14000aae8  sbb     eax, eax
0x14000aaea  not     eax
0x14000aaec  and     eax, 8007000Eh
0x14000aaf1  add     rsp, 20h
0x14000aaf5  pop     rbx
0x14000aaf6  retn
```
