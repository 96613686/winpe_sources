# CMagellan::TrackUpdateMagellanMButtonDown(CTxtEdit &,tagPOINT)

- ea: `0x1801399cc`
- end: `0x180139de8`
- name: `?TrackUpdateMagellanMButtonDown@CMagellan@@QEAAXAEAVCTxtEdit@@UtagPOINT@@@Z`
- size: `1052`
- prototype: `void __fastcall(CMagellan *__hidden this, struct CTxtEdit *, struct tagPOINT)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, installer_update`

## callers

- `0x1800e0270`

## callees

- `0x18002610c`
- `0x1800277e4`
- `0x1800278ec`
- `0x18006e770`
- `0x18006fd9c`
- `0x18007a49c`
- `0x18012ac54`
- `0x1801399cc`
- `0x180139df0`
- `0x180160d74`
- `0x180161188`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x180139bcd`
- `ext-ms-win-ntuser-draw-l1-1-1!LoadBitmapW` at `0x180139bcd`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180139ba4`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180139ba4`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180139da7`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x180139da7`

## pseudocode

```c
void __fastcall CMagellan::TrackUpdateMagellanMButtonDown(CMagellan *this, struct CTxtEdit *a2, struct tagPOINT a3)
{
  int *v3; // rdi
  unsigned __int16 v6; // si
  int v7; // r12d
  int v8; // edx
  unsigned __int16 v9; // r15
  int IsUScrollEnabled; // eax
  int v11; // ebx
  int v12; // r12d
  __int16 v13; // ax
  char v14; // al
  __int64 v15; // rax
  __int64 v16; // rsi
  const WCHAR *v17; // rdx
  HINSTANCE v18; // rcx
  void ***v19; // r15
  int v20; // edx
  int v21; // esi
  int v22; // ebx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // r11d
  int v26; // r14d
  __int64 v27; // r9
  __int64 v28; // r8
  void ***v29; // rcx
  bool v30; // zf
  void ***v31; // rcx
  void (__fastcall *v32)(void ***, HCURSOR, _QWORD); // rbx
  HCURSOR CursorW; // rax
  int v34; // [rsp+30h] [rbp-39h]
  int v35; // [rsp+30h] [rbp-39h]
  int v36; // [rsp+34h] [rbp-35h]
  __int64 v37; // [rsp+38h] [rbp-31h] BYREF
  __int64 v38; // [rsp+40h] [rbp-29h]
  __int128 v39; // [rsp+48h] [rbp-21h] BYREF
  _OWORD v40[6]; // [rsp+58h] [rbp-11h] BYREF
  unsigned __int16 v41; // [rsp+D8h] [rbp+6Fh]
  struct tagPOINT v42; // [rsp+E0h] [rbp+77h] BYREF
  int v43; // [rsp+E8h] [rbp+7Fh]

  v42 = a3;
  v3 = (int *)*((_QWORD *)a2 + 17);
  v37 = 0;
  if ( v3 )
  {
    v43 = 0;
    v6 = 0;
    CDisplay::PointuvFromPoint((CDisplay *)v3, (struct Ptls6::tagLSPOINTUV *)&v37, &v42);
    v34 = *((_DWORD *)this + 4);
    v7 = CW32System::MulDivFunc(60, v3[14], 1440);
    if ( (v3[29] & 0x400) != 0 )
    {
      v8 = *((_DWORD *)this + 5);
      v9 = 1;
      if ( SHIDWORD(v37) < v8 - v7 || SHIDWORD(v37) > v8 + v7 )
      {
        v43 = 1;
        if ( SHIDWORD(v37) >= v8 )
          v6 = 2;
        else
          v6 = 1;
      }
    }
    else
    {
      v9 = 0;
    }
    IsUScrollEnabled = CDisplay::IsUScrollEnabled((CDisplay *)v3);
    v11 = v37;
    if ( IsUScrollEnabled
      && (CTxtEdit::TxGetScrollBars(a2) & 0x100000) != 0
      && ((v9 |= 2u, v11 < v34 - v7) || v11 > v7 + v34) )
    {
      v12 = 1;
      v13 = 6;
      if ( v11 >= *((_DWORD *)this + 4) )
        v13 = 3;
      v6 += v13;
    }
    else
    {
      v12 = 0;
    }
    v14 = (*(__int64 (__fastcall **)(int *))(*(_QWORD *)v3 + 176LL))(v3);
    switch ( v14 )
    {
      case 1:
        v6 = *((unsigned __int8 *)&qword_1802BF310[2] + v6);
        break;
      case 2:
        v6 = *((unsigned __int8 *)qword_1802BF310 + v6);
        break;
      case 3:
        v6 = *((unsigned __int8 *)&qword_1802BF310[4] + v6);
        break;
    }
    if ( ((*(__int64 (__fastcall **)(int *, struct HINSTANCE__ *))(*(_QWORD *)v3 + 176LL))(v3, &_ImageBase) & 1) != 0 )
    {
      if ( v9 == 2 )
      {
        v9 = 1;
      }
      else if ( v9 == 1 )
      {
        v9 = 2;
      }
    }
    v15 = v6;
    v16 = v9;
    v41 = word_1802BF340[v15];
    if ( word_1802BF360[v9] != *((_WORD *)this + 1) )
    {
      if ( *((_QWORD *)this + 1) )
      {
        CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 0, 0);
        DeleteObject(*((HGDIOBJ *)this + 1));
        *((_QWORD *)this + 1) = 0;
      }
      v17 = (const WCHAR *)(unsigned __int16)word_1802BF360[v9];
      v18 = hinstRE;
      *((_WORD *)this + 1) = (_WORD)v17;
      *((_QWORD *)this + 1) = LoadBitmapW(v18, v17);
      CMagellan::InvertMagellanDownBMP((HGDIOBJ *)this, (struct CDisplay *)v3, 1, 0);
    }
    v19 = &CITextHost2Ref::s_dummyHost;
    if ( v43 || v12 )
    {
      v39 = 0;
      CTxtEdit::TxGetClientRect(a2, (struct RECTUV *)&v39, 0);
      v20 = HIDWORD(v37) - *((_DWORD *)this + 5);
      v21 = HIDWORD(v39) - DWORD1(v39);
      v22 = v11 - *((_DWORD *)this + 4);
      v35 = (DWORD2(v39) - (int)v39) >> 1;
      LODWORD(v38) = v39 + v22 + v35;
      v36 = v20;
      v23 = CW32System::MulDivFunc(250 * v20, v20, 4 * (HIDWORD(v39) - DWORD1(v39)));
      v26 = v43;
      v27 = v23;
      if ( !v23 )
        v27 = 1;
      if ( v43 )
        CDisplay::SmoothVScroll((CDisplay *)v3, v25 - HIDWORD(v37), 0, v27, 10 * v21, 0);
      if ( v12 )
      {
        v28 = (unsigned int)(v35 - 2);
        HIDWORD(v38) = DWORD1(v39) + (v21 >> 1);
        if ( (unsigned int)v28 > 0xFFFF )
          SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v24, 0, v28, v27);
        CDisplay::AutoScroll(v3, v38, v28, 0);
      }
      if ( (*((_BYTE *)a2 + 272) & 8) != 0 && (v12 || v26) )
      {
        memset(v40, 0, 44);
        if ( v12 )
        {
          DWORD2(v40[1]) = 276;
          v29 = &CITextHost2Ref::s_dummyHost;
          v30 = *((_QWORD *)a2 + 14) == 0;
          *(_QWORD *)((char *)&v40[1] + 12) = v22 > 0;
          if ( !v30 )
            v29 = (void ***)*((_QWORD *)a2 + 14);
          ((void (__fastcall *)(void ***, __int64, _OWORD *, __int64))(*v29)[38])(v29, 1792, v40, v27);
        }
        if ( v26 )
        {
          DWORD2(v40[1]) = 277;
          v31 = &CITextHost2Ref::s_dummyHost;
          v30 = *((_QWORD *)a2 + 14) == 0;
          *(_QWORD *)((char *)&v40[1] + 12) = v36 > 0;
          if ( !v30 )
            v31 = (void ***)*((_QWORD *)a2 + 14);
          ((void (__fastcall *)(void ***, __int64, _OWORD *, __int64))(*v31)[38])(v31, 1792, v40, v27);
        }
      }
    }
    else
    {
      v41 = word_1802BF358[v16];
      CDisplay::FinishSmoothVScroll((CDisplay *)v3);
    }
    if ( *((_QWORD *)a2 + 14) )
      v19 = (void ***)*((_QWORD *)a2 + 14);
    v32 = (void (__fastcall *)(void ***, HCURSOR, _QWORD))(*v19)[19];
    if ( v41 )
      CursorW = LoadCursorW(hinstRE, (LPCWSTR)v41);
    else
      CursorW = CTxtEdit::_hcurArrow;
    v32(v19, CursorW, 0);
  }
}

```

## disassembly

```asm
0x1801399cc  mov     [rsp-8+arg_0], rbx
0x1801399d1  mov     qword ptr [rsp-8+arg_10.x], r8
0x1801399d6  push    rbp
0x1801399d7  push    rsi
0x1801399d8  push    rdi
0x1801399d9  push    r12
0x1801399db  push    r13
0x1801399dd  push    r14
0x1801399df  push    r15
0x1801399e1  lea     rbp, [rsp-27h]
0x1801399e6  sub     rsp, 90h
0x1801399ed  mov     rdi, [rdx+88h]
0x1801399f4  xor     ebx, ebx
0x1801399f6  mov     [rbp+57h+var_88], rbx
0x1801399fa  mov     r13, rdx
0x1801399fd  mov     r14, rcx
0x180139a00  test    rdi, rdi
0x180139a03  jz      loc_180139DCD
0x180139a09  lea     r8, [rbp+57h+arg_10]; struct tagPOINT *
0x180139a0d  mov     [rbp+57h+arg_8], ebx
0x180139a10  lea     rdx, [rbp+57h+var_88]; struct Ptls6::tagLSPOINTUV *
0x180139a14  mov     [rbp+57h+arg_18], ebx
0x180139a17  mov     rcx, rdi; this
0x180139a1a  mov     esi, ebx
0x180139a1c  call    ?PointuvFromPoint@CDisplay@@QEBAXAEAUtagLSPOINTUV@Ptls6@@AEBUtagPOINT@@@Z; CDisplay::PointuvFromPoint(Ptls6::tagLSPOINTUV &,tagPOINT const &)
0x180139a21  mov     eax, [r14+10h]
0x180139a25  lea     ecx, [rbx+3Ch]; int
0x180139a28  mov     edx, [rdi+38h]; int
0x180139a2b  mov     r8d, 5A0h; int
0x180139a31  mov     [rbp+57h+var_90], eax
0x180139a34  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180139a39  test    dword ptr [rdi+74h], 400h
0x180139a40  lea     r9d, [rbx+1]
0x180139a44  mov     r8d, dword ptr [rbp+57h+var_88+4]
0x180139a48  mov     r12d, eax
0x180139a4b  lea     eax, [rbx+2]
0x180139a4e  jz      short loc_180139A82
0x180139a50  mov     edx, [r14+14h]
0x180139a54  movzx   r15d, r9w
0x180139a58  mov     ecx, edx
0x180139a5a  sub     ecx, r12d
0x180139a5d  cmp     r8d, ecx
0x180139a60  jl      short loc_180139A6E
0x180139a62  lea     eax, [rdx+r12]
0x180139a66  cmp     r8d, eax
0x180139a69  jle     short loc_180139A85
0x180139a6b  lea     eax, [rbx+2]
0x180139a6e  mov     [rbp+57h+arg_18], r9d
0x180139a72  cmp     r8d, edx
0x180139a75  jge     short loc_180139A7D
0x180139a77  movzx   esi, r9w
0x180139a7b  jmp     short loc_180139A85
0x180139a7d  movzx   esi, ax
0x180139a80  jmp     short loc_180139A85
0x180139a82  mov     r15d, ebx
0x180139a85  mov     rcx, rdi; this
0x180139a88  call    ?IsUScrollEnabled@CDisplay@@QEAAHXZ; CDisplay::IsUScrollEnabled(void)
0x180139a8d  mov     rbx, [rbp+57h+var_88]
0x180139a91  test    eax, eax
0x180139a93  jz      short loc_180139AD7
0x180139a95  mov     rcx, r13; this
0x180139a98  call    ?TxGetScrollBars@CTxtEdit@@QEBAKXZ; CTxtEdit::TxGetScrollBars(void)
0x180139a9d  bt      eax, 14h
0x180139aa1  jnb     short loc_180139AD7
0x180139aa3  mov     ecx, [rbp+57h+var_90]
0x180139aa6  or      r15w, 2
0x180139aab  mov     eax, ecx
0x180139aad  sub     eax, r12d
0x180139ab0  cmp     ebx, eax
0x180139ab2  jl      short loc_180139ABC
0x180139ab4  lea     eax, [r12+rcx]
0x180139ab8  cmp     ebx, eax
0x180139aba  jle     short loc_180139AD7
0x180139abc  mov     r12d, 1
0x180139ac2  lea     eax, [r12+5]
0x180139ac7  cmp     ebx, [r14+10h]
0x180139acb  jl      short loc_180139AD2
0x180139acd  lea     eax, [r12+2]
0x180139ad2  add     si, ax
0x180139ad5  jmp     short loc_180139ADB
0x180139ad7  mov     r12d, [rbp+57h+arg_8]
0x180139adb  mov     rax, [rdi]
0x180139ade  mov     rcx, rdi
0x180139ae1  mov     rax, [rax+0B0h]
0x180139ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139aed  movzx   ecx, al
0x180139af0  lea     rdx, __ImageBase
0x180139af7  sub     ecx, 1
0x180139afa  jz      short loc_180139B20
0x180139afc  sub     ecx, 1
0x180139aff  jz      short loc_180139B13
0x180139b01  cmp     ecx, 1
0x180139b04  jnz     short loc_180139B2B
0x180139b06  movzx   eax, si
0x180139b09  movzx   esi, byte ptr [rax+rdx+2BF330h]
0x180139b11  jmp     short loc_180139B2B
0x180139b13  movzx   eax, si
0x180139b16  movzx   esi, byte ptr [rax+rdx+2BF310h]
0x180139b1e  jmp     short loc_180139B2B
0x180139b20  movzx   eax, si
0x180139b23  movzx   esi, byte ptr [rax+rdx+2BF320h]
0x180139b2b  mov     rax, [rdi]
0x180139b2e  mov     rcx, rdi
0x180139b31  mov     rax, [rax+0B0h]
0x180139b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139b3d  mov     ecx, 1
0x180139b42  test    cl, al
0x180139b44  jz      short loc_180139B5F
0x180139b46  lea     eax, [rcx+1]
0x180139b49  cmp     r15w, ax
0x180139b4d  jnz     short loc_180139B55
0x180139b4f  movzx   r15d, cx
0x180139b53  jmp     short loc_180139B5F
0x180139b55  cmp     r15w, cx
0x180139b59  jnz     short loc_180139B5F
0x180139b5b  movzx   r15d, ax
0x180139b5f  movzx   eax, si
0x180139b62  lea     rdx, __ImageBase
0x180139b69  movzx   esi, r15w
0x180139b6d  movzx   ecx, ds:rva word_1802BF340[rdx+rax*2]
0x180139b75  movzx   eax, word ptr [r14+2]
0x180139b7a  mov     word ptr [rbp+57h+arg_8], cx
0x180139b7e  cmp     ds:rva word_1802BF360[rdx+rsi*2], ax
0x180139b86  jz      short loc_180139BF0
0x180139b88  cmp     qword ptr [r14+8], 0
0x180139b8d  jz      short loc_180139BB9
0x180139b8f  xor     r9d, r9d; HDC
0x180139b92  xor     r8d, r8d; int
0x180139b95  mov     rdx, rdi; struct CDisplay *
0x180139b98  mov     rcx, r14; this
0x180139b9b  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180139ba0  mov     rcx, [r14+8]; ho
0x180139ba4  call    cs:__imp_DeleteObject
0x180139baa  lea     rdx, __ImageBase
0x180139bb1  mov     qword ptr [r14+8], 0
0x180139bb9  movzx   edx, ds:rva word_1802BF360[rdx+rsi*2]; lpBitmapName
0x180139bc1  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x180139bc8  mov     [r14+2], dx
0x180139bcd  call    cs:__imp_LoadBitmapW
0x180139bd3  xor     r9d, r9d; HDC
0x180139bd6  mov     rdx, rdi; struct CDisplay *
0x180139bd9  mov     rcx, r14; this
0x180139bdc  mov     [r14+8], rax
0x180139be0  lea     r8d, [r9+1]; int
0x180139be4  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x180139be9  lea     rdx, __ImageBase
0x180139bf0  xor     eax, eax
0x180139bf2  lea     r15, ?s_dummyHost@CITextHost2Ref@@0VCDummyHost@@A; CDummyHost CITextHost2Ref::s_dummyHost
0x180139bf9  cmp     [rbp+57h+arg_18], eax
0x180139bfc  jnz     short loc_180139C1C
0x180139bfe  test    r12d, r12d
0x180139c01  jnz     short loc_180139C1C
0x180139c03  movzx   ecx, ds:rva word_1802BF358[rdx+rsi*2]
0x180139c0b  mov     word ptr [rbp+57h+arg_8], cx
0x180139c0f  mov     rcx, rdi; this
0x180139c12  call    ?FinishSmoothVScroll@CDisplay@@QEAAXXZ; CDisplay::FinishSmoothVScroll(void)
0x180139c17  jmp     loc_180139D80
0x180139c1c  xorps   xmm0, xmm0
0x180139c1f  lea     rdx, [rbp+57h+var_78]; struct RECTUV *
0x180139c23  xor     r8d, r8d; struct RECTUV *
0x180139c26  mov     rcx, r13; this
0x180139c29  movdqu  [rbp+57h+var_78], xmm0
0x180139c2e  call    ?TxGetClientRect@CTxtEdit@@QEBAXAEAURECTUV@@PEAU2@@Z; CTxtEdit::TxGetClientRect(RECTUV &,RECTUV *)
0x180139c33  mov     eax, dword ptr [rbp+57h+var_78+8]
0x180139c36  sub     eax, dword ptr [rbp+57h+var_78]
0x180139c39  mov     edx, dword ptr [rbp+57h+var_88+4]
0x180139c3c  mov     esi, dword ptr [rbp+57h+var_78+0Ch]
0x180139c3f  mov     r11d, [r14+14h]
0x180139c43  sub     edx, r11d; int
0x180139c46  sub     esi, dword ptr [rbp+57h+var_78+4]
0x180139c49  sub     ebx, [r14+10h]
0x180139c4d  sar     eax, 1
0x180139c4f  mov     [rbp+57h+var_90], eax
0x180139c52  add     eax, ebx
0x180139c54  add     eax, dword ptr [rbp+57h+var_78]
0x180139c57  lea     r8d, ds:0[rsi*4]; int
0x180139c5f  imul    ecx, edx, 0FAh; int
0x180139c65  mov     dword ptr [rbp+57h+var_80], eax
0x180139c68  mov     [rbp+57h+var_8C], edx
0x180139c6b  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x180139c70  mov     r14d, [rbp+57h+arg_18]
0x180139c74  xor     edx, edx
0x180139c76  test    eax, eax
0x180139c78  mov     r9d, eax
0x180139c7b  lea     eax, [rdx+1]
0x180139c7e  cmovz   r9d, eax; int
0x180139c82  test    r14d, r14d
0x180139c85  jz      short loc_180139CA8
0x180139c87  sub     r11d, dword ptr [rbp+57h+var_88+4]
0x180139c8b  lea     eax, [rsi+rsi*4]
0x180139c8e  mov     [rsp+0C0h+var_98], edx; int
0x180139c92  add     eax, eax
0x180139c94  xor     r8d, r8d; unsigned __int16
0x180139c97  mov     [rsp+0C0h+var_A0], eax; int
0x180139c9b  mov     edx, r11d; int
0x180139c9e  mov     rcx, rdi; this
0x180139ca1  call    ?SmoothVScroll@CDisplay@@QEAAXHGHHH@Z; CDisplay::SmoothVScroll(int,ushort,int,int,int)
0x180139ca6  xor     edx, edx
0x180139ca8  test    r12d, r12d
0x180139cab  jz      short loc_180139CDB
0x180139cad  mov     r8d, [rbp+57h+var_90]
0x180139cb1  sar     esi, 1
0x180139cb3  add     r8d, 0FFFFFFFEh
0x180139cb7  add     esi, dword ptr [rbp+57h+var_78+4]
0x180139cba  mov     dword ptr [rbp+57h+var_80+4], esi
0x180139cbd  cmp     r8d, 0FFFFh
0x180139cc4  ja      loc_180139DAF
0x180139cca  mov     rdx, [rbp+57h+var_80]
0x180139cce  xor     r9d, r9d
0x180139cd1  mov     rcx, rdi
0x180139cd4  call    ?AutoScroll@CDisplay@@QEAAHUtagLSPOINTUV@Ptls6@@GG@Z; CDisplay::AutoScroll(Ptls6::tagLSPOINTUV,ushort,ushort)
0x180139cd9  xor     edx, edx
0x180139cdb  test    byte ptr [r13+110h], 8
0x180139ce3  jz      loc_180139D80
0x180139ce9  test    r12d, r12d
0x180139cec  jnz     short loc_180139CF7
0x180139cee  test    r14d, r14d
0x180139cf1  jz      loc_180139D80
0x180139cf7  xorps   xmm0, xmm0
0x180139cfa  mov     edi, 700h
0x180139cff  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180139d03  movups  xmmword ptr [rbp+57h+var_58+0Ch], xmm0
0x180139d07  movups  [rbp+57h+var_68], xmm0
0x180139d0b  test    r12d, r12d
0x180139d0e  jz      short loc_180139D46
0x180139d10  mov     rax, rdx
0x180139d13  mov     dword ptr [rbp+57h+var_58+8], 114h
0x180139d1a  test    ebx, ebx
0x180139d1c  lea     r8, [rbp+57h+var_68]
0x180139d20  mov     rcx, r15
0x180139d23  setnle  al
0x180139d26  cmp     [r13+70h], rdx
0x180139d2a  mov     qword ptr [rbp+57h+var_58+0Ch], rax
0x180139d2e  mov     edx, edi
0x180139d30  cmovnz  rcx, [r13+70h]
0x180139d35  mov     rax, [rcx]
0x180139d38  mov     rax, [rax+130h]
0x180139d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d44  xor     edx, edx
0x180139d46  test    r14d, r14d
0x180139d49  jz      short loc_180139D80
0x180139d4b  cmp     [rbp+57h+var_8C], edx
0x180139d4e  lea     r8, [rbp+57h+var_68]
0x180139d52  mov     rax, rdx
0x180139d55  mov     dword ptr [rbp+57h+var_58+8], 115h
0x180139d5c  setnle  al
0x180139d5f  mov     rcx, r15
0x180139d62  cmp     [r13+70h], rdx
0x180139d66  mov     edx, edi
0x180139d68  mov     qword ptr [rbp+57h+var_58+0Ch], rax
0x180139d6c  cmovnz  rcx, [r13+70h]
0x180139d71  mov     rax, [rcx]
0x180139d74  mov     rax, [rax+130h]
0x180139d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139d80  xor     ecx, ecx
0x180139d82  cmp     [r13+70h], rcx
0x180139d86  cmovnz  r15, [r13+70h]
0x180139d8b  mov     rax, [r15]
0x180139d8e  mov     rbx, [rax+98h]
0x180139d95  movzx   eax, word ptr [rbp+57h+arg_8]
0x180139d99  test    ax, ax
0x180139d9c  jz      short loc_180139DB5
0x180139d9e  mov     rcx, cs:?hinstRE@@3PEAUHINSTANCE__@@EA; hInstance
0x180139da5  mov     edx, eax; lpCursorName
0x180139da7  call    cs:__imp_LoadCursorW
0x180139dad  jmp     short loc_180139DBC
0x180139daf  call    ?SafeIntOnOverflow@?$SafeIntExceptionHandler@VSafeIntException@@@SafeIntInternal@@SAXXZ; SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(void)
0x180139db5  mov     rax, cs:?_hcurArrow@CTxtEdit@@2PEAUHICON__@@EA; HICON__ * CTxtEdit::_hcurArrow
0x180139dbc  mov     rdx, rax
0x180139dbf  xor     r8d, r8d
0x180139dc2  mov     rax, rbx
0x180139dc5  mov     rcx, r15
0x180139dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180139dcd  mov     rbx, [rsp+0C0h+arg_0]
0x180139dd5  add     rsp, 90h
0x180139ddc  pop     r15
0x180139dde  pop     r14
0x180139de0  pop     r13
0x180139de2  pop     r12
0x180139de4  pop     rdi
0x180139de5  pop     rsi
0x180139de6  pop     rbp
0x180139de7  retn
```
