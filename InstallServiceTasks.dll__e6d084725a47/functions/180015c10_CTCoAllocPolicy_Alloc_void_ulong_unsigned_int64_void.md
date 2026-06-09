# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x180015c10`
- end: `0x180015c5e`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `78`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180014c84`

## callees

- `0x180003fe4`
- `0x180015c10`
- `0x1800192e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c22`

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
0x180015c10  mov     [rsp+arg_0], rbx
0x180015c15  push    rdi
0x180015c16  sub     rsp, 20h
0x180015c1a  mov     rcx, r8; cb
0x180015c1d  mov     rdi, r9
0x180015c20  mov     ebx, edx
0x180015c22  call    cs:__imp_CoTaskMemAlloc
0x180015c28  mov     [rdi], rax
0x180015c2b  test    rax, rax
0x180015c2e  jz      short loc_180015C4E
0x180015c30  test    bl, 1
0x180015c33  jz      short loc_180015C4A
0x180015c35  mov     rcx, rax; void *
0x180015c38  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180015c3d  mov     rcx, [rdi]; void *
0x180015c40  mov     r8, rax; Size
0x180015c43  xor     edx, edx; Val
0x180015c45  call    memset_0
0x180015c4a  xor     eax, eax
0x180015c4c  jmp     short loc_180015C53
0x180015c4e  mov     eax, 8007000Eh
0x180015c53  mov     rbx, [rsp+28h+arg_0]
0x180015c58  add     rsp, 20h
0x180015c5c  pop     rdi
0x180015c5d  retn
```
