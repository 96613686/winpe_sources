# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180033e8c`
- end: `0x180033eda`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180033c88`
- `0x180054858`

## callees

- `0x1800033a0`
- `0x180025360`
- `0x180033e8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033e9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180033e9e`

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
0x180033e8c  mov     [rsp+arg_0], rbx
0x180033e91  push    rdi
0x180033e92  sub     rsp, 20h
0x180033e96  mov     rcx, r8; cb
0x180033e99  mov     rdi, r9
0x180033e9c  mov     ebx, edx
0x180033e9e  call    cs:__imp_CoTaskMemAlloc
0x180033ea4  mov     [rdi], rax
0x180033ea7  test    rax, rax
0x180033eaa  jz      short loc_180033ECA
0x180033eac  test    bl, 1
0x180033eaf  jz      short loc_180033EC6
0x180033eb1  mov     rcx, rax; void *
0x180033eb4  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180033eb9  mov     rcx, [rdi]; void *
0x180033ebc  mov     r8, rax; Size
0x180033ebf  xor     edx, edx; Val
0x180033ec1  call    memset_0
0x180033ec6  xor     eax, eax
0x180033ec8  jmp     short loc_180033ECF
0x180033eca  mov     eax, 8007000Eh
0x180033ecf  mov     rbx, [rsp+28h+arg_0]
0x180033ed4  add     rsp, 20h
0x180033ed8  pop     rdi
0x180033ed9  retn
```
