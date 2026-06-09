# BCalcTotalOEMDMSize

- ea: `0x180031c70`
- end: `0x180031de5`
- name: `BCalcTotalOEMDMSize`
- size: `373`
- prototype: `__int64 __fastcall(__int64, __int64 *, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800034bc`
- `0x180031654`

## callees

- `0x180002938`
- `0x180031c70`
- `0x1800321e4`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall BCalcTotalOEMDMSize(__int64 a1, __int64 *a2, _DWORD *a3)
{
  int v6; // ebp
  int v7; // r14d
  __int64 *i; // rbx
  __int64 v9; // rsi
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rax
  int v13; // ecx
  unsigned int (__fastcall *v14)(__int64, int *); // rax
  int v16; // [rsp+20h] [rbp-88h] BYREF
  __int64 v17; // [rsp+28h] [rbp-80h]
  __int64 v18; // [rsp+30h] [rbp-78h]
  __int64 v19; // [rsp+38h] [rbp-70h]
  int v20; // [rsp+60h] [rbp-48h]

  memset_0(&v16, 0, 0x48u);
  v6 = *((_DWORD *)a2 + 2);
  *a3 = 0;
  if ( !v6 )
    return 1;
  v7 = 0;
  for ( i = a2 + 3; ; i += 22 )
  {
    v9 = i[4];
    if ( v9 )
      break;
LABEL_20:
    if ( !--v6 )
    {
      *a3 = v7;
      return 1;
    }
  }
  v10 = *((_DWORD *)i + 12);
  if ( (v10 & 4) != 0 )
    goto LABEL_19;
  *((_DWORD *)i + 12) = v10 | 4;
  memset_0(&v16, 0, 0x48u);
  v11 = i[9];
  v12 = *a2;
  v16 = 72;
  v17 = v12;
  v18 = a1;
  v19 = v9;
  if ( !v11 )
  {
    if ( (*((_BYTE *)i + 100) & 2) == 0 )
    {
      v14 = (unsigned int (__fastcall *)(__int64, int *))PGetOemEntrypointAddress((__int64)i, 1u);
      if ( v14 )
      {
        if ( !v14(1, &v16) )
          goto LABEL_23;
        goto LABEL_17;
      }
    }
LABEL_19:
    v7 += *((_DWORD *)i + 16);
    goto LABEL_20;
  }
  if ( i[10] == *(_QWORD *)&IID_IPrintOemPS.Data1 && i[11] == *(_QWORD *)IID_IPrintOemPS.Data4
    || i[10] == *(_QWORD *)&IID_IPrintOemPS2.Data1 && i[11] == *(_QWORD *)IID_IPrintOemPS2.Data4 )
  {
    v13 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v11 + 32LL))(v11, 1, &v16);
    if ( (int)(v13 + 0x80000000) < 0 || v13 == -2147467263 )
    {
      if ( ~v13 < 0 )
      {
LABEL_17:
        if ( (unsigned int)(v20 - 1) <= 0xA )
          goto LABEL_23;
        *((_DWORD *)i + 16) = v20;
        goto LABEL_19;
      }
      goto LABEL_19;
    }
  }
LABEL_23:
  *((_DWORD *)i + 12) &= ~4u;
  return 0;
}

```

## disassembly

```asm
0x180031c70  push    rbx
0x180031c72  push    rbp
0x180031c73  push    rsi
0x180031c74  push    r12
0x180031c76  push    r13
0x180031c78  push    r14
0x180031c7a  push    r15
0x180031c7c  sub     rsp, 70h
0x180031c80  mov     r15, rdx
0x180031c83  mov     r12, r8
0x180031c86  xor     edx, edx; Val
0x180031c88  mov     r13, rcx
0x180031c8b  lea     rcx, [rsp+0A8h+var_88]; void *
0x180031c90  lea     r8d, [rdx+48h]; Size
0x180031c94  call    memset_0
0x180031c99  mov     ebp, [r15+8]
0x180031c9d  mov     dword ptr [r12], 0
0x180031ca5  test    ebp, ebp
0x180031ca7  jz      loc_180031DC7
0x180031cad  xor     r14d, r14d
0x180031cb0  lea     rbx, [r15+18h]
0x180031cb4  mov     rsi, [rbx+20h]
0x180031cb8  test    rsi, rsi
0x180031cbb  jz      loc_180031DB3
0x180031cc1  mov     eax, [rbx+30h]
0x180031cc4  test    al, 4
0x180031cc6  jnz     loc_180031DAF
0x180031ccc  xor     edx, edx; Val
0x180031cce  lea     rcx, [rsp+0A8h+var_88]; void *
0x180031cd3  or      eax, 4
0x180031cd6  mov     [rbx+30h], eax
0x180031cd9  lea     r8d, [rdx+48h]; Size
0x180031cdd  call    memset_0
0x180031ce2  mov     rcx, [rbx+48h]
0x180031ce6  mov     rax, [r15]
0x180031ce9  mov     [rsp+0A8h+var_88], 48h ; 'H'
0x180031cf1  mov     [rsp+0A8h+var_80], rax
0x180031cf6  mov     [rsp+0A8h+var_78], r13
0x180031cfb  mov     [rsp+0A8h+var_70], rsi
0x180031d00  test    rcx, rcx
0x180031d03  jz      short loc_180031D75
0x180031d05  mov     rax, [rbx+50h]
0x180031d09  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data1
0x180031d10  jnz     short loc_180031D1F
0x180031d12  mov     rax, [rbx+58h]
0x180031d16  cmp     rax, qword ptr cs:IID_IPrintOemPS.Data4
0x180031d1d  jz      short loc_180031D41
0x180031d1f  mov     rax, [rbx+50h]
0x180031d23  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data1
0x180031d2a  jnz     loc_180031DDD
0x180031d30  mov     rax, [rbx+58h]
0x180031d34  cmp     rax, qword ptr cs:IID_IPrintOemPS2.Data4
0x180031d3b  jnz     loc_180031DDD
0x180031d41  mov     rax, [rcx]
0x180031d44  lea     r8, [rsp+0A8h+var_88]
0x180031d49  mov     edx, 1
0x180031d4e  mov     rax, [rax+20h]
0x180031d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d57  mov     edx, 80000000h
0x180031d5c  mov     ecx, eax
0x180031d5e  lea     eax, [rax+rdx]
0x180031d61  test    edx, eax
0x180031d63  jnz     short loc_180031D6D
0x180031d65  cmp     ecx, 80004001h
0x180031d6b  jnz     short loc_180031DDD
0x180031d6d  not     ecx
0x180031d6f  test    edx, ecx
0x180031d71  jz      short loc_180031DAF
0x180031d73  jmp     short loc_180031DA0
0x180031d75  test    byte ptr [rbx+64h], 2
0x180031d79  jnz     short loc_180031DAF
0x180031d7b  mov     edx, 1
0x180031d80  mov     rcx, rbx
0x180031d83  call    PGetOemEntrypointAddress
0x180031d88  test    rax, rax
0x180031d8b  jz      short loc_180031DAF
0x180031d8d  lea     rdx, [rsp+0A8h+var_88]
0x180031d92  mov     ecx, 1
0x180031d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031d9c  test    eax, eax
0x180031d9e  jz      short loc_180031DDD
0x180031da0  mov     ecx, [rsp+0A8h+var_48]
0x180031da4  lea     eax, [rcx-1]
0x180031da7  cmp     eax, 0Ah
0x180031daa  jbe     short loc_180031DDD
0x180031dac  mov     [rbx+40h], ecx
0x180031daf  add     r14d, [rbx+40h]
0x180031db3  add     rbx, 0B0h
0x180031dba  add     ebp, 0FFFFFFFFh
0x180031dbd  jnz     loc_180031CB4
0x180031dc3  mov     [r12], r14d
0x180031dc7  mov     eax, 1
0x180031dcc  add     rsp, 70h
0x180031dd0  pop     r15
0x180031dd2  pop     r14
0x180031dd4  pop     r13
0x180031dd6  pop     r12
0x180031dd8  pop     rsi
0x180031dd9  pop     rbp
0x180031dda  pop     rbx
0x180031ddb  retn
0x180031ddd  and     dword ptr [rbx+30h], 0FFFFFFFBh
0x180031de1  xor     eax, eax
0x180031de3  jmp     short loc_180031DCC
```
