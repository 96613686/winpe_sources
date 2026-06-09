# CoTaskMemAllocString_1

- ea: `0x180008ef0`
- end: `0x180008f5d`
- name: `CoTaskMemAllocString_1`
- size: `109`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180038a50`

## callees

- `0x180008ef0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008f49`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008f49`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008f2b`

## pseudocode

```c
__int64 __fastcall CoTaskMemAllocString_1(char *Source, char **a2)
{
  __int64 v5; // rax
  rsize_t v6; // rbp
  char *v7; // rax
  char *v8; // rsi

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( Source )
  {
    v5 = -1;
    do
      ++v5;
    while ( Source[v5] );
    v6 = v5 + 1;
    v7 = (char *)CoTaskMemAlloc(v5 + 1);
    v8 = v7;
    if ( !v7 )
      return 2147942414LL;
    strcpy_s(v7, v6, Source);
    *a2 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x180008ef0  push    rbx
0x180008ef2  push    rbp
0x180008ef3  push    rsi
0x180008ef4  push    rdi
0x180008ef5  sub     rsp, 28h
0x180008ef9  mov     rbx, rdx
0x180008efc  mov     rdi, rcx
0x180008eff  test    rdx, rdx
0x180008f02  jnz     short loc_180008F0B
0x180008f04  mov     eax, 80004003h
0x180008f09  jmp     short loc_180008F54
0x180008f0b  mov     qword ptr [rdx], 0
0x180008f12  test    rdi, rdi
0x180008f15  jz      short loc_180008F52
0x180008f17  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f1b  inc     rax
0x180008f1e  cmp     byte ptr [rcx+rax], 0
0x180008f22  jnz     short loc_180008F1B
0x180008f24  lea     rbp, [rax+1]
0x180008f28  mov     rcx, rbp; cb
0x180008f2b  call    cs:__imp_CoTaskMemAlloc
0x180008f31  mov     rsi, rax
0x180008f34  test    rax, rax
0x180008f37  jnz     short loc_180008F40
0x180008f39  mov     eax, 8007000Eh
0x180008f3e  jmp     short loc_180008F54
0x180008f40  mov     r8, rdi; Source
0x180008f43  mov     rdx, rbp; SizeInBytes
0x180008f46  mov     rcx, rsi; Destination
0x180008f49  call    cs:__imp_strcpy_s
0x180008f4f  mov     [rbx], rsi
0x180008f52  xor     eax, eax
0x180008f54  add     rsp, 28h
0x180008f58  pop     rdi
0x180008f59  pop     rsi
0x180008f5a  pop     rbp
0x180008f5b  pop     rbx
0x180008f5c  retn
```
