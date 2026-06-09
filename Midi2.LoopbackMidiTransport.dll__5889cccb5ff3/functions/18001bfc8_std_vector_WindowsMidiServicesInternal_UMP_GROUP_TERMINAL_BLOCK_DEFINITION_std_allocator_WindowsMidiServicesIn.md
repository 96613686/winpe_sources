# std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION,std::allocator<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>>::_Emplace_reallocate<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &>(WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION * const,WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &)

- ea: `0x18001bfc8`
- end: `0x18001c17f`
- name: `??$_Emplace_reallocate@AEBUUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@@?$vector@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@V?$allocator@UUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@@std@@@std@@AEAAPEAUUMP_GROUP_TERMINAL_BLOCK_DEFINITION@WindowsMidiServicesInternal@@QEAU23@AEBU23@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x1800210e4`

## callees

- `0x1800041a4`
- `0x1800041d0`
- `0x180005000`
- `0x18000c290`
- `0x180013954`
- `0x18001bfc8`

## pseudocode

```c
char *__fastcall std::vector<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION>::_Emplace_reallocate<WindowsMidiServicesInternal::UMP_GROUP_TERMINAL_BLOCK_DEFINITION const &>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3)
{
  _BYTE *v3; // r14
  __int64 v5; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rax
  __int64 v11; // r15
  bool v12; // cf
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  _QWORD *v15; // rbx
  void *v16; // rax
  void *v17; // rcx
  char *v18; // r14
  _BYTE *v19; // r8
  _BYTE *v20; // rdx
  size_t v21; // r8
  _BYTE *v22; // rcx
  _BYTE *v23; // rax
  char *result; // rax

  v3 = (_BYTE *)*a1;
  v5 = 0x4EC4EC4EC4EC4EC5LL * (a1[1] - *a1);
  if ( v5 == 0x13B13B13B13B13B1LL )
    std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength();
  v8 = 0x4EC4EC4EC4EC4EC5LL * (a1[2] - (_QWORD)v3);
  v9 = v8 >> 1;
  if ( v8 > 0x13B13B13B13B13B1LL - (v8 >> 1) )
    goto LABEL_24;
  v10 = v8 + v9;
  v11 = v5 + 1;
  v12 = v8 + v9 < v5 + 1;
  v13 = v5 + 1;
  if ( !v12 )
    v13 = v10;
  if ( v13 > 0x13B13B13B13B13B1LL )
    goto LABEL_24;
  v14 = 13 * v13;
  if ( !(13 * v13) )
  {
    v15 = 0;
    goto LABEL_13;
  }
  if ( v14 < 0x1000 )
  {
    v15 = operator new(13 * v13);
    goto LABEL_13;
  }
  if ( v14 + 39 < v14 )
LABEL_24:
    __scrt_throw_std_bad_array_new_length();
  v16 = operator new(v14 + 39);
  if ( !v16 )
    goto LABEL_19;
  v15 = (_QWORD *)(((unsigned __int64)v16 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v15 - 1) = v16;
LABEL_13:
  v17 = v15;
  v18 = (char *)v15 + 13 * ((a2 - v3) / 13);
  *(_QWORD *)v18 = *(_QWORD *)a3;
  *((_DWORD *)v18 + 2) = *(_DWORD *)(a3 + 8);
  v18[12] = *(_BYTE *)(a3 + 12);
  v19 = (_BYTE *)a1[1];
  v20 = (_BYTE *)*a1;
  if ( a2 == v19 )
  {
    v21 = v19 - v20;
  }
  else
  {
    memmove_0(v15, v20, (size_t)&a2[-*a1]);
    v17 = v18 + 13;
    v21 = a1[1] - (_QWORD)a2;
    v20 = a2;
  }
  memmove_0(v17, v20, v21);
  v22 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( a1[2] - (_QWORD)v22 < 0x1000u )
    {
      v23 = (_BYTE *)*a1;
    }
    else
    {
      v23 = (_BYTE *)*((_QWORD *)v22 - 1);
      if ( (unsigned __int64)(v22 - v23 - 8) > 0x1F )
LABEL_19:
        __fastfail(5u);
    }
    operator delete(v23);
  }
  *a1 = v15;
  result = v18;
  a1[1] = (char *)v15 + 13 * v11;
  a1[2] = (char *)v15 + v14;
  return result;
}

```

## disassembly

```asm
0x18001bfc8  push    rbx
0x18001bfca  push    rbp
0x18001bfcb  push    rsi
0x18001bfcc  push    rdi
0x18001bfcd  push    r12
0x18001bfcf  push    r13
0x18001bfd1  push    r14
0x18001bfd3  push    r15
0x18001bfd5  sub     rsp, 28h
0x18001bfd9  mov     r14, [rcx]
0x18001bfdc  mov     r12, 4EC4EC4EC4EC4EC5h
0x18001bfe6  mov     r9, [rcx+8]
0x18001bfea  mov     r13, r8
0x18001bfed  sub     r9, r14
0x18001bff0  mov     r8, 13B13B13B13B13B1h
0x18001bffa  imul    r9, r12
0x18001bffe  mov     rbp, rdx
0x18001c001  mov     rdi, rcx
0x18001c004  cmp     r9, r8
0x18001c007  jz      loc_18001C173
0x18001c00d  mov     rcx, [rcx+10h]
0x18001c011  mov     rax, r8
0x18001c014  sub     rcx, r14
0x18001c017  imul    rcx, r12
0x18001c01b  mov     rdx, rcx
0x18001c01e  shr     rdx, 1
0x18001c021  sub     rax, rdx
0x18001c024  cmp     rcx, rax
0x18001c027  ja      loc_18001C179
0x18001c02d  lea     rax, [rcx+rdx]
0x18001c031  lea     r15, [r9+1]
0x18001c035  cmp     rax, r15
0x18001c038  mov     rcx, r15
0x18001c03b  cmovnb  rcx, rax
0x18001c03f  cmp     rcx, r8
0x18001c042  ja      loc_18001C179
0x18001c048  imul    rsi, rcx, 0Dh
0x18001c04c  test    rsi, rsi
0x18001c04f  jnz     short loc_18001C055
0x18001c051  xor     ebx, ebx
0x18001c053  jmp     short loc_18001C092
0x18001c055  cmp     rsi, 1000h
0x18001c05c  jb      short loc_18001C087
0x18001c05e  lea     rcx, [rsi+27h]; Size
0x18001c062  cmp     rcx, rsi
0x18001c065  jbe     loc_18001C179
0x18001c06b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c070  test    rax, rax
0x18001c073  jz      loc_18001C137
0x18001c079  lea     rbx, [rax+27h]
0x18001c07d  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001c081  mov     [rbx-8], rax
0x18001c085  jmp     short loc_18001C092
0x18001c087  mov     rcx, rsi; Size
0x18001c08a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c08f  mov     rbx, rax
0x18001c092  movsd   xmm0, qword ptr [r13+0]
0x18001c098  mov     rcx, rbp
0x18001c09b  sub     rcx, r14
0x18001c09e  mov     rax, r12
0x18001c0a1  imul    rcx
0x18001c0a4  sar     rdx, 2
0x18001c0a8  mov     rcx, rdx
0x18001c0ab  shr     rcx, 3Fh
0x18001c0af  add     rdx, rcx
0x18001c0b2  mov     rcx, rbx; void *
0x18001c0b5  imul    r14, rdx, 0Dh
0x18001c0b9  add     r14, rbx
0x18001c0bc  movsd   qword ptr [r14], xmm0
0x18001c0c1  mov     eax, [r13+8]
0x18001c0c5  mov     [r14+8], eax
0x18001c0c9  mov     al, [r13+0Ch]
0x18001c0cd  mov     [r14+0Ch], al
0x18001c0d1  mov     r8, [rdi+8]
0x18001c0d5  mov     rdx, [rdi]; Src
0x18001c0d8  cmp     rbp, r8
0x18001c0db  jnz     short loc_18001C0E2
0x18001c0dd  sub     r8, rdx
0x18001c0e0  jmp     short loc_18001C0FB
0x18001c0e2  mov     r8, rbp
0x18001c0e5  sub     r8, [rdi]; Size
0x18001c0e8  call    memmove_0
0x18001c0ed  mov     r8, [rdi+8]
0x18001c0f1  lea     rcx, [r14+0Dh]; void *
0x18001c0f5  sub     r8, rbp; Size
0x18001c0f8  mov     rdx, rbp; Src
0x18001c0fb  call    memmove_0
0x18001c100  mov     rcx, [rdi]
0x18001c103  test    rcx, rcx
0x18001c106  jz      short loc_18001C149
0x18001c108  mov     rax, [rdi+10h]
0x18001c10c  sub     rax, rcx
0x18001c10f  imul    rax, r12
0x18001c113  imul    rdx, rax, 0Dh
0x18001c117  cmp     rdx, 1000h
0x18001c11e  jb      short loc_18001C13E
0x18001c120  mov     rax, [rcx-8]
0x18001c124  sub     rcx, rax
0x18001c127  sub     rcx, 8
0x18001c12b  cmp     rcx, 1Fh
0x18001c12f  ja      short loc_18001C137
0x18001c131  add     rdx, 27h ; '''
0x18001c135  jmp     short loc_18001C141
0x18001c137  mov     ecx, 5
0x18001c13c  int     29h; Win8: RtlFailFast(ecx)
0x18001c13e  mov     rax, rcx
0x18001c141  mov     rcx, rax; Block
0x18001c144  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001c149  mov     [rdi], rbx
0x18001c14c  mov     rax, r14
0x18001c14f  imul    rcx, r15, 0Dh
0x18001c153  add     rcx, rbx
0x18001c156  mov     [rdi+8], rcx
0x18001c15a  lea     rcx, [rsi+rbx]
0x18001c15e  mov     [rdi+10h], rcx
0x18001c162  add     rsp, 28h
0x18001c166  pop     r15
0x18001c168  pop     r14
0x18001c16a  pop     r13
0x18001c16c  pop     r12
0x18001c16e  pop     rdi
0x18001c16f  pop     rsi
0x18001c170  pop     rbp
0x18001c171  pop     rbx
0x18001c172  retn
0x18001c173  call    ?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength(void)
0x18001c179  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
