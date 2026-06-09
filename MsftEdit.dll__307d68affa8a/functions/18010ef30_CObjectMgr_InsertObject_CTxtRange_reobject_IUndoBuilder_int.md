# CObjectMgr::InsertObject(CTxtRange *,_reobject *,IUndoBuilder *,int)

- ea: `0x18010ef30`
- end: `0x18010f3f0`
- name: `?InsertObject@CObjectMgr@@QEAAJPEAVCTxtRange@@PEAU_reobject@@PEAVIUndoBuilder@@H@Z`
- size: `1216`
- prototype: `int(CObjectMgr *__hidden this, struct CTxtRange *, struct _reobject *, struct IUndoBuilder *, int)`
- caller_count: `6`
- callee_count: `21`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180093e8c`
- `0x180110078`
- `0x180122588`
- `0x180165e58`
- `0x180175910`
- `0x180181bf8`

## callees

- `0x18001c6e0`
- `0x18001c800`
- `0x18002d2bc`
- `0x18002f618`
- `0x18002fbbc`
- `0x18003c384`
- `0x180050060`
- `0x180060490`
- `0x180067f60`
- `0x18006e770`
- `0x18008e644`
- `0x1800907f8`
- `0x18010ef30`
- `0x180129bd0`
- `0x18012a4a0`
- `0x18013509c`
- `0x18013bad0`
- `0x1801476cc`
- `0x180162378`
- `0x1801623cc`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010f18c`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18010f18c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2a0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2be`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2f0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f330`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2a0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2be`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f2f0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x18010f330`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18010f2e4`
- `ext-ms-win-gdi-draw-l1-1-1!PatBlt` at `0x18010f2e4`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010f288`
- `ext-ms-win-gdi-draw-l1-1-0!CreateCompatibleBitmap` at `0x18010f288`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010f2af`
- `ext-ms-win-gdi-draw-l1-1-0!CreateSolidBrush` at `0x18010f2af`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f2f9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f320`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f339`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f2f9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f320`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18010f339`

## pseudocode

```c
__int64 __fastcall CObjectMgr::InsertObject(
        CObjectMgr *this,
        struct CTxtRange *a2,
        struct _reobject *a3,
        struct IUndoBuilder *a4,
        int a5)
{
  CTxtPtr *v5; // r12
  __int64 v8; // rdx
  __int64 v10; // rax
  CTxtEdit *v11; // r13
  LPOLECLIENTSITE polesite; // r14
  __int64 v13; // rdx
  CTxtStory *v14; // rbp
  __int64 result; // rax
  int v16; // ecx
  int v17; // edx
  int v18; // eax
  struct IUndoBuilder *v19; // rax
  unsigned int v20; // edi
  int v21; // edx
  __int64 v22; // rcx
  const struct CCharFormat *CF; // rax
  CObjectMgr *v24; // rcx
  unsigned int v25; // ebx
  DWORD dwFlags; // eax
  struct CDocInfo *DocInfo; // rbp
  HDC ScreenDC; // rax
  HDC CompatibleDC; // r15
  __int64 v30; // r11
  int v31; // r11^4
  __int64 v32; // r11
  HDC v33; // rax
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v35; // r12
  HGDIOBJ v36; // r13
  HBRUSH SolidBrush; // rdi
  HGDIOBJ v38; // rbx
  void *v39; // rcx
  int v40; // [rsp+50h] [rbp-78h]
  LONG h; // [rsp+50h] [rbp-78h]
  LONG wa; // [rsp+58h] [rbp-70h]
  struct tagRECT v44; // [rsp+60h] [rbp-68h] BYREF

  v5 = (struct CTxtRange *)((char *)a2 + 24);
  v8 = *((_QWORD *)a2 + 3);
  v10 = v8 - 8;
  if ( v8 )
    v11 = *(CTxtEdit **)(v10 + 48);
  else
    v11 = 0;
  polesite = a3->polesite;
  v13 = -v8;
  v14 = (CTxtStory *)(v10 & -(__int64)(v13 != 0));
  if ( !polesite
    || !COleObject::EnsureNmp((COleObject *)a3->polesite, (struct CTxtStory *)(v10 & -(__int64)(v13 != 0)), (int)a3) )
  {
    return 2147500037LL;
  }
  result = CTxtStory::InitObjects(v14);
  if ( !(_DWORD)result )
  {
    polesite[9].lpVtbl = (struct IOleClientSiteVtbl *)v14;
    v16 = *((_DWORD *)a2 + 26);
    v17 = -v16;
    if ( v16 > 0 )
      v17 = *((_DWORD *)a2 + 26);
    v18 = *((_DWORD *)a2 + 10) - v16;
    if ( v16 < 0 )
      v18 = *((_DWORD *)a2 + 10);
    LODWORD(polesite[10].lpVtbl) = ~v18;
    v19 = 0;
    if ( (a3->dwFlags & 0x400) == 0 )
      v19 = a4;
    v20 = 0;
    *(_QWORD *)&v44.left = v19;
    if ( a5 && v17 == 1 )
    {
      v21 = *((_DWORD *)a2 + 26);
      if ( v21 > 0 )
      {
        CRchTxtPtr::Move((struct CTxtRange *)((char *)a2 + 8), -v21);
        *((_DWORD *)a2 + 26) = -*((_DWORD *)a2 + 26);
      }
      if ( CTxtPtr::GetChar(v5) == 32 && (*(_DWORD *)CTxtEdit::GetCharFormat(v11, *((_WORD *)a2 + 56)) & 0x100) == 0 )
        v20 = 64;
    }
    CTxtRange::CheckTableSelection(a2, v17, 1, 0, v20, 0);
    v22 = *((_QWORD *)this + 3);
    if ( !v22
      || (result = (*(__int64 (__fastcall **)(__int64, CLSID *, LPSTORAGE, __int64))(*(_QWORD *)v22 + 48LL))(
                     v22,
                     &a3->clsid,
                     a3->pstg,
                     0xFFFFFFFFLL),
          !(_DWORD)result) )
    {
      if ( !a5 )
        goto LABEL_27;
      v40 = *(_DWORD *)CRchTxtPtr::GetCFBackward((struct CTxtRange *)((char *)a2 + 8));
      CF = CRchTxtPtr::GetCF((struct CTxtRange *)((char *)a2 + 8));
      if ( !*((_DWORD *)a2 + 10) || (v40 & *(_DWORD *)CF & 0x800000) != 0 && (*(_DWORD *)CF & 0x100) != 0 )
        v20 |= 0x18u;
      if ( (*(unsigned int (__fastcall **)(struct CTxtRange *, __int64, const unsigned __int16 *, _QWORD, _DWORD, _QWORD, unsigned int, _DWORD))(*(_QWORD *)a2 + 888LL))(
             a2,
             1,
             &szEmbedding,
             *(_QWORD *)&v44.left,
             0,
             0,
             v20,
             0) == 1 )
      {
LABEL_27:
        if ( CTxtPtr::GetPrevChar(v5) == 0xFFFC )
        {
          result = COleObject::InitFromREOBJECT(
                     (COleObject *)polesite,
                     (struct CTxtStory *)((*((_QWORD *)a2 + 3) - 8LL) & -(__int64)(*((_QWORD *)a2 + 3) != 0)),
                     *((_DWORD *)a2 + 10) - 1,
                     a3);
          if ( (_DWORD)result )
            return result;
          v25 = CObjectMgr::RestoreObject(v24, (struct COleObject *)polesite);
          dwFlags = a3->dwFlags;
          if ( (dwFlags & 0x400) == 0 )
          {
            if ( (dwFlags & 0x200) != 0 )
              CTxtEdit::OnSetTypographyOptions(v11, 0x10u, 16);
            if ( !v25 && (WORD1(polesite[19].lpVtbl) & 0x1000) != 0 )
              CTxtStory::ModifyBlobCount(v14, 1);
            return v25;
          }
          DocInfo = CTxtEdit::GetDocInfo(v11);
          if ( DocInfo )
          {
            ScreenDC = CW32System::GetScreenDC();
            CompatibleDC = CreateCompatibleDC(ScreenDC);
            if ( CompatibleDC )
            {
              if ( *((_BYTE *)DocInfo + 139) == 0xFF )
              {
                v30 = *(__int64 *)((char *)&polesite[10].lpVtbl + 4);
                *((_BYTE *)DocInfo + 139) = 3;
                *((_DWORD *)DocInfo + 42) = 6553700;
                *((_WORD *)DocInfo + 86) = CW32System::MulDivFunc(v30, 72, 127);
                *((_WORD *)DocInfo + 87) = CW32System::MulDivFunc(v31, 72, 127);
              }
              wa = CW32System::MulDivFunc(
                     *((__int16 *)DocInfo + 84) * *((__int16 *)DocInfo + 86) / 100,
                     *(_DWORD *)(*((_QWORD *)v11 + 17) + 52LL),
                     1440);
              h = CW32System::MulDivFunc(
                    *((__int16 *)DocInfo + 87) * *((__int16 *)DocInfo + 85) / 100,
                    *(_DWORD *)(v32 + 56),
                    1440);
              v44.bottom = h;
              *(_QWORD *)&v44.left = 0;
              v44.right = wa;
              v33 = CW32System::GetScreenDC();
              CompatibleBitmap = CreateCompatibleBitmap(v33, wa, h);
              v35 = CompatibleBitmap;
              if ( CompatibleBitmap )
              {
                v36 = SelectObject(CompatibleDC, CompatibleBitmap);
                SolidBrush = CreateSolidBrush(*((_DWORD *)DocInfo + 32));
                v38 = SelectObject(CompatibleDC, SolidBrush);
                PatBlt(CompatibleDC, 0, 0, wa, h, 0xF00021u);
                SelectObject(CompatibleDC, v38);
                DeleteObject(SolidBrush);
                CW32System::OleDraw(
                  (struct IUnknown *)polesite[7].lpVtbl,
                  HIDWORD(polesite[18].lpVtbl),
                  CompatibleDC,
                  &v44);
                v39 = (void *)*((_QWORD *)DocInfo + 12);
                if ( v39 )
                  DeleteObject(v39);
                *((_QWORD *)DocInfo + 12) = v35;
                SelectObject(CompatibleDC, v36);
              }
              DeleteObject(CompatibleDC);
            }
            CTxtRange::Set(a2, *((_DWORD *)a2 + 10), 1);
            (*(void (__fastcall **)(struct CTxtRange *, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, int, _DWORD))(*(_QWORD *)a2 + 888LL))(
              a2,
              0,
              0,
              0,
              0,
              0,
              32,
              0);
            return 1;
          }
        }
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18010ef30  push    rbx
0x18010ef32  push    rbp
0x18010ef33  push    rsi
0x18010ef34  push    rdi
0x18010ef35  push    r12
0x18010ef37  push    r13
0x18010ef39  push    r14
0x18010ef3b  push    r15
0x18010ef3d  sub     rsp, 88h
0x18010ef44  mov     rax, cs:__security_cookie
0x18010ef4b  xor     rax, rsp
0x18010ef4e  mov     [rsp+0C8h+var_58], rax
0x18010ef53  lea     r12, [rdx+18h]
0x18010ef57  mov     qword ptr [rsp+0C8h+w], rcx
0x18010ef5c  mov     rsi, rdx
0x18010ef5f  mov     rbx, r9
0x18010ef62  mov     rdx, [r12]
0x18010ef66  mov     r15, r8
0x18010ef69  lea     rax, [rdx-8]
0x18010ef6d  test    rdx, rdx
0x18010ef70  jz      short loc_18010EF78
0x18010ef72  mov     r13, [rax+30h]
0x18010ef76  jmp     short loc_18010EF7B
0x18010ef78  xor     r13d, r13d
0x18010ef7b  mov     r14, [r8+28h]
0x18010ef7f  neg     rdx
0x18010ef82  sbb     rbp, rbp
0x18010ef85  and     rbp, rax
0x18010ef88  test    r14, r14
0x18010ef8b  jz      loc_18010F3CA
0x18010ef91  mov     rdx, rbp; struct CTxtStory *
0x18010ef94  mov     rcx, r14; this
0x18010ef97  call    ?EnsureNmp@COleObject@@QEAAHPEAVCTxtStory@@H@Z; COleObject::EnsureNmp(CTxtStory *,int)
0x18010ef9c  test    eax, eax
0x18010ef9e  jz      loc_18010F3CA
0x18010efa4  mov     rcx, rbp; this
0x18010efa7  call    ?InitObjects@CTxtStory@@QEAAJXZ; CTxtStory::InitObjects(void)
0x18010efac  test    eax, eax
0x18010efae  jnz     loc_18010F3CF
0x18010efb4  mov     [r14+48h], rbp
0x18010efb8  mov     ecx, [rsi+68h]
0x18010efbb  mov     edx, ecx
0x18010efbd  mov     eax, [rsi+28h]
0x18010efc0  neg     edx
0x18010efc2  cmovs   edx, ecx
0x18010efc5  sub     eax, ecx
0x18010efc7  test    ecx, ecx
0x18010efc9  cmovs   eax, [rsi+28h]
0x18010efcd  not     eax
0x18010efcf  mov     [r14+50h], eax
0x18010efd3  mov     eax, 0
0x18010efd8  test    dword ptr [r15+3Ch], 400h
0x18010efe0  cmovz   rax, rbx
0x18010efe4  mov     ebx, [rsp+0C8h+arg_20]
0x18010efeb  xor     edi, edi
0x18010efed  mov     qword ptr [rsp+0C8h+var_68.left], rax
0x18010eff2  test    ebx, ebx
0x18010eff4  jz      short loc_18010F041
0x18010eff6  cmp     edx, 1
0x18010eff9  jnz     short loc_18010F041
0x18010effb  mov     edx, [rsi+68h]
0x18010effe  test    edx, edx
0x18010f000  jle     short loc_18010F015
0x18010f002  neg     edx; int
0x18010f004  lea     rcx, [rsi+8]; this
0x18010f008  call    ?Move@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Move(long)
0x18010f00d  mov     eax, [rsi+68h]
0x18010f010  neg     eax
0x18010f012  mov     [rsi+68h], eax
0x18010f015  mov     rcx, r12; this
0x18010f018  call    ?GetChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetChar(void)
0x18010f01d  mov     ecx, 20h ; ' '
0x18010f022  cmp     ax, cx
0x18010f025  jnz     short loc_18010F041
0x18010f027  movzx   edx, word ptr [rsi+70h]; __int16
0x18010f02b  mov     rcx, r13; this
0x18010f02e  call    ?GetCharFormat@CTxtEdit@@QEBAPEBVCCharFormat@@F@Z; CTxtEdit::GetCharFormat(short)
0x18010f033  test    dword ptr [rax], 100h
0x18010f039  mov     eax, 40h ; '@'
0x18010f03e  cmovz   edi, eax
0x18010f041  xor     r9d, r9d; int *
0x18010f044  mov     qword ptr [rsp+0C8h+rop], 0; int *
0x18010f04d  mov     rcx, rsi; this
0x18010f050  mov     [rsp+0C8h+h], edi; unsigned int
0x18010f054  lea     r8d, [r9+1]; int
0x18010f058  call    ?CheckTableSelection@CTxtRange@@QEAAHHHPEAHK0@Z; CTxtRange::CheckTableSelection(int,int,int *,ulong,int *)
0x18010f05d  mov     rax, qword ptr [rsp+0C8h+w]
0x18010f062  mov     rcx, [rax+18h]
0x18010f066  test    rcx, rcx
0x18010f069  jz      short loc_18010F08B
0x18010f06b  mov     rax, [rcx]
0x18010f06e  lea     rdx, [r15+8]
0x18010f072  mov     r8, [r15+20h]
0x18010f076  or      r9d, 0FFFFFFFFh
0x18010f07a  mov     rax, [rax+30h]
0x18010f07e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f083  test    eax, eax
0x18010f085  jnz     loc_18010F3CF
0x18010f08b  test    ebx, ebx
0x18010f08d  jz      loc_18010F117
0x18010f093  lea     rcx, [rsi+8]; this
0x18010f097  call    ?GetCFBackward@CRchTxtPtr@@QEAAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCFBackward(void)
0x18010f09c  lea     rcx, [rsi+8]; this
0x18010f0a0  mov     eax, [rax]
0x18010f0a2  mov     [rsp+0C8h+var_78], eax
0x18010f0a6  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18010f0ab  cmp     dword ptr [rsi+28h], 0
0x18010f0af  jz      short loc_18010F0CB
0x18010f0b1  mov     edx, [rax]
0x18010f0b3  mov     eax, edx
0x18010f0b5  and     eax, [rsp+0C8h+var_78]
0x18010f0b9  bt      eax, 17h
0x18010f0bd  setb    cl
0x18010f0c0  bt      edx, 8
0x18010f0c4  setb    al
0x18010f0c7  test    al, cl
0x18010f0c9  jz      short loc_18010F0CE
0x18010f0cb  or      edi, 18h
0x18010f0ce  mov     rax, [rsi]
0x18010f0d1  lea     r8, ?szEmbedding@@3QBGB; ushort const near * const szEmbedding
0x18010f0d8  mov     r9, qword ptr [rsp+0C8h+var_68.left]
0x18010f0dd  mov     edx, 1
0x18010f0e2  mov     [rsp+0C8h+var_90], 0
0x18010f0ea  mov     rcx, rsi
0x18010f0ed  mov     [rsp+0C8h+var_98], edi
0x18010f0f1  mov     rax, [rax+378h]
0x18010f0f8  mov     qword ptr [rsp+0C8h+rop], 0
0x18010f101  mov     [rsp+0C8h+h], 0
0x18010f109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f10e  cmp     eax, 1
0x18010f111  jnz     loc_18010F3CA
0x18010f117  mov     rcx, r12; this
0x18010f11a  call    ?GetPrevChar@CTxtPtr@@QEBAGXZ; CTxtPtr::GetPrevChar(void)
0x18010f11f  mov     ecx, 0FFFCh
0x18010f124  cmp     ax, cx
0x18010f127  jnz     loc_18010F3CA
0x18010f12d  mov     rcx, [rsi+18h]
0x18010f131  mov     r9, r15; struct _reobject *
0x18010f134  mov     r8d, [rsi+28h]
0x18010f138  dec     r8d; int
0x18010f13b  lea     rax, [rcx-8]
0x18010f13f  neg     rcx
0x18010f142  mov     rcx, r14; this
0x18010f145  sbb     rdx, rdx
0x18010f148  and     rdx, rax; struct CTxtStory *
0x18010f14b  call    ?InitFromREOBJECT@COleObject@@QEAAJPEAVCTxtStory@@JPEAU_reobject@@@Z; COleObject::InitFromREOBJECT(CTxtStory *,long,_reobject *)
0x18010f150  test    eax, eax
0x18010f152  jnz     loc_18010F3CF
0x18010f158  mov     rdx, r14; struct COleObject *
0x18010f15b  call    ?RestoreObject@CObjectMgr@@QEAAJPEAVCOleObject@@@Z; CObjectMgr::RestoreObject(COleObject *)
0x18010f160  mov     ebx, eax
0x18010f162  mov     eax, [r15+3Ch]
0x18010f166  bt      eax, 0Ah
0x18010f16a  jnb     loc_18010F392
0x18010f170  mov     rcx, r13; this
0x18010f173  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x18010f178  mov     rbp, rax
0x18010f17b  test    rax, rax
0x18010f17e  jz      loc_18010F3CA
0x18010f184  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x18010f189  mov     rcx, rax; hdc
0x18010f18c  call    cs:__imp_CreateCompatibleDC
0x18010f192  mov     r15, rax
0x18010f195  test    rax, rax
0x18010f198  jz      loc_18010F33F
0x18010f19e  cmp     byte ptr [rbp+8Bh], 0FFh
0x18010f1a5  jnz     short loc_18010F1F0
0x18010f1a7  mov     r11, [r14+54h]
0x18010f1ab  mov     edi, 7Fh
0x18010f1b0  mov     r8d, edi; int
0x18010f1b3  mov     byte ptr [rbp+8Bh], 3
0x18010f1ba  mov     ecx, r11d; int
0x18010f1bd  mov     dword ptr [rbp+0A8h], 640064h
0x18010f1c7  lea     ebx, [rdi-37h]
0x18010f1ca  mov     edx, ebx; int
0x18010f1cc  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18010f1d1  shr     r11, 20h
0x18010f1d5  mov     r8d, edi; int
0x18010f1d8  mov     ecx, r11d; int
0x18010f1db  mov     [rbp+0ACh], ax
0x18010f1e2  mov     edx, ebx; int
0x18010f1e4  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18010f1e9  mov     [rbp+0AEh], ax
0x18010f1f0  movsx   eax, word ptr [rbp+0A8h]
0x18010f1f7  mov     r12d, 51EB851Fh
0x18010f1fd  movsx   ecx, word ptr [rbp+0ACh]
0x18010f204  mov     edi, 5A0h
0x18010f209  mov     r11, [r13+88h]
0x18010f210  mov     r8d, edi; int
0x18010f213  imul    ecx, eax
0x18010f216  mov     eax, r12d
0x18010f219  imul    ecx
0x18010f21b  mov     ecx, edx
0x18010f21d  sar     ecx, 5
0x18010f220  mov     edx, ecx
0x18010f222  shr     edx, 1Fh
0x18010f225  add     ecx, edx; int
0x18010f227  mov     edx, [r11+34h]; int
0x18010f22b  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18010f230  movsx   ecx, word ptr [rbp+0AEh]
0x18010f237  mov     ebx, eax
0x18010f239  movsx   edx, word ptr [rbp+0AAh]
0x18010f240  mov     r8d, edi; int
0x18010f243  imul    edx, ecx
0x18010f246  mov     [rsp+0C8h+w], eax
0x18010f24a  mov     eax, r12d
0x18010f24d  imul    edx
0x18010f24f  mov     ecx, edx
0x18010f251  sar     ecx, 5
0x18010f254  mov     edx, ecx
0x18010f256  shr     edx, 1Fh
0x18010f259  add     ecx, edx; int
0x18010f25b  mov     edx, [r11+38h]; int
0x18010f25f  call    ?MulDivFunc@CW32System@@SAHHHH@Z; CW32System::MulDivFunc(int,int,int)
0x18010f264  mov     edi, eax
0x18010f266  mov     [rsp+0C8h+var_78], eax
0x18010f26a  mov     [rsp+0C8h+var_68.bottom], eax
0x18010f26e  mov     qword ptr [rsp+0C8h+var_68.left], 0
0x18010f277  mov     [rsp+0C8h+var_68.right], ebx
0x18010f27b  call    ?GetScreenDC@CW32System@@SAPEAUHDC__@@XZ; CW32System::GetScreenDC(void)
0x18010f280  mov     rcx, rax; hdc
0x18010f283  mov     r8d, edi; cy
0x18010f286  mov     edx, ebx; cx
0x18010f288  call    cs:__imp_CreateCompatibleBitmap
0x18010f28e  mov     r12, rax
0x18010f291  test    rax, rax
0x18010f294  jz      loc_18010F336
0x18010f29a  mov     rdx, rax; h
0x18010f29d  mov     rcx, r15; hdc
0x18010f2a0  call    cs:__imp_SelectObject
0x18010f2a6  mov     ecx, [rbp+80h]; color
0x18010f2ac  mov     r13, rax
0x18010f2af  call    cs:__imp_CreateSolidBrush
0x18010f2b5  mov     rdx, rax; h
0x18010f2b8  mov     rcx, r15; hdc
0x18010f2bb  mov     rdi, rax
0x18010f2be  call    cs:__imp_SelectObject
0x18010f2c4  mov     r9d, [rsp+0C8h+w]; w
0x18010f2c9  xor     r8d, r8d; y
0x18010f2cc  mov     rbx, rax
0x18010f2cf  mov     [rsp+0C8h+rop], 0F00021h; rop
0x18010f2d7  mov     eax, [rsp+0C8h+var_78]
0x18010f2db  xor     edx, edx; x
0x18010f2dd  mov     rcx, r15; hdc
0x18010f2e0  mov     [rsp+0C8h+h], eax; h
0x18010f2e4  call    cs:__imp_PatBlt
0x18010f2ea  mov     rdx, rbx; h
0x18010f2ed  mov     rcx, r15; hdc
0x18010f2f0  call    cs:__imp_SelectObject
0x18010f2f6  mov     rcx, rdi; ho
0x18010f2f9  call    cs:__imp_DeleteObject
0x18010f2ff  mov     edx, [r14+94h]; unsigned int
0x18010f306  lea     r9, [rsp+0C8h+var_68]; struct tagRECT *
0x18010f30b  mov     rcx, [r14+38h]; struct IUnknown *
0x18010f30f  mov     r8, r15; HDC
0x18010f312  call    ?OleDraw@CW32System@@SAJPEAUIUnknown@@KPEAUHDC__@@PEBUtagRECT@@@Z; CW32System::OleDraw(IUnknown *,ulong,HDC__ *,tagRECT const *)
0x18010f317  mov     rcx, [rbp+60h]; ho
0x18010f31b  test    rcx, rcx
0x18010f31e  jz      short loc_18010F326
0x18010f320  call    cs:__imp_DeleteObject
0x18010f326  mov     rdx, r13; h
0x18010f329  mov     [rbp+60h], r12
0x18010f32d  mov     rcx, r15; hdc
0x18010f330  call    cs:__imp_SelectObject
0x18010f336  mov     rcx, r15; ho
0x18010f339  call    cs:__imp_DeleteObject
0x18010f33f  mov     edx, [rsi+28h]; int
0x18010f342  mov     r8d, 1; int
0x18010f348  mov     rcx, rsi; this
0x18010f34b  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18010f350  mov     rax, [rsi]
0x18010f353  xor     r9d, r9d
0x18010f356  mov     [rsp+0C8h+var_90], 0
0x18010f35e  xor     r8d, r8d
0x18010f361  mov     [rsp+0C8h+var_98], 20h ; ' '
0x18010f369  xor     edx, edx
0x18010f36b  mov     qword ptr [rsp+0C8h+rop], 0
0x18010f374  mov     rcx, rsi
0x18010f377  mov     rax, [rax+378h]
0x18010f37e  mov     [rsp+0C8h+h], 0
0x18010f386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010f38b  mov     ebx, 1
0x18010f390  jmp     short loc_18010F3C6
0x18010f392  bt      eax, 9
0x18010f396  jnb     short loc_18010F3A8
0x18010f398  mov     edx, 10h; unsigned __int64
0x18010f39d  mov     rcx, r13; this
0x18010f3a0  mov     r8d, edx; __int64
0x18010f3a3  call    ?OnSetTypographyOptions@CTxtEdit@@QEAAJ_K_J@Z; CTxtEdit::OnSetTypographyOptions(unsigned __int64,__int64)
0x18010f3a8  test    ebx, ebx
0x18010f3aa  jnz     short loc_18010F3C6
0x18010f3ac  mov     eax, 1000h
0x18010f3b1  test    [r14+9Ah], ax
0x18010f3b9  jz      short loc_18010F3C6
0x18010f3bb  lea     edx, [rbx+1]; int
0x18010f3be  mov     rcx, rbp; this
0x18010f3c1  call    ?ModifyBlobCount@CTxtStory@@QEAAXJ@Z; CTxtStory::ModifyBlobCount(long)
0x18010f3c6  mov     eax, ebx
0x18010f3c8  jmp     short loc_18010F3CF
0x18010f3ca  mov     eax, 80004005h
  ... truncated ...
```
