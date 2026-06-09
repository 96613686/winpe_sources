# std::vector<web::json::value,std::allocator<web::json::value>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180004f00`
- end: `0x180004fb4`
- name: `??1_Reallocation_guard@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180027790`

## callees

- `0x180002cc0`
- `0x180004f00`
- `0x18002a010`

## pseudocode

```c
void __fastcall std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rsi
  void *v4; // rcx
  unsigned __int64 v5; // rdx
  _BYTE *v6; // rax

  if ( a1[1] )
  {
    v2 = (_QWORD *)a1[3];
    for ( i = (_QWORD *)a1[4]; v2 != i; ++v2 )
    {
      if ( *v2 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 192LL))(*v2, 1);
    }
    v4 = (void *)a1[1];
    v5 = 8LL * a1[2];
    if ( v5 < 0x1000 )
    {
      operator delete(v4, v5);
    }
    else
    {
      v6 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)((_BYTE *)v4 - v6 - 8) > 0x1F )
        __fastfail(5u);
      operator delete(v6, v5 + 39);
    }
  }
}

```

## disassembly

```asm
0x180004f00  push    rdi
0x180004f02  sub     rsp, 20h
0x180004f06  cmp     qword ptr [rcx+8], 0
0x180004f0b  mov     rdi, rcx
0x180004f0e  jz      loc_180004FAE
0x180004f14  mov     [rsp+28h+arg_0], rbx
0x180004f19  mov     rbx, [rcx+18h]
0x180004f1d  mov     [rsp+28h+arg_8], rsi
0x180004f22  mov     rsi, [rcx+20h]
0x180004f26  cmp     rbx, rsi
0x180004f29  jz      short loc_180004F55
0x180004f2b  nop     dword ptr [rax+rax+00h]
0x180004f30  mov     rcx, [rbx]
0x180004f33  test    rcx, rcx
0x180004f36  jz      short loc_180004F4C
0x180004f38  mov     rax, [rcx]
0x180004f3b  mov     edx, 1
0x180004f40  mov     rax, [rax+0C0h]
0x180004f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4c  add     rbx, 8
0x180004f50  cmp     rbx, rsi
0x180004f53  jnz     short loc_180004F30
0x180004f55  mov     rax, [rdi+10h]
0x180004f59  mov     rcx, [rdi+8]; void *
0x180004f5d  mov     rsi, [rsp+28h+arg_8]
0x180004f62  mov     rbx, [rsp+28h+arg_0]
0x180004f67  lea     rdx, ds:0[rax*8]; unsigned __int64
0x180004f6f  cmp     rdx, 1000h
0x180004f76  jb      short loc_180004FA1
0x180004f78  mov     rax, [rcx-8]
0x180004f7c  sub     rcx, rax
0x180004f7f  sub     rcx, 8
0x180004f83  cmp     rcx, 1Fh
0x180004f87  ja      short loc_180004F9A
0x180004f89  add     rdx, 27h ; '''; unsigned __int64
0x180004f8d  mov     rcx, rax; void *
0x180004f90  add     rsp, 20h
0x180004f94  pop     rdi
0x180004f95  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004f9a  mov     ecx, 5
0x180004f9f  int     29h; Win8: RtlFailFast(ecx)
0x180004fa1  mov     rax, rcx
0x180004fa4  add     rsp, 20h
0x180004fa8  pop     rdi
0x180004fa9  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004fae  add     rsp, 20h
0x180004fb2  pop     rdi
0x180004fb3  retn
```
