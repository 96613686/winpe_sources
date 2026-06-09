# wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x1400084fc`
- end: `0x14000851d`
- name: `??1?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011dae`

## callees

- `0x1400084fc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140008512`
- `KERNEL32!LocalFree` at `0x140008512`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<void,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
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
0x1400084fc  sub     rsp, 28h
0x140008500  mov     rax, [rcx]
0x140008503  mov     qword ptr [rcx], 0
0x14000850a  test    rax, rax
0x14000850d  jz      short loc_140008518
0x14000850f  mov     rcx, rax; hMem
0x140008512  call    cs:__imp_LocalFree
0x140008518  add     rsp, 28h
0x14000851c  retn
```
