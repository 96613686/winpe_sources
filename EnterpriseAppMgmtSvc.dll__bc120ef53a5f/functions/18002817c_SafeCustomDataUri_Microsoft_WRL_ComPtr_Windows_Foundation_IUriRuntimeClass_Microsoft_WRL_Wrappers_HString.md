# SafeCustomDataUri(Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>,Microsoft::WRL::Wrappers::HString *)

- ea: `0x18002817c`
- end: `0x180028512`
- name: `?SafeCustomDataUri@@YAJV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@23@@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180025cec`

## callees

- `0x180002fb4`
- `0x18000d3dc`
- `0x180020c7c`
- `0x1800246b8`
- `0x18002817c`
- `0x180070010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800281d7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002826b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028313`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028337`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028393`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028458`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002847c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800284ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800284d2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800281d7`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002826b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028313`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028337`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028393`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180028458`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002847c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800284ae`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800284d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002841e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002841e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800282cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800282cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028216`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028258`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028324`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028380`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800283e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028402`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180028469`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800284bf`

## string_xrefs

- `0x1800281c3`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180028242`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800282f8`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002836a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002843d`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SafeCustomDataUri(__int64 *a1, HSTRING *a2)
{
  void *v4; // rbx
  __int64 v5; // rcx
  __int64 v7; // rsi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rdi
  int v9; // eax
  unsigned int v10; // edi
  __int64 v11; // rcx
  int ScratchDirectory; // eax
  int i; // esi
  const WCHAR *StringRawBuffer; // rax
  int SafeSource; // eax
  unsigned int v16; // esi
  __int64 v17; // rcx
  __int64 v18; // rcx
  void *v19; // rsi
  unsigned __int64 v20; // r15
  UINT32 v21; // edx
  const WCHAR *v22; // rcx
  int v23; // r15d
  HRESULT v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int128 v27; // [rsp+20h] [rbp-20h] BYREF
  int v28; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  HSTRING string; // [rsp+90h] [rbp+50h] BYREF
  void *v31; // [rsp+98h] [rbp+58h]

  v4 = operator new[](0x208u);
  v31 = v4;
  if ( v4 )
  {
    string = 0;
    v7 = *a1;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*a1 + 128LL);
    WindowsDeleteString(0);
    string = 0;
    v9 = v8(v7, &string);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF0,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v9,
        v27);
      WindowsDeleteString(string);
      string = 0;
      operator delete[](v4);
      v11 = *a1;
      if ( *a1 )
      {
        *a1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return v10;
    }
    ScratchDirectory = CreateScratchDirectory((unsigned __int16 *)v4);
    for ( i = 0; ; ++i )
    {
      v10 = ScratchDirectory;
      if ( ScratchDirectory >= 0 )
        break;
      if ( i >= 3 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFC,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)ScratchDirectory,
          v27);
        WindowsDeleteString(string);
        string = 0;
        operator delete[](v4);
        v18 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        return v10;
      }
      ScratchDirectory = CreateScratchDirectory((unsigned __int16 *)v4);
    }
    v27 = 0;
    v28 = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    SafeSource = MakeSafeSource(StringRawBuffer, (const unsigned __int16 *)v4, (struct Common::StringBuffer *)&v27);
    v16 = SafeSource;
    if ( SafeSource < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)SafeSource,
        v27);
      if ( *((_QWORD *)&v27 + 1) )
        operator delete[](*((void **)&v27 + 1));
      WindowsDeleteString(string);
      string = 0;
      operator delete[](v4);
      v17 = *a1;
      if ( *a1 )
      {
        *a1 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      return v16;
    }
    v19 = (void *)*((_QWORD *)&v27 + 1);
    if ( *((_QWORD *)&v27 + 1) )
    {
      v20 = -1;
      do
        ++v20;
      while ( *(_WORD *)(*((_QWORD *)&v27 + 1) + 2 * v20) );
      if ( v20 > 0xFFFFFFFF )
      {
        v23 = -2147024362;
LABEL_30:
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x102,
            (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
            (const char *)(unsigned int)v23,
            v27);
          if ( *((_QWORD *)&v27 + 1) )
            operator delete[](*((void **)&v27 + 1));
          WindowsDeleteString(string);
          string = 0;
          operator delete[](v4);
          v25 = *a1;
          if ( *a1 )
          {
            *a1 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          return (unsigned int)v23;
        }
        if ( v19 )
          operator delete[](v19);
        WindowsDeleteString(string);
        string = 0;
        operator delete[](v4);
        v26 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        return v10;
      }
      WindowsDeleteString(*a2);
      v21 = v20;
      v22 = (const WCHAR *)v19;
    }
    else
    {
      WindowsDeleteString(*a2);
      v21 = 0;
      v22 = &Src;
    }
    *a2 = 0;
    v24 = WindowsCreateString(v22, v21, a2);
    v19 = (void *)*((_QWORD *)&v27 + 1);
    v23 = v24;
    goto LABEL_30;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xED,
    (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
    (const char *)0x8007000ELL,
    v27);
  operator delete[](0);
  v5 = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18002817c  mov     [rsp-38h+arg_8], rbx
0x180028181  mov     [rsp-38h+arg_0], rcx
0x180028186  push    rbp
0x180028187  push    rsi
0x180028188  push    rdi
0x180028189  push    r12
0x18002818b  push    r13
0x18002818d  push    r14
0x18002818f  push    r15
0x180028191  mov     rbp, rsp
0x180028194  sub     rsp, 40h
0x180028198  mov     r12, rdx
0x18002819b  mov     r14, rcx
0x18002819e  mov     ecx, 208h; unsigned __int64
0x1800281a3  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800281a8  mov     rbx, rax
0x1800281ab  mov     [rbp+arg_18], rax
0x1800281af  xor     r13d, r13d
0x1800281b2  test    rax, rax
0x1800281b5  jnz     short loc_180028203
0x1800281b7  mov     rcx, [rbp+38h]; this
0x1800281bb  mov     ebx, 8007000Eh
0x1800281c0  mov     r9d, ebx; char *
0x1800281c3  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800281ca  mov     edx, 0EDh; void *
0x1800281cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800281d4  nop
0x1800281d5  xor     ecx, ecx
0x1800281d7  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800281de  nop     dword ptr [rax+rax+00h]
0x1800281e3  nop
0x1800281e4  mov     rcx, [r14]
0x1800281e7  test    rcx, rcx
0x1800281ea  jz      short loc_1800281FC
0x1800281ec  mov     [r14], r13
0x1800281ef  mov     rdx, [rcx]
0x1800281f2  mov     rax, [rdx+10h]
0x1800281f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281fb  nop
0x1800281fc  mov     eax, ebx
0x1800281fe  jmp     loc_1800284F9
0x180028203  mov     [rbp+string], r13
0x180028207  mov     rsi, [r14]
0x18002820a  mov     rax, [rsi]
0x18002820d  mov     rdi, [rax+80h]
0x180028214  xor     ecx, ecx; string
0x180028216  call    cs:__imp_WindowsDeleteString
0x18002821d  nop     dword ptr [rax+rax+00h]
0x180028222  mov     [rbp+string], r13
0x180028226  lea     rdx, [rbp+string]
0x18002822a  mov     rcx, rsi
0x18002822d  mov     rax, rdi
0x180028230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028235  mov     edi, eax
0x180028237  test    eax, eax
0x180028239  jns     short loc_180028295
0x18002823b  mov     rcx, [rbp+38h]; this
0x18002823f  mov     r9d, eax; char *
0x180028242  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028249  mov     edx, 0F0h; void *
0x18002824e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028253  nop
0x180028254  mov     rcx, [rbp+string]; string
0x180028258  call    cs:__imp_WindowsDeleteString
0x18002825f  nop     dword ptr [rax+rax+00h]
0x180028264  mov     [rbp+string], r13
0x180028268  mov     rcx, rbx
0x18002826b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028272  nop     dword ptr [rax+rax+00h]
0x180028277  nop
0x180028278  mov     rcx, [r14]
0x18002827b  test    rcx, rcx
0x18002827e  jz      short loc_180028290
0x180028280  mov     [r14], r13
0x180028283  mov     rax, [rcx]
0x180028286  mov     rax, [rax+10h]
0x18002828a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002828f  nop
0x180028290  jmp     loc_1800284F7
0x180028295  mov     rcx, rbx; unsigned __int16 *
0x180028298  call    ?CreateScratchDirectory@@YAJPEAG@Z; CreateScratchDirectory(ushort *)
0x18002829d  mov     esi, r13d
0x1800282a0  jmp     short loc_1800282B5
0x1800282a2  cmp     esi, 3
0x1800282a5  jge     loc_180028363
0x1800282ab  mov     rcx, rbx; unsigned __int16 *
0x1800282ae  call    ?CreateScratchDirectory@@YAJPEAG@Z; CreateScratchDirectory(ushort *)
0x1800282b3  inc     esi
0x1800282b5  test    eax, eax
0x1800282b7  mov     edi, eax
0x1800282b9  js      short loc_1800282A2
0x1800282bb  xorps   xmm0, xmm0
0x1800282be  movups  [rbp+var_20], xmm0
0x1800282c2  mov     [rbp+var_10], r13d
0x1800282c6  xor     edx, edx; length
0x1800282c8  mov     rcx, [rbp+string]; string
0x1800282cc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800282d3  nop     dword ptr [rax+rax+00h]
0x1800282d8  lea     r8, [rbp+var_20]; struct Common::StringBuffer *
0x1800282dc  mov     rdx, rbx; unsigned __int16 *
0x1800282df  mov     rcx, rax; lpExistingFileName
0x1800282e2  call    ?MakeSafeSource@@YAJPEBG0PEAVStringBuffer@Common@@@Z; MakeSafeSource(ushort const *,ushort const *,Common::StringBuffer *)
0x1800282e7  mov     esi, eax
0x1800282e9  test    eax, eax
0x1800282eb  jns     loc_1800283BD
0x1800282f1  mov     rcx, [rbp+38h]; this
0x1800282f5  mov     r9d, eax; char *
0x1800282f8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800282ff  mov     edx, 100h; void *
0x180028304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028309  nop
0x18002830a  mov     rcx, qword ptr [rbp+var_20+8]
0x18002830e  test    rcx, rcx
0x180028311  jz      short loc_180028320
0x180028313  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002831a  nop     dword ptr [rax+rax+00h]
0x18002831f  nop
0x180028320  mov     rcx, [rbp+string]; string
0x180028324  call    cs:__imp_WindowsDeleteString
0x18002832b  nop     dword ptr [rax+rax+00h]
0x180028330  mov     [rbp+string], r13
0x180028334  mov     rcx, rbx
0x180028337  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002833e  nop     dword ptr [rax+rax+00h]
0x180028343  nop
0x180028344  mov     rcx, [r14]
0x180028347  test    rcx, rcx
0x18002834a  jz      short loc_18002835C
0x18002834c  mov     [r14], r13
0x18002834f  mov     rax, [rcx]
0x180028352  mov     rax, [rax+10h]
0x180028356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002835b  nop
0x18002835c  mov     eax, esi
0x18002835e  jmp     loc_1800284F9
0x180028363  mov     rcx, [rbp+38h]; this
0x180028367  mov     r9d, edi; char *
0x18002836a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028371  mov     edx, 0FCh; void *
0x180028376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002837b  nop
0x18002837c  mov     rcx, [rbp+string]; string
0x180028380  call    cs:__imp_WindowsDeleteString
0x180028387  nop     dword ptr [rax+rax+00h]
0x18002838c  mov     [rbp+string], r13
0x180028390  mov     rcx, rbx
0x180028393  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002839a  nop     dword ptr [rax+rax+00h]
0x18002839f  nop
0x1800283a0  mov     rcx, [r14]
0x1800283a3  test    rcx, rcx
0x1800283a6  jz      short loc_1800283B8
0x1800283a8  mov     [r14], r13
0x1800283ab  mov     rax, [rcx]
0x1800283ae  mov     rax, [rax+10h]
0x1800283b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283b7  nop
0x1800283b8  jmp     loc_1800284F7
0x1800283bd  mov     rsi, qword ptr [rbp+var_20+8]
0x1800283c1  test    rsi, rsi
0x1800283c4  jz      short loc_1800283FE
0x1800283c6  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800283ca  inc     r15
0x1800283cd  cmp     [rsi+r15*2], r13w
0x1800283d2  jnz     short loc_1800283CA
0x1800283d4  mov     eax, 0FFFFFFFFh
0x1800283d9  cmp     r15, rax
0x1800283dc  ja      short loc_1800283F6
0x1800283de  mov     rcx, [r12]; string
0x1800283e2  call    cs:__imp_WindowsDeleteString
0x1800283e9  nop     dword ptr [rax+rax+00h]
0x1800283ee  mov     edx, r15d
0x1800283f1  mov     rcx, rsi
0x1800283f4  jmp     short loc_180028417
0x1800283f6  mov     r15d, 80070216h
0x1800283fc  jmp     short loc_180028431
0x1800283fe  mov     rcx, [r12]; string
0x180028402  call    cs:__imp_WindowsDeleteString
0x180028409  nop     dword ptr [rax+rax+00h]
0x18002840e  xor     edx, edx; length
0x180028410  lea     rcx, Src; sourceString
0x180028417  mov     [r12], r13
0x18002841b  mov     r8, r12; string
0x18002841e  call    cs:__imp_WindowsCreateString
0x180028425  nop     dword ptr [rax+rax+00h]
0x18002842a  mov     rsi, qword ptr [rbp+var_20+8]
0x18002842e  mov     r15d, eax
0x180028431  test    r15d, r15d
0x180028434  jns     short loc_1800284A6
0x180028436  mov     rcx, [rbp+38h]; this
0x18002843a  mov     r9d, r15d; char *
0x18002843d  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180028444  mov     edx, 102h; void *
0x180028449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002844e  nop
0x18002844f  mov     rcx, qword ptr [rbp+var_20+8]
0x180028453  test    rcx, rcx
0x180028456  jz      short loc_180028465
0x180028458  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002845f  nop     dword ptr [rax+rax+00h]
0x180028464  nop
0x180028465  mov     rcx, [rbp+string]; string
0x180028469  call    cs:__imp_WindowsDeleteString
0x180028470  nop     dword ptr [rax+rax+00h]
0x180028475  mov     [rbp+string], r13
0x180028479  mov     rcx, rbx
0x18002847c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180028483  nop     dword ptr [rax+rax+00h]
0x180028488  nop
0x180028489  mov     rcx, [r14]
0x18002848c  test    rcx, rcx
0x18002848f  jz      short loc_1800284A1
0x180028491  mov     [r14], r13
0x180028494  mov     rax, [rcx]
0x180028497  mov     rax, [rax+10h]
0x18002849b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284a0  nop
0x1800284a1  mov     eax, r15d
0x1800284a4  jmp     short loc_1800284F9
0x1800284a6  test    rsi, rsi
0x1800284a9  jz      short loc_1800284BB
0x1800284ab  mov     rcx, rsi
0x1800284ae  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800284b5  nop     dword ptr [rax+rax+00h]
0x1800284ba  nop
0x1800284bb  mov     rcx, [rbp+string]; string
0x1800284bf  call    cs:__imp_WindowsDeleteString
0x1800284c6  nop     dword ptr [rax+rax+00h]
0x1800284cb  mov     [rbp+string], r13
0x1800284cf  mov     rcx, rbx
0x1800284d2  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800284d9  nop     dword ptr [rax+rax+00h]
0x1800284de  nop
0x1800284df  mov     rcx, [r14]
0x1800284e2  test    rcx, rcx
0x1800284e5  jz      short loc_1800284F7
0x1800284e7  mov     [r14], r13
0x1800284ea  mov     rax, [rcx]
0x1800284ed  mov     rax, [rax+10h]
0x1800284f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284f6  nop
0x1800284f7  mov     eax, edi
0x1800284f9  mov     rbx, [rsp+40h+arg_8]
0x180028501  add     rsp, 40h
0x180028505  pop     r15
0x180028507  pop     r14
0x180028509  pop     r13
0x18002850b  pop     r12
0x18002850d  pop     rdi
0x18002850e  pop     rsi
0x18002850f  pop     rbp
0x180028510  retn
```
