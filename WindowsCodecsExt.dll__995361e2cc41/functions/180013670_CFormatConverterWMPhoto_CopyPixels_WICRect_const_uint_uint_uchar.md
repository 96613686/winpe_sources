# CFormatConverterWMPhoto::CopyPixels(WICRect const *,uint,uint,uchar *)

- ea: `0x180013670`
- end: `0x18001395f`
- name: `?CopyPixels@CFormatConverterWMPhoto@@UEAAJPEBUWICRect@@IIPEAE@Z`
- size: `751`
- prototype: `__int64 __fastcall(CFormatConverterWMPhoto *__hidden this, const struct WICRect *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops`

## callees

- `0x1800058c0`
- `0x1800058e0`
- `0x180013670`
- `0x1800171c4`
- `0x180021628`
- `0x180021634`
- `0x180021a30`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CFormatConverterWMPhoto::CopyPixels(
        CFormatConverterWMPhoto *this,
        const struct WICRect *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned __int8 *a5)
{
  CMTALock *v5; // rbx
  __int64 v7; // r13
  __int64 v10; // r9
  unsigned int v11; // edi
  unsigned __int64 v12; // r12
  INT Width; // ecx
  INT v15; // edx
  INT Height; // ecx
  INT Y; // eax
  unsigned __int64 v18; // rax
  int v19; // eax
  int v20; // ecx
  unsigned int X; // eax
  INT v22; // ecx
  __int64 v23; // rdx
  INT v24; // r8d
  unsigned __int64 v25; // r15
  void *v26; // rdx
  INT v27; // ecx
  INT v28; // eax
  __int64 v29; // rcx
  INT v30; // r13d
  unsigned int v31; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v32; // [rsp+34h] [rbp-4Ch] BYREF
  void *Block; // [rsp+38h] [rbp-48h]
  unsigned __int8 *v34; // [rsp+40h] [rbp-40h]
  __int64 v35; // [rsp+48h] [rbp-38h]
  __int128 v36; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v37[2]; // [rsp+60h] [rbp-20h] BYREF
  INT v38; // [rsp+68h] [rbp-18h]
  int v39; // [rsp+6Ch] [rbp-14h]

  v5 = (CFormatConverterWMPhoto *)((char *)this - 56);
  v7 = a3;
  v34 = a5;
  Block = 0;
  v36 = 0;
  CMTALock::Enter((CFormatConverterWMPhoto *)((char *)this - 56));
  if ( !a5 )
  {
    v11 = -2147024809;
    goto LABEL_7;
  }
  v10 = *((_QWORD *)this + 9);
  if ( !v10 || !*((_QWORD *)this + 8) )
  {
    v11 = -2003292412;
LABEL_7:
    if ( !g_doStackCaptures )
      goto LABEL_8;
    v20 = v11;
LABEL_26:
    DoStackCapture(v20);
    goto LABEL_8;
  }
  if ( !a2 )
  {
    if ( *((_DWORD *)this + 4) > 0x7FFFFFFFu )
      goto LABEL_17;
    DWORD2(v36) = *((_DWORD *)this + 4);
    if ( *((_DWORD *)this + 5) > 0x7FFFFFFFu )
      goto LABEL_17;
    HIDWORD(v36) = *((_DWORD *)this + 5);
    a2 = (const struct WICRect *)&v36;
  }
  Width = a2->Width;
  v15 = Width + a2->X;
  if ( Width > v15 )
    goto LABEL_20;
  if ( a2->X > v15 )
    goto LABEL_20;
  Height = a2->Height;
  Y = a2->Y;
  if ( Height > Y + Height || Y > Y + Height )
    goto LABEL_20;
  v35 = v7;
  v18 = v7 * (unsigned int)Height;
  if ( v18 > 0xFFFFFFFF )
  {
LABEL_17:
    v11 = -2147024362;
    goto LABEL_7;
  }
  if ( (unsigned int)v18 > a4 )
  {
    v11 = -2003292276;
    goto LABEL_7;
  }
  v31 = 0;
  v32 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(*(_QWORD *)v10 + 24LL))(v10, &v31, &v32);
  v11 = v19;
  if ( v19 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_8;
LABEL_25:
    v20 = v19;
    goto LABEL_26;
  }
  X = a2->X;
  if ( a2->X < 0
    || (v22 = a2->Y, v22 < 0)
    || v22 >= v32
    || X >= v31
    || (v23 = a2->Width, (int)v23 < 0)
    || (v24 = a2->Height, v24 < 0)
    || (unsigned int)v23 + X > v31
    || v22 + v24 > v32 )
  {
LABEL_20:
    v11 = -2003292273;
    goto LABEL_7;
  }
  v12 = (v23 * (unsigned __int64)*((unsigned int *)this + 15) + 7) >> 3;
  if ( (unsigned int)v12 > (unsigned int)v7 )
  {
    v11 = -2003292276;
    goto LABEL_7;
  }
  v25 = (v23 * (unsigned __int64)*((unsigned int *)this + 14) + 7) >> 3;
  Block = operator new[]((unsigned int)v25);
  v26 = Block;
  if ( !Block )
  {
    v11 = -2147024882;
    goto LABEL_7;
  }
  v11 = 0;
  v30 = 0;
  if ( a2->Height > 0 )
  {
    while ( 1 )
    {
      v27 = a2->Y;
      v37[0] = a2->X;
      v28 = a2->Width;
      v37[1] = v30 + v27;
      v29 = *((_QWORD *)this + 9);
      v38 = v28;
      v39 = 1;
      v19 = (*(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, _QWORD, void *))(*(_QWORD *)v29 + 56LL))(
              v29,
              v37,
              (unsigned int)v25,
              (unsigned int)v25,
              v26);
      v11 = v19;
      if ( v19 < 0 )
      {
        if ( g_doStackCaptures )
          goto LABEL_25;
        goto LABEL_8;
      }
      v19 = (*((__int64 (__fastcall **)(unsigned __int8 *, _QWORD, void *, _QWORD, INT))this + 8))(
              v34,
              (unsigned int)v12,
              Block,
              (unsigned int)v25,
              v38);
      v11 = v19;
      if ( v19 < 0 )
        break;
      ++v30;
      v34 += v35;
      if ( v30 >= a2->Height )
        goto LABEL_8;
      v26 = Block;
    }
    if ( g_doStackCaptures )
      goto LABEL_25;
  }
LABEL_8:
  operator delete(Block);
  if ( v5 )
    CMTALock::Leave(v5);
  return v11;
}

```

## disassembly

```asm
0x180013670  mov     [rsp-38h+arg_10], rbx
0x180013675  push    rbp
0x180013676  push    rsi
0x180013677  push    rdi
0x180013678  push    r12
0x18001367a  push    r13
0x18001367c  push    r14
0x18001367e  push    r15
0x180013680  mov     rbp, rsp
0x180013683  sub     rsp, 80h
0x18001368a  mov     rax, cs:__security_cookie
0x180013691  xor     rax, rsp
0x180013694  mov     [rbp+var_10], rax
0x180013698  mov     r15, [rbp+arg_20]
0x18001369c  lea     rbx, [rcx-38h]
0x1800136a0  mov     r14, rcx
0x1800136a3  mov     r13d, r8d
0x1800136a6  xorps   xmm0, xmm0
0x1800136a9  mov     [rbp+var_40], r15
0x1800136ad  xor     r12d, r12d
0x1800136b0  mov     rcx, rbx; this
0x1800136b3  mov     edi, r9d
0x1800136b6  mov     [rbp+Block], r12
0x1800136ba  mov     rsi, rdx
0x1800136bd  movups  [rbp+var_30], xmm0
0x1800136c1  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800136c6  test    r15, r15
0x1800136c9  jz      loc_180013916
0x1800136cf  mov     r9, [r14+48h]
0x1800136d3  test    r9, r9
0x1800136d6  jz      short loc_1800136DE
0x1800136d8  cmp     [r14+40h], r12
0x1800136dc  jnz     short loc_180013755
0x1800136de  mov     edi, 88982F04h
0x1800136e3  jmp     short loc_180013709
0x1800136e5  mov     r12d, [r14+3Ch]
0x1800136e9  mov     rax, rdx
0x1800136ec  imul    r12, rdx
0x1800136f0  add     r12, 7
0x1800136f4  shr     r12, 3
0x1800136f8  cmp     r12d, r13d
0x1800136fb  jbe     loc_180013834
0x180013701  mov     edi, 88982F8Ch
0x180013706  xor     r12d, r12d
0x180013709  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180013710  jnz     loc_180013866
0x180013716  mov     rcx, [rbp+Block]; Block
0x18001371a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001371f  test    rbx, rbx
0x180013722  jz      short loc_18001372C
0x180013724  mov     rcx, rbx; this
0x180013727  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x18001372c  mov     eax, edi
0x18001372e  mov     rcx, [rbp+var_10]
0x180013732  xor     rcx, rsp; StackCookie
0x180013735  call    __security_check_cookie
0x18001373a  mov     rbx, [rsp+80h+arg_10]
0x180013742  add     rsp, 80h
0x180013749  pop     r15
0x18001374b  pop     r14
0x18001374d  pop     r13
0x18001374f  pop     r12
0x180013751  pop     rdi
0x180013752  pop     rsi
0x180013753  pop     rbp
0x180013754  retn
0x180013755  test    rsi, rsi
0x180013758  jz      loc_180013920
0x18001375e  mov     ecx, [rsi+8]
0x180013761  mov     eax, [rsi]
0x180013763  lea     edx, [rcx+rax]
0x180013766  cmp     ecx, edx
0x180013768  jg      short loc_1800137B1
0x18001376a  cmp     eax, edx
0x18001376c  jg      short loc_1800137B1
0x18001376e  mov     ecx, [rsi+0Ch]
0x180013771  mov     eax, [rsi+4]
0x180013774  lea     edx, [rax+rcx]
0x180013777  cmp     ecx, edx
0x180013779  jg      short loc_1800137B1
0x18001377b  cmp     eax, edx
0x18001377d  jg      short loc_1800137B1
0x18001377f  mov     eax, ecx
0x180013781  mov     [rbp+var_38], r13
0x180013785  imul    rax, r13
0x180013789  mov     ecx, 0FFFFFFFFh
0x18001378e  cmp     rax, rcx
0x180013791  jbe     short loc_1800137BB
0x180013793  mov     edi, 80070216h
0x180013798  jmp     loc_180013709
0x18001379d  add     eax, edx
0x18001379f  cmp     eax, [rbp+var_50]
0x1800137a2  ja      short loc_1800137B1
0x1800137a4  lea     eax, [rcx+r8]
0x1800137a8  cmp     eax, [rbp+var_4C]
0x1800137ab  jbe     loc_1800136E5
0x1800137b1  mov     edi, 88982F8Fh
0x1800137b6  jmp     loc_180013709
0x1800137bb  cmp     eax, edi
0x1800137bd  jbe     short loc_1800137C9
0x1800137bf  mov     edi, 88982F8Ch
0x1800137c4  jmp     loc_180013709
0x1800137c9  mov     [rbp+var_50], r12d
0x1800137cd  lea     r8, [rbp+var_4C]
0x1800137d1  mov     [rbp+var_4C], r12d
0x1800137d5  lea     rdx, [rbp+var_50]
0x1800137d9  mov     rax, [r9]
0x1800137dc  mov     rcx, r9
0x1800137df  mov     rax, [rax+18h]
0x1800137e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137e8  mov     edi, eax
0x1800137ea  test    eax, eax
0x1800137ec  jns     short loc_180013807
0x1800137ee  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800137f5  jz      loc_180013716
0x1800137fb  mov     ecx, eax; int
0x1800137fd  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180013802  jmp     loc_180013716
0x180013807  mov     eax, [rsi]
0x180013809  test    eax, eax
0x18001380b  js      short loc_1800137B1
0x18001380d  mov     ecx, [rsi+4]
0x180013810  test    ecx, ecx
0x180013812  js      short loc_1800137B1
0x180013814  cmp     ecx, [rbp+var_4C]
0x180013817  jnb     short loc_1800137B1
0x180013819  cmp     eax, [rbp+var_50]
0x18001381c  jnb     short loc_1800137B1
0x18001381e  movsxd  rdx, dword ptr [rsi+8]
0x180013822  test    edx, edx
0x180013824  js      short loc_1800137B1
0x180013826  mov     r8d, [rsi+0Ch]
0x18001382a  test    r8d, r8d
0x18001382d  js      short loc_1800137B1
0x18001382f  jmp     loc_18001379D
0x180013834  mov     r15d, [r14+38h]
0x180013838  imul    r15, rax
0x18001383c  add     r15, 7
0x180013840  shr     r15, 3
0x180013844  mov     ecx, r15d; unsigned __int64
0x180013847  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18001384c  mov     [rbp+Block], rax
0x180013850  mov     rdx, rax
0x180013853  test    rax, rax
0x180013856  jnz     loc_18001394C
0x18001385c  mov     edi, 8007000Eh
0x180013861  jmp     loc_180013706
0x180013866  mov     ecx, edi
0x180013868  jmp     short loc_1800137FD
0x18001386a  mov     eax, [rsi]
0x18001386c  mov     r9d, r15d
0x18001386f  mov     ecx, [rsi+4]
0x180013872  mov     r8d, r15d
0x180013875  mov     [rbp+var_20], eax
0x180013878  add     ecx, r13d
0x18001387b  mov     eax, [rsi+8]
0x18001387e  mov     [rbp+var_1C], ecx
0x180013881  mov     rcx, [r14+48h]
0x180013885  mov     [rbp+var_18], eax
0x180013888  mov     [rbp+var_14], 1
0x18001388f  mov     [rsp+80h+var_60], rdx
0x180013894  lea     rdx, [rbp+var_20]
0x180013898  mov     rax, [rcx]
0x18001389b  mov     rax, [rax+38h]
0x18001389f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138a4  mov     edi, eax
0x1800138a6  test    eax, eax
0x1800138a8  jns     short loc_1800138BF
0x1800138aa  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800138b1  jnz     loc_1800137FB
0x1800138b7  test    eax, eax
0x1800138b9  js      loc_180013716
0x1800138bf  mov     ecx, [rbp+var_18]
0x1800138c2  mov     r9d, r15d
0x1800138c5  mov     r8, [rbp+Block]
0x1800138c9  mov     edx, r12d
0x1800138cc  mov     rax, [r14+40h]
0x1800138d0  mov     dword ptr [rsp+80h+var_60], ecx
0x1800138d4  mov     rcx, [rbp+var_40]
0x1800138d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138dd  mov     edi, eax
0x1800138df  test    eax, eax
0x1800138e1  jns     short loc_1800138F8
0x1800138e3  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800138ea  jnz     loc_1800137FB
0x1800138f0  test    eax, eax
0x1800138f2  js      loc_180013716
0x1800138f8  mov     rax, [rbp+var_38]
0x1800138fc  inc     r13d
0x1800138ff  add     [rbp+var_40], rax
0x180013903  cmp     r13d, [rsi+0Ch]
0x180013907  jge     loc_180013716
0x18001390d  mov     rdx, [rbp+Block]
0x180013911  jmp     loc_18001386A
0x180013916  mov     edi, 80070057h
0x18001391b  jmp     loc_180013709
0x180013920  mov     eax, [r14+10h]
0x180013924  mov     ecx, 7FFFFFFFh
0x180013929  cmp     eax, ecx
0x18001392b  ja      loc_180013793
0x180013931  mov     dword ptr [rbp+var_30+8], eax
0x180013934  mov     eax, [r14+14h]
0x180013938  cmp     eax, ecx
0x18001393a  ja      loc_180013793
0x180013940  mov     dword ptr [rbp+var_30+0Ch], eax
0x180013943  lea     rsi, [rbp+var_30]
0x180013947  jmp     loc_18001375E
0x18001394c  xor     edi, edi
0x18001394e  xor     r13d, r13d
0x180013951  cmp     [rsi+0Ch], edi
0x180013954  jle     loc_180013716
0x18001395a  jmp     loc_18001386A
```
