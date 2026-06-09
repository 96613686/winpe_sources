# avio_seek

- ea: `0x1800049e0`
- end: `0x180004cd2`
- name: `avio_seek`
- size: `754`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `4`
- tags: ``

## callers

- `0x180003fb0`
- `0x180004e00`
- `0x1800058b0`
- `0x180006390`
- `0x180007900`
- `0x180008cf4`
- `0x180010290`
- `0x180010818`
- `0x1800110fc`
- `0x180011814`
- `0x180014b00`
- `0x18001507c`
- `0x1800157e8`
- `0x180015db0`
- `0x180015eb0`
- `0x180015fc4`
- `0x18001aaf0`
- `0x18001ae48`
- `0x18001b08c`
- `0x18001b420`

## callees

- `0x1800049e0`
- `0x180005ac0`
- `0x180005c3c`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall avio_seek(__int64 a1, __int64 a2, int a3)
{
  unsigned int v3; // esi
  int v6; // r15d
  int v7; // eax
  __int64 v8; // rbp
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 (__fastcall *v11)(_QWORD); // rax
  int v12; // r14d
  int v13; // eax
  unsigned __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // r8d
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rbp
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 (__fastcall *v23)(_QWORD, __int64, _QWORD); // rax
  __int64 (__fastcall *v24)(_QWORD); // rax

  v3 = a3 & 0xFFFDFFFF;
  if ( !a1 )
    return -22;
  if ( (a3 & 0x10000) == 0 )
  {
    while ( 1 )
    {
      v6 = *(_DWORD *)(a1 + 32) - *(_DWORD *)(a1 + 8);
      v7 = v6;
      if ( *(_DWORD *)(a1 + 88) )
        v7 = 0;
      v8 = *(_QWORD *)(a1 + 72) - v7;
      if ( v3 == 1 )
      {
        v10 = v8 + *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8);
        if ( !a2 )
          return v8 + *(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8);
        if ( a2 > 0x7FFFFFFFFFFFFFFFLL - v10 )
          return -22;
        a2 += v10;
      }
      else if ( v3 )
      {
        return -22;
      }
      if ( a2 < 0 )
        return -22;
      v11 = *(__int64 (__fastcall **)(_QWORD))(a1 + 200);
      v12 = *(_DWORD *)(a1 + 208);
      if ( v11 )
      {
        v13 = v11(*(_QWORD *)(a1 + 40));
        if ( v13 > v12 )
          v12 = v13;
      }
      v14 = *(_QWORD *)(a1 + 24);
      v15 = a2 - v8;
      v16 = *(_DWORD *)(a1 + 140);
      if ( *(_QWORD *)(a1 + 176) > v14 )
        v14 = *(_QWORD *)(a1 + 176);
      *(_QWORD *)(a1 + 176) = v14;
      if ( (!v16 || !*(_QWORD *)(a1 + 64)) && v15 >= 0 )
      {
        v17 = *(_DWORD *)(a1 + 88) ? v14 - *(_QWORD *)(a1 + 8) : v6;
        if ( v15 <= v17 )
        {
          v21 = v15 + *(_QWORD *)(a1 + 8);
LABEL_55:
          _mm_lfence();
          *(_QWORD *)(a1 + 24) = v21;
          result = a2;
          *(_DWORD *)(a1 + 80) = 0;
          return result;
        }
      }
      if ( (*(_BYTE *)(a1 + 136) & 1) != 0 && v15 > v12 + v6 )
      {
        if ( *(_DWORD *)(a1 + 88) )
        {
LABEL_47:
          sub_180005C3C(a1);
          goto LABEL_48;
        }
        if ( v15 >= 0 )
          goto LABEL_48;
      }
      else
      {
        if ( *(_DWORD *)(a1 + 88) )
          goto LABEL_47;
        if ( v15 >= 0 )
        {
          if ( !v16 || !*(_QWORD *)(a1 + 64) )
          {
            while ( 1 )
            {
              v22 = *(_QWORD *)(a1 + 72);
              if ( v22 >= a2 )
                break;
              if ( *(_DWORD *)(a1 + 80) )
                return -541478725;
              sub_180005AC0(a1);
            }
            if ( *(_DWORD *)(a1 + 80) )
              return -541478725;
            v21 = a2 + *(_QWORD *)(a1 + 32) - v22;
            goto LABEL_55;
          }
LABEL_48:
          v23 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 64);
          if ( !v23 )
            return -32;
          _mm_lfence();
          result = v23(*(_QWORD *)(a1 + 40), a2, 0);
          if ( result < 0 )
          {
LABEL_51:
            _mm_lfence();
            return result;
          }
          ++*(_DWORD *)(a1 + 248);
          if ( !*(_DWORD *)(a1 + 88) )
            *(_QWORD *)(a1 + 32) = *(_QWORD *)(a1 + 8);
          v21 = *(_QWORD *)(a1 + 8);
          *(_QWORD *)(a1 + 176) = v21;
          *(_QWORD *)(a1 + 72) = a2;
          goto LABEL_55;
        }
      }
      v18 = (__int64)v6 >> 1;
      if ( v8 - a2 >= v18 || !*(_QWORD *)(a1 + 64) || a2 <= 0 )
        goto LABEL_48;
      _mm_lfence();
      if ( v18 > v8 )
        v18 = v8;
      v19 = v8 - v18;
      result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(a1 + 64))(*(_QWORD *)(a1 + 40), v19, 0);
      if ( result < 0 )
        goto LABEL_51;
      v20 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(a1 + 24) = v20;
      *(_QWORD *)(a1 + 32) = v20;
      *(_QWORD *)(a1 + 72) = v19;
      *(_DWORD *)(a1 + 80) = 0;
      sub_180005AC0(a1);
      v3 = 0;
    }
  }
  v24 = *(__int64 (__fastcall **)(_QWORD))(a1 + 64);
  if ( v24 )
    return v24(*(_QWORD *)(a1 + 40));
  else
    return -40;
}

```

## disassembly

```asm
0x1800049e0  mov     [rsp+arg_0], rbx
0x1800049e5  mov     [rsp+arg_8], rbp
0x1800049ea  mov     [rsp+arg_10], rsi
0x1800049ef  push    rdi
0x1800049f0  push    r12
0x1800049f2  push    r13
0x1800049f4  push    r14
0x1800049f6  push    r15
0x1800049f8  sub     rsp, 20h
0x1800049fc  mov     esi, r8d
0x1800049ff  mov     r13d, r8d
0x180004a02  and     r13d, 20000h
0x180004a09  btr     esi, 11h
0x180004a0d  xor     r10d, r10d
0x180004a10  mov     rdi, rdx
0x180004a13  mov     rbx, rcx
0x180004a16  test    rcx, rcx
0x180004a19  jz      short loc_180004A4F
0x180004a1b  mov     r8d, 10000h
0x180004a21  test    r8d, esi
0x180004a24  jnz     loc_180004CAE
0x180004a2a  mov     r15d, [rbx+20h]
0x180004a2e  sub     r15d, [rbx+8]
0x180004a32  cmp     [rbx+58h], r10d
0x180004a36  mov     eax, r15d
0x180004a39  mov     rbp, [rbx+48h]
0x180004a3d  cmovnz  eax, r10d
0x180004a41  cdqe
0x180004a43  sub     rbp, rax
0x180004a46  cmp     esi, 1
0x180004a49  jz      short loc_180004A73
0x180004a4b  test    esi, esi
0x180004a4d  jz      short loc_180004A9C
0x180004a4f  mov     rax, 0FFFFFFFFFFFFFFEAh
0x180004a56  mov     rbx, [rsp+48h+arg_0]
0x180004a5b  mov     rbp, [rsp+48h+arg_8]
0x180004a60  mov     rsi, [rsp+48h+arg_10]
0x180004a65  add     rsp, 20h
0x180004a69  pop     r15
0x180004a6b  pop     r14
0x180004a6d  pop     r13
0x180004a6f  pop     r12
0x180004a71  pop     rdi
0x180004a72  retn
0x180004a73  mov     rcx, [rbx+18h]
0x180004a77  sub     rcx, [rbx+8]
0x180004a7b  add     rcx, rbp
0x180004a7e  test    rdi, rdi
0x180004a81  jz      loc_180004CA6
0x180004a87  mov     rax, 7FFFFFFFFFFFFFFFh
0x180004a91  sub     rax, rcx
0x180004a94  cmp     rdi, rax
0x180004a97  jg      short loc_180004A4F
0x180004a99  add     rdi, rcx
0x180004a9c  test    rdi, rdi
0x180004a9f  js      short loc_180004A4F
0x180004aa1  mov     rax, [rbx+0C8h]
0x180004aa8  mov     r14d, [rbx+0D0h]
0x180004aaf  test    rax, rax
0x180004ab2  jz      short loc_180004AC8
0x180004ab4  mov     rcx, [rbx+28h]
0x180004ab8  call    cs:__guard_dispatch_icall_fptr
0x180004abe  cmp     eax, r14d
0x180004ac1  cmovg   r14d, eax
0x180004ac5  xor     r10d, r10d
0x180004ac8  mov     rax, [rbx+0B0h]
0x180004acf  mov     rdx, rdi
0x180004ad2  mov     rcx, [rbx+18h]
0x180004ad6  sub     rdx, rbp
0x180004ad9  mov     r8d, [rbx+8Ch]
0x180004ae0  cmp     rax, rcx
0x180004ae3  cmova   rcx, rax
0x180004ae7  mov     [rbx+0B0h], rcx
0x180004aee  test    r8d, r8d
0x180004af1  jz      short loc_180004AF9
0x180004af3  cmp     [rbx+40h], r10
0x180004af7  jnz     short loc_180004B16
0x180004af9  test    rdx, rdx
0x180004afc  js      short loc_180004B16
0x180004afe  cmp     [rbx+58h], r10d
0x180004b02  jz      short loc_180004B0A
0x180004b04  sub     rcx, [rbx+8]
0x180004b08  jmp     short loc_180004B0D
0x180004b0a  movsxd  rcx, r15d
0x180004b0d  cmp     rdx, rcx
0x180004b10  jle     loc_180004BE9
0x180004b16  test    byte ptr [rbx+88h], 1
0x180004b1d  jz      short loc_180004B2B
0x180004b1f  lea     eax, [r14+r15]
0x180004b23  movsxd  rcx, eax
0x180004b26  cmp     rdx, rcx
0x180004b29  jg      short loc_180004B5B
0x180004b2b  cmp     [rbx+58h], r10d
0x180004b2f  jnz     loc_180004C30
0x180004b35  test    rdx, rdx
0x180004b38  js      short loc_180004B6E
0x180004b3a  test    r8d, r8d
0x180004b3d  jz      short loc_180004B49
0x180004b3f  cmp     [rbx+40h], r10
0x180004b43  jnz     loc_180004C38
0x180004b49  cmp     esi, 2
0x180004b4c  jnz     loc_180004C09
0x180004b52  test    r13d, r13d
0x180004b55  jnz     loc_180004C09
0x180004b5b  cmp     [rbx+58h], r10d
0x180004b5f  jnz     loc_180004C30
0x180004b65  test    rdx, rdx
0x180004b68  jns     loc_180004C38
0x180004b6e  movsxd  rax, r15d
0x180004b71  neg     rdx
0x180004b74  sar     rax, 1
0x180004b77  cmp     rdx, rax
0x180004b7a  jge     loc_180004C38
0x180004b80  mov     r9, [rbx+40h]
0x180004b84  test    r9, r9
0x180004b87  jz      loc_180004C38
0x180004b8d  test    rdi, rdi
0x180004b90  jle     loc_180004C38
0x180004b96  lfence
0x180004b99  mov     rcx, [rbx+28h]
0x180004b9d  cmp     rax, rbp
0x180004ba0  cmovg   rax, rbp
0x180004ba4  xor     r8d, r8d
0x180004ba7  sub     rbp, rax
0x180004baa  mov     rax, r9
0x180004bad  mov     rdx, rbp
0x180004bb0  call    cs:__guard_dispatch_icall_fptr
0x180004bb6  test    rax, rax
0x180004bb9  js      loc_180004C68
0x180004bbf  mov     rax, [rbx+8]
0x180004bc3  mov     rcx, rbx
0x180004bc6  mov     [rbx+18h], rax
0x180004bca  mov     [rbx+20h], rax
0x180004bce  mov     [rbx+48h], rbp
0x180004bd2  mov     dword ptr [rbx+50h], 0
0x180004bd9  call    sub_180005AC0
0x180004bde  xor     r10d, r10d
0x180004be1  mov     esi, r10d
0x180004be4  jmp     loc_180004A2A
0x180004be9  mov     rcx, [rbx+8]
0x180004bed  add     rcx, rdx
0x180004bf0  jmp     loc_180004C93
0x180004bf5  cmp     [rbx+50h], r10d
0x180004bf9  jnz     short loc_180004C18
0x180004bfb  mov     rcx, rbx
0x180004bfe  call    sub_180005AC0
0x180004c03  mov     r10d, 0
0x180004c09  mov     rax, [rbx+48h]
0x180004c0d  cmp     rax, rdi
0x180004c10  jl      short loc_180004BF5
0x180004c12  cmp     [rbx+50h], r10d
0x180004c16  jz      short loc_180004C24
0x180004c18  mov     rax, 0FFFFFFFFDFB9B0BBh
0x180004c1f  jmp     loc_180004A56
0x180004c24  mov     rcx, [rbx+20h]
0x180004c28  sub     rcx, rax
0x180004c2b  add     rcx, rdi
0x180004c2e  jmp     short loc_180004C93
0x180004c30  mov     rcx, rbx
0x180004c33  call    sub_180005C3C
0x180004c38  mov     rax, [rbx+40h]
0x180004c3c  test    rax, rax
0x180004c3f  jnz     short loc_180004C4D
0x180004c41  mov     rax, 0FFFFFFFFFFFFFFE0h
0x180004c48  jmp     loc_180004A56
0x180004c4d  lfence
0x180004c50  mov     rcx, [rbx+28h]
0x180004c54  xor     r8d, r8d
0x180004c57  mov     rdx, rdi
0x180004c5a  call    cs:__guard_dispatch_icall_fptr
0x180004c60  xor     r10d, r10d
0x180004c63  test    rax, rax
0x180004c66  jns     short loc_180004C70
0x180004c68  lfence
0x180004c6b  jmp     loc_180004A56
0x180004c70  inc     dword ptr [rbx+0F8h]
0x180004c76  cmp     [rbx+58h], r10d
0x180004c7a  jnz     short loc_180004C84
0x180004c7c  mov     rcx, [rbx+8]
0x180004c80  mov     [rbx+20h], rcx
0x180004c84  mov     rcx, [rbx+8]
0x180004c88  mov     [rbx+0B0h], rcx
0x180004c8f  mov     [rbx+48h], rdi
0x180004c93  lfence
0x180004c96  mov     [rbx+18h], rcx
0x180004c9a  mov     rax, rdi
0x180004c9d  mov     [rbx+50h], r10d
0x180004ca1  jmp     loc_180004A56
0x180004ca6  mov     rax, rcx
0x180004ca9  jmp     loc_180004A56
0x180004cae  mov     rax, [rcx+40h]
0x180004cb2  test    rax, rax
0x180004cb5  jz      short loc_180004CC6
0x180004cb7  mov     rcx, [rcx+28h]
0x180004cbb  call    cs:__guard_dispatch_icall_fptr
0x180004cc1  jmp     loc_180004A56
0x180004cc6  mov     rax, 0FFFFFFFFFFFFFFD8h
0x180004ccd  jmp     loc_180004A56
```
