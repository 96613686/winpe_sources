# CRenderer::RenderOutlineSymbol(void)

- ea: `0x180073c50`
- end: `0x180073e6d`
- name: `?RenderOutlineSymbol@CRenderer@@QEAAHXZ`
- size: `541`
- prototype: `__int64 __fastcall(CRenderer *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180006e50`

## callees

- `0x1800064d0`
- `0x180024910`
- `0x180027d38`
- `0x180037620`
- `0x180039ecc`
- `0x18005fce0`
- `0x18005fd44`
- `0x1800739ac`
- `0x180073c50`

## import_xrefs

- `GDI32!DeleteDC` at `0x180073e43`
- `GDI32!DeleteDC` at `0x180073e43`
- `GDI32!StretchBlt` at `0x180073e2e`
- `GDI32!StretchBlt` at `0x180073e2e`
- `GDI32!CreateCompatibleDC` at `0x180073cbf`
- `GDI32!CreateCompatibleDC` at `0x180073cbf`
- `GDI32!SelectObject` at `0x180073d9f`
- `GDI32!SelectObject` at `0x180073e3a`
- `GDI32!SelectObject` at `0x180073d9f`
- `GDI32!SelectObject` at `0x180073e3a`

## pseudocode

```c
__int64 __fastcall CRenderer::RenderOutlineSymbol(CRenderer *this)
{
  int v2; // r13d
  int v3; // r12d
  HDC hdcSrc; // r14
  HGDIOBJ v5; // rdi
  int wSrc; // r15d
  __int64 v7; // rax
  int CchLeft; // eax
  int EOP; // r8d
  __int128 v10; // xmm1
  int v11; // ebx
  HGDIOBJ v12; // rsi
  int hDest; // edi
  int v14; // ebx
  int v15; // r9d
  int v16; // eax
  __int128 v18; // [rsp+60h] [rbp-78h] BYREF
  __int64 v19; // [rsp+70h] [rbp-68h]
  _OWORD v20[6]; // [rsp+78h] [rbp-60h] BYREF
  int v21; // [rsp+E0h] [rbp+8h]
  int v22; // [rsp+E8h] [rbp+10h]

  v2 = CMeasurer::LXtoDX(this, 360 * *(unsigned __int8 *)(*((_QWORD *)this + 18) + 35LL));
  v3 = *((_DWORD *)this + 76);
  v22 = *((_DWORD *)this + 21);
  v21 = *((_DWORD *)this + 77);
  if ( !h && (unsigned int)InitializeOutlineBitmaps() )
    return 0;
  hdcSrc = CreateCompatibleDC(*((HDC *)this + 35));
  if ( !hdcSrc )
    return 0;
  if ( (*(_BYTE *)(*((_QWORD *)this + 18) + 35LL) & 1) != 0 )
  {
    v5 = h;
    wSrc = 4;
  }
  else
  {
    v7 = *((_QWORD *)this + 5);
    v5 = qword_1800A4230;
    wSrc = 10;
    v18 = *((_OWORD *)this + 4);
    v19 = v7;
    CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v18);
    if ( EOP < CchLeft )
    {
      v10 = *((_OWORD *)this + 2);
      v20[0] = *((_OWORD *)this + 1);
      v20[1] = v10;
      EOP = CTxtPtr::FindEOP((CTxtPtr *)v20, 0x3FFFFFFF, 0);
    }
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v18, EOP);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v18) )
    {
      v5 = qword_1800A4238;
    }
    else
    {
      v11 = *(unsigned __int8 *)(*((_QWORD *)this + 18) + 35LL);
      if ( v11 < (int)CPFRunPtr::GetOutlineLevel((CPFRunPtr *)&v18) )
        v5 = qword_1800A4240;
    }
  }
  if ( !v5 )
    return 0;
  v12 = SelectObject(hdcSrc, v5);
  hDest = CDisplay::Zoom(*((CDisplay **)this + 15), wSrc);
  v14 = *((__int16 *)this + 46) - *((__int16 *)this + 47) - hDest;
  v15 = CDisplay::Zoom(*((CDisplay **)this + 15), wSrc);
  v16 = v14 / 2;
  if ( v14 <= 0 )
    v16 = -v14;
  StretchBlt(*((HDC *)this + 35), v3 - v22 + v2, v21 + v16, v15, hDest, hdcSrc, 0, 0, wSrc, wSrc, 0xCC0020u);
  SelectObject(hdcSrc, v12);
  DeleteDC(hdcSrc);
  return 1;
}

```

## disassembly

```asm
0x180073c50  mov     [rsp+arg_10], rbx
0x180073c55  push    rbp
0x180073c56  push    rsi
0x180073c57  push    rdi
0x180073c58  push    r12
0x180073c5a  push    r13
0x180073c5c  push    r14
0x180073c5e  push    r15
0x180073c60  sub     rsp, 0A0h
0x180073c67  mov     rax, [rcx+90h]
0x180073c6e  mov     rbp, rcx
0x180073c71  movzx   edx, byte ptr [rax+23h]
0x180073c75  imul    edx, 168h; int
0x180073c7b  call    ?LXtoDX@CMeasurer@@QEAAJJ@Z; CMeasurer::LXtoDX(long)
0x180073c80  cmp     cs:h, 0
0x180073c88  mov     r13d, eax
0x180073c8b  mov     eax, [rbp+54h]
0x180073c8e  mov     r12d, [rbp+130h]
0x180073c95  mov     [rsp+0D8h+arg_8], eax
0x180073c9c  mov     eax, [rbp+134h]
0x180073ca2  mov     [rsp+0D8h+arg_0], eax
0x180073ca9  jnz     short loc_180073CB8
0x180073cab  call    ?InitializeOutlineBitmaps@@YAJXZ; InitializeOutlineBitmaps(void)
0x180073cb0  test    eax, eax
0x180073cb2  jnz     loc_180073E50
0x180073cb8  mov     rcx, [rbp+118h]; hdc
0x180073cbf  call    cs:__imp_CreateCompatibleDC
0x180073cc5  mov     r14, rax
0x180073cc8  test    rax, rax
0x180073ccb  jz      loc_180073E50
0x180073cd1  mov     rcx, [rbp+90h]
0x180073cd8  test    byte ptr [rcx+23h], 1
0x180073cdc  jz      short loc_180073CF0
0x180073cde  mov     rdi, cs:h
0x180073ce5  mov     r15d, 4
0x180073ceb  jmp     loc_180073D90
0x180073cf0  mov     rax, [rbp+28h]
0x180073cf4  lea     rcx, [rsp+0D8h+var_78]; this
0x180073cf9  movups  xmm0, xmmword ptr [rbp+40h]
0x180073cfd  mov     rdi, cs:qword_1800A4230
0x180073d04  mov     r15d, 0Ah
0x180073d0a  mov     r8d, [rbp+50h]
0x180073d0e  movdqu  [rsp+0D8h+var_78], xmm0
0x180073d14  mov     [rsp+0D8h+var_68], rax
0x180073d19  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x180073d1e  cmp     r8d, eax
0x180073d21  jge     short loc_180073D4D
0x180073d23  movups  xmm0, xmmword ptr [rbp+10h]
0x180073d27  xor     r8d, r8d; int *
0x180073d2a  mov     edx, 3FFFFFFFh; int
0x180073d2f  movups  xmm1, xmmword ptr [rbp+20h]
0x180073d33  lea     rcx, [rsp+0D8h+var_60]; this
0x180073d38  movups  [rsp+0D8h+var_60], xmm0
0x180073d3d  movups  [rsp+0D8h+var_50], xmm1
0x180073d45  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180073d4a  mov     r8d, eax
0x180073d4d  mov     edx, r8d; int
0x180073d50  lea     rcx, [rsp+0D8h+var_78]; this
0x180073d55  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x180073d5a  lea     rcx, [rsp+0D8h+var_78]; this
0x180073d5f  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x180073d64  test    eax, eax
0x180073d66  jz      short loc_180073D71
0x180073d68  mov     rdi, cs:qword_1800A4238
0x180073d6f  jmp     short loc_180073D90
0x180073d71  mov     rax, [rbp+90h]
0x180073d78  lea     rcx, [rsp+0D8h+var_78]; this
0x180073d7d  movzx   ebx, byte ptr [rax+23h]
0x180073d81  call    ?GetOutlineLevel@CPFRunPtr@@QEAAJXZ; CPFRunPtr::GetOutlineLevel(void)
0x180073d86  cmp     ebx, eax
0x180073d88  cmovl   rdi, cs:qword_1800A4240
0x180073d90  test    rdi, rdi
0x180073d93  jz      loc_180073E50
0x180073d99  mov     rdx, rdi; h
0x180073d9c  mov     rcx, r14; hdc
0x180073d9f  call    cs:__imp_SelectObject
0x180073da5  mov     rcx, [rbp+78h]; this
0x180073da9  mov     edx, r15d; int
0x180073dac  mov     rsi, rax
0x180073daf  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180073db4  movsx   ecx, word ptr [rbp+5Eh]
0x180073db8  mov     edx, r15d; int
0x180073dbb  movsx   ebx, word ptr [rbp+5Ch]
0x180073dbf  mov     edi, eax
0x180073dc1  sub     ebx, ecx
0x180073dc3  mov     rcx, [rbp+78h]; this
0x180073dc7  sub     ebx, eax
0x180073dc9  call    ?Zoom@CDisplay@@QEBAJJ@Z; CDisplay::Zoom(long)
0x180073dce  mov     r9d, eax; wDest
0x180073dd1  mov     [rsp+0D8h+rop], 0CC0020h; rop
0x180073dd9  mov     [rsp+0D8h+hSrc], r15d; hSrc
0x180073dde  mov     r8d, 2
0x180073de4  mov     eax, ebx
0x180073de6  mov     [rsp+0D8h+wSrc], r15d; wSrc
0x180073deb  cdq
0x180073dec  mov     [rsp+0D8h+ySrc], 0; ySrc
0x180073df4  idiv    r8d
0x180073df7  mov     ecx, ebx
0x180073df9  mov     [rsp+0D8h+xSrc], 0; xSrc
0x180073e01  neg     ecx
0x180073e03  mov     [rsp+0D8h+hdcSrc], r14; hdcSrc
0x180073e08  test    ebx, ebx
0x180073e0a  mov     [rsp+0D8h+hDest], edi; hDest
0x180073e0e  cmovle  eax, ecx
0x180073e11  sub     r12d, [rsp+0D8h+arg_8]
0x180073e19  add     eax, [rsp+0D8h+arg_0]
0x180073e20  mov     rcx, [rbp+118h]; hdcDest
0x180073e27  mov     r8d, eax; yDest
0x180073e2a  lea     edx, [r12+r13]; xDest
0x180073e2e  call    cs:__imp_StretchBlt
0x180073e34  mov     rdx, rsi; h
0x180073e37  mov     rcx, r14; hdc
0x180073e3a  call    cs:__imp_SelectObject
0x180073e40  mov     rcx, r14; hdc
0x180073e43  call    cs:__imp_DeleteDC
0x180073e49  mov     eax, 1
0x180073e4e  jmp     short loc_180073E52
0x180073e50  xor     eax, eax
0x180073e52  mov     rbx, [rsp+0D8h+arg_10]
0x180073e5a  add     rsp, 0A0h
0x180073e61  pop     r15
0x180073e63  pop     r14
0x180073e65  pop     r13
0x180073e67  pop     r12
0x180073e69  pop     rdi
0x180073e6a  pop     rsi
0x180073e6b  pop     rbp
0x180073e6c  retn
```
