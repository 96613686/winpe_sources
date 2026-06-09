# ConvertXMPArrayToStringVectorOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180006ae8`
- end: `0x180006d9b`
- name: `?ConvertXMPArrayToStringVectorOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `691`
- prototype: `int(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006860`

## callees

- `0x180006ae8`
- `0x1800076b0`
- `0x180007734`
- `0x180013e34`
- `0x180016020`
- `0x1800169b8`
- `0x180028010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006c8b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006c8b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006b20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006cee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d69`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006b20`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006cee`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180006d69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006d38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d8f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConvertXMPArrayToStringVectorOnRead(const struct tagPROPVARIANT *a1, struct tagPROPVARIANT *a2)
{
  int v4; // ebx
  _QWORD *v5; // rsi
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r15
  unsigned int v8; // r12d
  unsigned __int64 v9; // r14
  BYTE *v10; // r14
  unsigned __int64 i; // rcx
  unsigned __int64 j; // r14
  void *v14; // rcx
  BYTE *v15; // rax
  __int64 v16; // [rsp+20h] [rbp-B9h] BYREF
  PROPVARIANT pvar; // [rsp+28h] [rbp-B1h] BYREF
  _QWORD *v18; // [rsp+40h] [rbp-99h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-91h]
  unsigned __int64 v20; // [rsp+50h] [rbp-89h]
  int v21; // [rsp+58h] [rbp-81h]
  __int64 v22; // [rsp+60h] [rbp-79h]
  unsigned __int16 v23[64]; // [rsp+70h] [rbp-69h] BYREF

  v4 = -2147467259;
  PropVariantClear(a2);
  if ( a1->vt == 13 )
  {
    v16 = 0;
    v4 = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))a1->hVal.QuadPart)(
           a1->hVal,
           &GUID_30989668_e1c9_4597_b395_458eedb808df,
           &v16);
    if ( v4 >= 0 )
    {
      v5 = 0;
      v18 = 0;
      v6 = 0;
      v19 = 0;
      v7 = 0;
      v20 = 0;
      v21 = 0;
      memset_0(v23, 0, sizeof(v23));
      v8 = 0;
      while ( v4 >= 0 )
      {
        v4 = StringCchPrintfW(v23, 0x40u, L"/{uint=%d}", v8);
        if ( v4 >= 0 )
        {
          memset(&pvar, 0, sizeof(pvar));
          v4 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 *, PROPVARIANT *))(*(_QWORD *)v16 + 40LL))(
                 v16,
                 v23,
                 &pvar);
          if ( v4 < 0 )
          {
            PropVariantClear(&pvar);
            if ( v4 == -2003292352 )
            {
              v22 = 0;
              if ( is_mul_ok(v6, 8u) )
              {
                if ( v6 )
                {
                  v15 = (BYTE *)CoTaskMemAlloc(8 * v6);
                  v10 = v15;
                  if ( v15 )
                  {
                    v4 = 0;
                    memset_0(v15, 0, 8 * v6);
                  }
                  else
                  {
                    v4 = -2147024882;
                  }
                }
                else
                {
                  v4 = 0;
                  v10 = 0;
                }
                if ( v4 >= 0 )
                {
                  a2->vt = 4127;
                  a2->lVal = v6;
                  a2->bstrblobVal.pData = v10;
                  for ( i = 0; i < v6; ++i )
                  {
                    *(_QWORD *)&v10[8 * i] = v5[i];
                    v5[i] = 0;
                  }
                }
              }
              else
              {
                v4 = -2147024362;
              }
            }
            break;
          }
          if ( pvar.vt == 31 )
          {
            v9 = v6;
            if ( v6 >= v7 )
            {
              if ( !(unsigned __int8)ATL::CAtlArray<unsigned short *,ATL::CElementTraits<unsigned short *>>::GrowBuffer(
                                       &v18,
                                       v6 + 1) )
                ATL::AtlThrowImpl(-2147024882);
              v7 = v20;
              v6 = v19;
              v5 = v18;
            }
            v5[v9] = pvar.hVal.QuadPart;
            v19 = ++v6;
          }
          else
          {
            PropVariantClear(&pvar);
            v4 = -2147418113;
          }
        }
        ++v8;
      }
      for ( j = 0; j < v6; ++j )
      {
        v14 = (void *)v5[j];
        if ( v14 )
          CoTaskMemFree(v14);
      }
      if ( v5 )
        free(v5);
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006ae8  mov     [rsp-8+arg_10], rbx
0x180006aed  push    rbp
0x180006aee  push    rsi
0x180006aef  push    rdi
0x180006af0  push    r12
0x180006af2  push    r13
0x180006af4  push    r14
0x180006af6  push    r15
0x180006af8  lea     rbp, [rsp-27h]
0x180006afd  sub     rsp, 100h
0x180006b04  mov     rax, cs:__security_cookie
0x180006b0b  xor     rax, rsp
0x180006b0e  mov     [rbp+57h+var_40], rax
0x180006b12  mov     r13, rdx
0x180006b15  mov     rdi, rcx
0x180006b18  mov     ebx, 80004005h
0x180006b1d  mov     rcx, rdx; pvar
0x180006b20  call    cs:__imp_PropVariantClear
0x180006b26  cmp     word ptr [rdi], 0Dh
0x180006b2a  jnz     loc_180006CA9
0x180006b30  mov     [rsp+130h+var_110], 0
0x180006b39  mov     rcx, [rdi+8]
0x180006b3d  mov     rax, [rcx]
0x180006b40  lea     r8, [rsp+130h+var_110]
0x180006b45  lea     rdx, _GUID_30989668_e1c9_4597_b395_458eedb808df
0x180006b4c  mov     rax, [rax]
0x180006b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b54  mov     ebx, eax
0x180006b56  test    eax, eax
0x180006b58  js      loc_180006C92
0x180006b5e  xor     esi, esi
0x180006b60  mov     [rsp+130h+var_F0], rsi
0x180006b65  xor     edi, edi
0x180006b67  mov     [rsp+130h+var_E8], rdi
0x180006b6c  xor     r15d, r15d
0x180006b6f  mov     [rsp+130h+var_E0], r15
0x180006b74  mov     [rsp+130h+var_D8], esi
0x180006b78  xor     edx, edx; Val
0x180006b7a  mov     r8d, 80h; Size
0x180006b80  lea     rcx, [rbp+57h+var_C0]; void *
0x180006b84  call    memset_0
0x180006b89  xor     r12d, r12d
0x180006b8c  test    ebx, ebx
0x180006b8e  js      loc_180006C7B
0x180006b94  mov     r9d, r12d
0x180006b97  lea     r8, aUintD; "/{uint=%d}"
0x180006b9e  mov     edx, 40h ; '@'; unsigned __int64
0x180006ba3  lea     rcx, [rbp+57h+var_C0]; unsigned __int16 *
0x180006ba7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006bac  mov     ebx, eax
0x180006bae  test    eax, eax
0x180006bb0  js      short loc_180006C0E
0x180006bb2  xorps   xmm0, xmm0
0x180006bb5  xor     eax, eax
0x180006bb7  movups  xmmword ptr [rsp+130h+pvar], xmm0
0x180006bbc  mov     qword ptr [rsp+130h+pvar+10h], rax
0x180006bc1  mov     rcx, [rsp+130h+var_110]
0x180006bc6  mov     rax, [rcx]
0x180006bc9  lea     r8, [rsp+130h+pvar]
0x180006bce  lea     rdx, [rbp+57h+var_C0]
0x180006bd2  mov     rax, [rax+28h]
0x180006bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdb  mov     ebx, eax
0x180006bdd  test    eax, eax
0x180006bdf  js      loc_180006CE9
0x180006be5  cmp     word ptr [rsp+130h+pvar], 1Fh
0x180006beb  jnz     loc_180006D64
0x180006bf1  mov     r14, rdi
0x180006bf4  cmp     rdi, r15
0x180006bf7  jnb     loc_180006D0F
0x180006bfd  mov     rax, qword ptr [rsp+130h+pvar+8]
0x180006c02  mov     [rsi+r14*8], rax
0x180006c06  inc     rdi
0x180006c09  mov     [rsp+130h+var_E8], rdi
0x180006c0e  inc     r12d
0x180006c11  jmp     loc_180006B8C
0x180006c16  mov     [rbp+57h+var_D0], 0
0x180006c1e  mov     eax, 8
0x180006c23  mul     rdi
0x180006c26  mov     r15, rax
0x180006c29  test    rdx, rdx
0x180006c2c  jnz     loc_180006D05
0x180006c32  test    rdi, rdi
0x180006c35  jnz     loc_180006D35
0x180006c3b  xor     ebx, ebx
0x180006c3d  xor     r14d, r14d
0x180006c40  test    ebx, ebx
0x180006c42  js      short loc_180006C7B
0x180006c44  mov     word ptr [r13+0], 101Fh
0x180006c4b  mov     [r13+8], edi
0x180006c4f  mov     [r13+10h], r14
0x180006c53  xor     ecx, ecx
0x180006c55  test    rdi, rdi
0x180006c58  jz      short loc_180006C7B
0x180006c5a  cmp     rcx, rdi
0x180006c5d  jnb     loc_180006D84
0x180006c63  mov     rax, [rsi+rcx*8]
0x180006c67  mov     [r14+rcx*8], rax
0x180006c6b  mov     qword ptr [rsi+rcx*8], 0
0x180006c73  inc     rcx
0x180006c76  cmp     rcx, rdi
0x180006c79  jb      short loc_180006C63
0x180006c7b  xor     r14d, r14d
0x180006c7e  test    rdi, rdi
0x180006c81  jnz     short loc_180006CD2
0x180006c83  test    rsi, rsi
0x180006c86  jz      short loc_180006C92
0x180006c88  mov     rcx, rsi; Block
0x180006c8b  call    cs:__imp_free
0x180006c91  nop
0x180006c92  mov     rcx, [rsp+130h+var_110]
0x180006c97  test    rcx, rcx
0x180006c9a  jz      short loc_180006CA9
0x180006c9c  mov     rax, [rcx]
0x180006c9f  mov     rax, [rax+10h]
0x180006ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca8  nop
0x180006ca9  mov     eax, ebx
0x180006cab  mov     rcx, [rbp+57h+var_40]
0x180006caf  xor     rcx, rsp; StackCookie
0x180006cb2  call    __security_check_cookie
0x180006cb7  mov     rbx, [rsp+130h+arg_10]
0x180006cbf  add     rsp, 100h
0x180006cc6  pop     r15
0x180006cc8  pop     r14
0x180006cca  pop     r13
0x180006ccc  pop     r12
0x180006cce  pop     rdi
0x180006ccf  pop     rsi
0x180006cd0  pop     rbp
0x180006cd1  retn
0x180006cd2  mov     rcx, [rsi+r14*8]; pv
0x180006cd6  test    rcx, rcx
0x180006cd9  jnz     loc_180006D8F
0x180006cdf  inc     r14
0x180006ce2  cmp     r14, rdi
0x180006ce5  jnb     short loc_180006C83
0x180006ce7  jmp     short loc_180006CD2
0x180006ce9  lea     rcx, [rsp+130h+pvar]; pvar
0x180006cee  call    cs:__imp_PropVariantClear
0x180006cf4  cmp     ebx, 88982F40h
0x180006cfa  jz      loc_180006C16
0x180006d00  jmp     loc_180006C7B
0x180006d05  mov     ebx, 80070216h
0x180006d0a  jmp     loc_180006C7B
0x180006d0f  lea     rdx, [rdi+1]
0x180006d13  lea     rcx, [rsp+130h+var_F0]
0x180006d18  call    ?GrowBuffer@?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::GrowBuffer(unsigned __int64)
0x180006d1d  test    al, al
0x180006d1f  jz      short loc_180006D79
0x180006d21  mov     r15, [rsp+130h+var_E0]
0x180006d26  mov     rdi, [rsp+130h+var_E8]
0x180006d2b  mov     rsi, [rsp+130h+var_F0]
0x180006d30  jmp     loc_180006BFD
0x180006d35  mov     rcx, r15; cb
0x180006d38  call    cs:__imp_CoTaskMemAlloc
0x180006d3e  mov     r14, rax
0x180006d41  test    rax, rax
0x180006d44  jz      short loc_180006D5A
0x180006d46  xor     ebx, ebx
0x180006d48  mov     r8, r15; Size
0x180006d4b  xor     edx, edx; Val
0x180006d4d  mov     rcx, rax; void *
0x180006d50  call    memset_0
0x180006d55  jmp     loc_180006C40
0x180006d5a  mov     ebx, 8007000Eh
0x180006d5f  jmp     loc_180006C40
0x180006d64  lea     rcx, [rsp+130h+pvar]; pvar
0x180006d69  call    cs:__imp_PropVariantClear
0x180006d6f  mov     ebx, 8000FFFFh
0x180006d74  jmp     loc_180006C0E
0x180006d79  mov     ecx, 8007000Eh; int
0x180006d7e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006d84  mov     ecx, 80070057h; int
0x180006d89  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006d8f  call    cs:__imp_CoTaskMemFree
0x180006d95  jmp     loc_180006CDF
```
