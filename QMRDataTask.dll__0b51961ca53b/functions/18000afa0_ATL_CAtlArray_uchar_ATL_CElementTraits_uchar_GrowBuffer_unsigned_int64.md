# ATL::CAtlArray<uchar,ATL::CElementTraits<uchar>>::GrowBuffer(unsigned __int64)

- ea: `0x18000afa0`
- end: `0x18000b096`
- name: `?GrowBuffer@?$CAtlArray@EV?$CElementTraits@E@ATL@@@ATL@@AEAA_N_K@Z`
- size: `246`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ec8`

## callees

- `0x180006a30`
- `0x18000afa0`

## import_xrefs

- `msvcrt!free` at `0x18000b056`
- `msvcrt!free` at `0x18000b056`
- `msvcrt!calloc` at `0x18000afdb`
- `msvcrt!calloc` at `0x18000b016`
- `msvcrt!calloc` at `0x18000afdb`
- `msvcrt!calloc` at `0x18000b016`
- `msvcrt!memmove_s` at `0x18000b035`
- `msvcrt!memmove_s` at `0x18000b035`

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
    v7 = calloc(a2, 1u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, *(_QWORD *)(a1 + 8), *(const void *const *)a1, *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 1u);
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
0x18000afa0  mov     [rsp+arg_0], rbx
0x18000afa5  mov     [rsp+arg_8], rsi
0x18000afaa  push    rdi
0x18000afab  sub     rsp, 20h
0x18000afaf  mov     rdi, rdx
0x18000afb2  mov     rbx, rcx
0x18000afb5  mov     rdx, [rcx+10h]
0x18000afb9  cmp     rdi, rdx
0x18000afbc  jbe     loc_18000B063
0x18000afc2  cmp     qword ptr [rbx], 0
0x18000afc6  movsxd  rcx, dword ptr [rcx+18h]
0x18000afca  jnz     short loc_18000AFEB
0x18000afcc  cmp     rcx, rdi
0x18000afcf  mov     edx, 1; Size
0x18000afd4  cmova   rdi, rcx
0x18000afd8  mov     rcx, rdi; Count
0x18000afdb  call    cs:__imp_calloc
0x18000afe1  mov     [rbx], rax
0x18000afe4  test    rax, rax
0x18000afe7  jz      short loc_18000B024
0x18000afe9  jmp     short loc_18000B05F
0x18000afeb  test    rcx, rcx
0x18000afee  jnz     short loc_18000B003
0x18000aff0  mov     rcx, rdx
0x18000aff3  mov     rax, rdi
0x18000aff6  shr     rcx, 1
0x18000aff9  sub     rax, rdx
0x18000affc  cmp     rax, rcx
0x18000afff  cmova   rcx, rax
0x18000b003  lea     rax, [rdx+rcx]
0x18000b007  mov     edx, 1; Size
0x18000b00c  cmp     rdi, rax
0x18000b00f  cmovb   rdi, rax
0x18000b013  mov     rcx, rdi; Count
0x18000b016  call    cs:__imp_calloc
0x18000b01c  mov     rsi, rax
0x18000b01f  test    rax, rax
0x18000b022  jnz     short loc_18000B028
0x18000b024  xor     al, al
0x18000b026  jmp     short loc_18000B065
0x18000b028  mov     rdx, [rbx+8]; DestinationSize
0x18000b02c  mov     rcx, rsi; Destination
0x18000b02f  mov     r8, [rbx]; Source
0x18000b032  mov     r9, rdx; SourceSize
0x18000b035  call    cs:__imp_memmove_s
0x18000b03b  test    eax, eax
0x18000b03d  jz      short loc_18000B053
0x18000b03f  cmp     eax, 0Ch
0x18000b042  jz      short loc_18000B08B
0x18000b044  cmp     eax, 16h
0x18000b047  jz      short loc_18000B080
0x18000b049  cmp     eax, 22h ; '"'
0x18000b04c  jz      short loc_18000B080
0x18000b04e  cmp     eax, 50h ; 'P'
0x18000b051  jnz     short loc_18000B075
0x18000b053  mov     rcx, [rbx]; Block
0x18000b056  call    cs:__imp_free
0x18000b05c  mov     [rbx], rsi
0x18000b05f  mov     [rbx+10h], rdi
0x18000b063  mov     al, 1
0x18000b065  mov     rbx, [rsp+28h+arg_0]
0x18000b06a  mov     rsi, [rsp+28h+arg_8]
0x18000b06f  add     rsp, 20h
0x18000b073  pop     rdi
0x18000b074  retn
0x18000b075  mov     ecx, 80004005h; int
0x18000b07a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b080  mov     ecx, 80070057h; int
0x18000b085  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b08b  mov     ecx, 8007000Eh; int
0x18000b090  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
