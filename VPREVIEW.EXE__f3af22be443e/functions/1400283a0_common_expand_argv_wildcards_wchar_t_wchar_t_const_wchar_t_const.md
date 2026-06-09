# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x1400283a0`
- end: `0x1400285dd`
- name: `??$common_expand_argv_wildcards@_W@@YAHQEAPEA_WQEAPEAPEA_W@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140005090`
- `0x140006534`
- `0x1400065a8`
- `0x14000bffc`
- `0x1400217f0`
- `0x140024238`
- `0x1400283a0`
- `0x14005a8a0`
- `0x14005c580`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall common_expand_argv_wildcards<wchar_t>(ULONGLONG a1, ULONGLONG *a2, __int64 a3)
{
  char v5; // r14
  char v6; // r13
  ULONGLONG v7; // r12
  ULONGLONG *v8; // rsi
  __int64 v9; // rax
  ULONGLONG *v10; // rdx
  ULONGLONG *v11; // rcx
  __int64 result; // rax
  ULONGLONG v13; // rcx
  ULONGLONG v14; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v15[2]; // [rsp+38h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+48h] [rbp-38h] BYREF
  ULONGLONG *v17; // [rsp+58h] [rbp-28h]
  __int64 v18; // [rsp+60h] [rbp-20h]
  _QWORD *v19; // [rsp+68h] [rbp-18h]
  __int64 v20; // [rsp+70h] [rbp-10h]

  if ( !*a2 )
    sub_140005090(19153742);
  if ( (dword_140078D40 & 0x10) != 0 )
  {
    v15[0] = *a2;
    v14 = a1;
    v17 = &v14;
    v18 = 8;
    v19 = v15;
    v20 = 8;
    sub_14000BFFC((REGHANDLE *)qword_140076110, (const EVENT_DESCRIPTOR *)qword_1400652F0, a3, 3u, &v16);
  }
  v5 = 0;
  sub_1400065A8(v15, a1 + 328);
  v6 = *(_BYTE *)(a1 + 96);
  if ( !v6 )
  {
    v7 = *a2;
    *a2 = 0;
    v16.Ptr = v7;
    *(_QWORD *)&v16.Size = a1;
    if ( a1 )
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)a1 + 8LL))(a1);
    v8 = *(ULONGLONG **)(a1 + 496);
    v17 = v8;
    if ( v8 )
      (*(void (__fastcall **)(ULONGLONG *))*v8)(v8);
    v5 = 1;
    v9 = ++*(_QWORD *)(a1 + 104);
    v18 = v9;
    v10 = *(ULONGLONG **)(a1 + 128);
    if ( v10 == *(ULONGLONG **)(a1 + 136) )
    {
      sub_1400217F0(a1 + 120, v10, &v16);
      v11 = v17;
    }
    else
    {
      *v10 = v7;
      v16 = 0;
      v10[1] = a1;
      v11 = 0;
      v10[2] = (ULONGLONG)v8;
      v10[3] = v9;
      *(_QWORD *)(a1 + 128) += 32LL;
    }
    if ( v11 )
      (*(void (__fastcall **)(ULONGLONG *))(*v11 + 8))(v11);
    if ( *(_QWORD *)&v16.Size )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&v16.Size + 16LL))(*(_QWORD *)&v16.Size);
    if ( v16.Ptr )
      (*(void (__fastcall **)(ULONGLONG))(*(_QWORD *)v16.Ptr + 16LL))(v16.Ptr);
    *(_BYTE *)(a1 + 100) = 0;
    if ( *(_BYTE *)(a1 + 98)
      || *(_QWORD *)(a1 + 168) == (__int64)(*(_QWORD *)(a1 + 152) - *(_QWORD *)(a1 + 144)) >> 5
      && *(_QWORD *)(a1 + 120) == *(_QWORD *)(a1 + 128) )
    {
      v5 = 0;
    }
    else
    {
      *(_BYTE *)(a1 + 98) = 1;
    }
  }
  result = sub_140006534(v15);
  if ( v6 )
  {
    result = sub_140024238(a2, 2);
    v13 = *a2;
    *a2 = 0;
    if ( v13 )
      result = (*(__int64 (__fastcall **)(ULONGLONG))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( v5 )
    return (*(__int64 (__fastcall **)(ULONGLONG))(*(_QWORD *)a1 + 48LL))(a1);
  return result;
}

```

## disassembly

```asm
0x1400283a0  mov     [rsp-38h+arg_10], rbx
0x1400283a5  push    rbp
0x1400283a6  push    rsi
0x1400283a7  push    rdi
0x1400283a8  push    r12
0x1400283aa  push    r13
0x1400283ac  push    r14
0x1400283ae  push    r15
0x1400283b0  mov     rbp, rsp
0x1400283b3  sub     rsp, 80h
0x1400283ba  mov     rax, cs:__security_cookie
0x1400283c1  xor     rax, rsp
0x1400283c4  mov     [rbp+var_8], rax
0x1400283c8  mov     rdi, rdx
0x1400283cb  mov     rbx, rcx
0x1400283ce  mov     rax, [rdx]
0x1400283d1  xor     esi, esi
0x1400283d3  test    rax, rax
0x1400283d6  jz      loc_1400285D0
0x1400283dc  test    byte ptr cs:dword_140078D40, 10h
0x1400283e3  jz      short loc_14002842D
0x1400283e5  mov     [rbp+var_48], rax
0x1400283e9  mov     [rbp+var_50], rcx
0x1400283ed  lea     rax, [rbp+var_50]
0x1400283f1  mov     [rbp+var_28], rax
0x1400283f5  mov     [rbp+var_20], 8
0x1400283fd  lea     rax, [rbp+var_48]
0x140028401  mov     [rbp+var_18], rax
0x140028405  mov     [rbp+var_10], 8
0x14002840d  lea     rax, [rbp+var_38]
0x140028411  mov     [rsp+80h+var_60], rax
0x140028416  lea     r9d, [rsi+3]
0x14002841a  lea     rdx, qword_1400652F0
0x140028421  lea     rcx, qword_140076110
0x140028428  call    sub_14000BFFC
0x14002842d  mov     r14b, sil
0x140028430  lea     rdx, [rbx+148h]
0x140028437  lea     rcx, [rbp+var_48]
0x14002843b  call    sub_1400065A8
0x140028440  mov     r13b, [rbx+60h]
0x140028444  test    r13b, r13b
0x140028447  jnz     loc_140028560
0x14002844d  mov     r12, [rdi]
0x140028450  mov     [rdi], rsi
0x140028453  mov     qword ptr [rbp+var_38], r12
0x140028457  mov     qword ptr [rbp+var_38+8], rbx
0x14002845b  test    rbx, rbx
0x14002845e  jz      short loc_140028470
0x140028460  mov     rax, [rbx]
0x140028463  mov     rcx, rbx
0x140028466  mov     rax, [rax+8]
0x14002846a  call    cs:__guard_dispatch_icall_fptr
0x140028470  mov     rsi, [rbx+1F0h]
0x140028477  mov     [rbp+var_28], rsi
0x14002847b  test    rsi, rsi
0x14002847e  jz      short loc_14002848F
0x140028480  mov     rax, [rsi]
0x140028483  mov     rcx, rsi
0x140028486  mov     rax, [rax]
0x140028489  call    cs:__guard_dispatch_icall_fptr
0x14002848f  mov     r14d, 1
0x140028495  add     [rbx+68h], r14
0x140028499  mov     rax, [rbx+68h]
0x14002849d  mov     [rbp+var_20], rax
0x1400284a1  mov     rdx, [rbx+80h]
0x1400284a8  cmp     rdx, [rbx+88h]
0x1400284af  jz      short loc_1400284D4
0x1400284b1  mov     [rdx], r12
0x1400284b4  xorps   xmm0, xmm0
0x1400284b7  movdqu  [rbp+var_38], xmm0
0x1400284bc  mov     [rdx+8], rbx
0x1400284c0  xor     ecx, ecx
0x1400284c2  mov     [rdx+10h], rsi
0x1400284c6  mov     [rdx+18h], rax
0x1400284ca  add     qword ptr [rbx+80h], 20h ; ' '
0x1400284d2  jmp     short loc_1400284E5
0x1400284d4  lea     r8, [rbp+var_38]
0x1400284d8  lea     rcx, [rbx+78h]
0x1400284dc  call    sub_1400217F0
0x1400284e1  mov     rcx, [rbp+var_28]
0x1400284e5  xor     esi, esi
0x1400284e7  test    rcx, rcx
0x1400284ea  jz      short loc_1400284F9
0x1400284ec  mov     rax, [rcx]
0x1400284ef  mov     rax, [rax+8]
0x1400284f3  call    cs:__guard_dispatch_icall_fptr
0x1400284f9  mov     rcx, qword ptr [rbp+var_38+8]
0x1400284fd  test    rcx, rcx
0x140028500  jz      short loc_14002850F
0x140028502  mov     rax, [rcx]
0x140028505  mov     rax, [rax+10h]
0x140028509  call    cs:__guard_dispatch_icall_fptr
0x14002850f  mov     rcx, qword ptr [rbp+var_38]
0x140028513  test    rcx, rcx
0x140028516  jz      short loc_140028525
0x140028518  mov     rax, [rcx]
0x14002851b  mov     rax, [rax+10h]
0x14002851f  call    cs:__guard_dispatch_icall_fptr
0x140028525  mov     [rbx+64h], sil
0x140028529  cmp     [rbx+62h], sil
0x14002852d  jnz     short loc_14002855D
0x14002852f  mov     rax, [rbx+98h]
0x140028536  sub     rax, [rbx+90h]
0x14002853d  sar     rax, 5
0x140028541  cmp     [rbx+0A8h], rax
0x140028548  jnz     short loc_140028557
0x14002854a  mov     rax, [rbx+80h]
0x140028551  cmp     [rbx+78h], rax
0x140028555  jz      short loc_14002855D
0x140028557  mov     [rbx+62h], r14b
0x14002855b  jmp     short loc_140028560
0x14002855d  mov     r14b, sil
0x140028560  lea     rcx, [rbp+var_48]
0x140028564  call    sub_140006534
0x140028569  test    r13b, r13b
0x14002856c  jz      short loc_140028593
0x14002856e  mov     edx, 2
0x140028573  mov     rcx, rdi
0x140028576  call    sub_140024238
0x14002857b  mov     rcx, [rdi]
0x14002857e  mov     [rdi], rsi
0x140028581  test    rcx, rcx
0x140028584  jz      short loc_140028593
0x140028586  mov     rax, [rcx]
0x140028589  mov     rax, [rax+10h]
0x14002858d  call    cs:__guard_dispatch_icall_fptr
0x140028593  test    r14b, r14b
0x140028596  jz      short loc_1400285A9
0x140028598  mov     rax, [rbx]
0x14002859b  mov     rcx, rbx
0x14002859e  mov     rax, [rax+30h]
0x1400285a2  call    cs:__guard_dispatch_icall_fptr
0x1400285a8  nop
0x1400285a9  mov     rcx, [rbp+var_8]
0x1400285ad  xor     rcx, rsp; StackCookie
0x1400285b0  call    __security_check_cookie
0x1400285b5  mov     rbx, [rsp+80h+arg_10]
0x1400285bd  add     rsp, 80h
0x1400285c4  pop     r15
0x1400285c6  pop     r14
0x1400285c8  pop     r13
0x1400285ca  pop     r12
0x1400285cc  pop     rdi
0x1400285cd  pop     rsi
0x1400285ce  pop     rbp
0x1400285cf  retn
0x1400285d0  xor     edx, edx
0x1400285d2  mov     ecx, 124434Eh
0x1400285d7  call    sub_140005090
```
