# UWAInstallWork::_DoDirectAcquireLicense(void)

- ea: `0x1800eef5c`
- end: `0x1800ef47a`
- name: `?_DoDirectAcquireLicense@UWAInstallWork@@AEAAJXZ`
- size: `1310`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f0fc0`
- `0x1800f6c24`

## callees

- `0x180009ea0`
- `0x1800111c8`
- `0x1800127c8`
- `0x18001c414`
- `0x1800228c4`
- `0x18002865c`
- `0x18002cec8`
- `0x18002ec2c`
- `0x180031d3c`
- `0x180033188`
- `0x1800509c8`
- `0x180056c60`
- `0x180056d64`
- `0x180070ebc`
- `0x180072248`
- `0x1800ed1d8`
- `0x1800eef5c`
- `0x1801deaf8`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef063`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef255`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef26b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ef2d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eefae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef3cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eefae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef0a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef327`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ef3cb`

## string_xrefs

- `0x1800eefee`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef386`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800ef34b`: `License could not be acquired with the client token and user (SID: %s) isnt logged on`
- `0x1800eefe1`: `UWAInstallWork::_DoDirectAcquireLicense`
- `0x1800ef2ae`: `UWAInstallWork::_DoDirectAcquireLicense`
- `0x1800ef35b`: `UWAInstallWork::_DoDirectAcquireLicense`
- `0x1800ef3ef`: `UWAInstallWork::_DoDirectAcquireLicense`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UWAInstallWork::_DoDirectAcquireLicense(UWAInstallWork *this)
{
  HSTRING *v2; // r13
  const unsigned __int16 *StringRawBuffer; // rax
  __int64 v4; // rdi
  int (__fastcall *v5)(__int64, HSTRING *); // rbx
  HSTRING v6; // rcx
  const WCHAR *v7; // rdi
  int ContentId; // ebx
  int v9; // eax
  int v10; // eax
  unsigned __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rbx
  const char *v15; // rsi
  const unsigned __int16 *v16; // rax
  __int64 *v17; // rax
  __int64 *v18; // rcx
  unsigned int v19; // edi
  HSTRING v20; // rcx
  PCWSTR v21; // rbx
  const unsigned __int16 *v22; // rax
  const char *v23; // r9
  int v25; // [rsp+20h] [rbp-168h]
  unsigned __int16 *v26; // [rsp+28h] [rbp-160h]
  unsigned __int16 *v27; // [rsp+38h] [rbp-150h]
  bool IsUserLoggedIn; // [rsp+70h] [rbp-118h]
  unsigned int v29[2]; // [rsp+78h] [rbp-110h] BYREF
  HSTRING string; // [rsp+80h] [rbp-108h] BYREF
  __int64 v31; // [rsp+88h] [rbp-100h] BYREF
  HSTRING v32; // [rsp+90h] [rbp-F8h] BYREF
  __int64 *v33; // [rsp+98h] [rbp-F0h]
  const char *v34; // [rsp+A0h] [rbp-E8h]
  __int64 *i; // [rsp+A8h] [rbp-E0h]
  HSTRING *v36; // [rsp+B0h] [rbp-D8h]
  _BYTE v37[16]; // [rsp+B8h] [rbp-D0h] BYREF
  _BYTE v38[16]; // [rsp+C8h] [rbp-C0h] BYREF
  _BYTE v39[16]; // [rsp+D8h] [rbp-B0h] BYREF
  __int128 v40; // [rsp+E8h] [rbp-A0h]
  unsigned __int16 v41[40]; // [rsp+100h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(v37);
  v2 = (HSTRING *)((char *)this + 472);
  v36 = (HSTRING *)((char *)this + 472);
  StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)this + 59), 0);
  try
  {
    v15 = (char *)this + 304;
    v34 = (char *)this + 304;
    LogSimpleMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      0xECAu,
      "UWAInstallWork::_DoDirectAcquireLicense",
      -1,
      L"[Start] _DoDirectAcquireLicense, Starting direct licensing.",
      (const char *)this + 304,
      StringRawBuffer);
    CallerContext::ImpersonateUser((char *)this + 152, v38);
    IsUserLoggedIn = CallerContext::IsUserLoggedIn((UWAInstallWork *)((char *)this + 152));
    v17 = (__int64 *)*((_QWORD *)this + 146);
    v18 = (__int64 *)*((_QWORD *)this + 147);
    for ( i = v18; ; v18 = i )
    {
      v33 = v17;
      if ( v17 == v18 )
        break;
      string = 0;
      v4 = *v17;
      v5 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)*v17 + 88LL);
      WindowsDeleteString(0);
      string = 0;
      if ( v5(v4, &string) >= 0 )
      {
        v6 = string;
        if ( !string )
          goto LABEL_16;
        v7 = WindowsGetStringRawBuffer(string, 0);
        *(_QWORD *)v29 = v7;
        v40 = 0;
        ContentId = GetContentId(v7);
        if ( ContentId < 0 )
        {
          v16 = WindowsGetStringRawBuffer(*v2, 0);
          LogMessage(
            2u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
            0xEF5u,
            "UWAInstallWork::_DoDirectAcquireLicense",
            ContentId,
            L"Failed to get ContentId for PFN: %s",
            v15,
            v16,
            v7);
        }
        else
        {
          LODWORD(v26) = WORD3(v40);
          v25 = WORD2(v40);
          v9 = StringCchPrintfW(v41, 0x25u, L"%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x", (unsigned int)v40);
          if ( v9 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEEC,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)v9,
              v25);
          v32 = 0;
          v10 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v32, v29);
          if ( v10 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEEE,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)v10,
              v25);
          v31 = 0;
          v29[0] = 0;
          v11 = -1;
          do
            ++v11;
          while ( v41[v11] );
          v12 = ULongLongToUInt(v11, v29);
          if ( v12 >= 0 )
            v12 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&v31, v41, v29[0]);
          if ( v12 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0xEF0,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
              (const char *)(unsigned int)v12,
              v25);
          v13 = std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(
                  v37,
                  v39,
                  &v32);
          v14 = *(_QWORD *)v13;
          WindowsDeleteString(*(HSTRING *)(*(_QWORD *)v13 + 40LL));
          *(_QWORD *)(v14 + 40) = 0;
          *(_QWORD *)(v14 + 40) = v31;
          v31 = 0;
          WindowsDeleteString(0);
          v31 = 0;
          WindowsDeleteString(v32);
          v32 = 0;
          v15 = v34;
        }
      }
      v6 = string;
LABEL_16:
      WindowsDeleteString(v6);
      v17 = v33 + 1;
    }
    v19 = UWAInstallWork::_AcquireLicensesForUpdates(this);
    if ( v19 == -2143322111 && !IsUserLoggedIn )
    {
      v19 = -2147023584;
      v20 = (HSTRING)*((_QWORD *)this + 28);
      if ( !v20 )
        v20 = (HSTRING)*((_QWORD *)this + 19);
      v21 = WindowsGetStringRawBuffer(v20, 0);
      v22 = WindowsGetStringRawBuffer(*v2, 0);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        0xF05u,
        "UWAInstallWork::_DoDirectAcquireLicense",
        -2147023584,
        L"License could not be acquired with the client token and user (SID: %s) isnt logged on",
        v15,
        v22,
        v21);
    }
    TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v38);
  }
  catch ( ... )
  {
    v29[0] = wil::details::in1diag3::Log_CaughtException(
               retaddr,
               (void *)0xF0A,
               (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
               v23);
    v19 = v29[0];
    v2 = v36;
    v15 = v34;
  }
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0xF0D,
    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    (const char *)v19,
    (int)"Direct license acquisition failed.",
    (const char *)v26);
  v27 = (unsigned __int16 *)WindowsGetStringRawBuffer(*v2, 0);
  LogSimpleMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
    0xF0Eu,
    "UWAInstallWork::_DoDirectAcquireLicense",
    -1,
    L"[End] _DoDirectAcquireLicense.",
    v15,
    v27);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::Wrappers::HString>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::Wrappers::HString>>,0>>(v37);
  return v19;
}

```

## disassembly

```asm
0x1800eef5c  mov     [rsp+arg_8], rbx
0x1800eef61  mov     [rsp+arg_10], rsi
0x1800eef66  push    rdi
0x1800eef67  push    r12
0x1800eef69  push    r13
0x1800eef6b  push    r14
0x1800eef6d  push    r15
0x1800eef6f  sub     rsp, 160h
0x1800eef76  mov     rax, cs:__security_cookie
0x1800eef7d  xor     rax, rsp
0x1800eef80  mov     [rsp+188h+var_38], rax
0x1800eef88  mov     r15, rcx
0x1800eef8b  lea     rcx, [rsp+188h+var_D0]
0x1800eef93  call    ??0?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@QEAA@XZ; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>(void)
0x1800eef98  nop
0x1800eef99  lea     r13, [r15+1D8h]
0x1800eefa0  mov     [rsp+188h+var_D8], r13
0x1800eefa8  xor     edx, edx; length
0x1800eefaa  mov     rcx, [r13+0]; string
0x1800eefae  call    cs:__imp_WindowsGetStringRawBuffer
0x1800eefb4  lea     rsi, [r15+130h]
0x1800eefbb  mov     [rsp+188h+var_E8], rsi
0x1800eefc3  mov     [rsp+188h+var_150], rax; unsigned __int16 *
0x1800eefc8  mov     [rsp+188h+var_158], rsi; char *
0x1800eefcd  lea     rax, aStartDodirecta; "[Start] _DoDirectAcquireLicense, Starti"...
0x1800eefd4  mov     [rsp+188h+var_160], rax; unsigned __int16 *
0x1800eefd9  mov     [rsp+188h+var_168], 0FFFFFFFFh; int
0x1800eefe1  lea     r9, aUwainstallwork_55; "UWAInstallWork::_DoDirectAcquireLicense"
0x1800eefe8  mov     r8d, 0ECAh; unsigned int
0x1800eefee  lea     r14, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800eeff5  mov     rdx, r14; char *
0x1800eeff8  mov     ecx, 3; unsigned int
0x1800eeffd  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef002  lea     r12, [r15+98h]
0x1800ef009  lea     rdx, [rsp+188h+var_C0]
0x1800ef011  mov     rcx, r12
0x1800ef014  call    ?ImpersonateUser@CallerContext@@QEAA?AVImpersonateContext@TokenHelpers@@XZ; CallerContext::ImpersonateUser(void)
0x1800ef019  nop
0x1800ef01a  mov     rcx, r12; this
0x1800ef01d  call    ?IsUserLoggedIn@CallerContext@@QEBA_NXZ; CallerContext::IsUserLoggedIn(void)
0x1800ef022  mov     [rsp+188h+var_118], al
0x1800ef026  mov     rax, [r15+490h]
0x1800ef02d  mov     rcx, [r15+498h]
0x1800ef034  mov     [rsp+188h+var_E0], rcx
0x1800ef03c  xor     edi, edi
0x1800ef03e  mov     [rsp+188h+var_F0], rax
0x1800ef046  cmp     rax, rcx
0x1800ef049  jz      loc_1800EF2F1
0x1800ef04f  mov     [rsp+188h+string], rdi
0x1800ef057  mov     rdi, [rax]
0x1800ef05a  mov     rax, [rdi]
0x1800ef05d  mov     rbx, [rax+58h]
0x1800ef061  xor     ecx, ecx; string
0x1800ef063  call    cs:__imp_WindowsDeleteString
0x1800ef069  xor     eax, eax
0x1800ef06b  mov     [rsp+188h+string], rax
0x1800ef073  lea     rdx, [rsp+188h+string]
0x1800ef07b  mov     rcx, rdi
0x1800ef07e  mov     rax, rbx
0x1800ef081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef086  xor     edi, edi
0x1800ef088  test    eax, eax
0x1800ef08a  js      loc_1800EF2CA
0x1800ef090  mov     rcx, [rsp+188h+string]; string
0x1800ef098  test    rcx, rcx
0x1800ef09b  jz      loc_1800EF2D2
0x1800ef0a1  xor     edx, edx; length
0x1800ef0a3  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef0a9  mov     rdi, rax
0x1800ef0ac  mov     qword ptr [rsp+188h+var_110], rax
0x1800ef0b1  xorps   xmm0, xmm0
0x1800ef0b4  movups  [rsp+188h+var_A0], xmm0
0x1800ef0bc  lea     r8, [rsp+188h+var_A0]
0x1800ef0c4  mov     edx, 2
0x1800ef0c9  mov     rcx, rax; packageFamilyName
0x1800ef0cc  call    GetContentId
0x1800ef0d1  mov     ebx, eax
0x1800ef0d3  test    eax, eax
0x1800ef0d5  js      loc_1800EF283
0x1800ef0db  movzx   eax, byte ptr [rsp+188h+var_A0+0Fh]
0x1800ef0e3  movzx   ecx, byte ptr [rsp+188h+var_A0+0Eh]
0x1800ef0eb  movzx   edx, byte ptr [rsp+188h+var_A0+0Dh]
0x1800ef0f3  movzx   r8d, byte ptr [rsp+188h+var_A0+0Ch]
0x1800ef0fc  movzx   r9d, byte ptr [rsp+188h+var_A0+0Bh]
0x1800ef105  movzx   r10d, byte ptr [rsp+188h+var_A0+0Ah]
0x1800ef10e  movzx   r11d, byte ptr [rsp+188h+var_A0+9]
0x1800ef117  movzx   ebx, byte ptr [rsp+188h+var_A0+8]
0x1800ef11f  movzx   edi, word ptr [rsp+188h+var_A0+6]
0x1800ef127  movzx   esi, word ptr [rsp+188h+var_A0+4]
0x1800ef12f  mov     [rsp+188h+var_120], eax
0x1800ef133  mov     [rsp+188h+var_128], ecx
0x1800ef137  mov     [rsp+188h+var_130], edx
0x1800ef13b  mov     [rsp+188h+var_138], r8d
0x1800ef140  mov     [rsp+188h+var_140], r9d
0x1800ef145  mov     dword ptr [rsp+188h+var_148], r10d
0x1800ef14a  mov     dword ptr [rsp+188h+var_150], r11d
0x1800ef14f  mov     dword ptr [rsp+188h+var_158], ebx
0x1800ef153  mov     dword ptr [rsp+188h+var_160], edi
0x1800ef157  mov     [rsp+188h+var_168], esi; int
0x1800ef15b  mov     r9d, dword ptr [rsp+188h+var_A0]
0x1800ef163  lea     r8, a08x04x04x02x02; "%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02"...
0x1800ef16a  mov     edx, 25h ; '%'; unsigned __int64
0x1800ef16f  lea     rcx, [rsp+188h+var_88]; unsigned __int16 *
0x1800ef177  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ef17c  mov     rcx, [rsp+188h]; this
0x1800ef184  xor     edi, edi
0x1800ef186  test    eax, eax
0x1800ef188  js      loc_1800EF446
0x1800ef18e  mov     [rsp+188h+var_F8], rdi
0x1800ef196  lea     rdx, [rsp+188h+var_110]
0x1800ef19b  lea     rcx, [rsp+188h+var_F8]
0x1800ef1a3  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1800ef1a8  mov     rcx, [rsp+188h]; this
0x1800ef1b0  test    eax, eax
0x1800ef1b2  js      loc_1800EF457
0x1800ef1b8  mov     [rsp+188h+var_100], rdi
0x1800ef1c0  mov     [rsp+188h+var_110], edi
0x1800ef1c4  lea     rax, [rsp+188h+var_88]
0x1800ef1cc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800ef1d0  inc     rcx; unsigned __int64
0x1800ef1d3  cmp     [rax+rcx*2], di
0x1800ef1d7  jnz     short loc_1800EF1D0
0x1800ef1d9  lea     rdx, [rsp+188h+var_110]; unsigned int *
0x1800ef1de  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800ef1e3  test    eax, eax
0x1800ef1e5  js      short loc_1800EF201
0x1800ef1e7  mov     r8d, [rsp+188h+var_110]; unsigned int
0x1800ef1ec  lea     rdx, [rsp+188h+var_88]; unsigned __int16 *
0x1800ef1f4  lea     rcx, [rsp+188h+var_100]; this
0x1800ef1fc  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800ef201  mov     rcx, [rsp+188h]; this
0x1800ef209  test    eax, eax
0x1800ef20b  js      loc_1800EF468
0x1800ef211  lea     r8, [rsp+188h+var_F8]
0x1800ef219  lea     rdx, [rsp+188h+var_B0]
0x1800ef221  lea     rcx, [rsp+188h+var_D0]
0x1800ef229  call    ??$_Try_emplace@VHString@Wrappers@WRL@Microsoft@@$$V@?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString>::_Try_emplace<Microsoft::WRL::Wrappers::HString,>(Microsoft::WRL::Wrappers::HString &&)
0x1800ef22e  mov     rbx, [rax]
0x1800ef231  mov     rcx, [rbx+28h]; string
0x1800ef235  call    cs:__imp_WindowsDeleteString
0x1800ef23b  mov     [rbx+28h], rdi
0x1800ef23f  mov     rax, [rsp+188h+var_100]
0x1800ef247  mov     [rbx+28h], rax
0x1800ef24b  mov     [rsp+188h+var_100], rdi
0x1800ef253  xor     ecx, ecx; string
0x1800ef255  call    cs:__imp_WindowsDeleteString
0x1800ef25b  mov     [rsp+188h+var_100], rdi
0x1800ef263  mov     rcx, [rsp+188h+var_F8]; string
0x1800ef26b  call    cs:__imp_WindowsDeleteString
0x1800ef271  mov     [rsp+188h+var_F8], rdi
0x1800ef279  mov     rsi, [rsp+188h+var_E8]
0x1800ef281  jmp     short loc_1800EF2CA
0x1800ef283  xor     edx, edx; length
0x1800ef285  mov     rcx, [r13+0]; string
0x1800ef289  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef28f  mov     [rsp+188h+var_148], rdi
0x1800ef294  mov     [rsp+188h+var_150], rax; unsigned __int16 *
0x1800ef299  mov     [rsp+188h+var_158], rsi; char *
0x1800ef29e  lea     rax, aFailedToGetCon; "Failed to get ContentId for PFN: %s"
0x1800ef2a5  mov     [rsp+188h+var_160], rax; unsigned __int16 *
0x1800ef2aa  mov     [rsp+188h+var_168], ebx; int
0x1800ef2ae  lea     r9, aUwainstallwork_55; "UWAInstallWork::_DoDirectAcquireLicense"
0x1800ef2b5  mov     r8d, 0EF5h; unsigned int
0x1800ef2bb  mov     rdx, r14; char *
0x1800ef2be  mov     ecx, 2; unsigned int
0x1800ef2c3  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800ef2c8  xor     edi, edi
0x1800ef2ca  mov     rcx, [rsp+188h+string]; string
0x1800ef2d2  call    cs:__imp_WindowsDeleteString
0x1800ef2d8  mov     rax, [rsp+188h+var_F0]
0x1800ef2e0  add     rax, 8
0x1800ef2e4  mov     rcx, [rsp+188h+var_E0]
0x1800ef2ec  jmp     loc_1800EF03E
0x1800ef2f1  lea     rdx, [rsp+188h+var_D0]
0x1800ef2f9  mov     rcx, r15
0x1800ef2fc  call    ?_AcquireLicensesForUpdates@UWAInstallWork@@AEAAJAEAV?$map@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@@std@@@Z; UWAInstallWork::_AcquireLicensesForUpdates(std::map<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString> &)
0x1800ef301  mov     edi, eax
0x1800ef303  cmp     eax, 803F8001h
0x1800ef308  jnz     short loc_1800EF376
0x1800ef30a  xor     eax, eax
0x1800ef30c  cmp     [rsp+188h+var_118], al
0x1800ef310  jnz     short loc_1800EF376
0x1800ef312  mov     edi, 80070520h
0x1800ef317  mov     rcx, [r12+48h]
0x1800ef31c  test    rcx, rcx
0x1800ef31f  jnz     short loc_1800EF325
0x1800ef321  mov     rcx, [r12]; string
0x1800ef325  xor     edx, edx; length
0x1800ef327  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef32d  mov     rbx, rax
0x1800ef330  xor     edx, edx; length
0x1800ef332  mov     rcx, [r13+0]; string
0x1800ef336  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef33c  mov     [rsp+188h+var_148], rbx
0x1800ef341  mov     [rsp+188h+var_150], rax; unsigned __int16 *
0x1800ef346  mov     [rsp+188h+var_158], rsi; char *
0x1800ef34b  lea     rax, aLicenseCouldNo; "License could not be acquired with the "...
0x1800ef352  mov     [rsp+188h+var_160], rax; unsigned __int16 *
0x1800ef357  mov     [rsp+188h+var_168], edi; int
0x1800ef35b  lea     r9, aUwainstallwork_55; "UWAInstallWork::_DoDirectAcquireLicense"
0x1800ef362  mov     r8d, 0F05h; unsigned int
0x1800ef368  mov     rdx, r14; char *
0x1800ef36b  mov     ecx, 3; unsigned int
0x1800ef370  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800ef375  nop
0x1800ef376  lea     rcx, [rsp+188h+var_C0]; this
0x1800ef37e  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x1800ef383  nop
0x1800ef384  jmp     short loc_1800EF3A1
0x1800ef386  lea     r14, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800ef38d  mov     edi, [rsp+188h+var_110]
0x1800ef391  mov     r13, [rsp+188h+var_D8]
0x1800ef399  mov     rsi, [rsp+188h+var_E8]
0x1800ef3a1  mov     rcx, [rsp+188h]; this
0x1800ef3a9  lea     rax, aDirectLicenseA; "Direct license acquisition failed."
0x1800ef3b0  mov     qword ptr [rsp+188h+var_168], rax; int
0x1800ef3b5  mov     r9d, edi; char *
0x1800ef3b8  mov     r8, r14; unsigned int
0x1800ef3bb  mov     edx, 0F0Dh; void *
0x1800ef3c0  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800ef3c5  xor     edx, edx; length
0x1800ef3c7  mov     rcx, [r13+0]; string
0x1800ef3cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ef3d1  mov     [rsp+188h+var_150], rax; unsigned __int16 *
0x1800ef3d6  mov     [rsp+188h+var_158], rsi; char *
0x1800ef3db  lea     rax, aEndDodirectacq; "[End] _DoDirectAcquireLicense."
0x1800ef3e2  mov     [rsp+188h+var_160], rax; unsigned __int16 *
0x1800ef3e7  mov     [rsp+188h+var_168], 0FFFFFFFFh; int
0x1800ef3ef  lea     r9, aUwainstallwork_55; "UWAInstallWork::_DoDirectAcquireLicense"
0x1800ef3f6  mov     r8d, 0F0Eh; unsigned int
0x1800ef3fc  mov     rdx, r14; char *
0x1800ef3ff  mov     ecx, 3; unsigned int
0x1800ef404  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x1800ef409  nop
0x1800ef40a  lea     rcx, [rsp+188h+var_D0]
0x1800ef412  call    ??1?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@V1234@U?$less@VHString@Wrappers@WRL@Microsoft@@@std@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@V1234@@std@@@6@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::Wrappers::HString>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::Wrappers::HString,std::less<Microsoft::WRL::Wrappers::HString>,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::Wrappers::HString>>,0>>(void)
0x1800ef417  mov     eax, edi
0x1800ef419  mov     rcx, [rsp+188h+var_38]
0x1800ef421  xor     rcx, rsp; StackCookie
0x1800ef424  call    __security_check_cookie
0x1800ef429  lea     r11, [rsp+188h+var_28]
0x1800ef431  mov     rbx, [r11+38h]
0x1800ef435  mov     rsi, [r11+40h]
0x1800ef439  mov     rsp, r11
0x1800ef43c  pop     r15
0x1800ef43e  pop     r14
0x1800ef440  pop     r13
0x1800ef442  pop     r12
0x1800ef444  pop     rdi
0x1800ef445  retn
0x1800ef446  mov     r9d, eax; char *
0x1800ef449  mov     r8, r14; unsigned int
0x1800ef44c  mov     edx, 0EECh; void *
0x1800ef451  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef457  mov     r9d, eax; char *
0x1800ef45a  mov     r8, r14; unsigned int
0x1800ef45d  mov     edx, 0EEEh; void *
0x1800ef462  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ef468  mov     r9d, eax; char *
0x1800ef46b  mov     r8, r14; unsigned int
0x1800ef46e  mov     edx, 0EF0h; void *
0x1800ef473  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
