# CopyString

- ea: `0x180010350`
- end: `0x1800103d1`
- name: `CopyString`
- size: `129`
- prototype: `__int64 __fastcall(char *Source)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013440`
- `0x180029380`

## callees

- `0x180010350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800103c2`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x1800103c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010394`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180010394`

## pseudocode

```c
__int64 __fastcall CopyString(char *Source, __int64 a2, char **a3)
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
0x180010350  mov     [rsp+arg_10], rbx
0x180010355  push    rdi
0x180010356  sub     rsp, 20h
0x18001035a  mov     rdi, r8
0x18001035d  mov     rbx, rcx
0x180010360  test    r8, r8
0x180010363  jz      short loc_1800103CD
0x180010365  mov     qword ptr [r8], 0
0x18001036c  test    rcx, rcx
0x18001036f  jz      short loc_1800103CD
0x180010371  mov     [rsp+28h+arg_0], rbp
0x180010376  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18001037d  mov     [rsp+28h+arg_8], rsi
0x180010382  cmp     byte ptr [rcx+rax+1], 0
0x180010387  lea     rax, [rax+1]
0x18001038b  jnz     short loc_180010382
0x18001038d  lea     rbp, [rax+1]
0x180010391  mov     rcx, rbp; cb
0x180010394  call    cs:__imp_CoTaskMemAlloc
0x18001039a  mov     rsi, rax
0x18001039d  test    rax, rax
0x1800103a0  jnz     short loc_1800103B9
0x1800103a2  mov     rbp, [rsp+28h+arg_0]
0x1800103a7  xor     eax, eax
0x1800103a9  mov     rsi, [rsp+28h+arg_8]
0x1800103ae  mov     rbx, [rsp+28h+arg_10]
0x1800103b3  add     rsp, 20h
0x1800103b7  pop     rdi
0x1800103b8  retn
0x1800103b9  mov     r8, rbx; Source
0x1800103bc  mov     rdx, rbp; SizeInBytes
0x1800103bf  mov     rcx, rsi; Destination
0x1800103c2  call    cs:__imp_strcpy_s
0x1800103c8  mov     [rdi], rsi
0x1800103cb  jmp     short loc_1800103A2
0x1800103cd  xor     eax, eax
0x1800103cf  jmp     short loc_1800103AE
```
