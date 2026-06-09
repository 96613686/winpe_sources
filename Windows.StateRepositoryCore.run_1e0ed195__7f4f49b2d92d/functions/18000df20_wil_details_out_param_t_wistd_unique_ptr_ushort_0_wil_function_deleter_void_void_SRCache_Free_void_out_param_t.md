# wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)

- ea: `0x18000df20`
- end: `0x18000df49`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000df50`

## callees

- `0x1800022a0`
- `0x18000df20`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(
        __int64 a1)
{
  void *v1; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    v1 = **(void ***)a1;
    **(_QWORD **)a1 = *(_QWORD *)(a1 + 8);
    if ( v1 )
      operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000df20  sub     rsp, 28h
0x18000df24  cmp     byte ptr [rcx+10h], 0
0x18000df28  jz      short loc_18000DF44
0x18000df2a  mov     rdx, [rcx]; unsigned __int64
0x18000df2d  mov     rax, [rcx+8]
0x18000df31  mov     r8, [rdx]
0x18000df34  mov     [rdx], rax
0x18000df37  test    r8, r8
0x18000df3a  jz      short loc_18000DF44
0x18000df3c  mov     rcx, r8; void *
0x18000df3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000df44  add     rsp, 28h
0x18000df48  retn
```
