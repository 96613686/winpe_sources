# CFormatConverterNChannel::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x180010cf0`
- end: `0x18001107f`
- name: `?CopyPixels@CFormatConverterNChannel@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `911`
- prototype: `__int64 __fastcall(CFormatConverterNChannel *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180010cf0`
- `0x1800171c4`
- `0x180021a30`
- `0x180022644`
- `0x180022650`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CFormatConverterNChannel::CopyPixels(
        CFormatConverterNChannel *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  char *v5; // rbx
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  unsigned int v8; // r9d
  INT Height; // r8d
  unsigned __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int Y; // r8d
  __int64 Width; // rax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v21; // rcx
  unsigned int v22; // edx
  unsigned __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // r13d
  unsigned __int8 *v26; // rsi
  signed int v27; // eax
  unsigned int v28; // r12d
  int v29; // eax
  INT X; // [rsp+70h] [rbp-21h] BYREF
  unsigned int v32; // [rsp+74h] [rbp-1Dh]
  int v33; // [rsp+78h] [rbp-19h]
  int v34; // [rsp+7Ch] [rbp-15h]
  __int128 v35; // [rsp+80h] [rbp-11h] BYREF

  v5 = (char *)this - 56;
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this - 48);
  v35 = 0;
  v8 = a3;
  if ( *((_BYTE *)this - 8) )
  {
    EnterCriticalSection_0((LPCRITICAL_SECTION)((char *)this - 48));
    v8 = a3;
  }
  if ( a5 )
  {
    if ( !a2 )
    {
      if ( *((_DWORD *)this + 6) > 0x7FFFFFFFu )
      {
        DWORD2(v35) = -1;
        goto LABEL_18;
      }
      DWORD2(v35) = *((_DWORD *)this + 6);
      if ( *((_DWORD *)this + 7) > 0x7FFFFFFFu )
      {
        HIDWORD(v35) = -1;
        goto LABEL_18;
      }
      HIDWORD(v35) = *((_DWORD *)this + 7);
      a2 = (const struct WICRect *)&v35;
    }
    Height = a2->Height;
    if ( Height )
    {
      v12 = (unsigned int)a2->Width * (unsigned __int64)*((unsigned int *)this + 23);
      if ( v12 > 0xFFFFFFFF
        || (v21 = (unsigned int)v12 * (unsigned __int64)*((unsigned int *)this + 20), v21 > 0xFFFFFFFF)
        || (v22 = v21 + 7, (int)v21 + 7 < (unsigned int)v21)
        || (v23 = v8 * (unsigned __int64)(unsigned int)(Height - 1), v23 > 0xFFFFFFFF)
        || (v24 = (v22 >> 3) + v23, v24 < (unsigned int)v23) )
      {
        if ( g_doStackCaptures )
          DoStackCapture(-2147024362);
        v13 = -2147024362;
        goto LABEL_10;
      }
      v13 = 0;
    }
    else
    {
      v13 = 0;
      v24 = 0;
    }
    if ( v24 > a4 )
    {
      v13 = -2003292276;
      if ( g_doStackCaptures )
        DoStackCapture(-2003292276);
    }
    if ( v13 >= 0 )
    {
      v14 = *((_QWORD *)this + 17);
      if ( !v14 )
      {
LABEL_21:
        v6 = (struct _RTL_CRITICAL_SECTION *)(v5 + 8);
        goto LABEL_22;
      }
      if ( !*((_QWORD *)this + 16) )
      {
        v29 = (*(__int64 (__fastcall **)(__int64, const struct WICRect *, _QWORD, _QWORD, unsigned __int8 *))(*(_QWORD *)v14 + 56LL))(
                v14,
                a2,
                a3,
                a4,
                a5);
        v13 = v29;
        if ( v29 < 0 && g_doStackCaptures )
LABEL_49:
          DoStackCapture(v29);
        goto LABEL_21;
      }
      v15 = *((unsigned int *)this + 23);
      Y = a2->Y;
      X = a2->X;
      Width = (unsigned int)a2->Width;
      v18 = Width * v15;
      v32 = Y;
      v33 = Width;
      v34 = 1;
      if ( v18 <= 0xFFFFFFFF )
      {
        v19 = (unsigned int)v18 * (unsigned __int64)*((unsigned int *)this + 20);
        if ( v19 <= 0xFFFFFFFF && (int)v19 + 7 >= (unsigned int)v19 )
        {
          v25 = Y + a2->Height;
          if ( v25 >= Y )
          {
            v26 = a5;
            v27 = Y;
            v28 = (unsigned int)(v19 + 7) >> 3;
            v13 = 0;
            while ( 1 )
            {
              v32 = v27;
              if ( v27 >= (int)v25 )
                goto LABEL_21;
              v29 = (*(__int64 (__fastcall **)(_QWORD, INT *, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 17) + 56LL))(
                      *((_QWORD *)this + 17),
                      &X,
                      *((unsigned int *)this + 30),
                      *((unsigned int *)this + 30),
                      *((_QWORD *)this + 14));
              v13 = v29;
              if ( v29 < 0 )
              {
                if ( g_doStackCaptures )
                  goto LABEL_49;
                goto LABEL_21;
              }
              v29 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned __int8 *, unsigned int, _QWORD, INT, _DWORD, _DWORD))this
                     + 16))(
                      *((_QWORD *)this + 18),
                      *((_QWORD *)this + 14),
                      *((unsigned int *)this + 30),
                      *((_QWORD *)this + 12),
                      v26,
                      v28,
                      *((_QWORD *)this + 13),
                      a2->Width,
                      *((_DWORD *)this + 18),
                      *((_DWORD *)this + 38));
              v13 = v29;
              if ( v29 < 0 )
              {
                if ( g_doStackCaptures )
                  goto LABEL_49;
                goto LABEL_21;
              }
              v26 += a3;
              v27 = v32 + 1;
            }
          }
        }
      }
LABEL_18:
      if ( g_doStackCaptures )
        DoStackCapture(-2147024362);
      v13 = -2147024362;
      goto LABEL_21;
    }
LABEL_10:
    if ( g_doStackCaptures )
      DoStackCapture(v13);
    goto LABEL_21;
  }
  v13 = -2147024809;
  if ( g_doStackCaptures )
    DoStackCapture(-2147024809);
LABEL_22:
  if ( v5 && v5[48] )
    LeaveCriticalSection_0(v6);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180010cf0  push    rbp
0x180010cf2  push    rbx
0x180010cf3  push    rsi
0x180010cf4  push    rdi
0x180010cf5  push    r12
0x180010cf7  push    r13
0x180010cf9  push    r14
0x180010cfb  push    r15
0x180010cfd  lea     rbp, [rsp-17h]
0x180010d02  sub     rsp, 0A8h
0x180010d09  mov     rax, cs:__security_cookie
0x180010d10  xor     rax, rsp
0x180010d13  mov     [rbp+4Fh+var_50], rax
0x180010d17  mov     r12, [rbp+4Fh+arg_20]
0x180010d1b  lea     rbx, [rcx-38h]
0x180010d1f  xorps   xmm0, xmm0
0x180010d22  mov     [rbp+4Fh+var_80], r8d
0x180010d26  lea     rsi, [rbx+8]
0x180010d2a  mov     [rbp+4Fh+var_78], r12
0x180010d2e  movups  [rbp+4Fh+var_60], xmm0
0x180010d32  cmp     byte ptr [rsi+28h], 0
0x180010d36  mov     r13d, r9d
0x180010d39  mov     r9d, r8d
0x180010d3c  mov     r15, rdx
0x180010d3f  mov     r14, rcx
0x180010d42  jz      short loc_180010D50
0x180010d44  mov     rcx, rsi; lpCriticalSection
0x180010d47  call    EnterCriticalSection_0
0x180010d4c  mov     r9d, [rbp+4Fh+var_80]
0x180010d50  test    r12, r12
0x180010d53  jz      loc_180010FB2
0x180010d59  test    r15, r15
0x180010d5c  jz      loc_180011041
0x180010d62  mov     r8d, [r15+0Ch]
0x180010d66  mov     esi, 80070216h
0x180010d6b  mov     r10d, 0FFFFFFFFh
0x180010d71  test    r8d, r8d
0x180010d74  jz      loc_180010FD0
0x180010d7a  mov     edx, [r14+5Ch]
0x180010d7e  mov     eax, [r15+8]
0x180010d82  imul    rdx, rax
0x180010d86  cmp     rdx, r10
0x180010d89  jbe     loc_180010E5C
0x180010d8f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010d96  jnz     loc_180010FD9
0x180010d9c  mov     edi, esi
0x180010d9e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010da5  jnz     loc_180010F9A
0x180010dab  test    edi, edi
0x180010dad  js      short loc_180010E23
0x180010daf  mov     rcx, [r14+88h]
0x180010db6  test    rcx, rcx
0x180010db9  jz      short loc_180010E23
0x180010dbb  cmp     qword ptr [r14+80h], 0
0x180010dc3  jz      loc_180010FE5
0x180010dc9  mov     eax, [r15]
0x180010dcc  mov     r9d, 0FFFFFFFFh
0x180010dd2  mov     edx, [r14+5Ch]
0x180010dd6  mov     r8d, [r15+4]
0x180010dda  mov     [rbp+4Fh+var_70], eax
0x180010ddd  mov     eax, [r15+8]
0x180010de1  imul    rdx, rax
0x180010de5  mov     [rbp+4Fh+var_6C], r8d
0x180010de9  mov     [rbp+4Fh+var_68], eax
0x180010dec  mov     [rbp+4Fh+var_64], 1
0x180010df3  cmp     rdx, r9
0x180010df6  ja      short loc_180010E14
0x180010df8  mov     ecx, [r14+50h]
0x180010dfc  mov     eax, edx
0x180010dfe  imul    rcx, rax
0x180010e02  cmp     rcx, r9
0x180010e05  ja      short loc_180010E14
0x180010e07  lea     r12d, [rcx+7]
0x180010e0b  cmp     r12d, ecx
0x180010e0e  jnb     loc_180010EB4
0x180010e14  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010e1b  jnz     loc_180010FA6
0x180010e21  mov     edi, esi
0x180010e23  lea     rsi, [rbx+8]
0x180010e27  test    rbx, rbx
0x180010e2a  jz      short loc_180010E3A
0x180010e2c  cmp     byte ptr [rbx+30h], 0
0x180010e30  jz      short loc_180010E3A
0x180010e32  mov     rcx, rsi; lpCriticalSection
0x180010e35  call    LeaveCriticalSection_0
0x180010e3a  mov     eax, edi
0x180010e3c  mov     rcx, [rbp+4Fh+var_50]
0x180010e40  xor     rcx, rsp; StackCookie
0x180010e43  call    __security_check_cookie
0x180010e48  add     rsp, 0A8h
0x180010e4f  pop     r15
0x180010e51  pop     r14
0x180010e53  pop     r13
0x180010e55  pop     r12
0x180010e57  pop     rdi
0x180010e58  pop     rsi
0x180010e59  pop     rbx
0x180010e5a  pop     rbp
0x180010e5b  retn
0x180010e5c  mov     ecx, [r14+50h]
0x180010e60  mov     eax, edx
0x180010e62  imul    rcx, rax
0x180010e66  cmp     rcx, r10
0x180010e69  ja      loc_180010D8F
0x180010e6f  lea     edx, [rcx+7]
0x180010e72  cmp     edx, ecx
0x180010e74  jb      loc_180010D8F
0x180010e7a  lea     ecx, [r8-1]
0x180010e7e  mov     eax, r9d
0x180010e81  imul    rcx, rax
0x180010e85  cmp     rcx, r10
0x180010e88  ja      loc_180010D8F
0x180010e8e  shr     edx, 3
0x180010e91  lea     eax, [rdx+rcx]
0x180010e94  cmp     eax, ecx
0x180010e96  jb      loc_180010D8F
0x180010e9c  xor     edi, edi
0x180010e9e  cmp     eax, r13d
0x180010ea1  ja      loc_180011023
0x180010ea7  test    edi, edi
0x180010ea9  js      loc_180010D9E
0x180010eaf  jmp     loc_180010DAF
0x180010eb4  mov     r13d, [r15+0Ch]
0x180010eb8  add     r13d, r8d
0x180010ebb  cmp     r13d, r8d
0x180010ebe  jb      loc_180010E14
0x180010ec4  mov     rsi, [rbp+4Fh+var_78]
0x180010ec8  mov     eax, r8d
0x180010ecb  shr     r12d, 3
0x180010ecf  xor     edi, edi
0x180010ed1  mov     [rbp+4Fh+var_6C], eax
0x180010ed4  cmp     eax, r13d
0x180010ed7  jge     loc_180010E23
0x180010edd  mov     rcx, [r14+88h]
0x180010ee4  lea     rdx, [rbp+4Fh+var_70]
0x180010ee8  mov     r8d, [r14+78h]
0x180010eec  mov     r9d, r8d
0x180010eef  mov     rax, [rcx]
0x180010ef2  mov     r10, [rax+38h]
0x180010ef6  mov     rax, [r14+70h]
0x180010efa  mov     [rsp+0E0h+var_C0], rax
0x180010eff  mov     rax, r10
0x180010f02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f07  mov     edi, eax
0x180010f09  test    eax, eax
0x180010f0b  jns     short loc_180010F22
0x180010f0d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010f14  jnz     loc_180011017
0x180010f1a  test    eax, eax
0x180010f1c  js      loc_180010E23
0x180010f22  mov     eax, [r14+98h]
0x180010f29  mov     r9, [r14+60h]
0x180010f2d  mov     r8d, [r14+78h]
0x180010f31  mov     rdx, [r14+70h]
0x180010f35  mov     rcx, [r14+90h]
0x180010f3c  mov     [rsp+0E0h+var_98], eax
0x180010f40  mov     eax, [r14+48h]
0x180010f44  mov     [rsp+0E0h+var_A0], eax
0x180010f48  mov     eax, [r15+8]
0x180010f4c  mov     [rsp+0E0h+var_A8], eax
0x180010f50  mov     rax, [r14+68h]
0x180010f54  mov     [rsp+0E0h+var_B0], rax
0x180010f59  mov     rax, [r14+80h]
0x180010f60  mov     [rsp+0E0h+var_B8], r12d
0x180010f65  mov     [rsp+0E0h+var_C0], rsi
0x180010f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f6f  mov     edi, eax
0x180010f71  test    eax, eax
0x180010f73  jns     short loc_180010F8A
0x180010f75  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010f7c  jnz     loc_180011017
0x180010f82  test    eax, eax
0x180010f84  js      loc_180010E23
0x180010f8a  mov     eax, [rbp+4Fh+var_80]
0x180010f8d  add     rsi, rax
0x180010f90  mov     eax, [rbp+4Fh+var_6C]
0x180010f93  inc     eax
0x180010f95  jmp     loc_180010ED1
0x180010f9a  mov     ecx, edi; int
0x180010f9c  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010fa1  jmp     loc_180010DAB
0x180010fa6  mov     ecx, esi; int
0x180010fa8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010fad  jmp     loc_180010E21
0x180010fb2  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180010fb9  mov     edi, 80070057h
0x180010fbe  jz      loc_180010E27
0x180010fc4  mov     ecx, edi; int
0x180010fc6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010fcb  jmp     loc_180010E27
0x180010fd0  xor     edi, edi
0x180010fd2  xor     eax, eax
0x180010fd4  jmp     loc_180010E9E
0x180010fd9  mov     ecx, esi; int
0x180010fdb  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010fe0  jmp     loc_180010D9C
0x180010fe5  mov     rax, [rcx]
0x180010fe8  mov     r9d, r13d
0x180010feb  mov     r8d, [rbp+4Fh+var_80]
0x180010fef  mov     rdx, r15
0x180010ff2  mov     [rsp+0E0h+var_C0], r12
0x180010ff7  mov     rax, [rax+38h]
0x180010ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011000  mov     edi, eax
0x180011002  test    eax, eax
0x180011004  jns     loc_180010E23
0x18001100a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011011  jz      loc_180010E23
0x180011017  mov     ecx, eax; int
0x180011019  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001101e  jmp     loc_180010E23
0x180011023  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001102a  mov     edi, 88982F8Ch
0x18001102f  jz      loc_180010EA7
0x180011035  mov     ecx, edi; int
0x180011037  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001103c  jmp     loc_180010EA7
0x180011041  mov     eax, [r14+18h]
0x180011045  mov     ecx, 7FFFFFFFh
0x18001104a  cmp     eax, ecx
0x18001104c  ja      short loc_18001106E
0x18001104e  mov     dword ptr [rbp+4Fh+var_60+8], eax
0x180011051  mov     eax, [r14+1Ch]
0x180011055  cmp     eax, ecx
0x180011057  ja      short loc_180011065
0x180011059  mov     dword ptr [rbp+4Fh+var_60+0Ch], eax
0x18001105c  lea     r15, [rbp+4Fh+var_60]
0x180011060  jmp     loc_180010D62
0x180011065  mov     dword ptr [rbp+4Fh+var_60+0Ch], 0FFFFFFFFh
0x18001106c  jmp     short loc_180011075
0x18001106e  mov     dword ptr [rbp+4Fh+var_60+8], 0FFFFFFFFh
0x180011075  mov     esi, 80070216h
0x18001107a  jmp     loc_180010E14
```
