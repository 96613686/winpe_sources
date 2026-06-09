# CTCoAllocPolicy::Realloc(void *,ulong,void *,unsigned __int64,void * *)

- ea: `0x180012fd4`
- end: `0x18001302e`
- name: `?Realloc@CTCoAllocPolicy@@SAJPEAXK0_KPEAPEAX@Z`
- size: `90`
- prototype: `static int(void *, unsigned int, void *, unsigned __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002a7e0`

## callees

- `0x180009cf0`
- `0x180012fd4`
- `0x180013808`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180012fe7`

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
0x180012fd4  mov     [rsp+arg_0], rbx
0x180012fd9  push    rdi
0x180012fda  sub     rsp, 20h
0x180012fde  mov     rdx, r9; cb
0x180012fe1  mov     rcx, r8; pv
0x180012fe4  mov     rbx, r9
0x180012fe7  call    cs:__imp_CoTaskMemRealloc
0x180012fed  mov     rdi, [rsp+28h+arg_20]
0x180012ff2  mov     [rdi], rax
0x180012ff5  test    rax, rax
0x180012ff8  jz      short loc_18001301E
0x180012ffa  mov     rcx, rax; void *
0x180012ffd  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180013002  cmp     rax, rbx
0x180013005  jbe     short loc_18001301A
0x180013007  mov     rcx, [rdi]
0x18001300a  sub     rax, rbx
0x18001300d  add     rcx, rbx; void *
0x180013010  mov     r8, rax; Size
0x180013013  xor     edx, edx; Val
0x180013015  call    memset_0
0x18001301a  xor     eax, eax
0x18001301c  jmp     short loc_180013023
0x18001301e  mov     eax, 8007000Eh
0x180013023  mov     rbx, [rsp+28h+arg_0]
0x180013028  add     rsp, 20h
0x18001302c  pop     rdi
0x18001302d  retn
```
