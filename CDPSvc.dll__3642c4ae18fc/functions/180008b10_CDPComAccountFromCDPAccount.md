# CDPComAccountFromCDPAccount

- ea: `0x180008b10`
- end: `0x180008bc3`
- name: `CDPComAccountFromCDPAccount`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180016808`

## callees

- `0x180008b10`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008bb2`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180008bb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b77`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180008b77`

## pseudocode

```c
__int64 __fastcall CDPComAccountFromCDPAccount(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rcx
  rsize_t v7; // rsi
  LPVOID v8; // rax
  const char *v10; // rax

  if ( !a2 || !a1 )
    return 2147942487LL;
  *(_OWORD *)a2 = 0;
  *(_DWORD *)(a2 + 8) = (*(unsigned __int16 (__fastcall **)(__int64))(*(_QWORD *)a1 + 24LL))(a1);
  v4 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  v5 = -1;
  while ( *(_BYTE *)(v4 + v5++ + 1) != 0 )
    ;
  v7 = v5 + 1;
  v8 = CoTaskMemAlloc(v5 + 1);
  *(_QWORD *)a2 = v8;
  if ( !v8 )
    return 2147942414LL;
  v10 = (const char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 32LL))(a1);
  strcpy_s(*(char **)a2, v7, v10);
  return 0;
}

```

## disassembly

```asm
0x180008b10  mov     [rsp+arg_8], rbx
0x180008b15  push    rdi
0x180008b16  sub     rsp, 20h
0x180008b1a  mov     rbx, rdx
0x180008b1d  mov     rdi, rcx
0x180008b20  test    rdx, rdx
0x180008b23  jz      loc_180008BBC
0x180008b29  test    rcx, rcx
0x180008b2c  jz      loc_180008BBC
0x180008b32  xorps   xmm0, xmm0
0x180008b35  mov     [rsp+28h+arg_0], rsi
0x180008b3a  movups  xmmword ptr [rdx], xmm0
0x180008b3d  mov     rax, [rcx]
0x180008b40  mov     rax, [rax+18h]
0x180008b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b49  movzx   eax, ax
0x180008b4c  mov     rcx, rdi
0x180008b4f  mov     [rbx+8], eax
0x180008b52  mov     rax, [rdi]
0x180008b55  mov     rax, [rax+20h]
0x180008b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008b65  cmp     byte ptr [rax+rcx+1], 0
0x180008b6a  lea     rcx, [rcx+1]
0x180008b6e  jnz     short loc_180008B65
0x180008b70  lea     rsi, [rcx+1]
0x180008b74  mov     rcx, rsi; cb
0x180008b77  call    cs:__imp_CoTaskMemAlloc
0x180008b7d  mov     [rbx], rax
0x180008b80  test    rax, rax
0x180008b83  jnz     short loc_180008B9A
0x180008b85  mov     eax, 8007000Eh
0x180008b8a  mov     rsi, [rsp+28h+arg_0]
0x180008b8f  mov     rbx, [rsp+28h+arg_8]
0x180008b94  add     rsp, 20h
0x180008b98  pop     rdi
0x180008b99  retn
0x180008b9a  mov     rax, [rdi]
0x180008b9d  mov     rcx, rdi
0x180008ba0  mov     rax, [rax+20h]
0x180008ba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ba9  mov     rcx, [rbx]; Destination
0x180008bac  mov     r8, rax; Source
0x180008baf  mov     rdx, rsi; SizeInBytes
0x180008bb2  call    cs:__imp_strcpy_s
0x180008bb8  xor     eax, eax
0x180008bba  jmp     short loc_180008B8A
0x180008bbc  mov     eax, 80070057h
0x180008bc1  jmp     short loc_180008B8F
```
