# ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::GrowBuffer(unsigned __int64)

- ea: `0x180010118`
- end: `0x180010212`
- name: `?GrowBuffer@?$CAtlArray@V?$SmartPtr@VString@UnBCL@@@UnBCL@@V?$CElementTraits@V?$SmartPtr@VString@UnBCL@@@UnBCL@@@ATL@@@ATL@@AEAA_N_K@Z`
- size: `250`
- prototype: `char __fastcall(__int64, size_t)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e4d4`
- `0x180013764`

## callees

- `0x180005ef8`
- `0x180010118`

## import_xrefs

- `msvcrt!free` at `0x1800101d2`
- `msvcrt!free` at `0x1800101d2`
- `msvcrt!memmove_s` at `0x1800101b1`
- `msvcrt!memmove_s` at `0x1800101b1`
- `msvcrt!calloc` at `0x180010153`
- `msvcrt!calloc` at `0x18001018e`
- `msvcrt!calloc` at `0x180010153`
- `msvcrt!calloc` at `0x18001018e`

## pseudocode

```c
char __fastcall ATL::CAtlArray<UnBCL::SmartPtr<UnBCL::String>,ATL::CElementTraits<UnBCL::SmartPtr<UnBCL::String>>>::GrowBuffer(
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
    v7 = calloc(a2, 0x10u);
    v8 = v7;
    if ( v7 )
    {
      v10 = memmove_s(v7, 16LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 16LL * *(_QWORD *)(a1 + 8));
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
  v6 = calloc(a2, 0x10u);
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
0x180010118  mov     [rsp+arg_0], rbx
0x18001011d  mov     [rsp+arg_8], rsi
0x180010122  push    rdi
0x180010123  sub     rsp, 20h
0x180010127  mov     rdi, rdx
0x18001012a  mov     rbx, rcx
0x18001012d  mov     rdx, [rcx+10h]
0x180010131  cmp     rdi, rdx
0x180010134  jbe     loc_1800101DF
0x18001013a  cmp     qword ptr [rbx], 0
0x18001013e  movsxd  rcx, dword ptr [rcx+18h]
0x180010142  jnz     short loc_180010163
0x180010144  cmp     rcx, rdi
0x180010147  mov     edx, 10h; Size
0x18001014c  cmova   rdi, rcx
0x180010150  mov     rcx, rdi; Count
0x180010153  call    cs:__imp_calloc
0x180010159  mov     [rbx], rax
0x18001015c  test    rax, rax
0x18001015f  jz      short loc_18001019C
0x180010161  jmp     short loc_1800101DB
0x180010163  test    rcx, rcx
0x180010166  jnz     short loc_18001017B
0x180010168  mov     rcx, rdx
0x18001016b  mov     rax, rdi
0x18001016e  shr     rcx, 1
0x180010171  sub     rax, rdx
0x180010174  cmp     rax, rcx
0x180010177  cmova   rcx, rax
0x18001017b  lea     rax, [rdx+rcx]
0x18001017f  mov     edx, 10h; Size
0x180010184  cmp     rdi, rax
0x180010187  cmovb   rdi, rax
0x18001018b  mov     rcx, rdi; Count
0x18001018e  call    cs:__imp_calloc
0x180010194  mov     rsi, rax
0x180010197  test    rax, rax
0x18001019a  jnz     short loc_1800101A0
0x18001019c  xor     al, al
0x18001019e  jmp     short loc_1800101E1
0x1800101a0  mov     rdx, [rbx+8]
0x1800101a4  mov     rcx, rsi; Destination
0x1800101a7  mov     r8, [rbx]; Source
0x1800101aa  shl     rdx, 4; DestinationSize
0x1800101ae  mov     r9, rdx; SourceSize
0x1800101b1  call    cs:__imp_memmove_s
0x1800101b7  test    eax, eax
0x1800101b9  jz      short loc_1800101CF
0x1800101bb  cmp     eax, 0Ch
0x1800101be  jz      short loc_180010207
0x1800101c0  cmp     eax, 16h
0x1800101c3  jz      short loc_1800101FC
0x1800101c5  cmp     eax, 22h ; '"'
0x1800101c8  jz      short loc_1800101FC
0x1800101ca  cmp     eax, 50h ; 'P'
0x1800101cd  jnz     short loc_1800101F1
0x1800101cf  mov     rcx, [rbx]; Block
0x1800101d2  call    cs:__imp_free
0x1800101d8  mov     [rbx], rsi
0x1800101db  mov     [rbx+10h], rdi
0x1800101df  mov     al, 1
0x1800101e1  mov     rbx, [rsp+28h+arg_0]
0x1800101e6  mov     rsi, [rsp+28h+arg_8]
0x1800101eb  add     rsp, 20h
0x1800101ef  pop     rdi
0x1800101f0  retn
0x1800101f1  mov     ecx, 80004005h; int
0x1800101f6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800101fc  mov     ecx, 80070057h; int
0x180010201  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010207  mov     ecx, 8007000Eh; int
0x18001020c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
