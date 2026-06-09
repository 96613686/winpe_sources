# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18000fddc`
- end: `0x18000fe03`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `39`
- prototype: `__int64 __fastcall(void *, __int64, SIZE_T, void **)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000fa0c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fde8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000fde8`

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
0x18000fddc  push    rbx
0x18000fdde  sub     rsp, 20h
0x18000fde2  mov     rcx, r8; cb
0x18000fde5  mov     rbx, r9
0x18000fde8  call    cs:__imp_CoTaskMemAlloc
0x18000fdee  mov     [rbx], rax
0x18000fdf1  neg     rax
0x18000fdf4  sbb     eax, eax
0x18000fdf6  not     eax
0x18000fdf8  and     eax, 8007000Eh
0x18000fdfd  add     rsp, 20h
0x18000fe01  pop     rbx
0x18000fe02  retn
```
