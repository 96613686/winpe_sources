# __acrt_fp_format

- ea: `0x14001a500`
- end: `0x14001a7e5`
- name: `__acrt_fp_format`
- size: `741`
- prototype: `__int64 __fastcall(__int64 *, char *, unsigned __int64, __int64, __int64, int, int, unsigned __int64, int, __crt_cached_ptd_host *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140013808`
- `0x140013a64`

## callees

- `0x140015fe4`
- `0x1400160bc`
- `0x1400191a0`
- `0x1400199f0`
- `0x140019d84`
- `0x14001a06c`
- `0x14001a294`
- `0x14001a500`

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
    sub_140015FE4(0, 0, 0, 0, 0, a10);
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
          return sub_140019D84(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
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
        return sub_140019D84(a1, v11, a3, a4, a5, a7, v13, v19, v20, a10);
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
    while ( (*(&off_140030600[2 * (v13 ^ 1u)])[v16])[v18] );
    if ( (unsigned int)sub_1400191A0(v11, v10, (char *)(&(&off_140030600[2 * (v13 ^ 1)])[v16])[v10 <= v18]) )
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
0x14001a500  mov     [rsp+arg_0], rbx
0x14001a505  mov     [rsp+arg_8], rsi
0x14001a50a  push    rdi
0x14001a50b  sub     rsp, 50h
0x14001a50f  mov     r11, r8
0x14001a512  mov     r10, rdx
0x14001a515  mov     rdi, rcx
0x14001a518  test    rdx, rdx
0x14001a51b  jnz     short loc_14001A550
0x14001a51d  mov     rcx, [rsp+58h+arg_48]
0x14001a525  lea     ebx, [rdx+16h]
0x14001a528  mov     [rsp+58h+var_30], rcx; __crt_cached_ptd_host *
0x14001a52d  mov     byte ptr [rcx+30h], 1
0x14001a531  mov     [rcx+2Ch], ebx
0x14001a534  and     [rsp+58h+var_38], 0
0x14001a53a  xor     r9d, r9d; LineNo
0x14001a53d  xor     r8d, r8d; FileName
0x14001a540  xor     edx, edx; FunctionName
0x14001a542  xor     ecx, ecx; Expression
0x14001a544  call    sub_140015FE4
0x14001a549  mov     eax, ebx
0x14001a54b  jmp     loc_14001A7BF
0x14001a550  test    r11, r11
0x14001a553  jnz     short loc_14001A570
0x14001a555  mov     rax, [rsp+58h+arg_48]
0x14001a55d  mov     ebx, 16h
0x14001a562  mov     [rsp+58h+var_30], rax
0x14001a567  mov     byte ptr [rax+30h], 1
0x14001a56b  mov     [rax+2Ch], ebx
0x14001a56e  jmp     short loc_14001A534
0x14001a570  test    r9, r9
0x14001a573  jz      short loc_14001A555
0x14001a575  mov     r8, [rsp+58h+arg_20]
0x14001a57d  test    r8, r8
0x14001a580  jz      short loc_14001A555
0x14001a582  mov     ecx, [rsp+58h+arg_28]
0x14001a589  cmp     ecx, 41h ; 'A'
0x14001a58c  jz      short loc_14001A59B
0x14001a58e  lea     eax, [rcx-45h]
0x14001a591  cmp     eax, 2
0x14001a594  jbe     short loc_14001A59B
0x14001a596  xor     sil, sil
0x14001a599  jmp     short loc_14001A59E
0x14001a59b  mov     sil, 1
0x14001a59e  mov     rbx, [rsp+58h+arg_38]
0x14001a5a6  test    bl, 8
0x14001a5a9  jnz     loc_14001A695
0x14001a5af  mov     rdx, [rdi]
0x14001a5b2  mov     rax, rdx
0x14001a5b5  shr     rax, 34h
0x14001a5b9  and     eax, 7FFh
0x14001a5be  cmp     rax, 7FFh
0x14001a5c4  jnz     loc_14001A695
0x14001a5ca  mov     rcx, 0FFFFFFFFFFFFFh
0x14001a5d4  mov     rax, rdx
0x14001a5d7  mov     r8d, 0Ch
0x14001a5dd  and     rax, rcx
0x14001a5e0  jnz     short loc_14001A5E6
0x14001a5e2  xor     ecx, ecx
0x14001a5e4  jmp     short loc_14001A613
0x14001a5e6  mov     rcx, 8000000000000h
0x14001a5f0  test    rdx, rdx
0x14001a5f3  jns     short loc_14001A5FF
0x14001a5f5  cmp     rax, rcx
0x14001a5f8  jnz     short loc_14001A5FF
0x14001a5fa  mov     rcx, r8
0x14001a5fd  jmp     short loc_14001A613
0x14001a5ff  mov     rax, rdx
0x14001a602  and     rax, rcx
0x14001a605  neg     rax
0x14001a608  sbb     rcx, rcx
0x14001a60b  and     rcx, 0FFFFFFFFFFFFFFFCh
0x14001a60f  add     rcx, 8
0x14001a613  shr     rdx, 3Fh
0x14001a617  lea     rax, [rdx+4]
0x14001a61b  cmp     r11, rax
0x14001a61e  jnb     short loc_14001A626
0x14001a620  mov     byte ptr [r10], 0
0x14001a624  jmp     short loc_14001A68D
0x14001a626  or      r8, 0FFFFFFFFFFFFFFFFh
0x14001a62a  test    dl, dl
0x14001a62c  jz      short loc_14001A641
0x14001a62e  mov     byte ptr [r10], 2Dh ; '-'
0x14001a632  inc     r10
0x14001a635  mov     byte ptr [r10], 0
0x14001a639  cmp     r11, r8
0x14001a63c  jz      short loc_14001A641
0x14001a63e  dec     r11
0x14001a641  movzx   edx, sil
0x14001a645  lea     rbx, off_140030600
0x14001a64c  xor     edx, 1
0x14001a64f  add     edx, edx
0x14001a651  mov     eax, edx
0x14001a653  add     rax, rcx
0x14001a656  mov     r9, [rbx+rax*8]
0x14001a65a  inc     r8
0x14001a65d  cmp     byte ptr [r9+r8], 0
0x14001a662  jnz     short loc_14001A65A
0x14001a664  xor     eax, eax
0x14001a666  cmp     r11, r8
0x14001a669  setbe   al
0x14001a66c  lea     r8d, [rdx+rax]
0x14001a670  mov     rdx, r11
0x14001a673  add     r8, rcx
0x14001a676  mov     rcx, r10
0x14001a679  mov     r8, [rbx+r8*8]
0x14001a67d  call    sub_1400191A0
0x14001a682  test    eax, eax
0x14001a684  jnz     loc_14001A7CF
0x14001a68a  xor     r8d, r8d
0x14001a68d  mov     eax, r8d
0x14001a690  jmp     loc_14001A7BF
0x14001a695  mov     rdx, rbx
0x14001a698  and     bl, 20h
0x14001a69b  shr     rdx, 4
0x14001a69f  and     edx, 1
0x14001a6a2  or      edx, 2
0x14001a6a5  neg     bl
0x14001a6a7  sbb     ebx, ebx
0x14001a6a9  and     ebx, [rsp+58h+arg_40]
0x14001a6b0  sub     ecx, 41h ; 'A'
0x14001a6b3  jz      loc_14001A787
0x14001a6b9  sub     ecx, 4
0x14001a6bc  jz      loc_14001A74D
0x14001a6c2  sub     ecx, 1
0x14001a6c5  jz      short loc_14001A71C
0x14001a6c7  sub     ecx, 1
0x14001a6ca  jz      short loc_14001A6DF
0x14001a6cc  sub     ecx, 1Ah
0x14001a6cf  jz      loc_14001A787
0x14001a6d5  sub     ecx, 4
0x14001a6d8  jz      short loc_14001A74D
0x14001a6da  cmp     ecx, 1
0x14001a6dd  jz      short loc_14001A71C
0x14001a6df  mov     rax, [rsp+58h+arg_48]
0x14001a6e7  mov     rcx, rdi
0x14001a6ea  mov     [rsp+58h+var_10], rax
0x14001a6ef  mov     eax, [rsp+58h+arg_30]
0x14001a6f6  mov     [rsp+58h+var_18], ebx
0x14001a6fa  mov     dword ptr [rsp+58h+var_20], edx
0x14001a6fe  mov     rdx, r10
0x14001a701  mov     byte ptr [rsp+58h+var_28], sil
0x14001a706  mov     dword ptr [rsp+58h+var_30], eax
0x14001a70a  mov     [rsp+58h+var_38], r8
0x14001a70f  mov     r8, r11
0x14001a712  call    ?fp_format_g@@YAHQEBNQEAD_K12H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x14001a717  jmp     loc_14001A7BF
0x14001a71c  mov     rax, [rsp+58h+arg_48]
0x14001a724  mov     rdx, r10
0x14001a727  mov     [rsp+58h+var_20], rax
0x14001a72c  mov     rcx, rdi
0x14001a72f  mov     eax, [rsp+58h+arg_30]
0x14001a736  mov     [rsp+58h+var_28], ebx
0x14001a73a  mov     dword ptr [rsp+58h+var_30], eax
0x14001a73e  mov     [rsp+58h+var_38], r8
0x14001a743  mov     r8, r11
0x14001a746  call    ?fp_format_f@@YAHQEBNQEAD_K12HW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x14001a74b  jmp     short loc_14001A7BF
0x14001a74d  mov     rax, [rsp+58h+arg_48]
0x14001a755  mov     rcx, rdi
0x14001a758  mov     [rsp+58h+var_10], rax
0x14001a75d  mov     eax, [rsp+58h+arg_30]
0x14001a764  mov     [rsp+58h+var_18], ebx
0x14001a768  mov     dword ptr [rsp+58h+var_20], edx
0x14001a76c  mov     rdx, r10
0x14001a76f  mov     byte ptr [rsp+58h+var_28], sil
0x14001a774  mov     dword ptr [rsp+58h+var_30], eax
0x14001a778  mov     [rsp+58h+var_38], r8
0x14001a77d  mov     r8, r11
0x14001a780  call    sub_140019D84
0x14001a785  jmp     short loc_14001A7BF
0x14001a787  mov     rax, [rsp+58h+arg_48]
0x14001a78f  mov     rcx, rdi
0x14001a792  mov     [rsp+58h+var_10], rax
0x14001a797  mov     eax, [rsp+58h+arg_30]
0x14001a79e  mov     [rsp+58h+var_18], ebx
0x14001a7a2  mov     dword ptr [rsp+58h+var_20], edx
0x14001a7a6  mov     rdx, r10
0x14001a7a9  mov     byte ptr [rsp+58h+var_28], sil
0x14001a7ae  mov     dword ptr [rsp+58h+var_30], eax
0x14001a7b2  mov     [rsp+58h+var_38], r8
0x14001a7b7  mov     r8, r11
0x14001a7ba  call    ?fp_format_a@@YAHQEBNPEAD_KQEAD2H_NIW4__acrt_rounding_mode@@AEAV__crt_cached_ptd_host@@@Z
0x14001a7bf  mov     rbx, [rsp+58h+arg_0]
0x14001a7c4  mov     rsi, [rsp+58h+arg_8]
0x14001a7c9  add     rsp, 50h
0x14001a7cd  pop     rdi
0x14001a7ce  retn
0x14001a7cf  and     [rsp+58h+var_38], 0
0x14001a7d5  xor     r9d, r9d; LineNo
0x14001a7d8  xor     r8d, r8d; FileName
0x14001a7db  xor     edx, edx; FunctionName
0x14001a7dd  xor     ecx, ecx; Expression
0x14001a7df  call    _invoke_watson
```
