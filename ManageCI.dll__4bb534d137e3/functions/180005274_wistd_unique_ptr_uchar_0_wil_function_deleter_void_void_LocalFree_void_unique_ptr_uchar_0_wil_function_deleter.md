# wistd::unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<uchar [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x180005274`
- end: `0x180005295`
- name: `??1?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800298e6`
- `0x180029dad`
- `0x18002a334`
- `0x18002a980`
- `0x18002b577`
- `0x18002b589`
- `0x18002b5d1`

## callees

- `0x180005274`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000528a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000528a`

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
0x180005274  sub     rsp, 28h
0x180005278  mov     rax, [rcx]
0x18000527b  mov     qword ptr [rcx], 0
0x180005282  test    rax, rax
0x180005285  jz      short loc_180005290
0x180005287  mov     rcx, rax; hMem
0x18000528a  call    cs:__imp_LocalFree
0x180005290  add     rsp, 28h
0x180005294  retn
```
