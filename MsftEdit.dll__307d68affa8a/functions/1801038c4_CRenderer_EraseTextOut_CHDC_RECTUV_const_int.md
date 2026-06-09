# CRenderer::EraseTextOut(CHDC &,RECTUV const *,int)

- ea: `0x1801038c4`
- end: `0x180103df7`
- name: `?EraseTextOut@CRenderer@@AEAAXAEAVCHDC@@PEBURECTUV@@H@Z`
- size: `1331`
- prototype: `void __fastcall(CRenderer *__hidden this, struct CHDC *, const struct RECTUV *, int)`
- caller_count: `14`
- callee_count: `7`
- tags: ``

## callers

- `0x18005900c`
- `0x18005a840`
- `0x18005cd1c`
- `0x18006d710`
- `0x18006f710`
- `0x18008c684`
- `0x1800b0240`
- `0x1800fdfa8`
- `0x180120a90`
- `0x1801252dc`
- `0x18014ceec`
- `0x18014d4a0`
- `0x18014da44`
- `0x18014ddc4`

## callees

- `0x18006e4d4`
- `0x18008c668`
- `0x1801038c4`
- `0x180103e00`
- `0x18013bad0`
- `0x18014d124`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103d07`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103d13`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103db5`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103d07`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103d13`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180103db5`
- `ext-ms-win-gdi-draw-l1-1-1!Polyline` at `0x180103d87`
- `ext-ms-win-gdi-draw-l1-1-1!Polyline` at `0x180103d87`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103cc7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103da9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103cc7`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180103da9`

## pseudocode

```c
void __fastcall CRenderer::EraseTextOut(CRenderer *this, struct CHDC *a2, const struct RECTUV *a3, int a4)
{
  bool v4; // zf
  struct CHDC *v6; // r12
  CDisplay *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rsi
  _DWORD *v13; // rcx
  int v14; // r15d
  int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // edi
  signed int v20; // ecx
  int v21; // r8d
  int v22; // r10d
  LONG v23; // r13d
  int v24; // eax
  unsigned int v25; // eax
  int v26; // r8d
  int v27; // edx
  LONG v28; // r8d
  int v29; // edx
  int v30; // r11d
  unsigned int v31; // r12d
  LONG v32; // r15d
  int v33; // edx
  int v34; // r9d
  unsigned int i; // ebx
  __int64 *v36; // rcx
  __int64 v37; // rax
  unsigned int v38; // eax
  unsigned int *v39; // r8
  __int64 *v40; // rcx
  int v41; // r15d
  LONG right; // eax
  int v43; // r13d
  LONG left; // r15d
  void *v45; // r14
  int v46; // esi
  int v47; // ecx
  LONG v48; // edi
  int v49; // eax
  int v50; // r12d
  unsigned int ShadedColor; // eax
  void *v52; // rax
  HDC v53; // r12
  int top; // eax
  HGDIOBJ v55; // rbx
  int v56; // [rsp+70h] [rbp-29h]
  LONG v57; // [rsp+70h] [rbp-29h]
  unsigned int v58; // [rsp+74h] [rbp-25h]
  unsigned int v59; // [rsp+74h] [rbp-25h]
  unsigned int v60; // [rsp+74h] [rbp-25h]
  unsigned int v61; // [rsp+78h] [rbp-21h] BYREF
  POINT apt; // [rsp+80h] [rbp-19h] BYREF
  LONG v63; // [rsp+88h] [rbp-11h]
  LONG bottom; // [rsp+8Ch] [rbp-Dh]
  HGDIOBJ h; // [rsp+90h] [rbp-9h]
  HDC hdc; // [rsp+98h] [rbp-1h]
  struct tagRECT v67; // [rsp+A0h] [rbp+7h] BYREF

  v4 = (*((_DWORD *)this + 125) & 0x4000) == 0;
  v6 = a2;
  apt = (POINT)a2;
  if ( !v4 )
    return;
  v8 = (CDisplay *)*((_QWORD *)this + 19);
  v67 = 0;
  CDisplay::RectFromRectuv(v8, &v67, a3, 1, 0);
  if ( a4 || (unsigned int)CRenderer::IsSimpleBackground(this) )
    goto LABEL_44;
  v9 = *((_QWORD *)this + 2);
  v10 = v9 ? *(_QWORD *)(v9 + 40) : 0LL;
  if ( (*(_DWORD *)(v10 + 184) & 0x40000000) != 0 )
    goto LABEL_44;
  v11 = v9 ? *(_QWORD *)(v9 + 40) : 0LL;
  v12 = *(_QWORD *)(v11 + 256);
  if ( !v12 )
    goto LABEL_44;
  v13 = (_DWORD *)*((_QWORD *)this + 19);
  v14 = v13[34];
  v15 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v13 + 376LL))(v13);
  v16 = CMeasurerNoFC::GetTflow(this) - 1;
  if ( v16 )
  {
    v17 = v16 - 1;
    if ( v17 )
    {
      v18 = v17 - 1;
      if ( v18 )
      {
        if ( v18 != 2 )
        {
          v19 = v14;
          goto LABEL_23;
        }
        v19 = v15;
        goto LABEL_22;
      }
      v19 = v15;
      v15 = v14;
    }
    else
    {
      v19 = -v14;
    }
    v15 = -v15;
    goto LABEL_23;
  }
  v19 = -v15;
LABEL_22:
  v15 = v14;
LABEL_23:
  if ( (unsigned int)(*(char *)(v12 + 139) - 1) > 2 )
  {
    v40 = *(__int64 **)v6;
    v41 = *(__int16 *)(v12 + 140);
    v61 = *(_DWORD *)(v12 + 128);
    v59 = *(_DWORD *)(v12 + 132);
    hdc = (HDC)(*(__int64 (__fastcall **)(__int64 *))(*v40 + 48))(v40);
    if ( !hdc )
      goto LABEL_44;
    right = v67.right;
    v43 = v41;
    left = v67.left;
    v45 = 0;
    h = 0;
    v57 = v67.right;
    if ( v43 == -135 || v43 == -45 )
    {
      v46 = v67.bottom - v67.top;
      if ( v43 != -45 )
      {
        v15 += v67.top + v19;
        right = v46 + v67.right;
        goto LABEL_55;
      }
      left = v67.left - v46;
      v15 = v19 - v15 - v67.top;
      v46 = v67.top - v67.bottom;
    }
    else
    {
      v46 = 0;
      if ( !v43 )
      {
        left = v67.top;
        right = v67.bottom;
LABEL_55:
        v57 = right;
        goto LABEL_56;
      }
      v15 = v19;
    }
LABEL_56:
    v47 = v59;
    v48 = left;
    if ( !v59 )
      v47 = 6579300;
    v60 = v47;
    if ( left < right )
    {
      do
      {
        v49 = (v48 + v15) % 600 + 600;
        if ( (v48 + v15) % 600 >= 0 )
          v49 = (v48 + v15) % 600;
        v50 = 600 - v49;
        if ( v49 <= 300 )
          v50 = v49;
        if ( v50 <= 30 )
        {
          v50 = 30;
        }
        else if ( v50 >= 270 )
        {
          v50 = 270;
        }
        if ( v45 )
          DeleteObject(v45);
        ShadedColor = GetShadedColor(v60, v61, v50);
        v52 = (void *)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))pfnCreatePen)(0, 0, ShadedColor);
        v53 = hdc;
        v45 = v52;
        if ( v52 )
        {
          if ( h )
            SelectObject(hdc, v52);
          else
            h = SelectObject(hdc, v52);
        }
        if ( v43 )
        {
          if ( v48 <= v67.right )
          {
            top = v67.top;
            apt.x = v48;
          }
          else
          {
            apt.x = v67.right;
            top = v67.top + v48 - v67.right;
          }
          apt.y = top;
          if ( v48 - v46 >= left )
          {
            v63 = v48 - v46;
            bottom = v67.bottom;
          }
          else
          {
            v63 = left - 1;
            bottom = v67.bottom + 1 + v48 - left - v46;
          }
        }
        else
        {
          apt.x = v67.left;
          v63 = v67.right;
          apt.y = v48;
          bottom = v48;
        }
        Polyline(v53, &apt, 2);
        ++v48;
      }
      while ( v48 < v57 );
      if ( v45 )
      {
        v55 = h;
        if ( h )
        {
          DeleteObject(v45);
          SelectObject(v53, v55);
        }
      }
    }
    return;
  }
  if ( *((__int16 *)this + 248) <= 0
    || (v20 = *((__int16 *)this + 249), *((__int16 *)this + 249) <= 0)
    || !*(_QWORD *)(v12 + 88) )
  {
LABEL_43:
    *(_BYTE *)(v12 + 139) = 0;
LABEL_44:
    v36 = *(__int64 **)v6;
    v37 = **(_QWORD **)v6;
    if ( *((char *)this + 500) >= 0 )
    {
      v39 = 0;
    }
    else
    {
      v38 = (*(__int64 (**)(void))(v37 + 360))();
      v36 = *(__int64 **)v6;
      v39 = &v61;
      v61 = v38;
      v37 = *v36;
    }
    (*(void (__fastcall **)(__int64 *, struct tagRECT *, unsigned int *))(v37 + 256))(v36, &v67, v39);
    return;
  }
  v21 = *(__int16 *)(v12 + 170);
  v22 = *((__int16 *)this + 248);
  v23 = v67.top;
  LODWORD(hdc) = v22;
  v24 = *(__int16 *)(v12 + 164);
  v61 = v20;
  v25 = (int)((unsigned __int64)(1374389535LL * v24 * *(__int16 *)(v12 + 168)) >> 32) >> 5;
  v26 = *(__int16 *)(v12 + 166) * v21;
  LODWORD(h) = (v25 >> 31) + v25;
  v27 = (unsigned __int64)(1374389535LL * v26) >> 32;
  v28 = v67.right;
  v58 = ((unsigned int)v27 >> 31) + (v27 >> 5);
  v29 = (v15 + v67.top) % v20;
  v30 = v29 + v20;
  if ( v29 >= 0 )
    v30 = (v15 + v67.top) % v20;
  v31 = v20 - v30;
LABEL_30:
  v56 = v30;
  if ( v23 < v67.bottom )
  {
    if ( (int)(v31 + v23) > v67.bottom )
      v31 = v67.bottom - v23;
    v32 = v67.left;
    v33 = (v19 + v67.left) % v22;
    v34 = v33 + v22;
    if ( v33 >= 0 )
      v34 = (v19 + v67.left) % v22;
    for ( i = v22 - v34; ; i = (unsigned int)hdc )
    {
      if ( v32 >= v28 )
      {
        v23 += v31;
        v31 = v61;
        v30 = 0;
        goto LABEL_30;
      }
      if ( (int)(v32 + i) > v28 )
        i = v28 - v32;
      if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD, unsigned int, int, int, int, _DWORD, unsigned int, _QWORD, __int64, __int64))(***(_QWORD ***)&apt + 240LL))(
              **(_QWORD **)&apt,
              (unsigned int)v32,
              (unsigned int)v23,
              i,
              v31,
              v34,
              v30,
              13369376,
              (_DWORD)h,
              v58,
              *(_QWORD *)(v12 + 88),
              v12 + 96,
              v12 + 104) )
        break;
      v22 = (int)hdc;
      v32 += i;
      v28 = v67.right;
      v34 = 0;
      v30 = v56;
    }
    v6 = (struct CHDC *)apt;
    goto LABEL_43;
  }
}

```

## disassembly

```asm
0x1801038c4  mov     [rsp-8+arg_18], rbx
0x1801038c9  push    rbp
0x1801038ca  push    rsi
0x1801038cb  push    rdi
0x1801038cc  push    r12
0x1801038ce  push    r13
0x1801038d0  push    r14
0x1801038d2  push    r15
0x1801038d4  lea     rbp, [rsp-27h]
0x1801038d9  sub     rsp, 0C0h
0x1801038e0  mov     rax, cs:__security_cookie
0x1801038e7  xor     rax, rsp
0x1801038ea  mov     [rbp+57h+var_40], rax
0x1801038ee  test    dword ptr [rcx+1F4h], 4000h
0x1801038f8  mov     ebx, r9d
0x1801038fb  mov     r12, rdx
0x1801038fe  mov     qword ptr [rbp+57h+apt.x], rdx
0x180103902  mov     r14, rcx
0x180103905  jnz     loc_180103DD0
0x18010390b  mov     rcx, [rcx+98h]; this
0x180103912  lea     rdx, [rbp+57h+var_50]; struct tagRECT *
0x180103916  xorps   xmm0, xmm0
0x180103919  xor     r13d, r13d
0x18010391c  mov     r9b, 1; bool
0x18010391f  mov     [rsp+0F0h+var_D0], r13b; bool
0x180103924  movups  xmmword ptr [rbp+57h+var_50.left], xmm0
0x180103928  call    ?RectFromRectuv@CDisplay@@QEBAXAEAUtagRECT@@AEBURECTUV@@_N2@Z; CDisplay::RectFromRectuv(tagRECT &,RECTUV const &,bool,bool)
0x18010392d  test    ebx, ebx
0x18010392f  jnz     loc_180103B8D
0x180103935  mov     rcx, r14; this
0x180103938  call    ?IsSimpleBackground@CRenderer@@QEBAHXZ; CRenderer::IsSimpleBackground(void)
0x18010393d  test    eax, eax
0x18010393f  jnz     loc_180103B8D
0x180103945  mov     rdx, [r14+10h]
0x180103949  test    rdx, rdx
0x18010394c  jz      short loc_180103954
0x18010394e  mov     rax, [rdx+28h]
0x180103952  jmp     short loc_180103957
0x180103954  mov     rax, r13
0x180103957  mov     eax, [rax+0B8h]
0x18010395d  shr     eax, 1Eh
0x180103960  test    al, 1
0x180103962  jnz     loc_180103B8D
0x180103968  test    rdx, rdx
0x18010396b  jz      short loc_180103973
0x18010396d  mov     rsi, [rdx+28h]
0x180103971  jmp     short loc_180103976
0x180103973  mov     rsi, r13
0x180103976  mov     rsi, [rsi+100h]
0x18010397d  test    rsi, rsi
0x180103980  jz      loc_180103B8D
0x180103986  mov     rcx, [r14+98h]
0x18010398d  mov     rax, [rcx]
0x180103990  mov     r15d, [rcx+88h]
0x180103997  mov     rax, [rax+178h]
0x18010399e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801039a3  mov     rcx, r14; this
0x1801039a6  mov     ebx, eax
0x1801039a8  call    ?GetTflow@CMeasurerNoFC@@QEBAEXZ; CMeasurerNoFC::GetTflow(void)
0x1801039ad  movzx   eax, al
0x1801039b0  sub     eax, 1
0x1801039b3  jz      short loc_1801039DD
0x1801039b5  sub     eax, 1
0x1801039b8  jz      short loc_1801039D4
0x1801039ba  sub     eax, 1
0x1801039bd  jz      short loc_1801039CD
0x1801039bf  cmp     eax, 2
0x1801039c2  jz      short loc_1801039C9
0x1801039c4  mov     edi, r15d
0x1801039c7  jmp     short loc_1801039E4
0x1801039c9  mov     edi, ebx
0x1801039cb  jmp     short loc_1801039E1
0x1801039cd  mov     edi, ebx
0x1801039cf  mov     ebx, r15d
0x1801039d2  jmp     short loc_1801039D9
0x1801039d4  mov     edi, r15d
0x1801039d7  neg     edi
0x1801039d9  neg     ebx
0x1801039db  jmp     short loc_1801039E4
0x1801039dd  mov     edi, ebx
0x1801039df  neg     edi
0x1801039e1  mov     ebx, r15d
0x1801039e4  movsx   eax, byte ptr [rsi+8Bh]
0x1801039eb  dec     eax
0x1801039ed  cmp     eax, 2
0x1801039f0  ja      loc_180103BC1
0x1801039f6  movsx   eax, word ptr [r14+1F0h]
0x1801039fe  test    ax, ax
0x180103a01  jle     loc_180103B86
0x180103a07  movsx   ecx, word ptr [r14+1F2h]
0x180103a0f  test    cx, cx
0x180103a12  jle     loc_180103B86
0x180103a18  cmp     [rsi+58h], r13
0x180103a1c  jz      loc_180103B86
0x180103a22  movsx   r8d, word ptr [rsi+0AAh]
0x180103a2a  mov     r10d, eax
0x180103a2d  mov     r13d, [rbp+57h+var_50.top]
0x180103a31  mov     r9d, ecx
0x180103a34  mov     dword ptr [rbp+57h+hdc], eax
0x180103a37  mov     r11d, 51EB851Fh
0x180103a3d  movsx   eax, word ptr [rsi+0A4h]
0x180103a44  mov     r12d, r9d
0x180103a47  mov     [rbp+57h+var_78], ecx
0x180103a4a  movsx   ecx, word ptr [rsi+0A8h]
0x180103a51  imul    ecx, eax
0x180103a54  mov     eax, r11d
0x180103a57  imul    ecx
0x180103a59  mov     eax, edx
0x180103a5b  sar     eax, 5
0x180103a5e  mov     ecx, eax
0x180103a60  shr     ecx, 1Fh
0x180103a63  add     eax, ecx
0x180103a65  movsx   ecx, word ptr [rsi+0A6h]
0x180103a6c  imul    r8d, ecx
0x180103a70  mov     dword ptr [rbp+57h+h], eax
0x180103a73  mov     eax, r11d
0x180103a76  imul    r8d
0x180103a79  mov     r8d, [rbp+57h+var_50.right]
0x180103a7d  mov     ecx, edx
0x180103a7f  sar     ecx, 5
0x180103a82  mov     eax, ecx
0x180103a84  shr     eax, 1Fh
0x180103a87  add     ecx, eax
0x180103a89  lea     eax, [rbx+r13]
0x180103a8d  cdq
0x180103a8e  mov     [rbp+57h+var_7C], ecx
0x180103a91  idiv    r9d
0x180103a94  test    edx, edx
0x180103a96  lea     r11d, [rdx+r9]
0x180103a9a  cmovns  r11d, edx
0x180103a9e  sub     r12d, r11d
0x180103aa1  mov     ecx, [rbp+57h+var_50.bottom]
0x180103aa4  mov     [rbp+57h+var_80], r11d
0x180103aa8  cmp     r13d, ecx
0x180103aab  jge     loc_180103DD0
0x180103ab1  lea     eax, [r12+r13]
0x180103ab5  cmp     eax, ecx
0x180103ab7  jle     short loc_180103ABF
0x180103ab9  mov     r12d, ecx
0x180103abc  sub     r12d, r13d
0x180103abf  mov     r15d, [rbp+57h+var_50.left]
0x180103ac3  mov     ebx, r10d
0x180103ac6  lea     eax, [rdi+r15]
0x180103aca  cdq
0x180103acb  idiv    r10d
0x180103ace  test    edx, edx
0x180103ad0  lea     r9d, [rdx+r10]
0x180103ad4  cmovns  r9d, edx
0x180103ad8  sub     ebx, r9d
0x180103adb  cmp     r15d, r8d
0x180103ade  jge     loc_180103B70
0x180103ae4  lea     eax, [r15+rbx]
0x180103ae8  cmp     eax, r8d
0x180103aeb  jle     short loc_180103AF3
0x180103aed  mov     ebx, r8d
0x180103af0  sub     ebx, r15d
0x180103af3  mov     rax, qword ptr [rbp+57h+apt.x]
0x180103af7  lea     r8, [rsi+60h]
0x180103afb  lea     rdx, [rsi+68h]
0x180103aff  mov     [rsp+0F0h+var_90], rdx
0x180103b04  mov     rdx, [rsi+58h]
0x180103b08  mov     rcx, [rax]
0x180103b0b  mov     [rsp+0F0h+var_98], r8
0x180103b10  mov     r8d, r13d
0x180103b13  mov     [rsp+0F0h+var_A0], rdx
0x180103b18  mov     edx, [rbp+57h+var_7C]
0x180103b1b  mov     rax, [rcx]
0x180103b1e  mov     [rsp+0F0h+var_A8], edx
0x180103b22  mov     edx, dword ptr [rbp+57h+h]
0x180103b25  mov     [rsp+0F0h+var_B0], edx
0x180103b29  mov     edx, r15d
0x180103b2c  mov     rax, [rax+0F0h]
0x180103b33  mov     [rsp+0F0h+var_B8], 0CC0020h
0x180103b3b  mov     [rsp+0F0h+var_C0], r11d
0x180103b40  mov     [rsp+0F0h+var_C8], r9d
0x180103b45  mov     r9d, ebx
0x180103b48  mov     dword ptr [rsp+0F0h+var_D0], r12d
0x180103b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103b52  test    al, al
0x180103b54  jz      short loc_180103B7F
0x180103b56  mov     r10d, dword ptr [rbp+57h+hdc]
0x180103b5a  add     r15d, ebx
0x180103b5d  mov     r8d, [rbp+57h+var_50.right]
0x180103b61  xor     r9d, r9d
0x180103b64  mov     r11d, [rbp+57h+var_80]
0x180103b68  mov     ebx, r10d
0x180103b6b  jmp     loc_180103ADB
0x180103b70  add     r13d, r12d
0x180103b73  mov     r12d, [rbp+57h+var_78]
0x180103b77  xor     r11d, r11d
0x180103b7a  jmp     loc_180103AA1
0x180103b7f  mov     r12, qword ptr [rbp+57h+apt.x]
0x180103b83  xor     r13d, r13d
0x180103b86  mov     [rsi+8Bh], r13b
0x180103b8d  test    byte ptr [r14+1F4h], 80h
0x180103b95  mov     rcx, [r12]
0x180103b99  mov     rax, [rcx]
0x180103b9c  jz      loc_180103DBD
0x180103ba2  mov     rax, [rax+168h]
0x180103ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103bae  mov     rcx, [r12]
0x180103bb2  lea     r8, [rbp+57h+var_78]
0x180103bb6  mov     [rbp+57h+var_78], eax
0x180103bb9  mov     rax, [rcx]
0x180103bbc  jmp     loc_180103DC0
0x180103bc1  mov     eax, [rsi+80h]
0x180103bc7  mov     rcx, [r12]
0x180103bcb  movsx   r15d, word ptr [rsi+8Ch]
0x180103bd3  mov     [rbp+57h+var_78], eax
0x180103bd6  mov     eax, [rsi+84h]
0x180103bdc  mov     [rbp+57h+var_7C], eax
0x180103bdf  mov     rax, [rcx]
0x180103be2  mov     rax, [rax+30h]
0x180103be6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103beb  mov     [rbp+57h+hdc], rax
0x180103bef  test    rax, rax
0x180103bf2  jz      short loc_180103B8D
0x180103bf4  mov     eax, [rbp+57h+var_50.right]
0x180103bf7  mov     r13d, r15d
0x180103bfa  mov     r15d, [rbp+57h+var_50.left]
0x180103bfe  xor     r14d, r14d
0x180103c01  mov     [rbp+57h+h], r14
0x180103c05  mov     [rbp+57h+var_80], eax
0x180103c08  cmp     r13d, 0FFFFFF79h
0x180103c0f  jz      short loc_180103C2B
0x180103c11  cmp     r13d, 0FFFFFFD3h
0x180103c15  jz      short loc_180103C2B
0x180103c17  xor     esi, esi
0x180103c19  test    r13d, r13d
0x180103c1c  jnz     short loc_180103C27
0x180103c1e  mov     r15d, [rbp+57h+var_50.top]
0x180103c22  mov     eax, [rbp+57h+var_50.bottom]
0x180103c25  jmp     short loc_180103C4C
0x180103c27  mov     ebx, edi
0x180103c29  jmp     short loc_180103C4F
0x180103c2b  mov     esi, [rbp+57h+var_50.bottom]
0x180103c2e  mov     ecx, [rbp+57h+var_50.top]
0x180103c31  sub     esi, ecx
0x180103c33  cmp     r13d, 0FFFFFFD3h
0x180103c37  jnz     short loc_180103C46
0x180103c39  sub     edi, ebx
0x180103c3b  sub     r15d, esi
0x180103c3e  mov     ebx, edi
0x180103c40  sub     ebx, ecx
0x180103c42  neg     esi
0x180103c44  jmp     short loc_180103C4F
0x180103c46  add     ebx, edi
0x180103c48  add     ebx, ecx
0x180103c4a  add     eax, esi
0x180103c4c  mov     [rbp+57h+var_80], eax
0x180103c4f  mov     ecx, [rbp+57h+var_7C]
0x180103c52  mov     edx, 646464h
0x180103c57  test    ecx, ecx
0x180103c59  mov     edi, r15d
0x180103c5c  cmovz   ecx, edx
0x180103c5f  mov     [rbp+57h+var_7C], ecx
0x180103c62  cmp     r15d, eax
0x180103c65  jge     loc_180103DD0
0x180103c6b  lea     ecx, [rdi+rbx]
0x180103c6e  mov     eax, 1B4E81B5h
0x180103c73  imul    ecx
0x180103c75  mov     r12d, 258h
0x180103c7b  sar     edx, 6
0x180103c7e  mov     eax, edx
0x180103c80  shr     eax, 1Fh
0x180103c83  add     edx, eax
0x180103c85  imul    eax, edx, 258h
0x180103c8b  sub     ecx, eax
0x180103c8d  lea     eax, [rcx+258h]
0x180103c93  cmovns  eax, ecx
0x180103c96  sub     r12d, eax
0x180103c99  cmp     eax, 12Ch
0x180103c9e  cmovle  r12d, eax
0x180103ca2  cmp     r12d, 1Eh
0x180103ca6  jle     short loc_180103CB9
0x180103ca8  cmp     r12d, 10Eh
0x180103caf  jl      short loc_180103CBF
0x180103cb1  mov     r12d, 10Eh
0x180103cb7  jmp     short loc_180103CBF
0x180103cb9  mov     r12d, 1Eh
0x180103cbf  test    r14, r14
0x180103cc2  jz      short loc_180103CCD
0x180103cc4  mov     rcx, r14; ho
0x180103cc7  call    cs:__imp_DeleteObject
0x180103ccd  mov     edx, [rbp+57h+var_78]; unsigned int
0x180103cd0  mov     r8d, r12d; int
0x180103cd3  mov     ecx, [rbp+57h+var_7C]; unsigned int
0x180103cd6  call    ?GetShadedColor@@YAKKKJ@Z; GetShadedColor(ulong,ulong,long)
0x180103cdb  mov     r8d, eax
0x180103cde  xor     edx, edx
0x180103ce0  mov     rax, cs:?pfnCreatePen@@3P6A_JXZEA; __int64 (*pfnCreatePen)(void)
0x180103ce7  xor     ecx, ecx
0x180103ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103cee  mov     r12, [rbp+57h+hdc]
0x180103cf2  mov     r14, rax
0x180103cf5  test    rax, rax
0x180103cf8  jz      short loc_180103D19
0x180103cfa  cmp     [rbp+57h+h], 0
0x180103cff  mov     rdx, rax; h
0x180103d02  mov     rcx, r12; hdc
  ... truncated ...
```
