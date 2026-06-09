# ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::GrowBuffer(unsigned __int64)

- ea: `0x18005d4c0`
- end: `0x18005d584`
- name: `?GrowBuffer@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@AEAA_N_K@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005d58c`

## callees

- `0x180006424`
- `0x18005d4c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18005d555`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18005d555`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d4fb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d536`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d4fb`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18005d536`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005d565`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005d565`

## pseudocode

```c
char __fastcall ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 1u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 1u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, *(_QWORD *)(a1 + 8), *(const void *const *)a1, *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18005d4c0  mov     [rsp+arg_0], rbx
0x18005d4c5  mov     [rsp+arg_8], rsi
0x18005d4ca  push    rdi
0x18005d4cb  sub     rsp, 20h
0x18005d4cf  mov     rdi, rdx
0x18005d4d2  mov     rbx, rcx
0x18005d4d5  mov     rdx, [rcx+10h]
0x18005d4d9  cmp     rdi, rdx
0x18005d4dc  jbe     loc_18005D572
0x18005d4e2  cmp     qword ptr [rbx], 0
0x18005d4e6  movsxd  rcx, dword ptr [rcx+18h]
0x18005d4ea  jnz     short loc_18005D50B
0x18005d4ec  cmp     rcx, rdi
0x18005d4ef  mov     edx, 1; Size
0x18005d4f4  cmova   rdi, rcx
0x18005d4f8  mov     rcx, rdi; Count
0x18005d4fb  call    cs:__imp_calloc
0x18005d501  mov     [rbx], rax
0x18005d504  test    rax, rax
0x18005d507  jz      short loc_18005D544
0x18005d509  jmp     short loc_18005D56E
0x18005d50b  test    rcx, rcx
0x18005d50e  jnz     short loc_18005D523
0x18005d510  mov     rcx, rdx
0x18005d513  mov     rax, rdi
0x18005d516  shr     rcx, 1
0x18005d519  sub     rax, rdx
0x18005d51c  cmp     rax, rcx
0x18005d51f  cmova   rcx, rax
0x18005d523  lea     rax, [rdx+rcx]
0x18005d527  mov     edx, 1; Size
0x18005d52c  cmp     rdi, rax
0x18005d52f  cmovb   rdi, rax
0x18005d533  mov     rcx, rdi; Count
0x18005d536  call    cs:__imp_calloc
0x18005d53c  mov     rsi, rax
0x18005d53f  test    rax, rax
0x18005d542  jnz     short loc_18005D548
0x18005d544  xor     al, al
0x18005d546  jmp     short loc_18005D574
0x18005d548  mov     rdx, [rbx+8]; DestinationSize
0x18005d54c  mov     rcx, rsi; Destination
0x18005d54f  mov     r8, [rbx]; Source
0x18005d552  mov     r9, rdx; SourceSize
0x18005d555  call    cs:__imp_memmove_s
0x18005d55b  mov     ecx, eax; int
0x18005d55d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18005d562  mov     rcx, [rbx]; Block
0x18005d565  call    cs:__imp_free
0x18005d56b  mov     [rbx], rsi
0x18005d56e  mov     [rbx+10h], rdi
0x18005d572  mov     al, 1
0x18005d574  mov     rbx, [rsp+28h+arg_0]
0x18005d579  mov     rsi, [rsp+28h+arg_8]
0x18005d57e  add     rsp, 20h
0x18005d582  pop     rdi
0x18005d583  retn
```
