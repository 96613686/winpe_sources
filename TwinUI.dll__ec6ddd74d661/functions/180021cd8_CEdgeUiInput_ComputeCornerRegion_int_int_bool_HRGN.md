# CEdgeUiInput::_ComputeCornerRegion(int,int,bool,HRGN__ * *)

- ea: `0x180021cd8`
- end: `0x1800220de`
- name: `?_ComputeCornerRegion@CEdgeUiInput@@AEAAJHH_NPEAPEAUHRGN__@@@Z`
- size: `1030`
- prototype: `int(CEdgeUiInput *__hidden this, int, int, bool, HRGN *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180022b50`

## callees

- `0x180009dfc`
- `0x180021cd8`
- `0x180142e10`
- `0x1803bb010`

## import_xrefs

- `GDI32!DeleteObject` at `0x180021e9b`
- `GDI32!DeleteObject` at `0x180021f44`
- `GDI32!DeleteObject` at `0x180021f58`
- `GDI32!DeleteObject` at `0x180021e9b`
- `GDI32!DeleteObject` at `0x180021f44`
- `GDI32!DeleteObject` at `0x180021f58`
- `GDI32!CreateRectRgn` at `0x180021e38`
- `GDI32!CreateRectRgn` at `0x180021e5e`
- `GDI32!CreateRectRgn` at `0x180021f09`
- `GDI32!CreateRectRgn` at `0x180021e38`
- `GDI32!CreateRectRgn` at `0x180021e5e`
- `GDI32!CreateRectRgn` at `0x180021f09`
- `GDI32!CombineRgn` at `0x180021e88`
- `GDI32!CombineRgn` at `0x180021f2d`
- `GDI32!CombineRgn` at `0x180021e88`
- `GDI32!CombineRgn` at `0x180021f2d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021de1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021df1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021ff0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022000`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022010`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021de1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021df1`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180021ff0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022000`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022010`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021e19`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021f7d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021fa3`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021fce`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022043`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022068`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022088`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800220b6`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021e19`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021f7d`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021fa3`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180021fce`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022043`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022068`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022088`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x1800220b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CEdgeUiInput::_ComputeCornerRegion(CEdgeUiInput *this, int a2, int a3, char a4, HRGN *a5)
{
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v10)(_QWORD, GUID *, __int64 *); // rbx
  signed int v11; // edi
  int v12; // r8d
  int v13; // edx
  int v14; // r9d
  HRGN RectRgn; // rbx
  HRGN v16; // rax
  HRGN v17; // rsi
  __int64 v18; // rcx
  HRGN v20; // rax
  HRGN v21; // r14
  int v22; // r8d
  int yBottom; // [rsp+20h] [rbp-60h]
  int yBottoma; // [rsp+20h] [rbp-60h]
  int yTop; // [rsp+30h] [rbp-50h] BYREF
  int v26; // [rsp+34h] [rbp-4Ch] BYREF
  int v27; // [rsp+38h] [rbp-48h] BYREF
  int v28; // [rsp+3Ch] [rbp-44h] BYREF
  __int64 v29; // [rsp+40h] [rbp-40h] BYREF
  struct tagRECT v30; // [rsp+48h] [rbp-38h] BYREF
  struct tagRECT v31; // [rsp+58h] [rbp-28h] BYREF
  struct tagRECT rc; // [rsp+68h] [rbp-18h] BYREF

  *a5 = 0;
  rc = 0;
  v31 = 0;
  v30 = 0;
  v29 = 0;
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 2);
  v10 = **v9;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  v11 = v10(v9, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &v29);
  if ( v11 < 0 )
    goto LABEL_15;
  v27 = 0;
  yTop = 0;
  v28 = 0;
  v26 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, int *, int *, int *, int *))(*(_QWORD *)v29 + 24LL))(
          v29,
          &v27,
          &yTop,
          &v28,
          &v26);
  if ( v11 < 0 )
    goto LABEL_15;
  switch ( *((_DWORD *)this + 34) )
  {
    case 4:
      SetRect(&rc, 0, 0, a2, 1);
      yBottoma = a3;
      v22 = yTop;
      if ( !a4 )
      {
LABEL_22:
        SetRect(&v31, 0, v22, 1, yBottoma);
        yBottom = yTop;
        v12 = 0;
LABEL_23:
        v14 = v27;
        v13 = 0;
        goto LABEL_10;
      }
LABEL_24:
      SetRect(&v31, a2 - 1, v22, a2, yBottoma);
      v12 = 0;
      yBottom = yTop;
      goto LABEL_25;
    case 5:
      SetRect(&rc, 0, 0, a2, 1);
      yBottoma = a3;
      v22 = yTop;
      if ( a4 )
        goto LABEL_22;
      goto LABEL_24;
    case 6:
      SetRect(&rc, 0, a3 - 1, a2, a3);
      if ( !a4 )
      {
        SetRect(&v31, 0, 0, 1, v26);
        yBottom = a3;
        v12 = v26;
        goto LABEL_23;
      }
      SetRect(&v31, a2 - 1, 0, a2, v26);
      yBottom = a3;
      v12 = v26;
LABEL_25:
      v13 = v28;
      goto LABEL_9;
  }
  if ( *((_DWORD *)this + 34) != 7 )
  {
    SetRectEmpty(&rc);
    SetRectEmpty(&v31);
    SetRectEmpty(&v30);
    v11 = -2147418113;
    goto LABEL_15;
  }
  SetRectEmpty(&rc);
  SetRectEmpty(&v31);
  v12 = a3 - 20;
  yBottom = a3;
  if ( !a4 )
  {
    v13 = a2 - 20;
LABEL_9:
    v14 = a2;
    goto LABEL_10;
  }
  v13 = 0;
  v14 = 20;
LABEL_10:
  SetRect(&v30, v13, v12, v14, yBottom);
  v11 = -2147024882;
  RectRgn = CreateRectRgn(rc.left, rc.top, rc.right, rc.bottom);
  if ( !RectRgn )
    goto LABEL_20;
  v16 = CreateRectRgn(v31.left, v31.top, v31.right, v31.bottom);
  v17 = v16;
  if ( !v16 )
    goto LABEL_20;
  if ( CombineRgn(RectRgn, RectRgn, v16, 2) )
  {
    v20 = CreateRectRgn(v30.left, v30.top, v30.right, v30.bottom);
    v21 = v20;
    if ( v20 )
    {
      v11 = CombineRgn(RectRgn, RectRgn, v20, 2) == 0 ? 0x8007000E : 0;
      DeleteObject(v21);
    }
  }
  DeleteObject(v17);
  if ( v11 >= 0 )
    *a5 = RectRgn;
  else
LABEL_20:
    DeleteObject(RectRgn);
LABEL_15:
  v18 = v29;
  if ( v29 )
  {
    v29 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180021cd8  mov     [rsp-38h+arg_18], rbx
0x180021cdd  push    rbp
0x180021cde  push    rsi
0x180021cdf  push    rdi
0x180021ce0  push    r12
0x180021ce2  push    r13
0x180021ce4  push    r14
0x180021ce6  push    r15
0x180021ce8  mov     rbp, rsp
0x180021ceb  sub     rsp, 80h
0x180021cf2  mov     rax, cs:__security_cookie
0x180021cf9  xor     rax, rsp
0x180021cfc  mov     [rbp+var_8], rax
0x180021d00  mov     r15b, r9b
0x180021d03  mov     r14d, r8d
0x180021d06  mov     esi, edx
0x180021d08  mov     r13, rcx
0x180021d0b  mov     r12, [rbp+arg_20]
0x180021d0f  mov     qword ptr [r12], 0
0x180021d17  xorps   xmm0, xmm0
0x180021d1a  movdqu  xmmword ptr [rbp+rc.left], xmm0
0x180021d1f  xorps   xmm1, xmm1
0x180021d22  movdqu  xmmword ptr [rbp+var_28.left], xmm1
0x180021d27  movdqu  xmmword ptr [rbp+var_38.left], xmm0
0x180021d2c  mov     [rbp+var_40], 0
0x180021d34  mov     rdi, [rcx+10h]
0x180021d38  mov     rax, [rdi]
0x180021d3b  mov     rbx, [rax]
0x180021d3e  lea     rcx, [rbp+var_40]
0x180021d42  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180021d47  lea     r8, [rbp+var_40]
0x180021d4b  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180021d52  mov     rcx, rdi
0x180021d55  mov     rax, rbx
0x180021d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d5d  mov     edi, eax
0x180021d5f  test    eax, eax
0x180021d61  js      loc_180021EB3
0x180021d67  mov     [rbp+var_48], 0
0x180021d6e  mov     [rbp+yTop], 0
0x180021d75  mov     [rbp+var_44], 0
0x180021d7c  mov     [rbp+var_4C], 0
0x180021d83  mov     rcx, [rbp+var_40]
0x180021d87  mov     rax, [rcx]
0x180021d8a  lea     rdx, [rbp+var_4C]
0x180021d8e  mov     qword ptr [rsp+80h+yBottom], rdx
0x180021d93  lea     r9, [rbp+var_44]
0x180021d97  lea     r8, [rbp+yTop]
0x180021d9b  lea     rdx, [rbp+var_48]
0x180021d9f  mov     rax, [rax+18h]
0x180021da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021da8  mov     edi, eax
0x180021daa  test    eax, eax
0x180021dac  js      loc_180021EB3
0x180021db2  mov     ecx, [r13+88h]
0x180021db9  sub     ecx, 4
0x180021dbc  jz      loc_180021F69
0x180021dc2  sub     ecx, 1
0x180021dc5  jz      loc_1800220A2
0x180021dcb  sub     ecx, 1
0x180021dce  jz      loc_180022031
0x180021dd4  cmp     ecx, 1
0x180021dd7  lea     rcx, [rbp+rc]; lprc
0x180021ddb  jnz     loc_180021FF0
0x180021de1  call    cs:__imp_SetRectEmpty
0x180021de8  nop     dword ptr [rax+rax+00h]
0x180021ded  lea     rcx, [rbp+var_28]; lprc
0x180021df1  call    cs:__imp_SetRectEmpty
0x180021df8  nop     dword ptr [rax+rax+00h]
0x180021dfd  lea     r8d, [r14-14h]; yTop
0x180021e01  mov     [rsp+80h+yBottom], r14d; yBottom
0x180021e06  lea     rcx, [rbp+var_38]; lprc
0x180021e0a  test    r15b, r15b
0x180021e0d  jnz     loc_180022026
0x180021e13  lea     edx, [rsi-14h]; xLeft
0x180021e16  mov     r9d, esi; xRight
0x180021e19  call    cs:__imp_SetRect
0x180021e20  nop     dword ptr [rax+rax+00h]
0x180021e25  mov     edi, 8007000Eh
0x180021e2a  mov     r9d, [rbp+rc.bottom]; y2
0x180021e2e  mov     r8d, [rbp+rc.right]; x2
0x180021e32  mov     edx, [rbp+rc.top]; y1
0x180021e35  mov     ecx, [rbp+rc.left]; x1
0x180021e38  call    cs:__imp_CreateRectRgn
0x180021e3f  nop     dword ptr [rax+rax+00h]
0x180021e44  mov     rbx, rax
0x180021e47  test    rax, rax
0x180021e4a  jz      loc_180021F55
0x180021e50  mov     r9d, [rbp+var_28.bottom]; y2
0x180021e54  mov     r8d, [rbp+var_28.right]; x2
0x180021e58  mov     edx, [rbp+var_28.top]; y1
0x180021e5b  mov     ecx, [rbp+var_28.left]; x1
0x180021e5e  call    cs:__imp_CreateRectRgn
0x180021e65  nop     dword ptr [rax+rax+00h]
0x180021e6a  mov     rsi, rax
0x180021e6d  test    rax, rax
0x180021e70  jz      loc_180021F55
0x180021e76  mov     r15d, 2
0x180021e7c  mov     r9d, r15d; iMode
0x180021e7f  mov     r8, rax; hrgnSrc2
0x180021e82  mov     rdx, rbx; hrgnSrc1
0x180021e85  mov     rcx, rbx; hrgnDst
0x180021e88  call    cs:__imp_CombineRgn
0x180021e8f  nop     dword ptr [rax+rax+00h]
0x180021e94  test    eax, eax
0x180021e96  jnz     short loc_180021EFB
0x180021e98  mov     rcx, rsi; ho
0x180021e9b  call    cs:__imp_DeleteObject
0x180021ea2  nop     dword ptr [rax+rax+00h]
0x180021ea7  test    edi, edi
0x180021ea9  js      loc_180021F55
0x180021eaf  mov     [r12], rbx
0x180021eb3  mov     rcx, [rbp+var_40]
0x180021eb7  test    rcx, rcx
0x180021eba  jz      short loc_180021ED1
0x180021ebc  mov     [rbp+var_40], 0
0x180021ec4  mov     rax, [rcx]
0x180021ec7  mov     rax, [rax+10h]
0x180021ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021ed0  nop
0x180021ed1  mov     eax, edi
0x180021ed3  mov     rcx, [rbp+var_8]
0x180021ed7  xor     rcx, rsp; StackCookie
0x180021eda  call    __security_check_cookie
0x180021edf  mov     rbx, [rsp+80h+arg_18]
0x180021ee7  add     rsp, 80h
0x180021eee  pop     r15
0x180021ef0  pop     r14
0x180021ef2  pop     r13
0x180021ef4  pop     r12
0x180021ef6  pop     rdi
0x180021ef7  pop     rsi
0x180021ef8  pop     rbp
0x180021ef9  retn
0x180021efb  mov     r9d, [rbp+var_38.bottom]; y2
0x180021eff  mov     r8d, [rbp+var_38.right]; x2
0x180021f03  mov     edx, [rbp+var_38.top]; y1
0x180021f06  mov     ecx, [rbp+var_38.left]; x1
0x180021f09  call    cs:__imp_CreateRectRgn
0x180021f10  nop     dword ptr [rax+rax+00h]
0x180021f15  mov     r14, rax
0x180021f18  test    rax, rax
0x180021f1b  jz      loc_180021E98
0x180021f21  mov     r9d, r15d; iMode
0x180021f24  mov     r8, rax; hrgnSrc2
0x180021f27  mov     rdx, rbx; hrgnSrc1
0x180021f2a  mov     rcx, rbx; hrgnDst
0x180021f2d  call    cs:__imp_CombineRgn
0x180021f34  nop     dword ptr [rax+rax+00h]
0x180021f39  neg     eax
0x180021f3b  sbb     ecx, ecx
0x180021f3d  not     ecx
0x180021f3f  and     edi, ecx
0x180021f41  mov     rcx, r14; ho
0x180021f44  call    cs:__imp_DeleteObject
0x180021f4b  nop     dword ptr [rax+rax+00h]
0x180021f50  jmp     loc_180021E98
0x180021f55  mov     rcx, rbx; ho
0x180021f58  call    cs:__imp_DeleteObject
0x180021f5f  nop     dword ptr [rax+rax+00h]
0x180021f64  jmp     loc_180021EB3
0x180021f69  mov     [rsp+80h+yBottom], 1; yBottom
0x180021f71  mov     r9d, esi; xRight
0x180021f74  xor     r8d, r8d; yTop
0x180021f77  xor     edx, edx; xLeft
0x180021f79  lea     rcx, [rbp+rc]; lprc
0x180021f7d  call    cs:__imp_SetRect
0x180021f84  nop     dword ptr [rax+rax+00h]
0x180021f89  mov     [rsp+80h+yBottom], r14d; yBottom
0x180021f8e  mov     r8d, [rbp+yTop]; yTop
0x180021f92  lea     rcx, [rbp+var_28]; lprc
0x180021f96  test    r15b, r15b
0x180021f99  jnz     short loc_180021FC8
0x180021f9b  mov     r9d, 1; xRight
0x180021fa1  xor     edx, edx; xLeft
0x180021fa3  call    cs:__imp_SetRect
0x180021faa  nop     dword ptr [rax+rax+00h]
0x180021faf  mov     eax, [rbp+yTop]
0x180021fb2  mov     [rsp+80h+yBottom], eax
0x180021fb6  xor     r8d, r8d
0x180021fb9  mov     r9d, [rbp+var_48]
0x180021fbd  xor     edx, edx
0x180021fbf  lea     rcx, [rbp+var_38]
0x180021fc3  jmp     loc_180021E19
0x180021fc8  mov     r9d, esi; xRight
0x180021fcb  lea     edx, [rsi-1]; xLeft
0x180021fce  call    cs:__imp_SetRect
0x180021fd5  nop     dword ptr [rax+rax+00h]
0x180021fda  mov     eax, [rbp+yTop]
0x180021fdd  xor     r8d, r8d
0x180021fe0  mov     [rsp+80h+yBottom], eax
0x180021fe4  mov     edx, [rbp+var_44]
0x180021fe7  lea     rcx, [rbp+var_38]
0x180021feb  jmp     loc_180021E16
0x180021ff0  call    cs:__imp_SetRectEmpty
0x180021ff7  nop     dword ptr [rax+rax+00h]
0x180021ffc  lea     rcx, [rbp+var_28]; lprc
0x180022000  call    cs:__imp_SetRectEmpty
0x180022007  nop     dword ptr [rax+rax+00h]
0x18002200c  lea     rcx, [rbp+var_38]; lprc
0x180022010  call    cs:__imp_SetRectEmpty
0x180022017  nop     dword ptr [rax+rax+00h]
0x18002201c  mov     edi, 8000FFFFh
0x180022021  jmp     loc_180021EB3
0x180022026  xor     edx, edx
0x180022028  lea     r9d, [rdx+14h]
0x18002202c  jmp     loc_180021E19
0x180022031  lea     r8d, [r14-1]; yTop
0x180022035  mov     [rsp+80h+yBottom], r14d; yBottom
0x18002203a  mov     r9d, esi; xRight
0x18002203d  xor     edx, edx; xLeft
0x18002203f  lea     rcx, [rbp+rc]; lprc
0x180022043  call    cs:__imp_SetRect
0x18002204a  nop     dword ptr [rax+rax+00h]
0x18002204f  mov     eax, [rbp+var_4C]
0x180022052  xor     r8d, r8d; yTop
0x180022055  lea     rcx, [rbp+var_28]; lprc
0x180022059  mov     [rsp+80h+yBottom], eax; yBottom
0x18002205d  test    r15b, r15b
0x180022060  jnz     short loc_180022082
0x180022062  lea     r9d, [r8+1]; xRight
0x180022066  xor     edx, edx; xLeft
0x180022068  call    cs:__imp_SetRect
0x18002206f  nop     dword ptr [rax+rax+00h]
0x180022074  mov     [rsp+80h+yBottom], r14d
0x180022079  mov     r8d, [rbp+var_4C]
0x18002207d  jmp     loc_180021FB9
0x180022082  lea     edx, [rsi-1]; xLeft
0x180022085  mov     r9d, esi; xRight
0x180022088  call    cs:__imp_SetRect
0x18002208f  nop     dword ptr [rax+rax+00h]
0x180022094  mov     [rsp+80h+yBottom], r14d
0x180022099  mov     r8d, [rbp+var_4C]
0x18002209d  jmp     loc_180021FE4
0x1800220a2  mov     [rsp+80h+yBottom], 1; yBottom
0x1800220aa  mov     r9d, esi; xRight
0x1800220ad  xor     r8d, r8d; yTop
0x1800220b0  xor     edx, edx; xLeft
0x1800220b2  lea     rcx, [rbp+rc]; lprc
0x1800220b6  call    cs:__imp_SetRect
0x1800220bd  nop     dword ptr [rax+rax+00h]
0x1800220c2  mov     [rsp+80h+yBottom], r14d
0x1800220c7  mov     r8d, [rbp+yTop]
0x1800220cb  lea     rcx, [rbp+var_28]
0x1800220cf  test    r15b, r15b
0x1800220d2  jz      loc_180021FC8
0x1800220d8  jmp     loc_180021F9B
```
