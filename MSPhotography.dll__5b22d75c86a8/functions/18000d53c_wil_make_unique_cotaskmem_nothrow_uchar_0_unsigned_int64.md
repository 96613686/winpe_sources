# wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x18000d53c`
- end: `0x18000d57d`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014858`
- `0x1800151a0`

## callees

- `0x18000d53c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d54f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d54f`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  _BYTE *v5; // rdx

  v4 = CoTaskMemAlloc(a2);
  *a1 = v4;
  if ( v4 )
  {
    v5 = &v4[a2];
    while ( v4 != v5 )
      *v4++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000d53c  mov     [rsp+arg_0], rbx
0x18000d541  push    rdi
0x18000d542  sub     rsp, 20h
0x18000d546  mov     rbx, rcx
0x18000d549  mov     rdi, rdx
0x18000d54c  mov     rcx, rdx; cb
0x18000d54f  call    cs:__imp_CoTaskMemAlloc
0x18000d555  mov     [rbx], rax
0x18000d558  test    rax, rax
0x18000d55b  jz      short loc_18000D56F
0x18000d55d  lea     rdx, [rax+rdi]
0x18000d561  jmp     short loc_18000D56A
0x18000d563  xor     ecx, ecx
0x18000d565  mov     [rax], cl
0x18000d567  inc     rax
0x18000d56a  cmp     rax, rdx
0x18000d56d  jnz     short loc_18000D563
0x18000d56f  mov     rax, rbx
0x18000d572  mov     rbx, [rsp+28h+arg_0]
0x18000d577  add     rsp, 20h
0x18000d57b  pop     rdi
0x18000d57c  retn
```
