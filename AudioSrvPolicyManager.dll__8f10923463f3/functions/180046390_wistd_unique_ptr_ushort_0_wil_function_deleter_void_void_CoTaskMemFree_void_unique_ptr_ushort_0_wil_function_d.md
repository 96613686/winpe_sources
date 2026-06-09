# wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::~unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>(void)

- ea: `0x180046390`
- end: `0x1800463b1`
- name: `??1?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004a1e9`

## callees

- `0x180046390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800463a6`

## pseudocode

```c
void __fastcall wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(
        void **a1)
{
  void *v1; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x180046390  sub     rsp, 28h
0x180046394  mov     rax, [rcx]
0x180046397  mov     qword ptr [rcx], 0
0x18004639e  test    rax, rax
0x1800463a1  jz      short loc_1800463AC
0x1800463a3  mov     rcx, rax; pv
0x1800463a6  call    cs:__imp_CoTaskMemFree
0x1800463ac  add     rsp, 28h
0x1800463b0  retn
```
