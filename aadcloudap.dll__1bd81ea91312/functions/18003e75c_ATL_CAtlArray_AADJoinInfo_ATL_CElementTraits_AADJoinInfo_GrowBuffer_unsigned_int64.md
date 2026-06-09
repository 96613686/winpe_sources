# ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>::GrowBuffer(unsigned __int64)

- ea: `0x18003e75c`
- end: `0x18003e828`
- name: `?GrowBuffer@?$CAtlArray@UAADJoinInfo@@V?$CElementTraits@UAADJoinInfo@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18003d328`
- `0x18003fe74`

## callees

- `0x180006424`
- `0x18003e75c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003e7f9`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18003e7f9`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003e797`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003e7d2`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003e797`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18003e7d2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003e809`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18003e809`

## pseudocode

```c
char __fastcall ATL::CAtlArray<AADJoinInfo,ATL::CElementTraits<AADJoinInfo>>::GrowBuffer(__int64 a1, size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rsi
  errno_t v9; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 0x50u);
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
  v7 = calloc(a2, 0x50u);
  if ( !v7 )
    return 0;
  v9 = memmove_s(v7, 80LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 80LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v9);
  free(*(void **)a1);
  *(_QWORD *)a1 = v7;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18003e75c  mov     [rsp+arg_0], rbx
0x18003e761  mov     [rsp+arg_8], rsi
0x18003e766  push    rdi
0x18003e767  sub     rsp, 20h
0x18003e76b  mov     rdi, rdx
0x18003e76e  mov     rbx, rcx
0x18003e771  mov     rdx, [rcx+10h]
0x18003e775  cmp     rdi, rdx
0x18003e778  jbe     loc_18003E816
0x18003e77e  cmp     qword ptr [rbx], 0
0x18003e782  movsxd  rcx, dword ptr [rcx+18h]
0x18003e786  jnz     short loc_18003E7A7
0x18003e788  cmp     rcx, rdi
0x18003e78b  mov     edx, 50h ; 'P'; Size
0x18003e790  cmova   rdi, rcx
0x18003e794  mov     rcx, rdi; Count
0x18003e797  call    cs:__imp_calloc
0x18003e79d  mov     [rbx], rax
0x18003e7a0  test    rax, rax
0x18003e7a3  jz      short loc_18003E7E0
0x18003e7a5  jmp     short loc_18003E812
0x18003e7a7  test    rcx, rcx
0x18003e7aa  jnz     short loc_18003E7BF
0x18003e7ac  mov     rcx, rdx
0x18003e7af  mov     rax, rdi
0x18003e7b2  shr     rcx, 1
0x18003e7b5  sub     rax, rdx
0x18003e7b8  cmp     rax, rcx
0x18003e7bb  cmova   rcx, rax
0x18003e7bf  lea     rax, [rdx+rcx]
0x18003e7c3  mov     edx, 50h ; 'P'; Size
0x18003e7c8  cmp     rdi, rax
0x18003e7cb  cmovb   rdi, rax
0x18003e7cf  mov     rcx, rdi; Count
0x18003e7d2  call    cs:__imp_calloc
0x18003e7d8  mov     rsi, rax
0x18003e7db  test    rax, rax
0x18003e7de  jnz     short loc_18003E7E4
0x18003e7e0  xor     al, al
0x18003e7e2  jmp     short loc_18003E818
0x18003e7e4  mov     rax, [rbx+8]
0x18003e7e8  mov     rcx, rsi; Destination
0x18003e7eb  mov     r8, [rbx]; Source
0x18003e7ee  lea     rdx, [rax+rax*4]
0x18003e7f2  shl     rdx, 4; DestinationSize
0x18003e7f6  mov     r9, rdx; SourceSize
0x18003e7f9  call    cs:__imp_memmove_s
0x18003e7ff  mov     ecx, eax; int
0x18003e801  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18003e806  mov     rcx, [rbx]; Block
0x18003e809  call    cs:__imp_free
0x18003e80f  mov     [rbx], rsi
0x18003e812  mov     [rbx+10h], rdi
0x18003e816  mov     al, 1
0x18003e818  mov     rbx, [rsp+28h+arg_0]
0x18003e81d  mov     rsi, [rsp+28h+arg_8]
0x18003e822  add     rsp, 20h
0x18003e826  pop     rdi
0x18003e827  retn
```
