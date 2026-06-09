# std::vector<web::json::value,std::allocator<web::json::value>>::_Tidy(void)

- ea: `0x18002c514`
- end: `0x18002c5ce`
- name: `?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ`
- size: `186`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x18002acb4`
- `0x18002b380`
- `0x18002c5d4`
- `0x180033980`
- `0x180033c14`

## callees

- `0x18002c514`
- `0x180042bc4`
- `0x180047a30`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c5c7`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18002c5c7`

## pseudocode

```c
void __fastcall std::vector<web::json::value>::_Tidy(__int64 a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rsi
  _QWORD *v4; // rcx

  v1 = *(_QWORD **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(_QWORD **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v1 + 192LL))(*v1, 1);
      ++v1;
    }
    v4 = *(_QWORD **)a1;
    if ( ((*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL) >= 0x1000 )
    {
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18002c514  mov     [rsp+arg_8], rbx
0x18002c519  mov     [rsp+arg_10], rsi
0x18002c51e  push    rdi
0x18002c51f  sub     rsp, 30h
0x18002c523  mov     rbx, [rcx]
0x18002c526  mov     rdi, rcx
0x18002c529  test    rbx, rbx
0x18002c52c  jz      short loc_18002C5A4
0x18002c52e  mov     rsi, [rcx+8]
0x18002c532  jmp     short loc_18002C554
0x18002c534  mov     rcx, [rbx]
0x18002c537  test    rcx, rcx
0x18002c53a  jz      short loc_18002C550
0x18002c53c  mov     rax, [rcx]
0x18002c53f  mov     edx, 1
0x18002c544  mov     rax, [rax+0C0h]
0x18002c54b  call    _guard_dispatch_icall
0x18002c550  add     rbx, 8
0x18002c554  cmp     rbx, rsi
0x18002c557  jnz     short loc_18002C534
0x18002c559  mov     rcx, [rdi]
0x18002c55c  mov     rdx, [rdi+10h]
0x18002c560  sub     rdx, rcx
0x18002c563  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18002c567  cmp     rdx, 1000h
0x18002c56e  jb      short loc_18002C588
0x18002c570  mov     rax, [rcx-8]
0x18002c574  add     rdx, 27h ; '''; unsigned __int64
0x18002c578  sub     rcx, rax
0x18002c57b  sub     rcx, 8
0x18002c57f  cmp     rcx, 1Fh
0x18002c583  ja      short loc_18002C5B4
0x18002c585  mov     rcx, rax; void *
0x18002c588  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002c58d  mov     qword ptr [rdi], 0
0x18002c594  mov     qword ptr [rdi+8], 0
0x18002c59c  mov     qword ptr [rdi+10h], 0
0x18002c5a4  mov     rbx, [rsp+38h+arg_8]
0x18002c5a9  mov     rsi, [rsp+38h+arg_10]
0x18002c5ae  add     rsp, 30h
0x18002c5b2  pop     rdi
0x18002c5b3  retn
0x18002c5b4  xor     r9d, r9d; LineNo
0x18002c5b7  mov     [rsp+38h+Reserved], 0; Reserved
0x18002c5c0  xor     r8d, r8d; FileName
0x18002c5c3  xor     edx, edx; FunctionName
0x18002c5c5  xor     ecx, ecx; Expression
0x18002c5c7  call    cs:__imp__invoke_watson
```
