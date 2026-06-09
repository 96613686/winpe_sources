# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::_Emplace_reallocate<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(WindowsMidiServicesNamingLib::Midi1PortNameEntry * const,WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)

- ea: `0x180022a6c`
- end: `0x180022cbf`
- name: `??$_Emplace_reallocate@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@AEAAPEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@QEAU23@$$QEAU23@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18002ad40`

## callees

- `0x1800041a4`
- `0x1800041d0`
- `0x180005000`
- `0x18000c290`
- `0x180013954`
- `0x180022a6c`

## pseudocode

```c
char *__fastcall std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Emplace_reallocate<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3)
{
  _BYTE *v3; // rbp
  unsigned __int64 v6; // r9
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // r15
  bool v12; // cf
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rsi
  _QWORD *v15; // rbx
  void *v16; // rax
  void *v17; // rcx
  char *v18; // rbp
  _BYTE *v19; // r8
  _BYTE *v20; // rdx
  size_t v21; // r8
  _BYTE *v22; // rcx
  _BYTE *v23; // rax
  char *result; // rax

  v3 = (_BYTE *)*a1;
  v6 = 0x8F5C28F5C28F5C29uLL * ((__int64)(a1[1] - *a1) >> 3);
  if ( v6 == 0x147AE147AE147AELL )
    std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength();
  v8 = 0x8F5C28F5C28F5C29uLL * ((__int64)(a1[2] - (_QWORD)v3) >> 3);
  v9 = v8 >> 1;
  if ( v8 > 0x147AE147AE147AELL - (v8 >> 1) )
    goto LABEL_24;
  v10 = v8 + v9;
  v11 = v6 + 1;
  v12 = v8 + v9 < v6 + 1;
  v13 = v6 + 1;
  if ( !v12 )
    v13 = v10;
  if ( v13 > 0x147AE147AE147AELL )
    goto LABEL_24;
  v14 = 200 * v13;
  if ( !(200 * v13) )
  {
    v15 = 0;
    goto LABEL_13;
  }
  if ( v14 < 0x1000 )
  {
    v15 = operator new(200 * v13);
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
  v18 = (char *)&v15[25 * ((a2 - v3) / 200)];
  *(_OWORD *)v18 = *(_OWORD *)a3;
  *((_OWORD *)v18 + 1) = *(_OWORD *)(a3 + 16);
  *((_OWORD *)v18 + 2) = *(_OWORD *)(a3 + 32);
  *((_OWORD *)v18 + 3) = *(_OWORD *)(a3 + 48);
  *((_OWORD *)v18 + 4) = *(_OWORD *)(a3 + 64);
  *((_OWORD *)v18 + 5) = *(_OWORD *)(a3 + 80);
  *((_OWORD *)v18 + 6) = *(_OWORD *)(a3 + 96);
  *((_OWORD *)v18 + 7) = *(_OWORD *)(a3 + 112);
  *((_OWORD *)v18 + 8) = *(_OWORD *)(a3 + 128);
  *((_OWORD *)v18 + 9) = *(_OWORD *)(a3 + 144);
  *((_OWORD *)v18 + 10) = *(_OWORD *)(a3 + 160);
  *((_OWORD *)v18 + 11) = *(_OWORD *)(a3 + 176);
  *((_QWORD *)v18 + 24) = *(_QWORD *)(a3 + 192);
  v19 = (_BYTE *)a1[1];
  v20 = (_BYTE *)*a1;
  if ( a2 == v19 )
  {
    v21 = v19 - v20;
  }
  else
  {
    memmove_0(v15, v20, (size_t)&a2[-*a1]);
    v17 = v18 + 200;
    v21 = a1[1] - (_QWORD)a2;
    v20 = a2;
  }
  memmove_0(v17, v20, v21);
  v22 = (_BYTE *)*a1;
  if ( *a1 )
  {
    if ( (unsigned __int64)(8 * ((__int64)(a1[2] - (_QWORD)v22) >> 3)) < 0x1000 )
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
  a1[1] = &v15[25 * v11];
  a1[2] = &v15[v14 / 8];
  return result;
}

```

## disassembly

```asm
0x180022a6c  push    rbx
0x180022a6e  push    rbp
0x180022a6f  push    rsi
0x180022a70  push    rdi
0x180022a71  push    r12
0x180022a73  push    r13
0x180022a75  push    r14
0x180022a77  push    r15
0x180022a79  sub     rsp, 28h
0x180022a7d  mov     rbp, [rcx]
0x180022a80  mov     r12, 8F5C28F5C28F5C29h
0x180022a8a  mov     r9, [rcx+8]
0x180022a8e  mov     r13, r8
0x180022a91  sub     r9, rbp
0x180022a94  mov     r8, 147AE147AE147AEh
0x180022a9e  sar     r9, 3
0x180022aa2  mov     r14, rdx
0x180022aa5  imul    r9, r12
0x180022aa9  mov     rdi, rcx
0x180022aac  cmp     r9, r8
0x180022aaf  jz      loc_180022CB3
0x180022ab5  mov     rcx, [rcx+10h]
0x180022ab9  mov     rax, r8
0x180022abc  sub     rcx, rbp
0x180022abf  sar     rcx, 3
0x180022ac3  imul    rcx, r12
0x180022ac7  mov     rdx, rcx
0x180022aca  shr     rdx, 1
0x180022acd  sub     rax, rdx
0x180022ad0  cmp     rcx, rax
0x180022ad3  ja      loc_180022CB9
0x180022ad9  lea     rax, [rcx+rdx]
0x180022add  lea     r15, [r9+1]
0x180022ae1  cmp     rax, r15
0x180022ae4  mov     rcx, r15
0x180022ae7  cmovnb  rcx, rax
0x180022aeb  cmp     rcx, r8
0x180022aee  ja      loc_180022CB9
0x180022af4  imul    rsi, rcx, 0C8h
0x180022afb  test    rsi, rsi
0x180022afe  jnz     short loc_180022B04
0x180022b00  xor     ebx, ebx
0x180022b02  jmp     short loc_180022B41
0x180022b04  cmp     rsi, 1000h
0x180022b0b  jb      short loc_180022B36
0x180022b0d  lea     rcx, [rsi+27h]; Size
0x180022b11  cmp     rcx, rsi
0x180022b14  jbe     loc_180022CB9
0x180022b1a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022b1f  test    rax, rax
0x180022b22  jz      loc_180022C74
0x180022b28  lea     rbx, [rax+27h]
0x180022b2c  and     rbx, 0FFFFFFFFFFFFFFE0h
0x180022b30  mov     [rbx-8], rax
0x180022b34  jmp     short loc_180022B41
0x180022b36  mov     rcx, rsi; Size
0x180022b39  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022b3e  mov     rbx, rax
0x180022b41  movups  xmm0, xmmword ptr [r13+0]
0x180022b46  mov     rcx, r14
0x180022b49  mov     rax, 0A3D70A3D70A3D70Bh
0x180022b53  sub     rcx, rbp
0x180022b56  imul    rcx
0x180022b59  add     rdx, rcx
0x180022b5c  sar     rdx, 7
0x180022b60  mov     rcx, rdx
0x180022b63  shr     rcx, 3Fh
0x180022b67  add     rdx, rcx
0x180022b6a  mov     rcx, rbx; void *
0x180022b6d  imul    rbp, rdx, 0C8h
0x180022b74  add     rbp, rbx
0x180022b77  movups  xmmword ptr [rbp+0], xmm0
0x180022b7b  movups  xmm1, xmmword ptr [r13+10h]
0x180022b80  movups  xmmword ptr [rbp+10h], xmm1
0x180022b84  movups  xmm0, xmmword ptr [r13+20h]
0x180022b89  movups  xmmword ptr [rbp+20h], xmm0
0x180022b8d  movups  xmm1, xmmword ptr [r13+30h]
0x180022b92  movups  xmmword ptr [rbp+30h], xmm1
0x180022b96  movups  xmm0, xmmword ptr [r13+40h]
0x180022b9b  movups  xmmword ptr [rbp+40h], xmm0
0x180022b9f  movups  xmm1, xmmword ptr [r13+50h]
0x180022ba4  movups  xmmword ptr [rbp+50h], xmm1
0x180022ba8  movups  xmm0, xmmword ptr [r13+60h]
0x180022bad  movups  xmmword ptr [rbp+60h], xmm0
0x180022bb1  movups  xmm1, xmmword ptr [r13+70h]
0x180022bb6  movups  xmmword ptr [rbp+70h], xmm1
0x180022bba  movups  xmm0, xmmword ptr [r13+80h]
0x180022bc2  movups  xmmword ptr [rbp+80h], xmm0
0x180022bc9  movups  xmm1, xmmword ptr [r13+90h]
0x180022bd1  movups  xmmword ptr [rbp+90h], xmm1
0x180022bd8  movups  xmm0, xmmword ptr [r13+0A0h]
0x180022be0  movups  xmmword ptr [rbp+0A0h], xmm0
0x180022be7  movups  xmm1, xmmword ptr [r13+0B0h]
0x180022bef  movups  xmmword ptr [rbp+0B0h], xmm1
0x180022bf6  mov     rax, [r13+0C0h]
0x180022bfd  mov     [rbp+0C0h], rax
0x180022c04  mov     r8, [rdi+8]
0x180022c08  mov     rdx, [rdi]; Src
0x180022c0b  cmp     r14, r8
0x180022c0e  jnz     short loc_180022C15
0x180022c10  sub     r8, rdx
0x180022c13  jmp     short loc_180022C31
0x180022c15  mov     r8, r14
0x180022c18  sub     r8, [rdi]; Size
0x180022c1b  call    memmove_0
0x180022c20  mov     r8, [rdi+8]
0x180022c24  lea     rcx, [rbp+0C8h]; void *
0x180022c2b  sub     r8, r14; Size
0x180022c2e  mov     rdx, r14; Src
0x180022c31  call    memmove_0
0x180022c36  mov     rcx, [rdi]
0x180022c39  test    rcx, rcx
0x180022c3c  jz      short loc_180022C86
0x180022c3e  mov     rax, [rdi+10h]
0x180022c42  sub     rax, rcx
0x180022c45  sar     rax, 3
0x180022c49  imul    rax, r12
0x180022c4d  imul    rdx, rax, 0C8h
0x180022c54  cmp     rdx, 1000h
0x180022c5b  jb      short loc_180022C7B
0x180022c5d  mov     rax, [rcx-8]
0x180022c61  sub     rcx, rax
0x180022c64  sub     rcx, 8
0x180022c68  cmp     rcx, 1Fh
0x180022c6c  ja      short loc_180022C74
0x180022c6e  add     rdx, 27h ; '''
0x180022c72  jmp     short loc_180022C7E
0x180022c74  mov     ecx, 5
0x180022c79  int     29h; Win8: RtlFailFast(ecx)
0x180022c7b  mov     rax, rcx
0x180022c7e  mov     rcx, rax; Block
0x180022c81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022c86  mov     [rdi], rbx
0x180022c89  mov     rax, rbp
0x180022c8c  imul    rcx, r15, 0C8h
0x180022c93  add     rcx, rbx
0x180022c96  mov     [rdi+8], rcx
0x180022c9a  lea     rcx, [rsi+rbx]
0x180022c9e  mov     [rdi+10h], rcx
0x180022ca2  add     rsp, 28h
0x180022ca6  pop     r15
0x180022ca8  pop     r14
0x180022caa  pop     r13
0x180022cac  pop     r12
0x180022cae  pop     rdi
0x180022caf  pop     rsi
0x180022cb0  pop     rbp
0x180022cb1  pop     rbx
0x180022cb2  retn
0x180022cb3  call    ?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength(void)
0x180022cb9  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
