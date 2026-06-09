# CDetourDis::CopyVexEvexCommon(uchar,uchar *,uchar *,uchar)

- ea: `0x180032080`
- end: `0x1800321c0`
- name: `?CopyVexEvexCommon@CDetourDis@@IEAAPEAEEPEAE0E@Z`
- size: `320`
- prototype: `unsigned __int8 *__fastcall(CDetourDis *this, char, unsigned __int8 *, unsigned __int8 *, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180031c20`
- `0x180032010`

## callees

- `0x180030ef0`
- `0x180031540`
- `0x180032080`
- `0x18003bed0`

## pseudocode

```c
unsigned __int8 *__fastcall CDetourDis::CopyVexEvexCommon(
        CDetourDis *this,
        char a2,
        unsigned __int8 *a3,
        unsigned __int8 *a4,
        char a5)
{
  int v6; // [rsp+30h] [rbp-28h]

  v6 = a5 & 3;
  switch ( v6 )
  {
    case 1:
      *(_DWORD *)this = 1;
      break;
    case 2:
      *((_DWORD *)this + 6) = 1;
      break;
    case 3:
      *((_DWORD *)this + 5) = 1;
      break;
  }
  switch ( a2 )
  {
    case 1:
      return (unsigned __int8 *)(*((__int64 (__fastcall **)(CDetourDis *, const struct CDetourDis::COPYENTRY near *const *, unsigned __int8 *, unsigned __int8 *))&CDetourDis::s_rceCopyTable0F
                                 + 2 * *a4
                                 + 1))(
                                  this,
                                  &CDetourDis::s_rceCopyTable0F + 2 * *a4,
                                  a3,
                                  a4);
    case 2:
      return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&qword_180062190, a3, a4);
    case 3:
      return CDetourDis::CopyBytes(this, (const struct CDetourDis::COPYENTRY *)&qword_1800621A0, a3, a4);
  }
  return CDetourDis::Invalid(this, (const struct CDetourDis::COPYENTRY *)&qword_1800621B0, a3, a4);
}

```

## disassembly

```asm
0x180032080  mov     [rsp+arg_18], r9
0x180032085  mov     [rsp+arg_10], r8
0x18003208a  mov     [rsp+arg_8], dl
0x18003208e  mov     [rsp+arg_0], rcx
0x180032093  sub     rsp, 58h
0x180032097  movzx   eax, [rsp+58h+arg_20]
0x18003209f  and     eax, 3
0x1800320a2  mov     [rsp+58h+var_28], eax
0x1800320a6  cmp     [rsp+58h+var_28], 1
0x1800320ab  jz      short loc_1800320BF
0x1800320ad  cmp     [rsp+58h+var_28], 2
0x1800320b2  jz      short loc_1800320CC
0x1800320b4  cmp     [rsp+58h+var_28], 3
0x1800320b9  jz      short loc_1800320DA
0x1800320bb  jmp     short loc_1800320E6
0x1800320bd  jmp     short loc_1800320E6
0x1800320bf  mov     rax, [rsp+58h+arg_0]
0x1800320c4  mov     dword ptr [rax], 1
0x1800320ca  jmp     short loc_1800320E6
0x1800320cc  mov     rax, [rsp+58h+arg_0]
0x1800320d1  mov     dword ptr [rax+18h], 1
0x1800320d8  jmp     short loc_1800320E6
0x1800320da  mov     rax, [rsp+58h+arg_0]
0x1800320df  mov     dword ptr [rax+14h], 1
0x1800320e6  movzx   eax, [rsp+58h+arg_8]
0x1800320eb  mov     [rsp+58h+var_24], al
0x1800320ef  cmp     [rsp+58h+var_24], 1
0x1800320f4  jz      short loc_18003212C
0x1800320f6  cmp     [rsp+58h+var_24], 2
0x1800320fb  jz      loc_180032183
0x180032101  cmp     [rsp+58h+var_24], 3
0x180032106  jz      loc_1800321A0
0x18003210c  mov     r9, [rsp+58h+arg_18]; unsigned __int8 *
0x180032111  mov     r8, [rsp+58h+arg_10]; unsigned __int8 *
0x180032116  lea     rdx, qword_1800621B0; struct CDetourDis::COPYENTRY *
0x18003211d  mov     rcx, [rsp+58h+arg_0]; this
0x180032122  call    ?Invalid@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::Invalid(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x180032127  jmp     loc_1800321BB
0x18003212c  mov     eax, 1
0x180032131  imul    rax, 0
0x180032135  mov     rcx, [rsp+58h+arg_18]
0x18003213a  movzx   eax, byte ptr [rcx+rax]
0x18003213e  imul    rax, 10h
0x180032142  lea     rcx, ?s_rceCopyTable0F@CDetourDis@@1QBUCOPYENTRY@1@B; CDetourDis::COPYENTRY const near * const CDetourDis::s_rceCopyTable0F
0x180032149  add     rcx, rax
0x18003214c  mov     rax, rcx
0x18003214f  mov     [rsp+58h+var_20], rax
0x180032154  mov     rax, [rsp+58h+var_20]
0x180032159  mov     rax, [rax+8]
0x18003215d  mov     [rsp+58h+var_18], rax
0x180032162  mov     r9, [rsp+58h+arg_18]
0x180032167  mov     r8, [rsp+58h+arg_10]
0x18003216c  mov     rdx, [rsp+58h+var_20]
0x180032171  mov     rcx, [rsp+58h+arg_0]
0x180032176  mov     rax, [rsp+58h+var_18]
0x18003217b  call    cs:__guard_dispatch_icall_fptr
0x180032181  jmp     short loc_1800321BB
0x180032183  mov     r9, [rsp+58h+arg_18]; unsigned __int8 *
0x180032188  mov     r8, [rsp+58h+arg_10]; unsigned __int8 *
0x18003218d  lea     rdx, qword_180062190; struct CDetourDis::COPYENTRY *
0x180032194  mov     rcx, [rsp+58h+arg_0]; this
0x180032199  call    ?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x18003219e  jmp     short loc_1800321BB
0x1800321a0  mov     r9, [rsp+58h+arg_18]; unsigned __int8 *
0x1800321a5  mov     r8, [rsp+58h+arg_10]; unsigned __int8 *
0x1800321aa  lea     rdx, qword_1800621A0; struct CDetourDis::COPYENTRY *
0x1800321b1  mov     rcx, [rsp+58h+arg_0]; this
0x1800321b6  call    ?CopyBytes@CDetourDis@@IEAAPEAEPEBUCOPYENTRY@1@PEAE1@Z; CDetourDis::CopyBytes(CDetourDis::COPYENTRY const *,uchar *,uchar *)
0x1800321bb  add     rsp, 58h
0x1800321bf  retn
```
