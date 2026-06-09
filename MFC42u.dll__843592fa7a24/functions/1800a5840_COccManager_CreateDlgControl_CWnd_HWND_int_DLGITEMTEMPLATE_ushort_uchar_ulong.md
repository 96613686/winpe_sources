# COccManager::CreateDlgControl(CWnd *,HWND__ *,int,DLGITEMTEMPLATE *,ushort,uchar *,ulong)

- ea: `0x1800a5840`
- end: `0x1800a5c07`
- name: `?CreateDlgControl@COccManager@@IEAAPEAUHWND__@@PEAVCWnd@@PEAU2@HPEAUDLGITEMTEMPLATE@@GPEAEK@Z`
- size: `967`
- prototype: `HWND __fastcall(COccManager *__hidden this, struct CWnd *, HWND, int, struct DLGITEMTEMPLATE *, unsigned __int16, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a5c10`

## callees

- `0x18000a430`
- `0x18000ce50`
- `0x18000d960`
- `0x180019290`
- `0x180039610`
- `0x180039690`
- `0x1800a5840`
- `0x1800a6a20`
- `0x1800a7710`
- `0x1800aa860`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800a5a94`
- `api-ms-win-core-com-l1-1-0!CLSIDFromProgID` at `0x1800a5a94`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a5a8c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800a5a8c`
- `USER32!SetWindowPos` at `0x1800a5b72`
- `USER32!SetWindowPos` at `0x1800a5b72`
- `USER32!MapDialogRect` at `0x1800a590a`
- `USER32!MapDialogRect` at `0x1800a590a`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800a5933`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x1800a5933`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a5bbb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a5bbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
COleControlSite *__fastcall COccManager::CreateDlgControl(
        COccManager *this,
        HWND *a2,
        HWND a3,
        int a4,
        struct DLGITEMTEMPLATE *a5,
        unsigned __int16 a6,
        unsigned __int8 *a7,
        unsigned int a8)
{
  struct DLGITEMTEMPLATE *v9; // rdi
  unsigned __int8 *v10; // rsi
  const OLECHAR *v11; // r13
  LONG y; // edx
  unsigned __int16 *v13; // r12
  unsigned int v14; // r14d
  __int64 v15; // rbx
  unsigned __int16 v16; // r15
  int v17; // eax
  int v18; // r15d
  _WORD *v19; // rdi
  int v20; // ebx
  int v21; // ecx
  _WORD *v22; // rax
  HRESULT v23; // eax
  int v24; // r13d
  struct CFile *v25; // rsi
  COleControlSite *v26; // rbx
  CWnd *v27; // r14
  int v28; // eax
  __int16 v30; // [rsp+60h] [rbp-A0h]
  __int16 v31; // [rsp+64h] [rbp-9Ch]
  int v32; // [rsp+68h] [rbp-98h]
  int v33; // [rsp+6Ch] [rbp-94h]
  COleControlSite *v34; // [rsp+70h] [rbp-90h] BYREF
  _WORD *v35; // [rsp+78h] [rbp-88h]
  LPCWSTR v36; // [rsp+80h] [rbp-80h] BYREF
  __int128 v37; // [rsp+88h] [rbp-78h] BYREF
  __int16 style_high; // [rsp+98h] [rbp-68h]
  struct DLGITEMTEMPLATE *v39; // [rsp+A0h] [rbp-60h]
  CWnd *v40; // [rsp+A8h] [rbp-58h]
  HWND hWndInsertAfter; // [rsp+B0h] [rbp-50h]
  _BYTE v42[64]; // [rsp+C0h] [rbp-40h] BYREF
  struct tagRECT Rect; // [rsp+100h] [rbp+0h] BYREF
  CLSID pclsid; // [rsp+110h] [rbp+10h] BYREF

  hWndInsertAfter = a3;
  v40 = (CWnd *)a2;
  v9 = a5;
  v39 = a5;
  v10 = a7;
  v37 = 0;
  style_high = 0;
  if ( a4 )
  {
    LODWORD(v37) = *(_DWORD *)&a5->x;
    DWORD1(v37) = a5->dwExtendedStyle;
    *((_QWORD *)&v37 + 1) = *(_QWORD *)&a5->cx;
    style_high = HIWORD(a5[1].style);
    v9 = (struct DLGITEMTEMPLATE *)&v37;
    v39 = (struct DLGITEMTEMPLATE *)&v37;
    v11 = (const OLECHAR *)&a5[1].dwExtendedStyle + 1;
  }
  else
  {
    v11 = (const OLECHAR *)&a5[1];
  }
  y = v9->y;
  Rect.left = v9->x;
  Rect.top = y;
  Rect.right = Rect.left + v9->cx;
  Rect.bottom = y + v9->cy;
  MapDialogRect(a2[8], &Rect);
  v13 = 0;
  v14 = a8;
  if ( a8 >= 4 )
  {
    v15 = *(unsigned int *)a7;
    v10 = a7 + 4;
    v14 = a8 - 4;
    if ( (_DWORD)v15 )
    {
      v13 = SysAllocStringLen((const OLECHAR *)v10, v15);
      v10 += 2 * v15;
      v14 -= 2 * v15;
    }
  }
  v35 = 0;
  v36 = _afxPchNil;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v16 = a6;
  if ( (unsigned __int16)(a6 - 890) <= 1u )
  {
    v17 = *(_DWORD *)v10;
    LODWORD(v34) = v17;
    v18 = v17 - 12;
    v10 += 12;
    if ( v17 != 12 )
    {
      v19 = v35;
      do
      {
        v20 = *(_DWORD *)v10;
        v30 = *((_WORD *)v10 + 2);
        v10 += 6;
        v18 -= 6;
        if ( v20 == -2147418111 )
        {
          v32 = *(_DWORD *)v10;
          v33 = *((_DWORD *)v10 + 1);
          CString::operator=((CString *)&v36, (LPCCH)v10 + 16);
          v21 = *((_DWORD *)v36 - 2);
          v10 += v21 + 17;
          v18 = v18 - v21 - 17;
          v31 = v30;
        }
        else
        {
          v22 = operator new(0x28u);
          v35 = v22;
          if ( v22 )
          {
            *(_QWORD *)v22 = 0;
            v22[4] = v30;
            *((_DWORD *)v22 + 3) = v20;
            *((_QWORD *)v22 + 2) = 0;
            *((_DWORD *)v22 + 7) = 0;
            *((_QWORD *)v22 + 4) = v19;
            v19 = v22;
          }
          else
          {
            v19 = 0;
          }
        }
      }
      while ( v18 );
      v35 = v19;
      v9 = v39;
      v17 = (int)v34;
    }
    v14 -= v17;
    v16 = a6 - 4;
  }
  pclsid = 0;
  if ( *v11 == 123 )
    v23 = CLSIDFromString(v11, &pclsid);
  else
    v23 = CLSIDFromProgID(v11, &pclsid);
  v24 = v23;
  CMemFile::CMemFile((CMemFile *)v42, v10, v14, 0);
  v25 = (struct CFile *)v42;
  if ( v16 == 888 )
    v25 = 0;
  v26 = 0;
  v34 = 0;
  if ( v24 >= 0 )
  {
    v27 = v40;
    if ( (unsigned int)CWnd::InitControlContainer(v40) )
    {
      v28 = COleControlContainer::CreateControl(
              *((COleControlContainer **)v27 + 14),
              0,
              &pclsid,
              0,
              v9->style,
              &Rect,
              v9->id,
              v25,
              v16 == 887,
              v13,
              &v34);
      v26 = v34;
      if ( v28 )
      {
        COleControlSite::FreezeEvents(v34, 1);
        SetWindowPos(*((HWND *)v26 + 9), hWndInsertAfter, 0, 0, 0, 0, 0x13u);
        *((_QWORD *)v26 + 29) = v35;
        CString::operator=((char *)v26 + 256, &v36);
        *((_WORD *)v26 + 120) = v31;
        *((_DWORD *)v26 + 62) = v32;
        *((_DWORD *)v26 + 63) = v33;
      }
    }
  }
  if ( v13 )
    SysFreeString(v13);
  if ( v26 )
    v26 = (COleControlSite *)*((_QWORD *)v26 + 9);
  CMemFile::~CMemFile((CMemFile *)v42);
  CString::~CString((CString *)&v36);
  return v26;
}

```

## disassembly

```asm
0x1800a5840  mov     [rsp-8+arg_0], rbx
0x1800a5845  push    rbp
0x1800a5846  push    rsi
0x1800a5847  push    rdi
0x1800a5848  push    r12
0x1800a584a  push    r13
0x1800a584c  push    r14
0x1800a584e  push    r15
0x1800a5850  lea     rbp, [rsp-30h]
0x1800a5855  sub     rsp, 130h
0x1800a585c  mov     rax, cs:__security_cookie
0x1800a5863  xor     rax, rsp
0x1800a5866  mov     [rbp+60h+var_40], rax
0x1800a586a  mov     [rbp+60h+hWndInsertAfter], r8
0x1800a586e  mov     r8, rdx
0x1800a5871  mov     [rbp+60h+var_B8], rdx
0x1800a5875  mov     rdi, [rbp+60h+arg_20]
0x1800a587c  mov     [rbp+60h+var_C0], rdi
0x1800a5880  mov     rsi, [rbp+60h+arg_30]
0x1800a5887  xorps   xmm0, xmm0
0x1800a588a  xor     eax, eax
0x1800a588c  movups  [rbp+60h+var_D8], xmm0
0x1800a5890  mov     [rbp+60h+var_C8], ax
0x1800a5894  test    r9d, r9d
0x1800a5897  jz      short loc_1800A58DE
0x1800a5899  mov     r13, rdi
0x1800a589c  mov     eax, [rdi+8]
0x1800a589f  mov     dword ptr [rbp+60h+var_D8], eax
0x1800a58a2  mov     eax, [rdi+4]
0x1800a58a5  mov     dword ptr [rbp+60h+var_D8+4], eax
0x1800a58a8  movzx   eax, word ptr [rdi+0Ch]
0x1800a58ac  mov     word ptr [rbp+60h+var_D8+8], ax
0x1800a58b0  movzx   eax, word ptr [rdi+0Eh]
0x1800a58b4  mov     word ptr [rbp+60h+var_D8+0Ah], ax
0x1800a58b8  movzx   eax, word ptr [rdi+10h]
0x1800a58bc  mov     word ptr [rbp+60h+var_D8+0Ch], ax
0x1800a58c0  movzx   eax, word ptr [rdi+12h]
0x1800a58c4  mov     word ptr [rbp+60h+var_D8+0Eh], ax
0x1800a58c8  movzx   eax, word ptr [rdi+14h]
0x1800a58cc  mov     [rbp+60h+var_C8], ax
0x1800a58d0  lea     rdi, [rbp+60h+var_D8]
0x1800a58d4  mov     [rbp+60h+var_C0], rdi
0x1800a58d8  add     r13, 18h
0x1800a58dc  jmp     short loc_1800A58E2
0x1800a58de  lea     r13, [rdi+12h]
0x1800a58e2  movsx   edx, word ptr [rdi+0Ah]
0x1800a58e6  movsx   ecx, word ptr [rdi+8]
0x1800a58ea  mov     [rbp+60h+Rect.left], ecx
0x1800a58ed  mov     [rbp+60h+Rect.top], edx
0x1800a58f0  movsx   eax, word ptr [rdi+0Ch]
0x1800a58f4  add     eax, ecx
0x1800a58f6  mov     [rbp+60h+Rect.right], eax
0x1800a58f9  movsx   eax, word ptr [rdi+0Eh]
0x1800a58fd  add     eax, edx
0x1800a58ff  mov     [rbp+60h+Rect.bottom], eax
0x1800a5902  lea     rdx, [rbp+60h+Rect]; lpRect
0x1800a5906  mov     rcx, [r8+40h]; hDlg
0x1800a590a  call    cs:__imp_MapDialogRect
0x1800a5910  xor     r12d, r12d
0x1800a5913  mov     r14d, [rbp+60h+arg_38]
0x1800a591a  cmp     r14d, 4
0x1800a591e  jb      short loc_1800A5946
0x1800a5920  mov     ebx, [rsi]
0x1800a5922  add     rsi, 4
0x1800a5926  add     r14d, 0FFFFFFFCh
0x1800a592a  test    ebx, ebx
0x1800a592c  jz      short loc_1800A5946
0x1800a592e  mov     edx, ebx; ui
0x1800a5930  mov     rcx, rsi; strIn
0x1800a5933  call    cs:__imp_SysAllocStringLen
0x1800a5939  mov     r12, rax
0x1800a593c  lea     rsi, [rsi+rbx*2]
0x1800a5940  lea     ecx, [rbx+rbx]
0x1800a5943  sub     r14d, ecx
0x1800a5946  mov     [rsp+160h+var_E8], 0
0x1800a594f  mov     rax, cs:?_afxPchNil@@3PEBGEB; ushort const * const _afxPchNil
0x1800a5956  mov     [rbp+60h+var_E0], rax
0x1800a595a  mov     [rsp+160h+var_FC], 0
0x1800a5962  mov     [rsp+160h+var_F8], 0
0x1800a596a  mov     [rsp+160h+var_F4], 0
0x1800a5972  mov     ecx, 37Ah
0x1800a5977  movzx   r15d, [rbp+60h+arg_28]
0x1800a597f  movzx   eax, r15w
0x1800a5983  sub     ax, cx
0x1800a5986  mov     ecx, 1
0x1800a598b  cmp     ax, cx
0x1800a598e  ja      loc_1800A5A76
0x1800a5994  mov     eax, [rsi]
0x1800a5996  mov     dword ptr [rsp+160h+var_F0], eax
0x1800a599a  lea     r15d, [rax-0Ch]
0x1800a599e  add     rsi, 0Ch
0x1800a59a2  test    r15d, r15d
0x1800a59a5  jz      loc_1800A5A62
0x1800a59ab  mov     rdi, [rsp+160h+var_E8]
0x1800a59b0  mov     ebx, [rsi]
0x1800a59b2  movzx   ecx, word ptr [rsi+4]
0x1800a59b6  mov     [rsp+160h+var_100], cx
0x1800a59bb  add     rsi, 6
0x1800a59bf  add     r15d, 0FFFFFFFAh
0x1800a59c3  cmp     ebx, 80010001h
0x1800a59c9  jnz     short loc_1800A5A0B
0x1800a59cb  mov     eax, [rsi]
0x1800a59cd  mov     [rsp+160h+var_F8], eax
0x1800a59d1  mov     eax, [rsi+4]
0x1800a59d4  mov     [rsp+160h+var_F4], eax
0x1800a59d8  lea     rbx, [rsi+10h]
0x1800a59dc  mov     rdx, rbx; lpMultiByteStr
0x1800a59df  lea     rcx, [rbp+60h+var_E0]; this
0x1800a59e3  call    ??4CString@@QEAAAEBV0@PEBD@Z; CString::operator=(char const *)
0x1800a59e8  mov     rax, [rbp+60h+var_E0]
0x1800a59ec  mov     ecx, [rax-8]
0x1800a59ef  lea     eax, [rcx+1]
0x1800a59f2  movsxd  rsi, eax
0x1800a59f5  add     rsi, rbx
0x1800a59f8  sub     r15d, ecx
0x1800a59fb  sub     r15d, 11h
0x1800a59ff  movzx   ecx, [rsp+160h+var_100]
0x1800a5a04  mov     word ptr [rsp+160h+var_FC], cx
0x1800a5a09  jmp     short loc_1800A5A4C
0x1800a5a0b  mov     ecx, 28h ; '('; Size
0x1800a5a10  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a5a15  mov     [rsp+160h+var_E8], rax
0x1800a5a1a  test    rax, rax
0x1800a5a1d  jz      short loc_1800A5A4A
0x1800a5a1f  mov     qword ptr [rax], 0
0x1800a5a26  movzx   ecx, [rsp+160h+var_100]
0x1800a5a2b  mov     [rax+8], cx
0x1800a5a2f  mov     [rax+0Ch], ebx
0x1800a5a32  mov     qword ptr [rax+10h], 0
0x1800a5a3a  mov     dword ptr [rax+1Ch], 0
0x1800a5a41  mov     [rax+20h], rdi
0x1800a5a45  mov     rdi, rax
0x1800a5a48  jmp     short loc_1800A5A4C
0x1800a5a4a  xor     edi, edi
0x1800a5a4c  test    r15d, r15d
0x1800a5a4f  jnz     loc_1800A59B0
0x1800a5a55  mov     [rsp+160h+var_E8], rdi
0x1800a5a5a  mov     rdi, [rbp+60h+var_C0]
0x1800a5a5e  mov     eax, dword ptr [rsp+160h+var_F0]
0x1800a5a62  sub     r14d, eax
0x1800a5a65  mov     eax, 0FFFCh
0x1800a5a6a  movzx   r15d, [rbp+60h+arg_28]
0x1800a5a72  add     r15w, ax
0x1800a5a76  xorps   xmm0, xmm0
0x1800a5a79  movups  xmmword ptr [rbp+60h+pclsid.Data1], xmm0
0x1800a5a7d  lea     rdx, [rbp+60h+pclsid]; lpclsid
0x1800a5a81  mov     rcx, r13; lpszProgID
0x1800a5a84  cmp     word ptr [r13+0], 7Bh ; '{'
0x1800a5a8a  jnz     short loc_1800A5A94
0x1800a5a8c  call    cs:__imp_CLSIDFromString
0x1800a5a92  jmp     short loc_1800A5A9A
0x1800a5a94  call    cs:__imp_CLSIDFromProgID
0x1800a5a9a  mov     r13d, eax
0x1800a5a9d  xor     r9d, r9d; unsigned int
0x1800a5aa0  mov     r8d, r14d; unsigned int
0x1800a5aa3  mov     rdx, rsi; unsigned __int8 *
0x1800a5aa6  lea     rcx, [rbp+60h+var_A0]; this
0x1800a5aaa  call    ??0CMemFile@@QEAA@PEAEII@Z; CMemFile::CMemFile(uchar *,uint,uint)
0x1800a5aaf  nop
0x1800a5ab0  mov     ecx, 378h
0x1800a5ab5  lea     rsi, [rbp+60h+var_A0]
0x1800a5ab9  xor     eax, eax
0x1800a5abb  cmp     r15w, cx
0x1800a5abf  cmovz   rsi, rax
0x1800a5ac3  xor     ebx, ebx
0x1800a5ac5  mov     [rsp+160h+var_F0], rbx
0x1800a5aca  test    r13d, r13d
0x1800a5acd  js      loc_1800A5BB3
0x1800a5ad3  mov     r14, [rbp+60h+var_B8]
0x1800a5ad7  mov     rcx, r14; this
0x1800a5ada  call    ?InitControlContainer@CWnd@@IEAAHXZ; CWnd::InitControlContainer(void)
0x1800a5adf  test    eax, eax
0x1800a5ae1  jz      loc_1800A5BB3
0x1800a5ae7  mov     eax, 377h
0x1800a5aec  xor     edx, edx
0x1800a5aee  cmp     r15w, ax
0x1800a5af2  setz    dl
0x1800a5af5  movzx   eax, word ptr [rdi+10h]
0x1800a5af9  lea     rcx, [rsp+160h+var_F0]
0x1800a5afe  mov     [rsp+160h+var_110], rcx; struct COleControlSite **
0x1800a5b03  mov     [rsp+160h+var_118], r12; unsigned __int16 *
0x1800a5b08  mov     [rsp+160h+var_120], edx; int
0x1800a5b0c  mov     [rsp+160h+var_128], rsi; struct CFile *
0x1800a5b11  mov     [rsp+160h+uFlags], eax; unsigned int
0x1800a5b15  lea     rax, [rbp+60h+Rect]
0x1800a5b19  mov     qword ptr [rsp+160h+cy], rax; lprcSrc
0x1800a5b1e  mov     eax, [rdi]
0x1800a5b20  mov     [rsp+160h+var_140], eax; unsigned int
0x1800a5b24  xor     r9d, r9d; unsigned __int16 *
0x1800a5b27  lea     r8, [rbp+60h+pclsid]; struct _GUID *
0x1800a5b2b  xor     edx, edx; struct CWnd *
0x1800a5b2d  mov     rcx, [r14+70h]; this
0x1800a5b31  call    ?CreateControl@COleControlContainer@@QEAAHPEAVCWnd@@AEBU_GUID@@PEBGKAEBUtagRECT@@IPEAVCFile@@HPEAGPEAPEAVCOleControlSite@@@Z; COleControlContainer::CreateControl(CWnd *,_GUID const &,ushort const *,ulong,tagRECT const &,uint,CFile *,int,ushort *,COleControlSite * *)
0x1800a5b36  mov     rbx, [rsp+160h+var_F0]
0x1800a5b3b  test    eax, eax
0x1800a5b3d  jz      short loc_1800A5BB3
0x1800a5b3f  mov     edx, 1; int
0x1800a5b44  mov     rcx, rbx; this
0x1800a5b47  call    ?FreezeEvents@COleControlSite@@QEAAXH@Z; COleControlSite::FreezeEvents(int)
0x1800a5b4c  mov     [rsp+160h+uFlags], 13h; uFlags
0x1800a5b54  mov     [rsp+160h+cy], 0; cy
0x1800a5b5c  mov     [rsp+160h+var_140], 0; cx
0x1800a5b64  xor     r9d, r9d; Y
0x1800a5b67  xor     r8d, r8d; X
0x1800a5b6a  mov     rdx, [rbp+60h+hWndInsertAfter]; hWndInsertAfter
0x1800a5b6e  mov     rcx, [rbx+48h]; hWnd
0x1800a5b72  call    cs:__imp_SetWindowPos
0x1800a5b78  mov     rax, [rsp+160h+var_E8]
0x1800a5b7d  mov     [rbx+0E8h], rax
0x1800a5b84  lea     rcx, [rbx+100h]
0x1800a5b8b  lea     rdx, [rbp+60h+var_E0]
0x1800a5b8f  call    ??4CString@@QEAAAEBV0@AEBV0@@Z; CString::operator=(CString const &)
0x1800a5b94  mov     eax, [rsp+160h+var_FC]
0x1800a5b98  mov     [rbx+0F0h], ax
0x1800a5b9f  mov     eax, [rsp+160h+var_F8]
0x1800a5ba3  mov     [rbx+0F8h], eax
0x1800a5ba9  mov     eax, [rsp+160h+var_F4]
0x1800a5bad  mov     [rbx+0FCh], eax
0x1800a5bb3  test    r12, r12
0x1800a5bb6  jz      short loc_1800A5BC1
0x1800a5bb8  mov     rcx, r12; bstrString
0x1800a5bbb  call    cs:__imp_SysFreeString
0x1800a5bc1  test    rbx, rbx
0x1800a5bc4  jz      short loc_1800A5BCA
0x1800a5bc6  mov     rbx, [rbx+48h]
0x1800a5bca  lea     rcx, [rbp+60h+var_A0]; this
0x1800a5bce  call    ??1CMemFile@@UEAA@XZ; CMemFile::~CMemFile(void)
0x1800a5bd3  nop
0x1800a5bd4  lea     rcx, [rbp+60h+var_E0]; this
0x1800a5bd8  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800a5bdd  mov     rax, rbx
0x1800a5be0  mov     rcx, [rbp+60h+var_40]
0x1800a5be4  xor     rcx, rsp; StackCookie
0x1800a5be7  call    __security_check_cookie
0x1800a5bec  mov     rbx, [rsp+160h+arg_0]
0x1800a5bf4  add     rsp, 130h
0x1800a5bfb  pop     r15
0x1800a5bfd  pop     r14
0x1800a5bff  pop     r13
0x1800a5c01  pop     r12
0x1800a5c03  pop     rdi
0x1800a5c04  pop     rsi
0x1800a5c05  pop     rbp
0x1800a5c06  retn
```
