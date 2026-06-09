# Appx::Packaging::Manifest::BundlePayloadPackageId::GetPackageFullName(ushort * *)

- ea: `0x1800279b0`
- end: `0x180027be1`
- name: `?GetPackageFullName@BundlePayloadPackageId@Manifest@Packaging@Appx@@UEAAJPEAPEAG@Z`
- size: `561`
- prototype: `__int64 __fastcall(Appx::Packaging::Manifest::BundlePayloadPackageId *__hidden this, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e60e0`

## callees

- `0x1800133fc`
- `0x1800279b0`
- `0x180027bf0`
- `0x180071f50`
- `0x1800992a0`
- `0x18009d729`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027a4b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027b00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027b5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180027b5b`

## string_xrefs

- `0x180027adc`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x180027ab7`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x180027b9a`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x180027bc5`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::BundlePayloadPackageId::GetPackageFullName(
        Appx::Packaging::Manifest::BundlePayloadPackageId *this,
        unsigned __int16 **a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  _WORD *v5; // rax
  __int64 v6; // rcx
  unsigned __int16 *v7; // rbx
  int v8; // edi
  __int64 v9; // r8
  __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  int v15; // [rsp+20h] [rbp-168h] BYREF
  _DWORD v16[2]; // [rsp+28h] [rbp-160h] BYREF
  __int64 v17; // [rsp+30h] [rbp-158h]
  __int64 v18; // [rsp+38h] [rbp-150h]
  __int64 v19; // [rsp+40h] [rbp-148h]
  __int64 v20; // [rsp+48h] [rbp-140h]
  __int64 v21; // [rsp+50h] [rbp-138h]
  _BYTE Src[256]; // [rsp+60h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)0x80004003LL,
      v15);
    return 2147500035LL;
  }
  v18 = *((_QWORD *)this + 5);
  v17 = *((_QWORD *)this + 10);
  v16[1] = *((_DWORD *)this + 22);
  v20 = *((_QWORD *)this + 13);
  v19 = *((_QWORD *)this + 8);
  v15 = 128;
  v16[0] = 0;
  v21 = 0;
  v3 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFullNameFromId(
         (__int64)v16,
         &v15,
         Src);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( (v4 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x144,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)v4,
      v15);
    return v4;
  }
  CoTaskMemFree(0);
  v5 = Src;
  v6 = 0x7FFFFFFF;
  v7 = 0;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v8 = -2147024809;
  if ( !v6 )
  {
    v8 = -2147024809;
    goto LABEL_26;
  }
  v9 = (unsigned int)(0x7FFFFFFF - v6);
  if ( (unsigned int)v9 <= 0x3FFFFFFF )
  {
    v10 = 2 * v9;
    if ( (unsigned __int64)(2 * v9) > 0xFFFFFFFF )
    {
      v11 = 27;
LABEL_14:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        v15);
LABEL_15:
      v8 = -2147024882;
      goto LABEL_16;
    }
    if ( (int)v10 + 2 < (unsigned int)v10 )
    {
      v11 = 29;
      goto LABEL_14;
    }
    v14 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)(v10 + 2));
    v7 = v14;
    if ( !v14 )
    {
      v7 = 0;
      goto LABEL_15;
    }
    memcpy_0(v14, Src, (unsigned int)v10);
    v7[(unsigned __int64)v10 / 2] = 0;
    v8 = 0;
  }
LABEL_16:
  if ( v8 < 0 )
  {
LABEL_26:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)(unsigned int)v8,
      v15);
    v13 = v7;
    goto LABEL_18;
  }
  *a2 = v7;
  v13 = 0;
LABEL_18:
  CoTaskMemFree(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800279b0  mov     r11, rsp
0x1800279b3  push    rsi
0x1800279b4  sub     rsp, 180h
0x1800279bb  mov     rax, cs:__security_cookie
0x1800279c2  xor     rax, rsp
0x1800279c5  mov     [rsp+188h+var_28], rax
0x1800279cd  mov     rsi, rdx
0x1800279d0  test    rdx, rdx
0x1800279d3  jz      loc_180027B92
0x1800279d9  mov     rax, [rcx+28h]
0x1800279dd  lea     r8, [rsp+188h+Src]
0x1800279e2  mov     [rsp+188h+var_150], rax
0x1800279e7  lea     rdx, [rsp+188h+var_168]
0x1800279ec  mov     rax, [rcx+50h]
0x1800279f0  mov     [rsp+188h+var_158], rax
0x1800279f5  mov     eax, [rcx+58h]
0x1800279f8  mov     [rsp+188h+var_15C], eax
0x1800279fc  mov     rax, [rcx+68h]
0x180027a00  mov     [r11+18h], rbx
0x180027a04  mov     [rsp+188h+var_140], rax
0x180027a09  mov     rax, [rcx+40h]
0x180027a0d  lea     rcx, [rsp+188h+var_160]
0x180027a12  mov     [r11-10h], rbp
0x180027a16  xor     ebp, ebp
0x180027a18  mov     [rsp+188h+var_148], rax
0x180027a1d  mov     [rsp+188h+var_168], 80h; int
0x180027a25  mov     [rsp+188h+var_160], ebp
0x180027a29  mov     [rsp+188h+var_138], rbp
0x180027a2e  call    ?PackageFullNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFullNameFromId(PACKAGE_ID const *,uint *,ushort *)
0x180027a33  mov     ebx, eax
0x180027a35  test    eax, eax
0x180027a37  jg      loc_180027B40
0x180027a3d  test    ebx, ebx
0x180027a3f  js      short loc_180027AAF
0x180027a41  xor     ecx, ecx; pv
0x180027a43  mov     [rsp+188h+var_18], rdi
0x180027a4b  call    cs:__imp_CoTaskMemFree
0x180027a52  nop     dword ptr [rax+rax+00h]
0x180027a57  mov     r8d, 7FFFFFFFh
0x180027a5d  lea     rax, [rsp+188h+Src]
0x180027a62  mov     ecx, r8d
0x180027a65  mov     rbx, rbp
0x180027a68  cmp     [rax], bx
0x180027a6b  jz      short loc_180027A77
0x180027a6d  add     rax, 2
0x180027a71  sub     rcx, 1
0x180027a75  jnz     short loc_180027A68
0x180027a77  mov     edi, 80070057h
0x180027a7c  test    rcx, rcx
0x180027a7f  mov     edx, edi
0x180027a81  cmovnz  edx, ebp
0x180027a84  jz      loc_180027BBB
0x180027a8a  sub     r8d, ecx
0x180027a8d  cmp     r8d, 3FFFFFFFh
0x180027a94  ja      short loc_180027AF3
0x180027a96  lea     rdi, [r8+r8]
0x180027a9a  mov     eax, 0FFFFFFFFh
0x180027a9f  cmp     rdi, rax
0x180027aa2  jbe     loc_180027B4E
0x180027aa8  mov     edx, 1Bh
0x180027aad  jmp     short loc_180027AD4
0x180027aaf  mov     rcx, [rsp+188h]; this
0x180027ab7  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027abe  mov     r9d, ebx; char *
0x180027ac1  mov     edx, 144h; void *
0x180027ac6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027acb  mov     eax, ebx
0x180027acd  jmp     short loc_180027B16
0x180027acf  mov     edx, 1Dh; void *
0x180027ad4  mov     rcx, [rsp+188h]; this
0x180027adc  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x180027ae3  mov     r9d, 80070216h; char *
0x180027ae9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027aee  mov     edi, 8007000Eh
0x180027af3  test    edi, edi
0x180027af5  js      loc_180027BBD
0x180027afb  mov     [rsi], rbx
0x180027afe  xor     ecx, ecx; pv
0x180027b00  call    cs:__imp_CoTaskMemFree
0x180027b07  nop     dword ptr [rax+rax+00h]
0x180027b0c  mov     eax, edi
0x180027b0e  mov     rdi, [rsp+188h+var_18]
0x180027b16  mov     rbx, [rsp+188h+arg_10]
0x180027b1e  mov     rbp, [rsp+188h+var_10]
0x180027b26  mov     rcx, [rsp+188h+var_28]
0x180027b2e  xor     rcx, rsp; StackCookie
0x180027b31  call    __security_check_cookie
0x180027b36  add     rsp, 180h
0x180027b3d  pop     rsi
0x180027b3e  retn
0x180027b40  movzx   ebx, ax
0x180027b43  or      ebx, 80070000h
0x180027b49  jmp     loc_180027A3D
0x180027b4e  lea     eax, [rdi+2]
0x180027b51  cmp     eax, edi
0x180027b53  jb      loc_180027ACF
0x180027b59  mov     ecx, eax; cb
0x180027b5b  call    cs:__imp_CoTaskMemAlloc
0x180027b62  nop     dword ptr [rax+rax+00h]
0x180027b67  mov     rbx, rax
0x180027b6a  test    rax, rax
0x180027b6d  jz      short loc_180027B8A
0x180027b6f  mov     r8d, edi; Size
0x180027b72  lea     rdx, [rsp+188h+Src]; Src
0x180027b77  mov     rcx, rax; void *
0x180027b7a  call    memcpy_0
0x180027b7f  mov     [rdi+rbx], bp
0x180027b83  mov     edi, ebp
0x180027b85  jmp     loc_180027AF3
0x180027b8a  mov     rbx, rbp
0x180027b8d  jmp     loc_180027AEE
0x180027b92  mov     rcx, [rsp+188h]; this
0x180027b9a  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027ba1  mov     r9d, 80004003h; char *
0x180027ba7  mov     edx, 135h; void *
0x180027bac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027bb1  mov     eax, 80004003h
0x180027bb6  jmp     loc_180027B26
0x180027bbb  mov     edi, edx
0x180027bbd  mov     rcx, [rsp+188h]; this
0x180027bc5  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027bcc  mov     r9d, edi; char *
0x180027bcf  mov     edx, 14Ch; void *
0x180027bd4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027bd9  mov     rcx, rbx
0x180027bdc  jmp     loc_180027B00
```
