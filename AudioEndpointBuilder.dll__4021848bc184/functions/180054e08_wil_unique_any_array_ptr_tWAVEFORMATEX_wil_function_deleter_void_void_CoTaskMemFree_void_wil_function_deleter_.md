# wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::reset(void)

- ea: `0x180054e08`
- end: `0x180054e66`
- name: `?reset@?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAAXXZ`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048b20`
- `0x18005df1c`

## callees

- `0x180054e08`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054e41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054e2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054e41`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::reset(
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
0x180054e08  mov     [rsp+arg_0], rbx
0x180054e0d  mov     [rsp+arg_8], rsi
0x180054e12  push    rdi
0x180054e13  sub     rsp, 20h
0x180054e17  mov     rbx, [rcx]
0x180054e1a  mov     rdi, rcx
0x180054e1d  test    rbx, rbx
0x180054e20  jz      short loc_180054E56
0x180054e22  mov     rax, [rcx+8]
0x180054e26  lea     rsi, [rbx+rax*8]
0x180054e2a  jmp     short loc_180054E39
0x180054e2c  mov     rcx, [rbx]; pv
0x180054e2f  call    cs:__imp_CoTaskMemFree
0x180054e35  add     rbx, 8
0x180054e39  cmp     rbx, rsi
0x180054e3c  jnz     short loc_180054E2C
0x180054e3e  mov     rcx, [rdi]; pv
0x180054e41  call    cs:__imp_CoTaskMemFree
0x180054e47  mov     qword ptr [rdi], 0
0x180054e4e  mov     qword ptr [rdi+8], 0
0x180054e56  mov     rbx, [rsp+28h+arg_0]
0x180054e5b  mov     rsi, [rsp+28h+arg_8]
0x180054e60  add     rsp, 20h
0x180054e64  pop     rdi
0x180054e65  retn
```
