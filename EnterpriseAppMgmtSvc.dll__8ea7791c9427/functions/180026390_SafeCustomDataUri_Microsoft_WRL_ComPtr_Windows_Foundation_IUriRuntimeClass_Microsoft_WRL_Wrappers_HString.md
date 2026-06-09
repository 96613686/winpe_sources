# SafeCustomDataUri(Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClass>,Microsoft::WRL::Wrappers::HString *)

- ea: `0x180026390`
- end: `0x1800266b3`
- name: `?SafeCustomDataUri@@YAJV?$ComPtr@UIUriRuntimeClass@Foundation@Windows@@@WRL@Microsoft@@PEAVHString@Wrappers@23@@Z`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800242c0`

## callees

- `0x180002f64`
- `0x18000cfe8`
- `0x18001f6a0`
- `0x180022df8`
- `0x180026390`
- `0x18006a010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800263eb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002646d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026509`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026521`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026571`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002661e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026636`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026662`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002667a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800263eb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002646d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026509`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026521`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026571`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002661e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026636`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180026662`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002667a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800265ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800265ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800264c8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002666d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026424`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026460`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026514`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026564`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800265d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180026629`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002666d`

## string_xrefs

- `0x1800263d7`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002644a`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800264ee`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002654e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180026603`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

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
0x180026390  mov     [rsp-38h+arg_8], rbx
0x180026395  mov     [rsp-38h+arg_0], rcx
0x18002639a  push    rbp
0x18002639b  push    rsi
0x18002639c  push    rdi
0x18002639d  push    r12
0x18002639f  push    r13
0x1800263a1  push    r14
0x1800263a3  push    r15
0x1800263a5  mov     rbp, rsp
0x1800263a8  sub     rsp, 40h
0x1800263ac  mov     r12, rdx
0x1800263af  mov     r14, rcx
0x1800263b2  mov     ecx, 208h; unsigned __int64
0x1800263b7  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800263bc  mov     rbx, rax
0x1800263bf  mov     [rbp+arg_18], rax
0x1800263c3  xor     r13d, r13d
0x1800263c6  test    rax, rax
0x1800263c9  jnz     short loc_180026411
0x1800263cb  mov     rcx, [rbp+38h]; this
0x1800263cf  mov     ebx, 8007000Eh
0x1800263d4  mov     r9d, ebx; char *
0x1800263d7  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800263de  mov     edx, 0EDh; void *
0x1800263e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800263e8  nop
0x1800263e9  xor     ecx, ecx
0x1800263eb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800263f1  nop
0x1800263f2  mov     rcx, [r14]
0x1800263f5  test    rcx, rcx
0x1800263f8  jz      short loc_18002640A
0x1800263fa  mov     [r14], r13
0x1800263fd  mov     rdx, [rcx]
0x180026400  mov     rax, [rdx+10h]
0x180026404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026409  nop
0x18002640a  mov     eax, ebx
0x18002640c  jmp     loc_18002669B
0x180026411  mov     [rbp+string], r13
0x180026415  mov     rsi, [r14]
0x180026418  mov     rax, [rsi]
0x18002641b  mov     rdi, [rax+80h]
0x180026422  xor     ecx, ecx; string
0x180026424  call    cs:__imp_WindowsDeleteString
0x18002642a  mov     [rbp+string], r13
0x18002642e  lea     rdx, [rbp+string]
0x180026432  mov     rcx, rsi
0x180026435  mov     rax, rdi
0x180026438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002643d  mov     edi, eax
0x18002643f  test    eax, eax
0x180026441  jns     short loc_180026491
0x180026443  mov     rcx, [rbp+38h]; this
0x180026447  mov     r9d, eax; char *
0x18002644a  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026451  mov     edx, 0F0h; void *
0x180026456  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002645b  nop
0x18002645c  mov     rcx, [rbp+string]; string
0x180026460  call    cs:__imp_WindowsDeleteString
0x180026466  mov     [rbp+string], r13
0x18002646a  mov     rcx, rbx
0x18002646d  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026473  nop
0x180026474  mov     rcx, [r14]
0x180026477  test    rcx, rcx
0x18002647a  jz      short loc_18002648C
0x18002647c  mov     [r14], r13
0x18002647f  mov     rax, [rcx]
0x180026482  mov     rax, [rax+10h]
0x180026486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002648b  nop
0x18002648c  jmp     loc_180026699
0x180026491  mov     rcx, rbx; unsigned __int16 *
0x180026494  call    ?CreateScratchDirectory@@YAJPEAG@Z; CreateScratchDirectory(ushort *)
0x180026499  mov     esi, r13d
0x18002649c  jmp     short loc_1800264B1
0x18002649e  cmp     esi, 3
0x1800264a1  jge     loc_180026547
0x1800264a7  mov     rcx, rbx; unsigned __int16 *
0x1800264aa  call    ?CreateScratchDirectory@@YAJPEAG@Z; CreateScratchDirectory(ushort *)
0x1800264af  inc     esi
0x1800264b1  test    eax, eax
0x1800264b3  mov     edi, eax
0x1800264b5  js      short loc_18002649E
0x1800264b7  xorps   xmm0, xmm0
0x1800264ba  movups  [rbp+var_20], xmm0
0x1800264be  mov     [rbp+var_10], r13d
0x1800264c2  xor     edx, edx; length
0x1800264c4  mov     rcx, [rbp+string]; string
0x1800264c8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800264ce  lea     r8, [rbp+var_20]; struct Common::StringBuffer *
0x1800264d2  mov     rdx, rbx; unsigned __int16 *
0x1800264d5  mov     rcx, rax; lpExistingFileName
0x1800264d8  call    ?MakeSafeSource@@YAJPEBG0PEAVStringBuffer@Common@@@Z; MakeSafeSource(ushort const *,ushort const *,Common::StringBuffer *)
0x1800264dd  mov     esi, eax
0x1800264df  test    eax, eax
0x1800264e1  jns     loc_180026595
0x1800264e7  mov     rcx, [rbp+38h]; this
0x1800264eb  mov     r9d, eax; char *
0x1800264ee  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800264f5  mov     edx, 100h; void *
0x1800264fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800264ff  nop
0x180026500  mov     rcx, qword ptr [rbp+var_20+8]
0x180026504  test    rcx, rcx
0x180026507  jz      short loc_180026510
0x180026509  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002650f  nop
0x180026510  mov     rcx, [rbp+string]; string
0x180026514  call    cs:__imp_WindowsDeleteString
0x18002651a  mov     [rbp+string], r13
0x18002651e  mov     rcx, rbx
0x180026521  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026527  nop
0x180026528  mov     rcx, [r14]
0x18002652b  test    rcx, rcx
0x18002652e  jz      short loc_180026540
0x180026530  mov     [r14], r13
0x180026533  mov     rax, [rcx]
0x180026536  mov     rax, [rax+10h]
0x18002653a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002653f  nop
0x180026540  mov     eax, esi
0x180026542  jmp     loc_18002669B
0x180026547  mov     rcx, [rbp+38h]; this
0x18002654b  mov     r9d, edi; char *
0x18002654e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180026555  mov     edx, 0FCh; void *
0x18002655a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002655f  nop
0x180026560  mov     rcx, [rbp+string]; string
0x180026564  call    cs:__imp_WindowsDeleteString
0x18002656a  mov     [rbp+string], r13
0x18002656e  mov     rcx, rbx
0x180026571  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026577  nop
0x180026578  mov     rcx, [r14]
0x18002657b  test    rcx, rcx
0x18002657e  jz      short loc_180026590
0x180026580  mov     [r14], r13
0x180026583  mov     rax, [rcx]
0x180026586  mov     rax, [rax+10h]
0x18002658a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002658f  nop
0x180026590  jmp     loc_180026699
0x180026595  mov     rsi, qword ptr [rbp+var_20+8]
0x180026599  test    rsi, rsi
0x18002659c  jz      short loc_1800265D0
0x18002659e  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800265a2  inc     r15
0x1800265a5  cmp     [rsi+r15*2], r13w
0x1800265aa  jnz     short loc_1800265A2
0x1800265ac  mov     eax, 0FFFFFFFFh
0x1800265b1  cmp     r15, rax
0x1800265b4  ja      short loc_1800265C8
0x1800265b6  mov     rcx, [r12]; string
0x1800265ba  call    cs:__imp_WindowsDeleteString
0x1800265c0  mov     edx, r15d
0x1800265c3  mov     rcx, rsi
0x1800265c6  jmp     short loc_1800265E3
0x1800265c8  mov     r15d, 80070216h
0x1800265ce  jmp     short loc_1800265F7
0x1800265d0  mov     rcx, [r12]; string
0x1800265d4  call    cs:__imp_WindowsDeleteString
0x1800265da  xor     edx, edx; length
0x1800265dc  lea     rcx, Src; sourceString
0x1800265e3  mov     [r12], r13
0x1800265e7  mov     r8, r12; string
0x1800265ea  call    cs:__imp_WindowsCreateString
0x1800265f0  mov     rsi, qword ptr [rbp+var_20+8]
0x1800265f4  mov     r15d, eax
0x1800265f7  test    r15d, r15d
0x1800265fa  jns     short loc_18002665A
0x1800265fc  mov     rcx, [rbp+38h]; this
0x180026600  mov     r9d, r15d; char *
0x180026603  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002660a  mov     edx, 102h; void *
0x18002660f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026614  nop
0x180026615  mov     rcx, qword ptr [rbp+var_20+8]
0x180026619  test    rcx, rcx
0x18002661c  jz      short loc_180026625
0x18002661e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026624  nop
0x180026625  mov     rcx, [rbp+string]; string
0x180026629  call    cs:__imp_WindowsDeleteString
0x18002662f  mov     [rbp+string], r13
0x180026633  mov     rcx, rbx
0x180026636  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002663c  nop
0x18002663d  mov     rcx, [r14]
0x180026640  test    rcx, rcx
0x180026643  jz      short loc_180026655
0x180026645  mov     [r14], r13
0x180026648  mov     rax, [rcx]
0x18002664b  mov     rax, [rax+10h]
0x18002664f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026654  nop
0x180026655  mov     eax, r15d
0x180026658  jmp     short loc_18002669B
0x18002665a  test    rsi, rsi
0x18002665d  jz      short loc_180026669
0x18002665f  mov     rcx, rsi
0x180026662  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026668  nop
0x180026669  mov     rcx, [rbp+string]; string
0x18002666d  call    cs:__imp_WindowsDeleteString
0x180026673  mov     [rbp+string], r13
0x180026677  mov     rcx, rbx
0x18002667a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180026680  nop
0x180026681  mov     rcx, [r14]
0x180026684  test    rcx, rcx
0x180026687  jz      short loc_180026699
0x180026689  mov     [r14], r13
0x18002668c  mov     rax, [rcx]
0x18002668f  mov     rax, [rax+10h]
0x180026693  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026698  nop
0x180026699  mov     eax, edi
0x18002669b  mov     rbx, [rsp+40h+arg_8]
0x1800266a3  add     rsp, 40h
0x1800266a7  pop     r15
0x1800266a9  pop     r14
0x1800266ab  pop     r13
0x1800266ad  pop     r12
0x1800266af  pop     rdi
0x1800266b0  pop     rsi
0x1800266b1  pop     rbp
0x1800266b2  retn
```
