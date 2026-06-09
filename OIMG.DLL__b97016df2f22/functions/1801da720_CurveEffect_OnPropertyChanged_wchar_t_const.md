# CurveEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801da720`
- end: `0x1801daa31`
- name: `?OnPropertyChanged@CurveEffect@@UEAAJPEB_W@Z`
- size: `785`
- prototype: `int(CurveEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1801da720`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801da770`
- `KERNEL32!CompareStringW` at `0x1801da828`
- `KERNEL32!CompareStringW` at `0x1801da850`
- `KERNEL32!CompareStringW` at `0x1801da878`
- `KERNEL32!CompareStringW` at `0x1801da8a8`
- `KERNEL32!CompareStringW` at `0x1801da770`
- `KERNEL32!CompareStringW` at `0x1801da828`
- `KERNEL32!CompareStringW` at `0x1801da850`
- `KERNEL32!CompareStringW` at `0x1801da878`
- `KERNEL32!CompareStringW` at `0x1801da8a8`
- `OLEAUT32!__imp_VariantInit` at `0x1801da796`
- `OLEAUT32!__imp_VariantInit` at `0x1801da8e4`
- `OLEAUT32!__imp_VariantInit` at `0x1801da796`
- `OLEAUT32!__imp_VariantInit` at `0x1801da8e4`
- `OLEAUT32!__imp_VariantClear` at `0x1801da803`
- `OLEAUT32!__imp_VariantClear` at `0x1801da803`

## string_xrefs

- `0x1801da75a`: `CurveExtension`
- `0x1801da843`: `CaptureOneCompatible`
- `0x1801da8ba`: `CropEffect.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CurveEffect::OnPropertyChanged(CurveEffect *this, const wchar_t *lpString2)
{
  int v4; // eax
  int v5; // r14d
  PCNZWCH *v6; // rsi
  int v7; // eax
  unsigned int v8; // eax
  VARIANTARG pvarg; // [rsp+48h] [rbp-40h] BYREF

  if ( !lpString2 )
    ATL::BaseAtlThrow(-2147467261);
  if ( CompareStringW(0x7Fu, 1u, L"CurveExtension", -1, lpString2, -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v4 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           lpString2,
           &pvarg);
    if ( v4 == -2147024882 || v4 == -2045378032 || v4 == -2045312765 || v4 == -2045247216 )
      ATL::BaseAtlThrow(v4);
    if ( v4 < 0 )
      ATL::BaseAtlThrow(v4);
    if ( pvarg.lVal > 1u )
      ATL::BaseAtlThrow(-2147024809);
    *((_BYTE *)this + 160) = 0;
    goto LABEL_10;
  }
  if ( CompareStringW(0x7Fu, 1u, L"ClampOutput", -1, lpString2, -1) == 2
    || CompareStringW(0x7Fu, 1u, L"CaptureOneCompatible", -1, lpString2, -1) == 2
    || CompareStringW(0x7Fu, 1u, L"Invert", -1, lpString2, -1) == 2 )
  {
    *((_BYTE *)this + 160) = 0;
    return 0;
  }
  v5 = 0;
  v6 = (PCNZWCH *)off_1805FC750;
  do
  {
    if ( CompareStringW(0x7Fu, 1u, *v6, -1, lpString2, -1) == 2 )
      break;
    ++v5;
    ++v6;
  }
  while ( (__int64)v6 < (__int64)L"CropEffect.xml" );
  if ( v5 < 4 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           lpString2,
           &pvarg);
    if ( v7 == -2147024882 || v7 == -2045378032 || v7 == -2045312765 || v7 == -2045247216 )
      ATL::BaseAtlThrow(v7);
    if ( v7 < 0 )
      ATL::BaseAtlThrow(v7);
    if ( pvarg.vt )
    {
      if ( *pvarg.bstrVal == 1 )
      {
        v8 = *(_DWORD *)(pvarg.llVal + 24);
        if ( (v8 & 1) != 0 )
          ATL::BaseAtlThrow(-2147024809);
        if ( (v8 >> 1) - 2 > 0x10 )
          ATL::BaseAtlThrow(-2147024809);
      }
      else
      {
        if ( *pvarg.bstrVal != 2 )
        {
LABEL_10:
          VariantClear(&pvarg);
          return 0;
        }
        if ( *(_DWORD *)(pvarg.llVal + 24) != 2 )
          ATL::BaseAtlThrow(-2147024809);
        if ( (unsigned int)(*(_DWORD *)(pvarg.llVal + 32) - 2) > 0x10 )
          ATL::BaseAtlThrow(-2147024809);
      }
    }
    *((_BYTE *)this + 160) = 0;
    goto LABEL_10;
  }
  return 0;
}

```

## disassembly

```asm
0x1801da720  mov     [rsp+arg_0], rbx
0x1801da725  mov     [rsp+arg_10], rsi
0x1801da72a  push    rdi
0x1801da72b  push    r12
0x1801da72d  push    r13
0x1801da72f  push    r14
0x1801da731  push    r15
0x1801da733  sub     rsp, 60h
0x1801da737  mov     rbx, rdx
0x1801da73a  mov     rdi, rcx
0x1801da73d  xor     r15d, r15d
0x1801da740  test    rdx, rdx
0x1801da743  jz      loc_1801DA9CF
0x1801da749  or      r13d, 0FFFFFFFFh
0x1801da74d  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x1801da752  mov     [rsp+88h+lpString2], rbx; lpString2
0x1801da757  mov     r9d, r13d; cchCount1
0x1801da75a  lea     r8, aCurveextension; "CurveExtension"
0x1801da761  lea     r12d, [r13+2]
0x1801da765  mov     edx, r12d; dwCmpFlags
0x1801da768  lea     r14d, [r12+7Eh]
0x1801da76d  mov     ecx, r14d; Locale
0x1801da770  call    cs:__imp_CompareStringW
0x1801da776  lea     esi, [r13+3]
0x1801da77a  cmp     eax, esi
0x1801da77c  jnz     loc_1801DA80E
0x1801da782  xorps   xmm0, xmm0
0x1801da785  xor     eax, eax
0x1801da787  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1801da78c  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1801da791  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1801da796  call    cs:__imp_VariantInit
0x1801da79c  mov     rcx, [rdi+80h]
0x1801da7a3  mov     rax, [rcx]
0x1801da7a6  lea     r8, [rsp+88h+pvarg]
0x1801da7ab  mov     rdx, rbx
0x1801da7ae  mov     rax, [rax+60h]
0x1801da7b2  call    cs:__guard_dispatch_icall_fptr
0x1801da7b8  cmp     eax, 8007000Eh
0x1801da7bd  jz      loc_1801DA9EE
0x1801da7c3  cmp     eax, 86160210h
0x1801da7c8  jz      loc_1801DA9EE
0x1801da7ce  cmp     eax, 86170103h
0x1801da7d3  jz      loc_1801DA9EE
0x1801da7d9  cmp     eax, 86180110h
0x1801da7de  jz      loc_1801DA9EE
0x1801da7e4  test    eax, eax
0x1801da7e6  js      loc_1801DA9DD
0x1801da7ec  cmp     dword ptr [rsp+88h+pvarg+8], r12d
0x1801da7f1  ja      loc_1801DA9E4
0x1801da7f7  mov     [rdi+0A0h], r15b
0x1801da7fe  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1801da803  call    cs:__imp_VariantClear
0x1801da809  jmp     loc_1801DA99E
0x1801da80e  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x1801da813  mov     [rsp+88h+lpString2], rbx; lpString2
0x1801da818  mov     r9d, r13d; cchCount1
0x1801da81b  lea     r8, aClampoutput; "ClampOutput"
0x1801da822  mov     edx, r12d; dwCmpFlags
0x1801da825  mov     ecx, r14d; Locale
0x1801da828  call    cs:__imp_CompareStringW
0x1801da82e  cmp     eax, esi
0x1801da830  jz      loc_1801DA997
0x1801da836  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x1801da83b  mov     [rsp+88h+lpString2], rbx; lpString2
0x1801da840  mov     r9d, r13d; cchCount1
0x1801da843  lea     r8, aCaptureonecomp; "CaptureOneCompatible"
0x1801da84a  mov     edx, r12d; dwCmpFlags
0x1801da84d  mov     ecx, r14d; Locale
0x1801da850  call    cs:__imp_CompareStringW
0x1801da856  cmp     eax, esi
0x1801da858  jz      loc_1801DA997
0x1801da85e  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x1801da863  mov     [rsp+88h+lpString2], rbx; lpString2
0x1801da868  mov     r9d, r13d; cchCount1
0x1801da86b  lea     r8, aInvert; "Invert"
0x1801da872  mov     edx, r12d; dwCmpFlags
0x1801da875  mov     ecx, r14d; Locale
0x1801da878  call    cs:__imp_CompareStringW
0x1801da87e  cmp     eax, esi
0x1801da880  jz      loc_1801DA997
0x1801da886  mov     r14d, r15d
0x1801da889  lea     rsi, off_1805FC750; "CurvePts0"
0x1801da890  mov     [rsp+88h+cchCount2], r13d; cchCount2
0x1801da895  mov     [rsp+88h+lpString2], rbx; lpString2
0x1801da89a  mov     r9d, r13d; cchCount1
0x1801da89d  mov     r8, [rsi]; lpString1
0x1801da8a0  mov     edx, r12d; dwCmpFlags
0x1801da8a3  mov     ecx, 7Fh; Locale
0x1801da8a8  call    cs:__imp_CompareStringW
0x1801da8ae  cmp     eax, 2
0x1801da8b1  jz      short loc_1801DA8C6
0x1801da8b3  add     r14d, r12d
0x1801da8b6  add     rsi, 8
0x1801da8ba  lea     rax, aCropeffectXml; "CropEffect.xml"
0x1801da8c1  cmp     rsi, rax
0x1801da8c4  jl      short loc_1801DA890
0x1801da8c6  cmp     r14d, 4
0x1801da8ca  jge     loc_1801DA99E
0x1801da8d0  xorps   xmm0, xmm0
0x1801da8d3  xor     eax, eax
0x1801da8d5  movups  xmmword ptr [rsp+88h+pvarg], xmm0
0x1801da8da  mov     qword ptr [rsp+88h+pvarg+10h], rax
0x1801da8df  lea     rcx, [rsp+88h+pvarg]; pvarg
0x1801da8e4  call    cs:__imp_VariantInit
0x1801da8ea  mov     rcx, [rdi+80h]
0x1801da8f1  mov     rax, [rcx]
0x1801da8f4  lea     r8, [rsp+88h+pvarg]
0x1801da8f9  mov     rdx, rbx
0x1801da8fc  mov     rax, [rax+60h]
0x1801da900  call    cs:__guard_dispatch_icall_fptr
0x1801da906  cmp     eax, 8007000Eh
0x1801da90b  jz      loc_1801DAA28
0x1801da911  cmp     eax, 86160210h
0x1801da916  jz      loc_1801DAA28
0x1801da91c  cmp     eax, 86170103h
0x1801da921  jz      loc_1801DAA28
0x1801da927  cmp     eax, 86180110h
0x1801da92c  jz      loc_1801DAA28
0x1801da932  test    eax, eax
0x1801da934  js      loc_1801DA9F9
0x1801da93a  cmp     word ptr [rsp+88h+pvarg], r15w
0x1801da940  jz      short loc_1801DA98B
0x1801da942  mov     rax, qword ptr [rsp+88h+pvarg+8]
0x1801da947  cmp     [rax], r12w
0x1801da94b  jnz     short loc_1801DA969
0x1801da94d  mov     eax, [rax+18h]
0x1801da950  test    r12b, al
0x1801da953  jnz     loc_1801DAA00
0x1801da959  shr     eax, 1
0x1801da95b  add     eax, 0FFFFFFFEh
0x1801da95e  cmp     eax, 10h
0x1801da961  ja      loc_1801DAA0A
0x1801da967  jmp     short loc_1801DA98B
0x1801da969  mov     ecx, 2
0x1801da96e  cmp     [rax], cx
0x1801da971  jnz     short loc_1801DA992
0x1801da973  cmp     [rax+18h], ecx
0x1801da976  jnz     loc_1801DAA14
0x1801da97c  mov     eax, [rax+20h]
0x1801da97f  add     eax, 0FFFFFFFEh
0x1801da982  cmp     eax, 10h
0x1801da985  ja      loc_1801DAA1E
0x1801da98b  mov     [rdi+0A0h], r15b
0x1801da992  jmp     loc_1801DA7FE
0x1801da997  mov     [rdi+0A0h], r15b
0x1801da99e  xor     eax, eax
0x1801da9a0  jmp     short loc_1801DA9B5
0x1801da9a2  mov     eax, [rsp+88h+arg_8]
0x1801da9a9  mov     edx, 86160101h
0x1801da9ae  cmp     ax, 216h
0x1801da9b2  cmovz   eax, edx
0x1801da9b5  lea     r11, [rsp+88h+var_28]
0x1801da9ba  mov     rbx, [r11+30h]
0x1801da9be  mov     rsi, [r11+40h]
0x1801da9c2  mov     rsp, r11
0x1801da9c5  pop     r15
0x1801da9c7  pop     r14
0x1801da9c9  pop     r13
0x1801da9cb  pop     r12
0x1801da9cd  pop     rdi
0x1801da9ce  retn
0x1801da9cf  mov     ecx, 80004003h; int
0x1801da9d4  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801da9da  jmp     short $+2
0x1801da9dc  nop
0x1801da9dd  mov     ecx, eax; int
0x1801da9df  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801da9e4  mov     ecx, 80070057h; int
0x1801da9e9  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801da9ee  mov     ecx, eax; int
0x1801da9f0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801da9f6  jmp     short $+2
0x1801da9f8  nop
0x1801da9f9  mov     ecx, eax; int
0x1801da9fb  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801daa00  mov     ecx, 80070057h; int
0x1801daa05  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801daa0a  mov     ecx, 80070057h; int
0x1801daa0f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801daa14  mov     ecx, 80070057h; int
0x1801daa19  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801daa1e  mov     ecx, 80070057h; int
0x1801daa23  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801daa28  mov     ecx, eax; int
0x1801daa2a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
