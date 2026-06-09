# InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkStrokeDisp(InkML::InkMethods<InkML::InkData> const &,IInkDisp *,Ofc::TCntPtr<IInkStrokeDisp> &)

- ea: `0x18039913c`
- end: `0x1803993c7`
- name: `?CreateInkStrokeDisp@?$InkTraceMethods@VInkTraceData@InkML@@@InkML@@QEBAXAEBV?$InkMethods@VInkData@InkML@@@2@PEAUIInkDisp@@AEAV?$TCntPtr@UIInkStrokeDisp@@@Ofc@@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180398f54`

## callees

- `0x18010cfdd`
- `0x1801420e0`
- `0x180279050`
- `0x1802d56d0`
- `0x18039913c`
- `0x180417c88`
- `0x1804813bc`
- `0x1804816c4`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1803992a7`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1803992c5`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180399378`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180399394`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1803992a7`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x1803992c5`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180399378`
- `Mso20Win32Client!__imp_?CrashWithRecoveryHrTag@@YAXHI@Z` at `0x180399394`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803993a4`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1803993a4`
- `OLEAUT32!__imp_VariantInit` at `0x180399188`
- `OLEAUT32!__imp_VariantInit` at `0x1803991cc`
- `OLEAUT32!__imp_VariantInit` at `0x180399188`
- `OLEAUT32!__imp_VariantInit` at `0x1803991cc`
- `OLEAUT32!__imp_VariantClear` at `0x180399296`
- `OLEAUT32!__imp_VariantClear` at `0x1803992b4`
- `OLEAUT32!__imp_VariantClear` at `0x180399367`
- `OLEAUT32!__imp_VariantClear` at `0x180399383`
- `OLEAUT32!__imp_VariantClear` at `0x180399296`
- `OLEAUT32!__imp_VariantClear` at `0x1803992b4`
- `OLEAUT32!__imp_VariantClear` at `0x180399367`
- `OLEAUT32!__imp_VariantClear` at `0x180399383`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1803991e7`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1803991e7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180399200`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180399200`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180399230`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180399230`

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
  HRESULT v12; // eax
  HRESULT v13; // eax
  void *v14; // rdx
  __int64 v15; // rax
  struct IInkStrokeDisp *v16; // rdx
  bool v17; // zf
  Dr *v18; // rcx
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
  {
    v12 = VariantClear(&v29);
    if ( v12 < 0 )
      CrashWithRecoveryHrTag(v12, 0x1F7A008Du);
    v13 = VariantClear(&pvarg);
    if ( v13 < 0 )
      CrashWithRecoveryHrTag(v13, 0x1F7A008Du);
  }
  else
  {
    v15 = 100 * (int)floor_0(*(double *)(a1 + 48) * 100.0);
    v17 = v15 + v21 == 0;
    v21 += v15;
    v18 = *a4;
    if ( v17 )
    {
      v11 = Dr::SetStrokeTimestamp(v18, v16);
    }
    else if ( v18 )
    {
      v22 = 0;
      v11 = (*(__int64 (__fastcall **)(Dr *, __int64 *))(*(_QWORD *)v18 + 96LL))(v18, &v22);
      if ( v11 >= 0 )
        v11 = sub_1804813BC(v22, &v21);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v11 < 0 )
      Ofc::CHResultException::ThrowTag(v11, 0x1E19660Cu);
    v19 = VariantClear(&v29);
    if ( v19 < 0 )
      CrashWithRecoveryHrTag(v19, 0x1F7A008Du);
    v20 = VariantClear(&pvarg);
    if ( v20 < 0 )
      CrashWithRecoveryHrTag(v20, 0x1F7A008Du);
  }
  if ( Src )
    Mso::Memory::Free((Mso::Memory *)Src, v14);
}

```

## disassembly

```asm
0x18039913c  mov     rax, rsp
0x18039913f  mov     [rax+8], rbx
0x180399143  mov     [rax+10h], rsi
0x180399147  mov     [rax+18h], rdi
0x18039914b  mov     [rax+20h], r14
0x18039914f  push    rbp
0x180399150  lea     rbp, [rax-5Fh]
0x180399154  sub     rsp, 0E0h
0x18039915b  mov     rdi, r9
0x18039915e  mov     rsi, r8
0x180399161  mov     rbx, rdx
0x180399164  mov     r14, rcx
0x180399167  mov     [rbp+57h+Src], 0
0x18039916f  mov     [rbp+57h+var_98], 0
0x180399176  mov     [rbp+57h+var_94], 80000000h
0x18039917d  mov     [rbp+57h+var_90], 0
0x180399184  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180399188  call    cs:__imp_VariantInit
0x18039918e  mov     [rbp+57h+var_B0], 0
0x180399196  lea     rax, [rbp+57h+var_B0]
0x18039919a  mov     [rsp+0E0h+var_B8], rax
0x18039919f  lea     rax, [rbp+57h+pvarg]
0x1803991a3  mov     [rsp+0E0h+var_C0], rax
0x1803991a8  lea     r9, [rbp+57h+var_90]
0x1803991ac  lea     r8, [rbp+57h+Src]
0x1803991b0  mov     rdx, rbx
0x1803991b3  mov     rcx, r14
0x1803991b6  call    ?CreateInkProps@?$InkTraceMethods@VInkTraceData@InkML@@@InkML@@AEBAXAEBV?$InkMethods@VInkData@InkML@@@2@AEAV?$TArray@H@Ofc@@AEAKAEAVVariantHolder@Mso@@PEA_K@Z; InkML::InkTraceMethods<InkML::InkTraceData>::CreateInkProps(InkML::InkMethods<InkML::InkData> const &,Ofc::TArray<int> &,ulong &,Mso::VariantHolder &,unsigned __int64 *)
0x1803991bb  mov     [rbp+57h+rgsabound.lLbound], 0
0x1803991c2  mov     eax, [rbp+57h+var_98]
0x1803991c5  mov     [rbp+57h+rgsabound.cElements], eax
0x1803991c8  lea     rcx, [rbp+57h+var_78]; pvarg
0x1803991cc  call    cs:__imp_VariantInit
0x1803991d2  mov     eax, 2003h
0x1803991d7  mov     word ptr [rbp+57h+var_78], ax
0x1803991db  mov     ecx, 3; vt
0x1803991e0  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1803991e4  lea     edx, [rcx-2]; cDims
0x1803991e7  call    cs:__imp_SafeArrayCreate
0x1803991ed  mov     qword ptr [rbp+57h+var_78+8], rax
0x1803991f1  mov     [rbp+57h+ppvData], 0
0x1803991f9  lea     rdx, [rbp+57h+ppvData]; ppvData
0x1803991fd  mov     rcx, rax; psa
0x180399200  call    cs:__imp_SafeArrayAccessData
0x180399206  test    eax, eax
0x180399208  jns     short loc_180399217
0x18039920a  mov     edx, 1E19660Eh; unsigned int
0x18039920f  mov     ecx, eax; int
0x180399211  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180399216  int     3; Trap to Debugger
0x180399217  mov     r8d, [rbp+57h+var_98]
0x18039921b  shl     r8, 2; Size
0x18039921f  mov     rdx, [rbp+57h+Src]; Src
0x180399223  mov     rcx, [rbp+57h+ppvData]; void *
0x180399227  call    memcpy_0
0x18039922c  mov     rcx, qword ptr [rbp+57h+var_78+8]; psa
0x180399230  call    cs:__imp_SafeArrayUnaccessData
0x180399236  test    eax, eax
0x180399238  jns     short loc_180399247
0x18039923a  mov     edx, 1E19660Dh; unsigned int
0x18039923f  mov     ecx, eax; int
0x180399241  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x180399246  int     3; Trap to Debugger
0x180399247  mov     rax, [rsi]
0x18039924a  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x18039924e  movaps  [rbp+57h+var_40], xmm0
0x180399252  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x180399257  movsd   [rbp+57h+var_30], xmm1
0x18039925c  movups  xmm0, xmmword ptr [rbp+57h+var_78]
0x180399260  movaps  [rbp+57h+var_20], xmm0
0x180399264  movsd   xmm1, qword ptr [rbp+57h+var_78+10h]
0x180399269  movsd   [rbp+57h+var_10], xmm1
0x18039926e  mov     r9, rdi
0x180399271  lea     r8, [rbp+57h+var_40]
0x180399275  lea     rdx, [rbp+57h+var_20]
0x180399279  mov     rcx, rsi
0x18039927c  mov     rax, [rax+0D8h]
0x180399283  call    cs:__guard_dispatch_icall_fptr
0x180399289  mov     ebx, 80070057h
0x18039928e  cmp     eax, ebx
0x180399290  jnz     short loc_1803992D1
0x180399292  lea     rcx, [rbp+57h+var_78]; pvarg
0x180399296  call    cs:__imp_VariantClear
0x18039929c  test    eax, eax
0x18039929e  jns     short loc_1803992B0
0x1803992a0  mov     edx, 1F7A008Dh
0x1803992a5  mov     ecx, eax
0x1803992a7  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x1803992ad  nop
0x1803992ae  xchg    ax, ax
0x1803992b0  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1803992b4  call    cs:__imp_VariantClear
0x1803992ba  test    eax, eax
0x1803992bc  jns     short loc_1803992CC
0x1803992be  mov     edx, 1F7A008Dh
0x1803992c3  mov     ecx, eax
0x1803992c5  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x1803992cb  nop
0x1803992cc  jmp     loc_18039939B
0x1803992d1  movsd   xmm0, qword ptr [r14+30h]
0x1803992d7  mulsd   xmm0, cs:__real@4059000000000000; X
0x1803992df  call    floor_0
0x1803992e4  cvttsd2si eax, xmm0
0x1803992e8  imul    eax, 64h ; 'd'
0x1803992eb  cdqe
0x1803992ed  mov     rcx, [rbp+57h+var_B0]
0x1803992f1  add     rcx, rax
0x1803992f4  mov     [rbp+57h+var_B0], rcx
0x1803992f8  mov     rcx, [rdi]; this
0x1803992fb  jz      short loc_180399348
0x1803992fd  test    rcx, rcx
0x180399300  jz      short loc_18039934F
0x180399302  mov     [rbp+57h+var_A8], 0
0x18039930a  mov     rax, [rcx]
0x18039930d  lea     rdx, [rbp+57h+var_A8]
0x180399311  mov     rax, [rax+60h]
0x180399315  call    cs:__guard_dispatch_icall_fptr
0x18039931b  mov     ebx, eax
0x18039931d  test    eax, eax
0x18039931f  js      short loc_180399330
0x180399321  lea     rdx, [rbp+57h+var_B0]
0x180399325  mov     rcx, [rbp+57h+var_A8]
0x180399329  call    sub_1804813BC
0x18039932e  mov     ebx, eax
0x180399330  mov     rcx, [rbp+57h+var_A8]
0x180399334  test    rcx, rcx
0x180399337  jz      short loc_18039934F
0x180399339  mov     rax, [rcx]
0x18039933c  mov     rax, [rax+10h]
0x180399340  call    cs:__guard_dispatch_icall_fptr
0x180399346  jmp     short loc_18039934F
0x180399348  call    ?SetStrokeTimestamp@Dr@@YAJPEAUIInkStrokeDisp@@@Z; Dr::SetStrokeTimestamp(IInkStrokeDisp *)
0x18039934d  mov     ebx, eax
0x18039934f  test    ebx, ebx
0x180399351  jns     short loc_180399363
0x180399353  mov     edx, 1E19660Ch; unsigned int
0x180399358  mov     ecx, ebx; int
0x18039935a  call    ?ThrowTag@CHResultException@Ofc@@SAXJK@Z; Ofc::CHResultException::ThrowTag(long,ulong)
0x18039935f  nop
0x180399360  jmp     short $+2
0x180399362  nop
0x180399363  lea     rcx, [rbp+57h+var_78]; pvarg
0x180399367  call    cs:__imp_VariantClear
0x18039936d  test    eax, eax
0x18039936f  jns     short loc_18039937F
0x180399371  mov     edx, 1F7A008Dh
0x180399376  mov     ecx, eax
0x180399378  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x18039937e  nop
0x18039937f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180399383  call    cs:__imp_VariantClear
0x180399389  test    eax, eax
0x18039938b  jns     short loc_18039939B
0x18039938d  mov     edx, 1F7A008Dh
0x180399392  mov     ecx, eax
0x180399394  call    cs:__imp_?CrashWithRecoveryHrTag@@YAXHI@Z; CrashWithRecoveryHrTag(int,uint)
0x18039939a  nop
0x18039939b  mov     rcx, [rbp+57h+Src]
0x18039939f  test    rcx, rcx
0x1803993a2  jz      short loc_1803993AA
0x1803993a4  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1803993aa  lea     r11, [rsp+0E0h+var_s0]
0x1803993b2  mov     rbx, [r11+10h]
0x1803993b6  mov     rsi, [r11+18h]
0x1803993ba  mov     rdi, [r11+20h]
0x1803993be  mov     r14, [r11+28h]
0x1803993c2  mov     rsp, r11
0x1803993c5  pop     rbp
0x1803993c6  retn
```
