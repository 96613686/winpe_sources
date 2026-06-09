# BUpdateFont

- ea: `0x18000f9d4`
- end: `0x18000fe4b`
- name: `BUpdateFont`
- size: `1143`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int16 *, __int64, int, _DWORD *, _DWORD *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000f2e4`

## callees

- `0x18000f9d4`
- `0x18000fe54`
- `0x180010ea8`
- `0x18001107c`
- `0x180011964`
- `0x18001e3cc`
- `0x18001e5c4`

## pseudocode

```c
__int64 __fastcall BUpdateFont(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 *a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        _DWORD *a8,
        int a9)
{
  __int64 v9; // r10
  bool v10; // zf
  unsigned int v13; // esi
  __int64 v14; // rax
  _DWORD *v15; // r14
  int v16; // eax
  __int64 result; // rax
  int v18; // r8d
  unsigned int v19; // ebx
  __int16 v20; // r12
  int v21; // eax
  __int16 v22; // r14
  __int16 v23; // r15
  int v24; // eax
  unsigned __int16 v25; // ax
  int v26; // ecx
  __int16 v27; // ax
  _BYTE *v28; // rax
  __int64 v29; // r8
  int v30; // edx
  __int64 v31; // rax
  BOOL v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int16 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  int v38; // edx
  int v39; // eax
  __int64 v40; // rax
  BOOL v41; // eax
  int v42; // [rsp+60h] [rbp-20h] BYREF
  int v43; // [rsp+64h] [rbp-1Ch]
  __int64 v44; // [rsp+68h] [rbp-18h]
  __int64 v45; // [rsp+70h] [rbp-10h]
  __int64 v46; // [rsp+78h] [rbp-8h]
  int v47; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v48; // [rsp+D0h] [rbp+50h]
  unsigned __int16 *v49; // [rsp+D8h] [rbp+58h]

  v49 = a4;
  v48 = a3;
  v9 = a3;
  v10 = *(_DWORD *)(a2 + 196) == 8;
  v47 = 0;
  v42 = 0;
  if ( !v10 )
  {
    if ( !a4 )
      return 1;
    v18 = a6;
    if ( !a6 )
      return 1;
    v46 = *(_QWORD *)(a1 + 3528);
    v19 = 1;
    v20 = 0;
    v44 = v46 + 1024;
    v45 = v46 + 3072;
    *a7 = 0;
    *a8 = 0;
    v21 = *(_DWORD *)(a2 + 196);
    if ( v21 == 7 || v21 == 10 )
      v22 = (*(_DWORD *)(a1 + 3564) >> 23) & 1;
    else
      v22 = -1;
    if ( v18 > 0 )
    {
      v23 = v22;
      do
      {
        v24 = *(_DWORD *)(a2 + 196);
        if ( v24 == 7 || v24 == 10 )
        {
          v43 = 0;
        }
        else
        {
          v25 = WSetSoiMapping(a2, *a4);
          v18 = a6;
          v26 = v25;
          v9 = v48;
          LOWORD(v26) = (unsigned __int8)v25;
          v27 = HIBYTE(v25);
          v43 = v26;
          v22 = v27;
          if ( v23 == -1 )
            v23 = v27;
        }
        if ( v20 > 254 || v22 != v23 )
        {
          if ( *(_DWORD *)(a2 + 196) == 6 && v23 )
            v28 = PNewSubFontByCopy(a1, a2, 0, v23, v9);
          else
            v28 = PNewSubFont(a1, a2, v23, v9);
          v29 = (__int64)v28;
          if ( !v28 )
            return 0;
          v30 = *(_DWORD *)(a2 + 196);
          if ( a9 )
          {
            if ( v30 == 7 || (v31 = v44, v30 == 10) )
              v31 = 0;
            v32 = BUFOVMNeeded((__int64)&v47, v30, v29, v20, v46, v31, v45, &v47, &v42);
          }
          else
          {
            if ( ((v30 - 7) & 0xFFFFFFFC) != 0 || (v33 = 0, v30 == 8) )
              v33 = v44;
            v32 = BUFODownload(a1, v30, (__int64)v28, v20, v46, v33, v45, a5, &v47, &v42, 0);
          }
          v19 = v32;
          if ( !v32 )
            return v19;
          v23 = v22;
          *a7 += v47;
          *a8 += v42;
          if ( a5 )
            a5 += 2LL * v20;
          v18 = a6;
          v20 = 0;
        }
        --v18;
        v34 = v20;
        v10 = *(_DWORD *)(a2 + 196) == 9;
        a6 = v18;
        v35 = v43;
        if ( !v10 )
          *(_QWORD *)(v44 + 8LL * v20) = off_1800730E0[(unsigned __int16)v43];
        ++v20;
        v36 = v46;
        v9 = v48;
        *(_WORD *)(v45 + 2 * v34) = v35;
        a4 = v49 + 12;
        *(_DWORD *)(v36 + 4 * v34) = *(_DWORD *)v49;
        v49 = a4;
      }
      while ( v18 > 0 );
      if ( v19 && v20 )
      {
        if ( *(_DWORD *)(a2 + 196) == 6 && v22 )
          result = (__int64)PNewSubFontByCopy(a1, a2, 0, v22, v9);
        else
          result = (__int64)PNewSubFont(a1, a2, v22, v48);
        v37 = result;
        if ( !result )
          return result;
        v38 = *(_DWORD *)(a2 + 196);
        v39 = v38 - 7;
        if ( a9 )
        {
          if ( (v39 & 0xFFFFFFFC) != 0 || (v40 = 0, v38 == 8) )
            v40 = v44;
          v41 = BUFOVMNeeded((__int64)&v47, v38, v37, v20, v46, v40, v45, &v47, &v42);
        }
        else
        {
          if ( (v39 & 0xFFFFFFFC) == 0 && v38 != 8 )
            v44 = 0;
          v41 = BUFODownload(a1, v38, v37, v20, v46, v44, v45, a5, &v47, &v42, 0);
        }
        v19 = v41;
        if ( v41 )
        {
          *a7 += v47;
          *a8 += v42;
        }
      }
    }
    return v19;
  }
  v13 = 1;
  v14 = *(_QWORD *)(a2 + 344);
  v15 = a7;
  if ( a9 )
  {
    v10 = v14 == 65278;
    v16 = 0;
    if ( !v10 )
      v16 = *(_DWORD *)(a2 + 392);
    *a7 = v16;
  }
  else if ( v14 != 65278 )
  {
    v13 = BWritePfbToOutput(a1, a2, a7);
    if ( v13 )
      *(_QWORD *)(a2 + 344) = 65278;
  }
  if ( *(_DWORD *)(a2 + 416) )
    *v15 = 0;
  return v13;
}

```

## disassembly

```asm
0x18000f9d4  mov     [rsp-38h+arg_0], rbx
0x18000f9d9  mov     [rsp-38h+arg_18], r9
0x18000f9de  mov     [rsp-38h+arg_10], r8
0x18000f9e3  push    rbp
0x18000f9e4  push    rsi
0x18000f9e5  push    rdi
0x18000f9e6  push    r12
0x18000f9e8  push    r13
0x18000f9ea  push    r14
0x18000f9ec  push    r15
0x18000f9ee  mov     rbp, rsp
0x18000f9f1  sub     rsp, 80h
0x18000f9f8  xor     r11d, r11d
0x18000f9fb  mov     r10, r8
0x18000f9fe  cmp     dword ptr [rdx+0C4h], 8
0x18000fa05  mov     rdi, rdx
0x18000fa08  mov     r13, rcx
0x18000fa0b  mov     [rbp+arg_8], r11d
0x18000fa0f  mov     [rbp+var_20], r11d
0x18000fa13  jnz     short loc_18000FA75
0x18000fa15  lea     esi, [r11+1]
0x18000fa19  mov     rax, [rdx+158h]
0x18000fa20  mov     ebx, 0FEFEh
0x18000fa25  mov     r14, [rbp+arg_30]
0x18000fa29  cmp     [rbp+arg_40], r11d
0x18000fa30  jz      short loc_18000FA45
0x18000fa32  cmp     rax, rbx
0x18000fa35  mov     eax, r11d
0x18000fa38  jz      short loc_18000FA40
0x18000fa3a  mov     eax, [rdx+188h]
0x18000fa40  mov     [r14], eax
0x18000fa43  jmp     short loc_18000FA62
0x18000fa45  cmp     rax, rbx
0x18000fa48  jz      short loc_18000FA62
0x18000fa4a  mov     r8, r14
0x18000fa4d  call    BWritePfbToOutput
0x18000fa52  xor     r11d, r11d
0x18000fa55  mov     esi, eax
0x18000fa57  test    eax, eax
0x18000fa59  jz      short loc_18000FA62
0x18000fa5b  mov     [rdi+158h], rbx
0x18000fa62  cmp     [rdi+1A0h], r11d
0x18000fa69  jz      short loc_18000FA6E
0x18000fa6b  mov     [r14], r11d
0x18000fa6e  mov     eax, esi
0x18000fa70  jmp     loc_18000FE2F
0x18000fa75  test    r9, r9
0x18000fa78  jz      loc_18000FE2A
0x18000fa7e  mov     r8d, [rbp+arg_28]
0x18000fa82  test    r8d, r8d
0x18000fa85  jz      loc_18000FE2A
0x18000fa8b  mov     rcx, [rcx+0DC8h]
0x18000fa92  mov     esi, 1
0x18000fa97  mov     [rbp+var_8], rcx
0x18000fa9b  mov     ebx, esi
0x18000fa9d  mov     r12d, r11d
0x18000faa0  lea     rax, [rcx+400h]
0x18000faa7  mov     [rbp+var_18], rax
0x18000faab  lea     rax, [rcx+0C00h]
0x18000fab2  mov     [rbp+var_10], rax
0x18000fab6  or      ecx, 0FFFFFFFFh
0x18000fab9  mov     rax, [rbp+arg_30]
0x18000fabd  mov     [rax], r11d
0x18000fac0  mov     rax, [rbp+arg_38]
0x18000fac4  mov     [rax], r11d
0x18000fac7  mov     eax, [rdx+0C4h]
0x18000facd  cmp     eax, 7
0x18000fad0  jz      short loc_18000FADD
0x18000fad2  cmp     eax, 0Ah
0x18000fad5  jz      short loc_18000FADD
0x18000fad7  movzx   r14d, cx
0x18000fadb  jmp     short loc_18000FAEC
0x18000fadd  mov     r14d, [r13+0DECh]
0x18000fae4  shr     r14d, 17h
0x18000fae8  and     r14w, si
0x18000faec  test    r8d, r8d
0x18000faef  jle     loc_18000FE26
0x18000faf5  movzx   r15d, r14w
0x18000faf9  mov     eax, [rdi+0C4h]
0x18000faff  cmp     eax, 7
0x18000fb02  jz      short loc_18000FB45
0x18000fb04  cmp     eax, 0Ah
0x18000fb07  jz      short loc_18000FB45
0x18000fb09  movzx   edx, word ptr [r9]
0x18000fb0d  mov     rcx, rdi
0x18000fb10  call    WSetSoiMapping
0x18000fb15  mov     r8d, [rbp+arg_28]
0x18000fb19  movzx   ecx, ax
0x18000fb1c  mov     r10, [rbp+arg_10]
0x18000fb20  mov     edx, 0FFh
0x18000fb25  and     cx, dx
0x18000fb28  shr     ax, 8
0x18000fb2c  mov     [rbp+var_1C], ecx
0x18000fb2f  xor     r11d, r11d
0x18000fb32  or      ecx, 0FFFFFFFFh
0x18000fb35  movzx   r14d, ax
0x18000fb39  cmp     r15w, cx
0x18000fb3d  jnz     short loc_18000FB49
0x18000fb3f  movzx   r15d, ax
0x18000fb43  jmp     short loc_18000FB49
0x18000fb45  mov     [rbp+var_1C], r11d
0x18000fb49  mov     eax, 0FEh
0x18000fb4e  cmp     r12w, ax
0x18000fb52  jg      short loc_18000FB5E
0x18000fb54  cmp     r14w, r15w
0x18000fb58  jz      loc_18000FC94
0x18000fb5e  cmp     dword ptr [rdi+0C4h], 6
0x18000fb65  jnz     short loc_18000FB86
0x18000fb67  test    r15w, r15w
0x18000fb6b  jz      short loc_18000FB86
0x18000fb6d  xor     r8d, r8d
0x18000fb70  mov     [rsp+80h+var_60], r10
0x18000fb75  movzx   r9d, r15w
0x18000fb79  mov     rdx, rdi
0x18000fb7c  mov     rcx, r13
0x18000fb7f  call    PNewSubFontByCopy
0x18000fb84  jmp     short loc_18000FB98
0x18000fb86  mov     r9, r10
0x18000fb89  movzx   r8d, r15w
0x18000fb8d  mov     rdx, rdi
0x18000fb90  mov     rcx, r13
0x18000fb93  call    PNewSubFont
0x18000fb98  xor     r15d, r15d
0x18000fb9b  mov     r8, rax
0x18000fb9e  test    rax, rax
0x18000fba1  jz      loc_18000FE23
0x18000fba7  mov     edx, [rdi+0C4h]
0x18000fbad  cmp     [rbp+arg_40], r15d
0x18000fbb4  jz      short loc_18000FBFB
0x18000fbb6  cmp     edx, 7
0x18000fbb9  jz      short loc_18000FBC4
0x18000fbbb  mov     rax, [rbp+var_18]
0x18000fbbf  cmp     edx, 0Ah
0x18000fbc2  jnz     short loc_18000FBC7
0x18000fbc4  mov     rax, r15
0x18000fbc7  mov     r10, [rbp+var_10]
0x18000fbcb  lea     rcx, [rbp+var_20]
0x18000fbcf  mov     [rsp+80h+var_40], rcx
0x18000fbd4  lea     rcx, [rbp+arg_8]
0x18000fbd8  mov     [rsp+80h+var_48], rcx
0x18000fbdd  mov     [rsp+80h+var_50], r10
0x18000fbe2  mov     [rsp+80h+var_58], rax
0x18000fbe7  mov     rax, [rbp+var_8]
0x18000fbeb  movsx   r9d, r12w
0x18000fbef  mov     [rsp+80h+var_60], rax
0x18000fbf4  call    BUFOVMNeeded
0x18000fbf9  jmp     short loc_18000FC55
0x18000fbfb  lea     eax, [rdx-7]
0x18000fbfe  test    eax, 0FFFFFFFCh
0x18000fc03  jnz     short loc_18000FC0D
0x18000fc05  mov     rcx, r15
0x18000fc08  cmp     edx, 8
0x18000fc0b  jnz     short loc_18000FC11
0x18000fc0d  mov     rcx, [rbp+var_18]
0x18000fc11  mov     r10, [rbp+var_10]
0x18000fc15  lea     rax, [rbp+var_20]
0x18000fc19  mov     [rsp+80h+var_30], r15w
0x18000fc1f  mov     [rsp+80h+var_38], rax
0x18000fc24  lea     rax, [rbp+arg_8]
0x18000fc28  mov     [rsp+80h+var_40], rax
0x18000fc2d  mov     rax, [rbp+arg_20]
0x18000fc31  mov     [rsp+80h+var_48], rax
0x18000fc36  mov     rax, [rbp+var_8]
0x18000fc3a  mov     [rsp+80h+var_50], r10
0x18000fc3f  mov     [rsp+80h+var_58], rcx
0x18000fc44  mov     rcx, r13
0x18000fc47  movsx   r9d, r12w
0x18000fc4b  mov     [rsp+80h+var_60], rax
0x18000fc50  call    BUFODownload
0x18000fc55  xor     r11d, r11d
0x18000fc58  mov     ebx, eax
0x18000fc5a  test    eax, eax
0x18000fc5c  jz      loc_18000FE26
0x18000fc62  mov     rcx, [rbp+arg_30]
0x18000fc66  movzx   r15d, r14w
0x18000fc6a  mov     eax, [rbp+arg_8]
0x18000fc6d  add     [rcx], eax
0x18000fc6f  mov     rcx, [rbp+arg_38]
0x18000fc73  mov     eax, [rbp+var_20]
0x18000fc76  add     [rcx], eax
0x18000fc78  mov     rcx, [rbp+arg_20]
0x18000fc7c  test    rcx, rcx
0x18000fc7f  jz      short loc_18000FC8D
0x18000fc81  movsx   rax, r12w
0x18000fc85  lea     rcx, [rcx+rax*2]
0x18000fc89  mov     [rbp+arg_20], rcx
0x18000fc8d  mov     r8d, [rbp+arg_28]
0x18000fc91  mov     r12d, r11d
0x18000fc94  sub     r8d, esi
0x18000fc97  movsx   rcx, r12w
0x18000fc9b  cmp     dword ptr [rdi+0C4h], 9
0x18000fca2  mov     [rbp+arg_28], r8d
0x18000fca6  jz      short loc_18000FCC5
0x18000fca8  mov     r9d, [rbp+var_1C]
0x18000fcac  lea     rdx, off_1800730E0; ".notdef"
0x18000fcb3  movzx   eax, r9w
0x18000fcb7  mov     rax, [rdx+rax*8]
0x18000fcbb  mov     rdx, [rbp+var_18]
0x18000fcbf  mov     [rdx+rcx*8], rax
0x18000fcc3  jmp     short loc_18000FCC9
0x18000fcc5  mov     r9d, [rbp+var_1C]
0x18000fcc9  mov     rax, [rbp+var_10]
0x18000fccd  add     r12w, si
0x18000fcd1  mov     rdx, [rbp+var_8]
0x18000fcd5  mov     r10, [rbp+arg_10]
0x18000fcd9  mov     [rax+rcx*2], r9w
0x18000fcde  mov     r9, [rbp+arg_18]
0x18000fce2  mov     eax, [r9]
0x18000fce5  add     r9, 18h
0x18000fce9  mov     [rdx+rcx*4], eax
0x18000fcec  mov     [rbp+arg_18], r9
0x18000fcf0  test    r8d, r8d
0x18000fcf3  jg      loc_18000FAF9
0x18000fcf9  test    ebx, ebx
0x18000fcfb  jz      loc_18000FE26
0x18000fd01  test    r12w, r12w
0x18000fd05  jz      loc_18000FE26
0x18000fd0b  cmp     dword ptr [rdi+0C4h], 6
0x18000fd12  jnz     short loc_18000FD36
0x18000fd14  test    r14w, r14w
0x18000fd18  jz      short loc_18000FD36
0x18000fd1a  mov     r9, r10
0x18000fd1d  mov     [rsp+80h+var_60], r10
0x18000fd22  movzx   r9d, r14w
0x18000fd26  xor     r8d, r8d
0x18000fd29  mov     rdx, rdi
0x18000fd2c  mov     rcx, r13
0x18000fd2f  call    PNewSubFontByCopy
0x18000fd34  jmp     short loc_18000FD49
0x18000fd36  mov     r9, [rbp+arg_10]
0x18000fd3a  movzx   r8d, r14w
0x18000fd3e  mov     rdx, rdi
0x18000fd41  mov     rcx, r13
0x18000fd44  call    PNewSubFont
0x18000fd49  xor     r15d, r15d
0x18000fd4c  mov     r8, rax
0x18000fd4f  test    rax, rax
0x18000fd52  jz      loc_18000FE2F
0x18000fd58  mov     edx, [rdi+0C4h]
0x18000fd5e  lea     eax, [rdx-7]
0x18000fd61  cmp     [rbp+arg_40], r15d
0x18000fd68  jz      short loc_18000FDB1
0x18000fd6a  test    eax, 0FFFFFFFCh
0x18000fd6f  jnz     short loc_18000FD79
0x18000fd71  mov     rax, r15
0x18000fd74  cmp     edx, 8
0x18000fd77  jnz     short loc_18000FD7D
0x18000fd79  mov     rax, [rbp+var_18]
0x18000fd7d  mov     r10, [rbp+var_10]
0x18000fd81  lea     rcx, [rbp+var_20]
0x18000fd85  mov     [rsp+80h+var_40], rcx
0x18000fd8a  lea     rcx, [rbp+arg_8]
0x18000fd8e  mov     [rsp+80h+var_48], rcx
0x18000fd93  mov     [rsp+80h+var_50], r10
0x18000fd98  mov     [rsp+80h+var_58], rax
0x18000fd9d  mov     rax, [rbp+var_8]
0x18000fda1  movsx   r9d, r12w
0x18000fda5  mov     [rsp+80h+var_60], rax
0x18000fdaa  call    BUFOVMNeeded
0x18000fdaf  jmp     short loc_18000FE09
0x18000fdb1  test    eax, 0FFFFFFFCh
0x18000fdb6  jnz     short loc_18000FDC1
0x18000fdb8  cmp     edx, 8
0x18000fdbb  jz      short loc_18000FDC1
0x18000fdbd  mov     [rbp+var_18], r15
0x18000fdc1  mov     [rsp+80h+var_30], r15w
0x18000fdc7  lea     rax, [rbp+var_20]
0x18000fdcb  mov     [rsp+80h+var_38], rax
0x18000fdd0  mov     rcx, r13
0x18000fdd3  lea     rax, [rbp+arg_8]
0x18000fdd7  movsx   r9d, r12w
0x18000fddb  mov     [rsp+80h+var_40], rax
0x18000fde0  mov     rax, [rbp+arg_20]
0x18000fde4  mov     [rsp+80h+var_48], rax
0x18000fde9  mov     rax, [rbp+var_10]
0x18000fded  mov     [rsp+80h+var_50], rax
0x18000fdf2  mov     rax, [rbp+var_18]
0x18000fdf6  mov     [rsp+80h+var_58], rax
0x18000fdfb  mov     rax, [rbp+var_8]
0x18000fdff  mov     [rsp+80h+var_60], rax
0x18000fe04  call    BUFODownload
0x18000fe09  mov     ebx, eax
0x18000fe0b  test    eax, eax
0x18000fe0d  jz      short loc_18000FE26
0x18000fe0f  mov     rcx, [rbp+arg_30]
0x18000fe13  mov     eax, [rbp+arg_8]
0x18000fe16  add     [rcx], eax
0x18000fe18  mov     rcx, [rbp+arg_38]
0x18000fe1c  mov     eax, [rbp+var_20]
0x18000fe1f  add     [rcx], eax
0x18000fe21  jmp     short loc_18000FE26
0x18000fe23  mov     ebx, r15d
0x18000fe26  mov     eax, ebx
0x18000fe28  jmp     short loc_18000FE2F
0x18000fe2a  mov     eax, 1
0x18000fe2f  mov     rbx, [rsp+80h+arg_0]
0x18000fe37  add     rsp, 80h
0x18000fe3e  pop     r15
0x18000fe40  pop     r14
0x18000fe42  pop     r13
  ... truncated ...
```
