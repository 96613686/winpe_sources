# OSIntegration::Tools::MoCOMHelper::FixACIDAliasProperty(void)

- ea: `0x180014e24`
- end: `0x18001520d`
- name: `?FixACIDAliasProperty@MoCOMHelper@Tools@OSIntegration@@AEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(OSIntegration::Tools::MoCOMHelper *__hidden this)`
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005f50`
- `0x180006258`
- `0x180014d50`

## callees

- `0x1800138e0`
- `0x180014e24`
- `0x180015eb8`
- `0x18003a300`
- `0x180085310`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0700`
- `0x1800f073c`
- `0x1800f0760`
- `0x1800fc229`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001506b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18001506b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001503c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180014e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001503c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001501c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001502b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015140`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001501c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001502b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015053`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800150d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015131`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015140`

## string_xrefs

- `0x180014fd2`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180015002`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800150f5`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x180015117`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800151e1`: `onecore\admin\appmodel\osim\src\deh\appx\common\mocomhelper.cpp`
- `0x1800151a4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x1800151bc`: `onecore\admin\appmodel\osim\src\deh\appx\common\MoCOMHelper.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSIntegration::Tools::MoCOMHelper::FixACIDAliasProperty(OSIntegration::Tools::MoCOMHelper *this)
{
  HSTRING v2; // rbx
  HRESULT v3; // eax
  unsigned int v4; // edi
  HSTRING v5; // rdi
  unsigned __int64 i; // r14
  const WCHAR *v7; // rcx
  unsigned __int64 v8; // rdx
  HRESULT v9; // esi
  _DWORD *v10; // rsi
  HSTRING v11; // r12
  __int64 v12; // rcx
  const WCHAR *v13; // rax
  unsigned int v14; // r8d
  int v15; // r14d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // r14
  void *v19; // rax
  void *v20; // r12
  HSTRING v22; // rcx
  const void *v23; // rdx
  unsigned __int64 v24; // rdx
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  HSTRING string; // [rsp+68h] [rbp+48h] BYREF
  HSTRING v29; // [rsp+70h] [rbp+50h] BYREF
  HSTRING v30; // [rsp+78h] [rbp+58h] BYREF

  v2 = 0;
  v30 = 0;
  v29 = 0;
  string = 0;
  v3 = WindowsCreateString(L"AppObject.Aliased", 0x11u, &string);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x48B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
      (const char *)(unsigned int)v3,
      savedregs);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v29);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v30);
    return v4;
  }
  v5 = string;
  v29 = string;
  WindowsDeleteString(0);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((_QWORD *)this + 67) )
    {
      v10 = 0;
      string = 0;
      v11 = (HSTRING)operator new(0x20u);
      string = v11;
      *(_DWORD *)v11 = 0;
      *((_QWORD *)v11 + 3) = 0;
      *(_OWORD *)(v11 + 2) = 0;
      v12 = 1073741822;
      v13 = L"AppObject.Aliased";
      while ( *v13 )
      {
        ++v13;
        if ( !--v12 )
        {
          v14 = 0;
          v15 = -2147024809;
          goto LABEL_14;
        }
      }
      v15 = 0;
      v14 = 1073741822 - v12;
LABEL_14:
      if ( v15 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x249,
          (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
          (const char *)(unsigned int)v15,
          savedregs);
      }
      else
      {
        v15 = Common::StringBuffer::SetValue((Common::StringBuffer *)(v11 + 2), L"AppObject.Aliased", v14);
        if ( v15 >= 0 )
        {
          v10 = v11;
          v15 = 0;
          goto LABEL_17;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\MoCOMHelper.hpp",
        (const char *)(unsigned int)v15,
        savedregs);
      Common::AutoPtrDeallocate<OSIntegration::Tools::Internal::Property<unsigned long>>(v11);
LABEL_17:
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
          (const char *)(unsigned int)v15,
          savedregs);
        if ( !v10 )
          goto LABEL_50;
        goto LABEL_29;
      }
      *v10 = 1;
      v16 = *((_QWORD *)this + 55) + 1LL;
      v17 = *((_QWORD *)this + 54);
      if ( v16 > v17 )
      {
        if ( v17 == 0x3FFFFFFF )
        {
          v15 = -2147483637;
          goto LABEL_28;
        }
        if ( v17 )
          v18 = ((3 * v17) >> 1) + 1;
        else
          v18 = 16;
        if ( v16 > v18 )
          v18 = *((_QWORD *)this + 55) + 1LL;
        if ( v18 > 0x3FFFFFFF )
          v18 = 0x3FFFFFFF;
        v19 = operator new[](8 * v18, (const struct std::nothrow_t *)std::nothrow);
        v20 = v19;
        if ( !v19 )
        {
          v15 = -2147024882;
LABEL_28:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC3,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
            (const char *)(unsigned int)v15,
            savedregs);
LABEL_29:
          OSIntegration::Tools::Internal::Property<unsigned long>::`scalar deleting destructor'(v10);
LABEL_50:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x49D,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
            (const char *)(unsigned int)v15,
            savedregsa);
          if ( v5 )
            WindowsDeleteString(v5);
          if ( v2 )
            WindowsDeleteString(v2);
          return (unsigned int)v15;
        }
        v23 = (const void *)*((_QWORD *)this + 53);
        if ( v23 )
        {
          memmove_0(v19, v23, 8LL * *((_QWORD *)this + 55));
          operator delete(*((void **)this + 53), v24);
        }
        *((_QWORD *)this + 53) = v20;
        *((_QWORD *)this + 54) = v18;
      }
      *(_QWORD *)(*((_QWORD *)this + 53) + 8LL * (*((_QWORD *)this + 55))++) = v10;
      if ( v5 )
        WindowsDeleteString(v5);
      if ( v2 )
        WindowsDeleteString(v2);
      return 0;
    }
    v7 = *(const WCHAR **)(*(_QWORD *)(*((_QWORD *)this + 65) + 8 * i) + 32LL);
    if ( !v7 )
      break;
    string = 0;
    v8 = -1;
    do
      ++v8;
    while ( v7[v8] );
    if ( v8 <= 0xFFFFFFFF )
    {
      v9 = WindowsCreateString(v7, v8, &string);
      if ( v9 >= 0 )
      {
        v22 = v2;
        v2 = string;
        v30 = string;
        WindowsDeleteString(v22);
      }
    }
    else
    {
      v9 = -2147024362;
    }
    if ( v9 < 0 )
      goto LABEL_31;
    LODWORD(string) = 0;
    WindowsCompareStringOrdinal(v2, v5, (INT32 *)&string);
    if ( !(_DWORD)string )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v29);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v30);
      return 0;
    }
  }
  v9 = -2147467261;
LABEL_31:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x492,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\common\\mocomhelper.cpp",
    (const char *)(unsigned int)v9,
    savedregs);
  if ( v5 )
    WindowsDeleteString(v5);
  if ( v2 )
    WindowsDeleteString(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180014e24  mov     [rsp-38h+arg_0], rbx
0x180014e29  push    rbp
0x180014e2a  push    rsi
0x180014e2b  push    rdi
0x180014e2c  push    r12
0x180014e2e  push    r13
0x180014e30  push    r14
0x180014e32  push    r15; int
0x180014e34  mov     rbp, rsp
0x180014e37  sub     rsp, 20h
0x180014e3b  mov     r15, rcx
0x180014e3e  xor     r13d, r13d
0x180014e41  mov     ebx, r13d
0x180014e44  mov     [rbp+arg_18], rbx
0x180014e48  mov     [rbp+arg_10], r13
0x180014e4c  mov     [rbp+string], r13
0x180014e50  lea     r8, [rbp+string]; string
0x180014e54  lea     edx, [r13+11h]; length
0x180014e58  lea     rcx, aAppobjectAlias; "AppObject.Aliased"
0x180014e5f  call    cs:__imp_WindowsCreateString
0x180014e65  mov     edi, eax
0x180014e67  test    eax, eax
0x180014e69  js      loc_1800151DA
0x180014e6f  mov     rdi, [rbp+string]
0x180014e73  mov     [rbp+arg_10], rdi
0x180014e77  xor     ecx, ecx; string
0x180014e79  call    cs:__imp_WindowsDeleteString
0x180014e7f  mov     r14d, r13d
0x180014e82  cmp     r14, [r15+218h]
0x180014e89  jnb     short loc_180014ECD
0x180014e8b  mov     rax, [r15+208h]
0x180014e92  mov     rcx, [rax+r14*8]
0x180014e96  mov     rcx, [rcx+20h]; sourceString
0x180014e9a  test    rcx, rcx
0x180014e9d  jz      loc_180014FF6
0x180014ea3  mov     [rbp+string], r13
0x180014ea7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180014eab  inc     rdx; length
0x180014eae  cmp     [rcx+rdx*2], r13w
0x180014eb3  jnz     short loc_180014EAB
0x180014eb5  mov     eax, 0FFFFFFFFh
0x180014eba  cmp     rdx, rax
0x180014ebd  jbe     loc_180015038
0x180014ec3  mov     esi, 80070216h
0x180014ec8  jmp     loc_180015059
0x180014ecd  mov     rsi, r13
0x180014ed0  mov     [rbp+string], r13
0x180014ed4  mov     ecx, 20h ; ' '; Size
0x180014ed9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014ede  mov     r12, rax
0x180014ee1  mov     [rbp+string], rax
0x180014ee5  mov     [rax], r13d
0x180014ee8  mov     [rax+18h], r13
0x180014eec  xorps   xmm0, xmm0
0x180014eef  movups  xmmword ptr [rax+8], xmm0
0x180014ef3  mov     r8d, 3FFFFFFEh
0x180014ef9  mov     ecx, r8d
0x180014efc  lea     rax, aAppobjectAlias; "AppObject.Aliased"
0x180014f03  cmp     [rax], r13w
0x180014f07  jz      short loc_180014F1E
0x180014f09  add     rax, 2
0x180014f0d  sub     rcx, 1
0x180014f11  jnz     short loc_180014F03
0x180014f13  mov     r8, r13
0x180014f16  mov     r14d, 80070057h
0x180014f1c  jmp     short loc_180014F24
0x180014f1e  mov     r14d, r13d
0x180014f21  sub     r8, rcx; unsigned int
0x180014f24  mov     rcx, [rbp+38h]; this
0x180014f28  test    r14d, r14d
0x180014f2b  js      loc_1800151A1
0x180014f31  lea     rdx, aAppobjectAlias; "AppObject.Aliased"
0x180014f38  lea     rcx, [r12+8]; this
0x180014f3d  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x180014f42  mov     r14d, eax
0x180014f45  test    eax, eax
0x180014f47  js      loc_1800151B5
0x180014f4d  mov     rsi, r12
0x180014f50  mov     r14d, r13d
0x180014f53  test    r14d, r14d
0x180014f56  js      loc_1800150EE
0x180014f5c  mov     dword ptr [rsi], 1
0x180014f62  mov     rcx, [r15+1B8h]
0x180014f69  inc     rcx
0x180014f6c  mov     rax, [r15+1B0h]
0x180014f73  cmp     rcx, rax
0x180014f76  jbe     loc_1800150A1
0x180014f7c  mov     edx, 3FFFFFFFh
0x180014f81  cmp     rax, rdx
0x180014f84  jz      loc_18001514B
0x180014f8a  test    rax, rax
0x180014f8d  jnz     loc_180015156
0x180014f93  lea     r14d, [rax+10h]
0x180014f97  cmp     rcx, r14
0x180014f9a  cmova   r14, rcx
0x180014f9e  cmp     r14, rdx
0x180014fa1  cmova   r14, rdx
0x180014fa5  lea     rcx, ds:0[r14*8]; unsigned __int64
0x180014fad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014fb4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014fb9  mov     r12, rax
0x180014fbc  test    rax, rax
0x180014fbf  jnz     loc_180015083
0x180014fc5  mov     r14d, 8007000Eh
0x180014fcb  mov     rcx, [rbp+38h]; this
0x180014fcf  mov     r9d, r14d; char *
0x180014fd2  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014fd9  mov     edx, 0C3h; void *
0x180014fde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014fe3  nop
0x180014fe4  mov     edx, 1
0x180014fe9  mov     rcx, rsi; void *
0x180014fec  call    ??_G?$Property@K@Internal@Tools@OSIntegration@@QEAAPEAXI@Z; OSIntegration::Tools::Internal::Property<ulong>::`scalar deleting destructor'(uint)
0x180014ff1  jmp     loc_180015110
0x180014ff6  mov     esi, 80004003h
0x180014ffb  mov     rcx, [rbp+38h]; this
0x180014fff  mov     r9d, esi; char *
0x180015002  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180015009  mov     edx, 492h; void *
0x18001500e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015013  nop
0x180015014  test    rdi, rdi
0x180015017  jz      short loc_180015023
0x180015019  mov     rcx, rdi; string
0x18001501c  call    cs:__imp_WindowsDeleteString
0x180015022  nop
0x180015023  test    rbx, rbx
0x180015026  jz      short loc_180015031
0x180015028  mov     rcx, rbx; string
0x18001502b  call    cs:__imp_WindowsDeleteString
0x180015031  mov     eax, esi
0x180015033  jmp     loc_1800150D9
0x180015038  lea     r8, [rbp+string]; string
0x18001503c  call    cs:__imp_WindowsCreateString
0x180015042  mov     esi, eax
0x180015044  test    eax, eax
0x180015046  js      short loc_180015059
0x180015048  mov     rcx, rbx; string
0x18001504b  mov     rbx, [rbp+string]
0x18001504f  mov     [rbp+arg_18], rbx
0x180015053  call    cs:__imp_WindowsDeleteString
0x180015059  test    esi, esi
0x18001505b  js      short loc_180014FFB
0x18001505d  mov     dword ptr [rbp+string], r13d
0x180015061  lea     r8, [rbp+string]; result
0x180015065  mov     rdx, rdi; string2
0x180015068  mov     rcx, rbx; string1
0x18001506b  call    cs:__imp_WindowsCompareStringOrdinal
0x180015071  cmp     dword ptr [rbp+string], r13d
0x180015075  jz      loc_180015189
0x18001507b  inc     r14
0x18001507e  jmp     loc_180014E82
0x180015083  mov     rdx, [r15+1A8h]; Src
0x18001508a  test    rdx, rdx
0x18001508d  jnz     loc_180015165
0x180015093  mov     [r15+1A8h], r12
0x18001509a  mov     [r15+1B0h], r14
0x1800150a1  mov     rcx, [r15+1B8h]
0x1800150a8  mov     rax, [r15+1A8h]
0x1800150af  mov     [rax+rcx*8], rsi
0x1800150b3  inc     qword ptr [r15+1B8h]
0x1800150ba  test    rdi, rdi
0x1800150bd  jz      short loc_1800150C9
0x1800150bf  mov     rcx, rdi; string
0x1800150c2  call    cs:__imp_WindowsDeleteString
0x1800150c8  nop
0x1800150c9  test    rbx, rbx
0x1800150cc  jz      short loc_1800150D7
0x1800150ce  mov     rcx, rbx; string
0x1800150d1  call    cs:__imp_WindowsDeleteString
0x1800150d7  xor     eax, eax
0x1800150d9  mov     rbx, [rsp+20h+arg_0]
0x1800150de  add     rsp, 20h
0x1800150e2  pop     r15
0x1800150e4  pop     r14
0x1800150e6  pop     r13
0x1800150e8  pop     r12
0x1800150ea  pop     rdi
0x1800150eb  pop     rsi
0x1800150ec  pop     rbp
0x1800150ed  retn
0x1800150ee  mov     rcx, [rbp+38h]; this
0x1800150f2  mov     r9d, r14d; char *
0x1800150f5  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800150fc  mov     edx, 0BFh; void *
0x180015101  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015106  nop
0x180015107  test    rsi, rsi
0x18001510a  jnz     loc_180014FE4
0x180015110  mov     rcx, [rbp+38h]; this
0x180015114  mov     r9d, r14d; char *
0x180015117  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18001511e  mov     edx, 49Dh; void *
0x180015123  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015128  nop
0x180015129  test    rdi, rdi
0x18001512c  jz      short loc_180015138
0x18001512e  mov     rcx, rdi; string
0x180015131  call    cs:__imp_WindowsDeleteString
0x180015137  nop
0x180015138  test    rbx, rbx
0x18001513b  jz      short loc_180015146
0x18001513d  mov     rcx, rbx; string
0x180015140  call    cs:__imp_WindowsDeleteString
0x180015146  mov     eax, r14d
0x180015149  jmp     short loc_1800150D9
0x18001514b  mov     r14d, 8000000Bh
0x180015151  jmp     loc_180014FCB
0x180015156  lea     r14, [rax+rax*2]
0x18001515a  shr     r14, 1
0x18001515d  inc     r14
0x180015160  jmp     loc_180014F97
0x180015165  mov     r8, [r15+1B8h]
0x18001516c  shl     r8, 3; Size
0x180015170  mov     rcx, r12; void *
0x180015173  call    memmove_0
0x180015178  mov     rcx, [r15+1A8h]; void *
0x18001517f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180015184  jmp     loc_180015093
0x180015189  lea     rcx, [rbp+arg_10]
0x18001518d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180015192  nop
0x180015193  lea     rcx, [rbp+arg_18]
0x180015197  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18001519c  jmp     loc_1800150D7
0x1800151a1  mov     r9d, r14d; char *
0x1800151a4  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appmodel\\common\\widest"...
0x1800151ab  mov     edx, 249h; void *
0x1800151b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800151b5  mov     rcx, [rbp+38h]; this
0x1800151b9  mov     r9d, r14d; char *
0x1800151bc  lea     r8, aOnecoreAdminAp_3; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800151c3  mov     edx, 27h ; '''; void *
0x1800151c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800151cd  mov     rcx, r12
0x1800151d0  call    ??$AutoPtrDeallocate@V?$Property@K@Internal@Tools@OSIntegration@@@Common@@YAXPEAV?$Property@K@Internal@Tools@OSIntegration@@@Z; Common::AutoPtrDeallocate<OSIntegration::Tools::Internal::Property<ulong>>(OSIntegration::Tools::Internal::Property<ulong> *)
0x1800151d5  jmp     loc_180014F53
0x1800151da  mov     rcx, [rbp+38h]; this
0x1800151de  mov     r9d, edi; char *
0x1800151e1  lea     r8, aOnecoreAdminAp_122; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800151e8  mov     edx, 48Bh; void *
0x1800151ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800151f2  nop
0x1800151f3  lea     rcx, [rbp+arg_10]
0x1800151f7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x1800151fc  nop
0x1800151fd  lea     rcx, [rbp+arg_18]
0x180015201  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180015206  mov     eax, edi
0x180015208  jmp     loc_1800150D9
```
