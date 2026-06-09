# CRenderer::StartRender(tagRECT const &,tagRECT const &,long)

- ea: `0x1800337ac`
- end: `0x180033a8b`
- name: `?StartRender@CRenderer@@QEAAHAEBUtagRECT@@0J@Z`
- size: `735`
- prototype: `int(CRenderer *__hidden this, const struct tagRECT *, const struct tagRECT *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800333d0`
- `0x180058d30`

## callees

- `0x1800337ac`
- `0x180033a94`
- `0x180033af0`
- `0x180092010`

## import_xrefs

- `GDI32!SetTextAlign` at `0x180033927`
- `GDI32!SetTextAlign` at `0x180033927`
- `GDI32!CreateCompatibleDC` at `0x1800339bf`
- `GDI32!CreateCompatibleDC` at `0x1800339bf`
- `GDI32!GetCurrentObject` at `0x180033983`
- `GDI32!GetCurrentObject` at `0x180033983`
- `GDI32!SelectObject` at `0x1800339f5`
- `GDI32!SelectObject` at `0x1800339f5`
- `GDI32!RealizePalette` at `0x180033a38`
- `GDI32!RealizePalette` at `0x180033a38`
- `GDI32!SelectPalette` at `0x180033a2b`
- `GDI32!SelectPalette` at `0x180033a2b`
- `GDI32!SetBkColor` at `0x180033899`
- `GDI32!SetBkColor` at `0x180033a0a`
- `GDI32!SetBkColor` at `0x180033899`
- `GDI32!SetBkColor` at `0x180033a0a`
- `GDI32!SetBkMode` at `0x180033939`
- `GDI32!SetBkMode` at `0x180033939`
- `GDI32!CreateCompatibleBitmap` at `0x1800339dc`
- `GDI32!CreateCompatibleBitmap` at `0x1800339dc`
- `GDI32!ExtTextOutA` at `0x180033918`
- `GDI32!ExtTextOutA` at `0x180033918`

## pseudocode

```c
__int64 __fastcall CRenderer::StartRender(CRenderer *this, const struct tagRECT *a2, const struct tagRECT *a3, int a4)
{
  __int64 v4; // rax
  __int64 v6; // rdi
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // ebp
  int v13; // esi
  int v14; // ebp
  unsigned int v15; // eax
  COLORREF v16; // edx
  HDC v17; // rcx
  int v18; // esi
  __int64 v19; // rcx
  HPALETTE CurrentObject; // rax
  HPALETTE v21; // rsi
  HDC v22; // r14
  HDC *v23; // rdi
  COLORREF v24; // r15d
  int v25; // ebp
  int v26; // r12d
  HDC CompatibleDC; // rax
  HBITMAP CompatibleBitmap; // rax
  HGDIOBJ v29; // rax
  HPALETTE v30; // rax
  HDC v31; // rcx

  v4 = *((_QWORD *)this + 15);
  v6 = *((_QWORD *)this + 5);
  v10 = *(_QWORD *)(v4 + 16);
  v11 = *(_QWORD *)(v4 + 24);
  v12 = *(_DWORD *)(v6 + 180);
  v13 = *(_DWORD *)(v10 + 180);
  if ( !v11 )
    v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v10 + 48) + 24LL))(*(_QWORD *)(v10 + 48));
  *((_QWORD *)this + 35) = v11;
  *(struct tagRECT *)((char *)this + 168) = *a2;
  *(struct tagRECT *)((char *)this + 184) = *a3;
  v14 = v12 & 0x8000000;
  if ( v14 && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 15) + 120LL))(*((_QWORD *)this + 15)) )
  {
    *((_DWORD *)this + 56) = dword_1800A3EC0;
    v15 = dword_1800A3EC4;
  }
  else
  {
    *((_DWORD *)this + 56) = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 48) + 224LL))(
                               *(_QWORD *)(v6 + 48),
                               5);
    v15 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v6 + 48) + 224LL))(*(_QWORD *)(v6 + 48), 8);
  }
  v16 = *((_DWORD *)this + 56);
  v17 = (HDC)*((_QWORD *)this + 35);
  *((_DWORD *)this + 59) = v15;
  SetBkColor(v17, v16);
  *((_DWORD *)this + 72) &= ~2u;
  v18 = v13 & 0x400;
  *((_DWORD *)this + 60) = *((_DWORD *)this + 56);
  *((_DWORD *)this + 72) |= v18 == 0 ? 2 : 0;
  v19 = *((_QWORD *)this + 15);
  if ( *(_QWORD *)(v19 + 24) && *(_DWORD *)(v19 + 32)
    || !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v19 + 112LL))(v19) )
  {
    *((_DWORD *)this + 72) &= 0xFFFFFFBD;
    if ( !v18 )
      ExtTextOutA(*((HDC *)this + 35), 0, 0, 2u, a3, 0, 0, 0);
  }
  SetTextAlign(*((HDC *)this + 35), 0);
  SetBkMode(*((HDC *)this + 35), 1);
  *((_DWORD *)this + 72) &= ~0x20u;
  if ( !a4 )
    goto LABEL_27;
  if ( !v14 )
  {
    CurrentObject = (HPALETTE)GetCurrentObject(*((HDC *)this + 35), 5u);
    goto LABEL_18;
  }
  if ( (*(_DWORD *)(v6 + 180) & 0x2000000) != 0 )
  {
    CurrentObject = (HPALETTE)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v6 + 48) + 360LL))(*(_QWORD *)(v6 + 48));
LABEL_18:
    v21 = CurrentObject;
    goto LABEL_19;
  }
  v21 = 0;
LABEL_19:
  v22 = (HDC)*((_QWORD *)this + 35);
  v23 = (HDC *)((char *)this + 248);
  v24 = *((_DWORD *)this + 56);
  v25 = *((_DWORD *)this + 48);
  v26 = *((_DWORD *)this + 46);
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  CompatibleDC = CreateCompatibleDC(v22);
  *((_QWORD *)this + 31) = CompatibleDC;
  if ( CompatibleDC )
  {
    CompatibleBitmap = CreateCompatibleBitmap(v22, v25 - v26, a4);
    *((_QWORD *)this + 33) = CompatibleBitmap;
    if ( CompatibleBitmap )
    {
      v29 = SelectObject(*v23, CompatibleBitmap);
      *((_QWORD *)this + 32) = v29;
      if ( v29 )
      {
        if ( SetBkColor(*v23, v24) != -1 && *v23 )
        {
          if ( v21 )
          {
            v30 = SelectPalette(*v23, v21, 1);
            v31 = *v23;
            *((_QWORD *)this + 34) = v30;
            RealizePalette(v31);
          }
          *((_DWORD *)this + 72) |= 0x20u;
LABEL_27:
          *((_DWORD *)this + 72) ^= ((unsigned __int16)*((_DWORD *)this + 72)
                                   ^ (unsigned __int16)((unsigned __int16)CW32System::IsEnhancedMetafileDC(*((HDC *)this + 35)) << 8))
                                  & 0x100;
          return 1;
        }
      }
    }
  }
  COffScreenDC::FreeData((CRenderer *)((char *)this + 248));
  return 0;
}

```

## disassembly

```asm
0x1800337ac  push    rbx
0x1800337ae  push    rbp
0x1800337af  push    rsi
0x1800337b0  push    rdi
0x1800337b1  push    r12
0x1800337b3  push    r13
0x1800337b5  push    r14
0x1800337b7  push    r15
0x1800337b9  sub     rsp, 48h
0x1800337bd  mov     rax, [rcx+78h]
0x1800337c1  mov     rbx, rcx
0x1800337c4  mov     rdi, [rcx+28h]
0x1800337c8  xor     r12d, r12d
0x1800337cb  mov     r13d, r9d
0x1800337ce  mov     r14, r8
0x1800337d1  mov     r15, rdx
0x1800337d4  mov     rcx, [rax+10h]
0x1800337d8  mov     rax, [rax+18h]
0x1800337dc  mov     ebp, [rdi+0B4h]
0x1800337e2  mov     esi, [rcx+0B4h]
0x1800337e8  test    rax, rax
0x1800337eb  jnz     short loc_1800337FD
0x1800337ed  mov     rcx, [rcx+30h]
0x1800337f1  mov     rax, [rcx]
0x1800337f4  mov     rax, [rax+18h]
0x1800337f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800337fd  mov     [rbx+118h], rax
0x180033804  movups  xmm0, xmmword ptr [r15]
0x180033808  mov     r15d, 5
0x18003380e  movdqu  xmmword ptr [rbx+0A8h], xmm0
0x180033816  movups  xmm1, xmmword ptr [r14]
0x18003381a  movdqu  xmmword ptr [rbx+0B8h], xmm1
0x180033822  and     ebp, 8000000h
0x180033828  jz      short loc_180033852
0x18003382a  mov     rcx, [rbx+78h]
0x18003382e  mov     rax, [rcx]
0x180033831  mov     rax, [rax+78h]
0x180033835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003383a  test    eax, eax
0x18003383c  jz      short loc_180033852
0x18003383e  mov     eax, cs:dword_1800A3EC0
0x180033844  mov     [rbx+0E0h], eax
0x18003384a  mov     eax, cs:dword_1800A3EC4
0x180033850  jmp     short loc_180033886
0x180033852  mov     rcx, [rdi+30h]
0x180033856  mov     edx, r15d
0x180033859  mov     rax, [rcx]
0x18003385c  mov     rax, [rax+0E0h]
0x180033863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033868  mov     [rbx+0E0h], eax
0x18003386e  mov     edx, 8
0x180033873  mov     rcx, [rdi+30h]
0x180033877  mov     rax, [rcx]
0x18003387a  mov     rax, [rax+0E0h]
0x180033881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033886  mov     edx, [rbx+0E0h]; color
0x18003388c  mov     rcx, [rbx+118h]; hdc
0x180033893  mov     [rbx+0ECh], eax
0x180033899  call    cs:__imp_SetBkColor
0x18003389f  and     dword ptr [rbx+120h], 0FFFFFFFDh
0x1800338a6  and     esi, 400h
0x1800338ac  mov     eax, [rbx+0E0h]
0x1800338b2  mov     [rbx+0F0h], eax
0x1800338b8  mov     eax, esi
0x1800338ba  neg     eax
0x1800338bc  sbb     ecx, ecx
0x1800338be  not     ecx
0x1800338c0  and     ecx, 2
0x1800338c3  or      [rbx+120h], ecx
0x1800338c9  mov     rcx, [rbx+78h]
0x1800338cd  cmp     [rcx+18h], r12
0x1800338d1  jz      short loc_1800338D9
0x1800338d3  cmp     [rcx+20h], r12d
0x1800338d7  jnz     short loc_1800338E9
0x1800338d9  mov     rax, [rcx]
0x1800338dc  mov     rax, [rax+70h]
0x1800338e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338e5  test    eax, eax
0x1800338e7  jnz     short loc_18003391E
0x1800338e9  and     dword ptr [rbx+120h], 0FFFFFFBDh
0x1800338f0  test    esi, esi
0x1800338f2  jnz     short loc_18003391E
0x1800338f4  mov     rcx, [rbx+118h]; hdc
0x1800338fb  lea     r9d, [rsi+2]; options
0x1800338ff  mov     [rsp+88h+lpDx], r12; lpDx
0x180033904  xor     r8d, r8d; y
0x180033907  mov     [rsp+88h+c], r12d; c
0x18003390c  xor     edx, edx; x
0x18003390e  mov     [rsp+88h+lpString], r12; lpString
0x180033913  mov     [rsp+88h+lprect], r14; lprect
0x180033918  call    cs:__imp_ExtTextOutA
0x18003391e  mov     rcx, [rbx+118h]; hdc
0x180033925  xor     edx, edx; align
0x180033927  call    cs:__imp_SetTextAlign
0x18003392d  mov     rcx, [rbx+118h]; hdc
0x180033934  mov     edx, 1; mode
0x180033939  call    cs:__imp_SetBkMode
0x18003393f  and     dword ptr [rbx+120h], 0FFFFFFDFh
0x180033946  test    r13d, r13d
0x180033949  jz      loc_180033A45
0x18003394f  test    ebp, ebp
0x180033951  jz      short loc_180033979
0x180033953  test    dword ptr [rdi+0B4h], 2000000h
0x18003395d  jz      short loc_180033974
0x18003395f  mov     rcx, [rdi+30h]
0x180033963  mov     rax, [rcx]
0x180033966  mov     rax, [rax+168h]
0x18003396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033972  jmp     short loc_180033989
0x180033974  mov     rsi, r12
0x180033977  jmp     short loc_18003398C
0x180033979  mov     rcx, [rbx+118h]; hdc
0x180033980  mov     edx, r15d; type
0x180033983  call    cs:__imp_GetCurrentObject
0x180033989  mov     rsi, rax
0x18003398c  mov     r14, [rbx+118h]
0x180033993  lea     rdi, [rbx+0F8h]
0x18003399a  mov     r15d, [rbx+0E0h]
0x1800339a1  xor     eax, eax
0x1800339a3  mov     ebp, [rbx+0C0h]
0x1800339a9  mov     rcx, r14; hdc
0x1800339ac  mov     r12d, [rbx+0B8h]
0x1800339b3  mov     [rdi+8], rax
0x1800339b7  mov     [rdi+10h], rax
0x1800339bb  mov     [rdi+18h], rax
0x1800339bf  call    cs:__imp_CreateCompatibleDC
0x1800339c5  mov     [rdi], rax
0x1800339c8  test    rax, rax
0x1800339cb  jz      loc_180033A7F
0x1800339d1  sub     ebp, r12d
0x1800339d4  mov     r8d, r13d; cy
0x1800339d7  mov     edx, ebp; cx
0x1800339d9  mov     rcx, r14; hdc
0x1800339dc  call    cs:__imp_CreateCompatibleBitmap
0x1800339e2  mov     [rdi+10h], rax
0x1800339e6  test    rax, rax
0x1800339e9  jz      loc_180033A7F
0x1800339ef  mov     rcx, [rdi]; hdc
0x1800339f2  mov     rdx, rax; h
0x1800339f5  call    cs:__imp_SelectObject
0x1800339fb  mov     [rdi+8], rax
0x1800339ff  test    rax, rax
0x180033a02  jz      short loc_180033A7F
0x180033a04  mov     rcx, [rdi]; hdc
0x180033a07  mov     edx, r15d; color
0x180033a0a  call    cs:__imp_SetBkColor
0x180033a10  cmp     eax, 0FFFFFFFFh
0x180033a13  jz      short loc_180033A7F
0x180033a15  mov     rcx, [rdi]; hdc
0x180033a18  test    rcx, rcx
0x180033a1b  jz      short loc_180033A7F
0x180033a1d  test    rsi, rsi
0x180033a20  jz      short loc_180033A3E
0x180033a22  mov     r8d, 1; bForceBkgd
0x180033a28  mov     rdx, rsi; hPal
0x180033a2b  call    cs:__imp_SelectPalette
0x180033a31  mov     rcx, [rdi]; hdc
0x180033a34  mov     [rdi+18h], rax
0x180033a38  call    cs:__imp_RealizePalette
0x180033a3e  or      dword ptr [rbx+120h], 20h
0x180033a45  mov     rcx, [rbx+118h]; hdc
0x180033a4c  call    ?IsEnhancedMetafileDC@CW32System@@SAHPEAUHDC__@@@Z; CW32System::IsEnhancedMetafileDC(HDC__ *)
0x180033a51  mov     ecx, [rbx+120h]
0x180033a57  shl     eax, 8
0x180033a5a  xor     eax, ecx
0x180033a5c  and     eax, 100h
0x180033a61  xor     eax, ecx
0x180033a63  mov     [rbx+120h], eax
0x180033a69  mov     eax, 1
0x180033a6e  add     rsp, 48h
0x180033a72  pop     r15
0x180033a74  pop     r14
0x180033a76  pop     r13
0x180033a78  pop     r12
0x180033a7a  pop     rdi
0x180033a7b  pop     rsi
0x180033a7c  pop     rbp
0x180033a7d  pop     rbx
0x180033a7e  retn
0x180033a7f  mov     rcx, rdi; this
0x180033a82  call    ?FreeData@COffScreenDC@@AEAAXXZ; COffScreenDC::FreeData(void)
0x180033a87  xor     eax, eax
0x180033a89  jmp     short loc_180033A6E
```
