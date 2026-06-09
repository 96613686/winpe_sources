# CSimpleChecker::ProcessTheJunction(void)

- ea: `0x1004394f0`
- end: `0x100439748`
- name: `?ProcessTheJunction@CSimpleChecker@@UEAAJXZ`
- size: `600`
- prototype: `__int64 __fastcall(CSimpleChecker *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path`

## callees

- `0x1004394f0`

## pseudocode

```c
__int64 __fastcall CSimpleChecker::ProcessTheJunction(CSimpleChecker *this)
{
  __int64 v1; // rdi
  char v2; // bp
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int16 v8; // dx
  bool v9; // zf
  __int16 v11; // cx
  __int64 v12; // rdx
  __int16 v13; // cx
  __int64 v14; // rcx
  __int16 v15; // dx
  __int64 v16; // rcx
  __int16 v17; // dx

  v1 = *((_QWORD *)this + 40);
  v2 = 0;
  v4 = *((_QWORD *)this + 41);
  v5 = *((_QWORD *)this + 38);
  v6 = *((_QWORD *)this + 39);
  if ( *((_DWORD *)this + 90) > 1u )
    goto LABEL_16;
  if ( !v5 )
  {
    if ( !v1 )
      goto LABEL_41;
    v2 = 1;
    if ( v4 == v1 )
    {
      v14 = *((_QWORD *)this + 42);
      if ( v14 )
      {
        while ( 1 )
        {
          v15 = *(_WORD *)(v14 + 72);
          if ( (v15 & 0x4840) == 0 )
            break;
          v14 = *(_QWORD *)(v14 + 32);
          if ( !v14 )
            goto LABEL_41;
        }
        if ( (v15 & 0x100) == 0 )
          goto LABEL_16;
      }
      goto LABEL_41;
    }
    if ( v4 != *(_QWORD *)(v1 + 24) )
      goto LABEL_16;
    v11 = *(_WORD *)(v1 + 72);
    if ( (v11 & 0x20) != 0 )
      goto LABEL_16;
    v12 = *((_QWORD *)this + 42);
    if ( (v11 & 0x4840) == 0 )
    {
      for ( ; v12; v12 = *(_QWORD *)(v12 + 32) )
      {
        if ( (*(_BYTE *)(v12 + 72) & 0x40) == 0 )
          break;
      }
      (*(void (__fastcall **)(__int64))(v1 + 80))(v1);
      (*(void (__fastcall **)(__int64, __int64))(v4 + 80))(v4, v1);
      if ( (*(_WORD *)(v1 + 72) & 0x200) != 0 || (*(_WORD *)(v4 + 72) & 0x200) != 0 )
        goto LABEL_16;
      goto LABEL_41;
    }
    if ( !v12 )
      goto LABEL_41;
    while ( 1 )
    {
      v13 = *(_WORD *)(v12 + 72);
      if ( (v13 & 0x4840) == 0 )
        break;
      v12 = *(_QWORD *)(v12 + 32);
      if ( !v12 )
        goto LABEL_41;
    }
    v9 = (v13 & 0x100) == 0;
    goto LABEL_15;
  }
  v2 = 1;
  if ( v6 != v5 )
  {
    if ( v1 || v6 != *(_QWORD *)(v5 + 24) )
      goto LABEL_16;
    goto LABEL_41;
  }
  if ( !v1 )
    goto LABEL_41;
  if ( v4 != v1 )
  {
LABEL_16:
    *((_BYTE *)this + 520) = 0;
LABEL_17:
    *((_BYTE *)this + 513) = 1;
    return 0;
  }
  if ( (*(_WORD *)(v5 + 72) & 0x4840) == 0 )
  {
    (*(void (__fastcall **)(__int64))(v1 + 88))(v1);
    goto LABEL_41;
  }
  v7 = *((_QWORD *)this + 42);
  if ( v7 )
  {
    while ( 1 )
    {
      v8 = *(_WORD *)(v7 + 72);
      if ( (v8 & 0x4840) == 0 )
        break;
      v7 = *(_QWORD *)(v7 + 32);
      if ( !v7 )
        goto LABEL_41;
    }
    v9 = (v8 & 0x100) == 0;
LABEL_15:
    if ( !v9 )
      goto LABEL_41;
    goto LABEL_16;
  }
LABEL_41:
  if ( *((_DWORD *)this + 90) )
  {
    if ( v2 )
      goto LABEL_48;
    v16 = *((_QWORD *)this + 42);
    if ( v16 )
    {
      while ( 1 )
      {
        v17 = *(_WORD *)(v16 + 72);
        if ( (v17 & 0x4840) == 0 )
          break;
        v16 = *(_QWORD *)(v16 + 32);
        if ( !v16 )
          return 0;
      }
      if ( (v17 & 0x100) == 0 )
      {
LABEL_48:
        *((_BYTE *)this + 520) = 0;
        goto LABEL_17;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1004394f0  mov     [rsp+arg_0], rbx
0x1004394f5  mov     [rsp+arg_8], rbp
0x1004394fa  mov     [rsp+arg_10], rsi
0x1004394ff  push    rdi
0x100439500  push    r14
0x100439502  push    r15
0x100439504  sub     rsp, 20h
0x100439508  mov     rdi, [rcx+140h]
0x10043950f  xor     bpl, bpl
0x100439512  cmp     dword ptr [rcx+168h], 1
0x100439519  mov     rbx, rcx
0x10043951c  mov     rsi, [rcx+148h]
0x100439523  mov     rdx, [rcx+130h]
0x10043952a  mov     rax, [rcx+138h]
0x100439531  ja      loc_1004395BC
0x100439537  xor     r15d, r15d
0x10043953a  mov     r14d, 4840h
0x100439540  test    rdx, rdx
0x100439543  jz      loc_1004395F0
0x100439549  mov     bpl, 1
0x10043954c  cmp     rax, rdx
0x10043954f  jz      short loc_100439562
0x100439551  test    rdi, rdi
0x100439554  jnz     short loc_1004395BC
0x100439556  cmp     rax, [rdx+18h]
0x10043955a  jz      loc_1004396E9
0x100439560  jmp     short loc_1004395BC
0x100439562  test    rdi, rdi
0x100439565  jz      loc_1004396E9
0x10043956b  cmp     rsi, rdi
0x10043956e  jnz     short loc_1004395BC
0x100439570  test    [rdx+48h], r14w
0x100439575  jz      short loc_1004395E5
0x100439577  mov     rcx, [rcx+150h]
0x10043957e  test    rcx, rcx
0x100439581  jz      loc_1004396E9
0x100439587  nop     word ptr [rax+rax+00000000h]
0x100439590  movzx   edx, word ptr [rcx+48h]
0x100439594  movzx   eax, dx
0x100439597  and     ax, r14w
0x10043959b  cmp     r15w, ax
0x10043959f  jz      short loc_1004395AF
0x1004395a1  mov     rcx, [rcx+20h]
0x1004395a5  test    rcx, rcx
0x1004395a8  jnz     short loc_100439590
0x1004395aa  jmp     loc_1004396E9
0x1004395af  shr     dx, 8
0x1004395b3  test    bpl, dl
0x1004395b6  jnz     loc_1004396E9
0x1004395bc  mov     byte ptr [rbx+208h], 0
0x1004395c3  mov     byte ptr [rbx+201h], 1
0x1004395ca  mov     rbx, [rsp+38h+arg_0]
0x1004395cf  xor     eax, eax
0x1004395d1  mov     rbp, [rsp+38h+arg_8]
0x1004395d6  mov     rsi, [rsp+38h+arg_10]
0x1004395db  add     rsp, 20h
0x1004395df  pop     r15
0x1004395e1  pop     r14
0x1004395e3  pop     rdi
0x1004395e4  retn
0x1004395e5  mov     rcx, rdi
0x1004395e8  call    qword ptr [rdi+58h]
0x1004395eb  jmp     loc_1004396E9
0x1004395f0  test    rdi, rdi
0x1004395f3  jz      loc_1004396E9
0x1004395f9  mov     bpl, 1
0x1004395fc  cmp     rsi, rdi
0x1004395ff  jz      loc_1004396A8
0x100439605  cmp     rsi, [rdi+18h]
0x100439609  jnz     short loc_1004395BC
0x10043960b  movzx   ecx, word ptr [rdi+48h]
0x10043960f  movzx   eax, cl
0x100439612  shr     al, 5
0x100439615  test    bpl, al
0x100439618  jnz     short loc_1004395BC
0x10043961a  mov     rdx, [rbx+150h]
0x100439621  test    r14w, cx
0x100439625  jz      short loc_10043965B
0x100439627  test    rdx, rdx
0x10043962a  jz      loc_1004396E9
0x100439630  movzx   ecx, word ptr [rdx+48h]
0x100439634  movzx   eax, cx
0x100439637  and     ax, r14w
0x10043963b  cmp     r15w, ax
0x10043963f  jz      short loc_10043964F
0x100439641  mov     rdx, [rdx+20h]
0x100439645  test    rdx, rdx
0x100439648  jnz     short loc_100439630
0x10043964a  jmp     loc_1004396E9
0x10043964f  shr     cx, 8
0x100439653  test    bpl, cl
0x100439656  jmp     loc_1004395B6
0x10043965b  test    rdx, rdx
0x10043965e  jz      short loc_100439675
0x100439660  movzx   eax, byte ptr [rdx+48h]
0x100439664  shr     al, 6
0x100439667  test    bpl, al
0x10043966a  jz      short loc_100439675
0x10043966c  mov     rdx, [rdx+20h]
0x100439670  test    rdx, rdx
0x100439673  jnz     short loc_100439660
0x100439675  mov     rcx, rdi
0x100439678  call    qword ptr [rdi+50h]
0x10043967b  mov     rdx, rdi
0x10043967e  mov     rcx, rsi
0x100439681  call    qword ptr [rsi+50h]
0x100439684  movzx   eax, word ptr [rdi+48h]
0x100439688  shr     ax, 9
0x10043968c  test    bpl, al
0x10043968f  jnz     loc_1004395BC
0x100439695  movzx   eax, word ptr [rsi+48h]
0x100439699  shr     ax, 9
0x10043969d  test    bpl, al
0x1004396a0  jnz     loc_1004395BC
0x1004396a6  jmp     short loc_1004396E9
0x1004396a8  mov     rcx, [rcx+150h]
0x1004396af  test    rcx, rcx
0x1004396b2  jz      short loc_1004396E9
0x1004396b4  nop     dword ptr [rax+00h]
0x1004396b8  nop     dword ptr [rax+rax+00000000h]
0x1004396c0  movzx   edx, word ptr [rcx+48h]
0x1004396c4  movzx   eax, dx
0x1004396c7  and     ax, r14w
0x1004396cb  cmp     r15w, ax
0x1004396cf  jz      short loc_1004396DC
0x1004396d1  mov     rcx, [rcx+20h]
0x1004396d5  test    rcx, rcx
0x1004396d8  jnz     short loc_1004396C0
0x1004396da  jmp     short loc_1004396E9
0x1004396dc  shr     dx, 8
0x1004396e0  test    bpl, dl
0x1004396e3  jz      loc_1004395BC
0x1004396e9  cmp     [rbx+168h], r15d
0x1004396f0  jbe     loc_1004395CA
0x1004396f6  test    bpl, bpl
0x1004396f9  jnz     short loc_10043973C
0x1004396fb  mov     rcx, [rbx+150h]
0x100439702  test    rcx, rcx
0x100439705  jz      loc_1004395CA
0x10043970b  nop     dword ptr [rax+rax+00h]
0x100439710  movzx   edx, word ptr [rcx+48h]
0x100439714  movzx   eax, dx
0x100439717  and     ax, r14w
0x10043971b  cmp     r15w, ax
0x10043971f  jz      short loc_10043972F
0x100439721  mov     rcx, [rcx+20h]
0x100439725  test    rcx, rcx
0x100439728  jnz     short loc_100439710
0x10043972a  jmp     loc_1004395CA
0x10043972f  shr     dx, 8
0x100439733  test    dl, 1
0x100439736  jnz     loc_1004395CA
0x10043973c  mov     [rbx+208h], r15b
0x100439743  jmp     loc_1004395C3
```
