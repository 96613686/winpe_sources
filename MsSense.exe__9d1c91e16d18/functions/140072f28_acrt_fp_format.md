# __acrt_fp_format

- ea: `0x140072f28`
- end: `0x14007320d`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __fastcall(__int64 *, char *, unsigned __int64, __int64, __int64, int, int, unsigned __int64, int, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x14006552c`
- `0x140065788`

## callees

- `0x14006147c`
- `0x140061554`
- `0x140071a90`
- `0x140072418`
- `0x1400727ac`
- `0x140072a94`
- `0x140072cbc`
- `0x140072f28`

## pseudocode

```c
__int64 __fastcall _acrt_fp_format(
        __int64 *a1,
        char *a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7,
        unsigned __int64 a8,
        int a9,
        __crt_cached_ptd_host *a10)
{
  unsigned __int64 v10; // r11
  char *v11; // r10
  unsigned __int8 v13; // si
  __int64 v14; // rdx
  unsigned int v15; // r8d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  unsigned int v19; // edx
  int v20; // ebx

  v10 = a3;
  v11 = a2;
  if ( !a2 || !a3 || !a4 || !a5 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 22;
    sub_14006147C(0, 0, 0, 0, 0, a10);
    return 22;
  }
  v13 = a6 == 65 || (unsigned int)(a6 - 69) <= 2;
  if ( (a8 & 8) != 0 || (v14 = *a1, (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF) )
  {
    v19 = (a8 >> 4) & 1 | 2;
    v20 = (a8 & 0x20) != 0 ? a9 : 0;
    if ( a6 != 65 )
    {
      switch ( a6 )
      {
        case 'E':
          return sub_1400727AC(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
        case 'F':
          return fp_format_f(a1, v11, a3, a4, a5, a7, v20, a10);
        case 'G':
          return fp_format_g(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
      }
      if ( a6 != 97 )
      {
        if ( a6 != 101 )
        {
          if ( a6 != 102 )
            return fp_format_g(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
          return fp_format_f(a1, v11, a3, a4, a5, a7, v20, a10);
        }
        return sub_1400727AC(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
      }
    }
    return fp_format_a(a1, (__int64)v11, a3, a4, a5, a7, v13, v19, v20, a10);
  }
  v15 = 12;
  if ( (v14 & 0xFFFFFFFFFFFFFLL) != 0 )
  {
    if ( v14 < 0 && (v14 & 0xFFFFFFFFFFFFFLL) == 0x8000000000000LL )
      v16 = 12;
    else
      v16 = (-(__int64)((v14 & 0x8000000000000LL) != 0) & 0xFFFFFFFFFFFFFFFCuLL) + 8;
  }
  else
  {
    v16 = 0;
  }
  v17 = (unsigned __int64)v14 >> 63;
  if ( v10 >= v17 + 4 )
  {
    v18 = -1;
    if ( (_BYTE)v17 )
    {
      *v11++ = 45;
      *v11 = 0;
      if ( v10 != -1 )
        --v10;
    }
    do
      ++v18;
    while ( (*(&off_14009FB50[2 * (v13 ^ 1u)])[v16])[v18] );
    if ( (unsigned int)sub_140071A90(v11, v10, (char *)(&(&off_14009FB50[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
      invoke_watson(0, 0, 0, 0, 0);
    return 0;
  }
  else
  {
    *v11 = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x140072f28  mov     [rsp+arg_0], rbx
0x140072f2d  mov     [rsp+arg_8], rsi
0x140072f32  push    rdi
0x140072f33  sub     rsp, 50h
0x140072f37  mov     r11, r8
0x140072f3a  mov     r10, rdx
0x140072f3d  mov     rdi, rcx
0x140072f40  test    rdx, rdx
0x140072f43  jnz     short loc_140072F78
0x140072f45  mov     rcx, [rsp+58h+arg_48]
0x140072f4d  lea     ebx, [rdx+16h]
0x140072f50  mov     [rsp+58h+var_30], rcx; __crt_cached_ptd_host *
0x140072f55  mov     byte ptr [rcx+30h], 1
0x140072f59  mov     [rcx+2Ch], ebx
0x140072f5c  and     [rsp+58h+var_38], 0
0x140072f62  xor     r9d, r9d; LineNo
0x140072f65  xor     r8d, r8d; FileName
0x140072f68  xor     edx, edx; FunctionName
0x140072f6a  xor     ecx, ecx; Expression
0x140072f6c  call    sub_14006147C
0x140072f71  mov     eax, ebx
0x140072f73  jmp     loc_1400731E7
0x140072f78  test    r11, r11
0x140072f7b  jnz     short loc_140072F98
0x140072f7d  mov     rax, [rsp+58h+arg_48]
0x140072f85  mov     ebx, 16h
0x140072f8a  mov     [rsp+58h+var_30], rax
0x140072f8f  mov     byte ptr [rax+30h], 1
0x140072f93  mov     [rax+2Ch], ebx
0x140072f96  jmp     short loc_140072F5C
0x140072f98  test    r9, r9
0x140072f9b  jz      short loc_140072F7D
0x140072f9d  mov     r8, [rsp+58h+arg_20]
0x140072fa5  test    r8, r8
0x140072fa8  jz      short loc_140072F7D
0x140072faa  mov     ecx, [rsp+58h+arg_28]
0x140072fb1  cmp     ecx, 41h ; 'A'
0x140072fb4  jz      short loc_140072FC3
0x140072fb6  lea     eax, [rcx-45h]
0x140072fb9  cmp     eax, 2
0x140072fbc  jbe     short loc_140072FC3
0x140072fbe  xor     sil, sil
0x140072fc1  jmp     short loc_140072FC6
0x140072fc3  mov     sil, 1
0x140072fc6  mov     rbx, [rsp+58h+arg_38]
0x140072fce  test    bl, 8
0x140072fd1  jnz     loc_1400730BD
0x140072fd7  mov     rdx, [rdi]
0x140072fda  mov     rax, rdx
0x140072fdd  shr     rax, 34h
0x140072fe1  and     eax, 7FFh
0x140072fe6  cmp     rax, 7FFh
0x140072fec  jnz     loc_1400730BD
0x140072ff2  mov     rcx, 0FFFFFFFFFFFFFh
0x140072ffc  mov     rax, rdx
0x140072fff  mov     r8d, 0Ch
0x140073005  and     rax, rcx
0x140073008  jnz     short loc_14007300E
0x14007300a  xor     ecx, ecx
0x14007300c  jmp     short loc_14007303B
0x14007300e  mov     rcx, 8000000000000h
0x140073018  test    rdx, rdx
0x14007301b  jns     short loc_140073027
0x14007301d  cmp     rax, rcx
0x140073020  jnz     short loc_140073027
0x140073022  mov     rcx, r8
0x140073025  jmp     short loc_14007303B
0x140073027  mov     rax, rdx
0x14007302a  and     rax, rcx
0x14007302d  neg     rax
0x140073030  sbb     rcx, rcx
0x140073033  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140073037  add     rcx, 8
0x14007303b  shr     rdx, 3Fh
0x14007303f  lea     rax, [rdx+4]
0x140073043  cmp     r11, rax
0x140073046  jnb     short loc_14007304E
0x140073048  mov     byte ptr [r10], 0
0x14007304c  jmp     short loc_1400730B5
0x14007304e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140073052  test    dl, dl
0x140073054  jz      short loc_140073069
0x140073056  mov     byte ptr [r10], 2Dh ; '-'
0x14007305a  inc     r10
0x14007305d  mov     byte ptr [r10], 0
0x140073061  cmp     r11, r8
0x140073064  jz      short loc_140073069
0x140073066  dec     r11
0x140073069  movzx   edx, sil
0x14007306d  lea     rbx, off_14009FB50
0x140073074  xor     edx, 1
0x140073077  add     edx, edx
0x140073079  mov     eax, edx
0x14007307b  add     rax, rcx
0x14007307e  mov     r9, [rbx+rax*8]
0x140073082  inc     r8
0x140073085  cmp     byte ptr [r9+r8], 0
0x14007308a  jnz     short loc_140073082
0x14007308c  xor     eax, eax
0x14007308e  cmp     r11, r8
0x140073091  setbe   al
0x140073094  lea     r8d, [rdx+rax]
0x140073098  mov     rdx, r11
0x14007309b  add     r8, rcx
0x14007309e  mov     rcx, r10
0x1400730a1  mov     r8, [rbx+r8*8]
0x1400730a5  call    sub_140071A90
0x1400730aa  test    eax, eax
0x1400730ac  jnz     loc_1400731F7
0x1400730b2  xor     r8d, r8d
0x1400730b5  mov     eax, r8d
0x1400730b8  jmp     loc_1400731E7
0x1400730bd  mov     rdx, rbx
0x1400730c0  and     bl, 20h
0x1400730c3  shr     rdx, 4
0x1400730c7  and     edx, 1
0x1400730ca  or      edx, 2
0x1400730cd  neg     bl
0x1400730cf  sbb     ebx, ebx
0x1400730d1  and     ebx, [rsp+58h+arg_40]
0x1400730d8  sub     ecx, 41h ; 'A'
0x1400730db  jz      loc_1400731AF
0x1400730e1  sub     ecx, 4
0x1400730e4  jz      loc_140073175
0x1400730ea  sub     ecx, 1
0x1400730ed  jz      short loc_140073144
0x1400730ef  sub     ecx, 1
0x1400730f2  jz      short loc_140073107
0x1400730f4  sub     ecx, 1Ah
0x1400730f7  jz      loc_1400731AF
0x1400730fd  sub     ecx, 4
0x140073100  jz      short loc_140073175
0x140073102  cmp     ecx, 1
0x140073105  jz      short loc_140073144
0x140073107  mov     rax, [rsp+58h+arg_48]
0x14007310f  mov     rcx, rdi
0x140073112  mov     [rsp+58h+var_10], rax
0x140073117  mov     eax, [rsp+58h+arg_30]
0x14007311e  mov     [rsp+58h+var_18], ebx
0x140073122  mov     dword ptr [rsp+58h+var_20], edx
0x140073126  mov     rdx, r10
0x140073129  mov     byte ptr [rsp+58h+var_28], sil
0x14007312e  mov     dword ptr [rsp+58h+var_30], eax
0x140073132  mov     [rsp+58h+var_38], r8
0x140073137  mov     r8, r11
0x14007313a  call    ?fp_format_g@@YAHQEBNQEAD_K12H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x14007313f  jmp     loc_1400731E7
0x140073144  mov     rax, [rsp+58h+arg_48]
0x14007314c  mov     rdx, r10
0x14007314f  mov     [rsp+58h+var_20], rax
0x140073154  mov     rcx, rdi
0x140073157  mov     eax, [rsp+58h+arg_30]
0x14007315e  mov     [rsp+58h+var_28], ebx
0x140073162  mov     dword ptr [rsp+58h+var_30], eax
0x140073166  mov     [rsp+58h+var_38], r8
0x14007316b  mov     r8, r11
0x14007316e  call    ?fp_format_f@@YAHQEBNQEAD_K12HW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x140073173  jmp     short loc_1400731E7
0x140073175  mov     rax, [rsp+58h+arg_48]
0x14007317d  mov     rcx, rdi
0x140073180  mov     [rsp+58h+var_10], rax
0x140073185  mov     eax, [rsp+58h+arg_30]
0x14007318c  mov     [rsp+58h+var_18], ebx
0x140073190  mov     dword ptr [rsp+58h+var_20], edx
0x140073194  mov     rdx, r10
0x140073197  mov     byte ptr [rsp+58h+var_28], sil
0x14007319c  mov     dword ptr [rsp+58h+var_30], eax
0x1400731a0  mov     [rsp+58h+var_38], r8
0x1400731a5  mov     r8, r11
0x1400731a8  call    sub_1400727AC
0x1400731ad  jmp     short loc_1400731E7
0x1400731af  mov     rax, [rsp+58h+arg_48]
0x1400731b7  mov     rcx, rdi
0x1400731ba  mov     [rsp+58h+var_10], rax
0x1400731bf  mov     eax, [rsp+58h+arg_30]
0x1400731c6  mov     [rsp+58h+var_18], ebx
0x1400731ca  mov     dword ptr [rsp+58h+var_20], edx
0x1400731ce  mov     rdx, r10
0x1400731d1  mov     byte ptr [rsp+58h+var_28], sil
0x1400731d6  mov     dword ptr [rsp+58h+var_30], eax
0x1400731da  mov     [rsp+58h+var_38], r8
0x1400731df  mov     r8, r11
0x1400731e2  call    ?fp_format_a@@YAHQEBNPEAD_KQEAD2H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x1400731e7  mov     rbx, [rsp+58h+arg_0]
0x1400731ec  mov     rsi, [rsp+58h+arg_8]
0x1400731f1  add     rsp, 50h
0x1400731f5  pop     rdi
0x1400731f6  retn
0x1400731f7  and     [rsp+58h+var_38], 0
0x1400731fd  xor     r9d, r9d; LineNo
0x140073200  xor     r8d, r8d; FileName
0x140073203  xor     edx, edx; FunctionName
0x140073205  xor     ecx, ecx; Expression
0x140073207  call    _invoke_watson
```
