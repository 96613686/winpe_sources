# CXgcPath::SetupVisual(xpsrdr::RenderState &)

- ea: `0x180019680`
- end: `0x180019a37`
- name: `?SetupVisual@CXgcPath@@UEAAXAEAURenderState@xpsrdr@@@Z`
- size: `951`
- prototype: `void __fastcall(CXgcPath *__hidden this, struct xpsrdr::RenderState *)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000e15c`
- `0x18000e4c4`
- `0x18000e990`
- `0x180011b0c`
- `0x1800123bc`
- `0x180018a70`
- `0x180018df4`
- `0x180019680`
- `0x18004a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CXgcPath::SetupVisual(CXgcPath *this, struct xpsrdr::RenderState *a2)
{
  float v3; // xmm1_4
  int v4; // r9d
  _QWORD *v5; // r13
  _QWORD *v6; // r15
  int v7; // r9d
  int v8; // r10d
  _QWORD *v9; // r11
  __int64 v10; // rcx
  int v11; // eax
  int *v12; // rbx
  char v13; // al
  int v14; // edx
  char v15; // al
  bool v16; // zf
  int *v17; // r14
  int v18; // edx
  __int64 v19; // rcx
  int v20; // r8d
  char v21; // al
  int v22; // eax
  int v23; // edx
  int v24; // ecx
  char v25; // al
  __int64 v26; // r10
  int v27; // eax
  int v28; // r9d
  char v29; // al
  int v30; // eax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, _QWORD *); // rcx
  __int64 (__fastcall **v32)(_QWORD, GUID *, _QWORD *); // rax
  __int64 v33; // r9
  int v34; // ebx
  __int128 v35; // [rsp+30h] [rbp-40h] BYREF
  _QWORD v36[4]; // [rsp+40h] [rbp-30h] BYREF
  int v37; // [rsp+B0h] [rbp+40h] BYREF
  struct xpsrdr::RenderState *v38; // [rsp+B8h] [rbp+48h]
  unsigned int v39; // [rsp+C0h] [rbp+50h] BYREF

  v38 = a2;
  v3 = *((float *)this + 2);
  v4 = 0;
  if ( v3 <= 0.0
    || !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 216)
    || (v5 = (_QWORD *)((char *)this + 168),
        v6 = (_QWORD *)((char *)this + 184),
        !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168))
    && !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 184) )
  {
    *((_DWORD *)this + 3) = v4;
    return;
  }
  if ( !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168)
    || !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 184) )
  {
    v17 = (int *)((char *)this + 12);
    v12 = (int *)((char *)this + 20);
    if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168) )
      v19 = *v5;
    else
      v19 = *v6;
    v18 = *(_DWORD *)(v19 + 24);
    *v17 = v18;
    v20 = *v12 ^ (*v12 ^ *(unsigned __int8 *)(v19 + 20)) & 1;
    *v12 = v20;
    *((_BYTE *)this + 33) = *(_DWORD *)(v19 + 28) == 2;
    if ( *(_DWORD *)(v19 + 28) == v7 || (v21 = 1, (v20 & 1) != 0) )
      v21 = v7;
    *((_BYTE *)this + 32) = v21;
    goto LABEL_44;
  }
  v10 = *v5;
  if ( *(_DWORD *)(*v5 + 24LL) != v7 )
  {
    if ( *(_DWORD *)(v10 + 24) == 1 )
      goto LABEL_13;
    goto LABEL_11;
  }
  if ( *(_DWORD *)(*v6 + 24LL) != v7 )
  {
LABEL_11:
    if ( *(_DWORD *)(*v6 + 24LL) != 1 )
    {
      *((_DWORD *)this + 3) = 2;
      goto LABEL_14;
    }
LABEL_13:
    *((_DWORD *)this + 3) = 1;
    goto LABEL_14;
  }
  *((_DWORD *)this + 3) = v7;
LABEL_14:
  if ( *(_BYTE *)(v10 + 20) != (_BYTE)v7 || (v11 = v7, *(_BYTE *)(*v6 + 20LL) != (_BYTE)v7) )
    v11 = 1;
  v12 = (int *)((char *)this + 20);
  *((_DWORD *)this + 5) &= ~1u;
  *((_DWORD *)this + 5) |= v11;
  if ( *(_DWORD *)(v10 + 28) == 2 || (v13 = v7, *(_DWORD *)(*v6 + 28LL) == 2) )
    v13 = 1;
  *((_BYTE *)this + 33) = v13;
  if ( (*(_BYTE *)v12 & 1) != 0 )
    goto LABEL_36;
  v14 = *(_DWORD *)(v10 + 28);
  if ( v14 && *(_DWORD *)(*v6 + 28LL) != v7 )
  {
    if ( v3 >= 1.0 && (*(_DWORD *)(v10 + 24) != 1 || *(_DWORD *)(*v6 + 24LL) != 1) )
    {
      v15 = 1;
LABEL_35:
      *((_BYTE *)this + 32) = v15;
      goto LABEL_36;
    }
LABEL_34:
    v15 = v7;
    goto LABEL_35;
  }
  if ( *(_DWORD *)(*v6 + 28LL) != v7 )
  {
    if ( v3 < 1.0 )
      goto LABEL_34;
    v16 = *(_DWORD *)(v10 + 24) == 1;
    goto LABEL_33;
  }
  if ( v14 )
  {
    if ( v3 < 1.0 )
      goto LABEL_34;
    v16 = *(_DWORD *)(*v6 + 24LL) == 1;
LABEL_33:
    v15 = 1;
    if ( !v16 )
      goto LABEL_35;
    goto LABEL_34;
  }
LABEL_36:
  v17 = (int *)((char *)this + 12);
  v18 = *((_DWORD *)this + 3);
LABEL_44:
  if ( v3 >= 1.0 )
  {
    v22 = v18;
  }
  else
  {
    v22 = 1;
    if ( v18 < 1 )
      v22 = v18;
    *v17 = v22;
  }
  v23 = *v12;
  if ( (*v12 & 2) != 0 )
  {
    v24 = 1;
    if ( v22 < 1 )
      v24 = v22;
    *v17 = v24;
    *v12 = v23 | 1;
    *((_BYTE *)this + 32) = v7;
  }
  else
  {
    v24 = v22;
  }
  if ( v24 )
  {
    CXgcGeometry::GetBounds(*v9, v8, (_DWORD)this + 104, (_DWORD)this + 200, (struct D2D_RECT_F *)((char *)this + 56));
    if ( (*(_BYTE *)v12 & 1) != 0 || (v25 = std::operator!=<ID3D11Device>((char *)this + 168), v7 = 0, !v25) )
    {
      CXgcPath::IsAlignedRectAndSetInnerBounds(this, v38);
      v7 = 0;
    }
  }
  if ( *v17 != v7 )
  {
    if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168) )
    {
      v35 = 0;
      if ( (unsigned __int8)IsSolidBrush(v26, *v5, &v35) )
      {
        if ( 1.0 != *(float *)&v35 || 1.0 != *((float *)&v35 + 1) || (v27 = 1, 1.0 != *((float *)&v35 + 2)) )
          v27 = 0;
        *((_DWORD *)this + 4) = v27;
      }
      else
      {
        *((_DWORD *)this + 58) = 2;
      }
    }
    if ( (unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 184) )
    {
      v35 = 0;
      v29 = IsSolidBrush(v38, *v6, &v35);
      v28 = 0;
      if ( v29 )
      {
        if ( *((_DWORD *)this + 4) == 1 || !(unsigned __int8)std::operator!=<ID3D11Device>((char *)this + 168) )
        {
          if ( 1.0 != *(float *)&v35 || 1.0 != *((float *)&v35 + 1) || (v30 = 1, 1.0 != *((float *)&v35 + 2)) )
            v30 = v28;
          *((_DWORD *)this + 4) = v30;
        }
      }
      else
      {
        *((_DWORD *)this + 58) = 2;
      }
    }
    if ( *v17 != v28 )
    {
      v37 = v28;
      std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(&v35);
      v31 = *(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))(*((_QWORD *)this + 27) + 16LL);
      v32 = *v31;
      v36[0] = v33;
      v36[1] = &v37;
      v36[2] = &v35;
      v34 = (*v32)(v31, &GUID_2cd906a5_12e2_11dc_9fed_001143a055f9, v36);
      detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(v36);
      if ( v34 >= 0 )
      {
        v39 = 0;
        if ( v37 >= 0
          && (*(int (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v35 + 152LL))(v35, &v39) >= 0
          && v39 > 0x31 )
        {
          *((_DWORD *)this + 58) = 2;
        }
      }
      std::_Ptr_base<ID2D1RenderTarget>::_Decref(&v35);
    }
  }
}

```

## disassembly

```asm
0x180019680  mov     [rsp-38h+arg_8], rdx
0x180019685  push    rbp
0x180019686  push    rbx
0x180019687  push    rsi
0x180019688  push    rdi
0x180019689  push    r13
0x18001968b  push    r14
0x18001968d  push    r15
0x18001968f  mov     rbp, rsp
0x180019692  sub     rsp, 70h
0x180019696  movaps  [rsp+70h+var_10], xmm6
0x18001969b  mov     r10, rdx
0x18001969e  mov     rdi, rcx
0x1800196a1  movss   xmm1, dword ptr [rcx+8]
0x1800196a6  xorps   xmm0, xmm0
0x1800196a9  xor     r9d, r9d
0x1800196ac  comiss  xmm0, xmm1
0x1800196af  jnb     loc_180019A1F
0x1800196b5  lea     r11, [rcx+0D8h]
0x1800196bc  mov     rcx, r11
0x1800196bf  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800196c4  test    al, al
0x1800196c6  jz      loc_180019A1F
0x1800196cc  lea     r13, [rdi+0A8h]
0x1800196d3  lea     r15, [rdi+0B8h]
0x1800196da  mov     rcx, r13
0x1800196dd  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800196e2  test    al, al
0x1800196e4  jnz     short loc_1800196F6
0x1800196e6  mov     rcx, r15
0x1800196e9  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800196ee  test    al, al
0x1800196f0  jz      loc_180019A1F
0x1800196f6  mov     rcx, r13
0x1800196f9  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800196fe  movss   xmm6, cs:__real@3f800000
0x180019706  test    al, al
0x180019708  jz      loc_1800197E6
0x18001970e  mov     rcx, r15
0x180019711  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180019716  test    al, al
0x180019718  jz      loc_1800197E6
0x18001971e  mov     rcx, [r13+0]
0x180019722  mov     esi, 1
0x180019727  cmp     [rcx+18h], r9d
0x18001972b  jnz     short loc_18001973C
0x18001972d  mov     rax, [r15]
0x180019730  cmp     [rax+18h], r9d
0x180019734  jnz     short loc_180019741
0x180019736  mov     [rdi+0Ch], r9d
0x18001973a  jmp     short loc_180019755
0x18001973c  cmp     [rcx+18h], esi
0x18001973f  jz      short loc_180019752
0x180019741  mov     rax, [r15]
0x180019744  cmp     [rax+18h], esi
0x180019747  jz      short loc_180019752
0x180019749  mov     dword ptr [rdi+0Ch], 2
0x180019750  jmp     short loc_180019755
0x180019752  mov     [rdi+0Ch], esi
0x180019755  cmp     [rcx+14h], r9b
0x180019759  jnz     short loc_180019767
0x18001975b  mov     rax, [r15]
0x18001975e  cmp     [rax+14h], r9b
0x180019762  mov     eax, r9d
0x180019765  jz      short loc_180019769
0x180019767  mov     eax, esi
0x180019769  lea     rbx, [rdi+14h]
0x18001976d  and     dword ptr [rbx], 0FFFFFFFEh
0x180019770  or      [rbx], eax
0x180019772  cmp     dword ptr [rcx+1Ch], 2
0x180019776  jz      short loc_180019784
0x180019778  mov     rax, [r15]
0x18001977b  cmp     dword ptr [rax+1Ch], 2
0x18001977f  mov     al, r9b
0x180019782  jnz     short loc_180019787
0x180019784  mov     al, sil
0x180019787  mov     [rdi+21h], al
0x18001978a  test    [rbx], sil
0x18001978d  jnz     short loc_1800197DD
0x18001978f  mov     edx, [rcx+1Ch]
0x180019792  test    edx, edx
0x180019794  jz      short loc_1800197B3
0x180019796  mov     rax, [r15]
0x180019799  cmp     [rax+1Ch], r9d
0x18001979d  jz      short loc_1800197B3
0x18001979f  comiss  xmm1, xmm6
0x1800197a2  jb      short loc_1800197D7
0x1800197a4  cmp     [rcx+18h], esi
0x1800197a7  jnz     short loc_1800197AE
0x1800197a9  cmp     [rax+18h], esi
0x1800197ac  jz      short loc_1800197D7
0x1800197ae  mov     al, sil
0x1800197b1  jmp     short loc_1800197DA
0x1800197b3  mov     rax, [r15]
0x1800197b6  cmp     [rax+1Ch], r9d
0x1800197ba  jz      short loc_1800197C6
0x1800197bc  comiss  xmm1, xmm6
0x1800197bf  jb      short loc_1800197D7
0x1800197c1  cmp     [rcx+18h], esi
0x1800197c4  jmp     short loc_1800197D2
0x1800197c6  test    edx, edx
0x1800197c8  jz      short loc_1800197DD
0x1800197ca  comiss  xmm1, xmm6
0x1800197cd  jb      short loc_1800197D7
0x1800197cf  cmp     [rax+18h], esi
0x1800197d2  mov     al, sil
0x1800197d5  jnz     short loc_1800197DA
0x1800197d7  mov     al, r9b
0x1800197da  mov     [rdi+20h], al
0x1800197dd  lea     r14, [rdi+0Ch]
0x1800197e1  mov     edx, [r14]
0x1800197e4  jmp     short loc_18001983D
0x1800197e6  lea     r14, [rdi+0Ch]
0x1800197ea  lea     rbx, [rdi+14h]
0x1800197ee  mov     rcx, r13
0x1800197f1  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800197f6  mov     esi, 1
0x1800197fb  test    al, al
0x1800197fd  jz      short loc_180019805
0x1800197ff  mov     rcx, [r13+0]
0x180019803  jmp     short loc_180019808
0x180019805  mov     rcx, [r15]
0x180019808  mov     edx, [rcx+18h]
0x18001980b  mov     [r14], edx
0x18001980e  movzx   r8d, byte ptr [rcx+14h]
0x180019813  xor     r8d, [rbx]
0x180019816  and     r8d, esi
0x180019819  xor     r8d, [rbx]
0x18001981c  mov     [rbx], r8d
0x18001981f  cmp     dword ptr [rcx+1Ch], 2
0x180019823  setz    al
0x180019826  mov     [rdi+21h], al
0x180019829  cmp     [rcx+1Ch], r9d
0x18001982d  jz      short loc_180019837
0x18001982f  mov     al, sil
0x180019832  test    sil, r8b
0x180019835  jz      short loc_18001983A
0x180019837  mov     al, r9b
0x18001983a  mov     [rdi+20h], al
0x18001983d  comiss  xmm6, xmm1
0x180019840  jbe     short loc_18001984E
0x180019842  mov     eax, esi
0x180019844  cmp     edx, esi
0x180019846  cmovl   eax, edx
0x180019849  mov     [r14], eax
0x18001984c  jmp     short loc_180019850
0x18001984e  mov     eax, edx
0x180019850  mov     edx, [rbx]
0x180019852  test    dl, 2
0x180019855  jz      short loc_18001986B
0x180019857  mov     ecx, esi
0x180019859  cmp     eax, esi
0x18001985b  cmovl   ecx, eax
0x18001985e  mov     [r14], ecx
0x180019861  or      edx, esi
0x180019863  mov     [rbx], edx
0x180019865  mov     [rdi+20h], r9b
0x180019869  jmp     short loc_18001986D
0x18001986b  mov     ecx, eax
0x18001986d  test    ecx, ecx
0x18001986f  jz      short loc_1800198B7
0x180019871  lea     rax, [rdi+38h]
0x180019875  lea     r9, [rdi+0C8h]; int
0x18001987c  lea     r8, [rdi+68h]; int
0x180019880  mov     [rsp+70h+var_50], rax; struct D2D_RECT_F *
0x180019885  mov     rdx, r10; int
0x180019888  mov     rcx, [r11]; int
0x18001988b  call    ?GetBounds@CXgcGeometry@@QEAAXAEAURenderState@xpsrdr@@AEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@VCXgcPenStyle@@@std@@AEAUD2D_RECT_F@@@Z; CXgcGeometry::GetBounds(xpsrdr::RenderState &,D2D_MATRIX_3X2_F const &,std::shared_ptr<CXgcPenStyle> const &,D2D_RECT_F &)
0x180019890  test    [rbx], sil
0x180019893  jnz     short loc_1800198A4
0x180019895  mov     rcx, r13
0x180019898  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18001989d  xor     r9d, r9d
0x1800198a0  test    al, al
0x1800198a2  jnz     short loc_1800198B3
0x1800198a4  mov     rdx, [rbp+arg_8]; struct xpsrdr::RenderState *
0x1800198a8  mov     rcx, rdi; this
0x1800198ab  call    ?IsAlignedRectAndSetInnerBounds@CXgcPath@@QEAAXAEAURenderState@xpsrdr@@@Z; CXgcPath::IsAlignedRectAndSetInnerBounds(xpsrdr::RenderState &)
0x1800198b0  xor     r9d, r9d
0x1800198b3  mov     r10, [rbp+arg_8]
0x1800198b7  cmp     [r14], r9d
0x1800198ba  jz      loc_180019A23
0x1800198c0  mov     rcx, r13
0x1800198c3  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x1800198c8  test    al, al
0x1800198ca  jz      short loc_180019916
0x1800198cc  xorps   xmm0, xmm0
0x1800198cf  movups  [rbp+var_40], xmm0
0x1800198d3  lea     r8, [rbp+var_40]
0x1800198d7  mov     rdx, [r13+0]
0x1800198db  mov     rcx, r10
0x1800198de  call    ?IsSolidBrush@@YA_NAEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@std@@PEAU_D3DCOLORVALUE@@@Z; IsSolidBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,_D3DCOLORVALUE *)
0x1800198e3  xor     r9d, r9d
0x1800198e6  test    al, al
0x1800198e8  jz      short loc_18001990C
0x1800198ea  ucomiss xmm6, dword ptr [rbp+var_40]
0x1800198ee  jp      short loc_180019904
0x1800198f0  jnz     short loc_180019904
0x1800198f2  ucomiss xmm6, dword ptr [rbp+var_40+4]
0x1800198f6  jp      short loc_180019904
0x1800198f8  jnz     short loc_180019904
0x1800198fa  ucomiss xmm6, dword ptr [rbp+var_40+8]
0x1800198fe  jp      short loc_180019904
0x180019900  mov     eax, esi
0x180019902  jz      short loc_180019907
0x180019904  mov     eax, r9d
0x180019907  mov     [rdi+10h], eax
0x18001990a  jmp     short loc_180019916
0x18001990c  mov     dword ptr [rdi+0E8h], 2
0x180019916  mov     rcx, r15
0x180019919  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18001991e  test    al, al
0x180019920  jz      short loc_18001997D
0x180019922  xorps   xmm0, xmm0
0x180019925  movups  [rbp+var_40], xmm0
0x180019929  lea     r8, [rbp+var_40]
0x18001992d  mov     rdx, [r15]
0x180019930  mov     rcx, [rbp+arg_8]
0x180019934  call    ?IsSolidBrush@@YA_NAEAURenderState@xpsrdr@@AEBV?$shared_ptr@UIXpsOMBrush@@@std@@PEAU_D3DCOLORVALUE@@@Z; IsSolidBrush(xpsrdr::RenderState &,std::shared_ptr<IXpsOMBrush> const &,_D3DCOLORVALUE *)
0x180019939  xor     r9d, r9d
0x18001993c  test    al, al
0x18001993e  jz      short loc_180019973
0x180019940  cmp     [rdi+10h], esi
0x180019943  jz      short loc_180019951
0x180019945  mov     rcx, r13
0x180019948  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x18001994d  test    al, al
0x18001994f  jnz     short loc_18001997D
0x180019951  ucomiss xmm6, dword ptr [rbp+var_40]
0x180019955  jp      short loc_18001996B
0x180019957  jnz     short loc_18001996B
0x180019959  ucomiss xmm6, dword ptr [rbp+var_40+4]
0x18001995d  jp      short loc_18001996B
0x18001995f  jnz     short loc_18001996B
0x180019961  ucomiss xmm6, dword ptr [rbp+var_40+8]
0x180019965  jp      short loc_18001996B
0x180019967  mov     eax, esi
0x180019969  jz      short loc_18001996E
0x18001996b  mov     eax, r9d
0x18001996e  mov     [rdi+10h], eax
0x180019971  jmp     short loc_18001997D
0x180019973  mov     dword ptr [rdi+0E8h], 2
0x18001997d  cmp     [r14], r9d
0x180019980  jz      loc_180019A23
0x180019986  mov     [rbp+arg_0], r9d
0x18001998a  lea     rcx, [rbp+var_40]
0x18001998e  call    ??0?$shared_ptr@UID2D1Factory1@@@std@@QEAA@XZ; std::shared_ptr<ID2D1Factory1>::shared_ptr<ID2D1Factory1>(void)
0x180019993  nop
0x180019994  mov     rax, [rdi+0D8h]
0x18001999b  mov     rcx, [rax+10h]
0x18001999f  mov     rax, [rcx]
0x1800199a2  mov     [rbp+var_30], r9
0x1800199a6  lea     rdx, [rbp+arg_0]
0x1800199aa  mov     [rbp+var_28], rdx
0x1800199ae  lea     rdx, [rbp+var_40]
0x1800199b2  mov     [rbp+var_20], rdx
0x1800199b6  lea     r8, [rbp+var_30]
0x1800199ba  lea     rdx, _GUID_2cd906a5_12e2_11dc_9fed_001143a055f9
0x1800199c1  mov     rax, [rax]
0x1800199c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199c9  mov     ebx, eax
0x1800199cb  lea     rcx, [rbp+var_30]
0x1800199cf  call    ??1?$ComReset@UIXpsOMVisualBrush@@@detail@@QEAA@XZ; detail::ComReset<IXpsOMVisualBrush>::~ComReset<IXpsOMVisualBrush>(void)
0x1800199d4  shr     ebx, 1Fh
0x1800199d7  xor     bl, sil
0x1800199da  jz      short loc_180019A14
0x1800199dc  mov     [rbp+arg_10], 0
0x1800199e3  cmp     [rbp+arg_0], 0
0x1800199e7  jl      short loc_180019A14
0x1800199e9  mov     rcx, qword ptr [rbp+var_40]
0x1800199ed  mov     rax, [rcx]
0x1800199f0  lea     rdx, [rbp+arg_10]
0x1800199f4  mov     rax, [rax+98h]
0x1800199fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a00  test    eax, eax
0x180019a02  js      short loc_180019A14
0x180019a04  cmp     [rbp+arg_10], 31h ; '1'
0x180019a08  jbe     short loc_180019A14
0x180019a0a  mov     dword ptr [rdi+0E8h], 2
0x180019a14  lea     rcx, [rbp+var_40]
0x180019a18  call    ?_Decref@?$_Ptr_base@UID2D1RenderTarget@@@std@@IEAAXXZ; std::_Ptr_base<ID2D1RenderTarget>::_Decref(void)
0x180019a1d  jmp     short loc_180019A23
0x180019a1f  mov     [rdi+0Ch], r9d
0x180019a23  movaps  xmm6, [rsp+70h+var_10]
0x180019a28  add     rsp, 70h
0x180019a2c  pop     r15
0x180019a2e  pop     r14
0x180019a30  pop     r13
0x180019a32  pop     rdi
0x180019a33  pop     rsi
0x180019a34  pop     rbx
0x180019a35  pop     rbp
0x180019a36  retn
```
