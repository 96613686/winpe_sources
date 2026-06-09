# fp_format_a

- ea: `0x180056f34`
- end: `0x1800572c7`
- name: `fp_format_a`
- size: `915`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, __int64, size_t Size, char, int, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180057b24`

## callees

- `0x1800073e8`
- `0x1800149cc`
- `0x180056f34`
- `0x1800572c8`
- `0x180057a04`
- `0x18005ff94`
- `0x180060270`

## pseudocode

```c
__int64 __fastcall fp_format_a(
        __int64 *a1,
        char *Str,
        unsigned __int64 a3,
        int a4,
        __int64 a5,
        size_t Size,
        char a7,
        int a8,
        unsigned int a9,
        __crt_cached_ptd_host *a10)
{
  int v10; // edi
  char *v11; // rbx
  __int64 result; // rax
  char *v14; // rax
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

  *Str = 0;
  v10 = 0;
  if ( (Size & 0x80000000) == 0LL )
    v10 = Size;
  v11 = Str;
  if ( a3 <= v10 + 11 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 34;
    invalid_parameter_internal(0, 0, 0, 0, 0, a10);
    return 34;
  }
  if ( (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF )
  {
    if ( *a1 < 0 )
    {
      *Str = 45;
      v11 = Str + 1;
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
      LODWORD(Str) = 48;
      v19 = 0xF000000000000LL;
      while ( v10 > 0 )
      {
        v20 = ((v19 & *a1 & 0xFFFFFFFFFFFFFLL) >> (char)Str) + 48;
        if ( v20 > 0x39u )
          LOBYTE(v20) = 32 * (a7 ^ 1) + 7 + v20;
        *v17 = v20;
        --v10;
        ++v17;
        v19 >>= 4;
        LOWORD(Str) = (_WORD)Str - 4;
        if ( (__int16)Str < 0 )
          goto LABEL_36;
      }
      if ( !(unsigned __int8)should_round_up(a1, v19, (unsigned __int16)Str, a9) )
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
      LOBYTE(Str) = 48;
      memset(v17, (int)Str, (unsigned int)v10);
      v17 += (unsigned int)v10;
    }
    goto LABEL_38;
  }
  result = fp_format_e((int)a1, (int)Str, a3, a4, a5, v10, 0, a8, a9, a10);
  if ( (_DWORD)result )
  {
    *v11 = 0;
    return result;
  }
  v14 = strrchr(v11, 101);
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
0x180056f34  mov     [rsp+arg_0], rbx
0x180056f39  mov     [rsp+arg_10], rbp
0x180056f3e  mov     [rsp+arg_18], rsi
0x180056f43  push    rdi
0x180056f44  push    r12
0x180056f46  push    r13
0x180056f48  push    r14
0x180056f4a  push    r15
0x180056f4c  sub     rsp, 50h
0x180056f50  mov     eax, dword ptr [rsp+78h+Size]
0x180056f57  xor     r11d, r11d
0x180056f5a  test    eax, eax
0x180056f5c  mov     [rdx], r11b
0x180056f5f  mov     edi, r11d
0x180056f62  mov     r10, r9
0x180056f65  cmovns  edi, eax
0x180056f68  mov     rbx, rdx
0x180056f6b  mov     r14, rcx
0x180056f6e  lea     eax, [rdi+0Bh]
0x180056f71  movsxd  r9, eax
0x180056f74  cmp     r8, r9
0x180056f77  ja      short loc_180056FAC
0x180056f79  mov     rcx, [rsp+78h+arg_48]
0x180056f81  lea     ebx, [r11+22h]
0x180056f85  mov     [rsp+78h+var_50], rcx; __crt_cached_ptd_host *
0x180056f8a  xor     r9d, r9d; LineNo
0x180056f8d  xor     r8d, r8d; FileName
0x180056f90  mov     [rsp+78h+var_58], r11; uintptr_t
0x180056f95  xor     edx, edx; FunctionName
0x180056f97  mov     byte ptr [rcx+30h], 1
0x180056f9b  mov     [rcx+2Ch], ebx
0x180056f9e  xor     ecx, ecx; Expression
0x180056fa0  call    _invalid_parameter_internal
0x180056fa5  mov     eax, ebx
0x180056fa7  jmp     loc_1800572A9
0x180056fac  mov     rax, [rcx]
0x180056faf  mov     ecx, 7FFh
0x180056fb4  shr     rax, 34h
0x180056fb8  and     rax, rcx
0x180056fbb  cmp     rax, rcx
0x180056fbe  jnz     loc_180057045
0x180056fc4  mov     rax, [rsp+78h+arg_48]
0x180056fcc  mov     r9, r10; int
0x180056fcf  mov     [rsp+78h+var_30], rax; __crt_cached_ptd_host *
0x180056fd4  mov     rcx, r14; int
0x180056fd7  mov     eax, [rsp+78h+arg_40]
0x180056fde  mov     [rsp+78h+var_38], eax; int
0x180056fe2  mov     eax, [rsp+78h+arg_38]
0x180056fe9  mov     [rsp+78h+var_40], eax; int
0x180056fed  mov     rax, [rsp+78h+arg_20]
0x180056ff5  mov     [rsp+78h+var_48], r11b; char
0x180056ffa  mov     dword ptr [rsp+78h+var_50], edi; int
0x180056ffe  mov     [rsp+78h+var_58], rax; __int64
0x180057003  call    fp_format_e
0x180057008  test    eax, eax
0x18005700a  jz      short loc_180057014
0x18005700c  mov     byte ptr [rbx], 0
0x18005700f  jmp     loc_1800572A9
0x180057014  mov     edx, 65h ; 'e'; Ch
0x180057019  mov     rcx, rbx; Str
0x18005701c  call    strrchr
0x180057021  test    rax, rax
0x180057024  jz      loc_1800572A7
0x18005702a  mov     cl, [rsp+78h+arg_30]
0x180057031  xor     cl, 1
0x180057034  shl     cl, 5
0x180057037  add     cl, 50h ; 'P'
0x18005703a  mov     [rax], cl
0x18005703c  mov     byte ptr [rax+3], 0
0x180057040  jmp     loc_1800572A7
0x180057045  cmp     [r14], r11
0x180057048  jge     short loc_180057050
0x18005704a  mov     byte ptr [rdx], 2Dh ; '-'
0x18005704d  inc     rbx
0x180057050  mov     al, [rsp+78h+arg_30]
0x180057057  lea     r12, [rbx+1]
0x18005705b  xor     al, 1
0x18005705d  mov     r15d, 3FFh
0x180057063  movzx   r13d, al
0x180057067  mov     r8d, 30h ; '0'
0x18005706d  mov     ebp, r13d
0x180057070  mov     rax, 7FF0000000000000h
0x18005707a  shl     ebp, 5
0x18005707d  mov     r9, 0FFFFFFFFFFFFFh
0x180057087  add     ebp, 7
0x18005708a  test    [r14], rax
0x18005708d  jnz     short loc_1800570A7
0x18005708f  mov     [rbx], r8b
0x180057092  mov     rax, [r14]
0x180057095  and     rax, r9
0x180057098  neg     rax
0x18005709b  sbb     r15, r15
0x18005709e  and     r15d, 3FEh
0x1800570a5  jmp     short loc_1800570AA
0x1800570a7  mov     byte ptr [rbx], 31h ; '1'
0x1800570aa  lea     rsi, [r12+1]
0x1800570af  test    edi, edi
0x1800570b1  jnz     short loc_1800570B8
0x1800570b3  mov     al, r11b
0x1800570b6  jmp     short loc_1800570EF
0x1800570b8  mov     rbx, [rsp+78h+arg_48]
0x1800570c0  cmp     [rbx+28h], r11b
0x1800570c4  jnz     short loc_1800570DF
0x1800570c6  mov     rcx, rbx; this
0x1800570c9  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x1800570ce  xor     r11d, r11d
0x1800570d1  mov     r9, 0FFFFFFFFFFFFFh
0x1800570db  lea     r8d, [r11+30h]
0x1800570df  mov     rax, [rbx+18h]
0x1800570e3  mov     rcx, [rax+0F8h]
0x1800570ea  mov     rax, [rcx]
0x1800570ed  mov     al, [rax]
0x1800570ef  mov     [r12], al
0x1800570f3  test    [r14], r9
0x1800570f6  jbe     loc_180057186
0x1800570fc  movzx   edx, r8w
0x180057100  mov     r10, 0F000000000000h
0x18005710a  movzx   ecx, dx
0x18005710d  test    edi, edi
0x18005710f  jle     short loc_18005713D
0x180057111  mov     rax, [r14]
0x180057114  and     rax, r10
0x180057117  and     rax, r9
0x18005711a  shr     rax, cl
0x18005711d  add     ax, r8w
0x180057121  cmp     ax, 39h ; '9'
0x180057125  jbe     short loc_18005712A
0x180057127  add     ax, bp
0x18005712a  mov     [rsi], al
0x18005712c  dec     edi
0x18005712e  inc     rsi
0x180057131  shr     r10, 4
0x180057135  add     dx, 0FFFCh
0x180057139  jns     short loc_18005710A
0x18005713b  jmp     short loc_180057186
0x18005713d  mov     r9d, [rsp+78h+arg_40]
0x180057145  movzx   r8d, cx
0x180057149  mov     rcx, r14
0x18005714c  mov     rdx, r10
0x18005714f  call    should_round_up
0x180057154  xor     r11d, r11d
0x180057157  test    al, al
0x180057159  jz      short loc_1800571A7
0x18005715b  lea     rcx, [rsi-1]
0x18005715f  mov     dl, [rcx]
0x180057161  lea     eax, [rdx-46h]
0x180057164  test    al, 0DFh
0x180057166  jnz     short loc_180057170
0x180057168  mov     byte ptr [rcx], 30h ; '0'
0x18005716b  dec     rcx
0x18005716e  jmp     short loc_18005715F
0x180057170  cmp     rcx, r12
0x180057173  jz      short loc_180057183
0x180057175  cmp     dl, 39h ; '9'
0x180057178  jnz     short loc_18005717D
0x18005717a  add     dl, bpl
0x18005717d  inc     dl
0x18005717f  mov     [rcx], dl
0x180057181  jmp     short loc_180057186
0x180057183  inc     byte ptr [rcx-1]
0x180057186  test    edi, edi
0x180057188  jle     short loc_1800571A7
0x18005718a  mov     r8d, edi; Size
0x18005718d  mov     rcx, rsi; void *
0x180057190  mov     ebx, edi
0x180057192  mov     edi, 30h ; '0'
0x180057197  mov     dl, dil; Val
0x18005719a  call    memset
0x18005719f  add     rsi, rbx
0x1800571a2  xor     r11d, r11d
0x1800571a5  jmp     short loc_1800571AC
0x1800571a7  mov     edi, 30h ; '0'
0x1800571ac  cmp     [r12], r11b
0x1800571b0  cmovz   rsi, r12
0x1800571b4  shl     r13b, 5
0x1800571b8  add     r13b, 50h ; 'P'
0x1800571bc  mov     [rsi], r13b
0x1800571bf  lea     r9, [rsi+2]
0x1800571c3  mov     rax, [r14]
0x1800571c6  shr     rax, 34h
0x1800571ca  and     eax, 7FFh
0x1800571cf  mov     ecx, eax
0x1800571d1  sub     rcx, r15
0x1800571d4  mov     rdx, rcx
0x1800571d7  jns     short loc_1800571DF
0x1800571d9  mov     rcx, r15
0x1800571dc  sub     rcx, rax
0x1800571df  test    rdx, rdx
0x1800571e2  mov     eax, 2Bh ; '+'
0x1800571e7  mov     r8, r9
0x1800571ea  lea     edx, [rax+2]
0x1800571ed  cmovs   eax, edx
0x1800571f0  mov     [rsi+1], al
0x1800571f3  mov     [r9], dil
0x1800571f6  cmp     rcx, 3E8h
0x1800571fd  jl      short loc_180057233
0x1800571ff  mov     rax, 20C49BA5E353F7CFh
0x180057209  lea     r8, [r9+1]
0x18005720d  imul    rcx
0x180057210  sar     rdx, 7
0x180057214  mov     rax, rdx
0x180057217  shr     rax, 3Fh
0x18005721b  add     rdx, rax
0x18005721e  lea     eax, [rdi+rdx]
0x180057221  mov     [r9], al
0x180057224  imul    rax, rdx, 0FFFFFFFFFFFFFC18h
0x18005722b  add     rcx, rax
0x18005722e  cmp     r8, r9
0x180057231  jnz     short loc_180057239
0x180057233  cmp     rcx, 64h ; 'd'
0x180057237  jl      short loc_18005726C
0x180057239  mov     rax, 0A3D70A3D70A3D70Bh
0x180057243  imul    rcx
0x180057246  add     rdx, rcx
0x180057249  sar     rdx, 6
0x18005724d  mov     rax, rdx
0x180057250  shr     rax, 3Fh
0x180057254  add     rdx, rax
0x180057257  lea     eax, [rdi+rdx]
0x18005725a  mov     [r8], al
0x18005725d  inc     r8
0x180057260  imul    rax, rdx, -64h
0x180057264  add     rcx, rax
0x180057267  cmp     r8, r9
0x18005726a  jnz     short loc_180057272
0x18005726c  cmp     rcx, 0Ah
0x180057270  jl      short loc_18005729D
0x180057272  mov     rax, 6666666666666667h
0x18005727c  imul    rcx
0x18005727f  sar     rdx, 2
0x180057283  mov     rax, rdx
0x180057286  shr     rax, 3Fh
0x18005728a  add     rdx, rax
0x18005728d  lea     eax, [rdi+rdx]
0x180057290  mov     [r8], al
0x180057293  inc     r8
0x180057296  imul    rax, rdx, -0Ah
0x18005729a  add     rcx, rax
0x18005729d  add     cl, dil
0x1800572a0  mov     [r8], cl
0x1800572a3  mov     [r8+1], r11b
0x1800572a7  xor     eax, eax
0x1800572a9  lea     r11, [rsp+78h+var_28]
0x1800572ae  mov     rbx, [r11+30h]
0x1800572b2  mov     rbp, [r11+40h]
0x1800572b6  mov     rsi, [r11+48h]
0x1800572ba  mov     rsp, r11
0x1800572bd  pop     r15
0x1800572bf  pop     r14
0x1800572c1  pop     r13
0x1800572c3  pop     r12
0x1800572c5  pop     rdi
0x1800572c6  retn
```
