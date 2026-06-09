# CopyString_0

- ea: `0x1800113c0`
- end: `0x180011448`
- name: `CopyString_0`
- size: `136`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180011328`

## callees

- `0x1800113c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001141b`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x18001141b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180011404`

## pseudocode

```c
__int64 __fastcall CopyString_0(char *Source, __int64 a2, char **a3)
{
  __int64 v5; // rax
  rsize_t v7; // rbp
  char *v8; // rax
  char *v9; // rsi

  if ( !a3 )
    return 0;
  *a3 = 0;
  if ( !Source )
    return 0;
  v5 = -1;
  while ( Source[++v5] != 0 )
    ;
  v7 = v5 + 1;
  v8 = (char *)CoTaskMemAlloc(v5 + 1);
  v9 = v8;
  if ( v8 )
  {
    strcpy_s(v8, v7, Source);
    *a3 = v9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800113c0  mov     [rsp+arg_10], rbx
0x1800113c5  push    rdi
0x1800113c6  sub     rsp, 20h
0x1800113ca  mov     rdi, r8
0x1800113cd  mov     rbx, rcx
0x1800113d0  test    r8, r8
0x1800113d3  jz      short loc_18001143B
0x1800113d5  mov     qword ptr [r8], 0
0x1800113dc  test    rcx, rcx
0x1800113df  jz      short loc_18001143B
0x1800113e1  mov     [rsp+28h+arg_0], rbp
0x1800113e6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800113ed  mov     [rsp+28h+arg_8], rsi
0x1800113f2  cmp     byte ptr [rcx+rax+1], 0
0x1800113f7  lea     rax, [rax+1]
0x1800113fb  jnz     short loc_1800113F2
0x1800113fd  lea     rbp, [rax+1]
0x180011401  mov     rcx, rbp; cb
0x180011404  call    cs:__imp_CoTaskMemAlloc
0x18001140a  mov     rsi, rax
0x18001140d  test    rax, rax
0x180011410  jz      short loc_180011424
0x180011412  mov     r8, rbx; Source
0x180011415  mov     rdx, rbp; SizeInBytes
0x180011418  mov     rcx, rax; Destination
0x18001141b  call    cs:__imp_strcpy_s
0x180011421  mov     [rdi], rsi
0x180011424  mov     rbp, [rsp+28h+arg_0]
0x180011429  xor     eax, eax
0x18001142b  mov     rsi, [rsp+28h+arg_8]
0x180011430  mov     rbx, [rsp+28h+arg_10]
0x180011435  add     rsp, 20h
0x180011439  pop     rdi
0x18001143a  retn
0x18001143b  mov     rbx, [rsp+28h+arg_10]
0x180011440  xor     eax, eax
0x180011442  add     rsp, 20h
0x180011446  pop     rdi
0x180011447  retn
```
