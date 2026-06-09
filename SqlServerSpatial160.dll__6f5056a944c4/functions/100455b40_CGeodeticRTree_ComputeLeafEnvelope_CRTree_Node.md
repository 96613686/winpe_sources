# CGeodeticRTree::ComputeLeafEnvelope(CRTree::Node &)

- ea: `0x100455b40`
- end: `0x100455d3e`
- name: `?ComputeLeafEnvelope@CGeodeticRTree@@MEBAJAEAUNode@CRTree@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(CGeodeticRTree *__hidden this, struct Node *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x100408b40`
- `0x100408db0`
- `0x100455b40`
- `0x100466f20`
- `0x100467140`
- `0x1004673f0`
- `0x100467ca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CGeodeticRTree::ComputeLeafEnvelope(CGeodeticRTree *this, struct Node *a2)
{
  int v4; // ebx
  int v5; // r14d
  __int64 v6; // r8
  __int64 v7; // r10
  __int64 v8; // r9
  const struct CPoint3D *v9; // rsi
  int v10; // edi
  int v11; // eax
  const struct CPoint3D *v12; // rsi
  int v13; // ecx
  int v14; // edi
  __int64 v16; // [rsp+20h] [rbp-88h]
  _BYTE v17[16]; // [rsp+30h] [rbp-78h] BYREF
  __int128 v18; // [rsp+40h] [rbp-68h]
  __int128 v19; // [rsp+50h] [rbp-58h]
  _BYTE v20[4]; // [rsp+60h] [rbp-48h] BYREF
  int v21; // [rsp+64h] [rbp-44h]
  int v22; // [rsp+70h] [rbp-38h]
  int v23; // [rsp+74h] [rbp-34h]
  __int64 v24; // [rsp+78h] [rbp-30h]

  v16 = -2;
  CCap::CCap((CCap *)v17, *((double *)this + 25));
  if ( v24 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v24 + 24LL))(v24, 0, 0);
    if ( v4 < 0 )
      goto LABEL_24;
  }
  v5 = 0;
  if ( !HIDWORD(a2->lpVtbl) )
  {
LABEL_22:
    v4 = CCap::EndGeometry((CCap *)v17, 1);
    if ( v4 >= 0 )
    {
      *(_OWORD *)&a2[1].lpVtbl = v18;
      *(_OWORD *)&a2[3].lpVtbl = v19;
    }
    goto LABEL_24;
  }
  while ( 1 )
  {
    v6 = *((_QWORD *)this + 20);
    v7 = *(unsigned int *)(*(_QWORD *)(*((_QWORD *)this + 9)
                                     + 8LL * ((unsigned int)(v5 + LODWORD(a2->lpVtbl)) / *((_DWORD *)this + 21)))
                         + 4LL * ((unsigned int)(v5 + LODWORD(a2->lpVtbl)) % *((_DWORD *)this + 21)));
    v8 = *(_QWORD *)(v6 + 16);
    v9 = (const struct CPoint3D *)(*(_QWORD *)(v6 + 40) + 24LL * *(unsigned int *)(v8 + 8 * v7));
    v10 = *(_DWORD *)(v8 + 8 * v7 + 4);
    if ( v10 == 1 )
    {
      v11 = CCap::AddLines3D((CCap *)v17, v9, 1u, 0);
      goto LABEL_20;
    }
    v4 = ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::Add(v20, v9);
    if ( v4 < 0 )
      goto LABEL_24;
    if ( v24 )
    {
      _mm_lfence();
      v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct CPoint3D *, _QWORD, __int64))(*(_QWORD *)v24 + 88LL))(
             v24,
             0,
             v9,
             0,
             v16);
      if ( v4 < 0 )
        goto LABEL_24;
    }
    _mm_lfence();
    v12 = (const struct CPoint3D *)((char *)v9 + 24);
    if ( v10 != 2 )
      break;
    v4 = CCap::AddLines3D((CCap *)v17, v12, 1u, 0);
    if ( v4 < 0 )
      goto LABEL_24;
LABEL_18:
    if ( v24 )
    {
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 56LL))(v24, 0);
LABEL_20:
      v4 = v11;
      if ( v11 < 0 )
        goto LABEL_24;
    }
    if ( (unsigned int)++v5 >= HIDWORD(a2->lpVtbl) )
      goto LABEL_22;
  }
  v13 = 0;
  if ( v21 )
    v13 = v21 - 1;
  if ( v22 + v13 * v23 )
  {
    v14 = 0;
    while ( 1 )
    {
      v4 = CCap::AddOneArc((CCap *)v17, (const struct CPoint3D *)((char *)v12 + 24 * (unsigned int)(2 * v14)));
      if ( v4 < 0 )
        break;
      if ( ++v14 )
        goto LABEL_18;
    }
  }
  else
  {
    v4 = -2147418113;
  }
LABEL_24:
  CCap::~CCap((CCap *)v17);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x100455b40  mov     rax, rsp
0x100455b43  push    rdi
0x100455b44  push    r14
0x100455b46  push    r15
0x100455b48  sub     rsp, 90h
0x100455b4f  mov     [rsp+0A8h+var_88], 0FFFFFFFFFFFFFFFEh
0x100455b58  mov     [rax+8], rbx
0x100455b5c  mov     [rax+10h], rbp
0x100455b60  mov     [rax+18h], rsi
0x100455b64  mov     r15, rdx
0x100455b67  mov     rbp, rcx
0x100455b6a  movsd   xmm1, qword ptr [rcx+0C8h]; double
0x100455b72  lea     rcx, [rax-78h]; this
0x100455b76  call    ??0CCap@@QEAA@N@Z; CCap::CCap(double)
0x100455b7b  nop
0x100455b7c  mov     rcx, [rsp+0A8h+var_30]
0x100455b81  test    rcx, rcx
0x100455b84  jz      short loc_100455B9B
0x100455b86  mov     rax, [rcx]
0x100455b89  xor     r8d, r8d
0x100455b8c  xor     edx, edx
0x100455b8e  call    qword ptr [rax+18h]
0x100455b91  mov     ebx, eax
0x100455b93  test    eax, eax
0x100455b95  js      loc_100455D0D
0x100455b9b  xor     r14d, r14d
0x100455b9e  cmp     [r15+4], r14d
0x100455ba2  jbe     loc_100455CE7
0x100455ba8  nop     dword ptr [rax+rax+00000000h]
0x100455bb0  mov     eax, [r15]
0x100455bb3  add     eax, r14d
0x100455bb6  xor     edx, edx
0x100455bb8  div     dword ptr [rbp+54h]
0x100455bbb  mov     ecx, eax
0x100455bbd  mov     rax, [rbp+48h]
0x100455bc1  mov     rcx, [rax+rcx*8]
0x100455bc5  mov     r8, [rbp+0A0h]
0x100455bcc  mov     r10d, [rcx+rdx*4]
0x100455bd0  mov     r9, [r8+10h]
0x100455bd4  mov     eax, [r9+r10*8]
0x100455bd8  lea     rcx, [rax+rax*2]
0x100455bdc  mov     rax, [r8+28h]
0x100455be0  lea     rsi, [rax+rcx*8]
0x100455be4  mov     edi, [r9+r10*8+4]
0x100455be9  mov     rdx, rsi; struct CPoint3D *
0x100455bec  cmp     edi, 1
0x100455bef  jnz     short loc_100455C06
0x100455bf1  xor     r9d, r9d; unsigned __int64 *
0x100455bf4  mov     r8d, edi; unsigned int
0x100455bf7  lea     rcx, [rsp+0A8h+var_78]; this
0x100455bfc  call    ?AddLines3D@CCap@@UEAAJPEBVCPoint3D@@IPEB_K@Z; CCap::AddLines3D(CPoint3D const *,uint,unsigned __int64 const *)
0x100455c01  jmp     loc_100455CD4
0x100455c06  lea     rcx, [rsp+0A8h+var_48]
0x100455c0b  call    ?Add@?$ArrayOverPages@VCPoint3D@@V?$Default_Allocator@VCPoint3D@@@@@@QEAAJAEBVCPoint3D@@@Z; ArrayOverPages<CPoint3D,Default_Allocator<CPoint3D>>::Add(CPoint3D const &)
0x100455c10  mov     ebx, eax
0x100455c12  test    eax, eax
0x100455c14  js      loc_100455D0D
0x100455c1a  cmp     [rsp+0A8h+var_30], 0
0x100455c20  jz      short loc_100455C42
0x100455c22  lfence
0x100455c25  mov     rcx, [rsp+0A8h+var_30]
0x100455c2a  mov     rax, [rcx]
0x100455c2d  xor     r9d, r9d
0x100455c30  mov     r8, rsi
0x100455c33  xor     edx, edx
0x100455c35  call    qword ptr [rax+58h]
0x100455c38  mov     ebx, eax
0x100455c3a  test    eax, eax
0x100455c3c  js      loc_100455D0D
0x100455c42  lfence
0x100455c45  add     rsi, 18h
0x100455c49  cmp     edi, 2
0x100455c4c  jnz     short loc_100455C6E
0x100455c4e  xor     r9d, r9d; unsigned __int64 *
0x100455c51  lea     r8d, [rdi-1]; unsigned int
0x100455c55  mov     rdx, rsi; struct CPoint3D *
0x100455c58  lea     rcx, [rsp+0A8h+var_78]; this
0x100455c5d  call    ?AddLines3D@CCap@@UEAAJPEBVCPoint3D@@IPEB_K@Z; CCap::AddLines3D(CPoint3D const *,uint,unsigned __int64 const *)
0x100455c62  mov     ebx, eax
0x100455c64  test    eax, eax
0x100455c66  js      loc_100455D0D
0x100455c6c  jmp     short loc_100455CC2
0x100455c6e  xor     ecx, ecx
0x100455c70  mov     eax, [rsp+0A8h+var_44]
0x100455c74  test    eax, eax
0x100455c76  jz      short loc_100455C7B
0x100455c78  lea     ecx, [rax-1]
0x100455c7b  mov     eax, [rsp+0A8h+var_34]
0x100455c7f  imul    eax, ecx
0x100455c82  add     eax, [rsp+0A8h+var_38]
0x100455c86  cmp     eax, 1
0x100455c89  jb      loc_100455D36
0x100455c8f  xor     edi, edi
0x100455c91  nop     dword ptr [rax+00h]
0x100455c95  nop     word ptr [rax+rax+00000000h]
0x100455ca0  lea     eax, [rdi+rdi]
0x100455ca3  lea     rax, [rax+rax*2]
0x100455ca7  lea     rdx, [rsi+rax*8]; struct CPoint3D *
0x100455cab  lea     rcx, [rsp+0A8h+var_78]; this
0x100455cb0  call    ?AddOneArc@CCap@@AEAAJPEBVCPoint3D@@@Z; CCap::AddOneArc(CPoint3D const *)
0x100455cb5  mov     ebx, eax
0x100455cb7  test    eax, eax
0x100455cb9  js      short loc_100455D0D
0x100455cbb  inc     edi
0x100455cbd  cmp     edi, 1
0x100455cc0  jb      short loc_100455CA0
0x100455cc2  mov     rcx, [rsp+0A8h+var_30]
0x100455cc7  test    rcx, rcx
0x100455cca  jz      short loc_100455CDA
0x100455ccc  mov     rax, [rcx]
0x100455ccf  xor     edx, edx
0x100455cd1  call    qword ptr [rax+38h]
0x100455cd4  test    eax, eax
0x100455cd6  mov     ebx, eax
0x100455cd8  js      short loc_100455D0D
0x100455cda  inc     r14d
0x100455cdd  cmp     r14d, [r15+4]
0x100455ce1  jb      loc_100455BB0
0x100455ce7  mov     dl, 1; bool
0x100455ce9  lea     rcx, [rsp+0A8h+var_78]; this
0x100455cee  call    ?EndGeometry@CCap@@UEAAJ_N@Z; CCap::EndGeometry(bool)
0x100455cf3  mov     ebx, eax
0x100455cf5  test    eax, eax
0x100455cf7  js      short loc_100455D0D
0x100455cf9  movaps  xmm0, [rsp+0A8h+var_68]
0x100455cfe  movups  xmmword ptr [r15+8], xmm0
0x100455d03  movaps  xmm0, [rsp+0A8h+var_58]
0x100455d08  movups  xmmword ptr [r15+18h], xmm0
0x100455d0d  lea     rcx, [rsp+0A8h+var_78]; this
0x100455d12  call    ??1CCap@@UEAA@XZ; CCap::~CCap(void)
0x100455d17  mov     eax, ebx
0x100455d19  lea     r11, [rsp+0A8h+var_18]
0x100455d21  mov     rbx, [r11+20h]
0x100455d25  mov     rbp, [r11+28h]
0x100455d29  mov     rsi, [r11+30h]
0x100455d2d  mov     rsp, r11
0x100455d30  pop     r15
0x100455d32  pop     r14
0x100455d34  pop     rdi
0x100455d35  retn
0x100455d36  mov     ebx, 8000FFFFh
0x100455d3b  jmp     short loc_100455D0D
```
