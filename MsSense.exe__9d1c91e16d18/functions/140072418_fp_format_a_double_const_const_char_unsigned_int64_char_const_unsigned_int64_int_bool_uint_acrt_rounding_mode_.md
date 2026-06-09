# fp_format_a(double const * const,char *,unsigned __int64,char * const,unsigned __int64,int,bool,uint,__acrt_rounding_mode,__crt_cached_ptd_host &)

- ea: `0x140072418`
- end: `0x1400727ab`
- name: `?fp_format_a@@YAHQEBNPEAD_KQEAD2H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z`
- size: `915`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int64, __int64, __int64, int, char, int, unsigned int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140072f28`

## callees

- `0x14006147c`
- `0x140065e50`
- `0x140072418`
- `0x1400727ac`
- `0x140072e10`
- `0x14007fa68`
- `0x1400802f0`

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
    sub_14006147C(0, 0, 0, 0, 0, a10);
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
      sub_1400802F0(v17, a2, (unsigned int)v10);
      v17 += (unsigned int)v10;
    }
    goto LABEL_38;
  }
  result = sub_1400727AC(a1, a2, a3, a4, a5, v10, 0, a8, a9, a10);
  if ( (_DWORD)result )
  {
    *v11 = 0;
    return result;
  }
  v14 = (_BYTE *)sub_14007FA68(v11, 101);
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
0x140072418  mov     [rsp+arg_0], rbx
0x14007241d  mov     [rsp+arg_10], rbp
0x140072422  mov     [rsp+arg_18], rsi
0x140072427  push    rdi
0x140072428  push    r12
0x14007242a  push    r13
0x14007242c  push    r14
0x14007242e  push    r15
0x140072430  sub     rsp, 50h
0x140072434  mov     eax, [rsp+78h+arg_28]
0x14007243b  xor     r11d, r11d
0x14007243e  test    eax, eax
0x140072440  mov     [rdx], r11b
0x140072443  mov     edi, r11d
0x140072446  mov     r10, r9
0x140072449  cmovns  edi, eax
0x14007244c  mov     rbx, rdx
0x14007244f  mov     r14, rcx
0x140072452  lea     eax, [rdi+0Bh]
0x140072455  movsxd  r9, eax
0x140072458  cmp     r8, r9
0x14007245b  ja      short loc_140072490
0x14007245d  mov     rcx, [rsp+78h+arg_48]
0x140072465  lea     ebx, [r11+22h]
0x140072469  mov     [rsp+78h+var_50], rcx; __crt_cached_ptd_host *
0x14007246e  xor     r9d, r9d; LineNo
0x140072471  xor     r8d, r8d; FileName
0x140072474  mov     [rsp+78h+var_58], r11; uintptr_t
0x140072479  xor     edx, edx; FunctionName
0x14007247b  mov     byte ptr [rcx+30h], 1
0x14007247f  mov     [rcx+2Ch], ebx
0x140072482  xor     ecx, ecx; Expression
0x140072484  call    sub_14006147C
0x140072489  mov     eax, ebx
0x14007248b  jmp     loc_14007278D
0x140072490  mov     rax, [rcx]
0x140072493  mov     ecx, 7FFh
0x140072498  shr     rax, 34h
0x14007249c  and     rax, rcx
0x14007249f  cmp     rax, rcx
0x1400724a2  jnz     loc_140072529
0x1400724a8  mov     rax, [rsp+78h+arg_48]
0x1400724b0  mov     r9, r10
0x1400724b3  mov     [rsp+78h+var_30], rax
0x1400724b8  mov     rcx, r14
0x1400724bb  mov     eax, [rsp+78h+arg_40]
0x1400724c2  mov     [rsp+78h+var_38], eax
0x1400724c6  mov     eax, [rsp+78h+arg_38]
0x1400724cd  mov     [rsp+78h+var_40], eax
0x1400724d1  mov     rax, [rsp+78h+arg_20]
0x1400724d9  mov     [rsp+78h+var_48], r11b
0x1400724de  mov     dword ptr [rsp+78h+var_50], edi
0x1400724e2  mov     [rsp+78h+var_58], rax
0x1400724e7  call    sub_1400727AC
0x1400724ec  test    eax, eax
0x1400724ee  jz      short loc_1400724F8
0x1400724f0  mov     byte ptr [rbx], 0
0x1400724f3  jmp     loc_14007278D
0x1400724f8  mov     edx, 65h ; 'e'
0x1400724fd  mov     rcx, rbx
0x140072500  call    sub_14007FA68
0x140072505  test    rax, rax
0x140072508  jz      loc_14007278B
0x14007250e  mov     cl, [rsp+78h+arg_30]
0x140072515  xor     cl, 1
0x140072518  shl     cl, 5
0x14007251b  add     cl, 50h ; 'P'
0x14007251e  mov     [rax], cl
0x140072520  mov     byte ptr [rax+3], 0
0x140072524  jmp     loc_14007278B
0x140072529  cmp     [r14], r11
0x14007252c  jge     short loc_140072534
0x14007252e  mov     byte ptr [rdx], 2Dh ; '-'
0x140072531  inc     rbx
0x140072534  mov     al, [rsp+78h+arg_30]
0x14007253b  lea     r12, [rbx+1]
0x14007253f  xor     al, 1
0x140072541  mov     r15d, 3FFh
0x140072547  movzx   r13d, al
0x14007254b  mov     r8d, 30h ; '0'
0x140072551  mov     ebp, r13d
0x140072554  mov     rax, 7FF0000000000000h
0x14007255e  shl     ebp, 5
0x140072561  mov     r9, 0FFFFFFFFFFFFFh
0x14007256b  add     ebp, 7
0x14007256e  test    [r14], rax
0x140072571  jnz     short loc_14007258B
0x140072573  mov     [rbx], r8b
0x140072576  mov     rax, [r14]
0x140072579  and     rax, r9
0x14007257c  neg     rax
0x14007257f  sbb     r15, r15
0x140072582  and     r15d, 3FEh
0x140072589  jmp     short loc_14007258E
0x14007258b  mov     byte ptr [rbx], 31h ; '1'
0x14007258e  lea     rsi, [r12+1]
0x140072593  test    edi, edi
0x140072595  jnz     short loc_14007259C
0x140072597  mov     al, r11b
0x14007259a  jmp     short loc_1400725D3
0x14007259c  mov     rbx, [rsp+78h+arg_48]
0x1400725a4  cmp     [rbx+28h], r11b
0x1400725a8  jnz     short loc_1400725C3
0x1400725aa  mov     rcx, rbx; this
0x1400725ad  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ
0x1400725b2  xor     r11d, r11d
0x1400725b5  mov     r9, 0FFFFFFFFFFFFFh
0x1400725bf  lea     r8d, [r11+30h]
0x1400725c3  mov     rax, [rbx+18h]
0x1400725c7  mov     rcx, [rax+0F8h]
0x1400725ce  mov     rax, [rcx]
0x1400725d1  mov     al, [rax]
0x1400725d3  mov     [r12], al
0x1400725d7  test    [r14], r9
0x1400725da  jbe     loc_14007266A
0x1400725e0  movzx   edx, r8w
0x1400725e4  mov     r10, 0F000000000000h
0x1400725ee  movzx   ecx, dx
0x1400725f1  test    edi, edi
0x1400725f3  jle     short loc_140072621
0x1400725f5  mov     rax, [r14]
0x1400725f8  and     rax, r10
0x1400725fb  and     rax, r9
0x1400725fe  shr     rax, cl
0x140072601  add     ax, r8w
0x140072605  cmp     ax, 39h ; '9'
0x140072609  jbe     short loc_14007260E
0x14007260b  add     ax, bp
0x14007260e  mov     [rsi], al
0x140072610  dec     edi
0x140072612  inc     rsi
0x140072615  shr     r10, 4
0x140072619  add     dx, 0FFFCh
0x14007261d  jns     short loc_1400725EE
0x14007261f  jmp     short loc_14007266A
0x140072621  mov     r9d, [rsp+78h+arg_40]
0x140072629  movzx   r8d, cx
0x14007262d  mov     rcx, r14
0x140072630  mov     rdx, r10
0x140072633  call    ?should_round_up@@YA_NQEBN_KFW4__acrt_rounding_mode@@@Z
0x140072638  xor     r11d, r11d
0x14007263b  test    al, al
0x14007263d  jz      short loc_14007268B
0x14007263f  lea     rcx, [rsi-1]
0x140072643  mov     dl, [rcx]
0x140072645  lea     eax, [rdx-46h]
0x140072648  test    al, 0DFh
0x14007264a  jnz     short loc_140072654
0x14007264c  mov     byte ptr [rcx], 30h ; '0'
0x14007264f  dec     rcx
0x140072652  jmp     short loc_140072643
0x140072654  cmp     rcx, r12
0x140072657  jz      short loc_140072667
0x140072659  cmp     dl, 39h ; '9'
0x14007265c  jnz     short loc_140072661
0x14007265e  add     dl, bpl
0x140072661  inc     dl
0x140072663  mov     [rcx], dl
0x140072665  jmp     short loc_14007266A
0x140072667  inc     byte ptr [rcx-1]
0x14007266a  test    edi, edi
0x14007266c  jle     short loc_14007268B
0x14007266e  mov     r8d, edi
0x140072671  mov     rcx, rsi
0x140072674  mov     ebx, edi
0x140072676  mov     edi, 30h ; '0'
0x14007267b  mov     dl, dil
0x14007267e  call    sub_1400802F0
0x140072683  add     rsi, rbx
0x140072686  xor     r11d, r11d
0x140072689  jmp     short loc_140072690
0x14007268b  mov     edi, 30h ; '0'
0x140072690  cmp     [r12], r11b
0x140072694  cmovz   rsi, r12
0x140072698  shl     r13b, 5
0x14007269c  add     r13b, 50h ; 'P'
0x1400726a0  mov     [rsi], r13b
0x1400726a3  lea     r9, [rsi+2]
0x1400726a7  mov     rax, [r14]
0x1400726aa  shr     rax, 34h
0x1400726ae  and     eax, 7FFh
0x1400726b3  mov     ecx, eax
0x1400726b5  sub     rcx, r15
0x1400726b8  mov     rdx, rcx
0x1400726bb  jns     short loc_1400726C3
0x1400726bd  mov     rcx, r15
0x1400726c0  sub     rcx, rax
0x1400726c3  test    rdx, rdx
0x1400726c6  mov     eax, 2Bh ; '+'
0x1400726cb  mov     r8, r9
0x1400726ce  lea     edx, [rax+2]
0x1400726d1  cmovs   eax, edx
0x1400726d4  mov     [rsi+1], al
0x1400726d7  mov     [r9], dil
0x1400726da  cmp     rcx, 3E8h
0x1400726e1  jl      short loc_140072717
0x1400726e3  mov     rax, 20C49BA5E353F7CFh
0x1400726ed  lea     r8, [r9+1]
0x1400726f1  imul    rcx
0x1400726f4  sar     rdx, 7
0x1400726f8  mov     rax, rdx
0x1400726fb  shr     rax, 3Fh
0x1400726ff  add     rdx, rax
0x140072702  lea     eax, [rdi+rdx]
0x140072705  mov     [r9], al
0x140072708  imul    rax, rdx, 0FFFFFFFFFFFFFC18h
0x14007270f  add     rcx, rax
0x140072712  cmp     r8, r9
0x140072715  jnz     short loc_14007271D
0x140072717  cmp     rcx, 64h ; 'd'
0x14007271b  jl      short loc_140072750
0x14007271d  mov     rax, 0A3D70A3D70A3D70Bh
0x140072727  imul    rcx
0x14007272a  add     rdx, rcx
0x14007272d  sar     rdx, 6
0x140072731  mov     rax, rdx
0x140072734  shr     rax, 3Fh
0x140072738  add     rdx, rax
0x14007273b  lea     eax, [rdi+rdx]
0x14007273e  mov     [r8], al
0x140072741  inc     r8
0x140072744  imul    rax, rdx, -64h
0x140072748  add     rcx, rax
0x14007274b  cmp     r8, r9
0x14007274e  jnz     short loc_140072756
0x140072750  cmp     rcx, 0Ah
0x140072754  jl      short loc_140072781
0x140072756  mov     rax, 6666666666666667h
0x140072760  imul    rcx
0x140072763  sar     rdx, 2
0x140072767  mov     rax, rdx
0x14007276a  shr     rax, 3Fh
0x14007276e  add     rdx, rax
0x140072771  lea     eax, [rdi+rdx]
0x140072774  mov     [r8], al
0x140072777  inc     r8
0x14007277a  imul    rax, rdx, -0Ah
0x14007277e  add     rcx, rax
0x140072781  add     cl, dil
0x140072784  mov     [r8], cl
0x140072787  mov     [r8+1], r11b
0x14007278b  xor     eax, eax
0x14007278d  lea     r11, [rsp+78h+var_28]
0x140072792  mov     rbx, [r11+30h]
0x140072796  mov     rbp, [r11+40h]
0x14007279a  mov     rsi, [r11+48h]
0x14007279e  mov     rsp, r11
0x1400727a1  pop     r15
0x1400727a3  pop     r14
0x1400727a5  pop     r13
0x1400727a7  pop     r12
0x1400727a9  pop     rdi
0x1400727aa  retn
```
