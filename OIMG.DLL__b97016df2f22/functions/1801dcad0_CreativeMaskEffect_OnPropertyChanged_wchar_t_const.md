# CreativeMaskEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x1801dcad0`
- end: `0x1801dcefa`
- name: `?OnPropertyChanged@CreativeMaskEffect@@UEAAJPEB_W@Z`
- size: `1066`
- prototype: `int(CreativeMaskEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1801dcad0`
- `0x1804c6944`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1801dcb1b`
- `KERNEL32!CompareStringW` at `0x1801dcbda`
- `KERNEL32!CompareStringW` at `0x1801dcca8`
- `KERNEL32!CompareStringW` at `0x1801dcd76`
- `KERNEL32!CompareStringW` at `0x1801dcb1b`
- `KERNEL32!CompareStringW` at `0x1801dcbda`
- `KERNEL32!CompareStringW` at `0x1801dcca8`
- `KERNEL32!CompareStringW` at `0x1801dcd76`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcb3e`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcbfd`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcccb`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcd99`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcb3e`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcbfd`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcccb`
- `OLEAUT32!__imp_VariantInit` at `0x1801dcd99`
- `OLEAUT32!__imp_VariantClear` at `0x1801dce12`
- `OLEAUT32!__imp_VariantClear` at `0x1801dce12`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CreativeMaskEffect::OnPropertyChanged(CreativeMaskEffect *this, const wchar_t *a2)
{
  char v4; // si
  int v5; // eax
  int v6; // eax
  float dblVal; // xmm0_4
  int v8; // eax
  float v9; // xmm0_4
  int v10; // eax
  int v11; // eax
  VARIANTARG pvarg; // [rsp+48h] [rbp-30h] BYREF

  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  v4 = 0;
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"MaskType", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v5 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           L"MaskType",
           &pvarg);
    if ( v5 == -2147024882 || v5 == -2045378032 || v5 == -2045312765 || v5 == -2045247216 )
      ATL::BaseAtlThrow(v5);
    if ( v5 < 0 )
      ATL::BaseAtlThrow(v5);
    if ( pvarg.lVal != *((_DWORD *)this + 38) )
    {
      if ( pvarg.lVal > 1u )
        ATL::BaseAtlThrow(-2147024809);
      *((_DWORD *)this + 38) = pvarg.lVal;
      v4 = 1;
    }
    goto LABEL_40;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"MaskSize", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v6 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           L"MaskSize",
           &pvarg);
    if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
      ATL::BaseAtlThrow(v6);
    if ( v6 < 0 )
      ATL::BaseAtlThrow(v6);
    dblVal = pvarg.dblVal;
    if ( dblVal < 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    if ( dblVal != *((float *)this + 36) )
    {
      *((float *)this + 36) = dblVal;
      v4 = 1;
    }
    goto LABEL_40;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"MaskFeather", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v8 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
           *((_QWORD *)this + 16),
           L"MaskFeather",
           &pvarg);
    if ( v8 == -2147024882 || v8 == -2045378032 || v8 == -2045312765 || v8 == -2045247216 )
      ATL::BaseAtlThrow(v8);
    if ( v8 < 0 )
      ATL::BaseAtlThrow(v8);
    v9 = pvarg.dblVal;
    if ( v9 < 0.0 )
      ATL::BaseAtlThrow(-2147024809);
    if ( v9 != *((float *)this + 37) )
    {
      *((float *)this + 37) = v9;
      v4 = 1;
    }
    goto LABEL_40;
  }
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"IsMaskInverted", -1) == 2 )
  {
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v10 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
            *((_QWORD *)this + 16),
            L"IsMaskInverted",
            &pvarg);
    if ( v10 == -2147024882 || v10 == -2045378032 || v10 == -2045312765 || v10 == -2045247216 )
      ATL::BaseAtlThrow(v10);
    if ( v10 < 0 )
      ATL::BaseAtlThrow(v10);
    if ( (pvarg.iVal != 0) != *((_BYTE *)this + 156) )
    {
      *((_BYTE *)this + 156) = pvarg.iVal != 0;
      v4 = 1;
    }
LABEL_40:
    VariantClear(&pvarg);
    if ( v4 )
      return 0;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
  if ( v11 < 0 )
    ATL::BaseAtlThrow(v11);
  return 0;
}

```

## disassembly

```asm
0x1801dcad0  mov     [rsp+arg_0], rbx
0x1801dcad5  mov     [rsp+arg_10], rsi
0x1801dcada  push    rdi
0x1801dcadb  push    r12
0x1801dcadd  push    r14
0x1801dcadf  sub     rsp, 60h
0x1801dcae3  mov     rdi, rdx
0x1801dcae6  mov     rbx, rcx
0x1801dcae9  xor     r14d, r14d
0x1801dcaec  test    rdx, rdx
0x1801dcaef  jz      loc_1801DCE69
0x1801dcaf5  mov     sil, r14b
0x1801dcaf8  or      r12d, 0FFFFFFFFh
0x1801dcafc  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801dcb01  lea     rax, aMasktype; "MaskType"
0x1801dcb08  mov     [rsp+78h+lpString2], rax; lpString2
0x1801dcb0d  mov     r9d, r12d; cchCount1
0x1801dcb10  mov     r8, rdi; lpString1
0x1801dcb13  lea     edx, [r12+2]; dwCmpFlags
0x1801dcb18  lea     ecx, [rdx+7Eh]; Locale
0x1801dcb1b  call    cs:__imp_CompareStringW
0x1801dcb21  cmp     eax, 2
0x1801dcb24  jnz     loc_1801DCBBB
0x1801dcb2a  xorps   xmm0, xmm0
0x1801dcb2d  xor     eax, eax
0x1801dcb2f  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801dcb34  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801dcb39  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801dcb3e  call    cs:__imp_VariantInit
0x1801dcb44  mov     rcx, [rbx+80h]
0x1801dcb4b  mov     rax, [rcx]
0x1801dcb4e  lea     r8, [rsp+78h+pvarg]
0x1801dcb53  lea     rdx, aMasktype; "MaskType"
0x1801dcb5a  mov     rax, [rax+60h]
0x1801dcb5e  call    cs:__guard_dispatch_icall_fptr
0x1801dcb64  cmp     eax, 8007000Eh
0x1801dcb69  jz      loc_1801DCE88
0x1801dcb6f  cmp     eax, 86160210h
0x1801dcb74  jz      loc_1801DCE88
0x1801dcb7a  cmp     eax, 86170103h
0x1801dcb7f  jz      loc_1801DCE88
0x1801dcb85  cmp     eax, 86180110h
0x1801dcb8a  jz      loc_1801DCE88
0x1801dcb90  test    eax, eax
0x1801dcb92  js      loc_1801DCE77
0x1801dcb98  mov     eax, dword ptr [rsp+78h+pvarg+8]
0x1801dcb9c  cmp     eax, [rbx+98h]
0x1801dcba2  jz      short loc_1801DCBB6
0x1801dcba4  cmp     eax, 1
0x1801dcba7  ja      loc_1801DCE7E
0x1801dcbad  mov     [rbx+98h], eax
0x1801dcbb3  mov     sil, 1
0x1801dcbb6  jmp     loc_1801DCE0D
0x1801dcbbb  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801dcbc0  lea     rax, aMasksize; "MaskSize"
0x1801dcbc7  mov     [rsp+78h+lpString2], rax; lpString2
0x1801dcbcc  mov     r9d, r12d; cchCount1
0x1801dcbcf  mov     r8, rdi; lpString1
0x1801dcbd2  mov     edx, 1; dwCmpFlags
0x1801dcbd7  lea     ecx, [rdx+7Eh]; Locale
0x1801dcbda  call    cs:__imp_CompareStringW
0x1801dcbe0  cmp     eax, 2
0x1801dcbe3  jnz     loc_1801DCC89
0x1801dcbe9  xorps   xmm0, xmm0
0x1801dcbec  xor     eax, eax
0x1801dcbee  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801dcbf3  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801dcbf8  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801dcbfd  call    cs:__imp_VariantInit
0x1801dcc03  mov     rcx, [rbx+80h]
0x1801dcc0a  mov     rax, [rcx]
0x1801dcc0d  lea     r8, [rsp+78h+pvarg]
0x1801dcc12  lea     rdx, aMasksize; "MaskSize"
0x1801dcc19  mov     rax, [rax+60h]
0x1801dcc1d  call    cs:__guard_dispatch_icall_fptr
0x1801dcc23  cmp     eax, 8007000Eh
0x1801dcc28  jz      loc_1801DCEB2
0x1801dcc2e  cmp     eax, 86160210h
0x1801dcc33  jz      loc_1801DCEB2
0x1801dcc39  cmp     eax, 86170103h
0x1801dcc3e  jz      loc_1801DCEB2
0x1801dcc44  cmp     eax, 86180110h
0x1801dcc49  jz      loc_1801DCEB2
0x1801dcc4f  test    eax, eax
0x1801dcc51  js      loc_1801DCEA1
0x1801dcc57  movsd   xmm0, qword ptr [rsp+78h+pvarg+8]
0x1801dcc5d  cvtpd2ps xmm0, xmm0
0x1801dcc61  comiss  xmm0, cs:__real@00000000
0x1801dcc68  jb      loc_1801DCEA8
0x1801dcc6e  ucomiss xmm0, dword ptr [rbx+90h]
0x1801dcc75  jp      short loc_1801DCC79
0x1801dcc77  jz      short loc_1801DCC84
0x1801dcc79  movss   dword ptr [rbx+90h], xmm0
0x1801dcc81  mov     sil, 1
0x1801dcc84  jmp     loc_1801DCE0D
0x1801dcc89  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801dcc8e  lea     rax, aMaskfeather; "MaskFeather"
0x1801dcc95  mov     [rsp+78h+lpString2], rax; lpString2
0x1801dcc9a  mov     r9d, r12d; cchCount1
0x1801dcc9d  mov     r8, rdi; lpString1
0x1801dcca0  mov     edx, 1; dwCmpFlags
0x1801dcca5  lea     ecx, [rdx+7Eh]; Locale
0x1801dcca8  call    cs:__imp_CompareStringW
0x1801dccae  cmp     eax, 2
0x1801dccb1  jnz     loc_1801DCD57
0x1801dccb7  xorps   xmm0, xmm0
0x1801dccba  xor     eax, eax
0x1801dccbc  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801dccc1  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801dccc6  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801dcccb  call    cs:__imp_VariantInit
0x1801dccd1  mov     rcx, [rbx+80h]
0x1801dccd8  mov     rax, [rcx]
0x1801dccdb  lea     r8, [rsp+78h+pvarg]
0x1801dcce0  lea     rdx, aMaskfeather; "MaskFeather"
0x1801dcce7  mov     rax, [rax+60h]
0x1801dcceb  call    cs:__guard_dispatch_icall_fptr
0x1801dccf1  cmp     eax, 8007000Eh
0x1801dccf6  jz      loc_1801DCECE
0x1801dccfc  cmp     eax, 86160210h
0x1801dcd01  jz      loc_1801DCECE
0x1801dcd07  cmp     eax, 86170103h
0x1801dcd0c  jz      loc_1801DCECE
0x1801dcd12  cmp     eax, 86180110h
0x1801dcd17  jz      loc_1801DCECE
0x1801dcd1d  test    eax, eax
0x1801dcd1f  js      loc_1801DCEBD
0x1801dcd25  movsd   xmm0, qword ptr [rsp+78h+pvarg+8]
0x1801dcd2b  cvtpd2ps xmm0, xmm0
0x1801dcd2f  comiss  xmm0, cs:__real@00000000
0x1801dcd36  jb      loc_1801DCEC4
0x1801dcd3c  ucomiss xmm0, dword ptr [rbx+94h]
0x1801dcd43  jp      short loc_1801DCD47
0x1801dcd45  jz      short loc_1801DCD52
0x1801dcd47  movss   dword ptr [rbx+94h], xmm0
0x1801dcd4f  mov     sil, 1
0x1801dcd52  jmp     loc_1801DCE0D
0x1801dcd57  mov     [rsp+78h+cchCount2], r12d; cchCount2
0x1801dcd5c  lea     rax, aIsmaskinverted; "IsMaskInverted"
0x1801dcd63  mov     [rsp+78h+lpString2], rax; lpString2
0x1801dcd68  mov     r9d, r12d; cchCount1
0x1801dcd6b  mov     r8, rdi; lpString1
0x1801dcd6e  mov     edx, 1; dwCmpFlags
0x1801dcd73  lea     ecx, [rdx+7Eh]; Locale
0x1801dcd76  call    cs:__imp_CompareStringW
0x1801dcd7c  cmp     eax, 2
0x1801dcd7f  jnz     loc_1801DCE1D
0x1801dcd85  xorps   xmm0, xmm0
0x1801dcd88  xor     eax, eax
0x1801dcd8a  movups  xmmword ptr [rsp+78h+pvarg], xmm0
0x1801dcd8f  mov     qword ptr [rsp+78h+pvarg+10h], rax
0x1801dcd94  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801dcd99  call    cs:__imp_VariantInit
0x1801dcd9f  mov     rcx, [rbx+80h]
0x1801dcda6  mov     rax, [rcx]
0x1801dcda9  lea     r8, [rsp+78h+pvarg]
0x1801dcdae  lea     rdx, aIsmaskinverted; "IsMaskInverted"
0x1801dcdb5  mov     rax, [rax+60h]
0x1801dcdb9  call    cs:__guard_dispatch_icall_fptr
0x1801dcdbf  cmp     eax, 8007000Eh
0x1801dcdc4  jz      loc_1801DCEF1
0x1801dcdca  cmp     eax, 86160210h
0x1801dcdcf  jz      loc_1801DCEF1
0x1801dcdd5  cmp     eax, 86170103h
0x1801dcdda  jz      loc_1801DCEF1
0x1801dcde0  cmp     eax, 86180110h
0x1801dcde5  jz      loc_1801DCEF1
0x1801dcdeb  test    eax, eax
0x1801dcded  js      loc_1801DCED9
0x1801dcdf3  cmp     word ptr [rsp+78h+pvarg+8], r14w
0x1801dcdf9  setnz   al
0x1801dcdfc  cmp     al, [rbx+9Ch]
0x1801dce02  jz      short loc_1801DCE0D
0x1801dce04  mov     [rbx+9Ch], al
0x1801dce0a  mov     sil, 1
0x1801dce0d  lea     rcx, [rsp+78h+pvarg]; pvarg
0x1801dce12  call    cs:__imp_VariantClear
0x1801dce18  test    sil, sil
0x1801dce1b  jnz     short loc_1801DCE3C
0x1801dce1d  mov     rcx, [rbx+80h]
0x1801dce24  mov     rax, [rcx]
0x1801dce27  mov     rax, [rax+110h]
0x1801dce2e  call    cs:__guard_dispatch_icall_fptr
0x1801dce34  test    eax, eax
0x1801dce36  js      loc_1801DCEE5
0x1801dce3c  xor     eax, eax
0x1801dce3e  jmp     short loc_1801DCE53
0x1801dce40  mov     eax, [rsp+78h+arg_8]
0x1801dce47  mov     edx, 86160101h
0x1801dce4c  cmp     ax, 216h
0x1801dce50  cmovz   eax, edx
0x1801dce53  lea     r11, [rsp+78h+var_18]
0x1801dce58  mov     rbx, [r11+20h]
0x1801dce5c  mov     rsi, [r11+30h]
0x1801dce60  mov     rsp, r11
0x1801dce63  pop     r14
0x1801dce65  pop     r12
0x1801dce67  pop     rdi
0x1801dce68  retn
0x1801dce69  mov     ecx, 80004003h; int
0x1801dce6e  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dce74  jmp     short $+2
0x1801dce76  nop
0x1801dce77  mov     ecx, eax; int
0x1801dce79  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dce7e  mov     ecx, 80070057h; int
0x1801dce83  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dce88  mov     ecx, eax; int
0x1801dce8a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dce90  jmp     short loc_1801DCEA0
0x1801dcea0  nop
0x1801dcea1  mov     ecx, eax; int
0x1801dcea3  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dcea8  mov     ecx, 80070057h; int
0x1801dcead  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dceb2  mov     ecx, eax; int
0x1801dceb4  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dceba  jmp     short $+2
0x1801dcebc  nop
0x1801dcebd  mov     ecx, eax; int
0x1801dcebf  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dcec4  mov     ecx, 80070057h; int
0x1801dcec9  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dcece  mov     ecx, eax; int
0x1801dced0  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dced6  jmp     short $+2
0x1801dced8  nop
0x1801dced9  mov     ecx, eax; int
0x1801dcedb  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dcee1  jmp     short loc_1801DCEE4
0x1801dcee4  nop
0x1801dcee5  mov     ecx, eax; int
0x1801dcee7  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x1801dcef1  mov     ecx, eax; int
0x1801dcef3  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
