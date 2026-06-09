# wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::~unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>(void)

- ea: `0x18000cfb0`
- end: `0x18000cfd1`
- name: `??1?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: `HLOCAL __fastcall(HLOCAL *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fa7c`
- `0x18000fab6`
- `0x18000fb22`

## callees

- `0x18000cfb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cfc6`

## pseudocode

```c
HLOCAL __fastcall wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::~unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>(
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
0x18000cfb0  sub     rsp, 28h
0x18000cfb4  mov     rax, [rcx]
0x18000cfb7  mov     qword ptr [rcx], 0
0x18000cfbe  test    rax, rax
0x18000cfc1  jz      short loc_18000CFCC
0x18000cfc3  mov     rcx, rax; hMem
0x18000cfc6  call    cs:__imp_LocalFree
0x18000cfcc  add     rsp, 28h
0x18000cfd0  retn
```
