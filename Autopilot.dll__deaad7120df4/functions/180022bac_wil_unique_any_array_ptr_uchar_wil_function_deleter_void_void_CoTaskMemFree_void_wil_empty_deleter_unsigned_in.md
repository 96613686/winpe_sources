# wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>::~unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>(void)

- ea: `0x180022bac`
- end: `0x180022bdf`
- name: `??1?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a4e7`
- `0x18002a51d`

## callees

- `0x180022bac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022bbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022bbd`

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
0x180022bac  push    rbx
0x180022bae  sub     rsp, 20h
0x180022bb2  mov     rbx, rcx
0x180022bb5  mov     rcx, [rcx]; pv
0x180022bb8  test    rcx, rcx
0x180022bbb  jz      short loc_180022BD8
0x180022bbd  call    cs:__imp_CoTaskMemFree
0x180022bc4  nop     dword ptr [rax+rax+00h]
0x180022bc9  mov     qword ptr [rbx], 0
0x180022bd0  mov     qword ptr [rbx+8], 0
0x180022bd8  add     rsp, 20h
0x180022bdc  pop     rbx
0x180022bdd  retn
```
