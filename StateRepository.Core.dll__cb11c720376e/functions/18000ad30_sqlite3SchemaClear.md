# sqlite3SchemaClear

- ea: `0x18000ad30`
- end: `0x18000b036`
- name: `sqlite3SchemaClear`
- size: `774`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x18002a050`
- `0x180030480`
- `0x180046938`
- `0x18005b4bc`

## callees

- `0x1800093ec`
- `0x18000aa60`
- `0x18000aac0`
- `0x18000ad30`
- `0x18000c454`
- `0x18000c960`
- `0x18000cbb8`
- `0x1800569e0`
- `0x180068880`
- `0x18006910e`

## pseudocode

```c
__int16 __fastcall sqlite3SchemaClear(__int64 a1)
{
  __m128i v2; // xmm7
  __m128i v3; // xmm6
  _QWORD *i; // rsi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  bool v11; // zf
  __int16 v12; // ax
  __int16 result; // ax
  _QWORD v14[4]; // [rsp+28h] [rbp-E0h] BYREF
  __m128i v15; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v16; // [rsp+58h] [rbp-B0h]
  _BYTE v17[456]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v18; // [rsp+230h] [rbp+128h]
  _QWORD *v19; // [rsp+240h] [rbp+138h]
  unsigned __int64 v20; // [rsp+248h] [rbp+140h]
  unsigned __int64 v21; // [rsp+250h] [rbp+148h]
  unsigned __int64 v22; // [rsp+258h] [rbp+150h]
  __int64 v23; // [rsp+370h] [rbp+268h]

  memset_0(v17, 0, 0x318u);
  v2 = *(__m128i *)(a1 + 8);
  v3 = *(__m128i *)(a1 + 56);
  v16 = *(_QWORD *)(a1 + 24);
  v14[3] = *(_QWORD *)(a1 + 72);
  v15 = v2;
  *(_QWORD *)(a1 + 64) = 0;
  *(__m128i *)&v14[1] = v3;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  sqlite3HashClear(a1 + 32);
  for ( i = (_QWORD *)_mm_srli_si128(v3, 8).m128i_u64[0]; i; i = (_QWORD *)*i )
  {
    v5 = (_QWORD *)i[2];
    if ( !v5 || *((_BYTE *)v5 + 18) )
      continue;
    sqlite3DeleteTriggerStep(v17, v5[7]);
    v6 = (_QWORD *)*v5;
    if ( *v5 )
    {
      if ( (unsigned __int64)v6 < v22 )
      {
        if ( (unsigned __int64)v6 >= v20 )
        {
          *v6 = v19;
          v19 = v6;
          goto LABEL_10;
        }
        if ( (unsigned __int64)v6 >= v21 )
        {
          *v6 = v18;
          v18 = v6;
          goto LABEL_10;
        }
      }
      if ( v23 )
        measureAllocationSize(v17, *v5);
      else
        sqlite3_free(v6);
    }
LABEL_10:
    v7 = (_QWORD *)v5[1];
    if ( v7 )
    {
      if ( (unsigned __int64)v7 >= v22 )
        goto LABEL_12;
      if ( (unsigned __int64)v7 >= v20 )
      {
        *v7 = v19;
        v19 = v7;
      }
      else
      {
        if ( (unsigned __int64)v7 < v21 )
        {
LABEL_12:
          if ( v23 )
            measureAllocationSize(v17, v5[1]);
          else
            sqlite3_free(v7);
          goto LABEL_14;
        }
        *v7 = v18;
        v18 = v7;
      }
    }
LABEL_14:
    v8 = v5[3];
    if ( v8 )
      sqlite3ExprDeleteNN((__int64)v17, v8);
    sqlite3IdListDelete(v17, v5[4]);
    if ( (unsigned __int64)v5 < v22 )
    {
      if ( (unsigned __int64)v5 >= v20 )
      {
        *v5 = v19;
        v19 = v5;
        continue;
      }
      if ( (unsigned __int64)v5 >= v21 )
      {
        *v5 = v18;
        v18 = v5;
        continue;
      }
    }
    if ( v23 )
      measureAllocationSize(v17, v5);
    else
      sqlite3_free(v5);
  }
  sqlite3HashClear(&v14[1]);
  v9 = (_QWORD *)_mm_srli_si128(v2, 8).m128i_u64[0];
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  while ( v9 )
  {
    v10 = v9[2];
    if ( v10 )
    {
      if ( v23 || (v11 = *(_DWORD *)(v10 + 44) == 1, --*(_DWORD *)(v10 + 44), v11) )
        deleteTable((__int64)v17, v10);
    }
    v9 = (_QWORD *)*v9;
  }
  sqlite3HashClear(&v15);
  sqlite3HashClear(a1 + 80);
  v12 = *(_WORD *)(a1 + 114);
  *(_QWORD *)(a1 + 104) = 0;
  if ( (v12 & 1) != 0 )
    ++*(_DWORD *)(a1 + 4);
  result = v12 & 0xFFF6;
  *(_WORD *)(a1 + 114) = result;
  return result;
}

```

## disassembly

```asm
0x18000ad30  mov     rax, rsp
0x18000ad33  mov     [rax+10h], rbx
0x18000ad37  mov     [rax+18h], rsi
0x18000ad3b  push    rbp
0x18000ad3c  push    rdi
0x18000ad3d  push    r14
0x18000ad3f  lea     rbp, [rax-2C8h]
0x18000ad46  sub     rsp, 3B0h
0x18000ad4d  movaps  xmmword ptr [rax-28h], xmm6
0x18000ad51  movaps  xmmword ptr [rax-38h], xmm7
0x18000ad55  mov     rax, cs:__security_cookie
0x18000ad5c  xor     rax, rsp
0x18000ad5f  mov     [rbp+2C0h+var_40], rax
0x18000ad66  mov     rdi, rcx
0x18000ad69  xor     edx, edx; Val
0x18000ad6b  lea     rcx, [rsp+3C0h+var_360]; void *
0x18000ad70  mov     r8d, 318h; Size
0x18000ad76  call    memset_0
0x18000ad7b  movsd   xmm0, qword ptr [rdi+18h]
0x18000ad80  lea     rcx, [rdi+20h]
0x18000ad84  movups  xmm7, xmmword ptr [rdi+8]
0x18000ad88  xor     r14d, r14d
0x18000ad8b  movups  xmm6, xmmword ptr [rdi+38h]
0x18000ad8f  movsd   [rsp+3C0h+var_370], xmm0
0x18000ad95  movsd   xmm0, qword ptr [rdi+48h]
0x18000ad9a  movsd   qword ptr [rsp+3C0h+var_388], xmm0
0x18000ada0  movups  xmmword ptr [rsp+3C0h+var_388+8], xmm7
0x18000ada5  mov     [rdi+40h], r14
0x18000ada9  movups  xmmword ptr [rsp+3C0h+var_3A0+8], xmm6
0x18000adae  mov     [rdi+38h], r14
0x18000adb2  mov     [rdi+48h], r14
0x18000adb6  call    sqlite3HashClear
0x18000adbb  psrldq  xmm6, 8
0x18000adc0  movq    rsi, xmm6
0x18000adc5  test    rsi, rsi
0x18000adc8  jz      loc_18000AF87
0x18000adce  mov     rbx, [rsi+10h]
0x18000add2  test    rbx, rbx
0x18000add5  jz      short loc_18000ADDD
0x18000add7  cmp     [rbx+12h], r14b
0x18000addb  jz      short loc_18000ADE2
0x18000addd  mov     rsi, [rsi]
0x18000ade0  jmp     short loc_18000ADC5
0x18000ade2  mov     rdx, [rbx+38h]
0x18000ade6  lea     rcx, [rsp+3C0h+var_360]
0x18000adeb  call    sqlite3DeleteTriggerStep
0x18000adf0  mov     rcx, [rbx]
0x18000adf3  test    rcx, rcx
0x18000adf6  jz      short loc_18000AE1F
0x18000adf8  cmp     rcx, [rbp+2C0h+var_170]
0x18000adff  jb      loc_18000AE98
0x18000ae05  cmp     [rbp+2C0h+var_58], r14
0x18000ae0c  jz      loc_18000AF24
0x18000ae12  mov     rdx, rcx
0x18000ae15  lea     rcx, [rsp+3C0h+var_360]
0x18000ae1a  call    measureAllocationSize
0x18000ae1f  mov     rcx, [rbx+8]
0x18000ae23  test    rcx, rcx
0x18000ae26  jz      short loc_18000AE4F
0x18000ae28  cmp     rcx, [rbp+2C0h+var_170]
0x18000ae2f  jb      loc_18000AEC8
0x18000ae35  cmp     [rbp+2C0h+var_58], r14
0x18000ae3c  jz      loc_18000AF2E
0x18000ae42  mov     rdx, rcx
0x18000ae45  lea     rcx, [rsp+3C0h+var_360]
0x18000ae4a  call    measureAllocationSize
0x18000ae4f  mov     rdx, [rbx+18h]
0x18000ae53  test    rdx, rdx
0x18000ae56  jz      short loc_18000AE62
0x18000ae58  lea     rcx, [rsp+3C0h+var_360]
0x18000ae5d  call    sqlite3ExprDeleteNN
0x18000ae62  mov     rdx, [rbx+20h]
0x18000ae66  lea     rcx, [rsp+3C0h+var_360]
0x18000ae6b  call    sqlite3IdListDelete
0x18000ae70  cmp     rbx, [rbp+2C0h+var_170]
0x18000ae77  jb      short loc_18000AEF8
0x18000ae79  cmp     [rbp+2C0h+var_58], r14
0x18000ae80  jz      loc_18000AF38
0x18000ae86  mov     rdx, rbx
0x18000ae89  lea     rcx, [rsp+3C0h+var_360]
0x18000ae8e  call    measureAllocationSize
0x18000ae93  jmp     loc_18000ADDD
0x18000ae98  cmp     rcx, [rbp+2C0h+var_180]
0x18000ae9f  jnb     loc_18000AF45
0x18000aea5  cmp     rcx, [rbp+2C0h+var_178]
0x18000aeac  jb      loc_18000AE05
0x18000aeb2  mov     rax, [rbp+2C0h+var_198]
0x18000aeb9  mov     [rcx], rax
0x18000aebc  mov     [rbp+2C0h+var_198], rcx
0x18000aec3  jmp     loc_18000AE1F
0x18000aec8  cmp     rcx, [rbp+2C0h+var_180]
0x18000aecf  jnb     loc_18000AF5B
0x18000aed5  cmp     rcx, [rbp+2C0h+var_178]
0x18000aedc  jb      loc_18000AE35
0x18000aee2  mov     rax, [rbp+2C0h+var_198]
0x18000aee9  mov     [rcx], rax
0x18000aeec  mov     [rbp+2C0h+var_198], rcx
0x18000aef3  jmp     loc_18000AE4F
0x18000aef8  cmp     rbx, [rbp+2C0h+var_180]
0x18000aeff  jnb     short loc_18000AF71
0x18000af01  cmp     rbx, [rbp+2C0h+var_178]
0x18000af08  jb      loc_18000AE79
0x18000af0e  mov     rax, [rbp+2C0h+var_198]
0x18000af15  mov     [rbx], rax
0x18000af18  mov     [rbp+2C0h+var_198], rbx
0x18000af1f  jmp     loc_18000ADDD
0x18000af24  call    sqlite3_free
0x18000af29  jmp     loc_18000AE1F
0x18000af2e  call    sqlite3_free
0x18000af33  jmp     loc_18000AE4F
0x18000af38  mov     rcx, rbx
0x18000af3b  call    sqlite3_free
0x18000af40  jmp     loc_18000ADDD
0x18000af45  mov     rax, [rbp+2C0h+var_188]
0x18000af4c  mov     [rcx], rax
0x18000af4f  mov     [rbp+2C0h+var_188], rcx
0x18000af56  jmp     loc_18000AE1F
0x18000af5b  mov     rax, [rbp+2C0h+var_188]
0x18000af62  mov     [rcx], rax
0x18000af65  mov     [rbp+2C0h+var_188], rcx
0x18000af6c  jmp     loc_18000AE4F
0x18000af71  mov     rax, [rbp+2C0h+var_188]
0x18000af78  mov     [rbx], rax
0x18000af7b  mov     [rbp+2C0h+var_188], rbx
0x18000af82  jmp     loc_18000ADDD
0x18000af87  lea     rcx, [rsp+3C0h+var_3A0+8]
0x18000af8c  call    sqlite3HashClear
0x18000af91  psrldq  xmm7, 8
0x18000af96  movq    rbx, xmm7
0x18000af9b  mov     [rdi+10h], r14
0x18000af9f  mov     [rdi+8], r14
0x18000afa3  mov     [rdi+18h], r14
0x18000afa7  test    rbx, rbx
0x18000afaa  jz      short loc_18000AFC9
0x18000afac  mov     rdx, [rbx+10h]
0x18000afb0  test    rdx, rdx
0x18000afb3  jz      short loc_18000AFC4
0x18000afb5  cmp     [rbp+2C0h+var_58], r14
0x18000afbc  jnz     short loc_18000B025
0x18000afbe  add     dword ptr [rdx+2Ch], 0FFFFFFFFh
0x18000afc2  jz      short loc_18000B025
0x18000afc4  mov     rbx, [rbx]
0x18000afc7  jmp     short loc_18000AFA7
0x18000afc9  lea     rcx, [rsp+3C0h+var_388+8]
0x18000afce  call    sqlite3HashClear
0x18000afd3  lea     rcx, [rdi+50h]
0x18000afd7  call    sqlite3HashClear
0x18000afdc  movzx   eax, word ptr [rdi+72h]
0x18000afe0  mov     [rdi+68h], r14
0x18000afe4  test    al, 1
0x18000afe6  jnz     short loc_18000B031
0x18000afe8  mov     ecx, 0FFF6h
0x18000afed  and     ax, cx
0x18000aff0  mov     [rdi+72h], ax
0x18000aff4  mov     rcx, [rbp+2C0h+var_40]
0x18000affb  xor     rcx, rsp; StackCookie
0x18000affe  call    __security_check_cookie
0x18000b003  lea     r11, [rsp+3C0h+var_10]
0x18000b00b  mov     rbx, [r11+28h]
0x18000b00f  mov     rsi, [r11+30h]
0x18000b013  movaps  xmm6, xmmword ptr [r11-10h]
0x18000b018  movaps  xmm7, xmmword ptr [r11-20h]
0x18000b01d  mov     rsp, r11
0x18000b020  pop     r14
0x18000b022  pop     rdi
0x18000b023  pop     rbp
0x18000b024  retn
0x18000b025  lea     rcx, [rsp+3C0h+var_360]
0x18000b02a  call    deleteTable
0x18000b02f  jmp     short loc_18000AFC4
0x18000b031  inc     dword ptr [rdi+4]
0x18000b034  jmp     short loc_18000AFE8
```
