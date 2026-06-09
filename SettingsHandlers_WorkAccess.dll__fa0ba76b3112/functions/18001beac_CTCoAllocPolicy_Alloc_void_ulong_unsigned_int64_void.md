# CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)

- ea: `0x18001beac`
- end: `0x18001bf01`
- name: `?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z`
- size: `85`
- prototype: `static int(void *, unsigned int, unsigned __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e100`
- `0x1800224e8`

## callees

- `0x180003534`
- `0x18001beac`
- `0x18001ff98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bebe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bebe`

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
0x18001beac  mov     [rsp+arg_0], rbx
0x18001beb1  push    rdi
0x18001beb2  sub     rsp, 20h
0x18001beb6  mov     rcx, r8; cb
0x18001beb9  mov     rdi, r9
0x18001bebc  mov     ebx, edx
0x18001bebe  call    cs:__imp_CoTaskMemAlloc
0x18001bec5  nop     dword ptr [rax+rax+00h]
0x18001beca  mov     [rdi], rax
0x18001becd  test    rax, rax
0x18001bed0  jz      short loc_18001BEF0
0x18001bed2  test    bl, 1
0x18001bed5  jz      short loc_18001BEEC
0x18001bed7  mov     rcx, rax; void *
0x18001beda  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18001bedf  mov     rcx, [rdi]; void *
0x18001bee2  mov     r8, rax; Size
0x18001bee5  xor     edx, edx; Val
0x18001bee7  call    memset_0
0x18001beec  xor     eax, eax
0x18001beee  jmp     short loc_18001BEF5
0x18001bef0  mov     eax, 8007000Eh
0x18001bef5  mov     rbx, [rsp+28h+arg_0]
0x18001befa  add     rsp, 20h
0x18001befe  pop     rdi
0x18001beff  retn
```
