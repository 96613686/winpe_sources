# fp_format_a(double const * const,char *,unsigned __int64,char * const,unsigned __int64,int,bool,uint,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x1400199f0`
- end: `0x140019d83`
- name: `?fp_format_a@@YAHQEBNPEAD_KQEAD2H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `915`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int64, __int64, __int64, int, char, int, unsigned int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14001a500`

## callees

- `0x140014130`
- `0x140015fe4`
- `0x1400199f0`
- `0x140019d84`
- `0x14001a3e8`
- `0x1400250e0`
- `0x14002a310`

## pseudocode

```c
__int64 __fastcall fp_format_a(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
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

  *(_BYTE *)a2 = 0;
  v10 = 0;
  if ( a6 >= 0 )
    v10 = a6;
  v11 = (_BYTE *)a2;
  if ( a3 <= v10 + 11 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 34;
    sub_140015FE4(0, 0, 0, 0, 0, a10);
    return 34;
  }
  if ( (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF )
  {
    if ( *a1 < 0 )
    {
      *(_BYTE *)a2 = 45;
      v11 = (_BYTE *)(a2 + 1);
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
      a2 = 48;
      v19 = 0xF000000000000LL;
      while ( v10 > 0 )
      {
        v20 = ((v19 & *a1 & 0xFFFFFFFFFFFFFLL) >> a2) + 48;
        if ( v20 > 0x39u )
          LOBYTE(v20) = 32 * (a7 ^ 1) + 7 + v20;
        *v17 = v20;
        --v10;
        ++v17;
        v19 >>= 4;
        LOWORD(a2) = a2 - 4;
        if ( (a2 & 0x8000u) != 0LL )
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
      sub_14002A310(v17, a2, (unsigned int)v10);
      v17 += (unsigned int)v10;
    }
    goto LABEL_38;
  }
  result = sub_140019D84(a1, a2, a3, a4, a5, v10, 0, a8, a9, a10);
  if ( (_DWORD)result )
  {
    *v11 = 0;
    return result;
  }
  v14 = (_BYTE *)sub_1400250E0(v11, 101);
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
0x1400199f0  mov     [rsp+arg_0], rbx
0x1400199f5  mov     [rsp+arg_10], rbp
0x1400199fa  mov     [rsp+arg_18], rsi
0x1400199ff  push    rdi
0x140019a00  push    r12
0x140019a02  push    r13
0x140019a04  push    r14
0x140019a06  push    r15
0x140019a08  sub     rsp, 50h
0x140019a0c  mov     eax, [rsp+78h+arg_28]
0x140019a13  xor     r11d, r11d
0x140019a16  test    eax, eax
0x140019a18  mov     [rdx], r11b
0x140019a1b  mov     edi, r11d
0x140019a1e  mov     r10, r9
0x140019a21  cmovns  edi, eax
0x140019a24  mov     rbx, rdx
0x140019a27  mov     r14, rcx
0x140019a2a  lea     eax, [rdi+0Bh]
0x140019a2d  movsxd  r9, eax
0x140019a30  cmp     r8, r9
0x140019a33  ja      short loc_140019A68
0x140019a35  mov     rcx, [rsp+78h+arg_48]
0x140019a3d  lea     ebx, [r11+22h]
0x140019a41  mov     [rsp+78h+var_50], rcx; __crt_cached_ptd_host *
0x140019a46  xor     r9d, r9d; LineNo
0x140019a49  xor     r8d, r8d; FileName
0x140019a4c  mov     [rsp+78h+var_58], r11; uintptr_t
0x140019a51  xor     edx, edx; FunctionName
0x140019a53  mov     byte ptr [rcx+30h], 1
0x140019a57  mov     [rcx+2Ch], ebx
0x140019a5a  xor     ecx, ecx; Expression
0x140019a5c  call    sub_140015FE4
0x140019a61  mov     eax, ebx
0x140019a63  jmp     loc_140019D65
0x140019a68  mov     rax, [rcx]
0x140019a6b  mov     ecx, 7FFh
0x140019a70  shr     rax, 34h
0x140019a74  and     rax, rcx
0x140019a77  cmp     rax, rcx
0x140019a7a  jnz     loc_140019B01
0x140019a80  mov     rax, [rsp+78h+arg_48]
0x140019a88  mov     r9, r10
0x140019a8b  mov     [rsp+78h+var_30], rax
0x140019a90  mov     rcx, r14
0x140019a93  mov     eax, [rsp+78h+arg_40]
0x140019a9a  mov     [rsp+78h+var_38], eax
0x140019a9e  mov     eax, [rsp+78h+arg_38]
0x140019aa5  mov     [rsp+78h+var_40], eax
0x140019aa9  mov     rax, [rsp+78h+arg_20]
0x140019ab1  mov     [rsp+78h+var_48], r11b
0x140019ab6  mov     dword ptr [rsp+78h+var_50], edi
0x140019aba  mov     [rsp+78h+var_58], rax
0x140019abf  call    sub_140019D84
0x140019ac4  test    eax, eax
0x140019ac6  jz      short loc_140019AD0
0x140019ac8  mov     byte ptr [rbx], 0
0x140019acb  jmp     loc_140019D65
0x140019ad0  mov     edx, 65h ; 'e'
0x140019ad5  mov     rcx, rbx
0x140019ad8  call    sub_1400250E0
0x140019add  test    rax, rax
0x140019ae0  jz      loc_140019D63
0x140019ae6  mov     cl, [rsp+78h+arg_30]
0x140019aed  xor     cl, 1
0x140019af0  shl     cl, 5
0x140019af3  add     cl, 50h ; 'P'
0x140019af6  mov     [rax], cl
0x140019af8  mov     byte ptr [rax+3], 0
0x140019afc  jmp     loc_140019D63
0x140019b01  cmp     [r14], r11
0x140019b04  jge     short loc_140019B0C
0x140019b06  mov     byte ptr [rdx], 2Dh ; '-'
0x140019b09  inc     rbx
0x140019b0c  mov     al, [rsp+78h+arg_30]
0x140019b13  lea     r12, [rbx+1]
0x140019b17  xor     al, 1
0x140019b19  mov     r15d, 3FFh
0x140019b1f  movzx   r13d, al
0x140019b23  mov     r8d, 30h ; '0'
0x140019b29  mov     ebp, r13d
0x140019b2c  mov     rax, 7FF0000000000000h
0x140019b36  shl     ebp, 5
0x140019b39  mov     r9, 0FFFFFFFFFFFFFh
0x140019b43  add     ebp, 7
0x140019b46  test    [r14], rax
0x140019b49  jnz     short loc_140019B63
0x140019b4b  mov     [rbx], r8b
0x140019b4e  mov     rax, [r14]
0x140019b51  and     rax, r9
0x140019b54  neg     rax
0x140019b57  sbb     r15, r15
0x140019b5a  and     r15d, 3FEh
0x140019b61  jmp     short loc_140019B66
0x140019b63  mov     byte ptr [rbx], 31h ; '1'
0x140019b66  lea     rsi, [r12+1]
0x140019b6b  test    edi, edi
0x140019b6d  jnz     short loc_140019B74
0x140019b6f  mov     al, r11b
0x140019b72  jmp     short loc_140019BAB
0x140019b74  mov     rbx, [rsp+78h+arg_48]
0x140019b7c  cmp     [rbx+28h], r11b
0x140019b80  jnz     short loc_140019B9B
0x140019b82  mov     rcx, rbx; this
0x140019b85  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x140019b8a  xor     r11d, r11d
0x140019b8d  mov     r9, 0FFFFFFFFFFFFFh
0x140019b97  lea     r8d, [r11+30h]
0x140019b9b  mov     rax, [rbx+18h]
0x140019b9f  mov     rcx, [rax+0F8h]
0x140019ba6  mov     rax, [rcx]
0x140019ba9  mov     al, [rax]
0x140019bab  mov     [r12], al
0x140019baf  test    [r14], r9
0x140019bb2  jbe     loc_140019C42
0x140019bb8  movzx   edx, r8w
0x140019bbc  mov     r10, 0F000000000000h
0x140019bc6  movzx   ecx, dx
0x140019bc9  test    edi, edi
0x140019bcb  jle     short loc_140019BF9
0x140019bcd  mov     rax, [r14]
0x140019bd0  and     rax, r10
0x140019bd3  and     rax, r9
0x140019bd6  shr     rax, cl
0x140019bd9  add     ax, r8w
0x140019bdd  cmp     ax, 39h ; '9'
0x140019be1  jbe     short loc_140019BE6
0x140019be3  add     ax, bp
0x140019be6  mov     [rsi], al
0x140019be8  dec     edi
0x140019bea  inc     rsi
0x140019bed  shr     r10, 4
0x140019bf1  add     dx, 0FFFCh
0x140019bf5  jns     short loc_140019BC6
0x140019bf7  jmp     short loc_140019C42
0x140019bf9  mov     r9d, [rsp+78h+arg_40]
0x140019c01  movzx   r8d, cx
0x140019c05  mov     rcx, r14
0x140019c08  mov     rdx, r10
0x140019c0b  call    ?should_round_up@@YA_NQEBN_KFW4__acrt_rounding_mode@@@Z
0x140019c10  xor     r11d, r11d
0x140019c13  test    al, al
0x140019c15  jz      short loc_140019C63
0x140019c17  lea     rcx, [rsi-1]
0x140019c1b  mov     dl, [rcx]
0x140019c1d  lea     eax, [rdx-46h]
0x140019c20  test    al, 0DFh
0x140019c22  jnz     short loc_140019C2C
0x140019c24  mov     byte ptr [rcx], 30h ; '0'
0x140019c27  dec     rcx
0x140019c2a  jmp     short loc_140019C1B
0x140019c2c  cmp     rcx, r12
0x140019c2f  jz      short loc_140019C3F
0x140019c31  cmp     dl, 39h ; '9'
0x140019c34  jnz     short loc_140019C39
0x140019c36  add     dl, bpl
0x140019c39  inc     dl
0x140019c3b  mov     [rcx], dl
0x140019c3d  jmp     short loc_140019C42
0x140019c3f  inc     byte ptr [rcx-1]
0x140019c42  test    edi, edi
0x140019c44  jle     short loc_140019C63
0x140019c46  mov     r8d, edi
0x140019c49  mov     rcx, rsi
0x140019c4c  mov     ebx, edi
0x140019c4e  mov     edi, 30h ; '0'
0x140019c53  mov     dl, dil
0x140019c56  call    sub_14002A310
0x140019c5b  add     rsi, rbx
0x140019c5e  xor     r11d, r11d
0x140019c61  jmp     short loc_140019C68
0x140019c63  mov     edi, 30h ; '0'
0x140019c68  cmp     [r12], r11b
0x140019c6c  cmovz   rsi, r12
0x140019c70  shl     r13b, 5
0x140019c74  add     r13b, 50h ; 'P'
0x140019c78  mov     [rsi], r13b
0x140019c7b  lea     r9, [rsi+2]
0x140019c7f  mov     rax, [r14]
0x140019c82  shr     rax, 34h
0x140019c86  and     eax, 7FFh
0x140019c8b  mov     ecx, eax
0x140019c8d  sub     rcx, r15
0x140019c90  mov     rdx, rcx
0x140019c93  jns     short loc_140019C9B
0x140019c95  mov     rcx, r15
0x140019c98  sub     rcx, rax
0x140019c9b  test    rdx, rdx
0x140019c9e  mov     eax, 2Bh ; '+'
0x140019ca3  mov     r8, r9
0x140019ca6  lea     edx, [rax+2]
0x140019ca9  cmovs   eax, edx
0x140019cac  mov     [rsi+1], al
0x140019caf  mov     [r9], dil
0x140019cb2  cmp     rcx, 3E8h
0x140019cb9  jl      short loc_140019CEF
0x140019cbb  mov     rax, 20C49BA5E353F7CFh
0x140019cc5  lea     r8, [r9+1]
0x140019cc9  imul    rcx
0x140019ccc  sar     rdx, 7
0x140019cd0  mov     rax, rdx
0x140019cd3  shr     rax, 3Fh
0x140019cd7  add     rdx, rax
0x140019cda  lea     eax, [rdi+rdx]
0x140019cdd  mov     [r9], al
0x140019ce0  imul    rax, rdx, 0FFFFFFFFFFFFFC18h
0x140019ce7  add     rcx, rax
0x140019cea  cmp     r8, r9
0x140019ced  jnz     short loc_140019CF5
0x140019cef  cmp     rcx, 64h ; 'd'
0x140019cf3  jl      short loc_140019D28
0x140019cf5  mov     rax, 0A3D70A3D70A3D70Bh
0x140019cff  imul    rcx
0x140019d02  add     rdx, rcx
0x140019d05  sar     rdx, 6
0x140019d09  mov     rax, rdx
0x140019d0c  shr     rax, 3Fh
0x140019d10  add     rdx, rax
0x140019d13  lea     eax, [rdi+rdx]
0x140019d16  mov     [r8], al
0x140019d19  inc     r8
0x140019d1c  imul    rax, rdx, -64h
0x140019d20  add     rcx, rax
0x140019d23  cmp     r8, r9
0x140019d26  jnz     short loc_140019D2E
0x140019d28  cmp     rcx, 0Ah
0x140019d2c  jl      short loc_140019D59
0x140019d2e  mov     rax, 6666666666666667h
0x140019d38  imul    rcx
0x140019d3b  sar     rdx, 2
0x140019d3f  mov     rax, rdx
0x140019d42  shr     rax, 3Fh
0x140019d46  add     rdx, rax
0x140019d49  lea     eax, [rdi+rdx]
0x140019d4c  mov     [r8], al
0x140019d4f  inc     r8
0x140019d52  imul    rax, rdx, -0Ah
0x140019d56  add     rcx, rax
0x140019d59  add     cl, dil
0x140019d5c  mov     [r8], cl
0x140019d5f  mov     [r8+1], r11b
0x140019d63  xor     eax, eax
0x140019d65  lea     r11, [rsp+78h+var_28]
0x140019d6a  mov     rbx, [r11+30h]
0x140019d6e  mov     rbp, [r11+40h]
0x140019d72  mov     rsi, [r11+48h]
0x140019d76  mov     rsp, r11
0x140019d79  pop     r15
0x140019d7b  pop     r14
0x140019d7d  pop     r13
0x140019d7f  pop     r12
0x140019d81  pop     rdi
0x140019d82  retn
```
