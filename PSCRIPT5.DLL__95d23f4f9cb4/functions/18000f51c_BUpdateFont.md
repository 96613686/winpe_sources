# BUpdateFont

- ea: `0x18000f51c`
- end: `0x18000f992`
- name: `BUpdateFont`
- size: `1142`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x18000ee40`

## callees

- `0x18000f51c`
- `0x18000f998`
- `0x180010984`
- `0x180010b48`
- `0x1800113f0`
- `0x18001d924`
- `0x18001db1c`

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
  unsigned __int16 v22; // r14
  unsigned __int16 v23; // r15
  int v24; // eax
  unsigned __int16 v25; // ax
  int v26; // ecx
  unsigned __int16 v27; // ax
  __int64 v28; // rax
  int v29; // r8d
  int v30; // edx
  __int64 v31; // rax
  unsigned int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int16 v35; // r9
  __int64 v36; // rdx
  int v37; // r8d
  int v38; // edx
  int v39; // eax
  __int64 v40; // rax
  unsigned int v41; // eax
  int v42; // [rsp+60h] [rbp-20h] BYREF
  int v43; // [rsp+64h] [rbp-1Ch]
  __int64 v44; // [rsp+68h] [rbp-18h]
  __int64 v45; // [rsp+70h] [rbp-10h]
  __int64 v46; // [rsp+78h] [rbp-8h]
  int v47; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v48; // [rsp+D0h] [rbp+50h]
  _DWORD *v49; // [rsp+D8h] [rbp+58h]

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
          if ( v23 == 0xFFFF )
            v23 = v27;
        }
        if ( v20 > 254 || v22 != v23 )
        {
          if ( *(_DWORD *)(a2 + 196) == 6 && v23 )
            v28 = PNewSubFontByCopy(a1, a2, 0, v23, v9);
          else
            v28 = PNewSubFont(a1, a2, v23, v9);
          v29 = v28;
          if ( !v28 )
            return 0;
          v30 = *(_DWORD *)(a2 + 196);
          if ( a9 )
          {
            if ( v30 == 7 || (v31 = v44, v30 == 10) )
              v31 = 0;
            v32 = BUFOVMNeeded((unsigned int)&v47, v30, v29, v20, v46, v31, v45, (__int64)&v47, (__int64)&v42);
          }
          else
          {
            if ( ((v30 - 7) & 0xFFFFFFFC) != 0 || (v33 = 0, v30 == 8) )
              v33 = v44;
            v32 = BUFODownload(a1, v30, v28, v20, v46, v33, v45, a5, (__int64)&v47, (__int64)&v42, 0);
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
          *(_QWORD *)(v44 + 8LL * v20) = off_1800710E0[(unsigned __int16)v43];
        ++v20;
        v36 = v46;
        v9 = v48;
        *(_WORD *)(v45 + 2 * v34) = v35;
        a4 = (unsigned __int16 *)(v49 + 6);
        *(_DWORD *)(v36 + 4 * v34) = *v49;
        v49 = a4;
      }
      while ( v18 > 0 );
      if ( v19 && v20 )
      {
        if ( *(_DWORD *)(a2 + 196) == 6 && v22 )
          result = PNewSubFontByCopy(a1, a2, 0, v22, v9);
        else
          result = PNewSubFont(a1, a2, v22, v48);
        v37 = result;
        if ( !result )
          return result;
        v38 = *(_DWORD *)(a2 + 196);
        v39 = v38 - 7;
        if ( a9 )
        {
          if ( (v39 & 0xFFFFFFFC) != 0 || (v40 = 0, v38 == 8) )
            v40 = v44;
          v41 = BUFOVMNeeded((unsigned int)&v47, v38, v37, v20, v46, v40, v45, (__int64)&v47, (__int64)&v42);
        }
        else
        {
          if ( (v39 & 0xFFFFFFFC) == 0 && v38 != 8 )
            v44 = 0;
          v41 = BUFODownload(a1, v38, v37, v20, v46, v44, v45, a5, (__int64)&v47, (__int64)&v42, 0);
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
0x18000f51c  mov     [rsp-38h+arg_0], rbx
0x18000f521  mov     [rsp-38h+arg_18], r9
0x18000f526  mov     [rsp-38h+arg_10], r8
0x18000f52b  push    rbp
0x18000f52c  push    rsi
0x18000f52d  push    rdi
0x18000f52e  push    r12
0x18000f530  push    r13
0x18000f532  push    r14
0x18000f534  push    r15
0x18000f536  mov     rbp, rsp
0x18000f539  sub     rsp, 80h
0x18000f540  xor     r11d, r11d
0x18000f543  mov     r10, r8
0x18000f546  cmp     dword ptr [rdx+0C4h], 8
0x18000f54d  mov     rdi, rdx
0x18000f550  mov     r13, rcx
0x18000f553  mov     [rbp+arg_8], r11d
0x18000f557  mov     [rbp+var_20], r11d
0x18000f55b  jnz     short loc_18000F5BD
0x18000f55d  lea     esi, [r11+1]
0x18000f561  mov     rax, [rdx+158h]
0x18000f568  mov     ebx, 0FEFEh
0x18000f56d  mov     r14, [rbp+arg_30]
0x18000f571  cmp     [rbp+arg_40], r11d
0x18000f578  jz      short loc_18000F58D
0x18000f57a  cmp     rax, rbx
0x18000f57d  mov     eax, r11d
0x18000f580  jz      short loc_18000F588
0x18000f582  mov     eax, [rdx+188h]
0x18000f588  mov     [r14], eax
0x18000f58b  jmp     short loc_18000F5AA
0x18000f58d  cmp     rax, rbx
0x18000f590  jz      short loc_18000F5AA
0x18000f592  mov     r8, r14
0x18000f595  call    BWritePfbToOutput
0x18000f59a  xor     r11d, r11d
0x18000f59d  mov     esi, eax
0x18000f59f  test    eax, eax
0x18000f5a1  jz      short loc_18000F5AA
0x18000f5a3  mov     [rdi+158h], rbx
0x18000f5aa  cmp     [rdi+1A0h], r11d
0x18000f5b1  jz      short loc_18000F5B6
0x18000f5b3  mov     [r14], r11d
0x18000f5b6  mov     eax, esi
0x18000f5b8  jmp     loc_18000F977
0x18000f5bd  test    r9, r9
0x18000f5c0  jz      loc_18000F972
0x18000f5c6  mov     r8d, [rbp+arg_28]
0x18000f5ca  test    r8d, r8d
0x18000f5cd  jz      loc_18000F972
0x18000f5d3  mov     rcx, [rcx+0DC8h]
0x18000f5da  mov     esi, 1
0x18000f5df  mov     [rbp+var_8], rcx
0x18000f5e3  mov     ebx, esi
0x18000f5e5  mov     r12d, r11d
0x18000f5e8  lea     rax, [rcx+400h]
0x18000f5ef  mov     [rbp+var_18], rax
0x18000f5f3  lea     rax, [rcx+0C00h]
0x18000f5fa  mov     [rbp+var_10], rax
0x18000f5fe  or      ecx, 0FFFFFFFFh
0x18000f601  mov     rax, [rbp+arg_30]
0x18000f605  mov     [rax], r11d
0x18000f608  mov     rax, [rbp+arg_38]
0x18000f60c  mov     [rax], r11d
0x18000f60f  mov     eax, [rdx+0C4h]
0x18000f615  cmp     eax, 7
0x18000f618  jz      short loc_18000F625
0x18000f61a  cmp     eax, 0Ah
0x18000f61d  jz      short loc_18000F625
0x18000f61f  movzx   r14d, cx
0x18000f623  jmp     short loc_18000F634
0x18000f625  mov     r14d, [r13+0DECh]
0x18000f62c  shr     r14d, 17h
0x18000f630  and     r14w, si
0x18000f634  test    r8d, r8d
0x18000f637  jle     loc_18000F96E
0x18000f63d  movzx   r15d, r14w
0x18000f641  mov     eax, [rdi+0C4h]
0x18000f647  cmp     eax, 7
0x18000f64a  jz      short loc_18000F68D
0x18000f64c  cmp     eax, 0Ah
0x18000f64f  jz      short loc_18000F68D
0x18000f651  movzx   edx, word ptr [r9]
0x18000f655  mov     rcx, rdi
0x18000f658  call    WSetSoiMapping
0x18000f65d  mov     r8d, [rbp+arg_28]
0x18000f661  movzx   ecx, ax
0x18000f664  mov     r10, [rbp+arg_10]
0x18000f668  mov     edx, 0FFh
0x18000f66d  and     cx, dx
0x18000f670  shr     ax, 8
0x18000f674  mov     [rbp+var_1C], ecx
0x18000f677  xor     r11d, r11d
0x18000f67a  or      ecx, 0FFFFFFFFh
0x18000f67d  movzx   r14d, ax
0x18000f681  cmp     r15w, cx
0x18000f685  jnz     short loc_18000F691
0x18000f687  movzx   r15d, ax
0x18000f68b  jmp     short loc_18000F691
0x18000f68d  mov     [rbp+var_1C], r11d
0x18000f691  mov     eax, 0FEh
0x18000f696  cmp     r12w, ax
0x18000f69a  jg      short loc_18000F6A6
0x18000f69c  cmp     r14w, r15w
0x18000f6a0  jz      loc_18000F7DC
0x18000f6a6  cmp     dword ptr [rdi+0C4h], 6
0x18000f6ad  jnz     short loc_18000F6CE
0x18000f6af  test    r15w, r15w
0x18000f6b3  jz      short loc_18000F6CE
0x18000f6b5  xor     r8d, r8d
0x18000f6b8  mov     [rsp+80h+var_60], r10
0x18000f6bd  movzx   r9d, r15w
0x18000f6c1  mov     rdx, rdi
0x18000f6c4  mov     rcx, r13
0x18000f6c7  call    PNewSubFontByCopy
0x18000f6cc  jmp     short loc_18000F6E0
0x18000f6ce  mov     r9, r10
0x18000f6d1  movzx   r8d, r15w
0x18000f6d5  mov     rdx, rdi
0x18000f6d8  mov     rcx, r13
0x18000f6db  call    PNewSubFont
0x18000f6e0  xor     r15d, r15d
0x18000f6e3  mov     r8, rax
0x18000f6e6  test    rax, rax
0x18000f6e9  jz      loc_18000F96B
0x18000f6ef  mov     edx, [rdi+0C4h]
0x18000f6f5  cmp     [rbp+arg_40], r15d
0x18000f6fc  jz      short loc_18000F743
0x18000f6fe  cmp     edx, 7
0x18000f701  jz      short loc_18000F70C
0x18000f703  mov     rax, [rbp+var_18]
0x18000f707  cmp     edx, 0Ah
0x18000f70a  jnz     short loc_18000F70F
0x18000f70c  mov     rax, r15
0x18000f70f  mov     r10, [rbp+var_10]
0x18000f713  lea     rcx, [rbp+var_20]
0x18000f717  mov     [rsp+80h+var_40], rcx
0x18000f71c  lea     rcx, [rbp+arg_8]
0x18000f720  mov     [rsp+80h+var_48], rcx
0x18000f725  mov     [rsp+80h+var_50], r10
0x18000f72a  mov     [rsp+80h+var_58], rax
0x18000f72f  mov     rax, [rbp+var_8]
0x18000f733  movsx   r9d, r12w
0x18000f737  mov     [rsp+80h+var_60], rax
0x18000f73c  call    BUFOVMNeeded
0x18000f741  jmp     short loc_18000F79D
0x18000f743  lea     eax, [rdx-7]
0x18000f746  test    eax, 0FFFFFFFCh
0x18000f74b  jnz     short loc_18000F755
0x18000f74d  mov     rcx, r15
0x18000f750  cmp     edx, 8
0x18000f753  jnz     short loc_18000F759
0x18000f755  mov     rcx, [rbp+var_18]
0x18000f759  mov     r10, [rbp+var_10]
0x18000f75d  lea     rax, [rbp+var_20]
0x18000f761  mov     [rsp+80h+var_30], r15w
0x18000f767  mov     [rsp+80h+var_38], rax
0x18000f76c  lea     rax, [rbp+arg_8]
0x18000f770  mov     [rsp+80h+var_40], rax
0x18000f775  mov     rax, [rbp+arg_20]
0x18000f779  mov     [rsp+80h+var_48], rax
0x18000f77e  mov     rax, [rbp+var_8]
0x18000f782  mov     [rsp+80h+var_50], r10
0x18000f787  mov     [rsp+80h+var_58], rcx
0x18000f78c  mov     rcx, r13
0x18000f78f  movsx   r9d, r12w
0x18000f793  mov     [rsp+80h+var_60], rax
0x18000f798  call    BUFODownload
0x18000f79d  xor     r11d, r11d
0x18000f7a0  mov     ebx, eax
0x18000f7a2  test    eax, eax
0x18000f7a4  jz      loc_18000F96E
0x18000f7aa  mov     rcx, [rbp+arg_30]
0x18000f7ae  movzx   r15d, r14w
0x18000f7b2  mov     eax, [rbp+arg_8]
0x18000f7b5  add     [rcx], eax
0x18000f7b7  mov     rcx, [rbp+arg_38]
0x18000f7bb  mov     eax, [rbp+var_20]
0x18000f7be  add     [rcx], eax
0x18000f7c0  mov     rcx, [rbp+arg_20]
0x18000f7c4  test    rcx, rcx
0x18000f7c7  jz      short loc_18000F7D5
0x18000f7c9  movsx   rax, r12w
0x18000f7cd  lea     rcx, [rcx+rax*2]
0x18000f7d1  mov     [rbp+arg_20], rcx
0x18000f7d5  mov     r8d, [rbp+arg_28]
0x18000f7d9  mov     r12d, r11d
0x18000f7dc  sub     r8d, esi
0x18000f7df  movsx   rcx, r12w
0x18000f7e3  cmp     dword ptr [rdi+0C4h], 9
0x18000f7ea  mov     [rbp+arg_28], r8d
0x18000f7ee  jz      short loc_18000F80D
0x18000f7f0  mov     r9d, [rbp+var_1C]
0x18000f7f4  lea     rdx, off_1800710E0; ".notdef"
0x18000f7fb  movzx   eax, r9w
0x18000f7ff  mov     rax, [rdx+rax*8]
0x18000f803  mov     rdx, [rbp+var_18]
0x18000f807  mov     [rdx+rcx*8], rax
0x18000f80b  jmp     short loc_18000F811
0x18000f80d  mov     r9d, [rbp+var_1C]
0x18000f811  mov     rax, [rbp+var_10]
0x18000f815  add     r12w, si
0x18000f819  mov     rdx, [rbp+var_8]
0x18000f81d  mov     r10, [rbp+arg_10]
0x18000f821  mov     [rax+rcx*2], r9w
0x18000f826  mov     r9, [rbp+arg_18]
0x18000f82a  mov     eax, [r9]
0x18000f82d  add     r9, 18h
0x18000f831  mov     [rdx+rcx*4], eax
0x18000f834  mov     [rbp+arg_18], r9
0x18000f838  test    r8d, r8d
0x18000f83b  jg      loc_18000F641
0x18000f841  test    ebx, ebx
0x18000f843  jz      loc_18000F96E
0x18000f849  test    r12w, r12w
0x18000f84d  jz      loc_18000F96E
0x18000f853  cmp     dword ptr [rdi+0C4h], 6
0x18000f85a  jnz     short loc_18000F87E
0x18000f85c  test    r14w, r14w
0x18000f860  jz      short loc_18000F87E
0x18000f862  mov     r9, r10
0x18000f865  mov     [rsp+80h+var_60], r10
0x18000f86a  movzx   r9d, r14w
0x18000f86e  xor     r8d, r8d
0x18000f871  mov     rdx, rdi
0x18000f874  mov     rcx, r13
0x18000f877  call    PNewSubFontByCopy
0x18000f87c  jmp     short loc_18000F891
0x18000f87e  mov     r9, [rbp+arg_10]
0x18000f882  movzx   r8d, r14w
0x18000f886  mov     rdx, rdi
0x18000f889  mov     rcx, r13
0x18000f88c  call    PNewSubFont
0x18000f891  xor     r15d, r15d
0x18000f894  mov     r8, rax
0x18000f897  test    rax, rax
0x18000f89a  jz      loc_18000F977
0x18000f8a0  mov     edx, [rdi+0C4h]
0x18000f8a6  lea     eax, [rdx-7]
0x18000f8a9  cmp     [rbp+arg_40], r15d
0x18000f8b0  jz      short loc_18000F8F9
0x18000f8b2  test    eax, 0FFFFFFFCh
0x18000f8b7  jnz     short loc_18000F8C1
0x18000f8b9  mov     rax, r15
0x18000f8bc  cmp     edx, 8
0x18000f8bf  jnz     short loc_18000F8C5
0x18000f8c1  mov     rax, [rbp+var_18]
0x18000f8c5  mov     r10, [rbp+var_10]
0x18000f8c9  lea     rcx, [rbp+var_20]
0x18000f8cd  mov     [rsp+80h+var_40], rcx
0x18000f8d2  lea     rcx, [rbp+arg_8]
0x18000f8d6  mov     [rsp+80h+var_48], rcx
0x18000f8db  mov     [rsp+80h+var_50], r10
0x18000f8e0  mov     [rsp+80h+var_58], rax
0x18000f8e5  mov     rax, [rbp+var_8]
0x18000f8e9  movsx   r9d, r12w
0x18000f8ed  mov     [rsp+80h+var_60], rax
0x18000f8f2  call    BUFOVMNeeded
0x18000f8f7  jmp     short loc_18000F951
0x18000f8f9  test    eax, 0FFFFFFFCh
0x18000f8fe  jnz     short loc_18000F909
0x18000f900  cmp     edx, 8
0x18000f903  jz      short loc_18000F909
0x18000f905  mov     [rbp+var_18], r15
0x18000f909  mov     [rsp+80h+var_30], r15w
0x18000f90f  lea     rax, [rbp+var_20]
0x18000f913  mov     [rsp+80h+var_38], rax
0x18000f918  mov     rcx, r13
0x18000f91b  lea     rax, [rbp+arg_8]
0x18000f91f  movsx   r9d, r12w
0x18000f923  mov     [rsp+80h+var_40], rax
0x18000f928  mov     rax, [rbp+arg_20]
0x18000f92c  mov     [rsp+80h+var_48], rax
0x18000f931  mov     rax, [rbp+var_10]
0x18000f935  mov     [rsp+80h+var_50], rax
0x18000f93a  mov     rax, [rbp+var_18]
0x18000f93e  mov     [rsp+80h+var_58], rax
0x18000f943  mov     rax, [rbp+var_8]
0x18000f947  mov     [rsp+80h+var_60], rax
0x18000f94c  call    BUFODownload
0x18000f951  mov     ebx, eax
0x18000f953  test    eax, eax
0x18000f955  jz      short loc_18000F96E
0x18000f957  mov     rcx, [rbp+arg_30]
0x18000f95b  mov     eax, [rbp+arg_8]
0x18000f95e  add     [rcx], eax
0x18000f960  mov     rcx, [rbp+arg_38]
0x18000f964  mov     eax, [rbp+var_20]
0x18000f967  add     [rcx], eax
0x18000f969  jmp     short loc_18000F96E
0x18000f96b  mov     ebx, r15d
0x18000f96e  mov     eax, ebx
0x18000f970  jmp     short loc_18000F977
0x18000f972  mov     eax, 1
0x18000f977  mov     rbx, [rsp+80h+arg_0]
0x18000f97f  add     rsp, 80h
0x18000f986  pop     r15
0x18000f988  pop     r14
0x18000f98a  pop     r13
  ... truncated ...
```
