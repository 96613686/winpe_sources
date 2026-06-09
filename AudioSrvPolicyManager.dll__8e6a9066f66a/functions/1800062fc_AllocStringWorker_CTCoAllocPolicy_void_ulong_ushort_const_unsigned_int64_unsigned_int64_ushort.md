# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x1800062fc`
- end: `0x18000642a`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003c70`
- `0x180005f14`

## callees

- `0x1800062fc`
- `0x1800327f8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000633f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000633f`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        unsigned __int64 a4,
        int a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // rbx
  _WORD *v9; // rax
  _WORD *v10; // rdx
  unsigned int v11; // edi
  _WORD *v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  _WORD *v15; // r9
  __int64 v16; // r11
  _WORD *v17; // rcx
  __int64 v18; // r10
  __int64 v20; // rbx
  bool v21; // cf

  v6 = a4 + 1;
  *a6 = 0;
  if ( a4 + 1 < a4 || !is_mul_ok(v6, 2u) )
    return (unsigned int)-2147024362;
  v9 = CoTaskMemAlloc(2 * v6);
  *a6 = v9;
  v10 = v9;
  v11 = v9 == 0 ? 0x8007000E : 0;
  if ( v9 )
  {
    if ( v6 <= 0x7FFFFFFF )
    {
      if ( a4 < 0x7FFFFFFF )
      {
        v12 = &unk_180053B30;
        if ( a3 )
          v12 = a3;
        v13 = a4 & -(__int64)(a3 != 0);
        if ( v6 )
        {
          v14 = v6;
          v15 = v10;
          v16 = 0;
          do
          {
            if ( !v13 )
              break;
            if ( !*v12 )
              break;
            *v15++ = *v12++;
            --v13;
            ++v16;
            --v14;
          }
          while ( v14 );
          v17 = v15 - 1;
          v18 = v16 - 1;
          if ( v14 )
          {
            v17 = v15;
            v18 = v16;
          }
          *v17 = 0;
          if ( v14 )
          {
            v21 = v6 == v18;
            v20 = v6 - v18;
            if ( !v21 && v20 != 1 && (unsigned __int64)(2 * v20) > 2 )
              memset_0(&v10[v18 + 1], 0, 2 * v20 - 2);
          }
        }
        return v11;
      }
      if ( !v6 )
        return v11;
    }
    *v9 = 0;
  }
  return v11;
}

```

## disassembly

```asm
0x1800062fc  mov     [rsp+arg_8], rbx
0x180006301  mov     [rsp+arg_10], rbp
0x180006306  push    rsi
0x180006307  push    rdi
0x180006308  push    r14
0x18000630a  sub     rsp, 20h
0x18000630e  mov     rdi, [rsp+38h+arg_28]
0x180006313  lea     rbx, [r9+1]
0x180006317  xor     r14d, r14d
0x18000631a  mov     rsi, r9
0x18000631d  mov     rbp, r8
0x180006320  mov     [rdi], r14
0x180006323  cmp     rbx, r9
0x180006326  jb      loc_1800063F1
0x18000632c  lea     eax, [r14+2]
0x180006330  mul     rbx
0x180006333  test    rdx, rdx
0x180006336  jnz     loc_1800063F1
0x18000633c  mov     rcx, rax; cb
0x18000633f  call    cs:__imp_CoTaskMemAlloc
0x180006345  mov     [rdi], rax
0x180006348  mov     rcx, rax
0x18000634b  neg     rcx
0x18000634e  mov     rdx, rax
0x180006351  sbb     edi, edi
0x180006353  not     edi
0x180006355  and     edi, 8007000Eh
0x18000635b  test    rax, rax
0x18000635e  jz      short loc_1800063DC
0x180006360  mov     eax, 7FFFFFFFh
0x180006365  cmp     rbx, rax
0x180006368  ja      loc_180006424
0x18000636e  cmp     rsi, rax
0x180006371  jnb     loc_18000641F
0x180006377  test    rbp, rbp
0x18000637a  lea     rcx, unk_180053B30
0x180006381  cmovnz  rcx, rbp
0x180006385  neg     rbp
0x180006388  sbb     rax, rax
0x18000638b  and     rax, rsi
0x18000638e  test    rbx, rbx
0x180006391  jz      short loc_1800063DC
0x180006393  mov     r8, rbx
0x180006396  mov     r9, rdx
0x180006399  mov     r11d, r14d
0x18000639c  test    rax, rax
0x18000639f  jz      short loc_1800063C3
0x1800063a1  movzx   r10d, word ptr [rcx]
0x1800063a5  test    r10w, r10w
0x1800063a9  jz      short loc_1800063C3
0x1800063ab  mov     [r9], r10w
0x1800063af  add     rcx, 2
0x1800063b3  add     r9, 2
0x1800063b7  dec     rax
0x1800063ba  inc     r11
0x1800063bd  sub     r8, 1
0x1800063c1  jnz     short loc_18000639C
0x1800063c3  test    r8, r8
0x1800063c6  lea     rcx, [r9-2]
0x1800063ca  lea     r10, [r11-1]
0x1800063ce  cmovnz  rcx, r9
0x1800063d2  cmovnz  r10, r11
0x1800063d6  mov     [rcx], r14w
0x1800063da  jnz     short loc_1800063F8
0x1800063dc  mov     rbx, [rsp+38h+arg_8]
0x1800063e1  mov     eax, edi
0x1800063e3  mov     rbp, [rsp+38h+arg_10]
0x1800063e8  add     rsp, 20h
0x1800063ec  pop     r14
0x1800063ee  pop     rdi
0x1800063ef  pop     rsi
0x1800063f0  retn
0x1800063f1  mov     edi, 80070216h
0x1800063f6  jmp     short loc_1800063DC
0x1800063f8  sub     rbx, r10
0x1800063fb  cmp     rbx, 1
0x1800063ff  jbe     short loc_1800063DC
0x180006401  lea     r8, [rbx+rbx]
0x180006405  cmp     r8, 2
0x180006409  jbe     short loc_1800063DC
0x18000640b  inc     r10
0x18000640e  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180006412  lea     rcx, [rdx+r10*2]; void *
0x180006416  xor     edx, edx; Val
0x180006418  call    memset_0
0x18000641d  jmp     short loc_1800063DC
0x18000641f  test    rbx, rbx
0x180006422  jz      short loc_1800063DC
0x180006424  mov     [rdx], r14w
0x180006428  jmp     short loc_1800063DC
```
