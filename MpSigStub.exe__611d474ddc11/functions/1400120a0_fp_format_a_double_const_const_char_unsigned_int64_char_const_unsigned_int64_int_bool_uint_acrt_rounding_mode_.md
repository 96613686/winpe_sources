# fp_format_a(double const * const,char *,unsigned __int64,char * const,unsigned __int64,int,bool,uint,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x1400120a0`
- end: `0x140012437`
- name: `?fp_format_a@@YAHQEBNPEAD_KQEAD2H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `919`
- prototype: `__int64 __fastcall(__int64 *, _BYTE *, unsigned __int64, __int64, __int64, int Size, char, int, unsigned int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140012bbc`

## callees

- `0x140004614`
- `0x14000ad70`
- `0x1400120a0`
- `0x140012438`
- `0x140012aa4`
- `0x14001e2d0`
- `0x14001ec74`

## pseudocode

```c
__int64 __fastcall fp_format_a(
        __int64 *a1,
        _BYTE *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int Size,
        char a7,
        int a8,
        unsigned int a9,
        __crt_cached_ptd_host *a10)
{
  int v10; // edi
  _BYTE *v11; // rbx
  __int64 result; // rax
  _BYTE *v14; // rax
  char *v15; // r12
  __int64 v16; // r15
  _BYTE *v17; // rsi
  char v18; // al
  unsigned __int64 v19; // r10
  unsigned __int16 v20; // ax
  char *i; // rcx
  char v22; // dl
  _BYTE *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  char v26; // al
  _BYTE *v27; // r8

  *a2 = 0;
  v10 = 0;
  if ( Size >= 0 )
    v10 = Size;
  v11 = a2;
  if ( a3 <= v10 + 11 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 34;
    sub_140004614(0, 0, 0, 0, 0, a10);
    return 34;
  }
  if ( (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF )
  {
    if ( *a1 < 0 )
    {
      *a2 = 45;
      v11 = a2 + 1;
    }
    v15 = v11 + 1;
    v16 = 1023;
    if ( (*a1 & 0x7FF0000000000000LL) != 0 )
    {
      *v11 = 49;
    }
    else
    {
      *v11 = 48;
      v16 = (*a1 & 0xFFFFFFFFFFFFFLL) != 0 ? 0x3FE : 0;
    }
    v17 = v11 + 2;
    if ( v10 )
    {
      if ( !*((_BYTE *)a10 + 40) )
        __crt_cached_ptd_host::update_locale_slow(a10);
      v18 = ***(_BYTE ***)(*((_QWORD *)a10 + 3) + 248LL);
    }
    else
    {
      v18 = 0;
    }
    *v15 = v18;
    if ( (*a1 & 0xFFFFFFFFFFFFFLL) != 0 )
    {
      LODWORD(a2) = 48;
      v19 = 0xF000000000000LL;
      while ( v10 > 0 )
      {
        v20 = ((v19 & *a1 & 0xFFFFFFFFFFFFFLL) >> (char)a2) + 48;
        if ( v20 > 0x39u )
          LOBYTE(v20) = 32 * (a7 ^ 1) + 7 + v20;
        *v17 = v20;
        --v10;
        ++v17;
        v19 >>= 4;
        LOWORD(a2) = (_WORD)a2 - 4;
        if ( (__int16)a2 < 0 )
          goto LABEL_36;
      }
      if ( !(unsigned __int8)should_round_up(a1, v19, (unsigned __int16)a2, a9) )
      {
LABEL_38:
        if ( !*v15 )
          v17 = v11 + 1;
        *v17 = 32 * (a7 ^ 1) + 80;
        v23 = v17 + 2;
        v24 = (((unsigned __int64)*a1 >> 52) & 0x7FF) - v16;
        v25 = v24;
        if ( v24 < 0 )
          v24 = v16 - (((unsigned __int64)*a1 >> 52) & 0x7FF);
        v26 = 43;
        v27 = v17 + 2;
        if ( v25 < 0 )
          v26 = 45;
        v17[1] = v26;
        *v23 = 48;
        if ( v24 < 1000 )
        {
          if ( v24 < 100 )
          {
LABEL_48:
            if ( v24 < 10 )
            {
LABEL_50:
              *v27 = v24 + 48;
              v27[1] = 0;
              return 0;
            }
LABEL_49:
            *v27++ = v24 / 10 + 48;
            v24 %= 10;
            goto LABEL_50;
          }
        }
        else
        {
          v27 = v17 + 3;
          *v23 = v24 / 1000 + 48;
          v24 %= 1000;
        }
        *v27++ = v24 / 100 + 48;
        v24 %= 100;
        if ( v27 != v23 )
          goto LABEL_49;
        goto LABEL_48;
      }
      for ( i = v17 - 1; ; --i )
      {
        v22 = *i;
        if ( ((*i - 70) & 0xDF) != 0 )
          break;
        *i = 48;
      }
      if ( i == v15 )
      {
        ++*(i - 1);
      }
      else
      {
        if ( v22 == 57 )
          v22 = 32 * (a7 ^ 1) + 64;
        *i = v22 + 1;
      }
    }
LABEL_36:
    if ( v10 > 0 )
    {
      LOBYTE(a2) = 48;
      memset(v17, (int)a2, (unsigned int)v10);
      v17 += (unsigned int)v10;
    }
    goto LABEL_38;
  }
  result = sub_140012438(a1, a2, a3, a4, a5, v10, 0, a8, a9, a10);
  if ( (_DWORD)result )
  {
    *v11 = 0;
    return result;
  }
  v14 = (_BYTE *)sub_14001EC74(v11, 101);
  if ( v14 )
  {
    *v14 = 32 * (a7 ^ 1) + 80;
    v14[3] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400120a0  mov     [rsp+arg_0], rbx
0x1400120a5  mov     [rsp+arg_10], rbp
0x1400120aa  mov     [rsp+arg_18], rsi
0x1400120af  push    rdi
0x1400120b0  push    r12
0x1400120b2  push    r13
0x1400120b4  push    r14
0x1400120b6  push    r15
0x1400120b8  sub     rsp, 50h
0x1400120bc  mov     eax, dword ptr [rsp+78h+Size]
0x1400120c3  xor     r11d, r11d
0x1400120c6  test    eax, eax
0x1400120c8  mov     [rdx], r11b
0x1400120cb  mov     edi, r11d
0x1400120ce  mov     r10, r9
0x1400120d1  cmovns  edi, eax
0x1400120d4  mov     rbx, rdx
0x1400120d7  mov     r14, rcx
0x1400120da  lea     eax, [rdi+0Bh]
0x1400120dd  movsxd  r9, eax
0x1400120e0  cmp     r8, r9
0x1400120e3  ja      short loc_140012118
0x1400120e5  mov     rcx, [rsp+78h+arg_48]
0x1400120ed  lea     ebx, [r11+22h]
0x1400120f1  mov     [rsp+78h+var_50], rcx; __crt_cached_ptd_host *
0x1400120f6  xor     r9d, r9d; LineNo
0x1400120f9  xor     r8d, r8d; FileName
0x1400120fc  mov     [rsp+78h+var_58], r11; uintptr_t
0x140012101  xor     edx, edx; FunctionName
0x140012103  mov     byte ptr [rcx+30h], 1
0x140012107  mov     [rcx+2Ch], ebx
0x14001210a  xor     ecx, ecx; Expression
0x14001210c  call    sub_140004614
0x140012111  mov     eax, ebx
0x140012113  jmp     loc_140012419
0x140012118  mov     rax, [rcx]
0x14001211b  mov     ecx, 7FFh
0x140012120  shr     rax, 34h
0x140012124  and     rax, rcx
0x140012127  cmp     rax, rcx
0x14001212a  jnz     loc_1400121B1
0x140012130  mov     rax, [rsp+78h+arg_48]
0x140012138  mov     r9, r10
0x14001213b  mov     [rsp+78h+var_30], rax
0x140012140  mov     rcx, r14
0x140012143  mov     eax, [rsp+78h+arg_40]
0x14001214a  mov     [rsp+78h+var_38], eax
0x14001214e  mov     eax, [rsp+78h+arg_38]
0x140012155  mov     [rsp+78h+var_40], eax
0x140012159  mov     rax, [rsp+78h+arg_20]
0x140012161  mov     [rsp+78h+var_48], r11b
0x140012166  mov     dword ptr [rsp+78h+var_50], edi
0x14001216a  mov     [rsp+78h+var_58], rax
0x14001216f  call    sub_140012438
0x140012174  test    eax, eax
0x140012176  jz      short loc_140012180
0x140012178  mov     byte ptr [rbx], 0
0x14001217b  jmp     loc_140012419
0x140012180  mov     edx, 65h ; 'e'
0x140012185  mov     rcx, rbx
0x140012188  call    sub_14001EC74
0x14001218d  test    rax, rax
0x140012190  jz      loc_140012417
0x140012196  mov     cl, [rsp+78h+arg_30]
0x14001219d  xor     cl, 1
0x1400121a0  shl     cl, 5
0x1400121a3  add     cl, 50h ; 'P'
0x1400121a6  mov     [rax], cl
0x1400121a8  mov     byte ptr [rax+3], 0
0x1400121ac  jmp     loc_140012417
0x1400121b1  mov     eax, 2Dh ; '-'
0x1400121b6  cmp     [r14], r11
0x1400121b9  jge     short loc_1400121C0
0x1400121bb  mov     [rdx], al
0x1400121bd  inc     rbx
0x1400121c0  mov     al, [rsp+78h+arg_30]
0x1400121c7  lea     r12, [rbx+1]
0x1400121cb  xor     al, 1
0x1400121cd  mov     r15d, 3FFh
0x1400121d3  movzx   r13d, al
0x1400121d7  mov     r8d, 30h ; '0'
0x1400121dd  mov     ebp, r13d
0x1400121e0  mov     rax, 7FF0000000000000h
0x1400121ea  shl     ebp, 5
0x1400121ed  mov     r9, 0FFFFFFFFFFFFFh
0x1400121f7  add     ebp, 7
0x1400121fa  test    [r14], rax
0x1400121fd  jnz     short loc_140012217
0x1400121ff  mov     [rbx], r8b
0x140012202  mov     rax, [r14]
0x140012205  and     rax, r9
0x140012208  neg     rax
0x14001220b  sbb     r15, r15
0x14001220e  and     r15d, 3FEh
0x140012215  jmp     short loc_14001221A
0x140012217  mov     byte ptr [rbx], 31h ; '1'
0x14001221a  lea     rsi, [r12+1]
0x14001221f  test    edi, edi
0x140012221  jnz     short loc_140012228
0x140012223  mov     al, r11b
0x140012226  jmp     short loc_14001225F
0x140012228  mov     rbx, [rsp+78h+arg_48]
0x140012230  cmp     [rbx+28h], r11b
0x140012234  jnz     short loc_14001224F
0x140012236  mov     rcx, rbx; this
0x140012239  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x14001223e  xor     r11d, r11d
0x140012241  mov     r9, 0FFFFFFFFFFFFFh
0x14001224b  lea     r8d, [r11+30h]
0x14001224f  mov     rax, [rbx+18h]
0x140012253  mov     rcx, [rax+0F8h]
0x14001225a  mov     rax, [rcx]
0x14001225d  mov     al, [rax]
0x14001225f  mov     [r12], al
0x140012263  test    [r14], r9
0x140012266  jbe     loc_1400122F6
0x14001226c  movzx   edx, r8w
0x140012270  mov     r10, 0F000000000000h
0x14001227a  movzx   ecx, dx
0x14001227d  test    edi, edi
0x14001227f  jle     short loc_1400122AD
0x140012281  mov     rax, [r14]
0x140012284  and     rax, r10
0x140012287  and     rax, r9
0x14001228a  shr     rax, cl
0x14001228d  add     ax, r8w
0x140012291  cmp     ax, 39h ; '9'
0x140012295  jbe     short loc_14001229A
0x140012297  add     ax, bp
0x14001229a  mov     [rsi], al
0x14001229c  dec     edi
0x14001229e  inc     rsi
0x1400122a1  shr     r10, 4
0x1400122a5  add     dx, 0FFFCh
0x1400122a9  jns     short loc_14001227A
0x1400122ab  jmp     short loc_1400122F6
0x1400122ad  mov     r9d, [rsp+78h+arg_40]
0x1400122b5  movzx   r8d, cx
0x1400122b9  mov     rcx, r14
0x1400122bc  mov     rdx, r10
0x1400122bf  call    ?should_round_up@@YA_NQEBN_KFW4__acrt_rounding_mode@@@Z
0x1400122c4  xor     r11d, r11d
0x1400122c7  test    al, al
0x1400122c9  jz      short loc_140012317
0x1400122cb  lea     rcx, [rsi-1]
0x1400122cf  mov     dl, [rcx]
0x1400122d1  lea     eax, [rdx-46h]
0x1400122d4  test    al, 0DFh
0x1400122d6  jnz     short loc_1400122E0
0x1400122d8  mov     byte ptr [rcx], 30h ; '0'
0x1400122db  dec     rcx
0x1400122de  jmp     short loc_1400122CF
0x1400122e0  cmp     rcx, r12
0x1400122e3  jz      short loc_1400122F3
0x1400122e5  cmp     dl, 39h ; '9'
0x1400122e8  jnz     short loc_1400122ED
0x1400122ea  add     dl, bpl
0x1400122ed  inc     dl
0x1400122ef  mov     [rcx], dl
0x1400122f1  jmp     short loc_1400122F6
0x1400122f3  inc     byte ptr [rcx-1]
0x1400122f6  test    edi, edi
0x1400122f8  jle     short loc_140012317
0x1400122fa  mov     r8d, edi; Size
0x1400122fd  mov     rcx, rsi; Dst
0x140012300  mov     ebx, edi
0x140012302  mov     edi, 30h ; '0'
0x140012307  mov     dl, dil; Val
0x14001230a  call    memset
0x14001230f  add     rsi, rbx
0x140012312  xor     r11d, r11d
0x140012315  jmp     short loc_14001231C
0x140012317  mov     edi, 30h ; '0'
0x14001231c  cmp     [r12], r11b
0x140012320  cmovz   rsi, r12
0x140012324  shl     r13b, 5
0x140012328  add     r13b, 50h ; 'P'
0x14001232c  mov     [rsi], r13b
0x14001232f  lea     r9, [rsi+2]
0x140012333  mov     rax, [r14]
0x140012336  shr     rax, 34h
0x14001233a  and     eax, 7FFh
0x14001233f  mov     ecx, eax
0x140012341  sub     rcx, r15
0x140012344  mov     rdx, rcx
0x140012347  jns     short loc_14001234F
0x140012349  mov     rcx, r15
0x14001234c  sub     rcx, rax
0x14001234f  test    rdx, rdx
0x140012352  mov     eax, 2Bh ; '+'
0x140012357  mov     r8, r9
0x14001235a  lea     edx, [rax+2]
0x14001235d  cmovs   eax, edx
0x140012360  mov     [rsi+1], al
0x140012363  mov     [r9], dil
0x140012366  cmp     rcx, 3E8h
0x14001236d  jl      short loc_1400123A3
0x14001236f  mov     rax, 20C49BA5E353F7CFh
0x140012379  lea     r8, [r9+1]
0x14001237d  imul    rcx
0x140012380  sar     rdx, 7
0x140012384  mov     rax, rdx
0x140012387  shr     rax, 3Fh
0x14001238b  add     rdx, rax
0x14001238e  lea     eax, [rdi+rdx]
0x140012391  mov     [r9], al
0x140012394  imul    rax, rdx, 0FFFFFFFFFFFFFC18h
0x14001239b  add     rcx, rax
0x14001239e  cmp     r8, r9
0x1400123a1  jnz     short loc_1400123A9
0x1400123a3  cmp     rcx, 64h ; 'd'
0x1400123a7  jl      short loc_1400123DC
0x1400123a9  mov     rax, 0A3D70A3D70A3D70Bh
0x1400123b3  imul    rcx
0x1400123b6  add     rdx, rcx
0x1400123b9  sar     rdx, 6
0x1400123bd  mov     rax, rdx
0x1400123c0  shr     rax, 3Fh
0x1400123c4  add     rdx, rax
0x1400123c7  lea     eax, [rdi+rdx]
0x1400123ca  mov     [r8], al
0x1400123cd  inc     r8
0x1400123d0  imul    rax, rdx, -64h
0x1400123d4  add     rcx, rax
0x1400123d7  cmp     r8, r9
0x1400123da  jnz     short loc_1400123E2
0x1400123dc  cmp     rcx, 0Ah
0x1400123e0  jl      short loc_14001240D
0x1400123e2  mov     rax, 6666666666666667h
0x1400123ec  imul    rcx
0x1400123ef  sar     rdx, 2
0x1400123f3  mov     rax, rdx
0x1400123f6  shr     rax, 3Fh
0x1400123fa  add     rdx, rax
0x1400123fd  lea     eax, [rdi+rdx]
0x140012400  mov     [r8], al
0x140012403  inc     r8
0x140012406  imul    rax, rdx, -0Ah
0x14001240a  add     rcx, rax
0x14001240d  add     cl, dil
0x140012410  mov     [r8], cl
0x140012413  mov     [r8+1], r11b
0x140012417  xor     eax, eax
0x140012419  lea     r11, [rsp+78h+var_28]
0x14001241e  mov     rbx, [r11+30h]
0x140012422  mov     rbp, [r11+40h]
0x140012426  mov     rsi, [r11+48h]
0x14001242a  mov     rsp, r11
0x14001242d  pop     r15
0x14001242f  pop     r14
0x140012431  pop     r13
0x140012433  pop     r12
0x140012435  pop     rdi
0x140012436  retn
```
