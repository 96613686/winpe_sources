# CDPComAccountFromCDPAccount

- ea: `0x180015174`
- end: `0x180015223`
- name: `CDPComAccountFromCDPAccount`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020540`

## callees

- `0x180015174`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180015212`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180015212`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800151d7`

## pseudocode

```c
__int64 __fastcall CDPComAccountFromCDPAccount(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  rsize_t v6; // rsi
  LPVOID v7; // rax
  const char *v9; // rax

  if ( !a2 || !a1 )
    return 2147942487LL;
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v5 = -1;
  do
    ++v5;
  while ( *(_BYTE *)(v4 + v5) );
  v6 = v5 + 1;
  v7 = CoTaskMemAlloc(v5 + 1);
  *(_QWORD *)a2 = v7;
  if ( !v7 )
    return 2147942414LL;
  v9 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  strcpy_s(*(char **)a2, v6, v9);
  return 0;
}

```

## disassembly

```asm
0x180015174  mov     [rsp+arg_0], rbx
0x180015179  mov     [rsp+arg_8], rsi
0x18001517e  push    rdi
0x18001517f  sub     rsp, 20h
0x180015183  mov     rdi, rdx
0x180015186  mov     rbx, rcx
0x180015189  test    rdx, rdx
0x18001518c  jz      loc_18001521C
0x180015192  test    rcx, rcx
0x180015195  jz      loc_18001521C
0x18001519b  xorps   xmm0, xmm0
0x18001519e  movdqu  xmmword ptr [rdx], xmm0
0x1800151a2  mov     rax, [rcx]
0x1800151a5  mov     rax, [rax+18h]
0x1800151a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ae  movzx   eax, ax
0x1800151b1  mov     rcx, rbx
0x1800151b4  mov     [rdi+8], eax
0x1800151b7  mov     rax, [rbx]
0x1800151ba  mov     rax, [rax+20h]
0x1800151be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151c3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800151c7  inc     rcx
0x1800151ca  cmp     byte ptr [rax+rcx], 0
0x1800151ce  jnz     short loc_1800151C7
0x1800151d0  lea     rsi, [rcx+1]
0x1800151d4  mov     rcx, rsi; cb
0x1800151d7  call    cs:__imp_CoTaskMemAlloc
0x1800151dd  mov     [rdi], rax
0x1800151e0  test    rax, rax
0x1800151e3  jnz     short loc_1800151FA
0x1800151e5  mov     eax, 8007000Eh
0x1800151ea  mov     rbx, [rsp+28h+arg_0]
0x1800151ef  mov     rsi, [rsp+28h+arg_8]
0x1800151f4  add     rsp, 20h
0x1800151f8  pop     rdi
0x1800151f9  retn
0x1800151fa  mov     rax, [rbx]
0x1800151fd  mov     rcx, rbx
0x180015200  mov     rax, [rax+20h]
0x180015204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015209  mov     rcx, [rdi]; Destination
0x18001520c  mov     r8, rax; Source
0x18001520f  mov     rdx, rsi; SizeInBytes
0x180015212  call    cs:__imp_strcpy_s
0x180015218  xor     eax, eax
0x18001521a  jmp     short loc_1800151EA
0x18001521c  mov     eax, 80070057h
0x180015221  jmp     short loc_1800151EA
```
