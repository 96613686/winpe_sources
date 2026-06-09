# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x1800469b0`
- end: `0x1800469fe`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014e14`
- `0x180047110`

## callees

- `0x180017e20`
- `0x1800469b0`
- `0x180049198`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800469c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800469c2`

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
0x1800469b0  mov     [rsp+arg_0], rbx
0x1800469b5  push    rdi
0x1800469b6  sub     rsp, 20h
0x1800469ba  mov     rcx, r8; cb
0x1800469bd  mov     rdi, r9
0x1800469c0  mov     ebx, edx
0x1800469c2  call    cs:__imp_CoTaskMemAlloc
0x1800469c8  mov     [rdi], rax
0x1800469cb  test    rax, rax
0x1800469ce  jz      short loc_1800469EE
0x1800469d0  test    bl, 1
0x1800469d3  jz      short loc_1800469EA
0x1800469d5  mov     rcx, rax; void *
0x1800469d8  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x1800469dd  mov     rcx, [rdi]; void *
0x1800469e0  mov     r8, rax; Size
0x1800469e3  xor     edx, edx; Val
0x1800469e5  call    memset_0
0x1800469ea  xor     eax, eax
0x1800469ec  jmp     short loc_1800469F3
0x1800469ee  mov     eax, 8007000Eh
0x1800469f3  mov     rbx, [rsp+28h+arg_0]
0x1800469f8  add     rsp, 20h
0x1800469fc  pop     rdi
0x1800469fd  retn
```
