# CTxtEdit::MoveSelection(__int64,IUndoBuilder *)

- ea: `0x180049814`
- end: `0x180049c13`
- name: `?MoveSelection@CTxtEdit@@QEAAJ_JPEAVIUndoBuilder@@@Z`
- size: `1023`
- prototype: `__int64 __fastcall(CTxtEdit *__hidden this, __int64, struct IUndoBuilder *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops`

## callers

- `0x18002cfd0`

## callees

- `0x180006610`
- `0x1800165c0`
- `0x1800175d0`
- `0x180017860`
- `0x18001d040`
- `0x1800319c0`
- `0x180031a38`
- `0x1800396fc`
- `0x1800411d4`
- `0x1800490f0`
- `0x180049814`
- `0x180049c1c`
- `0x180049cf4`
- `0x18004a070`
- `0x18004a0c8`
- `0x18006cc4c`
- `0x18006d38c`
- `0x18007204c`
- `0x1800879a0`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CTxtEdit::MoveSelection(CTxtEdit *this, __int64 a2, struct IUndoBuilder *a3)
{
  int *Sel; // rax
  int *v7; // rdi
  unsigned int v8; // r14d
  int Expanded; // eax
  int v10; // eax
  unsigned int v11; // eax
  struct IDataObject *v12; // r12
  unsigned int v13; // ebx
  __int64 v14; // rax
  int v15; // r13d
  int v16; // ebx
  int v17; // eax
  int v18; // edi
  int v19; // ebx
  int v21; // [rsp+40h] [rbp-C0h]
  int v22; // [rsp+40h] [rbp-C0h]
  int v23; // [rsp+40h] [rbp-C0h]
  int v24; // [rsp+44h] [rbp-BCh] BYREF
  int v25; // [rsp+48h] [rbp-B8h]
  struct IDataObject *v26; // [rsp+50h] [rbp-B0h] BYREF
  CDisplay *v27; // [rsp+58h] [rbp-A8h]
  _BYTE v28[40]; // [rsp+60h] [rbp-A0h] BYREF
  int v29; // [rsp+88h] [rbp-78h]
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int128 v31; // [rsp+A8h] [rbp-58h]
  int v32; // [rsp+B8h] [rbp-48h]
  __int16 v33; // [rsp+C2h] [rbp-3Eh]
  __int128 v34; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v35; // [rsp+E0h] [rbp-20h]
  _BYTE v36[160]; // [rsp+F0h] [rbp-10h] BYREF
  int v37; // [rsp+1A0h] [rbp+A0h] BYREF
  int v38; // [rsp+1B8h] [rbp+B8h]

  v27 = (CDisplay *)*((_QWORD *)this + 8);
  CDisplay::Freeze(v27);
  Sel = (int *)CTxtEdit::GetSel(this);
  v7 = Sel;
  if ( Sel )
  {
    v25 = Sel[22];
    v37 = 0;
    v38 = Sel[10];
    v24 = 0;
    v26 = 0;
    CTxtRange::CTxtRange((CTxtRange *)v28, (const struct CTxtRange *)Sel);
    if ( a3 )
      (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a3 + 48LL))(a3);
    v8 = 1;
    CTxtRange::Expander((CTxtRange *)v28, 4, 1, 0, &v24, &v37);
    v35 = v30;
    v34 = v31;
    Expanded = CPFRunPtr::FindExpanded((CPFRunPtr *)&v34);
    if ( Expanded < 0 )
      Expanded = 0x3FFFFFFF;
    v33 |= 1u;
    CTxtRange::Advance((CTxtRange *)v28, Expanded);
    v10 = v29;
    if ( v32 < 0 )
      v10 = v29 - v32;
    v37 = v10;
    if ( a2 > 0 && v10 == *((_DWORD *)this + 68) )
    {
      CTxtEdit::Beep(this);
      CTxtRange::~CTxtRange((CTxtRange *)v28);
    }
    else
    {
      v11 = CLightDTEngine::RangeToDataObject((CTxtEdit *)((char *)this + 96), (struct CTxtRange *)v28, 2, &v26);
      v12 = v26;
      v13 = v11;
      if ( !v11 )
      {
        v14 = *(_QWORD *)v7;
        if ( a2 <= 0 )
          (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(v14 + 264))(v7, 4, 0, 0);
        else
          (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(v14 + 272))(v7, 4, 0, 0);
        v21 = v7[10];
        v13 = (*(__int64 (__fastcall **)(int *, __int64, _QWORD))(*(_QWORD *)v7 + 280LL))(v7, 4, (unsigned int)a2);
        if ( v7[10] == v21 )
        {
          CTxtRange::Set((CTxtRange *)v7, v38, v25);
          CTxtEdit::Beep(this);
        }
        else
        {
          v15 = 0;
          if ( v7[10] >= v21 )
          {
            if ( !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(v7 + 6)) )
            {
              *((_WORD *)v7 + 49) &= ~1u;
              CTxtRange::Advance((CTxtRange *)v7, 0x3FFFFFFF);
              CTxtRange::CTxtRange((CTxtRange *)v36, (const struct CTxtRange *)v7);
              CTxtRange::ReplaceRange(v36, 1, &szCR, a3, 1, 0, 0);
              CTxtRange::Advance((CTxtRange *)v7, 1);
              v15 = 1;
              CTxtRange::~CTxtRange((CTxtRange *)v36);
            }
          }
          else
          {
            (*(void (__fastcall **)(int *, __int64, _QWORD, _QWORD))(*(_QWORD *)v7 + 264LL))(v7, 4, 0, 0);
          }
          v22 = v7[10];
          v13 = CLightDTEngine::PasteDataObjectToRange((CTxtEdit **)this + 12, v12, (struct CTxtRange *)v7, 0, 0, a3, 0);
          if ( !v13 )
          {
            if ( v15 )
            {
              CTxtRange::CTxtRange((CTxtRange *)v36, (const struct CTxtRange *)v7);
              CTxtRange::Delete((CTxtRange *)v36, 1, -1, (int *)&v26);
              CTxtRange::~CTxtRange((CTxtRange *)v36);
            }
            v16 = v7[10];
            CTxtRange::Set((CTxtRange *)v7, v22, 0);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v7, a3);
            CTxtRange::Set((CTxtRange *)v7, v16, 0);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v7, a3);
            v17 = v16 - (v37 - v24);
            v24 = v37 - v24;
            if ( v38 >= v22 )
              v17 = v16;
            v23 = v17;
            CTxtRange::Set((CTxtRange *)v7, v15 + v7[10], v24);
            v18 = v29;
            if ( v32 < 0 )
              v18 = v29 - v32;
            v19 = *((_DWORD *)this + 68);
            CTxtRange::ReplaceRange(v28, 0, 0, a3, 1, 0, 0);
            if ( v18 == v19 )
              CTxtRange::DeleteTerminatingEOP((CTxtRange *)v28, a3);
            CTxtRange::CheckOutlineLevel((CTxtRange *)v28, a3);
            if ( a3 )
              HandleSelectionAEInfo(this, a3, (unsigned int)v38, (unsigned int)v25, v23, v24, 2);
            v13 = 0;
          }
        }
      }
      if ( v12 )
        ((void (__fastcall *)(struct IDataObject *))v12->lpVtbl->Release)(v12);
      CTxtRange::~CTxtRange((CTxtRange *)v28);
      v8 = v13;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CDisplay::Thaw(v27);
  return v8;
}

```

## disassembly

```asm
0x180049814  mov     [rsp-8+arg_8], rbx
0x180049819  push    rbp
0x18004981a  push    rsi
0x18004981b  push    rdi
0x18004981c  push    r12
0x18004981e  push    r13
0x180049820  push    r14
0x180049822  push    r15
0x180049824  lea     rbp, [rsp-60h]
0x180049829  sub     rsp, 160h
0x180049830  mov     rax, [rcx+40h]
0x180049834  mov     r15, rcx
0x180049837  mov     rcx, rax; this
0x18004983a  mov     [rsp+190h+var_138], rax
0x18004983f  mov     rsi, r8
0x180049842  mov     r13, rdx
0x180049845  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18004984a  mov     rcx, r15; this
0x18004984d  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x180049852  xor     ebx, ebx
0x180049854  mov     rdi, rax
0x180049857  test    rax, rax
0x18004985a  jnz     short loc_180049867
0x18004985c  mov     r14d, 8007000Eh
0x180049862  jmp     loc_180049BEB
0x180049867  mov     eax, [rax+58h]
0x18004986a  lea     rcx, [rsp+190h+var_130]; this
0x18004986f  mov     [rsp+190h+var_148], eax
0x180049873  mov     rdx, rdi; struct CTxtRange *
0x180049876  mov     [rbp+90h+arg_0], ebx
0x18004987c  mov     eax, [rdi+28h]
0x18004987f  mov     [rbp+90h+arg_18], eax
0x180049885  mov     [rsp+190h+var_14C], ebx
0x180049889  mov     [rsp+190h+var_140], rbx
0x18004988e  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x180049893  test    rsi, rsi
0x180049896  jz      short loc_1800498A7
0x180049898  mov     rax, [rsi]
0x18004989b  mov     rcx, rsi
0x18004989e  mov     rax, [rax+30h]
0x1800498a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800498a7  xor     r9d, r9d; int *
0x1800498aa  lea     rax, [rbp+90h+arg_0]
0x1800498b1  mov     [rsp+190h+var_168], rax; int *
0x1800498b6  lea     rcx, [rsp+190h+var_130]; this
0x1800498bb  lea     rax, [rsp+190h+var_14C]
0x1800498c0  mov     [rsp+190h+var_170], rax; int *
0x1800498c5  lea     r14d, [r9+1]
0x1800498c9  mov     r8d, r14d; int
0x1800498cc  lea     edx, [r9+4]; int
0x1800498d0  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x1800498d5  movups  xmm0, [rbp+90h+var_E8]
0x1800498d9  mov     rax, [rbp+90h+var_100]
0x1800498dd  lea     rcx, [rbp+90h+var_C0]; this
0x1800498e1  mov     [rbp+90h+var_B0], rax
0x1800498e5  movdqu  [rbp+90h+var_C0], xmm0
0x1800498ea  call    ?FindExpanded@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpanded(void)
0x1800498ef  test    eax, eax
0x1800498f1  mov     ecx, 3FFFFFFFh
0x1800498f6  cmovs   eax, ecx
0x1800498f9  or      [rbp+90h+var_CE], r14w
0x1800498fe  mov     edx, eax; int
0x180049900  lea     rcx, [rsp+190h+var_130]; this
0x180049905  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18004990a  mov     ecx, [rbp+90h+var_D8]
0x18004990d  mov     eax, [rbp+90h+var_108]
0x180049910  test    ecx, ecx
0x180049912  jns     short loc_180049916
0x180049914  sub     eax, ecx
0x180049916  mov     [rbp+90h+arg_0], eax
0x18004991c  test    r13, r13
0x18004991f  jle     short loc_180049941
0x180049921  cmp     eax, [r15+110h]
0x180049928  jnz     short loc_180049941
0x18004992a  mov     rcx, r15; this
0x18004992d  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x180049932  lea     rcx, [rsp+190h+var_130]; this
0x180049937  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x18004993c  jmp     loc_180049BEB
0x180049941  lea     rcx, [r15+60h]; this
0x180049945  mov     r8d, 2; int
0x18004994b  lea     r9, [rsp+190h+var_140]; struct IDataObject **
0x180049950  lea     rdx, [rsp+190h+var_130]; struct CTxtRange *
0x180049955  call    ?RangeToDataObject@CLightDTEngine@@QEAAJPEAVCTxtRange@@JPEAPEAUIDataObject@@@Z; CLightDTEngine::RangeToDataObject(CTxtRange *,long,IDataObject * *)
0x18004995a  mov     r12, [rsp+190h+var_140]
0x18004995f  mov     ebx, eax
0x180049961  test    eax, eax
0x180049963  jnz     loc_180049BC9
0x180049969  mov     rax, [rdi]
0x18004996c  lea     edx, [rbx+4]
0x18004996f  xor     r9d, r9d
0x180049972  xor     r8d, r8d
0x180049975  mov     rcx, rdi
0x180049978  test    r13, r13
0x18004997b  jle     short loc_180049986
0x18004997d  mov     rax, [rax+110h]
0x180049984  jmp     short loc_18004998D
0x180049986  mov     rax, [rax+108h]
0x18004998d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049992  mov     eax, [rdi+28h]
0x180049995  xor     r9d, r9d
0x180049998  mov     [rsp+190h+var_150], eax
0x18004999c  mov     r8d, r13d
0x18004999f  mov     rax, [rdi]
0x1800499a2  mov     rcx, rdi
0x1800499a5  lea     edx, [r9+4]
0x1800499a9  mov     rax, [rax+118h]
0x1800499b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800499b5  mov     ebx, eax
0x1800499b7  mov     eax, [rsp+190h+var_150]
0x1800499bb  cmp     [rdi+28h], eax
0x1800499be  jnz     short loc_1800499E0
0x1800499c0  mov     r8d, [rsp+190h+var_148]; int
0x1800499c5  mov     rcx, rdi; this
0x1800499c8  mov     edx, [rbp+90h+arg_18]; int
0x1800499ce  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x1800499d3  mov     rcx, r15; this
0x1800499d6  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x1800499db  jmp     loc_180049BC9
0x1800499e0  xor     ebx, ebx
0x1800499e2  mov     r13d, ebx
0x1800499e5  cmp     [rdi+28h], eax
0x1800499e8  jge     short loc_180049A07
0x1800499ea  mov     rax, [rdi]
0x1800499ed  lea     edx, [rbx+4]
0x1800499f0  xor     r9d, r9d
0x1800499f3  xor     r8d, r8d
0x1800499f6  mov     rcx, rdi
0x1800499f9  mov     rax, [rax+108h]
0x180049a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a05  jmp     short loc_180049A71
0x180049a07  lea     rcx, [rdi+18h]; this
0x180049a0b  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x180049a10  test    eax, eax
0x180049a12  jnz     short loc_180049A71
0x180049a14  mov     eax, 0FFFEh
0x180049a19  mov     edx, 3FFFFFFFh; int
0x180049a1e  and     [rdi+62h], ax
0x180049a22  mov     rcx, rdi; this
0x180049a25  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x180049a2a  mov     rdx, rdi; struct CTxtRange *
0x180049a2d  lea     rcx, [rbp+90h+var_A0]; this
0x180049a31  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x180049a36  mov     [rsp+190h+var_160], ebx
0x180049a3a  lea     r8, ?szCR@@3QBGB; ushort const near * const szCR
0x180049a41  mov     [rsp+190h+var_168], rbx
0x180049a46  lea     rcx, [rbp+90h+var_A0]
0x180049a4a  mov     r9, rsi
0x180049a4d  mov     dword ptr [rsp+190h+var_170], r14d
0x180049a52  mov     edx, r14d
0x180049a55  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x180049a5a  mov     edx, r14d; int
0x180049a5d  mov     rcx, rdi; this
0x180049a60  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x180049a65  lea     rcx, [rbp+90h+var_A0]; this
0x180049a69  mov     r13d, r14d
0x180049a6c  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x180049a71  mov     eax, [rdi+28h]
0x180049a74  lea     rcx, [r15+60h]; this
0x180049a78  mov     [rsp+190h+var_160], ebx; unsigned int
0x180049a7c  xor     r9d, r9d; unsigned __int16
0x180049a7f  mov     [rsp+190h+var_168], rsi; struct IUndoBuilder *
0x180049a84  mov     r8, rdi; struct CTxtRange *
0x180049a87  mov     rdx, r12; struct IDataObject *
0x180049a8a  mov     [rsp+190h+var_170], rbx; struct _repastespecial *
0x180049a8f  mov     [rsp+190h+var_150], eax
0x180049a93  call    ?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z; CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)
0x180049a98  mov     ebx, eax
0x180049a9a  test    eax, eax
0x180049a9c  jnz     loc_180049BC9
0x180049aa2  test    r13d, r13d
0x180049aa5  jz      short loc_180049AD1
0x180049aa7  mov     rdx, rdi; struct CTxtRange *
0x180049aaa  lea     rcx, [rbp+90h+var_A0]; this
0x180049aae  call    ??0CTxtRange@@QEAA@AEBV0@@Z; CTxtRange::CTxtRange(CTxtRange const &)
0x180049ab3  lea     r9, [rsp+190h+var_140]; int *
0x180049ab8  or      r8d, 0FFFFFFFFh; int
0x180049abc  mov     edx, r14d; int
0x180049abf  lea     rcx, [rbp+90h+var_A0]; this
0x180049ac3  call    ?Delete@CTxtRange@@UEAAJJJPEAJ@Z; CTxtRange::Delete(long,long,long *)
0x180049ac8  lea     rcx, [rbp+90h+var_A0]; this
0x180049acc  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x180049ad1  mov     edx, [rsp+190h+var_150]; int
0x180049ad5  xor     r8d, r8d; int
0x180049ad8  mov     ebx, [rdi+28h]
0x180049adb  mov     rcx, rdi; this
0x180049ade  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180049ae3  mov     rdx, rsi; struct IUndoBuilder *
0x180049ae6  mov     rcx, rdi; this
0x180049ae9  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x180049aee  xor     r8d, r8d; int
0x180049af1  mov     edx, ebx; int
0x180049af3  mov     rcx, rdi; this
0x180049af6  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180049afb  mov     rdx, rsi; struct IUndoBuilder *
0x180049afe  mov     rcx, rdi; this
0x180049b01  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x180049b06  mov     edx, [rsp+190h+var_150]
0x180049b0a  mov     eax, ebx
0x180049b0c  mov     ecx, [rbp+90h+arg_0]
0x180049b12  sub     ecx, [rsp+190h+var_14C]
0x180049b16  sub     eax, ecx
0x180049b18  mov     [rsp+190h+var_14C], ecx
0x180049b1c  cmp     [rbp+90h+arg_18], edx
0x180049b22  mov     r8d, ecx; int
0x180049b25  mov     edx, [rdi+28h]
0x180049b28  mov     rcx, rdi; this
0x180049b2b  cmovge  eax, ebx
0x180049b2e  add     edx, r13d; int
0x180049b31  mov     [rsp+190h+var_150], eax
0x180049b35  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x180049b3a  mov     eax, [rbp+90h+var_D8]
0x180049b3d  mov     edi, [rbp+90h+var_108]
0x180049b40  test    eax, eax
0x180049b42  jns     short loc_180049B46
0x180049b44  sub     edi, eax
0x180049b46  mov     ebx, [r15+110h]
0x180049b4d  lea     rcx, [rsp+190h+var_130]
0x180049b52  mov     [rsp+190h+var_160], 0
0x180049b5a  mov     r9, rsi
0x180049b5d  mov     [rsp+190h+var_168], 0
0x180049b66  xor     r8d, r8d
0x180049b69  xor     edx, edx
0x180049b6b  mov     dword ptr [rsp+190h+var_170], r14d
0x180049b70  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x180049b75  cmp     edi, ebx
0x180049b77  jnz     short loc_180049B86
0x180049b79  mov     rdx, rsi; struct IUndoBuilder *
0x180049b7c  lea     rcx, [rsp+190h+var_130]; this
0x180049b81  call    ?DeleteTerminatingEOP@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::DeleteTerminatingEOP(IUndoBuilder *)
0x180049b86  mov     rdx, rsi; struct IUndoBuilder *
0x180049b89  lea     rcx, [rsp+190h+var_130]; this
0x180049b8e  call    ?CheckOutlineLevel@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::CheckOutlineLevel(IUndoBuilder *)
0x180049b93  test    rsi, rsi
0x180049b96  jz      short loc_180049BC7
0x180049b98  mov     eax, [rsp+190h+var_14C]
0x180049b9c  mov     rdx, rsi
0x180049b9f  mov     r9d, [rsp+190h+var_148]
0x180049ba4  mov     rcx, r15
0x180049ba7  mov     r8d, [rbp+90h+arg_18]
0x180049bae  mov     [rsp+190h+var_160], 2
0x180049bb6  mov     dword ptr [rsp+190h+var_168], eax
0x180049bba  mov     eax, [rsp+190h+var_150]
0x180049bbe  mov     dword ptr [rsp+190h+var_170], eax
0x180049bc2  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x180049bc7  xor     ebx, ebx
0x180049bc9  test    r12, r12
0x180049bcc  jz      short loc_180049BDE
0x180049bce  mov     rax, [r12]
0x180049bd2  mov     rcx, r12
0x180049bd5  mov     rax, [rax+10h]
0x180049bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bde  lea     rcx, [rsp+190h+var_130]; this
0x180049be3  call    ??1CTxtRange@@UEAA@XZ; CTxtRange::~CTxtRange(void)
0x180049be8  mov     r14d, ebx
0x180049beb  mov     rcx, [rsp+190h+var_138]; this
0x180049bf0  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x180049bf5  mov     rbx, [rsp+190h+arg_8]
0x180049bfd  mov     eax, r14d
0x180049c00  add     rsp, 160h
0x180049c07  pop     r15
0x180049c09  pop     r14
0x180049c0b  pop     r13
0x180049c0d  pop     r12
0x180049c0f  pop     rdi
0x180049c10  pop     rsi
0x180049c11  pop     rbp
0x180049c12  retn
```
