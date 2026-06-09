# boost::detail::function::functor_manager__lambda_00a7fa26a962e5711fec5fc8fc065262___::manage

- ea: `0x140084490`
- end: `0x1400844f3`
- name: `boost::detail::function::functor_manager__lambda_00a7fa26a962e5711fec5fc8fc065262___::manage`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140084490`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400844c0`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1400844c0`

## pseudocode

```c
void __fastcall boost::detail::function::functor_manager__lambda_00a7fa26a962e5711fec5fc8fc065262___::manage(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  if ( a3 == 4 )
    goto LABEL_5;
  if ( a3 <= 2 )
    return;
  if ( a3 != 3 )
  {
LABEL_5:
    *(_WORD *)(a2 + 8) = 0;
    *(_QWORD *)a2 = &_lambda_00a7fa26a962e5711fec5fc8fc065262_ `RTTI Type Descriptor';
  }
  else
  {
    *(_QWORD *)a2 = a1 & -(__int64)((unsigned int)__std_type_info_compare(*(_QWORD *)a2 + 8LL, &qword_1400CF368) == 0);
  }
}

```

## disassembly

```asm
0x140084490  mov     [rsp+arg_0], rbx
0x140084495  push    rdi
0x140084496  sub     rsp, 20h
0x14008449a  mov     rbx, rdx
0x14008449d  mov     rdi, rcx
0x1400844a0  cmp     r8d, 4
0x1400844a4  jz      short loc_1400844D8
0x1400844a6  cmp     r8d, 2
0x1400844aa  jbe     short loc_1400844E8
0x1400844ac  cmp     r8d, 3
0x1400844b0  jnz     short loc_1400844D8
0x1400844b2  mov     rcx, [rdx]
0x1400844b5  lea     rdx, qword_1400CF368
0x1400844bc  add     rcx, 8
0x1400844c0  call    cs:__imp___std_type_info_compare
0x1400844c6  test    eax, eax
0x1400844c8  setz    al
0x1400844cb  neg     al
0x1400844cd  sbb     rcx, rcx
0x1400844d0  and     rcx, rdi
0x1400844d3  mov     [rbx], rcx
0x1400844d6  jmp     short loc_1400844E8
0x1400844d8  lea     rax, ??_R0?AV_lambda_00a7fa26a962e5711fec5fc8fc065262_@@@8; _lambda_00a7fa26a962e5711fec5fc8fc065262_ `RTTI Type Descriptor'
0x1400844df  mov     word ptr [rdx+8], 0
0x1400844e5  mov     [rdx], rax
0x1400844e8  mov     rbx, [rsp+28h+arg_0]
0x1400844ed  add     rsp, 20h
0x1400844f1  pop     rdi
0x1400844f2  retn
```
