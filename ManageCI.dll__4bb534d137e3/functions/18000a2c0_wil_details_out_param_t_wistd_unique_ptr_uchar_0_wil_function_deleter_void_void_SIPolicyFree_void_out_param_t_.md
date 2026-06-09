# wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&SIPolicyFree(void *)>>>(void)

- ea: `0x18000a2c0`
- end: `0x18000a2ea`
- name: `??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?SIPolicyFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ad4c`
- `0x18001c714`
- `0x18002a346`
- `0x18002b5e3`

## callees

- `0x18000a2c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a2df`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void SIPolicyFree(void *)>>>(
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
0x18000a2c0  sub     rsp, 28h
0x18000a2c4  cmp     byte ptr [rcx+10h], 0
0x18000a2c8  jz      short loc_18000A2E5
0x18000a2ca  mov     rdx, [rcx]
0x18000a2cd  mov     rax, [rcx+8]
0x18000a2d1  mov     r8, [rdx]
0x18000a2d4  mov     [rdx], rax
0x18000a2d7  test    r8, r8
0x18000a2da  jz      short loc_18000A2E5
0x18000a2dc  mov     rcx, r8; hMem
0x18000a2df  call    cs:__imp_LocalFree
0x18000a2e5  add     rsp, 28h
0x18000a2e9  retn
```
