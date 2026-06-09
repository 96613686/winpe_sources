# comp_free_compress_memory

- ea: `0x14000a768`
- end: `0x14000a8c4`
- name: `comp_free_compress_memory`
- size: `348`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a578`
- `0x14000d354`

## callees

- `0x14000a768`
- `0x140011640`

## pseudocode

```c
__int64 __fastcall comp_free_compress_memory(__int64 a1)
{
  __int64 (**v2)(void); // rdi
  __int64 result; // rax
  __int64 (**v4)(void); // rsi
  __int64 (**v5)(void); // rdi

  v2 = (__int64 (**)(void))(a1 + 17320);
  if ( *(_QWORD *)(a1 + 16) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( *(_QWORD *)(a1 + 17280) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17280) = 0;
  }
  if ( *(_QWORD *)(a1 + 17288) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17288) = 0;
  }
  v4 = (__int64 (**)(void))(a1 + 17320);
  if ( *(_QWORD *)(a1 + 17272) )
  {
    result = (*v2)();
    *(_QWORD *)(a1 + 17272) = 0;
    *(_QWORD *)a1 = 0;
  }
  else
  {
    v4 = (__int64 (**)(void))(a1 + 17320);
  }
  if ( *(_QWORD *)(a1 + 72) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 72) = 0;
  }
  if ( *(_QWORD *)(a1 + 64) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 64) = 0;
    v5 = (__int64 (**)(void))(a1 + 17320);
  }
  else
  {
    v5 = v4;
  }
  if ( *(_QWORD *)(a1 + 80) )
  {
    result = (*v4)();
    *(_QWORD *)(a1 + 80) = 0;
  }
  else
  {
    v5 = v4;
  }
  if ( *(_QWORD *)(a1 + 9600) )
  {
    result = (*v5)();
    *(_QWORD *)(a1 + 9600) = 0;
  }
  if ( *(_QWORD *)(a1 + 2176) )
  {
    result = (*v5)();
    *(_QWORD *)(a1 + 2176) = 0;
  }
  *(_DWORD *)(a1 + 2216) = 0;
  return result;
}

```

## disassembly

```asm
0x14000a768  mov     [rsp+arg_0], rbx
0x14000a76d  mov     [rsp+arg_8], rsi
0x14000a772  push    rdi
0x14000a773  sub     rsp, 20h
0x14000a777  mov     rbx, rcx
0x14000a77a  mov     rcx, [rcx+10h]
0x14000a77e  lea     rdi, [rbx+43A8h]
0x14000a785  test    rcx, rcx
0x14000a788  jz      short loc_14000A79A
0x14000a78a  mov     rax, [rdi]
0x14000a78d  call    _guard_dispatch_icall
0x14000a792  mov     qword ptr [rbx+10h], 0
0x14000a79a  mov     rcx, [rbx+4380h]
0x14000a7a1  test    rcx, rcx
0x14000a7a4  jz      short loc_14000A7B9
0x14000a7a6  mov     rax, [rdi]
0x14000a7a9  call    _guard_dispatch_icall
0x14000a7ae  mov     qword ptr [rbx+4380h], 0
0x14000a7b9  mov     rcx, [rbx+4388h]
0x14000a7c0  test    rcx, rcx
0x14000a7c3  jz      short loc_14000A7E1
0x14000a7c5  mov     rax, [rdi]
0x14000a7c8  call    _guard_dispatch_icall
0x14000a7cd  mov     qword ptr [rbx+4388h], 0
0x14000a7d8  lea     rsi, [rbx+43A8h]
0x14000a7df  jmp     short loc_14000A7E4
0x14000a7e1  mov     rsi, rdi
0x14000a7e4  mov     rcx, [rbx+4378h]
0x14000a7eb  test    rcx, rcx
0x14000a7ee  jz      short loc_14000A80C
0x14000a7f0  mov     rax, [rdi]
0x14000a7f3  call    _guard_dispatch_icall
0x14000a7f8  mov     qword ptr [rbx+4378h], 0
0x14000a803  mov     qword ptr [rbx], 0
0x14000a80a  jmp     short loc_14000A80F
0x14000a80c  mov     rsi, rdi
0x14000a80f  mov     rcx, [rbx+48h]
0x14000a813  test    rcx, rcx
0x14000a816  jz      short loc_14000A828
0x14000a818  mov     rax, [rsi]
0x14000a81b  call    _guard_dispatch_icall
0x14000a820  mov     qword ptr [rbx+48h], 0
0x14000a828  mov     rcx, [rbx+40h]
0x14000a82c  test    rcx, rcx
0x14000a82f  jz      short loc_14000A84A
0x14000a831  mov     rax, [rsi]
0x14000a834  call    _guard_dispatch_icall
0x14000a839  mov     qword ptr [rbx+40h], 0
0x14000a841  lea     rdi, [rbx+43A8h]
0x14000a848  jmp     short loc_14000A84D
0x14000a84a  mov     rdi, rsi
0x14000a84d  mov     rcx, [rbx+50h]
0x14000a851  test    rcx, rcx
0x14000a854  jz      short loc_14000A868
0x14000a856  mov     rax, [rsi]
0x14000a859  call    _guard_dispatch_icall
0x14000a85e  mov     qword ptr [rbx+50h], 0
0x14000a866  jmp     short loc_14000A86B
0x14000a868  mov     rdi, rsi
0x14000a86b  mov     rcx, [rbx+2580h]
0x14000a872  test    rcx, rcx
0x14000a875  jz      short loc_14000A88A
0x14000a877  mov     rax, [rdi]
0x14000a87a  call    _guard_dispatch_icall
0x14000a87f  mov     qword ptr [rbx+2580h], 0
0x14000a88a  mov     rcx, [rbx+880h]
0x14000a891  test    rcx, rcx
0x14000a894  jz      short loc_14000A8A9
0x14000a896  mov     rax, [rdi]
0x14000a899  call    _guard_dispatch_icall
0x14000a89e  mov     qword ptr [rbx+880h], 0
0x14000a8a9  mov     rsi, [rsp+28h+arg_8]
0x14000a8ae  mov     dword ptr [rbx+8A8h], 0
0x14000a8b8  mov     rbx, [rsp+28h+arg_0]
0x14000a8bd  add     rsp, 20h
0x14000a8c1  pop     rdi
0x14000a8c2  retn
```
