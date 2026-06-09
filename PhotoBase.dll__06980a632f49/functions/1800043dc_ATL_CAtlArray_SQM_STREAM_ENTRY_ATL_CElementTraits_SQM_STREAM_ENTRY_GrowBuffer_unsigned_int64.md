# ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::GrowBuffer(unsigned __int64)

- ea: `0x1800043dc`
- end: `0x1800044bf`
- name: `?GrowBuffer@?$CAtlArray@U_SQM_STREAM_ENTRY@@V?$CElementTraits@U_SQM_STREAM_ENTRY@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000558c`
- `0x180006530`

## callees

- `0x180002106`
- `0x180002420`
- `0x1800043dc`
- `0x180007481`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800044a3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800044a3`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004417`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004452`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004417`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180004452`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004484`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180004484`

## pseudocode

```c
char __fastcall ATL::CAtlArray<_SQM_STREAM_ENTRY,ATL::CElementTraits<_SQM_STREAM_ENTRY>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  size_t v10; // r8
  int v11; // edx

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( *(_QWORD *)a1 )
  {
    if ( !v5 )
    {
      v5 = v4 >> 1;
      if ( a2 - v4 > v4 >> 1 )
        v5 = a2 - v4;
    }
    if ( a2 < v4 + v5 )
      a2 = v4 + v5;
    v7 = calloc(a2, 0x10u);
    v8 = v7;
    if ( v7 )
    {
      v10 = 16LL * *(_QWORD *)(a1 + 8);
      if ( v10 )
      {
        if ( !*(_QWORD *)a1 )
        {
          *(_DWORD *)_o__errno() = 22;
          invalid_parameter_noinfo();
          ATL::BaseAtlThrow((BasePrivate *)0x80070057LL, v11);
        }
        memcpy_0(v7, *(const void **)a1, v10);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_18;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 0x10u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_18:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x1800043dc  mov     [rsp+arg_0], rbx
0x1800043e1  mov     [rsp+arg_8], rsi
0x1800043e6  push    rdi
0x1800043e7  sub     rsp, 20h
0x1800043eb  mov     rdi, rdx
0x1800043ee  mov     rbx, rcx
0x1800043f1  mov     rdx, [rcx+10h]
0x1800043f5  cmp     rdi, rdx
0x1800043f8  jbe     loc_180004491
0x1800043fe  cmp     qword ptr [rbx], 0
0x180004402  movsxd  rcx, dword ptr [rcx+18h]
0x180004406  jnz     short loc_180004427
0x180004408  cmp     rcx, rdi
0x18000440b  mov     edx, 10h; Size
0x180004410  cmova   rdi, rcx
0x180004414  mov     rcx, rdi; Count
0x180004417  call    cs:__imp_calloc
0x18000441d  mov     [rbx], rax
0x180004420  test    rax, rax
0x180004423  jz      short loc_180004460
0x180004425  jmp     short loc_18000448D
0x180004427  test    rcx, rcx
0x18000442a  jnz     short loc_18000443F
0x18000442c  mov     rcx, rdx
0x18000442f  mov     rax, rdi
0x180004432  shr     rcx, 1
0x180004435  sub     rax, rdx
0x180004438  cmp     rax, rcx
0x18000443b  cmova   rcx, rax
0x18000443f  lea     rax, [rdx+rcx]
0x180004443  mov     edx, 10h; Size
0x180004448  cmp     rdi, rax
0x18000444b  cmovb   rdi, rax
0x18000444f  mov     rcx, rdi; Count
0x180004452  call    cs:__imp_calloc
0x180004458  mov     rsi, rax
0x18000445b  test    rax, rax
0x18000445e  jnz     short loc_180004464
0x180004460  xor     al, al
0x180004462  jmp     short loc_180004493
0x180004464  mov     r8, [rbx+8]
0x180004468  shl     r8, 4; Size
0x18000446c  test    r8, r8
0x18000446f  jz      short loc_180004481
0x180004471  mov     rdx, [rbx]; Src
0x180004474  test    rdx, rdx
0x180004477  jz      short loc_1800044A3
0x180004479  mov     rcx, rsi; void *
0x18000447c  call    memcpy_0
0x180004481  mov     rcx, [rbx]; Block
0x180004484  call    cs:__imp_free
0x18000448a  mov     [rbx], rsi
0x18000448d  mov     [rbx+10h], rdi
0x180004491  mov     al, 1
0x180004493  mov     rbx, [rsp+28h+arg_0]
0x180004498  mov     rsi, [rsp+28h+arg_8]
0x18000449d  add     rsp, 20h
0x1800044a1  pop     rdi
0x1800044a2  retn
0x1800044a3  call    cs:__imp__o__errno
0x1800044a9  mov     dword ptr [rax], 16h
0x1800044af  call    _invalid_parameter_noinfo
0x1800044b4  mov     ecx, 80070057h; int
0x1800044b9  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
