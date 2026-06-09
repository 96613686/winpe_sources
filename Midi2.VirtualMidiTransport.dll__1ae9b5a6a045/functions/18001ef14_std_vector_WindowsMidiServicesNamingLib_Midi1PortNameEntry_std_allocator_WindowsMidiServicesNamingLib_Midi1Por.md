# std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry,std::allocator<WindowsMidiServicesNamingLib::Midi1PortNameEntry>>::_Emplace_reallocate<WindowsMidiServicesNamingLib::Midi1PortNameEntry>(WindowsMidiServicesNamingLib::Midi1PortNameEntry * const,WindowsMidiServicesNamingLib::Midi1PortNameEntry &&)

- ea: `0x18001ef14`
- end: `0x18001f167`
- name: `??$_Emplace_reallocate@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@AEAAPEAUMidi1PortNameEntry@WindowsMidiServicesNamingLib@@QEAU23@$$QEAU23@@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task`

## callers

- `0x18001f340`

## callees

- `0x180003914`
- `0x180003940`
- `0x180004694`
- `0x180011a24`
- `0x180011a64`
- `0x18001ef14`

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
0x18001ef14  push    rbx
0x18001ef16  push    rbp
0x18001ef17  push    rsi
0x18001ef18  push    rdi
0x18001ef19  push    r12
0x18001ef1b  push    r13
0x18001ef1d  push    r14
0x18001ef1f  push    r15
0x18001ef21  sub     rsp, 28h
0x18001ef25  mov     rbp, [rcx]
0x18001ef28  mov     r12, 8F5C28F5C28F5C29h
0x18001ef32  mov     r9, [rcx+8]
0x18001ef36  mov     r13, r8
0x18001ef39  sub     r9, rbp
0x18001ef3c  mov     r8, 147AE147AE147AEh
0x18001ef46  sar     r9, 3
0x18001ef4a  mov     r14, rdx
0x18001ef4d  imul    r9, r12
0x18001ef51  mov     rdi, rcx
0x18001ef54  cmp     r9, r8
0x18001ef57  jz      loc_18001F15B
0x18001ef5d  mov     rcx, [rcx+10h]
0x18001ef61  mov     rax, r8
0x18001ef64  sub     rcx, rbp
0x18001ef67  sar     rcx, 3
0x18001ef6b  imul    rcx, r12
0x18001ef6f  mov     rdx, rcx
0x18001ef72  shr     rdx, 1
0x18001ef75  sub     rax, rdx
0x18001ef78  cmp     rcx, rax
0x18001ef7b  ja      loc_18001F161
0x18001ef81  lea     rax, [rcx+rdx]
0x18001ef85  lea     r15, [r9+1]
0x18001ef89  cmp     rax, r15
0x18001ef8c  mov     rcx, r15
0x18001ef8f  cmovnb  rcx, rax
0x18001ef93  cmp     rcx, r8
0x18001ef96  ja      loc_18001F161
0x18001ef9c  imul    rsi, rcx, 0C8h
0x18001efa3  test    rsi, rsi
0x18001efa6  jnz     short loc_18001EFAC
0x18001efa8  xor     ebx, ebx
0x18001efaa  jmp     short loc_18001EFE9
0x18001efac  cmp     rsi, 1000h
0x18001efb3  jb      short loc_18001EFDE
0x18001efb5  lea     rcx, [rsi+27h]; Size
0x18001efb9  cmp     rcx, rsi
0x18001efbc  jbe     loc_18001F161
0x18001efc2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001efc7  test    rax, rax
0x18001efca  jz      loc_18001F11C
0x18001efd0  lea     rbx, [rax+27h]
0x18001efd4  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18001efd8  mov     [rbx-8], rax
0x18001efdc  jmp     short loc_18001EFE9
0x18001efde  mov     rcx, rsi; Size
0x18001efe1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001efe6  mov     rbx, rax
0x18001efe9  movups  xmm0, xmmword ptr [r13+0]
0x18001efee  mov     rcx, r14
0x18001eff1  mov     rax, 0A3D70A3D70A3D70Bh
0x18001effb  sub     rcx, rbp
0x18001effe  imul    rcx
0x18001f001  add     rdx, rcx
0x18001f004  sar     rdx, 7
0x18001f008  mov     rcx, rdx
0x18001f00b  shr     rcx, 3Fh
0x18001f00f  add     rdx, rcx
0x18001f012  mov     rcx, rbx; void *
0x18001f015  imul    rbp, rdx, 0C8h
0x18001f01c  add     rbp, rbx
0x18001f01f  movups  xmmword ptr [rbp+0], xmm0
0x18001f023  movups  xmm1, xmmword ptr [r13+10h]
0x18001f028  movups  xmmword ptr [rbp+10h], xmm1
0x18001f02c  movups  xmm0, xmmword ptr [r13+20h]
0x18001f031  movups  xmmword ptr [rbp+20h], xmm0
0x18001f035  movups  xmm1, xmmword ptr [r13+30h]
0x18001f03a  movups  xmmword ptr [rbp+30h], xmm1
0x18001f03e  movups  xmm0, xmmword ptr [r13+40h]
0x18001f043  movups  xmmword ptr [rbp+40h], xmm0
0x18001f047  movups  xmm1, xmmword ptr [r13+50h]
0x18001f04c  movups  xmmword ptr [rbp+50h], xmm1
0x18001f050  movups  xmm0, xmmword ptr [r13+60h]
0x18001f055  movups  xmmword ptr [rbp+60h], xmm0
0x18001f059  movups  xmm1, xmmword ptr [r13+70h]
0x18001f05e  movups  xmmword ptr [rbp+70h], xmm1
0x18001f062  movups  xmm0, xmmword ptr [r13+80h]
0x18001f06a  movups  xmmword ptr [rbp+80h], xmm0
0x18001f071  movups  xmm1, xmmword ptr [r13+90h]
0x18001f079  movups  xmmword ptr [rbp+90h], xmm1
0x18001f080  movups  xmm0, xmmword ptr [r13+0A0h]
0x18001f088  movups  xmmword ptr [rbp+0A0h], xmm0
0x18001f08f  movups  xmm1, xmmword ptr [r13+0B0h]
0x18001f097  movups  xmmword ptr [rbp+0B0h], xmm1
0x18001f09e  mov     rax, [r13+0C0h]
0x18001f0a5  mov     [rbp+0C0h], rax
0x18001f0ac  mov     r8, [rdi+8]
0x18001f0b0  mov     rdx, [rdi]; Src
0x18001f0b3  cmp     r14, r8
0x18001f0b6  jnz     short loc_18001F0BD
0x18001f0b8  sub     r8, rdx
0x18001f0bb  jmp     short loc_18001F0D9
0x18001f0bd  mov     r8, r14
0x18001f0c0  sub     r8, [rdi]; Size
0x18001f0c3  call    memmove_0
0x18001f0c8  mov     r8, [rdi+8]
0x18001f0cc  lea     rcx, [rbp+0C8h]; void *
0x18001f0d3  sub     r8, r14; Size
0x18001f0d6  mov     rdx, r14; Src
0x18001f0d9  call    memmove_0
0x18001f0de  mov     rcx, [rdi]
0x18001f0e1  test    rcx, rcx
0x18001f0e4  jz      short loc_18001F12E
0x18001f0e6  mov     rax, [rdi+10h]
0x18001f0ea  sub     rax, rcx
0x18001f0ed  sar     rax, 3
0x18001f0f1  imul    rax, r12
0x18001f0f5  imul    rdx, rax, 0C8h
0x18001f0fc  cmp     rdx, 1000h
0x18001f103  jb      short loc_18001F123
0x18001f105  mov     rax, [rcx-8]
0x18001f109  sub     rcx, rax
0x18001f10c  sub     rcx, 8
0x18001f110  cmp     rcx, 1Fh
0x18001f114  ja      short loc_18001F11C
0x18001f116  add     rdx, 27h ; '''
0x18001f11a  jmp     short loc_18001F126
0x18001f11c  mov     ecx, 5
0x18001f121  int     29h; Win8: RtlFailFast(ecx)
0x18001f123  mov     rax, rcx
0x18001f126  mov     rcx, rax; Block
0x18001f129  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f12e  mov     [rdi], rbx
0x18001f131  mov     rax, rbp
0x18001f134  imul    rcx, r15, 0C8h
0x18001f13b  add     rcx, rbx
0x18001f13e  mov     [rdi+8], rcx
0x18001f142  lea     rcx, [rsi+rbx]
0x18001f146  mov     [rdi+10h], rcx
0x18001f14a  add     rsp, 28h
0x18001f14e  pop     r15
0x18001f150  pop     r14
0x18001f152  pop     r13
0x18001f154  pop     r12
0x18001f156  pop     rdi
0x18001f157  pop     rsi
0x18001f158  pop     rbp
0x18001f159  pop     rbx
0x18001f15a  retn
0x18001f15b  call    ?_Xlength@?$vector@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@V?$allocator@UMidi1PortNameEntry@WindowsMidiServicesNamingLib@@@std@@@std@@CAXXZ; std::vector<WindowsMidiServicesNamingLib::Midi1PortNameEntry>::_Xlength(void)
0x18001f161  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
