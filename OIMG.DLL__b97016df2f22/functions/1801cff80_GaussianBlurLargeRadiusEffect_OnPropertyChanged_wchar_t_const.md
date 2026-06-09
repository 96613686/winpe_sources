# GaussianBlurLargeRadiusEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801cff80`
- end: `0x1801d0488`
- name: `?OnPropertyChanged@GaussianBlurLargeRadiusEffect@@UEAAJPEB_W@Z`
- size: `1288`
- prototype: `__int64 __fastcall(GaussianBlurLargeRadiusEffect *__hidden this, PCNZWCH lpString1)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1801cf760`
- `0x1801cff80`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801cffcd`
- `KERNEL32!CompareStringW` at `0x1801cfff8`
- `KERNEL32!CompareStringW` at `0x1801d0023`
- `KERNEL32!CompareStringW` at `0x1801d018c`
- `KERNEL32!CompareStringW` at `0x1801cffcd`
- `KERNEL32!CompareStringW` at `0x1801cfff8`
- `KERNEL32!CompareStringW` at `0x1801d0023`
- `KERNEL32!CompareStringW` at `0x1801d018c`
- `OLEAUT32!__imp_VariantInit` at `0x1801d0046`
- `OLEAUT32!__imp_VariantInit` at `0x1801d01af`
- `OLEAUT32!__imp_VariantInit` at `0x1801d02e0`
- `OLEAUT32!__imp_VariantInit` at `0x1801d0046`
- `OLEAUT32!__imp_VariantInit` at `0x1801d01af`
- `OLEAUT32!__imp_VariantInit` at `0x1801d02e0`
- `OLEAUT32!__imp_VariantClear` at `0x1801d0163`
- `OLEAUT32!__imp_VariantClear` at `0x1801d034f`
- `OLEAUT32!__imp_VariantClear` at `0x1801d0163`
- `OLEAUT32!__imp_VariantClear` at `0x1801d034f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GaussianBlurLargeRadiusEffect::OnPropertyChanged(
        GaussianBlurLargeRadiusEffect *this,
        PCNZWCH lpString1)
{
  int v4; // eax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  float dblVal; // xmm6_4
  int v14; // eax
  __int64 result; // rax
  int v16; // [rsp+30h] [rbp-78h] BYREF
  _DWORD v17[4]; // [rsp+38h] [rbp-70h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-60h] BYREF
  VARIANTARG v19[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 *v20; // [rsp+B8h] [rbp+10h] BYREF

  try
  {
    if ( !lpString1 )
      ATL::BaseAtlThrow(-2147467261);
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Radius", -1) == 2
      || CompareStringW(0x7Fu, 1u, lpString1, -1, L"AppliedRadius", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v12 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
              *((_QWORD *)this + 16),
              L"AppliedRadius",
              &pvarg);
      if ( v12 == -2147024882 || v12 == -2045378032 || v12 == -2045312765 || v12 == -2045247216 )
        ATL::BaseAtlThrow(v12);
      if ( v12 < 0 )
        ATL::BaseAtlThrow(v12);
      dblVal = pvarg.dblVal;
      VariantClear(&pvarg);
      if ( dblVal < 0.0 )
        ATL::BaseAtlThrow(-2147024809);
      if ( GaussianBlurLargeRadiusEffect::GetRadiusProperty(this) < 0.0 )
        ATL::BaseAtlThrow(-2147024809);
      *((_BYTE *)this + 160) = 1;
      goto LABEL_41;
    }
    if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"RatioOfConvolutionWindowToDiameter", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v4 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             L"RatioOfConvolutionWindowToDiameter",
             &pvarg);
      if ( v4 == -2147024882 || v4 == -2045378032 || v4 == -2045312765 || v4 == -2045247216 )
        ATL::BaseAtlThrow(v4);
      if ( v4 < 0 )
        ATL::BaseAtlThrow(v4);
      v20 = 0;
      v5 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"BlurEffectId",
             &v20);
      if ( v5 < 0 )
        ATL::BaseAtlThrow(v5);
      if ( !v20 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
      v6 = *v20;
      v19[0] = pvarg;
      v7 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(v6 + 104))(
             v20,
             L"RatioOfConvolutionWindowToDiameter",
             v19);
      if ( v7 == -2147024882 || v7 == -2045378032 || v7 == -2045312765 || v7 == -2045247216 )
        ATL::BaseAtlThrow(v7);
      if ( v7 < 0 )
        ATL::BaseAtlThrow(v7);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, lpString1, -1, L"Channels", -1) != 2 )
      {
LABEL_41:
        if ( !*((_BYTE *)this + 160) )
        {
          v14 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
          if ( v14 < 0 )
            ATL::BaseAtlThrow(v14);
        }
        return 0;
      }
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v8 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             L"Channels",
             &pvarg);
      if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
        ATL::BaseAtlThrow(v8);
      if ( v8 < 0 )
        ATL::BaseAtlThrow(v8);
      v20 = 0;
      v9 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
             *((_QWORD *)this + 18),
             L"BlurEffectId",
             &v20);
      if ( v9 < 0 )
        ATL::BaseAtlThrow(v9);
      if ( !v20 )
        ATL::BaseAtlThrow(-2045247222);
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
      v10 = *v20;
      v19[0] = pvarg;
      v11 = (*(__int64 (__fastcall **)(__int64 *, const WCHAR *, VARIANTARG *))(v10 + 104))(v20, L"Channels", v19);
      if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
        ATL::BaseAtlThrow(v11);
      if ( v11 < 0 )
        ATL::BaseAtlThrow(v11);
    }
    VariantClear(&pvarg);
    goto LABEL_41;
  }
  catch ( Base::Exception v17 )
  {
    LODWORD(v20) = v17[2];
    goto LABEL_44;
  }
  catch ( long v16 )
  {
    LODWORD(v20) = v16;
LABEL_44:
    result = (unsigned int)v20;
    if ( (_WORD)v20 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801cff80  mov     rax, rsp
0x1801cff83  mov     [rax+8], rbx
0x1801cff87  mov     [rax+18h], rsi
0x1801cff8b  push    rdi
0x1801cff8c  push    r14
0x1801cff8e  push    r15
0x1801cff90  sub     rsp, 90h
0x1801cff97  movaps  xmmword ptr [rax-28h], xmm6
0x1801cff9b  mov     rbx, rdx
0x1801cff9e  mov     r15, rcx
0x1801cffa1  test    rdx, rdx
0x1801cffa4  jz      loc_1801D03DD
0x1801cffaa  or      esi, 0FFFFFFFFh
0x1801cffad  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801cffb1  lea     rax, aRadius; "Radius"
0x1801cffb8  mov     [rsp+0A8h+lpString2], rax; lpString2
0x1801cffbd  mov     r9d, esi; cchCount1
0x1801cffc0  mov     r8, rbx; lpString1
0x1801cffc3  lea     edx, [rsi+2]; dwCmpFlags
0x1801cffc6  lea     r14d, [rdx+7Eh]
0x1801cffca  mov     ecx, r14d; Locale
0x1801cffcd  call    cs:__imp_CompareStringW
0x1801cffd3  lea     rdi, aAppliedradius; "AppliedRadius"
0x1801cffda  cmp     eax, 2
0x1801cffdd  jz      loc_1801D02CC
0x1801cffe3  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801cffe7  mov     [rsp+0A8h+lpString2], rdi; lpString2
0x1801cffec  mov     r9d, esi; cchCount1
0x1801cffef  mov     r8, rbx; lpString1
0x1801cfff2  lea     edx, [rsi+2]; dwCmpFlags
0x1801cfff5  mov     ecx, r14d; Locale
0x1801cfff8  call    cs:__imp_CompareStringW
0x1801cfffe  cmp     eax, 2
0x1801d0001  jz      loc_1801D02CC
0x1801d0007  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801d000b  lea     rdi, aRatioofconvolu; "RatioOfConvolutionWindowToDiameter"
0x1801d0012  mov     [rsp+0A8h+lpString2], rdi; lpString2
0x1801d0017  mov     r9d, esi; cchCount1
0x1801d001a  mov     r8, rbx; lpString1
0x1801d001d  lea     edx, [rsi+2]; dwCmpFlags
0x1801d0020  mov     ecx, r14d; Locale
0x1801d0023  call    cs:__imp_CompareStringW
0x1801d0029  cmp     eax, 2
0x1801d002c  jnz     loc_1801D016E
0x1801d0032  xorps   xmm0, xmm0
0x1801d0035  xor     eax, eax
0x1801d0037  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1801d003c  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1801d0041  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801d0046  call    cs:__imp_VariantInit
0x1801d004c  mov     rcx, [r15+80h]
0x1801d0053  mov     rax, [rcx]
0x1801d0056  lea     r8, [rsp+0A8h+pvarg]
0x1801d005b  mov     rdx, rdi
0x1801d005e  mov     rax, [rax+60h]
0x1801d0062  call    cs:__guard_dispatch_icall_fptr
0x1801d0068  mov     ebx, 8007000Eh
0x1801d006d  cmp     eax, ebx
0x1801d006f  jz      loc_1801D0411
0x1801d0075  mov     edi, 86160210h
0x1801d007a  cmp     eax, edi
0x1801d007c  jz      loc_1801D0411
0x1801d0082  mov     esi, 86170103h
0x1801d0087  cmp     eax, esi
0x1801d0089  jz      loc_1801D0411
0x1801d008f  mov     r14d, 86180110h
0x1801d0095  cmp     eax, r14d
0x1801d0098  jz      loc_1801D0411
0x1801d009e  test    eax, eax
0x1801d00a0  js      loc_1801D03EB
0x1801d00a6  mov     [rsp+0A8h+arg_8], 0
0x1801d00b2  mov     rcx, [r15+90h]
0x1801d00b9  mov     rax, [rcx]
0x1801d00bc  lea     r8, [rsp+0A8h+arg_8]
0x1801d00c4  lea     rdx, aBlureffectid; "BlurEffectId"
0x1801d00cb  mov     rax, [rax+98h]
0x1801d00d2  call    cs:__guard_dispatch_icall_fptr
0x1801d00d8  test    eax, eax
0x1801d00da  js      loc_1801D03F2
0x1801d00e0  mov     rcx, [rsp+0A8h+arg_8]
0x1801d00e8  test    rcx, rcx
0x1801d00eb  jz      loc_1801D03F9
0x1801d00f1  mov     rax, [rcx]
0x1801d00f4  mov     rax, [rax+10h]
0x1801d00f8  call    cs:__guard_dispatch_icall_fptr
0x1801d00fe  mov     rcx, [rsp+0A8h+arg_8]
0x1801d0106  mov     rax, [rcx]
0x1801d0109  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x1801d010e  movaps  [rsp+0A8h+var_48], xmm0
0x1801d0113  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x1801d0119  movsd   [rsp+0A8h+var_38], xmm1
0x1801d011f  lea     r8, [rsp+0A8h+var_48]
0x1801d0124  lea     rdx, aRatioofconvolu; "RatioOfConvolutionWindowToDiameter"
0x1801d012b  mov     rax, [rax+68h]
0x1801d012f  call    cs:__guard_dispatch_icall_fptr
0x1801d0135  cmp     eax, ebx
0x1801d0137  jz      loc_1801D040A
0x1801d013d  cmp     eax, edi
0x1801d013f  jz      loc_1801D040A
0x1801d0145  cmp     eax, esi
0x1801d0147  jz      loc_1801D040A
0x1801d014d  cmp     eax, r14d
0x1801d0150  jz      loc_1801D040A
0x1801d0156  test    eax, eax
0x1801d0158  js      loc_1801D0403
0x1801d015e  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801d0163  call    cs:__imp_VariantClear
0x1801d0169  jmp     loc_1801D037F
0x1801d016e  mov     [rsp+0A8h+cchCount2], esi; cchCount2
0x1801d0172  lea     rdi, aChannels; "Channels"
0x1801d0179  mov     [rsp+0A8h+lpString2], rdi; lpString2
0x1801d017e  mov     r9d, esi; cchCount1
0x1801d0181  mov     r8, rbx; lpString1
0x1801d0184  mov     edx, 1; dwCmpFlags
0x1801d0189  mov     ecx, r14d; Locale
0x1801d018c  call    cs:__imp_CompareStringW
0x1801d0192  cmp     eax, 2
0x1801d0195  jnz     loc_1801D037F
0x1801d019b  xorps   xmm0, xmm0
0x1801d019e  xor     eax, eax
0x1801d01a0  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1801d01a5  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1801d01aa  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801d01af  call    cs:__imp_VariantInit
0x1801d01b5  mov     rcx, [r15+80h]
0x1801d01bc  mov     rax, [rcx]
0x1801d01bf  lea     r8, [rsp+0A8h+pvarg]
0x1801d01c4  mov     rdx, rdi
0x1801d01c7  mov     rax, [rax+60h]
0x1801d01cb  call    cs:__guard_dispatch_icall_fptr
0x1801d01d1  mov     ebx, 8007000Eh
0x1801d01d6  cmp     eax, ebx
0x1801d01d8  jz      loc_1801D0447
0x1801d01de  mov     edi, 86160210h
0x1801d01e3  cmp     eax, edi
0x1801d01e5  jz      loc_1801D0447
0x1801d01eb  mov     esi, 86170103h
0x1801d01f0  cmp     eax, esi
0x1801d01f2  jz      loc_1801D0447
0x1801d01f8  mov     r14d, 86180110h
0x1801d01fe  cmp     eax, r14d
0x1801d0201  jz      loc_1801D0447
0x1801d0207  test    eax, eax
0x1801d0209  js      loc_1801D0421
0x1801d020f  mov     [rsp+0A8h+arg_8], 0
0x1801d021b  mov     rcx, [r15+90h]
0x1801d0222  mov     rax, [rcx]
0x1801d0225  lea     r8, [rsp+0A8h+arg_8]
0x1801d022d  lea     rdx, aBlureffectid; "BlurEffectId"
0x1801d0234  mov     rax, [rax+98h]
0x1801d023b  call    cs:__guard_dispatch_icall_fptr
0x1801d0241  test    eax, eax
0x1801d0243  js      loc_1801D0428
0x1801d0249  mov     rcx, [rsp+0A8h+arg_8]
0x1801d0251  test    rcx, rcx
0x1801d0254  jz      loc_1801D042F
0x1801d025a  mov     rax, [rcx]
0x1801d025d  mov     rax, [rax+10h]
0x1801d0261  call    cs:__guard_dispatch_icall_fptr
0x1801d0267  mov     rcx, [rsp+0A8h+arg_8]
0x1801d026f  mov     rax, [rcx]
0x1801d0272  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x1801d0277  movaps  [rsp+0A8h+var_48], xmm0
0x1801d027c  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x1801d0282  movsd   [rsp+0A8h+var_38], xmm1
0x1801d0288  lea     r8, [rsp+0A8h+var_48]
0x1801d028d  lea     rdx, aChannels; "Channels"
0x1801d0294  mov     rax, [rax+68h]
0x1801d0298  call    cs:__guard_dispatch_icall_fptr
0x1801d029e  cmp     eax, ebx
0x1801d02a0  jz      loc_1801D0440
0x1801d02a6  cmp     eax, edi
0x1801d02a8  jz      loc_1801D0440
0x1801d02ae  cmp     eax, esi
0x1801d02b0  jz      loc_1801D0440
0x1801d02b6  cmp     eax, r14d
0x1801d02b9  jz      loc_1801D0440
0x1801d02bf  test    eax, eax
0x1801d02c1  js      loc_1801D0439
0x1801d02c7  jmp     loc_1801D015E
0x1801d02cc  xorps   xmm0, xmm0
0x1801d02cf  xor     eax, eax
0x1801d02d1  movups  xmmword ptr [rsp+0A8h+pvarg], xmm0
0x1801d02d6  mov     qword ptr [rsp+0A8h+pvarg+10h], rax
0x1801d02db  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801d02e0  call    cs:__imp_VariantInit
0x1801d02e6  mov     rcx, [r15+80h]
0x1801d02ed  mov     rax, [rcx]
0x1801d02f0  lea     r8, [rsp+0A8h+pvarg]
0x1801d02f5  mov     rdx, rdi
0x1801d02f8  mov     rax, [rax+60h]
0x1801d02fc  call    cs:__guard_dispatch_icall_fptr
0x1801d0302  mov     ebx, 8007000Eh
0x1801d0307  cmp     eax, ebx
0x1801d0309  jz      loc_1801D047F
0x1801d030f  mov     edi, 86160210h
0x1801d0314  cmp     eax, edi
0x1801d0316  jz      loc_1801D047F
0x1801d031c  mov     esi, 86170103h
0x1801d0321  cmp     eax, esi
0x1801d0323  jz      loc_1801D047F
0x1801d0329  mov     r14d, 86180110h
0x1801d032f  cmp     eax, r14d
0x1801d0332  jz      loc_1801D047F
0x1801d0338  test    eax, eax
0x1801d033a  js      loc_1801D0453
0x1801d0340  movsd   xmm6, qword ptr [rsp+0A8h+pvarg+8]
0x1801d0346  cvtpd2ps xmm6, xmm6
0x1801d034a  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x1801d034f  call    cs:__imp_VariantClear
0x1801d0355  comiss  xmm6, cs:__real@00000000
0x1801d035c  jb      loc_1801D045F
0x1801d0362  mov     rcx, r15; this
0x1801d0365  call    ?GetRadiusProperty@GaussianBlurLargeRadiusEffect@@IEAAMXZ; GaussianBlurLargeRadiusEffect::GetRadiusProperty(void)
0x1801d036a  comiss  xmm0, cs:__real@00000000
0x1801d0371  jb      loc_1801D0469
0x1801d0377  mov     byte ptr [r15+0A0h], 1
0x1801d037f  cmp     byte ptr [r15+0A0h], 0
0x1801d0387  jnz     short loc_1801D03A8
0x1801d0389  mov     rcx, [r15+80h]
0x1801d0390  mov     rax, [rcx]
0x1801d0393  mov     rax, [rax+110h]
0x1801d039a  call    cs:__guard_dispatch_icall_fptr
0x1801d03a0  test    eax, eax
0x1801d03a2  js      loc_1801D0473
0x1801d03a8  xor     eax, eax
0x1801d03aa  jmp     short loc_1801D03BF
0x1801d03ac  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x1801d03b3  mov     edx, 86160101h
0x1801d03b8  cmp     ax, 216h
0x1801d03bc  cmovz   eax, edx
0x1801d03bf  lea     r11, [rsp+0A8h+var_18]
0x1801d03c7  mov     rbx, [r11+20h]
0x1801d03cb  mov     rsi, [r11+30h]
0x1801d03cf  movaps  xmm6, xmmword ptr [r11-10h]
0x1801d03d4  mov     rsp, r11
0x1801d03d7  pop     r15
0x1801d03d9  pop     r14
0x1801d03db  pop     rdi
0x1801d03dc  retn
0x1801d03dd  mov     ecx, 80004003h; int
0x1801d03e2  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d03e8  jmp     short $+2
0x1801d03ea  nop
0x1801d03eb  mov     ecx, eax; int
0x1801d03ed  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d03f2  mov     ecx, eax; int
0x1801d03f4  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d03f9  mov     ecx, 8618010Ah; int
0x1801d03fe  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0403  mov     ecx, eax; int
0x1801d0405  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d040a  mov     ecx, eax; int
0x1801d040c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0411  mov     ecx, eax; int
0x1801d0413  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0421  mov     ecx, eax; int
0x1801d0423  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0428  mov     ecx, eax; int
0x1801d042a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d042f  mov     ecx, 8618010Ah; int
0x1801d0434  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0439  mov     ecx, eax; int
0x1801d043b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0440  mov     ecx, eax; int
0x1801d0442  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0447  mov     ecx, eax; int
0x1801d0449  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d044f  jmp     short loc_1801D0452
0x1801d0452  nop
0x1801d0453  mov     ecx, eax; int
0x1801d0455  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d045b  jmp     short loc_1801D045E
0x1801d045e  nop
0x1801d045f  mov     ecx, 80070057h; int
0x1801d0464  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0469  mov     ecx, 80070057h; int
0x1801d046e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d0473  mov     ecx, eax; int
0x1801d0475  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801d047b  jmp     short loc_1801D047E
0x1801d047e  nop
0x1801d047f  mov     ecx, eax; int
0x1801d0481  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
