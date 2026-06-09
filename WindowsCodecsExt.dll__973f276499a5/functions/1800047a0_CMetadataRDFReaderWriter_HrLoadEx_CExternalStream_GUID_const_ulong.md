# CMetadataRDFReaderWriter::HrLoadEx(CExternalStream *,_GUID const *,ulong)

- ea: `0x1800047a0`
- end: `0x180004ab3`
- name: `?HrLoadEx@CMetadataRDFReaderWriter@@UEAAJPEAVCExternalStream@@PEBU_GUID@@K@Z`
- size: `787`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *this, struct CExternalStream *llVal, const struct _GUID *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800047a0`
- `0x1800058c0`
- `0x1800058e0`
- `0x1800171c4`
- `0x180032db5`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800047e9`
- `OLEAUT32!__imp_VariantInit` at `0x1800047e9`
- `OLEAUT32!__imp_VariantClear` at `0x18000487c`
- `OLEAUT32!__imp_VariantClear` at `0x18000487c`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::HrLoadEx(
        CMetadataRDFReaderWriter *this,
        struct CExternalStream *llVal,
        const struct _GUID *a3)
{
  CMTALock *v3; // r14
  int v6; // eax
  int v7; // ebx
  int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 *v13; // rsi
  __int64 v14; // rcx
  __int64 v15; // rsi
  __int64 *v16; // [rsp+20h] [rbp-58h] BYREF
  __int64 v17; // [rsp+28h] [rbp-50h] BYREF
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-28h] BYREF
  __int16 v20; // [rsp+B0h] [rbp+38h] BYREF

  v3 = (CMetadataRDFReaderWriter *)((char *)this + 40);
  v20 = 0;
  v16 = 0;
  v17 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *(_OWORD *)&v19.vt = 0;
  CMTALock::Enter((CMetadataRDFReaderWriter *)((char *)this + 40));
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 288LL))(this);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_7;
    goto LABEL_16;
  }
  if ( !llVal )
  {
LABEL_38:
    (*(void (__fastcall **)(CMetadataRDFReaderWriter *, _QWORD))(*(_QWORD *)this + 128LL))(this, 0);
    goto LABEL_7;
  }
  v6 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64 **))(*(_QWORD *)this + 264LL))(this, &v16);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  pvarg.vt = 13;
  if ( !memcmp_0(&IID_IUnknown, &IID_IUnknown, 0x10u) )
  {
    pvarg.llVal = (LONGLONG)llVal;
  }
  else
  {
    v6 = (*(__int64 (__fastcall **)(struct CExternalStream *, GUID *, CY *))(*(_QWORD *)llVal + 32LL))(
           llVal,
           &IID_IUnknown,
           &pvarg.cyVal);
    v7 = v6;
    if ( v6 < 0 )
    {
      pvarg.llVal = 0;
LABEL_6:
      if ( !g_doStackCaptures )
        goto LABEL_7;
      goto LABEL_16;
    }
    llVal = (struct CExternalStream *)pvarg.llVal;
  }
  (*(void (__fastcall **)(struct CExternalStream *))(*(_QWORD *)llVal + 8LL))(llVal);
  v19.pRecInfo = 0;
  v19.vt = 11;
  v10 = *v16;
  v19.iVal = -1;
  v6 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v10 + 640))(v16, L"ProhibitDTD", &v19);
  v7 = v6;
  if ( v6 < 0 )
    goto LABEL_6;
  v11 = *v16;
  v19 = pvarg;
  v7 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int16 *))(v11 + 464))(v16, &v19, &v20);
  if ( v7 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_7;
LABEL_42:
    v9 = v7;
    goto LABEL_17;
  }
  if ( v7 )
  {
    v7 = -2147467259;
    goto LABEL_41;
  }
  if ( v20 != -1 )
  {
    v7 = -2147024809;
LABEL_41:
    if ( !g_doStackCaptures )
      goto LABEL_7;
    goto LABEL_42;
  }
  v6 = (*(__int64 (__fastcall **)(CMetadataRDFReaderWriter *, __int64 *, __int64 *))(*(_QWORD *)this + 360LL))(
         this,
         v16,
         &v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v12 = *((_QWORD *)this + 23);
    v13 = v16;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    *((_QWORD *)this + 23) = v13;
    if ( v13 )
      (*(void (__fastcall **)(__int64 *))(*v13 + 8))(v13);
    v14 = *((_QWORD *)this + 24);
    v15 = v17;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    *((_QWORD *)this + 24) = v15;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    goto LABEL_38;
  }
  if ( g_doStackCaptures )
  {
LABEL_16:
    v9 = v6;
LABEL_17:
    DoStackCapture(v9);
  }
LABEL_7:
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    v17 = 0;
  }
  VariantClear(&pvarg);
  if ( v7 < 0 )
    (*(void (__fastcall **)(CMetadataRDFReaderWriter *))(*(_QWORD *)this + 288LL))(this);
  if ( v3 )
    CMTALock::Leave(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800047a0  push    rbp
0x1800047a2  push    rbx
0x1800047a3  push    rsi
0x1800047a4  push    rdi
0x1800047a5  push    r12
0x1800047a7  push    r14
0x1800047a9  mov     rbp, rsp
0x1800047ac  sub     rsp, 78h
0x1800047b0  xor     eax, eax
0x1800047b2  lea     r14, [rcx+28h]
0x1800047b6  mov     rdi, rcx
0x1800047b9  mov     qword ptr [rbp+pvarg+10h], rax
0x1800047bd  xorps   xmm0, xmm0
0x1800047c0  mov     [rbp+arg_0], ax
0x1800047c4  xorps   xmm1, xmm1
0x1800047c7  mov     [rbp+var_58], rax
0x1800047cb  mov     rcx, r14; this
0x1800047ce  mov     [rbp+var_50], rax
0x1800047d2  mov     rsi, rdx
0x1800047d5  xor     r12d, r12d
0x1800047d8  movups  xmmword ptr [rbp+pvarg], xmm0
0x1800047dc  movups  [rbp+var_28], xmm1
0x1800047e0  call    ?Enter@CMTALock@@QEAAXXZ; CMTALock::Enter(void)
0x1800047e5  lea     rcx, [rbp+pvarg]; pvarg
0x1800047e9  call    cs:__imp_VariantInit
0x1800047ef  mov     rax, [rdi]
0x1800047f2  mov     rcx, rdi
0x1800047f5  mov     rax, [rax+120h]
0x1800047fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004801  mov     ebx, eax
0x180004803  test    eax, eax
0x180004805  jns     short loc_180004818
0x180004807  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000480e  jnz     loc_1800048A6
0x180004814  test    eax, eax
0x180004816  js      short loc_180004846
0x180004818  test    rsi, rsi
0x18000481b  jz      loc_180004A35
0x180004821  mov     rax, [rdi]
0x180004824  lea     rdx, [rbp+var_58]
0x180004828  mov     rcx, rdi
0x18000482b  mov     rax, [rax+108h]
0x180004832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004837  mov     ebx, eax
0x180004839  test    eax, eax
0x18000483b  jns     short loc_1800048AF
0x18000483d  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x180004844  jnz     short loc_1800048A6
0x180004846  mov     rcx, [rbp+var_58]
0x18000484a  test    rcx, rcx
0x18000484d  jz      short loc_18000485F
0x18000484f  mov     rax, [rcx]
0x180004852  mov     rax, [rax+10h]
0x180004856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000485b  mov     [rbp+var_58], r12
0x18000485f  mov     rcx, [rbp+var_50]
0x180004863  test    rcx, rcx
0x180004866  jz      short loc_180004878
0x180004868  mov     rax, [rcx]
0x18000486b  mov     rax, [rax+10h]
0x18000486f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004874  mov     [rbp+var_50], r12
0x180004878  lea     rcx, [rbp+pvarg]; pvarg
0x18000487c  call    cs:__imp_VariantClear
0x180004882  test    ebx, ebx
0x180004884  js      loc_180004A9C
0x18000488a  test    r14, r14
0x18000488d  jz      short loc_180004897
0x18000488f  mov     rcx, r14; this
0x180004892  call    ?Leave@CMTALock@@QEAAXXZ; CMTALock::Leave(void)
0x180004897  mov     eax, ebx
0x180004899  add     rsp, 78h
0x18000489d  pop     r14
0x18000489f  pop     r12
0x1800048a1  pop     rdi
0x1800048a2  pop     rsi
0x1800048a3  pop     rbx
0x1800048a4  pop     rbp
0x1800048a5  retn
0x1800048a6  mov     ecx, eax; int
0x1800048a8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800048ad  jmp     short loc_180004846
0x1800048af  mov     eax, 0Dh
0x1800048b4  lea     rbx, IID_IUnknown
0x1800048bb  mov     rdx, rbx; Buf2
0x1800048be  mov     word ptr [rbp+pvarg], ax
0x1800048c2  mov     rcx, rbx; Buf1
0x1800048c5  lea     r8d, [rax+3]; Size
0x1800048c9  call    memcmp_0
0x1800048ce  test    eax, eax
0x1800048d0  jz      loc_180004A4E
0x1800048d6  mov     rax, [rsi]
0x1800048d9  lea     r8, [rbp+pvarg+8]
0x1800048dd  mov     rdx, rbx
0x1800048e0  mov     rcx, rsi
0x1800048e3  mov     rax, [rax+20h]
0x1800048e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ec  mov     ebx, eax
0x1800048ee  test    eax, eax
0x1800048f0  js      loc_180004A57
0x1800048f6  mov     rsi, qword ptr [rbp+pvarg+8]
0x1800048fa  mov     rax, [rsi]
0x1800048fd  mov     rcx, rsi
0x180004900  mov     rax, [rax+8]
0x180004904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004909  mov     rcx, [rbp+var_58]
0x18000490d  lea     r8, [rbp+var_28]
0x180004911  mov     eax, 0Bh
0x180004916  mov     [rbp+var_18], r12
0x18000491a  mov     word ptr [rbp+var_28], ax
0x18000491e  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x180004925  or      esi, 0FFFFFFFFh
0x180004928  mov     rax, [rcx]
0x18000492b  mov     word ptr [rbp+var_28+8], si
0x18000492f  movups  xmm0, [rbp+var_28]
0x180004933  mov     rax, [rax+280h]
0x18000493a  movaps  [rbp+var_28], xmm0
0x18000493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004943  mov     ebx, eax
0x180004945  test    eax, eax
0x180004947  js      loc_18000483D
0x18000494d  mov     rcx, [rbp+var_58]
0x180004951  lea     r8, [rbp+arg_0]
0x180004955  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180004959  lea     rdx, [rbp+var_28]
0x18000495d  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180004962  mov     rax, [rcx]
0x180004965  movaps  [rbp+var_28], xmm0
0x180004969  movsd   [rbp+var_18], xmm1
0x18000496e  mov     rax, [rax+1D0h]
0x180004975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497a  mov     ebx, eax
0x18000497c  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180004982  test    ebx, ebx
0x180004984  jns     short loc_180004996
0x180004986  test    eax, eax
0x180004988  jnz     loc_180004A76
0x18000498e  test    ebx, ebx
0x180004990  js      loc_180004846
0x180004996  jnz     loc_180004A7D
0x18000499c  cmp     [rbp+arg_0], si
0x1800049a0  jnz     loc_180004A84
0x1800049a6  mov     rax, [rdi]
0x1800049a9  lea     r8, [rbp+var_50]
0x1800049ad  mov     rdx, [rbp+var_58]
0x1800049b1  mov     rcx, rdi
0x1800049b4  mov     rax, [rax+168h]
0x1800049bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049c0  mov     ebx, eax
0x1800049c2  test    eax, eax
0x1800049c4  jns     short loc_1800049DB
0x1800049c6  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x1800049cd  jnz     loc_1800048A6
0x1800049d3  test    eax, eax
0x1800049d5  js      loc_180004846
0x1800049db  mov     rcx, [rdi+0B8h]
0x1800049e2  mov     rsi, [rbp+var_58]
0x1800049e6  test    rcx, rcx
0x1800049e9  jnz     loc_180004A8B
0x1800049ef  mov     [rdi+0B8h], rsi
0x1800049f6  test    rsi, rsi
0x1800049f9  jz      short loc_180004A0A
0x1800049fb  mov     rax, [rsi]
0x1800049fe  mov     rcx, rsi
0x180004a01  mov     rax, [rax+8]
0x180004a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0a  mov     rcx, [rdi+0C0h]
0x180004a11  mov     rsi, [rbp+var_50]
0x180004a15  test    rcx, rcx
0x180004a18  jnz     short loc_180004A60
0x180004a1a  mov     [rdi+0C0h], rsi
0x180004a21  test    rsi, rsi
0x180004a24  jz      short loc_180004A35
0x180004a26  mov     rax, [rsi]
0x180004a29  mov     rcx, rsi
0x180004a2c  mov     rax, [rax+8]
0x180004a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a35  mov     rax, [rdi]
0x180004a38  xor     edx, edx
0x180004a3a  mov     rcx, rdi
0x180004a3d  mov     rax, [rax+80h]
0x180004a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a49  jmp     loc_180004846
0x180004a4e  mov     qword ptr [rbp+pvarg+8], rsi
0x180004a52  jmp     loc_1800048FA
0x180004a57  mov     qword ptr [rbp+pvarg+8], r12
0x180004a5b  jmp     loc_18000483D
0x180004a60  mov     rax, [rcx]
0x180004a63  mov     rax, [rax+10h]
0x180004a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6c  jmp     short loc_180004A1A
0x180004a6e  test    eax, eax
0x180004a70  jz      loc_180004846
0x180004a76  mov     ecx, ebx
0x180004a78  jmp     loc_1800048A8
0x180004a7d  mov     ebx, 80004005h
0x180004a82  jmp     short loc_180004A6E
0x180004a84  mov     ebx, 80070057h
0x180004a89  jmp     short loc_180004A6E
0x180004a8b  mov     rax, [rcx]
0x180004a8e  mov     rax, [rax+10h]
0x180004a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a97  jmp     loc_1800049EF
0x180004a9c  mov     rdx, [rdi]
0x180004a9f  mov     rcx, rdi
0x180004aa2  mov     rax, [rdx+120h]
0x180004aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aae  jmp     loc_18000488A
```
