# CoTaskMemAllocString_0

- ea: `0x180007890`
- end: `0x180007922`
- name: `CoTaskMemAllocString_0`
- size: `146`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002e4c4`

## callees

- `0x180007890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007902`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180007902`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800078e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800078e4`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocString_0(char *Source, char **a2)
{
  __int64 v5; // rax
  rsize_t v7; // rbp
  char *v8; // rax
  char *v9; // rsi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( Source )
  {
    v5 = -1;
    while ( Source[++v5] != 0 )
      ;
    v7 = v5 + 1;
    v8 = (char *)CoTaskMemAlloc(v5 + 1);
    v9 = v8;
    if ( !v8 )
      return 2147942414LL;
    strcpy_s(v8, v7, Source);
    *a2 = v9;
  }
  return 0;
}

```

## disassembly

```asm
0x180007890  mov     [rsp+arg_10], rbx
0x180007895  push    rdi
0x180007896  sub     rsp, 20h
0x18000789a  mov     rdi, rdx
0x18000789d  mov     rbx, rcx
0x1800078a0  test    rdx, rdx
0x1800078a3  jnz     short loc_1800078B5
0x1800078a5  mov     eax, 80004003h
0x1800078aa  mov     rbx, [rsp+28h+arg_10]
0x1800078af  add     rsp, 20h
0x1800078b3  pop     rdi
0x1800078b4  retn
0x1800078b5  mov     [rsp+28h+arg_0], rbp
0x1800078ba  mov     [rsp+28h+arg_8], rsi
0x1800078bf  mov     qword ptr [rdx], 0
0x1800078c6  test    rbx, rbx
0x1800078c9  jz      short loc_18000790B
0x1800078cb  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800078d2  cmp     byte ptr [rcx+rax+1], 0
0x1800078d7  lea     rax, [rax+1]
0x1800078db  jnz     short loc_1800078D2
0x1800078dd  lea     rbp, [rax+1]
0x1800078e1  mov     rcx, rbp; cb
0x1800078e4  call    cs:__imp_CoTaskMemAlloc
0x1800078ea  mov     rsi, rax
0x1800078ed  test    rax, rax
0x1800078f0  jnz     short loc_1800078F9
0x1800078f2  mov     eax, 8007000Eh
0x1800078f7  jmp     short loc_18000790D
0x1800078f9  mov     r8, rbx; Source
0x1800078fc  mov     rdx, rbp; SizeInBytes
0x1800078ff  mov     rcx, rsi; Destination
0x180007902  call    cs:__imp_strcpy_s
0x180007908  mov     [rdi], rsi
0x18000790b  xor     eax, eax
0x18000790d  mov     rbp, [rsp+28h+arg_0]
0x180007912  mov     rsi, [rsp+28h+arg_8]
0x180007917  mov     rbx, [rsp+28h+arg_10]
0x18000791c  add     rsp, 20h
0x180007920  pop     rdi
0x180007921  retn
```
