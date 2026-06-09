# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,wchar_t const *,unsigned __int64,unsigned __int64,wchar_t * *)

- ea: `0x1800063b8`
- end: `0x18000650e`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEB_W_K2PEAPEA_W@Z`
- size: `342`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180013160`
- `0x180013210`
- `0x180013250`
- `0x1800133b0`

## callees

- `0x1800063b8`
- `0x18000d2a0`
- `0x18000df4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006429`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        unsigned __int64 a4,
        int a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // rbx
  unsigned int v9; // edi
  _WORD *v11; // rax
  _WORD *v12; // rdx
  __int64 *v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v15; // r8
  _WORD *v16; // r9
  __int64 v17; // r11
  _WORD *v18; // rcx
  __int64 v19; // r10
  __int64 v20; // rbx
  bool v21; // cf

  v6 = a4 + 1;
  *a6 = 0;
  if ( a4 + 1 < a4 || !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v11 = CoTaskMemAlloc(2 * v6);
  *a6 = v11;
  v12 = v11;
  v9 = v11 == 0 ? 0x8007000E : 0;
  if ( !v11 )
    return v9;
  if ( v6 > 0x7FFFFFFF )
  {
LABEL_22:
    *v11 = 0;
    return v9;
  }
  if ( a4 >= 0x7FFFFFFF )
  {
    if ( !v6 )
      return v9;
    goto LABEL_22;
  }
  v13 = &qword_18002AF20;
  if ( a3 )
    v13 = a3;
  v14 = a4 & -(__int64)(a3 != 0);
  if ( v6 )
  {
    v15 = v6;
    v16 = v12;
    v17 = 0;
    do
    {
      if ( !v14 )
        break;
      if ( !*(_WORD *)v13 )
        break;
      *v16 = *(_WORD *)v13;
      v13 = (__int64 *)((char *)v13 + 2);
      ++v16;
      --v14;
      ++v17;
      --v15;
    }
    while ( v15 );
    v18 = v16 - 1;
    v19 = v17 - 1;
    if ( v15 )
    {
      v18 = v16;
      v19 = v17;
    }
    *v18 = 0;
    if ( v15 )
    {
      v21 = v6 == v19;
      v20 = v6 - v19;
      if ( !v21 && v20 != 1 && (unsigned __int64)(2 * v20) > 2 )
        memset_0(&v12[v19 + 1], 0, 2 * v20 - 2);
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800063b8  mov     [rsp+arg_0], rbx
0x1800063bd  mov     [rsp+arg_8], rbp
0x1800063c2  push    rsi
0x1800063c3  push    rdi
0x1800063c4  push    r14
0x1800063c6  sub     rsp, 30h
0x1800063ca  mov     rax, cs:__security_cookie
0x1800063d1  xor     rax, rsp
0x1800063d4  mov     [rsp+48h+var_20], rax
0x1800063d9  mov     rdi, [rsp+48h+arg_28]
0x1800063de  lea     rbx, [r9+1]
0x1800063e2  xor     r14d, r14d
0x1800063e5  mov     rsi, r9
0x1800063e8  mov     rbp, r8
0x1800063eb  mov     [rdi], r14
0x1800063ee  cmp     rbx, r9
0x1800063f1  jb      short loc_1800063FF
0x1800063f3  lea     eax, [r14+2]
0x1800063f7  mul     rbx
0x1800063fa  test    rdx, rdx
0x1800063fd  jz      short loc_180006426
0x1800063ff  mov     edi, 80070216h
0x180006404  mov     eax, edi
0x180006406  mov     rcx, [rsp+48h+var_20]
0x18000640b  xor     rcx, rsp; StackCookie
0x18000640e  call    __security_check_cookie
0x180006413  mov     rbx, [rsp+48h+arg_0]
0x180006418  mov     rbp, [rsp+48h+arg_8]
0x18000641d  add     rsp, 30h
0x180006421  pop     r14
0x180006423  pop     rdi
0x180006424  pop     rsi
0x180006425  retn
0x180006426  mov     rcx, rax; cb
0x180006429  call    cs:__imp_CoTaskMemAlloc
0x18000642f  mov     [rdi], rax
0x180006432  mov     rcx, rax
0x180006435  neg     rcx
0x180006438  mov     rdx, rax
0x18000643b  sbb     edi, edi
0x18000643d  not     edi
0x18000643f  and     edi, 8007000Eh
0x180006445  test    rax, rax
0x180006448  jz      short loc_180006404
0x18000644a  mov     eax, 7FFFFFFFh
0x18000644f  cmp     rbx, rax
0x180006452  ja      loc_180006505
0x180006458  cmp     rsi, rax
0x18000645b  jnb     loc_1800064FC
0x180006461  test    rbp, rbp
0x180006464  lea     rcx, qword_18002AF20
0x18000646b  cmovnz  rcx, rbp
0x18000646f  neg     rbp
0x180006472  sbb     rax, rax
0x180006475  and     rax, rsi
0x180006478  test    rbx, rbx
0x18000647b  jz      short loc_180006404
0x18000647d  mov     r8, rbx
0x180006480  mov     r9, rdx
0x180006483  mov     r11, r14
0x180006486  test    rax, rax
0x180006489  jz      short loc_1800064AD
0x18000648b  movzx   r10d, word ptr [rcx]
0x18000648f  test    r10w, r10w
0x180006493  jz      short loc_1800064AD
0x180006495  mov     [r9], r10w
0x180006499  add     rcx, 2
0x18000649d  add     r9, 2
0x1800064a1  dec     rax
0x1800064a4  inc     r11
0x1800064a7  sub     r8, 1
0x1800064ab  jnz     short loc_180006486
0x1800064ad  test    r8, r8
0x1800064b0  lea     rcx, [r9-2]
0x1800064b4  lea     r10, [r11-1]
0x1800064b8  cmovnz  rcx, r9
0x1800064bc  cmovnz  r10, r11
0x1800064c0  mov     [rcx], r14w
0x1800064c4  jz      loc_180006404
0x1800064ca  sub     rbx, r10
0x1800064cd  cmp     rbx, 1
0x1800064d1  jbe     loc_180006404
0x1800064d7  lea     r8, [rbx+rbx]
0x1800064db  cmp     r8, 2
0x1800064df  jbe     loc_180006404
0x1800064e5  inc     r10
0x1800064e8  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x1800064ec  lea     rcx, [rdx+r10*2]; void *
0x1800064f0  xor     edx, edx; Val
0x1800064f2  call    memset_0
0x1800064f7  jmp     loc_180006404
0x1800064fc  test    rbx, rbx
0x1800064ff  jz      loc_180006404
0x180006505  mov     [rdx], r14w
0x180006509  jmp     loc_180006404
```
