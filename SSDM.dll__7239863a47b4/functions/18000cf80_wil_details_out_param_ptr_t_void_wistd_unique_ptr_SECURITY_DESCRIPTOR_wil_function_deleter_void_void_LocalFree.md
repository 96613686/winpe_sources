# wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)

- ea: `0x18000cf80`
- end: `0x18000cfaa`
- name: `??1?$out_param_ptr_t@PEAPEAXV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000fb4e`

## callees

- `0x18000cf80`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf9f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000cf9f`

## pseudocode

```c
HLOCAL __fastcall wil::details::out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_ptr_t<void * *,wistd::unique_ptr<_SECURITY_DESCRIPTOR,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(
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
0x18000cf80  sub     rsp, 28h
0x18000cf84  cmp     byte ptr [rcx+10h], 0
0x18000cf88  jz      short loc_18000CFA5
0x18000cf8a  mov     rdx, [rcx]
0x18000cf8d  mov     rax, [rcx+8]
0x18000cf91  mov     r8, [rdx]
0x18000cf94  mov     [rdx], rax
0x18000cf97  test    r8, r8
0x18000cf9a  jz      short loc_18000CFA5
0x18000cf9c  mov     rcx, r8; hMem
0x18000cf9f  call    cs:__imp_LocalFree
0x18000cfa5  add     rsp, 28h
0x18000cfa9  retn
```
