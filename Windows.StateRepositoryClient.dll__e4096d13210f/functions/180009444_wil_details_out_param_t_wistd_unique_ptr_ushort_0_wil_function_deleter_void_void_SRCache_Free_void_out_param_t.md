# wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)

- ea: `0x180009444`
- end: `0x18000946e`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180009938`
- `0x180009fa4`
- `0x180012448`
- `0x180012638`
- `0x18001284c`
- `0x18001297c`
- `0x180016da0`
- `0x180016f78`

## callees

- `0x180009444`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009463`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180009463`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(
        __int64 **a1)
{
  __int64 result; // rax
  __int64 v2; // r8

  if ( *((_BYTE *)a1 + 16) )
  {
    result = (__int64)a1[1];
    v2 = **a1;
    **a1 = result;
    if ( v2 )
      return SRCache_Free(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180009444  sub     rsp, 28h
0x180009448  cmp     byte ptr [rcx+10h], 0
0x18000944c  jz      short loc_180009469
0x18000944e  mov     rdx, [rcx]
0x180009451  mov     rax, [rcx+8]
0x180009455  mov     r8, [rdx]
0x180009458  mov     [rdx], rax
0x18000945b  test    r8, r8
0x18000945e  jz      short loc_180009469
0x180009460  mov     rcx, r8
0x180009463  call    cs:__imp_SRCache_Free
0x180009469  add     rsp, 28h
0x18000946d  retn
```
