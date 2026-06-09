# wil::unique_any_array_ptr<_MVUIITem,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_struct_array_deleter<void (*)(_MVUIITem *),&Windows::Management::Provisioning::FreeMVUIItem(_MVUIITem *)>,unsigned __int64>::reset(void)

- ea: `0x18006ec5c`
- end: `0x18006ecbe`
- name: `?reset@?$unique_any_array_ptr@U_MVUIITem@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_struct_array_deleter@P6AXPEAU_MVUIITem@@@Z$1?FreeMVUIItem@Provisioning@Management@Windows@@YAX0@Z@details@3@_K@wil@@QEAAXXZ`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006e3bc`
- `0x18006e42c`

## callees

- `0x18006ec5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ec99`

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
0x18006ec5c  mov     [rsp+arg_0], rbx
0x18006ec61  mov     [rsp+arg_8], rsi
0x18006ec66  push    rdi
0x18006ec67  sub     rsp, 20h
0x18006ec6b  mov     rbx, [rcx]
0x18006ec6e  mov     rdi, rcx
0x18006ec71  test    rbx, rbx
0x18006ec74  jz      short loc_18006ECAE
0x18006ec76  mov     rsi, [rcx+8]
0x18006ec7a  shl     rsi, 4
0x18006ec7e  add     rsi, rbx
0x18006ec81  jmp     short loc_18006EC91
0x18006ec83  mov     rcx, [rbx+8]; pv
0x18006ec87  call    cs:__imp_CoTaskMemFree
0x18006ec8d  add     rbx, 10h
0x18006ec91  cmp     rbx, rsi
0x18006ec94  jnz     short loc_18006EC83
0x18006ec96  mov     rcx, [rdi]; pv
0x18006ec99  call    cs:__imp_CoTaskMemFree
0x18006ec9f  mov     qword ptr [rdi], 0
0x18006eca6  mov     qword ptr [rdi+8], 0
0x18006ecae  mov     rbx, [rsp+28h+arg_0]
0x18006ecb3  mov     rsi, [rsp+28h+arg_8]
0x18006ecb8  add     rsp, 20h
0x18006ecbc  pop     rdi
0x18006ecbd  retn
```
