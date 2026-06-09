# ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::GrowBuffer(unsigned __int64)

- ea: `0x1800099d0`
- end: `0x180009aca`
- name: `?GrowBuffer@?$CAtlArray@PEAVISetupCleanupJob@@V?$CElementTraits@PEAVISetupCleanupJob@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800051f4`
- `0x18000c1c0`

## callees

- `0x180005ef8`
- `0x1800099d0`

## import_xrefs

- `msvcrt!free` at `0x180009a8a`
- `msvcrt!free` at `0x180009a8a`
- `msvcrt!memmove_s` at `0x180009a69`
- `msvcrt!memmove_s` at `0x180009a69`
- `msvcrt!calloc` at `0x180009a0b`
- `msvcrt!calloc` at `0x180009a46`
- `msvcrt!calloc` at `0x180009a0b`
- `msvcrt!calloc` at `0x180009a46`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ISetupCleanupJob *,ATL::CElementTraits<ISetupCleanupJob *>>::GrowBuffer(
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
    v7 = calloc(a2, 8u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
      if ( v10 )
      {
        if ( v10 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v10 == 22 || v10 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v10 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      free(*(void **)a1);
      *(_QWORD *)a1 = v8;
      goto LABEL_20;
    }
    return 0;
  }
  if ( v5 > a2 )
    a2 = v5;
  v6 = calloc(a2, 8u);
  *(_QWORD *)a1 = v6;
  if ( !v6 )
    return 0;
LABEL_20:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x1800099d0  mov     [rsp+arg_0], rbx
0x1800099d5  mov     [rsp+arg_8], rsi
0x1800099da  push    rdi
0x1800099db  sub     rsp, 20h
0x1800099df  mov     rdi, rdx
0x1800099e2  mov     rbx, rcx
0x1800099e5  mov     rdx, [rcx+10h]
0x1800099e9  cmp     rdi, rdx
0x1800099ec  jbe     loc_180009A97
0x1800099f2  cmp     qword ptr [rbx], 0
0x1800099f6  movsxd  rcx, dword ptr [rcx+18h]
0x1800099fa  jnz     short loc_180009A1B
0x1800099fc  cmp     rcx, rdi
0x1800099ff  mov     edx, 8; Size
0x180009a04  cmova   rdi, rcx
0x180009a08  mov     rcx, rdi; Count
0x180009a0b  call    cs:__imp_calloc
0x180009a11  mov     [rbx], rax
0x180009a14  test    rax, rax
0x180009a17  jz      short loc_180009A54
0x180009a19  jmp     short loc_180009A93
0x180009a1b  test    rcx, rcx
0x180009a1e  jnz     short loc_180009A33
0x180009a20  mov     rcx, rdx
0x180009a23  mov     rax, rdi
0x180009a26  shr     rcx, 1
0x180009a29  sub     rax, rdx
0x180009a2c  cmp     rax, rcx
0x180009a2f  cmova   rcx, rax
0x180009a33  lea     rax, [rdx+rcx]
0x180009a37  mov     edx, 8; Size
0x180009a3c  cmp     rdi, rax
0x180009a3f  cmovb   rdi, rax
0x180009a43  mov     rcx, rdi; Count
0x180009a46  call    cs:__imp_calloc
0x180009a4c  mov     rsi, rax
0x180009a4f  test    rax, rax
0x180009a52  jnz     short loc_180009A58
0x180009a54  xor     al, al
0x180009a56  jmp     short loc_180009A99
0x180009a58  mov     rdx, [rbx+8]
0x180009a5c  mov     rcx, rsi; Destination
0x180009a5f  mov     r8, [rbx]; Source
0x180009a62  shl     rdx, 3; DestinationSize
0x180009a66  mov     r9, rdx; SourceSize
0x180009a69  call    cs:__imp_memmove_s
0x180009a6f  test    eax, eax
0x180009a71  jz      short loc_180009A87
0x180009a73  cmp     eax, 0Ch
0x180009a76  jz      short loc_180009ABF
0x180009a78  cmp     eax, 16h
0x180009a7b  jz      short loc_180009AB4
0x180009a7d  cmp     eax, 22h ; '"'
0x180009a80  jz      short loc_180009AB4
0x180009a82  cmp     eax, 50h ; 'P'
0x180009a85  jnz     short loc_180009AA9
0x180009a87  mov     rcx, [rbx]; Block
0x180009a8a  call    cs:__imp_free
0x180009a90  mov     [rbx], rsi
0x180009a93  mov     [rbx+10h], rdi
0x180009a97  mov     al, 1
0x180009a99  mov     rbx, [rsp+28h+arg_0]
0x180009a9e  mov     rsi, [rsp+28h+arg_8]
0x180009aa3  add     rsp, 20h
0x180009aa7  pop     rdi
0x180009aa8  retn
0x180009aa9  mov     ecx, 80004005h; int
0x180009aae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009ab4  mov     ecx, 80070057h; int
0x180009ab9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009abf  mov     ecx, 8007000Eh; int
0x180009ac4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
