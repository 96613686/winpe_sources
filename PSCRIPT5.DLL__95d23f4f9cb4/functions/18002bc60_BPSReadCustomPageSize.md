# BPSReadCustomPageSize

- ea: `0x18002bc60`
- end: `0x18002be1b`
- name: `BPSReadCustomPageSize`
- size: `443`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18002aed0`
- `0x18002c8d0`

## callees

- `0x180001ee0`
- `0x180002830`
- `0x18002bc60`
- `0x18005c434`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18002bd0d`
- `KERNEL32!MulDiv` at `0x18002bd0d`

## pseudocode

```c
_BOOL8 __fastcall BPSReadCustomPageSize(__int64 a1, int a2, char *a3, int a4, _DWORD *a5)
{
  int v5; // r13d
  __int64 v6; // rbx
  int v7; // esi
  char *v8; // rdi
  int v9; // ebp
  __int64 v10; // r12
  int v11; // r9d
  unsigned int v12; // eax
  __int64 v13; // r15
  int v14; // r14d
  char **v15; // rax
  char *v16; // rdx
  unsigned int v17; // r14d
  _BYTE Src[16]; // [rsp+28h] [rbp-50h] BYREF

  v5 = 0;
  v6 = a1 + *(unsigned __int16 *)(a1 + 68);
  v7 = a4;
  v8 = a3;
  if ( a2 )
  {
    if ( a3 && a4 >= 16 )
    {
      v8 = a3 + 16;
      *(_OWORD *)a3 = kstrPSFCustomPS;
    }
    v7 = a4 - 16;
    v5 = 16;
  }
  v9 = 0;
  v10 = -1;
  do
  {
    v11 = 0;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v11 = *(_DWORD *)(v6 + 156);
      }
      else if ( (unsigned int)(v9 - 2) <= 1 )
      {
        v11 = *(_DWORD *)(v6 + 160);
      }
    }
    else
    {
      v11 = *(_DWORD *)(v6 + 152);
    }
    v12 = MulDiv(v11, 72, 25400);
    o__ultoa_s_0(v12, Src, 16, 10);
    v13 = -1;
    do
      ++v13;
    while ( Src[v13] );
    v14 = v13 + 1;
    if ( v8 && v7 >= v14 )
    {
      memcpy_0(v8, Src, (unsigned int)v14);
      v8[(unsigned int)v13] = 32;
      v8 += (unsigned int)v13 + 1;
    }
    v7 -= v14;
    v5 += v14;
    ++v9;
  }
  while ( v9 < 4 );
  if ( "LongEdge" )
  {
    v15 = &off_180060120;
    while ( *(unsigned __int16 *)(v6 + 168) != *((_DWORD *)v15 + 2) )
    {
      v15 += 2;
      if ( !*v15 )
        goto LABEL_23;
    }
  }
  else
  {
LABEL_23:
    v15 = &off_180060120;
  }
  v16 = *v15;
  do
    ++v10;
  while ( v16[v10] );
  v17 = v10 + 1;
  if ( v8 && v7 >= (int)v17 )
  {
    memcpy_0(v8, v16, v17);
    v8 += v17;
  }
  if ( a5 )
    *a5 = v17 + v5;
  return v8 && (int)(v7 - v17) >= 0;
}

```

## disassembly

```asm
0x18002bc60  mov     [rsp+arg_8], rbx
0x18002bc65  push    rbp
0x18002bc66  push    rsi
0x18002bc67  push    rdi
0x18002bc68  push    r12
0x18002bc6a  push    r13
0x18002bc6c  push    r14
0x18002bc6e  push    r15
0x18002bc70  sub     rsp, 40h
0x18002bc74  mov     rax, cs:__security_cookie
0x18002bc7b  xor     rax, rsp
0x18002bc7e  mov     [rsp+78h+var_40], rax
0x18002bc83  movzx   ebx, word ptr [rcx+44h]
0x18002bc87  xor     r13d, r13d
0x18002bc8a  mov     rax, [rsp+78h+arg_20]
0x18002bc92  add     rbx, rcx
0x18002bc95  mov     [rsp+78h+var_58], rax
0x18002bc9a  mov     esi, r9d
0x18002bc9d  mov     rdi, r8
0x18002bca0  test    edx, edx
0x18002bca2  jz      short loc_18002BCC8
0x18002bca4  test    r8, r8
0x18002bca7  jz      short loc_18002BCBF
0x18002bca9  cmp     r9d, 10h
0x18002bcad  jl      short loc_18002BCBF
0x18002bcaf  movups  xmm0, cs:kstrPSFCustomPS
0x18002bcb6  add     rdi, 10h
0x18002bcba  movdqu  xmmword ptr [r8], xmm0
0x18002bcbf  sub     esi, 10h
0x18002bcc2  mov     r13d, 10h
0x18002bcc8  xor     ebp, ebp
0x18002bcca  or      r12, 0FFFFFFFFFFFFFFFFh
0x18002bcce  xor     r9d, r9d
0x18002bcd1  mov     ecx, ebp
0x18002bcd3  test    ebp, ebp
0x18002bcd5  jz      short loc_18002BCF8
0x18002bcd7  sub     ecx, 1
0x18002bcda  jz      short loc_18002BCEF
0x18002bcdc  sub     ecx, 1
0x18002bcdf  jz      short loc_18002BCE6
0x18002bce1  cmp     ecx, 1
0x18002bce4  jnz     short loc_18002BCFF
0x18002bce6  mov     r9d, [rbx+0A0h]
0x18002bced  jmp     short loc_18002BCFF
0x18002bcef  mov     r9d, [rbx+9Ch]
0x18002bcf6  jmp     short loc_18002BCFF
0x18002bcf8  mov     r9d, [rbx+98h]
0x18002bcff  mov     edx, 48h ; 'H'; nNumerator
0x18002bd04  mov     r8d, 6338h; nDenominator
0x18002bd0a  mov     ecx, r9d; nNumber
0x18002bd0d  call    cs:__imp_MulDiv
0x18002bd13  mov     r9d, 0Ah
0x18002bd19  lea     rdx, [rsp+78h+Src]
0x18002bd1e  mov     ecx, eax
0x18002bd20  lea     r8d, [r9+6]
0x18002bd24  call    _o__ultoa_s_0
0x18002bd29  lea     rax, [rsp+78h+Src]
0x18002bd2e  mov     r15, r12
0x18002bd31  inc     r15
0x18002bd34  cmp     byte ptr [rax+r15], 0
0x18002bd39  jnz     short loc_18002BD31
0x18002bd3b  lea     r14d, [r15+1]
0x18002bd3f  test    rdi, rdi
0x18002bd42  jz      short loc_18002BD66
0x18002bd44  cmp     esi, r14d
0x18002bd47  jl      short loc_18002BD66
0x18002bd49  mov     r8d, r14d; Size
0x18002bd4c  lea     rdx, [rsp+78h+Src]; Src
0x18002bd51  mov     rcx, rdi; void *
0x18002bd54  call    memcpy_0
0x18002bd59  mov     ecx, r15d
0x18002bd5c  mov     byte ptr [rcx+rdi], 20h ; ' '
0x18002bd60  inc     rdi
0x18002bd63  add     rdi, rcx
0x18002bd66  sub     esi, r14d
0x18002bd69  add     r13d, r14d
0x18002bd6c  inc     ebp
0x18002bd6e  cmp     ebp, 4
0x18002bd71  jl      loc_18002BCCE
0x18002bd77  cmp     cs:off_180060120, 0; "LongEdge"
0x18002bd7f  jz      short loc_18002BD9E
0x18002bd81  movzx   ecx, word ptr [rbx+0A8h]
0x18002bd88  lea     rax, off_180060120; "LongEdge"
0x18002bd8f  cmp     ecx, [rax+8]
0x18002bd92  jz      short loc_18002BDA5
0x18002bd94  add     rax, 10h
0x18002bd98  cmp     qword ptr [rax], 0
0x18002bd9c  jnz     short loc_18002BD8F
0x18002bd9e  lea     rax, off_180060120; "LongEdge"
0x18002bda5  mov     rdx, [rax]; Src
0x18002bda8  inc     r12
0x18002bdab  cmp     byte ptr [rdx+r12], 0
0x18002bdb0  jnz     short loc_18002BDA8
0x18002bdb2  lea     r14d, [r12+1]
0x18002bdb7  test    rdi, rdi
0x18002bdba  jz      short loc_18002BDD2
0x18002bdbc  cmp     esi, r14d
0x18002bdbf  jl      short loc_18002BDD2
0x18002bdc1  mov     r8d, r14d; Size
0x18002bdc4  mov     rcx, rdi; void *
0x18002bdc7  mov     ebx, r14d
0x18002bdca  call    memcpy_0
0x18002bdcf  add     rdi, rbx
0x18002bdd2  mov     rcx, [rsp+78h+var_58]
0x18002bdd7  test    rcx, rcx
0x18002bdda  jz      short loc_18002BDE2
0x18002bddc  lea     eax, [r14+r13]
0x18002bde0  mov     [rcx], eax
0x18002bde2  test    rdi, rdi
0x18002bde5  jz      short loc_18002BDF4
0x18002bde7  cmp     esi, r14d
0x18002bdea  mov     eax, 0
0x18002bdef  setns   al
0x18002bdf2  jmp     short loc_18002BDF6
0x18002bdf4  xor     eax, eax
0x18002bdf6  mov     rcx, [rsp+78h+var_40]
0x18002bdfb  xor     rcx, rsp; StackCookie
0x18002bdfe  call    __security_check_cookie
0x18002be03  mov     rbx, [rsp+78h+arg_8]
0x18002be0b  add     rsp, 40h
0x18002be0f  pop     r15
0x18002be11  pop     r14
0x18002be13  pop     r13
0x18002be15  pop     r12
0x18002be17  pop     rdi
0x18002be18  pop     rsi
0x18002be19  pop     rbp
0x18002be1a  retn
```
