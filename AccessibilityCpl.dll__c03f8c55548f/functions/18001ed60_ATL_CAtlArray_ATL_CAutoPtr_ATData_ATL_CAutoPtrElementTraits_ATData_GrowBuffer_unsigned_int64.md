# ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(unsigned __int64)

- ea: `0x18001ed60`
- end: `0x18001ee28`
- name: `?GrowBuffer@?$CAtlArray@V?$CAutoPtr@VATData@@@ATL@@V?$CAutoPtrElementTraits@VATData@@@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d978`
- `0x18001ee30`
- `0x18001f0d8`
- `0x1800256a0`

## callees

- `0x180005420`
- `0x18001ed60`

## import_xrefs

- `msvcrt!calloc` at `0x18001ed9b`
- `msvcrt!calloc` at `0x18001edd6`
- `msvcrt!calloc` at `0x18001ed9b`
- `msvcrt!calloc` at `0x18001edd6`
- `msvcrt!free` at `0x18001ee09`
- `msvcrt!free` at `0x18001ee09`
- `msvcrt!memmove_s` at `0x18001edf9`
- `msvcrt!memmove_s` at `0x18001edf9`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CAutoPtr<ATData>,ATL::CAutoPtrElementTraits<ATData>>::GrowBuffer(
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
0x18001ed60  mov     [rsp+arg_0], rbx
0x18001ed65  mov     [rsp+arg_8], rsi
0x18001ed6a  push    rdi
0x18001ed6b  sub     rsp, 20h
0x18001ed6f  mov     rbx, rdx
0x18001ed72  mov     rdi, rcx
0x18001ed75  mov     rdx, [rcx+10h]
0x18001ed79  cmp     rbx, rdx
0x18001ed7c  jbe     loc_18001EE16
0x18001ed82  cmp     qword ptr [rdi], 0
0x18001ed86  movsxd  rcx, dword ptr [rcx+18h]
0x18001ed8a  jnz     short loc_18001EDAB
0x18001ed8c  cmp     rcx, rbx
0x18001ed8f  mov     edx, 8; Size
0x18001ed94  cmova   rbx, rcx
0x18001ed98  mov     rcx, rbx; Count
0x18001ed9b  call    cs:__imp_calloc
0x18001eda1  mov     [rdi], rax
0x18001eda4  test    rax, rax
0x18001eda7  jz      short loc_18001EDE4
0x18001eda9  jmp     short loc_18001EE12
0x18001edab  test    rcx, rcx
0x18001edae  jnz     short loc_18001EDC3
0x18001edb0  mov     rcx, rdx
0x18001edb3  mov     rax, rbx
0x18001edb6  shr     rcx, 1
0x18001edb9  sub     rax, rdx
0x18001edbc  cmp     rax, rcx
0x18001edbf  cmova   rcx, rax
0x18001edc3  lea     rax, [rdx+rcx]
0x18001edc7  mov     edx, 8; Size
0x18001edcc  cmp     rbx, rax
0x18001edcf  cmovb   rbx, rax
0x18001edd3  mov     rcx, rbx; Count
0x18001edd6  call    cs:__imp_calloc
0x18001eddc  mov     rsi, rax
0x18001eddf  test    rax, rax
0x18001ede2  jnz     short loc_18001EDE8
0x18001ede4  xor     al, al
0x18001ede6  jmp     short loc_18001EE18
0x18001ede8  mov     rdx, [rdi+8]
0x18001edec  mov     rcx, rsi; Destination
0x18001edef  mov     r8, [rdi]; Source
0x18001edf2  shl     rdx, 3; DestinationSize
0x18001edf6  mov     r9, rdx; SourceSize
0x18001edf9  call    cs:__imp_memmove_s
0x18001edff  mov     ecx, eax; int
0x18001ee01  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001ee06  mov     rcx, [rdi]; Block
0x18001ee09  call    cs:__imp_free
0x18001ee0f  mov     [rdi], rsi
0x18001ee12  mov     [rdi+10h], rbx
0x18001ee16  mov     al, 1
0x18001ee18  mov     rbx, [rsp+28h+arg_0]
0x18001ee1d  mov     rsi, [rsp+28h+arg_8]
0x18001ee22  add     rsp, 20h
0x18001ee26  pop     rdi
0x18001ee27  retn
```
