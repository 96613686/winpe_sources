# wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x18001599c`
- end: `0x1800159bd`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019bb8`
- `0x180019fc8`

## callees

- `0x18001599c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800159b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800159b2`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<unsigned char [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
        HLOCAL *a1)
{
  HLOCAL result; // rax

  result = *a1;
  *a1 = 0;
  if ( result )
    return LocalFree(result);
  return result;
}

```

## disassembly

```asm
0x18001599c  sub     rsp, 28h
0x1800159a0  mov     rax, [rcx]
0x1800159a3  mov     qword ptr [rcx], 0
0x1800159aa  test    rax, rax
0x1800159ad  jz      short loc_1800159B8
0x1800159af  mov     rcx, rax; hMem
0x1800159b2  call    cs:__imp_LocalFree
0x1800159b8  add     rsp, 28h
0x1800159bc  retn
```
