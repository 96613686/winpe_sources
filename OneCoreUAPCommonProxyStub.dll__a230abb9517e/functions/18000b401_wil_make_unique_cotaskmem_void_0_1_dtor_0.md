# _wil::make_unique_cotaskmem_void___[0]__::_1_::dtor$0

- ea: `0x18000b401`
- end: `0x18000b427`
- name: `_wil::make_unique_cotaskmem_void___[0]__::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180007418`
- `0x18000b401`

## pseudocode

```c
void __fastcall wil::make_unique_cotaskmem_void____0___::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wistd::unique_ptr<unsigned long [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::~unique_ptr<unsigned long [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>(*(void ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x18000b401  push    rbp
0x18000b403  sub     rsp, 20h
0x18000b407  mov     rbp, rdx
0x18000b40a  mov     eax, [rbp+20h]
0x18000b40d  and     eax, 1
0x18000b410  test    eax, eax
0x18000b412  jz      short loc_18000B421
0x18000b414  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000b418  mov     rcx, [rbp+40h]
0x18000b41c  call    ??1?$unique_ptr@$$BY0A@KU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAA@XZ
0x18000b421  add     rsp, 20h
0x18000b425  pop     rbp
0x18000b426  retn
```
