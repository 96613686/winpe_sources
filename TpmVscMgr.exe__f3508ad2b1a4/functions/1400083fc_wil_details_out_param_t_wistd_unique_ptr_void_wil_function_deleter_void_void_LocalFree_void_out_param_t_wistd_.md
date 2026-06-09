# wil::details::out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<void,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x1400083fc`
- end: `0x140008426`
- name: `??1?$out_param_t@V?$unique_ptr@XU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140011dc0`

## callees

- `0x1400083fc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000841b`
- `KERNEL32!LocalFree` at `0x14000841b`

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
0x1400083fc  sub     rsp, 28h
0x140008400  cmp     byte ptr [rcx+10h], 0
0x140008404  jz      short loc_140008421
0x140008406  mov     rdx, [rcx]
0x140008409  mov     rax, [rcx+8]
0x14000840d  mov     r8, [rdx]
0x140008410  mov     [rdx], rax
0x140008413  test    r8, r8
0x140008416  jz      short loc_140008421
0x140008418  mov     rcx, r8; hMem
0x14000841b  call    cs:__imp_LocalFree
0x140008421  add     rsp, 28h
0x140008425  retn
```
