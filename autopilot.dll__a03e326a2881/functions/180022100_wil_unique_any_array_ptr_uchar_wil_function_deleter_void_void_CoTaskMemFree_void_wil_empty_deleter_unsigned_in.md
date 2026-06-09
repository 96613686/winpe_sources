# wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)

- ea: `0x180022100`
- end: `0x18002212c`
- name: `??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ`
- size: `44`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800291fd`
- `0x180029233`

## callees

- `0x180022100`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022111`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022111`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(
        __int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180022100  push    rbx
0x180022102  sub     rsp, 20h
0x180022106  mov     rbx, rcx
0x180022109  mov     rcx, [rcx]; pv
0x18002210c  test    rcx, rcx
0x18002210f  jz      short loc_180022126
0x180022111  call    cs:__imp_CoTaskMemFree
0x180022117  mov     qword ptr [rbx], 0
0x18002211e  mov     qword ptr [rbx+8], 0
0x180022126  add     rsp, 20h
0x18002212a  pop     rbx
0x18002212b  retn
```
