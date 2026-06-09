# __StringConvert::ConvertSafeArrayToLPWSTRArray(tagSAFEARRAY *,ushort * * *,ulong *)

- ea: `0x14000e2b8`
- end: `0x14000e469`
- name: `?ConvertSafeArrayToLPWSTRArray@__StringConvert@@SAJPEAUtagSAFEARRAY@@PEAPEAPEAGPEAK@Z`
- size: `433`
- prototype: `HRESULT __fastcall(SAFEARRAY *psa, unsigned __int16 ***, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000e470`

## callees

- `0x140006284`
- `0x14000e2b8`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000e370`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000e3fa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000e370`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000e3fa`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e3db`
- `OLEAUT32!__imp_SysStringLen` at `0x14000e3db`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000e328`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x14000e328`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000e33c`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x14000e33c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000e3b4`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x14000e3b4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000e43c`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x14000e43c`

## pseudocode

```c
HRESULT __fastcall __StringConvert::ConvertSafeArrayToLPWSTRArray(
        SAFEARRAY *psa,
        unsigned __int16 ***a2,
        unsigned int *a3)
{
  HRESULT result; // eax
  bool v7; // zf
  unsigned int v8; // eax
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // kr20_8
  unsigned __int16 **v11; // rax
  signed int j; // edx
  signed int k; // r14d
  OLECHAR *v14; // rcx
  unsigned __int64 v15; // r12
  unsigned __int16 *v16; // rax
  void **v17; // rbx
  __int64 v18; // rdi
  unsigned int *i; // rsi
  void *ppvData; // [rsp+20h] [rbp-48h] BYREF
  LONG plUbound; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int16 ***v22; // [rsp+78h] [rbp+10h]
  unsigned int *v23; // [rsp+80h] [rbp+18h]
  LONG plLbound; // [rsp+88h] [rbp+20h] BYREF

  v23 = a3;
  v22 = a2;
  if ( !psa )
    return -2147024809;
  if ( !a2 || !a3 )
    return -2147467261;
  *a2 = 0;
  *a3 = 0;
  plUbound = 0;
  plLbound = 0;
  SafeArrayGetUBound(psa, 1u, &plUbound);
  SafeArrayGetLBound(psa, 1u, &plLbound);
  v7 = plUbound - plLbound == -1;
  v8 = plUbound - plLbound + 1;
  *a3 = v8;
  if ( v7 )
    return 1;
  v10 = v8;
  v9 = 8LL * v8;
  if ( !is_mul_ok(v10, 8u) )
    v9 = -1;
  try
  {
    v11 = (unsigned __int16 **)CWin32DefaultArena::WbemMemAlloc(v9);
  }
  catch ( ... )
  {
    v17 = (void **)v22;
    if ( v22 && *v22 )
    {
      v18 = 0;
      for ( i = v23; (unsigned int)v18 < *i; v18 = (unsigned int)(v18 + 1) )
      {
        CWin32DefaultArena::WbemMemFree(*((void **)*v17 + v18));
        *((_QWORD *)*v17 + v18) = 0;
      }
      *i = 0;
      CWin32DefaultArena::WbemMemFree(*v17);
      *v17 = 0;
    }
    return -2147418113;
  }
  *a2 = v11;
  if ( !v11 )
    return -2147024882;
  for ( j = 0; j < (int)*a3; ++j )
    (*a2)[j] = 0;
  ppvData = 0;
  result = SafeArrayAccessData(psa, &ppvData);
  if ( result >= 0 )
  {
    for ( k = 0; k < (int)*a3; ++k )
    {
      v14 = (OLECHAR *)*((_QWORD *)ppvData + k);
      if ( v14 )
      {
        v15 = SysStringLen(v14) + 1;
        v16 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v15, 2u));
        (*a2)[k] = v16;
        if ( !v16 )
          return -2147024882;
        StringCchCopyW((*a2)[k], v15, *((const unsigned __int16 **)ppvData + k));
      }
    }
    SafeArrayUnaccessData(psa);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000e2b8  mov     [rsp+arg_10], r8
0x14000e2bd  mov     [rsp+arg_8], rdx
0x14000e2c2  push    rbx
0x14000e2c3  push    rsi
0x14000e2c4  push    rdi
0x14000e2c5  push    r12
0x14000e2c7  push    r14
0x14000e2c9  push    r15
0x14000e2cb  sub     rsp, 38h
0x14000e2cf  mov     rbx, r8
0x14000e2d2  mov     rdi, rdx
0x14000e2d5  mov     rsi, rcx
0x14000e2d8  test    rcx, rcx
0x14000e2db  jnz     short loc_14000E2E7
0x14000e2dd  mov     eax, 80070057h
0x14000e2e2  jmp     loc_14000E45A
0x14000e2e7  test    rdi, rdi
0x14000e2ea  jz      loc_14000E455
0x14000e2f0  test    rbx, rbx
0x14000e2f3  jz      loc_14000E455
0x14000e2f9  mov     qword ptr [rdx], 0
0x14000e300  mov     dword ptr [r8], 0
0x14000e307  mov     [rsp+68h+plUbound], 0
0x14000e30f  mov     [rsp+68h+plLbound], 0
0x14000e31a  lea     r8, [rsp+68h+plUbound]; plUbound
0x14000e31f  mov     r12d, 1
0x14000e325  mov     edx, r12d; nDim
0x14000e328  call    cs:__imp_SafeArrayGetUBound
0x14000e32e  lea     r8, [rsp+68h+plLbound]; plLbound
0x14000e336  mov     edx, r12d; nDim
0x14000e339  mov     rcx, rsi; psa
0x14000e33c  call    cs:__imp_SafeArrayGetLBound
0x14000e342  mov     eax, [rsp+68h+plUbound]
0x14000e346  sub     eax, [rsp+68h+plLbound]
0x14000e34d  add     eax, r12d
0x14000e350  mov     [rbx], eax
0x14000e352  jz      loc_14000E449
0x14000e358  mov     ecx, eax
0x14000e35a  lea     eax, [r12+7]
0x14000e35f  mul     rcx
0x14000e362  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e369  cmovb   rax, rcx
0x14000e36d  mov     rcx, rax
0x14000e370  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000e376  mov     [rdi], rax
0x14000e379  test    rax, rax
0x14000e37c  jnz     short loc_14000E388
0x14000e37e  mov     eax, 8007000Eh
0x14000e383  jmp     loc_14000E45A
0x14000e388  xor     edx, edx
0x14000e38a  cmp     [rbx], edx
0x14000e38c  jle     short loc_14000E3A3
0x14000e38e  movsxd  rcx, edx
0x14000e391  mov     rax, [rdi]
0x14000e394  mov     qword ptr [rax+rcx*8], 0
0x14000e39c  add     edx, r12d
0x14000e39f  cmp     edx, [rbx]
0x14000e3a1  jl      short loc_14000E38E
0x14000e3a3  mov     [rsp+68h+ppvData], 0
0x14000e3ac  lea     rdx, [rsp+68h+ppvData]; ppvData
0x14000e3b1  mov     rcx, rsi; psa
0x14000e3b4  call    cs:__imp_SafeArrayAccessData
0x14000e3ba  test    eax, eax
0x14000e3bc  js      loc_14000E447
0x14000e3c2  xor     r14d, r14d
0x14000e3c5  cmp     r14d, [rbx]
0x14000e3c8  jge     short loc_14000E439
0x14000e3ca  movsxd  r15, r14d
0x14000e3cd  mov     rax, [rsp+68h+ppvData]
0x14000e3d2  mov     rcx, [rax+r15*8]; pbstr
0x14000e3d6  test    rcx, rcx
0x14000e3d9  jz      short loc_14000E434
0x14000e3db  call    cs:__imp_SysStringLen
0x14000e3e1  add     r12d, eax
0x14000e3e4  mov     eax, 2
0x14000e3e9  mul     r12
0x14000e3ec  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000e3f3  cmovb   rax, rcx
0x14000e3f7  mov     rcx, rax
0x14000e3fa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x14000e400  mov     rcx, rax
0x14000e403  mov     rax, [rdi]
0x14000e406  mov     [rax+r15*8], rcx
0x14000e40a  test    rcx, rcx
0x14000e40d  jnz     short loc_14000E416
0x14000e40f  mov     eax, 8007000Eh
0x14000e414  jmp     short loc_14000E45A
0x14000e416  mov     rcx, [rdi]
0x14000e419  mov     r8, [rsp+68h+ppvData]
0x14000e41e  mov     r8, [r8+r15*8]; unsigned __int16 *
0x14000e422  mov     rdx, r12; unsigned __int64
0x14000e425  mov     rcx, [rcx+r15*8]; unsigned __int16 *
0x14000e429  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000e42e  mov     r12d, 1
0x14000e434  add     r14d, r12d
0x14000e437  jmp     short loc_14000E3C5
0x14000e439  mov     rcx, rsi; psa
0x14000e43c  call    cs:__imp_SafeArrayUnaccessData
0x14000e442  nop
0x14000e443  xor     eax, eax
0x14000e445  jmp     short loc_14000E45A
0x14000e447  jmp     short loc_14000E45A
0x14000e449  mov     eax, r12d
0x14000e44c  jmp     short loc_14000E45A
0x14000e44e  mov     eax, 8000FFFFh
0x14000e453  jmp     short loc_14000E45A
0x14000e455  mov     eax, 80004003h
0x14000e45a  add     rsp, 38h
0x14000e45e  pop     r15
0x14000e460  pop     r14
0x14000e462  pop     r12
0x14000e464  pop     rdi
0x14000e465  pop     rsi
0x14000e466  pop     rbx
0x14000e467  retn
```
