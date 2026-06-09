# ConvertXMPArrayToStringVectorOnRead(tagPROPVARIANT const *,tagPROPVARIANT *)

- ea: `0x180007db8`
- end: `0x180008090`
- name: `?ConvertXMPArrayToStringVectorOnRead@@YAJPEBUtagPROPVARIANT@@PEAU1@@Z`
- size: `728`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, struct tagPROPVARIANT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007af0`

## callees

- `0x180007db8`
- `0x1800089f0`
- `0x180008a74`
- `0x1800147f8`
- `0x180016a40`
- `0x180017408`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f61`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f61`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007df0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007fcb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008052`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007df0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007fcb`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008052`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000801b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000801b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000807e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000807e`

## pseudocode

```c
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
0x180007db8  mov     [rsp-8+arg_10], rbx
0x180007dbd  push    rbp
0x180007dbe  push    rsi
0x180007dbf  push    rdi
0x180007dc0  push    r12
0x180007dc2  push    r13
0x180007dc4  push    r14
0x180007dc6  push    r15
0x180007dc8  lea     rbp, [rsp-27h]
0x180007dcd  sub     rsp, 100h
0x180007dd4  mov     rax, cs:__security_cookie
0x180007ddb  xor     rax, rsp
0x180007dde  mov     [rbp+57h+var_40], rax
0x180007de2  mov     r13, rdx
0x180007de5  mov     rdi, rcx
0x180007de8  mov     ebx, 80004005h
0x180007ded  mov     rcx, rdx; pvar
0x180007df0  call    cs:__imp_PropVariantClear
0x180007df7  nop     dword ptr [rax+rax+00h]
0x180007dfc  cmp     word ptr [rdi], 0Dh
0x180007e00  jnz     loc_180007F85
0x180007e06  mov     [rsp+130h+var_110], 0
0x180007e0f  mov     rcx, [rdi+8]
0x180007e13  mov     rax, [rcx]
0x180007e16  lea     r8, [rsp+130h+var_110]
0x180007e1b  lea     rdx, _GUID_30989668_e1c9_4597_b395_458eedb808df
0x180007e22  mov     rax, [rax]
0x180007e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e2a  mov     ebx, eax
0x180007e2c  test    eax, eax
0x180007e2e  js      loc_180007F6E
0x180007e34  xor     esi, esi
0x180007e36  mov     [rsp+130h+var_F0], rsi
0x180007e3b  xor     edi, edi
0x180007e3d  mov     [rsp+130h+var_E8], rdi
0x180007e42  xor     r15d, r15d
0x180007e45  mov     [rsp+130h+var_E0], r15
0x180007e4a  mov     [rsp+130h+var_D8], esi
0x180007e4e  xor     edx, edx; Val
0x180007e50  mov     r8d, 80h; Size
0x180007e56  lea     rcx, [rbp+57h+var_C0]; void *
0x180007e5a  call    memset_0
0x180007e5f  xor     r12d, r12d
0x180007e62  test    ebx, ebx
0x180007e64  js      loc_180007F51
0x180007e6a  mov     r9d, r12d
0x180007e6d  lea     r8, aUintD; "/{uint=%d}"
0x180007e74  mov     edx, 40h ; '@'; unsigned __int64
0x180007e79  lea     rcx, [rbp+57h+var_C0]; unsigned __int16 *
0x180007e7d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007e82  mov     ebx, eax
0x180007e84  test    eax, eax
0x180007e86  js      short loc_180007EE4
0x180007e88  xorps   xmm0, xmm0
0x180007e8b  xor     eax, eax
0x180007e8d  movups  xmmword ptr [rsp+130h+pvar], xmm0
0x180007e92  mov     qword ptr [rsp+130h+pvar+10h], rax
0x180007e97  mov     rcx, [rsp+130h+var_110]
0x180007e9c  mov     rax, [rcx]
0x180007e9f  lea     r8, [rsp+130h+pvar]
0x180007ea4  lea     rdx, [rbp+57h+var_C0]
0x180007ea8  mov     rax, [rax+28h]
0x180007eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eb1  mov     ebx, eax
0x180007eb3  test    eax, eax
0x180007eb5  js      loc_180007FC6
0x180007ebb  cmp     word ptr [rsp+130h+pvar], 1Fh
0x180007ec1  jnz     loc_18000804D
0x180007ec7  mov     r14, rdi
0x180007eca  cmp     rdi, r15
0x180007ecd  jnb     loc_180007FF2
0x180007ed3  mov     rax, qword ptr [rsp+130h+pvar+8]
0x180007ed8  mov     [rsi+r14*8], rax
0x180007edc  inc     rdi
0x180007edf  mov     [rsp+130h+var_E8], rdi
0x180007ee4  inc     r12d
0x180007ee7  jmp     loc_180007E62
0x180007eec  mov     [rbp+57h+var_D0], 0
0x180007ef4  mov     eax, 8
0x180007ef9  mul     rdi
0x180007efc  mov     r15, rax
0x180007eff  test    rdx, rdx
0x180007f02  jnz     loc_180007FE8
0x180007f08  test    rdi, rdi
0x180007f0b  jnz     loc_180008018
0x180007f11  xor     ebx, ebx
0x180007f13  xor     r14d, r14d
0x180007f16  test    ebx, ebx
0x180007f18  js      short loc_180007F51
0x180007f1a  mov     word ptr [r13+0], 101Fh
0x180007f21  mov     [r13+8], edi
0x180007f25  mov     [r13+10h], r14
0x180007f29  xor     ecx, ecx
0x180007f2b  test    rdi, rdi
0x180007f2e  jz      short loc_180007F51
0x180007f30  cmp     rcx, rdi
0x180007f33  jnb     loc_180008073
0x180007f39  mov     rax, [rsi+rcx*8]
0x180007f3d  mov     [r14+rcx*8], rax
0x180007f41  mov     qword ptr [rsi+rcx*8], 0
0x180007f49  inc     rcx
0x180007f4c  cmp     rcx, rdi
0x180007f4f  jb      short loc_180007F39
0x180007f51  xor     r14d, r14d
0x180007f54  test    rdi, rdi
0x180007f57  jnz     short loc_180007FAF
0x180007f59  test    rsi, rsi
0x180007f5c  jz      short loc_180007F6E
0x180007f5e  mov     rcx, rsi; Block
0x180007f61  call    cs:__imp_free
0x180007f68  nop     dword ptr [rax+rax+00h]
0x180007f6d  nop
0x180007f6e  mov     rcx, [rsp+130h+var_110]
0x180007f73  test    rcx, rcx
0x180007f76  jz      short loc_180007F85
0x180007f78  mov     rax, [rcx]
0x180007f7b  mov     rax, [rax+10h]
0x180007f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f84  nop
0x180007f85  mov     eax, ebx
0x180007f87  mov     rcx, [rbp+57h+var_40]
0x180007f8b  xor     rcx, rsp; StackCookie
0x180007f8e  call    __security_check_cookie
0x180007f93  mov     rbx, [rsp+130h+arg_10]
0x180007f9b  add     rsp, 100h
0x180007fa2  pop     r15
0x180007fa4  pop     r14
0x180007fa6  pop     r13
0x180007fa8  pop     r12
0x180007faa  pop     rdi
0x180007fab  pop     rsi
0x180007fac  pop     rbp
0x180007fad  retn
0x180007faf  mov     rcx, [rsi+r14*8]; pv
0x180007fb3  test    rcx, rcx
0x180007fb6  jnz     loc_18000807E
0x180007fbc  inc     r14
0x180007fbf  cmp     r14, rdi
0x180007fc2  jnb     short loc_180007F59
0x180007fc4  jmp     short loc_180007FAF
0x180007fc6  lea     rcx, [rsp+130h+pvar]; pvar
0x180007fcb  call    cs:__imp_PropVariantClear
0x180007fd2  nop     dword ptr [rax+rax+00h]
0x180007fd7  cmp     ebx, 88982F40h
0x180007fdd  jz      loc_180007EEC
0x180007fe3  jmp     loc_180007F51
0x180007fe8  mov     ebx, 80070216h
0x180007fed  jmp     loc_180007F51
0x180007ff2  lea     rdx, [rdi+1]
0x180007ff6  lea     rcx, [rsp+130h+var_F0]
0x180007ffb  call    ?GrowBuffer@?$CAtlArray@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ushort *,ATL::CElementTraits<ushort *>>::GrowBuffer(unsigned __int64)
0x180008000  test    al, al
0x180008002  jz      short loc_180008068
0x180008004  mov     r15, [rsp+130h+var_E0]
0x180008009  mov     rdi, [rsp+130h+var_E8]
0x18000800e  mov     rsi, [rsp+130h+var_F0]
0x180008013  jmp     loc_180007ED3
0x180008018  mov     rcx, r15; cb
0x18000801b  call    cs:__imp_CoTaskMemAlloc
0x180008022  nop     dword ptr [rax+rax+00h]
0x180008027  mov     r14, rax
0x18000802a  test    rax, rax
0x18000802d  jz      short loc_180008043
0x18000802f  xor     ebx, ebx
0x180008031  mov     r8, r15; Size
0x180008034  xor     edx, edx; Val
0x180008036  mov     rcx, rax; void *
0x180008039  call    memset_0
0x18000803e  jmp     loc_180007F16
0x180008043  mov     ebx, 8007000Eh
0x180008048  jmp     loc_180007F16
0x18000804d  lea     rcx, [rsp+130h+pvar]; pvar
0x180008052  call    cs:__imp_PropVariantClear
0x180008059  nop     dword ptr [rax+rax+00h]
0x18000805e  mov     ebx, 8000FFFFh
0x180008063  jmp     loc_180007EE4
0x180008068  mov     ecx, 8007000Eh; int
0x18000806d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008073  mov     ecx, 80070057h; int
0x180008078  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000807e  call    cs:__imp_CoTaskMemFree
0x180008085  nop     dword ptr [rax+rax+00h]
0x18000808a  jmp     loc_180007FBC
```
