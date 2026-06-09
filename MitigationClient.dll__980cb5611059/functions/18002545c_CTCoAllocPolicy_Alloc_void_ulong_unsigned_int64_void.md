# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18002545c`
- end: `0x1800254aa`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180025130`
- `0x1800278dc`
- `0x18003b6f0`
- `0x18003db9c`

## callees

- `0x18000b2b4`
- `0x180016ce8`
- `0x18002545c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002546e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002546e`

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
0x18002545c  mov     [rsp+arg_0], rbx
0x180025461  push    rdi
0x180025462  sub     rsp, 20h
0x180025466  mov     rcx, r8; cb
0x180025469  mov     rdi, r9
0x18002546c  mov     ebx, edx
0x18002546e  call    cs:__imp_CoTaskMemAlloc
0x180025474  mov     [rdi], rax
0x180025477  test    rax, rax
0x18002547a  jz      short loc_18002549A
0x18002547c  test    bl, 1
0x18002547f  jz      short loc_180025496
0x180025481  mov     rcx, rax; void *
0x180025484  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180025489  mov     rcx, [rdi]; void *
0x18002548c  mov     r8, rax; Size
0x18002548f  xor     edx, edx; Val
0x180025491  call    memset_0
0x180025496  xor     eax, eax
0x180025498  jmp     short loc_18002549F
0x18002549a  mov     eax, 8007000Eh
0x18002549f  mov     rbx, [rsp+28h+arg_0]
0x1800254a4  add     rsp, 20h
0x1800254a8  pop     rdi
0x1800254a9  retn
```
