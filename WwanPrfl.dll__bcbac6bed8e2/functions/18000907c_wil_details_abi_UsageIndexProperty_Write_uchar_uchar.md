# wil::details_abi::UsageIndexProperty::Write(uchar * &,uchar *)

- ea: `0x18000907c`
- end: `0x180009164`
- name: `?Write@UsageIndexProperty@details_abi@wil@@QEBA_NAEAPEAEPEAE@Z`
- size: `232`
- prototype: `bool __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned __int8 **, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006c48`

## callees

- `0x180001fca`
- `0x18000907c`
- `0x18000e674`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090df`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800090df`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndexProperty::Write(
        wil::details_abi::UsageIndexProperty *this,
        unsigned __int8 **a2,
        unsigned __int8 *a3)
{
  char v3; // al
  unsigned __int8 *v4; // r9
  unsigned __int8 *v8; // rbx
  _DWORD *v9; // rax
  unsigned __int16 *v10; // rbp
  rsize_t v11; // r9
  bool result; // al

  v3 = *((_BYTE *)this + 2);
  v4 = *a2;
  if ( v3 == 1 )
  {
    v8 = v4 + 2;
    if ( v4 + 2 > a3 )
      return 0;
    if ( v4 )
    {
      *(_WORD *)v4 = *((_WORD *)this + 2);
      goto LABEL_13;
    }
LABEL_11:
    *(_DWORD *)_o__errno(this, a2, a3) = 22;
    invalid_parameter_noinfo();
    goto LABEL_13;
  }
  if ( v3 == 2 )
  {
    v8 = v4 + 4;
    if ( v4 + 4 > a3 )
      return 0;
    if ( v4 )
    {
      v9 = (_DWORD *)((char *)this + 4);
      if ( this != (wil::details_abi::UsageIndexProperty *)-4LL )
      {
        *(_DWORD *)v4 = *v9;
        goto LABEL_13;
      }
      *(_DWORD *)v4 = (_DWORD)v9;
    }
    goto LABEL_11;
  }
  v8 = *a2;
LABEL_13:
  if ( !*(_WORD *)this )
  {
    if ( v8 + 2 <= a3 )
    {
      v10 = (unsigned __int16 *)((char *)this + 8);
      memcpy_s_0(v8, a3 - v8, (char *)this + 8, 2u);
      v8 += 2;
      goto LABEL_17;
    }
    return 0;
  }
  v10 = (unsigned __int16 *)((char *)this + 8);
LABEL_17:
  v11 = *v10;
  if ( &v8[v11] > a3 )
    return 0;
  memcpy_s_0(v8, a3 - v8, *((const void *const *)this + 3), v11);
  result = 1;
  *a2 = &v8[*v10];
  return result;
}

```

## disassembly

```asm
0x18000907c  push    rbx
0x18000907e  push    rbp
0x18000907f  push    rsi
0x180009080  push    rdi
0x180009081  push    r14
0x180009083  push    r15
0x180009085  sub     rsp, 28h
0x180009089  mov     al, [rcx+2]
0x18000908c  xor     ebp, ebp
0x18000908e  mov     r9, [rdx]
0x180009091  mov     rdi, r8
0x180009094  mov     r15, rdx
0x180009097  mov     rsi, rcx
0x18000909a  cmp     al, 1
0x18000909c  jnz     short loc_1800090BA
0x18000909e  lea     rbx, [r9+2]
0x1800090a2  cmp     rbx, r8
0x1800090a5  ja      loc_180009135
0x1800090ab  test    r9, r9
0x1800090ae  jz      short loc_1800090DF
0x1800090b0  movzx   eax, word ptr [rcx+4]
0x1800090b4  mov     [r9], ax
0x1800090b8  jmp     short loc_1800090F5
0x1800090ba  cmp     al, 2
0x1800090bc  jnz     short loc_1800090F2
0x1800090be  lea     rbx, [r9+4]
0x1800090c2  cmp     rbx, rdi
0x1800090c5  ja      short loc_180009135
0x1800090c7  test    r9, r9
0x1800090ca  jz      short loc_1800090DF
0x1800090cc  lea     rax, [rcx+4]
0x1800090d0  test    rax, rax
0x1800090d3  jz      short loc_1800090DC
0x1800090d5  mov     eax, [rax]
0x1800090d7  mov     [r9], eax
0x1800090da  jmp     short loc_1800090F5
0x1800090dc  mov     [r9], eax
0x1800090df  call    cs:__imp__o__errno
0x1800090e5  mov     dword ptr [rax], 16h
0x1800090eb  call    _invalid_parameter_noinfo
0x1800090f0  jmp     short loc_1800090F5
0x1800090f2  mov     rbx, r9
0x1800090f5  cmp     [rsi], bp
0x1800090f8  jnz     short loc_180009123
0x1800090fa  lea     r14, [rbx+2]
0x1800090fe  cmp     r14, rdi
0x180009101  ja      short loc_180009135
0x180009103  lea     rbp, [rsi+8]
0x180009107  mov     rdx, rdi
0x18000910a  sub     rdx, rbx; DestinationSize
0x18000910d  mov     r8, rbp; Source
0x180009110  mov     r9d, 2; SourceSize
0x180009116  mov     rcx, rbx; Destination
0x180009119  call    memcpy_s_0
0x18000911e  mov     rbx, r14
0x180009121  jmp     short loc_180009127
0x180009123  lea     rbp, [rsi+8]
0x180009127  movzx   r9d, word ptr [rbp+0]; SourceSize
0x18000912c  lea     rax, [r9+rbx]
0x180009130  cmp     rax, rdi
0x180009133  jbe     short loc_180009139
0x180009135  xor     al, al
0x180009137  jmp     short loc_180009157
0x180009139  mov     r8, [rsi+18h]; Source
0x18000913d  sub     rdi, rbx
0x180009140  mov     rdx, rdi; DestinationSize
0x180009143  mov     rcx, rbx; Destination
0x180009146  call    memcpy_s_0
0x18000914b  movzx   ecx, word ptr [rbp+0]
0x18000914f  mov     al, 1
0x180009151  add     rcx, rbx
0x180009154  mov     [r15], rcx
0x180009157  add     rsp, 28h
0x18000915b  pop     r15
0x18000915d  pop     r14
0x18000915f  pop     rdi
0x180009160  pop     rsi
0x180009161  pop     rbp
0x180009162  pop     rbx
0x180009163  retn
```
