# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x180024a54`
- end: `0x180024aae`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `90`
- prototype: `static int(void *, unsigned int, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180026eb0`

## callees

- `0x1800033a0`
- `0x180024a54`
- `0x180025360`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180024a67`

## pseudocode

```c
__int64 __fastcall CTCoAllocPolicy::Realloc(void *a1, __int64 a2, void *a3, SIZE_T a4, void **a5)
{
  void *v6; // rax
  unsigned __int64 v7; // rax

  v6 = CoTaskMemRealloc(a3, a4);
  *a5 = v6;
  if ( !v6 )
    return 2147942414LL;
  v7 = CTCoAllocPolicy::_CoTaskMemSize(v6);
  if ( v7 > a4 )
    memset_0((char *)*a5 + a4, 0, v7 - a4);
  return 0;
}

```

## disassembly

```asm
0x180024a54  mov     [rsp+arg_0], rbx
0x180024a59  push    rdi
0x180024a5a  sub     rsp, 20h
0x180024a5e  mov     rdx, r9; cb
0x180024a61  mov     rcx, r8; pv
0x180024a64  mov     rbx, r9
0x180024a67  call    cs:__imp_CoTaskMemRealloc
0x180024a6d  mov     rdi, [rsp+28h+arg_20]
0x180024a72  mov     [rdi], rax
0x180024a75  test    rax, rax
0x180024a78  jz      short loc_180024A9E
0x180024a7a  mov     rcx, rax; void *
0x180024a7d  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180024a82  cmp     rax, rbx
0x180024a85  jbe     short loc_180024A9A
0x180024a87  mov     rcx, [rdi]
0x180024a8a  sub     rax, rbx
0x180024a8d  add     rcx, rbx; void *
0x180024a90  mov     r8, rax; Size
0x180024a93  xor     edx, edx; Val
0x180024a95  call    memset_0
0x180024a9a  xor     eax, eax
0x180024a9c  jmp     short loc_180024AA3
0x180024a9e  mov     eax, 8007000Eh
0x180024aa3  mov     rbx, [rsp+28h+arg_0]
0x180024aa8  add     rsp, 20h
0x180024aac  pop     rdi
0x180024aad  retn
```
