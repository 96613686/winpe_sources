# wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::reset(void)

- ea: `0x1800700d0`
- end: `0x18007013f`
- name: `?reset@?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAXXZ`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006f814`
- `0x18006f88c`

## callees

- `0x1800700d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800700fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070113`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800700fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180070113`

## pseudocode

```c
void __fastcall wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&void Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::reset(
        __int64 a1)
{
  LPVOID *v1; // rbx
  LPVOID *v3; // rsi

  v1 = *(LPVOID **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = &v1[2 * *(_QWORD *)(a1 + 8)];
    while ( v1 != v3 )
    {
      CoTaskMemFree(v1[1]);
      v1 += 2;
    }
    CoTaskMemFree(*(LPVOID *)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x1800700d0  mov     [rsp+arg_0], rbx
0x1800700d5  mov     [rsp+arg_8], rsi
0x1800700da  push    rdi
0x1800700db  sub     rsp, 20h
0x1800700df  mov     rbx, [rcx]
0x1800700e2  mov     rdi, rcx
0x1800700e5  test    rbx, rbx
0x1800700e8  jz      short loc_18007012E
0x1800700ea  mov     rsi, [rcx+8]
0x1800700ee  shl     rsi, 4
0x1800700f2  add     rsi, rbx
0x1800700f5  jmp     short loc_18007010B
0x1800700f7  mov     rcx, [rbx+8]; pv
0x1800700fb  call    cs:__imp_CoTaskMemFree
0x180070102  nop     dword ptr [rax+rax+00h]
0x180070107  add     rbx, 10h
0x18007010b  cmp     rbx, rsi
0x18007010e  jnz     short loc_1800700F7
0x180070110  mov     rcx, [rdi]; pv
0x180070113  call    cs:__imp_CoTaskMemFree
0x18007011a  nop     dword ptr [rax+rax+00h]
0x18007011f  mov     qword ptr [rdi], 0
0x180070126  mov     qword ptr [rdi+8], 0
0x18007012e  mov     rbx, [rsp+28h+arg_0]
0x180070133  mov     rsi, [rsp+28h+arg_8]
0x180070138  add     rsp, 20h
0x18007013c  pop     rdi
0x18007013d  retn
```
