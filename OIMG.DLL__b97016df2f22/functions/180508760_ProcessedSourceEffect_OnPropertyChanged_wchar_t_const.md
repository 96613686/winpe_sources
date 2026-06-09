# ProcessedSourceEffect::OnPropertyChanged(wchar_t const *)

- ea: `0x180508760`
- end: `0x180508b81`
- name: `?OnPropertyChanged@ProcessedSourceEffect@@UEAAJPEB_W@Z`
- size: `1057`
- prototype: `int(ProcessedSourceEffect *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1804c6944`
- `0x180508760`
- `0x180508b84`
- `0x180509080`
- `0x18056dce0`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1805087ad`
- `KERNEL32!CompareStringW` at `0x180508916`
- `KERNEL32!CompareStringW` at `0x180508a91`
- `KERNEL32!CompareStringW` at `0x180508aea`
- `KERNEL32!CompareStringW` at `0x1805087ad`
- `KERNEL32!CompareStringW` at `0x180508916`
- `KERNEL32!CompareStringW` at `0x180508a91`
- `KERNEL32!CompareStringW` at `0x180508aea`
- `OLEAUT32!__imp_SysFreeString` at `0x180508a6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180508a6b`
- `OLEAUT32!__imp_SysStringLen` at `0x180508996`
- `OLEAUT32!__imp_SysStringLen` at `0x180508996`
- `OLEAUT32!__imp_VariantInit` at `0x1805087d0`
- `OLEAUT32!__imp_VariantInit` at `0x1805087d0`
- `OLEAUT32!__imp_VariantClear` at `0x1805088f0`
- `OLEAUT32!__imp_VariantClear` at `0x1805088f0`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x180508a28`
- `SHLWAPI!SHCreateStreamOnFileW` at `0x180508a28`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ProcessedSourceEffect::OnPropertyChanged(ProcessedSourceEffect *this, const wchar_t *a2)
{
  HRESULT v4; // r12d
  char v5; // r13
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v13; // eax
  VARIANTARG pvarg; // [rsp+50h] [rbp-78h] BYREF
  VARIANTARG v15; // [rsp+70h] [rbp-58h] BYREF
  __int64 *v16; // [rsp+D8h] [rbp+10h] BYREF
  BSTR pbstr; // [rsp+E0h] [rbp+18h] BYREF
  IStream *ppstm; // [rsp+E8h] [rbp+20h] BYREF

  v4 = 0;
  if ( !a2 )
    ATL::BaseAtlThrow(-2147467261);
  v5 = 0;
  if ( CompareStringW(0x7Fu, 1u, a2, -1, L"OutputProfile", -1) != 2 )
  {
    if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Filename", -1) == 2 )
    {
      pbstr = 0;
      v10 = (*(__int64 (__fastcall **)(_QWORD, const WCHAR *, BSTR *))(**((_QWORD **)this + 16) + 88LL))(
              *((_QWORD *)this + 16),
              L"Filename",
              &pbstr);
      if ( v10 == -2147024882 || v10 == -2045378032 || v10 == -2045312765 || v10 == -2045247216 )
        ATL::BaseAtlThrow(v10);
      if ( v10 < 0 )
        ATL::BaseAtlThrow(v10);
      if ( SysStringLen(pbstr) )
      {
        LODWORD(v16) = 0;
        v11 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(**((_QWORD **)this + 16) + 176LL))(
                *((_QWORD *)this + 16),
                &v16);
        if ( v11 == -2147024882 || v11 == -2045378032 || v11 == -2045312765 || v11 == -2045247216 )
          ATL::BaseAtlThrow(v11);
        if ( v11 < 0 )
          ATL::BaseAtlThrow(v11);
        if ( !(_DWORD)v16 )
        {
          ppstm = 0;
          v4 = SHCreateStreamOnFileW(pbstr, 0, &ppstm);
          if ( v4 >= 0 )
            v4 = ProcessedSourceEffect::LoadFromStream(this, (struct IUnknown *)ppstm);
          if ( ppstm )
            ((void (__fastcall *)(IStream *))ppstm->lpVtbl->Release)(ppstm);
        }
      }
      SysFreeString(pbstr);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Orientation", -1) == 2 )
      {
        ProcessedSourceEffect::SetInternalTransform(this);
        return (unsigned int)v4;
      }
      if ( CompareStringW(0x7Fu, 1u, a2, -1, L"Scale", -1) != 2 )
        goto LABEL_41;
      v5 = 1;
    }
    if ( v4 < 0 || v5 )
      return (unsigned int)v4;
    goto LABEL_41;
  }
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 16) + 96LL))(
         *((_QWORD *)this + 16),
         a2,
         &pvarg);
  if ( v6 == -2147024882 || v6 == -2045378032 || v6 == -2045312765 || v6 == -2045247216 )
    ATL::BaseAtlThrow(v6);
  if ( v6 < 0 )
    ATL::BaseAtlThrow(v6);
  v16 = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, __int64 **))(**((_QWORD **)this + 18) + 152LL))(
         *((_QWORD *)this + 18),
         L"ColorProfileEffect",
         &v16);
  if ( v7 < 0 )
    ATL::BaseAtlThrow(v7);
  if ( !v16 )
    ATL::BaseAtlThrow(-2045247222);
  (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
  v8 = *v16;
  v15 = pvarg;
  v9 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(v8 + 104))(
         v16,
         L"DestinationColorProfile",
         &v15);
  if ( v9 == -2147024882 || v9 == -2045378032 || v9 == -2045312765 || v9 == -2045247216 )
    ATL::BaseAtlThrow(v9);
  if ( v9 < 0 )
    ATL::BaseAtlThrow(v9);
  VariantClear(&pvarg);
LABEL_41:
  v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 272LL))(*((_QWORD *)this + 16));
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180508760  push    rbx
0x180508762  push    rsi
0x180508763  push    rdi
0x180508764  push    r12
0x180508766  push    r13
0x180508768  push    r14
0x18050876a  push    r15
0x18050876c  sub     rsp, 90h
0x180508773  mov     rbx, rdx
0x180508776  mov     r15, rcx
0x180508779  xor     r12d, r12d
0x18050877c  test    rdx, rdx
0x18050877f  jz      loc_180508B24
0x180508785  xor     r13b, r13b
0x180508788  or      edi, 0FFFFFFFFh
0x18050878b  mov     [rsp+0C8h+cchCount2], edi; cchCount2
0x18050878f  lea     rax, aOutputprofile; "OutputProfile"
0x180508796  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050879b  mov     r9d, edi; cchCount1
0x18050879e  mov     r8, rbx; lpString1
0x1805087a1  lea     esi, [rdi+2]
0x1805087a4  mov     edx, esi; dwCmpFlags
0x1805087a6  lea     r14d, [rsi+7Eh]
0x1805087aa  mov     ecx, r14d; Locale
0x1805087ad  call    cs:__imp_CompareStringW
0x1805087b3  cmp     eax, 2
0x1805087b6  jnz     loc_1805088FB
0x1805087bc  xorps   xmm0, xmm0
0x1805087bf  xor     eax, eax
0x1805087c1  movups  xmmword ptr [rsp+0C8h+pvarg], xmm0
0x1805087c6  mov     qword ptr [rsp+0C8h+pvarg+10h], rax
0x1805087cb  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1805087d0  call    cs:__imp_VariantInit
0x1805087d6  mov     rcx, [r15+80h]
0x1805087dd  mov     rax, [rcx]
0x1805087e0  lea     r8, [rsp+0C8h+pvarg]
0x1805087e5  mov     rdx, rbx
0x1805087e8  mov     rax, [rax+60h]
0x1805087ec  call    cs:__guard_dispatch_icall_fptr
0x1805087f2  mov     ebx, 8007000Eh
0x1805087f7  cmp     eax, ebx
0x1805087f9  jz      loc_180508B58
0x1805087ff  mov     edi, 86160210h
0x180508804  cmp     eax, edi
0x180508806  jz      loc_180508B58
0x18050880c  mov     esi, 86170103h
0x180508811  cmp     eax, esi
0x180508813  jz      loc_180508B58
0x180508819  mov     r14d, 86180110h
0x18050881f  cmp     eax, r14d
0x180508822  jz      loc_180508B58
0x180508828  test    eax, eax
0x18050882a  js      loc_180508B32
0x180508830  mov     [rsp+0C8h+arg_8], 0
0x18050883c  mov     rcx, [r15+90h]
0x180508843  mov     rax, [rcx]
0x180508846  lea     r8, [rsp+0C8h+arg_8]
0x18050884e  lea     rdx, aColorprofileef; "ColorProfileEffect"
0x180508855  mov     rax, [rax+98h]
0x18050885c  call    cs:__guard_dispatch_icall_fptr
0x180508862  test    eax, eax
0x180508864  js      loc_180508B39
0x18050886a  mov     rcx, [rsp+0C8h+arg_8]
0x180508872  test    rcx, rcx
0x180508875  jz      loc_180508B40
0x18050887b  mov     rax, [rcx]
0x18050887e  mov     rax, [rax+10h]
0x180508882  call    cs:__guard_dispatch_icall_fptr
0x180508888  mov     rcx, [rsp+0C8h+arg_8]
0x180508890  mov     rax, [rcx]
0x180508893  movups  xmm0, xmmword ptr [rsp+0C8h+pvarg]
0x180508898  movaps  [rsp+0C8h+var_58], xmm0
0x18050889d  movsd   xmm1, qword ptr [rsp+0C8h+pvarg+10h]
0x1805088a3  movsd   [rsp+0C8h+var_48], xmm1
0x1805088ac  lea     r8, [rsp+0C8h+var_58]
0x1805088b1  lea     rdx, aDestinationcol; "DestinationColorProfile"
0x1805088b8  mov     rax, [rax+68h]
0x1805088bc  call    cs:__guard_dispatch_icall_fptr
0x1805088c2  cmp     eax, ebx
0x1805088c4  jz      loc_180508B51
0x1805088ca  cmp     eax, edi
0x1805088cc  jz      loc_180508B51
0x1805088d2  cmp     eax, esi
0x1805088d4  jz      loc_180508B51
0x1805088da  cmp     eax, r14d
0x1805088dd  jz      loc_180508B51
0x1805088e3  test    eax, eax
0x1805088e5  js      loc_180508B4A
0x1805088eb  lea     rcx, [rsp+0C8h+pvarg]; pvarg
0x1805088f0  call    cs:__imp_VariantClear
0x1805088f6  jmp     loc_180508B02
0x1805088fb  mov     [rsp+0C8h+cchCount2], edi; cchCount2
0x1805088ff  lea     rax, aFilename; "Filename"
0x180508906  mov     [rsp+0C8h+lpString2], rax; lpString2
0x18050890b  mov     r9d, edi; cchCount1
0x18050890e  mov     r8, rbx; lpString1
0x180508911  mov     edx, esi; dwCmpFlags
0x180508913  mov     ecx, r14d; Locale
0x180508916  call    cs:__imp_CompareStringW
0x18050891c  cmp     eax, 2
0x18050891f  jnz     loc_180508A76
0x180508925  mov     [rsp+0C8h+pbstr], r12
0x18050892d  mov     rcx, [r15+80h]
0x180508934  mov     rax, [rcx]
0x180508937  lea     r8, [rsp+0C8h+pbstr]
0x18050893f  lea     rdx, aFilename; "Filename"
0x180508946  mov     rax, [rax+58h]
0x18050894a  call    cs:__guard_dispatch_icall_fptr
0x180508950  mov     ebx, 8007000Eh
0x180508955  cmp     eax, ebx
0x180508957  jz      loc_180508B78
0x18050895d  mov     edi, 86160210h
0x180508962  cmp     eax, edi
0x180508964  jz      loc_180508B78
0x18050896a  mov     esi, 86170103h
0x18050896f  cmp     eax, esi
0x180508971  jz      loc_180508B78
0x180508977  mov     r14d, 86180110h
0x18050897d  cmp     eax, r14d
0x180508980  jz      loc_180508B78
0x180508986  test    eax, eax
0x180508988  js      loc_180508B63
0x18050898e  mov     rcx, [rsp+0C8h+pbstr]; pbstr
0x180508996  call    cs:__imp_SysStringLen
0x18050899c  test    eax, eax
0x18050899e  jz      loc_180508A63
0x1805089a4  mov     dword ptr [rsp+0C8h+arg_8], 0
0x1805089af  mov     rcx, [r15+80h]
0x1805089b6  mov     rax, [rcx]
0x1805089b9  lea     rdx, [rsp+0C8h+arg_8]
0x1805089c1  mov     rax, [rax+0B0h]
0x1805089c8  call    cs:__guard_dispatch_icall_fptr
0x1805089ce  cmp     eax, ebx
0x1805089d0  jz      loc_180508B71
0x1805089d6  cmp     eax, edi
0x1805089d8  jz      loc_180508B71
0x1805089de  cmp     eax, esi
0x1805089e0  jz      loc_180508B71
0x1805089e6  cmp     eax, r14d
0x1805089e9  jz      loc_180508B71
0x1805089ef  test    eax, eax
0x1805089f1  js      loc_180508B6A
0x1805089f7  cmp     dword ptr [rsp+0C8h+arg_8], 0
0x1805089ff  jnz     short loc_180508A63
0x180508a01  mov     [rsp+0C8h+var_90], 0
0x180508a0a  mov     [rsp+0C8h+ppstm], 0
0x180508a16  lea     r8, [rsp+0C8h+ppstm]; ppstm
0x180508a1e  xor     edx, edx; grfMode
0x180508a20  mov     rcx, [rsp+0C8h+pbstr]; pszFile
0x180508a28  call    cs:__imp_SHCreateStreamOnFileW
0x180508a2e  mov     r12d, eax
0x180508a31  test    eax, eax
0x180508a33  js      short loc_180508A48
0x180508a35  mov     rdx, [rsp+0C8h+ppstm]; struct IUnknown *
0x180508a3d  mov     rcx, r15; this
0x180508a40  call    ?LoadFromStream@ProcessedSourceEffect@@AEAAJPEAUIUnknown@@@Z; ProcessedSourceEffect::LoadFromStream(IUnknown *)
0x180508a45  mov     r12d, eax
0x180508a48  mov     rcx, [rsp+0C8h+ppstm]
0x180508a50  test    rcx, rcx
0x180508a53  jz      short loc_180508A63
0x180508a55  mov     rax, [rcx]
0x180508a58  mov     rax, [rax+10h]
0x180508a5c  call    cs:__guard_dispatch_icall_fptr
0x180508a62  nop
0x180508a63  mov     rcx, [rsp+0C8h+pbstr]; bstrString
0x180508a6b  call    cs:__imp_SysFreeString
0x180508a71  jmp     loc_180508AF8
0x180508a76  mov     [rsp+0C8h+cchCount2], edi; cchCount2
0x180508a7a  lea     rax, aOrientation; "Orientation"
0x180508a81  mov     [rsp+0C8h+lpString2], rax; lpString2
0x180508a86  mov     r9d, edi; cchCount1
0x180508a89  mov     r8, rbx; lpString1
0x180508a8c  mov     edx, esi; dwCmpFlags
0x180508a8e  mov     ecx, r14d; Locale
0x180508a91  call    cs:__imp_CompareStringW
0x180508a97  cmp     eax, 2
0x180508a9a  jnz     short loc_180508ACF
0x180508a9c  mov     rcx, r15; this
0x180508a9f  call    ?SetInternalTransform@ProcessedSourceEffect@@AEAAXXZ; ProcessedSourceEffect::SetInternalTransform(void)
0x180508aa4  mov     eax, r12d
0x180508aa7  jmp     short loc_180508ABC
0x180508aa9  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180508ab0  mov     edx, 86160101h
0x180508ab5  cmp     ax, 216h
0x180508ab9  cmovz   eax, edx
0x180508abc  add     rsp, 90h
0x180508ac3  pop     r15
0x180508ac5  pop     r14
0x180508ac7  pop     r13
0x180508ac9  pop     r12
0x180508acb  pop     rdi
0x180508acc  pop     rsi
0x180508acd  pop     rbx
0x180508ace  retn
0x180508acf  mov     [rsp+0C8h+cchCount2], edi; cchCount2
0x180508ad3  lea     rax, aScale_0; "Scale"
0x180508ada  mov     [rsp+0C8h+lpString2], rax; lpString2
0x180508adf  mov     r9d, edi; cchCount1
0x180508ae2  mov     r8, rbx; lpString1
0x180508ae5  mov     edx, esi; dwCmpFlags
0x180508ae7  mov     ecx, r14d; Locale
0x180508aea  call    cs:__imp_CompareStringW
0x180508af0  cmp     eax, 2
0x180508af3  jnz     short loc_180508B02
0x180508af5  mov     r13b, sil
0x180508af8  test    r12d, r12d
0x180508afb  js      short loc_180508AA4
0x180508afd  test    r13b, r13b
0x180508b00  jnz     short loc_180508AA4
0x180508b02  mov     rcx, [r15+80h]
0x180508b09  mov     rax, [rcx]
0x180508b0c  mov     rax, [rax+110h]
0x180508b13  call    cs:__guard_dispatch_icall_fptr
0x180508b19  test    eax, eax
0x180508b1b  jns     short loc_180508AA4
0x180508b1d  mov     ecx, eax; int
0x180508b1f  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b24  mov     ecx, 80004003h; int
0x180508b29  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b2f  jmp     short $+2
0x180508b31  nop
0x180508b32  mov     ecx, eax; int
0x180508b34  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b39  mov     ecx, eax; int
0x180508b3b  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b40  mov     ecx, 8618010Ah; int
0x180508b45  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b4a  mov     ecx, eax; int
0x180508b4c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b51  mov     ecx, eax; int
0x180508b53  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b58  mov     ecx, eax; int
0x180508b5a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b60  jmp     short $+2
0x180508b62  nop
0x180508b63  mov     ecx, eax; int
0x180508b65  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b6a  mov     ecx, eax; int
0x180508b6c  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b71  mov     ecx, eax; int
0x180508b73  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180508b78  mov     ecx, eax; int
0x180508b7a  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
