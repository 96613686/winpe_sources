# wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x180009d50`
- end: `0x180009d7a`
- name: `??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a150`

## callees

- `0x180009d50`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009d6f`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
        __int64 a1)
{
  HLOCAL result; // rax
  void *v2; // r8

  if ( *(_BYTE *)(a1 + 16) )
  {
    result = *(HLOCAL *)(a1 + 8);
    v2 = **(void ***)a1;
    **(_QWORD **)a1 = result;
    if ( v2 )
      return LocalFree(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180009d50  sub     rsp, 28h
0x180009d54  cmp     byte ptr [rcx+10h], 0
0x180009d58  jz      short loc_180009D75
0x180009d5a  mov     rdx, [rcx]
0x180009d5d  mov     rax, [rcx+8]
0x180009d61  mov     r8, [rdx]
0x180009d64  mov     [rdx], rax
0x180009d67  test    r8, r8
0x180009d6a  jz      short loc_180009D75
0x180009d6c  mov     rcx, r8; hMem
0x180009d6f  call    cs:__imp_LocalFree
0x180009d75  add     rsp, 28h
0x180009d79  retn
```
