# DpspWriteScenarioInstanceToMessageBuffer(INSTANCEINFO *,_DPS_MESSAGE *,uchar * *,ulong *,int)

- ea: `0x1800142f4`
- end: `0x1800145e7`
- name: `?DpspWriteScenarioInstanceToMessageBuffer@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@PEAPEAEPEAKH@Z`
- size: `755`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, struct _DPS_MESSAGE *, unsigned __int8 **, unsigned int *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180012e2c`

## callees

- `0x180009090`
- `0x1800142f4`
- `0x180018b49`

## import_xrefs

- `ntdll!AlpcMaxAllowedMessageLength` at `0x180014426`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180014444`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180014426`
- `ntdll!AlpcMaxAllowedMessageLength` at `0x180014444`

## string_xrefs

- `0x18001432c`: `DpspWriteScenarioInstanceToMessageBuffer`
- `0x1800145c0`: `DpspWriteScenarioInstanceToMessageBuffer`

## pseudocode

```c
__int64 __fastcall DpspWriteScenarioInstanceToMessageBuffer(
        struct INSTANCEINFO *a1,
        struct _DPS_MESSAGE *a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        int a5)
{
  int v9; // r8d
  unsigned int v10; // edi
  _DWORD *v11; // rcx
  unsigned int v12; // edx
  unsigned int v13; // r8d
  unsigned int v14; // edx
  unsigned int v15; // ebp
  unsigned __int64 v16; // rbx
  unsigned int v17; // ebp
  __int64 v18; // rax
  int v19; // edx
  int v20; // eax
  char *v21; // rbx
  __int64 v22; // rax
  __int64 v23; // rcx
  char *v24; // rbx
  __int64 v25; // rax
  __int64 v26; // rcx
  char *v27; // rbx
  __int64 v28; // r9
  int v29; // ecx
  int Args; // [rsp+20h] [rbp-48h]

  if ( !a1 )
  {
    v9 = 855;
LABEL_3:
    v10 = -2147024809;
    Args = 87;
LABEL_4:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (__int64)L"DpspWriteScenarioInstanceToMessageBuffer",
      v9,
      (const wchar_t *)L"Error = %d",
      Args);
    return v10;
  }
  v11 = (_DWORD *)*((_QWORD *)a1 + 152);
  if ( !v11 )
  {
    v9 = 856;
    goto LABEL_3;
  }
  if ( !a2 )
  {
    v9 = 857;
    goto LABEL_3;
  }
  if ( !a4 )
  {
    v9 = 858;
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = 859;
    goto LABEL_3;
  }
  v12 = v11[20] + 92;
  if ( v11[20] >= 0xFFFFFFA4 )
  {
    v10 = -2147024362;
    Args = 534;
    v9 = 878;
    goto LABEL_4;
  }
  v13 = v12 + v11[21];
  if ( v13 < v12 )
  {
    v10 = -2147024362;
    Args = 534;
    v9 = 884;
    goto LABEL_4;
  }
  v14 = v13 + v11[22];
  if ( v14 < v13 )
  {
    v10 = -2147024362;
    Args = 534;
    v9 = 890;
    goto LABEL_4;
  }
  v15 = v14 + *(_DWORD *)(*((_QWORD *)a1 + 101) + 144LL);
  if ( v15 < v14 )
  {
    v10 = -2147024362;
    Args = 534;
    v9 = 896;
    goto LABEL_4;
  }
  v16 = (unsigned __int64)*a3;
  if ( *a3
    && v16 >= (unsigned __int64)a2
    && v16 - (unsigned __int64)a2 <= AlpcMaxAllowedMessageLength()
    && (v17 = (v15 + 7) & 0xFFFFFFF8, v17 <= (unsigned __int64)a2 + AlpcMaxAllowedMessageLength() - v16) )
  {
    *(_DWORD *)v16 = v17;
    v10 = 0;
    *(_OWORD *)(v16 + 4) = *(_OWORD *)((char *)a1 + 24);
    *(_OWORD *)(v16 + 20) = *(_OWORD *)*((_QWORD *)a1 + 152);
    *(_OWORD *)(v16 + 36) = *(_OWORD *)*((_QWORD *)a1 + 101);
    *(_QWORD *)(v16 + 52) = *((_QWORD *)a1 + 17);
    if ( (*((_BYTE *)a1 + 92) & 0x20) != 0 )
    {
      v18 = *((_QWORD *)a1 + 15);
      v19 = 1;
    }
    else
    {
      v19 = 0;
      v18 = 0;
    }
    *(_QWORD *)(v16 + 60) = v18;
    *(_DWORD *)(v16 + 68) = *(_DWORD *)(*((_QWORD *)a1 + 101) + 56LL);
    v20 = v19 | 4;
    if ( !a5 )
      v20 = v19;
    *(_DWORD *)(v16 + 72) = v20;
    *(_DWORD *)(v16 + 76) = *(_DWORD *)(*((_QWORD *)a1 + 152) + 80LL);
    v21 = (char *)(v16 + 80);
    memcpy_0(v21, *(const void **)(*((_QWORD *)a1 + 152) + 56LL), *(unsigned int *)(*((_QWORD *)a1 + 152) + 80LL));
    v22 = *((_QWORD *)a1 + 152);
    v23 = *(unsigned int *)(v22 + 80);
    *(_DWORD *)&v21[v23] = *(_DWORD *)(v22 + 84);
    v24 = &v21[v23 + 4];
    memcpy_0(v24, *(const void **)(*((_QWORD *)a1 + 152) + 64LL), *(unsigned int *)(*((_QWORD *)a1 + 152) + 84LL));
    v25 = *((_QWORD *)a1 + 152);
    v26 = *(unsigned int *)(v25 + 84);
    *(_DWORD *)&v24[v26] = *(_DWORD *)(v25 + 88);
    v27 = &v24[v26 + 4];
    memcpy_0(v27, *(const void **)(*((_QWORD *)a1 + 152) + 72LL), *(unsigned int *)(*((_QWORD *)a1 + 152) + 88LL));
    v28 = *(unsigned int *)(*((_QWORD *)a1 + 152) + 88LL);
    *(_DWORD *)&v27[v28] = *(_DWORD *)(*((_QWORD *)a1 + 101) + 144LL);
    memcpy_0(
      &v27[v28 + 4],
      *(const void **)(*((_QWORD *)a1 + 101) + 136LL),
      *(unsigned int *)(*((_QWORD *)a1 + 101) + 144LL));
    v29 = *(_DWORD *)(*((_QWORD *)a1 + 101) + 144LL)
        + *(_DWORD *)(*((_QWORD *)a1 + 152) + 80LL)
        + *(_DWORD *)(*((_QWORD *)a1 + 152) + 84LL)
        + *(_DWORD *)(*((_QWORD *)a1 + 152) + 88LL);
    *a3 += v17;
    *a4 = v29;
  }
  else
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (__int64)L"DpspWriteScenarioInstanceToMessageBuffer",
      904,
      (const wchar_t *)L"Error = %d",
      111);
    return (unsigned int)-2147024362;
  }
  return v10;
}

```

## disassembly

```asm
0x1800142f4  push    rbx
0x1800142f6  push    rbp
0x1800142f7  push    rsi
0x1800142f8  push    rdi
0x1800142f9  push    r14
0x1800142fb  push    r15
0x1800142fd  sub     rsp, 38h
0x180014301  mov     r15, r9
0x180014304  mov     r14, r8
0x180014307  mov     rdi, rdx
0x18001430a  mov     rsi, rcx
0x18001430d  test    rcx, rcx
0x180014310  jnz     short loc_180014344
0x180014312  mov     r8d, 357h; int
0x180014318  mov     edi, 80070057h
0x18001431d  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x180014325  lea     r9, aErrorD; "Error = %d"
0x18001432c  lea     rdx, aDpspwritescena; "DpspWriteScenarioInstanceToMessageBuffe"...
0x180014333  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18001433a  call    WdipTraceError
0x18001433f  jmp     loc_1800145D8
0x180014344  mov     rcx, [rcx+4C0h]
0x18001434b  test    rcx, rcx
0x18001434e  jnz     short loc_180014358
0x180014350  mov     r8d, 358h
0x180014356  jmp     short loc_180014318
0x180014358  test    rdi, rdi
0x18001435b  jnz     short loc_180014365
0x18001435d  mov     r8d, 359h
0x180014363  jmp     short loc_180014318
0x180014365  test    r15, r15
0x180014368  jnz     short loc_180014372
0x18001436a  mov     r8d, 35Ah
0x180014370  jmp     short loc_180014318
0x180014372  test    r14, r14
0x180014375  jnz     short loc_18001437F
0x180014377  mov     r8d, 35Bh
0x18001437d  jmp     short loc_180014318
0x18001437f  mov     edx, [rcx+50h]
0x180014382  add     edx, 5Ch ; '\'
0x180014385  cmp     edx, 5Ch ; '\'
0x180014388  jnb     short loc_18001439F
0x18001438a  mov     edi, 80070216h
0x18001438f  mov     dword ptr [rsp+68h+Args], 216h
0x180014397  mov     r8d, 36Eh
0x18001439d  jmp     short loc_180014325
0x18001439f  mov     r8d, [rcx+54h]
0x1800143a3  add     r8d, edx
0x1800143a6  cmp     r8d, edx
0x1800143a9  jnb     short loc_1800143C3
0x1800143ab  mov     edi, 80070216h
0x1800143b0  mov     dword ptr [rsp+68h+Args], 216h
0x1800143b8  mov     r8d, 374h
0x1800143be  jmp     loc_180014325
0x1800143c3  mov     edx, [rcx+58h]
0x1800143c6  add     edx, r8d
0x1800143c9  cmp     edx, r8d
0x1800143cc  jnb     short loc_1800143E6
0x1800143ce  mov     edi, 80070216h
0x1800143d3  mov     dword ptr [rsp+68h+Args], 216h
0x1800143db  mov     r8d, 37Ah
0x1800143e1  jmp     loc_180014325
0x1800143e6  mov     rax, [rsi+328h]
0x1800143ed  mov     ebp, [rax+90h]
0x1800143f3  add     ebp, edx
0x1800143f5  cmp     ebp, edx
0x1800143f7  jnb     short loc_180014411
0x1800143f9  mov     edi, 80070216h
0x1800143fe  mov     dword ptr [rsp+68h+Args], 216h
0x180014406  mov     r8d, 380h
0x18001440c  jmp     loc_180014325
0x180014411  mov     rbx, [r14]
0x180014414  test    rbx, rbx
0x180014417  jz      loc_1800145AB
0x18001441d  cmp     rbx, rdi
0x180014420  jb      loc_1800145AB
0x180014426  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18001442c  mov     rcx, rax
0x18001442f  mov     rax, rbx
0x180014432  sub     rax, rdi
0x180014435  cmp     rax, rcx
0x180014438  ja      loc_1800145AB
0x18001443e  add     ebp, 7
0x180014441  and     ebp, 0FFFFFFF8h
0x180014444  call    cs:__imp_AlpcMaxAllowedMessageLength
0x18001444a  sub     rdi, rbx
0x18001444d  add     rax, rdi
0x180014450  cmp     rbp, rax
0x180014453  ja      loc_1800145AB
0x180014459  mov     [rbx], ebp
0x18001445b  xor     edi, edi
0x18001445d  movups  xmm0, xmmword ptr [rsi+18h]
0x180014461  movdqu  xmmword ptr [rbx+4], xmm0
0x180014466  mov     rax, [rsi+4C0h]
0x18001446d  movups  xmm0, xmmword ptr [rax]
0x180014470  movdqu  xmmword ptr [rbx+14h], xmm0
0x180014475  mov     rax, [rsi+328h]
0x18001447c  movups  xmm0, xmmword ptr [rax]
0x18001447f  movdqu  xmmword ptr [rbx+24h], xmm0
0x180014484  mov     rax, [rsi+88h]
0x18001448b  mov     [rbx+34h], rax
0x18001448f  test    byte ptr [rsi+5Ch], 20h
0x180014493  jz      short loc_18001449E
0x180014495  mov     rax, [rsi+78h]
0x180014499  lea     edx, [rdi+1]
0x18001449c  jmp     short loc_1800144A2
0x18001449e  xor     edx, edx
0x1800144a0  xor     eax, eax
0x1800144a2  mov     [rbx+3Ch], rax
0x1800144a6  mov     rax, [rsi+328h]
0x1800144ad  mov     ecx, [rax+38h]
0x1800144b0  mov     eax, edx
0x1800144b2  mov     [rbx+44h], ecx
0x1800144b5  or      eax, 4
0x1800144b8  cmp     [rsp+68h+arg_20], edi
0x1800144bf  cmovz   eax, edx
0x1800144c2  mov     [rbx+48h], eax
0x1800144c5  mov     rax, [rsi+4C0h]
0x1800144cc  mov     ecx, [rax+50h]
0x1800144cf  mov     [rbx+4Ch], ecx
0x1800144d2  add     rbx, 50h ; 'P'
0x1800144d6  mov     rdx, [rsi+4C0h]
0x1800144dd  mov     rcx, rbx; void *
0x1800144e0  mov     r8d, [rdx+50h]; Size
0x1800144e4  mov     rdx, [rdx+38h]; Src
0x1800144e8  call    memcpy_0
0x1800144ed  mov     rax, [rsi+4C0h]
0x1800144f4  mov     ecx, [rax+50h]
0x1800144f7  mov     eax, [rax+54h]
0x1800144fa  mov     [rcx+rbx], eax
0x1800144fd  add     rcx, 4
0x180014501  mov     rdx, [rsi+4C0h]
0x180014508  add     rbx, rcx
0x18001450b  mov     rcx, rbx; void *
0x18001450e  mov     r8d, [rdx+54h]; Size
0x180014512  mov     rdx, [rdx+40h]; Src
0x180014516  call    memcpy_0
0x18001451b  mov     rax, [rsi+4C0h]
0x180014522  mov     ecx, [rax+54h]
0x180014525  mov     eax, [rax+58h]
0x180014528  mov     [rcx+rbx], eax
0x18001452b  add     rcx, 4
0x18001452f  mov     rdx, [rsi+4C0h]
0x180014536  add     rbx, rcx
0x180014539  mov     rcx, rbx; void *
0x18001453c  mov     r8d, [rdx+58h]; Size
0x180014540  mov     rdx, [rdx+48h]; Src
0x180014544  call    memcpy_0
0x180014549  mov     rax, [rsi+4C0h]
0x180014550  mov     r9d, [rax+58h]
0x180014554  mov     rax, [rsi+328h]
0x18001455b  mov     ecx, [rax+90h]
0x180014561  mov     [r9+rbx], ecx
0x180014565  lea     rcx, [r9+4]
0x180014569  mov     rdx, [rsi+328h]
0x180014570  add     rcx, rbx; void *
0x180014573  mov     r8d, [rdx+90h]; Size
0x18001457a  mov     rdx, [rdx+88h]; Src
0x180014581  call    memcpy_0
0x180014586  mov     rax, [rsi+4C0h]
0x18001458d  mov     ecx, [rax+58h]
0x180014590  add     ecx, [rax+54h]
0x180014593  add     ecx, [rax+50h]
0x180014596  mov     rax, [rsi+328h]
0x18001459d  add     ecx, [rax+90h]
0x1800145a3  add     [r14], rbp
0x1800145a6  mov     [r15], ecx
0x1800145a9  jmp     short loc_1800145D8
0x1800145ab  lea     r9, aErrorD; "Error = %d"
0x1800145b2  mov     dword ptr [rsp+68h+Args], 6Fh ; 'o'; Args
0x1800145ba  mov     r8d, 388h; int
0x1800145c0  lea     rdx, aDpspwritescena; "DpspWriteScenarioInstanceToMessageBuffe"...
0x1800145c7  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800145ce  call    WdipTraceError
0x1800145d3  mov     edi, 80070216h
0x1800145d8  mov     eax, edi
0x1800145da  add     rsp, 38h
0x1800145de  pop     r15
0x1800145e0  pop     r14
0x1800145e2  pop     rdi
0x1800145e3  pop     rsi
0x1800145e4  pop     rbp
0x1800145e5  pop     rbx
0x1800145e6  retn
```
