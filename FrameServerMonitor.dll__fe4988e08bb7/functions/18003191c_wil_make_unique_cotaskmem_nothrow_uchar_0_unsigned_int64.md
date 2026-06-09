# wil::make_unique_cotaskmem_nothrow<uchar [0]>(unsigned __int64)

- ea: `0x18003191c`
- end: `0x18003195d`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `65`
- prototype: `_QWORD *__fastcall(_QWORD *, SIZE_T)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a48c`
- `0x180047000`

## callees

- `0x18003191c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003192f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003192f`

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
0x18003191c  mov     [rsp+arg_0], rbx
0x180031921  push    rdi
0x180031922  sub     rsp, 20h
0x180031926  mov     rbx, rcx
0x180031929  mov     rdi, rdx
0x18003192c  mov     rcx, rdx; cb
0x18003192f  call    cs:__imp_CoTaskMemAlloc
0x180031935  mov     [rbx], rax
0x180031938  test    rax, rax
0x18003193b  jz      short loc_18003194F
0x18003193d  lea     rdx, [rax+rdi]
0x180031941  jmp     short loc_18003194A
0x180031943  xor     ecx, ecx
0x180031945  mov     [rax], cl
0x180031947  inc     rax
0x18003194a  cmp     rax, rdx
0x18003194d  jnz     short loc_180031943
0x18003194f  mov     rax, rbx
0x180031952  mov     rbx, [rsp+28h+arg_0]
0x180031957  add     rsp, 20h
0x18003195b  pop     rdi
0x18003195c  retn
```
