# StraighteningEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801aa130`
- end: `0x1801aa554`
- name: `?OnPropertyChanged@StraighteningEffect@@UEAAJPEB_W@Z`
- size: `1060`
- prototype: `int(StraighteningEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1801aa130`
- `0x1801abff0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801aa177`
- `KERNEL32!CompareStringW` at `0x1801aa278`
- `KERNEL32!CompareStringW` at `0x1801aa345`
- `KERNEL32!CompareStringW` at `0x1801aa49e`
- `KERNEL32!CompareStringW` at `0x1801aa177`
- `KERNEL32!CompareStringW` at `0x1801aa278`
- `KERNEL32!CompareStringW` at `0x1801aa345`
- `KERNEL32!CompareStringW` at `0x1801aa49e`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa19a`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa29b`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa368`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa19a`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa29b`
- `OLEAUT32!__imp_VariantInit` at `0x1801aa368`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa223`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa31c`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa478`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa223`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa31c`
- `OLEAUT32!__imp_VariantClear` at `0x1801aa478`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StraighteningEffect::OnPropertyChanged(StraighteningEffect *this, const wchar_t *a2)
{
  bool v4; // bl
  int v5; // eax
  __int64 result; // rax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  int v12; // eax
  int v13; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v14[4]; // [rsp+38h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-50h] BYREF
  VARIANTARG v16; // [rsp+60h] [rbp-38h] BYREF
  __int64 *v17; // [rsp+A8h] [rbp+10h] BYREF

  try
  {
    if ( !a2 )
      ATL::BaseAtlThrow(-2147467261);
    v4 = 0;
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Angle", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v5 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             L"Angle",
             &pvarg);
      if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
        ATL::BaseAtlThrow(v5);
      if ( v5 < 0 )
        ATL::BaseAtlThrow(v5);
      if ( pvarg.dblVal < -3.402823466385289e38 || pvarg.dblVal > 3.402823466385289e38 )
        ATL::BaseAtlThrow(-2147024809);
      VariantClear(&pvarg);
      return 0;
    }
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"AutoCrop", -1) == 2 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
             *((_QWORD *)this + 16),
             a2,
             &pvarg);
      if ( v7 == -2147024882 || v7 == -2045378032 || v7 == -2045312765 || v7 == -2045247216 )
        ATL::BaseAtlThrow(v7);
      if ( v7 < 0 )
        ATL::BaseAtlThrow(v7);
      if ( pvarg.lVal > 1u )
        ATL::BaseAtlThrow(-2147024809);
      v4 = pvarg.lVal != *((_DWORD *)this + 44);
      *((_DWORD *)this + 44) = pvarg.lVal;
      VariantClear(&pvarg);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"InterpolationMode", -1) == 2 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
               *((_QWORD *)this + 16),
               a2,
               &pvarg);
        if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
          ATL::BaseAtlThrow(v8);
        if ( v8 < 0 )
          ATL::BaseAtlThrow(v8);
        v17 = 0;
        v9 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 19) + 56LL))(
               *((_QWORD *)this + 19),
               &v17);
        if ( v9 < 0 )
          ATL::BaseAtlThrow(v9);
        if ( !v17 )
          ATL::BaseAtlThrow(-2045247222);
        (*(void (__fastcall **)(__int64 *))(*v17 + 16))(v17);
        v10 = *v17;
        v16 = pvarg;
        v11 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v10 + 104))(v17, a2, &v16);
        if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
          ATL::BaseAtlThrow(v11);
        if ( v11 < 0 )
          ATL::BaseAtlThrow(v11);
        VariantClear(&pvarg);
        goto LABEL_41;
      }
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"_AutoFix", -1) != 2 )
      {
LABEL_41:
        v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
        if ( v12 < 0 )
          ATL::BaseAtlThrow(v12);
        return 0;
      }
      StraighteningEffect::AutoFix(this);
    }
    if ( v4 )
      return 0;
    goto LABEL_41;
  }
  catch ( Base::Exception v14 )
  {
    LODWORD(v17) = v14[2];
    goto LABEL_13;
  }
  catch ( long v13 )
  {
    LODWORD(v17) = v13;
LABEL_13:
    result = (unsigned int)v17;
    if ( (_WORD)v17 == 534 )
      return 2249588993LL;
  }
  return result;
}

```

## disassembly

```asm
0x1801aa130  mov     [rsp+arg_0], rbx
0x1801aa135  mov     [rsp+arg_10], rdi
0x1801aa13a  push    r12
0x1801aa13c  push    r14
0x1801aa13e  push    r15
0x1801aa140  sub     rsp, 80h
0x1801aa147  mov     r12, rdx
0x1801aa14a  mov     r15, rcx
0x1801aa14d  test    rdx, rdx
0x1801aa150  jz      loc_1801AA4DF
0x1801aa156  xor     bl, bl
0x1801aa158  or      edi, 0FFFFFFFFh
0x1801aa15b  mov     [rsp+98h+cchCount2], edi; cchCount2
0x1801aa15f  lea     r14, aAngle; "Angle"
0x1801aa166  mov     [rsp+98h+lpString2], r14; lpString2
0x1801aa16b  mov     r9d, edi; cchCount1
0x1801aa16e  mov     r8, r12; lpString1
0x1801aa171  lea     edx, [rdi+2]; dwCmpFlags
0x1801aa174  lea     ecx, [rdx+7Eh]; Locale
0x1801aa177  call    cs:__imp_CompareStringW
0x1801aa17d  cmp     eax, 2
0x1801aa180  jnz     loc_1801AA25A
0x1801aa186  xorps   xmm0, xmm0
0x1801aa189  xor     eax, eax
0x1801aa18b  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x1801aa190  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x1801aa195  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa19a  call    cs:__imp_VariantInit
0x1801aa1a0  mov     rcx, [r15+80h]
0x1801aa1a7  mov     rax, [rcx]
0x1801aa1aa  lea     r8, [rsp+98h+pvarg]
0x1801aa1af  mov     rdx, r14
0x1801aa1b2  mov     rax, [rax+60h]
0x1801aa1b6  call    cs:__guard_dispatch_icall_fptr
0x1801aa1bc  mov     ebx, 8007000Eh
0x1801aa1c1  cmp     eax, ebx
0x1801aa1c3  jz      loc_1801AA4FE
0x1801aa1c9  mov     edi, 86160210h
0x1801aa1ce  cmp     eax, edi
0x1801aa1d0  jz      loc_1801AA4FE
0x1801aa1d6  cmp     eax, 86170103h
0x1801aa1db  jz      loc_1801AA4FE
0x1801aa1e1  mov     r14d, 86180110h
0x1801aa1e7  cmp     eax, r14d
0x1801aa1ea  jz      loc_1801AA4FE
0x1801aa1f0  test    eax, eax
0x1801aa1f2  js      loc_1801AA4ED
0x1801aa1f8  movsd   xmm1, qword ptr [rsp+98h+pvarg+8]
0x1801aa1fe  comisd  xmm1, cs:__real@c7efffffe0000000
0x1801aa206  jb      loc_1801AA4F4
0x1801aa20c  movsd   xmm0, cs:__real@47efffffe0000000
0x1801aa214  comisd  xmm0, xmm1
0x1801aa218  jb      loc_1801AA4F4
0x1801aa21e  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa223  call    cs:__imp_VariantClear
0x1801aa229  xor     eax, eax
0x1801aa22b  jmp     short loc_1801AA240
0x1801aa22d  mov     eax, dword ptr [rsp+98h+arg_8]
0x1801aa234  mov     edx, 86160101h
0x1801aa239  cmp     ax, 216h
0x1801aa23d  cmovz   eax, edx
0x1801aa240  lea     r11, [rsp+98h+var_18]
0x1801aa248  mov     rbx, [r11+20h]
0x1801aa24c  mov     rdi, [r11+30h]
0x1801aa250  mov     rsp, r11
0x1801aa253  pop     r15
0x1801aa255  pop     r14
0x1801aa257  pop     r12
0x1801aa259  retn
0x1801aa25a  mov     [rsp+98h+cchCount2], edi; cchCount2
0x1801aa25e  lea     rax, aAutocrop; "AutoCrop"
0x1801aa265  mov     [rsp+98h+lpString2], rax; lpString2
0x1801aa26a  mov     r9d, edi; cchCount1
0x1801aa26d  mov     r8, r12; lpString1
0x1801aa270  mov     edx, 1; dwCmpFlags
0x1801aa275  lea     ecx, [rdx+7Eh]; Locale
0x1801aa278  call    cs:__imp_CompareStringW
0x1801aa27e  cmp     eax, 2
0x1801aa281  jnz     loc_1801AA327
0x1801aa287  xorps   xmm0, xmm0
0x1801aa28a  xor     eax, eax
0x1801aa28c  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x1801aa291  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x1801aa296  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa29b  call    cs:__imp_VariantInit
0x1801aa2a1  mov     rcx, [r15+80h]
0x1801aa2a8  mov     rax, [rcx]
0x1801aa2ab  lea     r8, [rsp+98h+pvarg]
0x1801aa2b0  mov     rdx, r12
0x1801aa2b3  mov     rax, [rax+60h]
0x1801aa2b7  call    cs:__guard_dispatch_icall_fptr
0x1801aa2bd  mov     ebx, 8007000Eh
0x1801aa2c2  cmp     eax, ebx
0x1801aa2c4  jz      loc_1801AA51A
0x1801aa2ca  mov     edi, 86160210h
0x1801aa2cf  cmp     eax, edi
0x1801aa2d1  jz      loc_1801AA51A
0x1801aa2d7  cmp     eax, 86170103h
0x1801aa2dc  jz      loc_1801AA51A
0x1801aa2e2  mov     r14d, 86180110h
0x1801aa2e8  cmp     eax, r14d
0x1801aa2eb  jz      loc_1801AA51A
0x1801aa2f1  test    eax, eax
0x1801aa2f3  js      loc_1801AA509
0x1801aa2f9  mov     eax, dword ptr [rsp+98h+pvarg+8]
0x1801aa2fd  cmp     eax, 1
0x1801aa300  ja      loc_1801AA510
0x1801aa306  cmp     eax, [r15+0B0h]
0x1801aa30d  setnz   bl
0x1801aa310  mov     [r15+0B0h], eax
0x1801aa317  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa31c  call    cs:__imp_VariantClear
0x1801aa322  jmp     loc_1801AA4B1
0x1801aa327  mov     [rsp+98h+cchCount2], edi; cchCount2
0x1801aa32b  lea     rax, aInterpolationm; "InterpolationMode"
0x1801aa332  mov     [rsp+98h+lpString2], rax; lpString2
0x1801aa337  mov     r9d, edi; cchCount1
0x1801aa33a  mov     r8, r12; lpString1
0x1801aa33d  mov     edx, 1; dwCmpFlags
0x1801aa342  lea     ecx, [rdx+7Eh]; Locale
0x1801aa345  call    cs:__imp_CompareStringW
0x1801aa34b  cmp     eax, 2
0x1801aa34e  jnz     loc_1801AA480
0x1801aa354  xorps   xmm0, xmm0
0x1801aa357  xor     eax, eax
0x1801aa359  movups  xmmword ptr [rsp+98h+pvarg], xmm0
0x1801aa35e  mov     qword ptr [rsp+98h+pvarg+10h], rax
0x1801aa363  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa368  call    cs:__imp_VariantInit
0x1801aa36e  mov     rcx, [r15+80h]
0x1801aa375  mov     rax, [rcx]
0x1801aa378  lea     r8, [rsp+98h+pvarg]
0x1801aa37d  mov     rdx, r12
0x1801aa380  mov     rax, [rax+60h]
0x1801aa384  call    cs:__guard_dispatch_icall_fptr
0x1801aa38a  mov     ebx, 8007000Eh
0x1801aa38f  cmp     eax, ebx
0x1801aa391  jz      loc_1801AA54B
0x1801aa397  mov     edi, 86160210h
0x1801aa39c  cmp     eax, edi
0x1801aa39e  jz      loc_1801AA54B
0x1801aa3a4  cmp     eax, 86170103h
0x1801aa3a9  jz      loc_1801AA54B
0x1801aa3af  mov     r14d, 86180110h
0x1801aa3b5  cmp     eax, r14d
0x1801aa3b8  jz      loc_1801AA54B
0x1801aa3be  test    eax, eax
0x1801aa3c0  js      loc_1801AA525
0x1801aa3c6  mov     [rsp+98h+arg_8], 0
0x1801aa3d2  mov     rcx, [r15+98h]
0x1801aa3d9  mov     rax, [rcx]
0x1801aa3dc  lea     rdx, [rsp+98h+arg_8]
0x1801aa3e4  mov     rax, [rax+38h]
0x1801aa3e8  call    cs:__guard_dispatch_icall_fptr
0x1801aa3ee  test    eax, eax
0x1801aa3f0  js      loc_1801AA52C
0x1801aa3f6  mov     rcx, [rsp+98h+arg_8]
0x1801aa3fe  test    rcx, rcx
0x1801aa401  jz      loc_1801AA533
0x1801aa407  mov     rax, [rcx]
0x1801aa40a  mov     rax, [rax+10h]
0x1801aa40e  call    cs:__guard_dispatch_icall_fptr
0x1801aa414  mov     rcx, [rsp+98h+arg_8]
0x1801aa41c  mov     rax, [rcx]
0x1801aa41f  movups  xmm0, xmmword ptr [rsp+98h+pvarg]
0x1801aa424  movaps  [rsp+98h+var_38], xmm0
0x1801aa429  movsd   xmm1, qword ptr [rsp+98h+pvarg+10h]
0x1801aa42f  movsd   [rsp+98h+var_28], xmm1
0x1801aa435  lea     r8, [rsp+98h+var_38]
0x1801aa43a  mov     rdx, r12
0x1801aa43d  mov     rax, [rax+68h]
0x1801aa441  call    cs:__guard_dispatch_icall_fptr
0x1801aa447  cmp     eax, ebx
0x1801aa449  jz      loc_1801AA544
0x1801aa44f  cmp     eax, edi
0x1801aa451  jz      loc_1801AA544
0x1801aa457  cmp     eax, 86170103h
0x1801aa45c  jz      loc_1801AA544
0x1801aa462  cmp     eax, r14d
0x1801aa465  jz      loc_1801AA544
0x1801aa46b  test    eax, eax
0x1801aa46d  js      loc_1801AA53D
0x1801aa473  lea     rcx, [rsp+98h+pvarg]; pvarg
0x1801aa478  call    cs:__imp_VariantClear
0x1801aa47e  jmp     short loc_1801AA4B9
0x1801aa480  mov     [rsp+98h+cchCount2], edi; cchCount2
0x1801aa484  lea     rax, aAutofix; "_AutoFix"
0x1801aa48b  mov     [rsp+98h+lpString2], rax; lpString2
0x1801aa490  mov     r9d, edi; cchCount1
0x1801aa493  mov     r8, r12; lpString1
0x1801aa496  mov     edx, 1; dwCmpFlags
0x1801aa49b  lea     ecx, [rdx+7Eh]; Locale
0x1801aa49e  call    cs:__imp_CompareStringW
0x1801aa4a4  cmp     eax, 2
0x1801aa4a7  jnz     short loc_1801AA4B9
0x1801aa4a9  mov     rcx, r15; this
0x1801aa4ac  call    ?AutoFix@StraighteningEffect@@AEAAXXZ; StraighteningEffect::AutoFix(void)
0x1801aa4b1  test    bl, bl
0x1801aa4b3  jnz     loc_1801AA229
0x1801aa4b9  mov     rcx, [r15+80h]
0x1801aa4c0  mov     rax, [rcx]
0x1801aa4c3  mov     rax, [rax+110h]
0x1801aa4ca  call    cs:__guard_dispatch_icall_fptr
0x1801aa4d0  test    eax, eax
0x1801aa4d2  jns     loc_1801AA229
0x1801aa4d8  mov     ecx, eax; int
0x1801aa4da  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa4df  mov     ecx, 80004003h; int
0x1801aa4e4  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa4ea  jmp     short $+2
0x1801aa4ec  nop
0x1801aa4ed  mov     ecx, eax; int
0x1801aa4ef  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa4f4  mov     ecx, 80070057h; int
0x1801aa4f9  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa4fe  mov     ecx, eax; int
0x1801aa500  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa506  jmp     short $+2
0x1801aa508  nop
0x1801aa509  mov     ecx, eax; int
0x1801aa50b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa510  mov     ecx, 80070057h; int
0x1801aa515  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa51a  mov     ecx, eax; int
0x1801aa51c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa522  jmp     short $+2
0x1801aa524  nop
0x1801aa525  mov     ecx, eax; int
0x1801aa527  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa52c  mov     ecx, eax; int
0x1801aa52e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa533  mov     ecx, 8618010Ah; int
0x1801aa538  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa53d  mov     ecx, eax; int
0x1801aa53f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa544  mov     ecx, eax; int
0x1801aa546  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801aa54b  mov     ecx, eax; int
0x1801aa54d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
