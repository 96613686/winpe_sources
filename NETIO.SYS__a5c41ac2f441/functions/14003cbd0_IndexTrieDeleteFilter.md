# IndexTrieDeleteFilter

- ea: `0x14003cbd0`
- end: `0x14003d10d`
- name: `IndexTrieDeleteFilter`
- size: `1341`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x140008a00`
- `0x14003cbb0`

## callees

- `0x140004870`
- `0x14002e950`
- `0x140035610`
- `0x14003cbd0`
- `0x14004efd4`
- `0x14004faf8`
- `0x140050a38`
- `0x14006b6d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d02b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003ce6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf32`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cf58`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003d02b`

## string_xrefs

- `0x14003d0a8`: `IndexTrieDeleteFilter`

## pseudocode

```c
__int64 __fastcall IndexTrieDeleteFilter(__int64 a1, _QWORD *a2, __int64 a3)
{
  __int64 v3; // r13
  __int64 v4; // r15
  __int64 v7; // rdx
  char *v8; // rsi
  __int64 v9; // rax
  __int64 v10; // rdx
  __m128i v11; // xmm0
  int v12; // edx
  __int64 v13; // r9
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 Key; // rax
  __int64 v20; // rax
  __int64 v21; // r8
  _WORD *v22; // rbx
  PVOID *v23; // rdi
  _QWORD **v24; // rdx
  _QWORD *v25; // rcx
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  __int64 v28; // rsi
  _WORD *v29; // rax
  void *v30; // rcx
  _QWORD *v31; // rdi
  _QWORD *v32; // rax
  _QWORD *v33; // rcx
  __int64 v35; // [rsp+40h] [rbp-30h] BYREF
  __int64 v36; // [rsp+48h] [rbp-28h]
  unsigned __int64 v37; // [rsp+50h] [rbp-20h] BYREF
  unsigned __int64 v38; // [rsp+58h] [rbp-18h]
  __m128i v39; // [rsp+60h] [rbp-10h] BYREF
  unsigned __int16 v40; // [rsp+B8h] [rbp+48h] BYREF
  int v41; // [rsp+C0h] [rbp+50h]
  char *v42; // [rsp+C8h] [rbp+58h]

  v3 = 0;
  v4 = 0;
  v40 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_5aefcf1cacbb3838841c93cd89c90b00_Traceguids);
  }
  v7 = a2[3];
  v8 = (char *)a2[4];
  v42 = v8;
  if ( *(_DWORD *)(v7 + 28) )
  {
    v9 = 0;
    a3 = 1;
    v41 = 0;
    while ( 1 )
    {
      v10 = *(_QWORD *)(v7 + 32) + 24 * v9;
      if ( *(_WORD *)v10 == **(_WORD **)(a1 + 32) )
        break;
LABEL_59:
      v7 = a2[3];
      v9 = (unsigned int)(v41 + 1);
      v41 = v9;
      if ( (unsigned int)v9 >= *(_DWORD *)(v7 + 28) )
        goto LABEL_60;
    }
    v11 = *(__m128i *)(v10 + 8);
    v12 = _mm_cvtsi128_si32(v11);
    v39 = v11;
    if ( v12 == 256 )
    {
      v13 = 1;
      v38 = 0;
      v36 = 0;
      v40 = 1;
      v14 = (unsigned __int64)*(unsigned int *)v39.m128i_i64[1] << 32;
      v35 = (unsigned __int64)*(unsigned int *)(v39.m128i_i64[1] + 4) << 32;
      v4 = 0;
      v37 = v14;
LABEL_24:
      v20 = VfpTrieLookupKey(*(_QWORD *)a1, &v37, &v35, v13);
      v22 = (_WORD *)v20;
      if ( !v20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
        {
          WPP_SF_II(WPP_GLOBAL_Control->AttachedDevice, *(_QWORD *)a2[3], v21, v14, *(_QWORD *)a2[3]);
        }
        goto LABEL_58;
      }
      v23 = (PVOID *)&v8[8 * v3];
      if ( !*v23 )
        goto LABEL_39;
      v24 = *(_QWORD ***)(v20 + 40);
      if ( !v24 || (v25 = *v24, *v24 == v24) )
      {
LABEL_38:
        HandleFilterDeref(*v23);
LABEL_39:
        v3 = (unsigned int)(v3 + 1);
        if ( v22[24] || (--*(_DWORD *)(a1 + 52), v22[24]) || *((_QWORD *)v22 + 1) || *((_QWORD *)v22 + 2) )
        {
LABEL_58:
          a3 = 1;
          goto LABEL_59;
        }
        while ( 1 )
        {
          v28 = *(_QWORD *)v22;
          if ( !*(_QWORD *)v22 || v22[24] || *((_QWORD *)v22 + 1) || *((_QWORD *)v22 + 2) )
          {
            v8 = v42;
            goto LABEL_58;
          }
          v29 = *(_WORD **)(v28 + 8);
          if ( v29 == v22 )
          {
            *(_QWORD *)(v28 + 8) = 0;
          }
          else
          {
            *(_QWORD *)(v28 + 16) = 0;
            if ( v29 )
              goto LABEL_52;
          }
          if ( !*(_QWORD *)(v28 + 16) )
          {
            ++*(_DWORD *)(a1 + 48);
            goto LABEL_53;
          }
LABEL_52:
          ++*(_DWORD *)(a1 + 44);
LABEL_53:
          v30 = (void *)*((_QWORD *)v22 + 5);
          if ( v30 )
          {
            ExFreePoolWithTag(v30, 0x54706657u);
            *((_QWORD *)v22 + 5) = 0;
            v31 = (_QWORD *)(a1 + 64);
            *(_QWORD *)(a1 + 64) -= 24LL;
          }
          else
          {
            v31 = (_QWORD *)(a1 + 64);
          }
          ExFreePoolWithTag(v22, 0x54706657u);
          --*(_DWORD *)(a1 + 40);
          v22 = (_WORD *)v28;
          *v31 -= 72LL;
        }
      }
      while ( (PVOID *)v25[2] != v23 )
      {
        v25 = (_QWORD *)*v25;
        if ( v25 == v24 )
          goto LABEL_38;
      }
      v26 = (_QWORD *)*v25;
      if ( *(_QWORD **)(*v25 + 8LL) == v25 )
      {
        v27 = (_QWORD *)v25[1];
        if ( (_QWORD *)*v27 == v25 )
        {
          *v27 = v26;
          v26[1] = v27;
          ExFreePoolWithTag(v25, 0x54706657u);
          --v22[24];
          *(_QWORD *)(a1 + 64) -= 32LL;
          goto LABEL_38;
        }
      }
LABEL_80:
      __fastfail(3u);
    }
    if ( v12 == 257 )
    {
      v15 = *(_QWORD *)v39.m128i_i64[1];
      v38 = _byteswap_uint64(*(_QWORD *)(v39.m128i_i64[1] + 8));
      v16 = *(unsigned __int8 *)(v39.m128i_i64[1] + 16);
      v14 = _byteswap_uint64(v15);
      v37 = v14;
      if ( (unsigned __int8)v16 >= 0x40u )
      {
        v35 = -1;
        v13 = 2;
        v18 = 1LL << (0x80 - (unsigned __int8)v16);
        v40 = 2;
        if ( 128 - v16 >= 64 )
          v18 = 0;
        v4 = 0;
        v36 = ~(v18 - 1);
      }
      else
      {
        v13 = 2;
        v40 = 2;
        v17 = 1LL << (64 - (unsigned __int8)v16);
        v36 = 0;
        if ( 64 - v16 >= 64 )
          v17 = 0;
        v4 = 0;
        v35 = ~(v17 - 1);
      }
      goto LABEL_24;
    }
    Key = IndexTrieGetKey((__int64)&v39, v12, &v40, &v37, &v35);
    v4 = Key;
    if ( !Key )
    {
      v13 = v40;
      v14 = v37;
      goto LABEL_24;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"IndexTrieGetKeyFromFilterCondition",
        Key);
    }
  }
  else
  {
LABEL_60:
    v32 = (_QWORD *)*a2;
    if ( (_QWORD *)*a2 != a2 )
    {
      if ( (_QWORD *)v32[1] != a2 )
        goto LABEL_80;
      v33 = (_QWORD *)a2[1];
      if ( (_QWORD *)*v33 != a2 )
        goto LABEL_80;
      *v33 = v32;
      v32[1] = v33;
      a2[1] = a2;
      *a2 = a2;
      --*(_DWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 64) -= 16LL;
      *(_DWORD *)(a1 + 56) -= v3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
      {
        WPP_SF_ddddd(
          WPP_GLOBAL_Control->AttachedDevice,
          v7,
          a3,
          *(unsigned int *)(a1 + 56),
          *(_DWORD *)(a1 + 40),
          *(_DWORD *)(a1 + 48),
          *(_DWORD *)(a1 + 52),
          *(_DWORD *)(a1 + 44),
          v35,
          v36);
      }
    }
  }
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  a2[10] -= 8LL * (unsigned int)v3;
  a2[4] = 0;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_5aefcf1cacbb3838841c93cd89c90b00_Traceguids);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"IndexTrieDeleteFilter",
        v4);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x14003cbd0  push    rbp
0x14003cbd2  push    rbx
0x14003cbd3  push    rsi
0x14003cbd4  push    r12
0x14003cbd6  push    r13
0x14003cbd8  push    r14
0x14003cbda  push    r15
0x14003cbdc  mov     rbp, rsp
0x14003cbdf  sub     rsp, 70h
0x14003cbe3  xor     r13d, r13d
0x14003cbe6  xor     r15d, r15d
0x14003cbe9  xor     eax, eax
0x14003cbeb  mov     r12, rdx
0x14003cbee  mov     [rbp+arg_8], ax
0x14003cbf2  mov     r14, rcx
0x14003cbf5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cbfc  lea     rbx, WPP_GLOBAL_Control
0x14003cc03  cmp     rcx, rbx
0x14003cc06  jz      short loc_14003CC33
0x14003cc08  cmp     byte ptr [rcx+29h], 5
0x14003cc0c  jb      short loc_14003CC33
0x14003cc0e  test    dword ptr [rcx+2Ch], 2000h
0x14003cc15  jz      short loc_14003CC33
0x14003cc17  mov     r9, [rdx+18h]
0x14003cc1b  lea     r8, WPP_5aefcf1cacbb3838841c93cd89c90b00_Traceguids
0x14003cc22  mov     rcx, [rcx+18h]
0x14003cc26  mov     edx, 0Dh
0x14003cc2b  mov     r9, [r9]
0x14003cc2e  call    WPP_SF_q
0x14003cc33  mov     rdx, [r12+18h]
0x14003cc38  mov     rsi, [r12+20h]
0x14003cc3d  mov     [rsp+70h+arg_0], rdi
0x14003cc45  mov     [rbp+arg_18], rsi
0x14003cc49  cmp     [rdx+1Ch], r13d
0x14003cc4d  jbe     loc_14003CF9B
0x14003cc53  xor     eax, eax
0x14003cc55  mov     r8d, 1
0x14003cc5b  mov     [rbp+arg_10], eax
0x14003cc5e  xchg    ax, ax
0x14003cc60  lea     rcx, [rax+rax*2]
0x14003cc64  mov     rax, [rdx+20h]
0x14003cc68  lea     rdx, [rax+rcx*8]
0x14003cc6c  mov     rax, [r14+20h]
0x14003cc70  movzx   ecx, word ptr [rax]
0x14003cc73  cmp     [rdx], cx
0x14003cc76  jnz     loc_14003CF85
0x14003cc7c  movups  xmm0, xmmword ptr [rdx+8]
0x14003cc80  movd    edx, xmm0
0x14003cc84  movups  [rbp+var_10], xmm0
0x14003cc88  cmp     edx, 100h
0x14003cc8e  jnz     short loc_14003CCCA
0x14003cc90  mov     rax, qword ptr [rbp+var_10+8]
0x14003cc94  movzx   r9d, r8w
0x14003cc98  mov     [rbp+var_18], 0
0x14003cca0  mov     [rbp+var_28], 0
0x14003cca8  mov     [rbp+arg_8], r8w
0x14003ccad  mov     edi, [rax]
0x14003ccaf  mov     eax, [rax+4]
0x14003ccb2  shl     rax, 20h
0x14003ccb6  shl     rdi, 20h
0x14003ccba  mov     [rbp+var_30], rax
0x14003ccbe  xor     r15d, r15d
0x14003ccc1  mov     [rbp+var_20], rdi
0x14003ccc5  jmp     loc_14003CDB6
0x14003ccca  cmp     edx, 101h
0x14003ccd0  jnz     loc_14003CD63
0x14003ccd6  mov     rcx, qword ptr [rbp+var_10+8]
0x14003ccda  mov     rdx, r8
0x14003ccdd  mov     rax, [rcx+8]
0x14003cce1  mov     rdi, [rcx]
0x14003cce4  bswap   rax
0x14003cce7  mov     [rbp+var_18], rax
0x14003cceb  movzx   eax, byte ptr [rcx+10h]
0x14003ccef  bswap   rdi
0x14003ccf2  mov     [rbp+var_20], rdi
0x14003ccf6  cmp     al, 40h ; '@'
0x14003ccf8  jnb     short loc_14003CD2E
0x14003ccfa  mov     ecx, 40h ; '@'
0x14003ccff  mov     r9d, 2
0x14003cd05  sub     ecx, eax
0x14003cd07  mov     [rbp+arg_8], r9w
0x14003cd0c  shl     rdx, cl
0x14003cd0f  xor     eax, eax
0x14003cd11  cmp     ecx, 40h ; '@'
0x14003cd14  mov     [rbp+var_28], rax
0x14003cd18  cmovge  rdx, rax
0x14003cd1c  dec     rdx
0x14003cd1f  not     rdx
0x14003cd22  xor     r15d, r15d
0x14003cd25  mov     [rbp+var_30], rdx
0x14003cd29  jmp     loc_14003CDB6
0x14003cd2e  mov     ecx, 80h
0x14003cd33  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFFh
0x14003cd3b  sub     ecx, eax
0x14003cd3d  mov     r9d, 2
0x14003cd43  shl     rdx, cl
0x14003cd46  xor     eax, eax
0x14003cd48  cmp     ecx, 40h ; '@'
0x14003cd4b  mov     [rbp+arg_8], r9w
0x14003cd50  cmovge  rdx, rax
0x14003cd54  dec     rdx
0x14003cd57  not     rdx
0x14003cd5a  xor     r15d, r15d
0x14003cd5d  mov     [rbp+var_28], rdx
0x14003cd61  jmp     short loc_14003CDB6
0x14003cd63  lea     rax, [rbp+var_30]
0x14003cd67  lea     r9, [rbp+var_20]
0x14003cd6b  mov     [rsp+70h+var_50], rax
0x14003cd70  lea     r8, [rbp+arg_8]
0x14003cd74  lea     rcx, [rbp+var_10]
0x14003cd78  call    IndexTrieGetKey
0x14003cd7d  mov     r15, rax
0x14003cd80  test    rax, rax
0x14003cd83  jz      short loc_14003CDAD
0x14003cd85  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cd8c  cmp     rcx, rbx
0x14003cd8f  jz      short loc_14003CDA4
0x14003cd91  cmp     byte ptr [rcx+29h], 2
0x14003cd95  jb      short loc_14003CDA4
0x14003cd97  test    dword ptr [rcx+2Ch], 1000h
0x14003cd9e  jnz     loc_14003D0E1
0x14003cda4  test    rax, rax
0x14003cda7  jnz     loc_14003D021
0x14003cdad  movzx   r9d, [rbp+arg_8]
0x14003cdb2  mov     rdi, [rbp+var_20]
0x14003cdb6  mov     rcx, [r14]
0x14003cdb9  lea     r8, [rbp+var_30]
0x14003cdbd  lea     rdx, [rbp+var_20]
0x14003cdc1  call    VfpTrieLookupKey
0x14003cdc6  mov     rbx, rax
0x14003cdc9  test    rax, rax
0x14003cdcc  jnz     short loc_14003CE1A
0x14003cdce  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cdd5  lea     rbx, WPP_GLOBAL_Control
0x14003cddc  cmp     rcx, rbx
0x14003cddf  jz      loc_14003CF7F
0x14003cde5  cmp     byte ptr [rcx+29h], 2
0x14003cde9  jb      loc_14003CF7F
0x14003cdef  test    dword ptr [rcx+2Ch], 2000h
0x14003cdf6  jz      loc_14003CF7F
0x14003cdfc  mov     rax, [r12+18h]
0x14003ce01  mov     r9, rdi
0x14003ce04  mov     rcx, [rcx+18h]
0x14003ce08  mov     rdx, [rax]
0x14003ce0b  mov     [rsp+70h+var_50], rdx
0x14003ce10  call    WPP_SF_II
0x14003ce15  jmp     loc_14003CF7F
0x14003ce1a  cmp     qword ptr [rsi+r13*8], 0
0x14003ce1f  lea     rdi, [rsi+r13*8]
0x14003ce23  jz      short loc_14003CE93
0x14003ce25  mov     rdx, [rax+28h]
0x14003ce29  test    rdx, rdx
0x14003ce2c  jz      short loc_14003CE89
0x14003ce2e  mov     rcx, [rdx]; P
0x14003ce31  cmp     rcx, rdx
0x14003ce34  jz      short loc_14003CE89
0x14003ce36  cmp     [rcx+10h], rdi
0x14003ce3a  jz      short loc_14003CE49
0x14003ce3c  mov     rax, [rcx]
0x14003ce3f  mov     rcx, rax
0x14003ce42  cmp     rax, rdx
0x14003ce45  jnz     short loc_14003CE36
0x14003ce47  jmp     short loc_14003CE89
0x14003ce49  mov     rdx, [rcx]
0x14003ce4c  cmp     [rdx+8], rcx
0x14003ce50  jnz     loc_14003D106
0x14003ce56  mov     rax, [rcx+8]
0x14003ce5a  cmp     [rax], rcx
0x14003ce5d  jnz     loc_14003D106
0x14003ce63  mov     [rax], rdx
0x14003ce66  mov     [rdx+8], rax
0x14003ce6a  mov     edx, 54706657h; Tag
0x14003ce6f  call    cs:__imp_ExFreePoolWithTag
0x14003ce76  nop     dword ptr [rax+rax+00h]
0x14003ce7b  mov     eax, 0FFFFh
0x14003ce80  add     [rbx+30h], ax
0x14003ce84  add     qword ptr [r14+40h], 0FFFFFFFFFFFFFFE0h
0x14003ce89  mov     rcx, [rdi]
0x14003ce8c  xor     edx, edx
0x14003ce8e  call    HandleFilterDeref
0x14003ce93  inc     r13d
0x14003ce96  cmp     word ptr [rbx+30h], 0
0x14003ce9b  jnz     loc_14003CF78
0x14003cea1  dec     dword ptr [r14+34h]
0x14003cea5  cmp     word ptr [rbx+30h], 0
0x14003ceaa  jnz     loc_14003CF78
0x14003ceb0  cmp     qword ptr [rbx+8], 0
0x14003ceb5  jnz     loc_14003CF78
0x14003cebb  cmp     qword ptr [rbx+10h], 0
0x14003cec0  jnz     loc_14003CF78
0x14003cec6  nop     word ptr [rax+rax+00000000h]
0x14003ced0  mov     rsi, [rbx]
0x14003ced3  test    rsi, rsi
0x14003ced6  jz      loc_14003CF74
0x14003cedc  cmp     word ptr [rbx+30h], 0
0x14003cee1  jnz     loc_14003CF74
0x14003cee7  cmp     qword ptr [rbx+8], 0
0x14003ceec  jnz     loc_14003CF74
0x14003cef2  cmp     qword ptr [rbx+10h], 0
0x14003cef7  jnz     short loc_14003CF74
0x14003cef9  mov     rax, [rsi+8]
0x14003cefd  xor     edi, edi
0x14003ceff  cmp     rax, rbx
0x14003cf02  jnz     short loc_14003CF0A
0x14003cf04  mov     [rsi+8], rdi
0x14003cf08  jmp     short loc_14003CF13
0x14003cf0a  mov     [rsi+10h], rdi
0x14003cf0e  test    rax, rax
0x14003cf11  jnz     short loc_14003CF20
0x14003cf13  cmp     qword ptr [rsi+10h], 0
0x14003cf18  jnz     short loc_14003CF20
0x14003cf1a  inc     dword ptr [r14+30h]
0x14003cf1e  jmp     short loc_14003CF24
0x14003cf20  inc     dword ptr [r14+2Ch]
0x14003cf24  mov     rcx, [rbx+28h]; P
0x14003cf28  test    rcx, rcx
0x14003cf2b  jz      short loc_14003CF4C
0x14003cf2d  mov     edx, 54706657h; Tag
0x14003cf32  call    cs:__imp_ExFreePoolWithTag
0x14003cf39  nop     dword ptr [rax+rax+00h]
0x14003cf3e  mov     [rbx+28h], rdi
0x14003cf42  lea     rdi, [r14+40h]
0x14003cf46  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x14003cf4a  jmp     short loc_14003CF50
0x14003cf4c  lea     rdi, [r14+40h]
0x14003cf50  mov     edx, 54706657h; Tag
0x14003cf55  mov     rcx, rbx; P
0x14003cf58  call    cs:__imp_ExFreePoolWithTag
0x14003cf5f  nop     dword ptr [rax+rax+00h]
0x14003cf64  dec     dword ptr [r14+28h]
0x14003cf68  mov     rbx, rsi
0x14003cf6b  add     qword ptr [rdi], 0FFFFFFFFFFFFFFB8h
0x14003cf6f  jmp     loc_14003CED0
0x14003cf74  mov     rsi, [rbp+arg_18]
0x14003cf78  lea     rbx, WPP_GLOBAL_Control
0x14003cf7f  mov     r8d, 1
0x14003cf85  mov     eax, [rbp+arg_10]
0x14003cf88  mov     rdx, [r12+18h]
0x14003cf8d  inc     eax
0x14003cf8f  mov     [rbp+arg_10], eax
0x14003cf92  cmp     eax, [rdx+1Ch]
0x14003cf95  jb      loc_14003CC60
0x14003cf9b  mov     rax, [r12]
0x14003cf9f  cmp     rax, r12
0x14003cfa2  jz      short loc_14003D021
0x14003cfa4  cmp     [rax+8], r12
0x14003cfa8  jnz     loc_14003D106
0x14003cfae  mov     rcx, [r12+8]
0x14003cfb3  cmp     [rcx], r12
0x14003cfb6  jnz     loc_14003D106
0x14003cfbc  mov     [rcx], rax
0x14003cfbf  mov     [rax+8], rcx
0x14003cfc3  mov     [r12+8], r12
0x14003cfc8  mov     [r12], r12
0x14003cfcc  dec     dword ptr [r14+18h]
0x14003cfd0  add     qword ptr [r14+40h], 0FFFFFFFFFFFFFFF0h
0x14003cfd5  sub     [r14+38h], r13d
0x14003cfd9  mov     r9d, [r14+38h]
0x14003cfdd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003cfe4  cmp     rcx, rbx
0x14003cfe7  jz      short loc_14003D021
0x14003cfe9  cmp     byte ptr [rcx+29h], 5
0x14003cfed  jb      short loc_14003D021
0x14003cfef  test    dword ptr [rcx+2Ch], 2000h
0x14003cff6  jz      short loc_14003D021
0x14003cff8  mov     eax, [r14+2Ch]
0x14003cffc  mov     rcx, [rcx+18h]
0x14003d000  mov     [rsp+70h+var_38], eax
0x14003d004  mov     eax, [r14+34h]
0x14003d008  mov     [rsp+70h+var_40], eax
0x14003d00c  mov     eax, [r14+30h]
0x14003d010  mov     [rsp+70h+var_48], eax
0x14003d014  mov     eax, [r14+28h]
0x14003d018  mov     dword ptr [rsp+70h+var_50], eax
0x14003d01c  call    WPP_SF_ddddd
0x14003d021  test    rsi, rsi
0x14003d024  jz      short loc_14003D037
0x14003d026  xor     edx, edx; Tag
0x14003d028  mov     rcx, rsi; P
0x14003d02b  call    cs:__imp_ExFreePoolWithTag
0x14003d032  nop     dword ptr [rax+rax+00h]
0x14003d037  mov     eax, r13d
0x14003d03a  shl     rax, 3
0x14003d03e  sub     [r12+50h], rax
0x14003d043  mov     qword ptr [r12+20h], 0
0x14003d04c  test    r15, r15
0x14003d04f  jz      short loc_14003D0C5
0x14003d051  mov     rcx, cs:WPP_GLOBAL_Control
0x14003d058  cmp     rcx, rbx
0x14003d05b  jz      short loc_14003D089
0x14003d05d  cmp     byte ptr [rcx+29h], 2
0x14003d061  jb      short loc_14003D089
0x14003d063  test    dword ptr [rcx+2Ch], 2000h
0x14003d06a  jz      short loc_14003D089
0x14003d06c  mov     r9, [r12+18h]
0x14003d071  lea     r8, WPP_5aefcf1cacbb3838841c93cd89c90b00_Traceguids
0x14003d078  mov     rcx, [rcx+18h]
0x14003d07c  mov     edx, 10h
0x14003d081  mov     r9, [r9]
0x14003d084  call    WPP_SF_q
  ... truncated ...
```
