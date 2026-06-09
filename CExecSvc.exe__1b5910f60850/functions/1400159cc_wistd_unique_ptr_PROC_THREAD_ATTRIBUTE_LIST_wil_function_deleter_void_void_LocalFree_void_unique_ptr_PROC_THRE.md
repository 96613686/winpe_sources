# wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x1400159cc`
- end: `0x1400159ed`
- name: `??1?$unique_ptr@U_PROC_THREAD_ATTRIBUTE_LIST@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140022cb9`
- `0x140022f14`
- `0x140023077`

## callees

- `0x1400159cc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400159e2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400159e2`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<_PROC_THREAD_ATTRIBUTE_LIST,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
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
0x1400159cc  sub     rsp, 28h
0x1400159d0  mov     rax, [rcx]
0x1400159d3  mov     qword ptr [rcx], 0
0x1400159da  test    rax, rax
0x1400159dd  jz      short loc_1400159E8
0x1400159df  mov     rcx, rax; hMem
0x1400159e2  call    cs:__imp_LocalFree
0x1400159e8  add     rsp, 28h
0x1400159ec  retn
```
