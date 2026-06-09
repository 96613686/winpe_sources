# ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::GrowBuffer(unsigned __int64)

- ea: `0x180009fd8`
- end: `0x18000a0a0`
- name: `?GrowBuffer@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800064a0`
- `0x180006500`
- `0x1800119dc`
- `0x180011a84`
- `0x18001f6e8`
- `0x180020418`
- `0x1800364c0`
- `0x180039374`
- `0x18005aed4`

## callees

- `0x1800067dc`
- `0x180009fd8`

## import_xrefs

- `msvcrt!calloc` at `0x18000a013`
- `msvcrt!calloc` at `0x18000a04e`
- `msvcrt!calloc` at `0x18000a013`
- `msvcrt!calloc` at `0x18000a04e`
- `msvcrt!memmove_s` at `0x18000a071`
- `msvcrt!memmove_s` at `0x18000a071`
- `msvcrt!free` at `0x18000a081`
- `msvcrt!free` at `0x18000a081`

## pseudocode

```c
char __fastcall ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::GrowBuffer(
        __int64 a1,
        size_t a2)
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
    v6 = calloc(a2, 8u);
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
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
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
0x180009fd8  mov     [rsp+arg_0], rbx
0x180009fdd  mov     [rsp+arg_8], rsi
0x180009fe2  push    rdi
0x180009fe3  sub     rsp, 20h
0x180009fe7  mov     rbx, rdx
0x180009fea  mov     rdi, rcx
0x180009fed  mov     rdx, [rcx+10h]
0x180009ff1  cmp     rbx, rdx
0x180009ff4  jbe     loc_18000A08E
0x180009ffa  cmp     qword ptr [rdi], 0
0x180009ffe  movsxd  rcx, dword ptr [rcx+18h]
0x18000a002  jnz     short loc_18000A023
0x18000a004  cmp     rcx, rbx
0x18000a007  mov     edx, 8; Size
0x18000a00c  cmova   rbx, rcx
0x18000a010  mov     rcx, rbx; Count
0x18000a013  call    cs:__imp_calloc
0x18000a019  mov     [rdi], rax
0x18000a01c  test    rax, rax
0x18000a01f  jz      short loc_18000A05C
0x18000a021  jmp     short loc_18000A08A
0x18000a023  test    rcx, rcx
0x18000a026  jnz     short loc_18000A03B
0x18000a028  mov     rcx, rdx
0x18000a02b  mov     rax, rbx
0x18000a02e  shr     rcx, 1
0x18000a031  sub     rax, rdx
0x18000a034  cmp     rax, rcx
0x18000a037  cmova   rcx, rax
0x18000a03b  lea     rax, [rdx+rcx]
0x18000a03f  mov     edx, 8; Size
0x18000a044  cmp     rbx, rax
0x18000a047  cmovb   rbx, rax
0x18000a04b  mov     rcx, rbx; Count
0x18000a04e  call    cs:__imp_calloc
0x18000a054  mov     rsi, rax
0x18000a057  test    rax, rax
0x18000a05a  jnz     short loc_18000A060
0x18000a05c  xor     al, al
0x18000a05e  jmp     short loc_18000A090
0x18000a060  mov     rdx, [rdi+8]
0x18000a064  mov     rcx, rsi; Destination
0x18000a067  mov     r8, [rdi]; Source
0x18000a06a  shl     rdx, 3; DestinationSize
0x18000a06e  mov     r9, rdx; SourceSize
0x18000a071  call    cs:__imp_memmove_s
0x18000a077  mov     ecx, eax; int
0x18000a079  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000a07e  mov     rcx, [rdi]; Block
0x18000a081  call    cs:__imp_free
0x18000a087  mov     [rdi], rsi
0x18000a08a  mov     [rdi+10h], rbx
0x18000a08e  mov     al, 1
0x18000a090  mov     rbx, [rsp+28h+arg_0]
0x18000a095  mov     rsi, [rsp+28h+arg_8]
0x18000a09a  add     rsp, 20h
0x18000a09e  pop     rdi
0x18000a09f  retn
```
