# sub_1801BCFEC

- ea: `0x1801bcfec`
- end: `0x1801bd3a8`
- name: `sub_1801BCFEC`
- size: `956`
- prototype: `char *__fastcall(__int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x1801bd4cc`

## callees

- `0x18011b15c`
- `0x1801b7b08`
- `0x1801b8984`
- `0x1801ba0c8`
- `0x1801ba218`
- `0x1801bceb4`
- `0x1801bcfec`

## import_xrefs

- `VCRUNTIME140!longjmp` at `0x1801bd086`
- `VCRUNTIME140!longjmp` at `0x1801bd096`
- `VCRUNTIME140!longjmp` at `0x1801bd2aa`
- `VCRUNTIME140!longjmp` at `0x1801bd086`
- `VCRUNTIME140!longjmp` at `0x1801bd096`
- `VCRUNTIME140!longjmp` at `0x1801bd2aa`

## string_xrefs

- `0x1801bd0aa`: `UPDATE`

## pseudocode

```c
char *__fastcall sub_1801BCFEC(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rsi
  int v10; // eax
  const void **v11; // rdi
  int v12; // eax
  __int64 v13; // r15
  __int64 v14; // rax
  char *v15; // rcx
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // r12
  unsigned int *v18; // rax
  char *result; // rax
  __int64 v20; // rcx
  _WORD *v21; // r8
  int v22; // eax
  char *v23; // rcx
  int v24; // esi
  __int64 v25; // rdi
  __int64 v26; // rbp
  int v27; // [rsp+20h] [rbp-58h]
  unsigned int v28; // [rsp+28h] [rbp-50h]
  int v29; // [rsp+88h] [rbp+10h]
  __int64 v30; // [rsp+90h] [rbp+18h]
  unsigned int *v31; // [rsp+90h] [rbp+18h]
  void **v32; // [rsp+98h] [rbp+20h]

  v6 = *(_QWORD *)(a2 + 440);
  v30 = *(_QWORD *)(a4 + 32);
  v10 = *(_DWORD *)(a5 + 64);
  v29 = v10;
  if ( (*(_DWORD *)(a3 + 40) & 0x8000) != 0 )
  {
    if ( v10 <= 0 )
      longjmp(*(_JBTYPE **)(a1 + 32), -1003);
    v29 = v10 - 1;
  }
  *(_QWORD *)(a4 + 1880) = 0;
  v32 = (void **)(a4 + 1880);
  v11 = (const void **)(a4 + 1848);
  v12 = sub_18011B15C((_QWORD *)a3, 2u, 1, (void **)(a4 + 1848));
  if ( v12 < 0 )
    longjmp(*(_JBTYPE **)(a1 + 32), v12);
  sub_1801BA0C8((_QWORD *)a3, v11, L"UPDATE", L" ");
  sub_1801B7B08((_QWORD *)a3, v11, *(const wchar_t **)(a2 + 384), (wchar_t *)(v6 + 48));
  sub_1801BA0C8((_QWORD *)a3, v11, L" ", 0);
  sub_1801BA0C8((_QWORD *)a3, v11, L"SET", L" ");
  v13 = -1;
  if ( *v11 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)*v11 + v14) );
  }
  else
  {
    LOWORD(v14) = 0;
  }
  *(_WORD *)(a4 + 1856) = v14;
  v15 = byte_1801F6158;
  v16 = *(_QWORD *)(a2 + 8);
  v17 = v16 + 88LL * *(int *)(a2 + 16);
  if ( v16 < v17 )
  {
    v18 = (unsigned int *)(v30 + 16);
    v31 = (unsigned int *)(v30 + 16);
    do
    {
      if ( (*(_WORD *)(v16 + 80) & 0x100) != 0 )
      {
        if ( (*(_WORD *)(v16 + 80) & 0x200) != 0 )
        {
          sub_1801BA0C8((_QWORD *)a3, v11, v15, 0);
          sub_1801BA218((_QWORD *)a3, v11, (const void *)(*(_QWORD *)(a4 + 16) + 2LL * *v31), v31[1] & 0x7F, v27, v28);
          sub_1801BA0C8((_QWORD *)a3, v11, L"=", L"?");
          v18 = v31;
          v15 = (char *)L",";
        }
        v18 += 8;
        v31 = v18;
      }
      v16 += 88LL;
    }
    while ( v16 < v17 );
  }
  result = byte_1801F6158;
  if ( v15 == byte_1801F6158 )
  {
    *v11 = 0;
    return result;
  }
  if ( *v11 )
  {
    do
      ++v13;
    while ( *((_WORD *)*v11 + v13) );
  }
  else
  {
    LOWORD(v13) = 0;
  }
  *(_WORD *)(a4 + 1858) = v13;
  result = (char *)sub_1801BA0C8((_QWORD *)a3, v11, L" WHERE ", *(_WORD **)(a2 + 408));
  if ( *(_WORD *)(a1 + 232) != 4 )
  {
    v21 = *(_WORD **)(a2 + 432);
    if ( v21 )
      result = (char *)sub_1801BA0C8((_QWORD *)a3, v11, v21, 0);
    else
      result = (char *)sub_1801BCEB4(v20, a2, a3, a4, v11);
  }
  if ( (*(_BYTE *)(a3 + 120) & 0x10) != 0 && *(_DWORD *)(a3 + 252) == 4 )
  {
    v22 = sub_18011B15C((_QWORD *)a3, 2u, 1, v32);
    if ( v22 < 0 )
      longjmp(*(_JBTYPE **)(a1 + 32), v22);
    result = (char *)a5;
    v23 = byte_1801F6158;
    v24 = 0;
    v25 = *(_QWORD *)(a5 + 56);
    if ( v29 - 1 <= 0 )
      goto LABEL_42;
    v26 = 0;
    while ( 1 )
    {
      if ( (*(_DWORD *)v25 & 0x1FF) == 1 )
      {
        if ( (*(_DWORD *)(v25 + 24) & 0x1FF) != 2 )
        {
          *(_DWORD *)(a3 + 120) &= ~0x10u;
          *v32 = 0;
LABEL_41:
          result = byte_1801F6158;
          if ( v23 == byte_1801F6158 )
          {
LABEL_42:
            *(_DWORD *)(a3 + 120) &= ~0x10u;
            *v32 = 0;
          }
          return result;
        }
        sub_1801BA0C8((_QWORD *)a3, (const void **)v32, v23, 0);
        sub_1801BA0C8((_QWORD *)a3, (const void **)v32, *(_WORD **)(*(_QWORD *)(a5 + 80) + 8 * v26 + 8), L"=");
        sub_1801B8984(a1, *(_QWORD *)(*(_QWORD *)(v25 + 16) + 16LL), a3, (const void **)v32, 0, 0, 0);
        ++v24;
        v23 = (char *)L",";
        ++v26;
        v25 += 24;
      }
      ++v24;
      ++v26;
      v25 += 24;
      if ( v24 >= v29 - 1 )
        goto LABEL_41;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801bcfec  mov     [rsp+arg_0], rbx
0x1801bcff1  push    rbp
0x1801bcff2  push    rsi
0x1801bcff3  push    rdi
0x1801bcff4  push    r12
0x1801bcff6  push    r13
0x1801bcff8  push    r14
0x1801bcffa  push    r15
0x1801bcffc  sub     rsp, 40h
0x1801bd000  mov     rax, [r9+20h]
0x1801bd004  xor     r12d, r12d
0x1801bd007  test    dword ptr [r8+28h], 8000h
0x1801bd00f  mov     r14, r9
0x1801bd012  mov     rsi, [rdx+1B8h]
0x1801bd019  mov     rbx, r8
0x1801bd01c  mov     [rsp+78h+arg_10], rax
0x1801bd024  mov     rbp, rdx
0x1801bd027  mov     rax, [rsp+78h+arg_20]
0x1801bd02f  mov     r13, rcx
0x1801bd032  mov     eax, [rax+40h]
0x1801bd035  mov     [rsp+78h+arg_8], eax
0x1801bd03c  jz      short loc_1801BD04B
0x1801bd03e  test    eax, eax
0x1801bd040  jle     short loc_1801BD08D
0x1801bd042  dec     eax
0x1801bd044  mov     [rsp+78h+arg_8], eax
0x1801bd04b  lea     rax, [r9+758h]
0x1801bd052  mov     [r9+758h], r12
0x1801bd059  mov     edx, 2
0x1801bd05e  mov     [rsp+78h+arg_18], rax
0x1801bd066  lea     rdi, [r9+738h]
0x1801bd06d  mov     rcx, rbx
0x1801bd070  mov     r9, rdi
0x1801bd073  lea     r8d, [rdx-1]
0x1801bd077  call    sub_18011B15C
0x1801bd07c  test    eax, eax
0x1801bd07e  jns     short loc_1801BD09D
0x1801bd080  mov     rcx, [r13+20h]; Buf
0x1801bd084  mov     edx, eax; Value
0x1801bd086  call    cs:longjmp
0x1801bd08d  mov     rcx, [rcx+20h]; Buf
0x1801bd091  mov     edx, 0FFFFFC15h; Value
0x1801bd096  call    cs:longjmp
0x1801bd09d  lea     r15, asc_1801F615C; " "
0x1801bd0a4  mov     rdx, rdi
0x1801bd0a7  mov     r9, r15
0x1801bd0aa  lea     r8, aUpdate_0; "UPDATE"
0x1801bd0b1  mov     rcx, rbx; lpAddress
0x1801bd0b4  call    sub_1801BA0C8
0x1801bd0b9  mov     r8, [rbp+180h]
0x1801bd0c0  lea     r9, [rsi+30h]
0x1801bd0c4  mov     rdx, rdi
0x1801bd0c7  mov     rcx, rbx; lpAddress
0x1801bd0ca  call    sub_1801B7B08
0x1801bd0cf  xor     r9d, r9d
0x1801bd0d2  mov     r8, r15
0x1801bd0d5  mov     rdx, rdi
0x1801bd0d8  mov     rcx, rbx; lpAddress
0x1801bd0db  call    sub_1801BA0C8
0x1801bd0e0  mov     r9, r15
0x1801bd0e3  lea     r8, aSet_0; "SET"
0x1801bd0ea  mov     rdx, rdi
0x1801bd0ed  mov     rcx, rbx; lpAddress
0x1801bd0f0  call    sub_1801BA0C8
0x1801bd0f5  mov     rcx, [rdi]
0x1801bd0f8  or      r15, 0FFFFFFFFFFFFFFFFh
0x1801bd0fc  test    rcx, rcx
0x1801bd0ff  jz      short loc_1801BD110
0x1801bd101  mov     rax, r15
0x1801bd104  inc     rax
0x1801bd107  cmp     [rcx+rax*2], r12w
0x1801bd10c  jnz     short loc_1801BD104
0x1801bd10e  jmp     short loc_1801BD114
0x1801bd110  movzx   eax, r12w
0x1801bd114  mov     [r14+740h], ax
0x1801bd11c  lea     rcx, byte_1801F6158
0x1801bd123  mov     rsi, [rbp+8]
0x1801bd127  movsxd  rax, dword ptr [rbp+10h]
0x1801bd12b  imul    r12, rax, 58h ; 'X'
0x1801bd12f  add     r12, rsi
0x1801bd132  cmp     rsi, r12
0x1801bd135  jnb     loc_1801BD1DC
0x1801bd13b  mov     rax, [rsp+78h+arg_10]
0x1801bd143  add     rax, 10h
0x1801bd147  mov     [rsp+78h+arg_10], rax
0x1801bd14f  mov     edx, 100h
0x1801bd154  test    [rsi+50h], dx
0x1801bd158  jz      short loc_1801BD1CF
0x1801bd15a  mov     edx, 200h
0x1801bd15f  test    [rsi+50h], dx
0x1801bd163  jz      short loc_1801BD1C3
0x1801bd165  mov     r8, rcx
0x1801bd168  xor     r9d, r9d
0x1801bd16b  mov     rcx, rbx; lpAddress
0x1801bd16e  mov     rdx, rdi
0x1801bd171  call    sub_1801BA0C8
0x1801bd176  mov     rax, [rsp+78h+arg_10]
0x1801bd17e  mov     rdx, rdi
0x1801bd181  mov     ecx, [rax]
0x1801bd183  mov     r9d, [rax+4]
0x1801bd187  mov     rax, [r14+10h]
0x1801bd18b  and     r9d, 7Fh
0x1801bd18f  lea     r8, [rax+rcx*2]
0x1801bd193  mov     rcx, rbx; lpAddress
0x1801bd196  call    sub_1801BA218
0x1801bd19b  lea     r9, asc_1801F61F0; "?"
0x1801bd1a2  mov     rdx, rdi
0x1801bd1a5  lea     r8, asc_1801F6214; "="
0x1801bd1ac  mov     rcx, rbx; lpAddress
0x1801bd1af  call    sub_1801BA0C8
0x1801bd1b4  mov     rax, [rsp+78h+arg_10]
0x1801bd1bc  lea     rcx, asc_1801F6150; ","
0x1801bd1c3  add     rax, 20h ; ' '
0x1801bd1c7  mov     [rsp+78h+arg_10], rax
0x1801bd1cf  add     rsi, 58h ; 'X'
0x1801bd1d3  cmp     rsi, r12
0x1801bd1d6  jb      loc_1801BD14F
0x1801bd1dc  lea     rax, byte_1801F6158
0x1801bd1e3  cmp     rcx, rax
0x1801bd1e6  jnz     short loc_1801BD1F4
0x1801bd1e8  mov     qword ptr [rdi], 0
0x1801bd1ef  jmp     loc_1801BD390
0x1801bd1f4  mov     rax, [rdi]
0x1801bd1f7  xor     r12d, r12d
0x1801bd1fa  test    rax, rax
0x1801bd1fd  jz      short loc_1801BD20B
0x1801bd1ff  inc     r15
0x1801bd202  cmp     [rax+r15*2], r12w
0x1801bd207  jnz     short loc_1801BD1FF
0x1801bd209  jmp     short loc_1801BD20F
0x1801bd20b  movzx   r15d, r12w
0x1801bd20f  mov     [r14+742h], r15w
0x1801bd217  lea     r8, aWhere_0; " WHERE "
0x1801bd21e  mov     r9, [rbp+198h]
0x1801bd225  mov     rdx, rdi
0x1801bd228  mov     rcx, rbx; lpAddress
0x1801bd22b  call    sub_1801BA0C8
0x1801bd230  mov     esi, 4
0x1801bd235  cmp     [r13+0E8h], si
0x1801bd23d  jz      short loc_1801BD26E
0x1801bd23f  mov     r8, [rbp+1B0h]
0x1801bd246  test    r8, r8
0x1801bd249  jz      short loc_1801BD25B
0x1801bd24b  xor     r9d, r9d
0x1801bd24e  mov     rdx, rdi
0x1801bd251  mov     rcx, rbx; lpAddress
0x1801bd254  call    sub_1801BA0C8
0x1801bd259  jmp     short loc_1801BD26E
0x1801bd25b  mov     r9, r14
0x1801bd25e  mov     [rsp+78h+var_58], rdi
0x1801bd263  mov     r8, rbx
0x1801bd266  mov     rdx, rbp
0x1801bd269  call    sub_1801BCEB4
0x1801bd26e  test    byte ptr [rbx+78h], 10h
0x1801bd272  jz      loc_1801BD390
0x1801bd278  cmp     [rbx+0FCh], esi
0x1801bd27e  jnz     loc_1801BD390
0x1801bd284  mov     r15, [rsp+78h+arg_18]
0x1801bd28c  mov     edx, 2
0x1801bd291  mov     r9, r15
0x1801bd294  mov     rcx, rbx
0x1801bd297  lea     r8d, [rdx-1]
0x1801bd29b  call    sub_18011B15C
0x1801bd2a0  test    eax, eax
0x1801bd2a2  jns     short loc_1801BD2B1
0x1801bd2a4  mov     rcx, [r13+20h]; Buf
0x1801bd2a8  mov     edx, eax; Value
0x1801bd2aa  call    cs:longjmp
0x1801bd2b1  mov     rax, [rsp+78h+arg_20]
0x1801bd2b9  lea     rcx, byte_1801F6158
0x1801bd2c0  mov     r14d, [rsp+78h+arg_8]
0x1801bd2c8  mov     esi, r12d
0x1801bd2cb  dec     r14d
0x1801bd2ce  mov     rdi, [rax+38h]
0x1801bd2d2  test    r14d, r14d
0x1801bd2d5  jle     loc_1801BD389
0x1801bd2db  mov     rbp, r12
0x1801bd2de  mov     eax, [rdi]
0x1801bd2e0  and     eax, 1FFh
0x1801bd2e5  cmp     eax, 1
0x1801bd2e8  jnz     short loc_1801BD362
0x1801bd2ea  mov     eax, [rdi+18h]
0x1801bd2ed  and     eax, 1FFh
0x1801bd2f2  cmp     eax, 2
0x1801bd2f5  jnz     short loc_1801BD376
0x1801bd2f7  mov     r8, rcx
0x1801bd2fa  xor     r9d, r9d
0x1801bd2fd  mov     rcx, rbx; lpAddress
0x1801bd300  mov     rdx, r15
0x1801bd303  call    sub_1801BA0C8
0x1801bd308  mov     rax, [rsp+78h+arg_20]
0x1801bd310  lea     r9, asc_1801F6214; "="
0x1801bd317  mov     rdx, r15
0x1801bd31a  mov     rcx, rbx; lpAddress
0x1801bd31d  mov     r8, [rax+50h]
0x1801bd321  mov     r8, [r8+rbp*8+8]
0x1801bd326  call    sub_1801BA0C8
0x1801bd32b  mov     rdx, [rdi+10h]
0x1801bd32f  xor     eax, eax
0x1801bd331  mov     [rsp+78h+var_48], rax
0x1801bd336  mov     r9, r15
0x1801bd339  mov     [rsp+78h+var_50], rax
0x1801bd33e  mov     r8, rbx
0x1801bd341  mov     rcx, r13
0x1801bd344  mov     word ptr [rsp+78h+var_58], ax
0x1801bd349  mov     rdx, [rdx+10h]
0x1801bd34d  call    sub_1801B8984
0x1801bd352  inc     esi
0x1801bd354  lea     rcx, asc_1801F6150; ","
0x1801bd35b  inc     rbp
0x1801bd35e  add     rdi, 18h
0x1801bd362  inc     esi
0x1801bd364  inc     rbp
0x1801bd367  add     rdi, 18h
0x1801bd36b  cmp     esi, r14d
0x1801bd36e  jl      loc_1801BD2DE
0x1801bd374  jmp     short loc_1801BD37D
0x1801bd376  and     dword ptr [rbx+78h], 0FFFFFFEFh
0x1801bd37a  mov     [r15], r12
0x1801bd37d  lea     rax, byte_1801F6158
0x1801bd384  cmp     rcx, rax
0x1801bd387  jnz     short loc_1801BD390
0x1801bd389  and     dword ptr [rbx+78h], 0FFFFFFEFh
0x1801bd38d  mov     [r15], r12
0x1801bd390  mov     rbx, [rsp+78h+arg_0]
0x1801bd398  add     rsp, 40h
0x1801bd39c  pop     r15
0x1801bd39e  pop     r14
0x1801bd3a0  pop     r13
0x1801bd3a2  pop     r12
0x1801bd3a4  pop     rdi
0x1801bd3a5  pop     rsi
0x1801bd3a6  pop     rbp
0x1801bd3a7  retn
```
