# InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkStrokeDisp(InkML::InkMethods<InkML::InkData> const &,IInkDisp *,Ofc::TCntPtr<IInkStrokeDisp> &)

- ea: `0x180266ad4`
- end: `0x180266d73`
- name: `?CreateInkStrokeDisp@?$InkTraceMethods@VInkTraceData@InkML@@@InkML@@QEBAXAEBV?$InkMethods@VInkData@InkML@@@2@PEAUIInkDisp@@AEAV?$TCntPtr@UIInkStrokeDisp@@@Ofc@@@Z`
- size: `671`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1802668ec`

## callees

- `0x180065980`
- `0x180071720`
- `0x1801b09dc`
- `0x180266ad4`
- `0x18033eb68`
- `0x18033eef0`
- `0x18035edb0`
- `0x180a2e10a`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266ce2`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266cf0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266d49`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266d57`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266ce2`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266cf0`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266d49`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180266d57`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180266cb8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180266cb8`
- `OLEAUT32!__imp_VariantInit` at `0x180266b20`
- `OLEAUT32!__imp_VariantInit` at `0x180266b64`
- `OLEAUT32!__imp_VariantInit` at `0x180266b20`
- `OLEAUT32!__imp_VariantInit` at `0x180266b64`
- `OLEAUT32!__imp_VariantClear` at `0x180266c97`
- `OLEAUT32!__imp_VariantClear` at `0x180266ca5`
- `OLEAUT32!__imp_VariantClear` at `0x180266d25`
- `OLEAUT32!__imp_VariantClear` at `0x180266d33`
- `OLEAUT32!__imp_VariantClear` at `0x180266c97`
- `OLEAUT32!__imp_VariantClear` at `0x180266ca5`
- `OLEAUT32!__imp_VariantClear` at `0x180266d25`
- `OLEAUT32!__imp_VariantClear` at `0x180266d33`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180266b7f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180266b7f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180266b98`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180266b98`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180266bbf`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180266bbf`

## pseudocode

```c
void __fastcall InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkStrokeDisp(
        __int64 a1,
        char *a2,
        __int64 *a3,
        Dr **a4)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  __int64 v10; // rax
  int v11; // ebx
  __int64 v12; // rax
  struct IInkStrokeDisp *v13; // rdx
  bool v14; // zf
  Dr *v15; // rcx
  HRESULT v16; // eax
  HRESULT v17; // eax
  void *v18; // rdx
  HRESULT v19; // eax
  HRESULT v20; // eax
  unsigned __int64 v21; // [rsp+38h] [rbp-59h] BYREF
  __int64 v22; // [rsp+40h] [rbp-51h] BYREF
  void *Src; // [rsp+48h] [rbp-49h] BYREF
  ULONG v24; // [rsp+50h] [rbp-41h]
  unsigned int v25; // [rsp+54h] [rbp-3Dh]
  unsigned int v26; // [rsp+58h] [rbp-39h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-31h] BYREF
  void *ppvData; // [rsp+68h] [rbp-29h] BYREF
  VARIANTARG v29; // [rsp+70h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-9h] BYREF
  VARIANTARG v31; // [rsp+A8h] [rbp+17h] BYREF
  VARIANTARG v32; // [rsp+C8h] [rbp+37h] BYREF

  Src = 0;
  v24 = 0;
  v25 = 0x80000000;
  v26 = 0;
  VariantInit(&pvarg);
  v21 = 0;
  InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkProps(a1, a2, (__int64)&Src, &v26, &pvarg, &v21);
  rgsabound.lLbound = 0;
  rgsabound.cElements = v24;
  VariantInit(&v29);
  v29.vt = 8195;
  v29.llVal = (LONGLONG)SafeArrayCreate(3u, 1u, &rgsabound);
  ppvData = 0;
  v8 = SafeArrayAccessData(v29.parray, &ppvData);
  if ( v8 < 0 )
  {
LABEL_18:
    Ofc::CHResultException::ThrowTag(v8, 0x1E19660Eu);
    __debugbreak();
  }
  memcpy_0(ppvData, Src, 4LL * v24);
  v9 = SafeArrayUnaccessData(v29.parray);
  if ( v9 < 0 )
  {
    Ofc::CHResultException::ThrowTag(v9, 0x1E19660Du);
    __debugbreak();
  }
  v10 = *a3;
  v31 = pvarg;
  v32 = v29;
  v11 = -2147024809;
  if ( (*(unsigned int (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, Dr **))(v10 + 216))(a3, &v32, &v31, a4) == -2147024809 )
    goto LABEL_21;
  v12 = 100 * (int)floor_0(*(double *)(a1 + 48) * 100.0);
  v14 = v12 + v21 == 0;
  v21 += v12;
  v15 = *a4;
  if ( v14 )
  {
    v11 = Dr::SetStrokeTimestamp(v15, v13);
    goto LABEL_10;
  }
  if ( !v15 )
    goto LABEL_10;
  v22 = 0;
  v11 = (*(__int64 (__fastcall **)(Dr *, __int64 *))(*(_QWORD *)v15 + 96LL))(v15, &v22);
  if ( v11 >= 0 )
    goto LABEL_26;
  while ( 1 )
  {
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
LABEL_10:
    if ( v11 >= 0 )
      break;
    Ofc::CHResultException::ThrowTag(v11, 0x1E19660Cu);
LABEL_21:
    v19 = VariantClear(&v29);
    if ( v19 < 0 )
    {
      CrashWithRecoveryHrTag(v19, 0x1F7A008Du);
    }
    else
    {
      v20 = VariantClear(&pvarg);
      if ( v20 >= 0 )
        goto LABEL_13;
    }
    CrashWithRecoveryHrTag(v20, 0x1F7A008Du);
LABEL_26:
    v11 = sub_18033EB68(v22, &v21);
  }
  v16 = VariantClear(&v29);
  if ( v16 < 0 )
  {
    CrashWithRecoveryHrTag(v16, 0x1F7A008Du);
    goto LABEL_17;
  }
  v17 = VariantClear(&pvarg);
  if ( v17 < 0 )
  {
LABEL_17:
    CrashWithRecoveryHrTag(v17, 0x1F7A008Du);
    goto LABEL_18;
  }
LABEL_13:
  if ( Src )
    Mso::Memory::Free((Mso::Memory *)Src, v18);
}

```

## disassembly

```asm
0x180266ad4  mov     rax, rsp
0x180266ad7  mov     [rax+8], rbx
0x180266adb  mov     [rax+10h], rsi
0x180266adf  mov     [rax+18h], rdi
0x180266ae3  mov     [rax+20h], r14
0x180266ae7  push    rbp
0x180266ae8  lea     rbp, [rax-5Fh]
0x180266aec  sub     rsp, 0E0h
0x180266af3  mov     rdi, r9
0x180266af6  mov     rsi, r8
0x180266af9  mov     rbx, rdx
0x180266afc  mov     r14, rcx
0x180266aff  mov     [rbp+57h+Src], 0
0x180266b07  mov     [rbp+57h+var_98], 0
0x180266b0e  mov     [rbp+57h+var_94], 80000000h
0x180266b15  mov     [rbp+57h+var_90], 0
0x180266b1c  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180266b20  call    cs:__imp_VariantInit
0x180266b26  mov     [rbp+57h+var_B0], 0
0x180266b2e  lea     rax, [rbp+57h+var_B0]
0x180266b32  mov     [rsp+0E0h+var_B8], rax
0x180266b37  lea     rax, [rbp+57h+pvarg]
0x180266b3b  mov     [rsp+0E0h+var_C0], rax
0x180266b40  lea     r9, [rbp+57h+var_90]
0x180266b44  lea     r8, [rbp+57h+Src]
0x180266b48  mov     rdx, rbx
0x180266b4b  mov     rcx, r14
0x180266b4e  call    ?CreateInkProps@?$InkTraceMethods@VInkTraceData@InkML@@@InkML@@AEBAXAEBV?$InkMethods@VInkData@InkML@@@2@AEAV?$TArray@H@Ofc@@AEAKAEAVVariantHolder@Mso@@PEA_K@Z; InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkProps(InkML::InkMethods<InkML::InkData> const &,Ofc::TArray<int> &,ulong &,Mso::VariantHolder &,unsigned __int64 *)
0x180266b53  mov     [rbp+57h+rgsabound.lLbound], 0
0x180266b5a  mov     eax, [rbp+57h+var_98]
0x180266b5d  mov     [rbp+57h+rgsabound.cElements], eax
0x180266b60  lea     rcx, [rbp+57h+var_78]; pvarg
0x180266b64  call    cs:__imp_VariantInit
0x180266b6a  mov     eax, 2003h
0x180266b6f  mov     word ptr [rbp+57h+var_78], ax
0x180266b73  mov     ecx, 3; vt
0x180266b78  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180266b7c  lea     edx, [rcx-2]; cDims
0x180266b7f  call    cs:__imp_SafeArrayCreate
0x180266b85  mov     qword ptr [rbp+57h+var_78+8], rax
0x180266b89  mov     [rbp+57h+ppvData], 0
0x180266b91  lea     rdx, [rbp+57h+ppvData]; ppvData
0x180266b95  mov     rcx, rax; psa
0x180266b98  call    cs:__imp_SafeArrayAccessData
0x180266b9e  test    eax, eax
0x180266ba0  js      loc_180266CF7
0x180266ba6  mov     r8d, [rbp+57h+var_98]
0x180266baa  shl     r8, 2; Size
0x180266bae  mov     rdx, [rbp+57h+Src]; Src
0x180266bb2  mov     rcx, [rbp+57h+ppvData]; void *
0x180266bb6  call    memcpy_0
0x180266bbb  mov     rcx, qword ptr [rbp+57h+var_78+8]; psa
0x180266bbf  call    cs:__imp_SafeArrayUnaccessData
0x180266bc5  test    eax, eax
0x180266bc7  js      loc_180266D04
0x180266bcd  mov     rax, [rsi]
0x180266bd0  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x180266bd4  movaps  [rbp+57h+var_40], xmm0
0x180266bd8  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180266bdd  movsd   [rbp+57h+var_30], xmm1
0x180266be2  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x180266be6  movaps  [rbp+57h+var_20], xmm0
0x180266bea  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x180266bef  movsd   [rbp+57h+var_10], xmm1
0x180266bf4  mov     r9, rdi
0x180266bf7  lea     r8, [rbp+57h+var_40]
0x180266bfb  lea     rdx, [rbp+57h+var_20]
0x180266bff  mov     rcx, rsi
0x180266c02  mov     rax, [rax+0D8h]
0x180266c09  call    cs:__guard_dispatch_icall_fptr
0x180266c0f  mov     ebx, 80070057h
0x180266c14  cmp     eax, ebx
0x180266c16  jz      loc_180266D21
0x180266c1c  movsd   xmm0, qword ptr [r14+30h]
0x180266c22  mulsd   xmm0, cs:__real@4059000000000000; X
0x180266c2a  call    floor_0
0x180266c2f  cvttsd2si eax, xmm0
0x180266c33  imul    eax, 64h ; 'd'
0x180266c36  cdqe
0x180266c38  mov     rcx, [rbp+57h+var_B0]
0x180266c3c  add     rcx, rax
0x180266c3f  mov     [rbp+57h+var_B0], rcx
0x180266c43  mov     rcx, [rdi]; this
0x180266c46  jz      short loc_180266C88
0x180266c48  test    rcx, rcx
0x180266c4b  jz      short loc_180266C8F
0x180266c4d  mov     [rbp+57h+var_A8], 0
0x180266c55  mov     rax, [rcx]
0x180266c58  lea     rdx, [rbp+57h+var_A8]
0x180266c5c  mov     rax, [rax+60h]
0x180266c60  call    cs:__guard_dispatch_icall_fptr
0x180266c66  mov     ebx, eax
0x180266c68  test    eax, eax
0x180266c6a  jns     loc_180266D5E
0x180266c70  mov     rcx, [rbp+57h+var_A8]
0x180266c74  test    rcx, rcx
0x180266c77  jz      short loc_180266C8F
0x180266c79  mov     rax, [rcx]
0x180266c7c  mov     rax, [rax+10h]
0x180266c80  call    cs:__guard_dispatch_icall_fptr
0x180266c86  jmp     short loc_180266C8F
0x180266c88  call    ?SetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@@Z; Dr::SetStrokeTimestamp(IInkStrokeDisp *)
0x180266c8d  mov     ebx, eax
0x180266c8f  test    ebx, ebx
0x180266c91  js      short loc_180266D11
0x180266c93  lea     rcx, [rbp+57h+var_78]; pvarg
0x180266c97  call    cs:__imp_VariantClear
0x180266c9d  test    eax, eax
0x180266c9f  js      short loc_180266CDB
0x180266ca1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180266ca5  call    cs:__imp_VariantClear
0x180266cab  test    eax, eax
0x180266cad  js      short loc_180266CE9
0x180266caf  mov     rcx, [rbp+57h+Src]
0x180266cb3  test    rcx, rcx
0x180266cb6  jz      short loc_180266CBE
0x180266cb8  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x180266cbe  lea     r11, [rsp+0E0h+var_s0]
0x180266cc6  mov     rbx, [r11+10h]
0x180266cca  mov     rsi, [r11+18h]
0x180266cce  mov     rdi, [r11+20h]
0x180266cd2  mov     r14, [r11+28h]
0x180266cd6  mov     rsp, r11
0x180266cd9  pop     rbp
0x180266cda  retn
0x180266cdb  mov     edx, 1F7A008Dh
0x180266ce0  mov     ecx, eax
0x180266ce2  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180266ce8  nop
0x180266ce9  mov     edx, 1F7A008Dh
0x180266cee  mov     ecx, eax
0x180266cf0  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180266cf6  nop
0x180266cf7  mov     edx, 1E19660Eh; unsigned int
0x180266cfc  mov     ecx, eax; int
0x180266cfe  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180266d03  int     3; Trap to Debugger
0x180266d04  mov     edx, 1E19660Dh; unsigned int
0x180266d09  mov     ecx, eax; int
0x180266d0b  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180266d10  int     3; Trap to Debugger
0x180266d11  mov     edx, 1E19660Ch; unsigned int
0x180266d16  mov     ecx, ebx; int
0x180266d18  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180266d1d  nop
0x180266d1e  jmp     short $+2
0x180266d20  nop
0x180266d21  lea     rcx, [rbp+57h+var_78]; pvarg
0x180266d25  call    cs:__imp_VariantClear
0x180266d2b  test    eax, eax
0x180266d2d  js      short loc_180266D42
0x180266d2f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180266d33  call    cs:__imp_VariantClear
0x180266d39  test    eax, eax
0x180266d3b  js      short loc_180266D50
0x180266d3d  jmp     loc_180266CAF
0x180266d42  mov     edx, 1F7A008Dh
0x180266d47  mov     ecx, eax
0x180266d49  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180266d4f  nop
0x180266d50  mov     edx, 1F7A008Dh
0x180266d55  mov     ecx, eax
0x180266d57  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x180266d5d  nop
0x180266d5e  lea     rdx, [rbp+57h+var_B0]
0x180266d62  mov     rcx, [rbp+57h+var_A8]
0x180266d66  call    sub_18033EB68
0x180266d6b  mov     ebx, eax
0x180266d6d  jmp     loc_180266C70
```
