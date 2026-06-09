# CMetadataRDFReaderWriter::CreateXMLNodeFromItem(RDFItem *,IXMLDOMDocument *,IXMLDOMNode * *,int)

- ea: `0x1800171e0`
- end: `0x180017557`
- name: `?CreateXMLNodeFromItem@CMetadataRDFReaderWriter@@MEAAJPEAVRDFItem@@PEAUIXMLDOMDocument@@PEAPEAUIXMLDOMNode@@H@Z`
- size: `887`
- prototype: `int(CMetadataRDFReaderWriter *__hidden this, struct RDFItem *, struct IXMLDOMDocument *, struct IXMLDOMNode **, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180004500`
- `0x1800171c4`
- `0x1800171e0`
- `0x18001f438`
- `0x180023e34`
- `0x180024714`
- `0x1800248cc`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800174f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001750b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174f1`
- `OLEAUT32!__imp_SysFreeString` at `0x1800174fb`
- `OLEAUT32!__imp_SysFreeString` at `0x18001750b`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateXMLNodeFromItem(
        CMetadataRDFReaderWriter *this,
        struct RDFItem *a2,
        struct IXMLDOMDocument *a3,
        struct IXMLDOMNode **a4,
        unsigned int a5)
{
  int PrefixAsBSTR; // eax
  unsigned int v10; // ebx
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // ecx
  __int128 v14; // xmm0
  __int64 v15; // xmm1_8
  HRESULT (__stdcall *createNode)(IXMLDOMDocument *, VARIANT, BSTR, BSTR, IXMLDOMNode **); // rax
  int v17; // eax
  __int64 v18; // rax
  struct IXMLDOMNode *v20; // [rsp+30h] [rbp-81h] BYREF
  unsigned __int16 *v21; // [rsp+38h] [rbp-79h] BYREF
  int v22; // [rsp+40h] [rbp-71h] BYREF
  BSTR v23; // [rsp+48h] [rbp-69h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-61h] BYREF
  __int64 v25; // [rsp+58h] [rbp-59h] BYREF
  BSTR v26[2]; // [rsp+60h] [rbp-51h] BYREF
  __int128 v27; // [rsp+70h] [rbp-41h] BYREF
  __int64 v28; // [rsp+80h] [rbp-31h]
  __int64 v29; // [rsp+90h] [rbp-21h]
  __int64 v30; // [rsp+98h] [rbp-19h]
  __int128 v31; // [rsp+A0h] [rbp-11h]

  v30 = 0;
  v29 = 0;
  v23 = 0;
  v22 = 0;
  v27 = 0;
  LOWORD(v27) = 18;
  v20 = 0;
  v31 = 0;
  LOWORD(v31) = 18;
  v25 = 0;
  WORD4(v31) = 2;
  v26[0] = 0;
  bstrString = 0;
  LODWORD(v21) = 0;
  WORD4(v27) = 1;
  PrefixAsBSTR = RDFItem::CheckHasChanged(a2, (int *)&v21);
  v10 = PrefixAsBSTR;
  if ( PrefixAsBSTR < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_45;
    goto LABEL_10;
  }
  if ( !(_DWORD)v21 )
  {
    v11 = *((_QWORD *)a2 + 2);
    if ( v11 )
    {
      v20 = (struct IXMLDOMNode *)*((_QWORD *)a2 + 2);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
LABEL_44:
      *a4 = v20;
      v20 = 0;
      goto LABEL_45;
    }
  }
  if ( (*((_BYTE *)a2 + 8) & 0x40) == 0 )
  {
    PrefixAsBSTR = (*(__int64 (__fastcall **)(struct RDFItem *, BSTR *))(*(_QWORD *)a2 + 72LL))(a2, &bstrString);
    v10 = PrefixAsBSTR;
    if ( PrefixAsBSTR >= 0 )
    {
      PrefixAsBSTR = RDFItem::GetPrefixAsBSTR(a2, &v23);
      v10 = PrefixAsBSTR;
      if ( PrefixAsBSTR >= 0 )
      {
        if ( v23 )
        {
          v22 = 1;
        }
        else
        {
          PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, BSTR, BSTR *, __int64, int *))(*(_QWORD *)this + 248LL))(
                           this,
                           bstrString,
                           &v23,
                           1,
                           &v22);
          v10 = PrefixAsBSTR;
          if ( PrefixAsBSTR < 0 )
            goto LABEL_9;
          PrefixAsBSTR = RDFItem::SetPrefix(a2, v23);
          v10 = PrefixAsBSTR;
          if ( PrefixAsBSTR < 0 )
            goto LABEL_9;
        }
        PrefixAsBSTR = (*(__int64 (__fastcall **)(struct RDFItem *, BSTR *))(*(_QWORD *)a2 + 80LL))(a2, v26);
        v10 = PrefixAsBSTR;
        if ( PrefixAsBSTR >= 0 )
        {
          CStackBSTR::CStackBSTR((CStackBSTR *)&v21, v23, v26[0]);
          if ( !v21 )
          {
            v10 = -2147024882;
LABEL_21:
            if ( !g_doStackCaptures )
            {
LABEL_24:
              FreeBSTR(&v21);
              goto LABEL_45;
            }
            v13 = v10;
LABEL_23:
            DoStackCapture(v13);
            goto LABEL_24;
          }
          if ( (*((_BYTE *)a2 + 8) & 0x10) != 0 )
          {
            v14 = v31;
            v15 = v29;
          }
          else
          {
            v14 = v27;
            v15 = v30;
          }
          createNode = a3->lpVtbl->createNode;
          v27 = v14;
          v28 = v15;
          v17 = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int128 *, unsigned __int16 *, BSTR, struct IXMLDOMNode **))createNode)(
                  a3,
                  &v27,
                  v21,
                  bstrString,
                  &v20);
          v10 = v17;
          if ( v17 < 0 )
          {
            if ( !g_doStackCaptures )
              goto LABEL_24;
            v13 = v17;
            goto LABEL_23;
          }
          if ( v17 )
          {
            v10 = -2147467259;
            goto LABEL_21;
          }
          FreeBSTR(&v21);
          v18 = *(_QWORD *)this;
          if ( (*((_BYTE *)a2 + 8) & 4) != 0 )
            PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct RDFItem *, __int64 *, _QWORD))(v18 + 208))(
                             this,
                             a2,
                             &v25,
                             a5);
          else
            PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct RDFItem *, struct IXMLDOMDocument *, __int64 *))(v18 + 216))(
                             this,
                             a2,
                             a3,
                             &v25);
          v10 = PrefixAsBSTR;
          if ( PrefixAsBSTR >= 0 )
          {
            PrefixAsBSTR = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64, _QWORD))v20->lpVtbl->appendChild)(
                             v20,
                             v25,
                             0);
            v10 = PrefixAsBSTR;
            if ( PrefixAsBSTR >= 0 )
            {
              if ( PrefixAsBSTR )
              {
                v10 = -2147467259;
                if ( !g_doStackCaptures )
                  goto LABEL_45;
                v12 = -2147467259;
LABEL_11:
                DoStackCapture(v12);
                goto LABEL_45;
              }
              goto LABEL_41;
            }
          }
        }
      }
    }
LABEL_9:
    if ( !g_doStackCaptures )
      goto LABEL_45;
    goto LABEL_10;
  }
  PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct RDFItem *, struct IXMLDOMNode **, _QWORD))(*(_QWORD *)this + 208LL))(
                   this,
                   a2,
                   &v20,
                   a5);
  v10 = PrefixAsBSTR;
  if ( PrefixAsBSTR < 0 )
    goto LABEL_9;
LABEL_41:
  PrefixAsBSTR = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, struct IXMLDOMDocument *, struct RDFItem *, struct IXMLDOMNode *))(*(_QWORD *)this + 376LL))(
                   this,
                   a3,
                   a2,
                   v20);
  v10 = PrefixAsBSTR;
  if ( PrefixAsBSTR >= 0 )
    goto LABEL_44;
  if ( g_doStackCaptures )
  {
LABEL_10:
    v12 = PrefixAsBSTR;
    goto LABEL_11;
  }
LABEL_45:
  SysFreeString(bstrString);
  SysFreeString(v26[0]);
  if ( v22 )
    SysFreeString(v23);
  if ( v20 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  return v10;
}

```

## disassembly

```asm
0x1800171e0  push    rbp
0x1800171e2  push    rbx
0x1800171e3  push    rsi
0x1800171e4  push    rdi
0x1800171e5  push    r12
0x1800171e7  push    r13
0x1800171e9  push    r14
0x1800171eb  push    r15
0x1800171ed  lea     rbp, [rsp-17h]
0x1800171f2  sub     rsp, 0C8h
0x1800171f9  xor     r12d, r12d
0x1800171fc  xor     eax, eax
0x1800171fe  mov     [rbp+4Fh+var_68], rax
0x180017202  mov     rdi, rdx
0x180017205  mov     [rbp+4Fh+var_70], rax
0x180017209  lea     rdx, [rbp+4Fh+var_C8]; int *
0x18001720d  xorps   xmm0, xmm0
0x180017210  mov     [rbp+4Fh+var_B8], r12
0x180017214  lea     eax, [r12+12h]
0x180017219  mov     [rbp+4Fh+var_C0], r12d
0x18001721d  movups  [rbp+4Fh+var_90], xmm0
0x180017221  mov     word ptr [rbp+4Fh+var_90], ax
0x180017225  mov     rsi, rcx
0x180017228  xorps   xmm1, xmm1
0x18001722b  mov     [rsp+100h+var_D0], r12
0x180017230  movups  [rbp+4Fh+var_60], xmm1
0x180017234  mov     word ptr [rbp+4Fh+var_60], ax
0x180017238  lea     r13d, [r12+1]
0x18001723d  lea     eax, [r12+2]
0x180017242  mov     [rbp+4Fh+var_A8], r12
0x180017246  mov     rcx, rdi; this
0x180017249  mov     word ptr [rbp+4Fh+var_60+8], ax
0x18001724d  mov     r15, r9
0x180017250  mov     [rbp+4Fh+var_A0], r12
0x180017254  mov     r14, r8
0x180017257  mov     [rbp+4Fh+bstrString], r12
0x18001725b  mov     dword ptr [rbp+4Fh+var_C8], r12d
0x18001725f  mov     word ptr [rbp+4Fh+var_90+8], r13w
0x180017264  call    ?CheckHasChanged@RDFItem@@QEAAJPEAH@Z; RDFItem::CheckHasChanged(int *)
0x180017269  mov     ebx, eax
0x18001726b  test    eax, eax
0x18001726d  jns     short loc_180017280
0x18001726f  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180017276  jnz     short loc_1800172E0
0x180017278  test    eax, eax
0x18001727a  js      loc_1800174ED
0x180017280  cmp     dword ptr [rbp+4Fh+var_C8], r12d
0x180017284  jnz     short loc_1800172A5
0x180017286  mov     rcx, [rdi+10h]
0x18001728a  test    rcx, rcx
0x18001728d  jz      short loc_1800172A5
0x18001728f  mov     [rsp+100h+var_D0], rcx
0x180017294  mov     rax, [rcx]
0x180017297  mov     rax, [rax+8]
0x18001729b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172a0  jmp     loc_1800174E0
0x1800172a5  test    byte ptr [rdi+8], 40h
0x1800172a9  jz      short loc_1800172EC
0x1800172ab  mov     rax, [rsi]
0x1800172ae  lea     r8, [rsp+100h+var_D0]
0x1800172b3  mov     r9d, [rbp+4Fh+arg_20]
0x1800172b7  mov     rdx, rdi
0x1800172ba  mov     rcx, rsi
0x1800172bd  mov     rax, [rax+0D0h]
0x1800172c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172c9  mov     ebx, eax
0x1800172cb  test    eax, eax
0x1800172cd  jns     loc_1800174AC
0x1800172d3  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800172da  jz      loc_1800174ED
0x1800172e0  mov     ecx, eax; int
0x1800172e2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800172e7  jmp     loc_1800174ED
0x1800172ec  mov     rax, [rdi]
0x1800172ef  lea     rdx, [rbp+4Fh+bstrString]
0x1800172f3  mov     rcx, rdi
0x1800172f6  mov     rax, [rax+48h]
0x1800172fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172ff  mov     ebx, eax
0x180017301  test    eax, eax
0x180017303  js      short loc_1800172D3
0x180017305  lea     rdx, [rbp+4Fh+var_B8]; unsigned __int16 **
0x180017309  mov     rcx, rdi; this
0x18001730c  call    ?GetPrefixAsBSTR@RDFItem@@QEAAJPEAPEAG@Z; RDFItem::GetPrefixAsBSTR(ushort * *)
0x180017311  mov     ebx, eax
0x180017313  test    eax, eax
0x180017315  js      short loc_1800172D3
0x180017317  cmp     [rbp+4Fh+var_B8], r12
0x18001731b  jz      short loc_180017323
0x18001731d  mov     [rbp+4Fh+var_C0], r13d
0x180017321  jmp     short loc_180017365
0x180017323  mov     rax, [rsi]
0x180017326  lea     rcx, [rbp+4Fh+var_C0]
0x18001732a  mov     rdx, [rbp+4Fh+bstrString]
0x18001732e  lea     r8, [rbp+4Fh+var_B8]
0x180017332  mov     [rsp+100h+var_E0], rcx
0x180017337  mov     r9d, r13d
0x18001733a  mov     rcx, rsi
0x18001733d  mov     rax, [rax+0F8h]
0x180017344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017349  mov     ebx, eax
0x18001734b  test    eax, eax
0x18001734d  js      short loc_1800172D3
0x18001734f  mov     rdx, [rbp+4Fh+var_B8]; unsigned __int16 *
0x180017353  mov     rcx, rdi; this
0x180017356  call    ?SetPrefix@RDFItem@@QEAAJPEBG@Z; RDFItem::SetPrefix(ushort const *)
0x18001735b  mov     ebx, eax
0x18001735d  test    eax, eax
0x18001735f  js      loc_1800172D3
0x180017365  mov     rax, [rdi]
0x180017368  lea     rdx, [rbp+4Fh+var_A0]
0x18001736c  mov     rcx, rdi
0x18001736f  mov     rax, [rax+50h]
0x180017373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017378  mov     ebx, eax
0x18001737a  test    eax, eax
0x18001737c  js      loc_1800172D3
0x180017382  mov     r8, [rbp+4Fh+var_A0]; unsigned __int16 *
0x180017386  lea     rcx, [rbp+4Fh+var_C8]; this
0x18001738a  mov     rdx, [rbp+4Fh+var_B8]; unsigned __int16 *
0x18001738e  call    ??0CStackBSTR@@QEAA@QEAG0@Z; CStackBSTR::CStackBSTR(ushort * const,ushort * const)
0x180017393  mov     r8, [rbp+4Fh+var_C8]
0x180017397  test    r8, r8
0x18001739a  jnz     short loc_1800173BF
0x18001739c  mov     ebx, 8007000Eh
0x1800173a1  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800173a8  jz      short loc_1800173B1
0x1800173aa  mov     ecx, ebx; int
0x1800173ac  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800173b1  lea     rcx, [rbp+4Fh+var_C8]; unsigned __int16 **
0x1800173b5  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x1800173ba  jmp     loc_1800174ED
0x1800173bf  test    byte ptr [rdi+8], 10h
0x1800173c3  mov     rax, [r14]
0x1800173c6  jz      short loc_1800173D3
0x1800173c8  movups  xmm0, [rbp+4Fh+var_60]
0x1800173cc  movsd   xmm1, [rbp+4Fh+var_70]
0x1800173d1  jmp     short loc_1800173DC
0x1800173d3  movups  xmm0, [rbp+4Fh+var_90]
0x1800173d7  movsd   xmm1, [rbp+4Fh+var_68]
0x1800173dc  mov     r9, [rbp+4Fh+bstrString]
0x1800173e0  lea     rcx, [rsp+100h+var_D0]
0x1800173e5  mov     rax, [rax+1C0h]
0x1800173ec  lea     rdx, [rbp+4Fh+var_90]
0x1800173f0  mov     [rsp+100h+var_E0], rcx
0x1800173f5  mov     rcx, r14
0x1800173f8  movaps  [rbp+4Fh+var_90], xmm0
0x1800173fc  movsd   [rbp+4Fh+var_80], xmm1
0x180017401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017406  mov     ebx, eax
0x180017408  test    eax, eax
0x18001740a  jns     short loc_180017419
0x18001740c  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180017413  jz      short loc_1800173B1
0x180017415  mov     ecx, eax
0x180017417  jmp     short loc_1800173AC
0x180017419  jz      short loc_180017425
0x18001741b  mov     ebx, 80004005h
0x180017420  jmp     loc_1800173A1
0x180017425  lea     rcx, [rbp+4Fh+var_C8]; unsigned __int16 **
0x180017429  call    ?FreeBSTR@@YAXAEAPEAG@Z; FreeBSTR(ushort * &)
0x18001742e  test    byte ptr [rdi+8], 4
0x180017432  mov     rdx, rdi
0x180017435  mov     rax, [rsi]
0x180017438  mov     rcx, rsi
0x18001743b  jz      short loc_180017497
0x18001743d  mov     r9d, [rbp+4Fh+arg_20]
0x180017441  lea     r8, [rbp+4Fh+var_A8]
0x180017445  mov     rax, [rax+0D0h]
0x18001744c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017451  mov     ebx, eax
0x180017453  test    eax, eax
0x180017455  js      loc_1800172D3
0x18001745b  mov     rcx, [rsp+100h+var_D0]
0x180017460  xor     r8d, r8d
0x180017463  mov     rdx, [rbp+4Fh+var_A8]
0x180017467  mov     rax, [rcx]
0x18001746a  mov     rax, [rax+0A8h]
0x180017471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017476  mov     ebx, eax
0x180017478  test    eax, eax
0x18001747a  js      loc_1800172D3
0x180017480  jz      short loc_1800174AC
0x180017482  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180017489  mov     ebx, 80004005h
0x18001748e  jz      short loc_1800174ED
0x180017490  mov     ecx, ebx
0x180017492  jmp     loc_1800172E2
0x180017497  mov     rax, [rax+0D8h]
0x18001749e  lea     r9, [rbp+4Fh+var_A8]
0x1800174a2  mov     r8, r14
0x1800174a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174aa  jmp     short loc_180017451
0x1800174ac  mov     rax, [rsi]
0x1800174af  mov     r8, rdi
0x1800174b2  mov     r9, [rsp+100h+var_D0]
0x1800174b7  mov     rdx, r14
0x1800174ba  mov     rcx, rsi
0x1800174bd  mov     rax, [rax+178h]
0x1800174c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174c9  mov     ebx, eax
0x1800174cb  test    eax, eax
0x1800174cd  jns     short loc_1800174E0
0x1800174cf  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800174d6  jnz     loc_1800172E0
0x1800174dc  test    eax, eax
0x1800174de  js      short loc_1800174ED
0x1800174e0  mov     rax, [rsp+100h+var_D0]
0x1800174e5  mov     [r15], rax
0x1800174e8  mov     [rsp+100h+var_D0], r12
0x1800174ed  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800174f1  call    cs:__imp_SysFreeString
0x1800174f7  mov     rcx, [rbp+4Fh+var_A0]; bstrString
0x1800174fb  call    cs:__imp_SysFreeString
0x180017501  cmp     [rbp+4Fh+var_C0], r12d
0x180017505  jz      short loc_180017511
0x180017507  mov     rcx, [rbp+4Fh+var_B8]; bstrString
0x18001750b  call    cs:__imp_SysFreeString
0x180017511  mov     rcx, [rsp+100h+var_D0]
0x180017516  test    rcx, rcx
0x180017519  jz      short loc_18001752C
0x18001751b  mov     rax, [rcx]
0x18001751e  mov     rax, [rax+10h]
0x180017522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017527  mov     [rsp+100h+var_D0], r12
0x18001752c  mov     rcx, [rbp+4Fh+var_A8]
0x180017530  test    rcx, rcx
0x180017533  jz      short loc_180017541
0x180017535  mov     rdx, [rcx]
0x180017538  mov     rax, [rdx+10h]
0x18001753c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017541  mov     eax, ebx
0x180017543  add     rsp, 0C8h
0x18001754a  pop     r15
0x18001754c  pop     r14
0x18001754e  pop     r13
0x180017550  pop     r12
0x180017552  pop     rdi
0x180017553  pop     rsi
0x180017554  pop     rbx
0x180017555  pop     rbp
0x180017556  retn
```
