# wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)

- ea: `0x18003edbc`
- end: `0x18003ee1a`
- name: `??1?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U12@_K@wil@@QEAA@XZ`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a9c0`

## callees

- `0x18003edbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ede3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edf5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ede3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003edf5`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(
        __int64 a1)
{
  LPVOID *v1; // rbx
  LPVOID *v3; // rsi

  v1 = *(LPVOID **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[*(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
      CoTaskMemFree(*v1++);
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18003edbc  mov     [rsp+arg_0], rbx
0x18003edc1  mov     [rsp+arg_8], rsi
0x18003edc6  push    rdi
0x18003edc7  sub     rsp, 20h
0x18003edcb  mov     rbx, [rcx]
0x18003edce  mov     rdi, rcx
0x18003edd1  test    rbx, rbx
0x18003edd4  jz      short loc_18003EE0A
0x18003edd6  mov     rax, [rcx+8]
0x18003edda  lea     rsi, [rbx+rax*8]
0x18003edde  jmp     short loc_18003EDED
0x18003ede0  mov     rcx, [rbx]; pv
0x18003ede3  call    cs:__imp_CoTaskMemFree
0x18003ede9  add     rbx, 8
0x18003eded  cmp     rbx, rsi
0x18003edf0  jnz     short loc_18003EDE0
0x18003edf2  mov     rcx, [rdi]; pv
0x18003edf5  call    cs:__imp_CoTaskMemFree
0x18003edfb  mov     qword ptr [rdi], 0
0x18003ee02  mov     qword ptr [rdi+8], 0
0x18003ee0a  mov     rbx, [rsp+28h+arg_0]
0x18003ee0f  mov     rsi, [rsp+28h+arg_8]
0x18003ee14  add     rsp, 20h
0x18003ee18  pop     rdi
0x18003ee19  retn
```
