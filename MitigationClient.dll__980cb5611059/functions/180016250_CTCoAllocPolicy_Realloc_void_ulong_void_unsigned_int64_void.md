# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x180016250`
- end: `0x1800162aa`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `90`
- prototype: `static int(void *, unsigned int, void *, unsigned __int64, void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016d4c`
- `0x180017ba8`
- `0x1800278dc`

## callees

- `0x18000b2b4`
- `0x180016250`
- `0x180016ce8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180016263`

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
0x180016250  mov     [rsp+arg_0], rbx
0x180016255  push    rdi
0x180016256  sub     rsp, 20h
0x18001625a  mov     rdx, r9; cb
0x18001625d  mov     rcx, r8; pv
0x180016260  mov     rbx, r9
0x180016263  call    cs:__imp_CoTaskMemRealloc
0x180016269  mov     rdi, [rsp+28h+arg_20]
0x18001626e  mov     [rdi], rax
0x180016271  test    rax, rax
0x180016274  jz      short loc_18001629A
0x180016276  mov     rcx, rax; void *
0x180016279  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001627e  cmp     rax, rbx
0x180016281  jbe     short loc_180016296
0x180016283  mov     rcx, [rdi]
0x180016286  sub     rax, rbx
0x180016289  add     rcx, rbx; void *
0x18001628c  mov     r8, rax; Size
0x18001628f  xor     edx, edx; Val
0x180016291  call    memset_0
0x180016296  xor     eax, eax
0x180016298  jmp     short loc_18001629F
0x18001629a  mov     eax, 8007000Eh
0x18001629f  mov     rbx, [rsp+28h+arg_0]
0x1800162a4  add     rsp, 20h
0x1800162a8  pop     rdi
0x1800162a9  retn
```
