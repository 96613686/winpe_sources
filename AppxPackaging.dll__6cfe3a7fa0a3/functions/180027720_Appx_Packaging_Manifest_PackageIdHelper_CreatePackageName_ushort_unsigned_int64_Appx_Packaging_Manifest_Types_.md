# Appx::Packaging::Manifest::PackageIdHelper::CreatePackageName(ushort *,unsigned __int64,Appx::Packaging::Manifest::Types::AppxPackageArchitecture,ushort *,ushort *,bool,ushort * *)

- ea: `0x180027720`
- end: `0x18002799b`
- name: `?CreatePackageName@PackageIdHelper@Manifest@Packaging@Appx@@SAJPEAG_KUAppxPackageArchitecture@Types@234@00_NPEAPEAG@Z`
- size: `635`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800199a4`
- `0x1800e6090`
- `0x1800e61c0`

## callees

- `0x1800133fc`
- `0x180027040`
- `0x180027720`
- `0x180027bf0`
- `0x180071f50`
- `0x1800992a0`
- `0x18009d729`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800277c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800277c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027879`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800278d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800278d4`

## string_xrefs

- `0x180027855`: `onecore\base\appmodel\common\autocotaskmemstring.cpp`
- `0x180027830`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x180027913`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x18002794f`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`
- `0x18002797f`: `onecore\printscan\appxpackaging\manifest\src\packageidhelper.cpp`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::Manifest::PackageIdHelper::CreatePackageName(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        char a6,
        _QWORD *a7)
{
  int v7; // eax
  unsigned int v8; // ebx
  _WORD *v9; // rax
  __int64 v10; // rcx
  char *v11; // rbx
  int v12; // edi
  __int64 v13; // r8
  __int64 v14; // rdi
  __int64 v15; // rdx
  void *v17; // rcx
  char *v18; // rax
  int v19; // eax
  unsigned int v20; // ebx
  int v21; // [rsp+20h] [rbp-168h] BYREF
  _DWORD v22[2]; // [rsp+28h] [rbp-160h] BYREF
  __int64 v23; // [rsp+30h] [rbp-158h]
  __int64 v24; // [rsp+38h] [rbp-150h]
  __int64 v25; // [rsp+40h] [rbp-148h]
  __int64 v26; // [rsp+48h] [rbp-140h]
  __int64 v27; // [rsp+50h] [rbp-138h]
  _BYTE Src[256]; // [rsp+60h] [rbp-128h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  if ( !a7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)0x80004003LL,
      v21);
    return 2147500035LL;
  }
  v24 = a1;
  v23 = a2;
  v22[1] = a3;
  v21 = 128;
  v22[0] = 0;
  v27 = 0;
  v26 = a4;
  v25 = a5;
  if ( a6 )
  {
    v7 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFullNameFromId(
           (__int64)v22,
           &v21,
           Src);
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( (v8 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
        (const char *)v8,
        v21);
      return v8;
    }
  }
  else
  {
    v19 = ARI::Identity::Convert<unsigned short,unsigned short *,unsigned short const *,PACKAGE_ID>::PackageFamilyNameFromId(
            v22,
            &v21,
            Src);
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( (v20 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
        (const char *)v20,
        v21);
      return v20;
    }
  }
  CoTaskMemFree(0);
  v9 = Src;
  v10 = 0x7FFFFFFF;
  v11 = 0;
  do
  {
    if ( !*v9 )
      break;
    ++v9;
    --v10;
  }
  while ( v10 );
  v12 = -2147024809;
  if ( !v10 )
  {
    v12 = -2147024809;
    goto LABEL_31;
  }
  v13 = (unsigned int)(0x7FFFFFFF - v10);
  if ( (unsigned int)v13 <= 0x3FFFFFFF )
  {
    v14 = 2 * v13;
    if ( (unsigned __int64)(2 * v13) > 0xFFFFFFFF )
    {
      v15 = 27;
LABEL_15:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\appmodel\\common\\autocotaskmemstring.cpp",
        (const char *)0x80070216LL,
        v21);
LABEL_16:
      v12 = -2147024882;
      goto LABEL_17;
    }
    if ( (int)v14 + 2 < (unsigned int)v14 )
    {
      v15 = 29;
      goto LABEL_15;
    }
    v18 = (char *)CoTaskMemAlloc((unsigned int)(v14 + 2));
    v11 = v18;
    if ( !v18 )
    {
      v11 = 0;
      goto LABEL_16;
    }
    memcpy_0(v18, Src, (unsigned int)v14);
    *(_WORD *)&v11[v14] = 0;
    v12 = 0;
  }
LABEL_17:
  if ( v12 < 0 )
  {
LABEL_31:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"onecore\\printscan\\appxpackaging\\manifest\\src\\packageidhelper.cpp",
      (const char *)(unsigned int)v12,
      v21);
    v17 = v11;
    goto LABEL_19;
  }
  *a7 = v11;
  v17 = 0;
LABEL_19:
  CoTaskMemFree(v17);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180027720  mov     r11, rsp
0x180027723  push    rsi
0x180027724  sub     rsp, 180h
0x18002772b  mov     rax, cs:__security_cookie
0x180027732  xor     rax, rsp
0x180027735  mov     [rsp+188h+var_28], rax
0x18002773d  mov     rsi, [rsp+188h+arg_30]
0x180027745  mov     rax, [rsp+188h+arg_20]
0x18002774d  test    rsi, rsi
0x180027750  jz      loc_18002790B
0x180027756  mov     [r11+18h], rbx
0x18002775a  mov     [r11-10h], rbp
0x18002775e  xor     ebp, ebp
0x180027760  mov     [rsp+188h+var_150], rcx
0x180027765  lea     rcx, [rsp+188h+var_160]
0x18002776a  mov     [rsp+188h+var_158], rdx
0x18002776f  lea     rdx, [rsp+188h+var_168]
0x180027774  mov     [rsp+188h+var_15C], r8d
0x180027779  lea     r8, [rsp+188h+Src]
0x18002777e  mov     [rsp+188h+var_168], 80h; int
0x180027786  mov     [rsp+188h+var_160], ebp
0x18002778a  mov     [rsp+188h+var_138], rbp
0x18002778f  mov     [rsp+188h+var_140], r9
0x180027794  mov     [rsp+188h+var_148], rax
0x180027799  cmp     [rsp+188h+arg_28], bpl
0x1800277a1  jz      loc_180027934
0x1800277a7  call    ?PackageFullNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFullNameFromId(PACKAGE_ID const *,uint *,ushort *)
0x1800277ac  mov     ebx, eax
0x1800277ae  test    eax, eax
0x1800277b0  jg      loc_1800278B9
0x1800277b6  test    ebx, ebx
0x1800277b8  js      short loc_180027828
0x1800277ba  xor     ecx, ecx; pv
0x1800277bc  mov     [rsp+188h+var_18], rdi
0x1800277c4  call    cs:__imp_CoTaskMemFree
0x1800277cb  nop     dword ptr [rax+rax+00h]
0x1800277d0  mov     r8d, 7FFFFFFFh
0x1800277d6  lea     rax, [rsp+188h+Src]
0x1800277db  mov     ecx, r8d
0x1800277de  mov     rbx, rbp
0x1800277e1  cmp     [rax], bx
0x1800277e4  jz      short loc_1800277F0
0x1800277e6  add     rax, 2
0x1800277ea  sub     rcx, 1
0x1800277ee  jnz     short loc_1800277E1
0x1800277f0  mov     edi, 80070057h
0x1800277f5  test    rcx, rcx
0x1800277f8  mov     edx, edi
0x1800277fa  cmovnz  edx, ebp
0x1800277fd  jz      loc_180027975
0x180027803  sub     r8d, ecx
0x180027806  cmp     r8d, 3FFFFFFFh
0x18002780d  ja      short loc_18002786C
0x18002780f  lea     rdi, [r8+r8]
0x180027813  mov     eax, 0FFFFFFFFh
0x180027818  cmp     rdi, rax
0x18002781b  jbe     loc_1800278C7
0x180027821  mov     edx, 1Bh
0x180027826  jmp     short loc_18002784D
0x180027828  mov     rcx, [rsp+188h]; this
0x180027830  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027837  mov     r9d, ebx; char *
0x18002783a  mov     edx, 144h; void *
0x18002783f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027844  mov     eax, ebx
0x180027846  jmp     short loc_18002788F
0x180027848  mov     edx, 1Dh; void *
0x18002784d  mov     rcx, [rsp+188h]; this
0x180027855  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\common\\autoco"...
0x18002785c  mov     r9d, 80070216h; char *
0x180027862  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027867  mov     edi, 8007000Eh
0x18002786c  test    edi, edi
0x18002786e  js      loc_180027977
0x180027874  mov     [rsi], rbx
0x180027877  xor     ecx, ecx; pv
0x180027879  call    cs:__imp_CoTaskMemFree
0x180027880  nop     dword ptr [rax+rax+00h]
0x180027885  mov     eax, edi
0x180027887  mov     rdi, [rsp+188h+var_18]
0x18002788f  mov     rbx, [rsp+188h+arg_10]
0x180027897  mov     rbp, [rsp+188h+var_10]
0x18002789f  mov     rcx, [rsp+188h+var_28]
0x1800278a7  xor     rcx, rsp; StackCookie
0x1800278aa  call    __security_check_cookie
0x1800278af  add     rsp, 180h
0x1800278b6  pop     rsi
0x1800278b7  retn
0x1800278b9  movzx   ebx, ax
0x1800278bc  or      ebx, 80070000h
0x1800278c2  jmp     loc_1800277B6
0x1800278c7  lea     eax, [rdi+2]
0x1800278ca  cmp     eax, edi
0x1800278cc  jb      loc_180027848
0x1800278d2  mov     ecx, eax; cb
0x1800278d4  call    cs:__imp_CoTaskMemAlloc
0x1800278db  nop     dword ptr [rax+rax+00h]
0x1800278e0  mov     rbx, rax
0x1800278e3  test    rax, rax
0x1800278e6  jz      short loc_180027903
0x1800278e8  mov     r8d, edi; Size
0x1800278eb  lea     rdx, [rsp+188h+Src]; Src
0x1800278f0  mov     rcx, rax; void *
0x1800278f3  call    memcpy_0
0x1800278f8  mov     [rdi+rbx], bp
0x1800278fc  mov     edi, ebp
0x1800278fe  jmp     loc_18002786C
0x180027903  mov     rbx, rbp
0x180027906  jmp     loc_180027867
0x18002790b  mov     rcx, [rsp+188h]; this
0x180027913  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x18002791a  mov     r9d, 80004003h; char *
0x180027920  mov     edx, 135h; void *
0x180027925  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002792a  mov     eax, 80004003h
0x18002792f  jmp     loc_18002789F
0x180027934  call    ?PackageFamilyNameFromId@?$Convert@GPEAGPEBGUPACKAGE_ID@@@Identity@ARI@@SAJPEBUPACKAGE_ID@@PEAIPEAG@Z; ARI::Identity::Convert<ushort,ushort *,ushort const *,PACKAGE_ID>::PackageFamilyNameFromId(PACKAGE_ID const *,uint *,ushort *)
0x180027939  mov     ebx, eax
0x18002793b  test    eax, eax
0x18002793d  jg      short loc_18002796A
0x18002793f  test    ebx, ebx
0x180027941  jns     loc_1800277BA
0x180027947  mov     rcx, [rsp+188h]; this
0x18002794f  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027956  mov     r9d, ebx; char *
0x180027959  mov     edx, 148h; void *
0x18002795e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027963  mov     eax, ebx
0x180027965  jmp     loc_18002788F
0x18002796a  movzx   ebx, ax
0x18002796d  or      ebx, 80070000h
0x180027973  jmp     short loc_18002793F
0x180027975  mov     edi, edx
0x180027977  mov     rcx, [rsp+188h]; this
0x18002797f  lea     r8, aOnecorePrintsc_149; "onecore\\printscan\\appxpackaging\\mani"...
0x180027986  mov     r9d, edi; char *
0x180027989  mov     edx, 14Ch; void *
0x18002798e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027993  mov     rcx, rbx
0x180027996  jmp     loc_180027879
```
