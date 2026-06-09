# FindPackage(PackageInfo &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180015298`
- end: `0x1800155dc`
- name: `?FindPackage@@YAJAEAUPackageInfo@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `836`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c354`
- `0x1800102b8`
- `0x180010700`

## callees

- `0x1800062ac`
- `0x1800070e4`
- `0x1800083fc`
- `0x18000a2c0`
- `0x18000a440`
- `0x180014fc4`
- `0x180015298`
- `0x180015c2c`
- `0x180016734`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180015565`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180015565`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800152ec`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800152ec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015599`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015576`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015599`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall FindPackage(_BYTE *a1, HSTRING a2)
{
  int CurrentUserSid; // eax
  int PackageInfo; // ebx
  LPCWSTR v6; // rcx
  __int64 v7; // rdx
  _QWORD *v8; // rax
  HSTRING v9; // r9
  _QWORD *v10; // rax
  HSTRING v11; // rax
  int PackageManager; // eax
  int v13; // eax
  _QWORD *v14; // rcx
  _QWORD *v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  _QWORD *v20; // [rsp+30h] [rbp-39h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-31h] BYREF
  struct Windows::Management::Deployment::IPackageManager *v22; // [rsp+40h] [rbp-29h] BYREF
  HSTRING string; // [rsp+48h] [rbp-21h] BYREF
  HSTRING v24[5]; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v25[3]; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int64 v26; // [rsp+90h] [rbp+27h]

  v24[4] = a2;
  v24[0] = 0;
  v26 = 7;
  v25[2] = 0;
  LOWORD(v25[0]) = 0;
  string = 0;
  v22 = 0;
  CurrentUserSid = RoInitialize(1);
  PackageInfo = CurrentUserSid;
  if ( CurrentUserSid >= 0 )
  {
    CurrentUserSid = GetCurrentUserSid(v25);
    PackageInfo = CurrentUserSid;
    if ( CurrentUserSid >= 0 )
    {
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v8 = v25;
        if ( v26 >= 8 )
          v8 = (_QWORD *)v25[0];
        if ( *((_QWORD *)a2 + 3) < 8u )
          LODWORD(v9) = (_DWORD)a2;
        else
          v9 = *(HSTRING *)a2;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)&WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
          (_DWORD)v9,
          (__int64)v8);
      }
      v10 = v25;
      if ( v26 >= 8 )
        v10 = (_QWORD *)v25[0];
      v21 = v10;
      Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(v24, &v21);
      if ( *((_QWORD *)a2 + 3) < 8u )
        v11 = a2;
      else
        v11 = *(HSTRING *)a2;
      v21 = v11;
      Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, &v21);
      memset(&v24[1], 0, 24);
      v20 = 0;
      PackageManager = GetPackageManager(&v22);
      PackageInfo = PackageManager;
      if ( PackageManager < 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
            (unsigned int)PackageManager);
        goto LABEL_44;
      }
      v13 = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, HSTRING, _QWORD **))(*(_QWORD *)v22 + 168LL))(
              v22,
              v24[0],
              string,
              &v20);
      PackageInfo = v13;
      if ( v13 < 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
            (unsigned int)v13);
        v14 = v20;
        if ( v20 )
        {
          v20 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        }
        goto LABEL_44;
      }
      v15 = v20;
      if ( v20 )
      {
        v21 = v20;
        (*(void (__fastcall **)(_QWORD *))(*v20 + 8LL))(v20);
        PackageInfo = GetPackageInfo(&v21, a1);
        if ( PackageInfo < 0 )
        {
          v16 = v20;
          if ( v20 )
          {
            v20 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
          }
          goto LABEL_44;
        }
        std::wstring::operator=(a1 + 32, v25);
        v15 = v20;
      }
      else
      {
        PackageInfo = -1879113722;
      }
      if ( v15 )
      {
        v20 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v7 = 33;
        goto LABEL_5;
      }
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      v7 = 32;
LABEL_5:
      WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids, (unsigned int)CurrentUserSid);
    }
  }
LABEL_44:
  if ( v22 )
  {
    (*(void (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  RoUninitialize();
  WindowsDeleteString(string);
  string = 0;
  LOBYTE(v17) = 1;
  std::wstring::_Tidy(v25, v17, 0);
  WindowsDeleteString(v24[0]);
  v24[0] = 0;
  LOBYTE(v18) = 1;
  std::wstring::_Tidy(a2, v18, 0);
  return (unsigned int)PackageInfo;
}

```

## disassembly

```asm
0x180015298  mov     [rsp-8+arg_10], rbx
0x18001529d  push    rbp
0x18001529e  push    rsi
0x18001529f  push    rdi
0x1800152a0  push    r14
0x1800152a2  push    r15
0x1800152a4  lea     rbp, [rsp-37h]
0x1800152a9  sub     rsp, 0A0h
0x1800152b0  mov     rax, cs:__security_cookie
0x1800152b7  xor     rax, rsp
0x1800152ba  mov     [rbp+57h+var_28], rax
0x1800152be  mov     rsi, rdx
0x1800152c1  mov     r14, rcx
0x1800152c4  mov     [rbp+57h+var_50], rdx
0x1800152c8  xor     r15d, r15d
0x1800152cb  mov     [rbp+57h+var_70], r15
0x1800152cf  mov     [rbp+57h+var_30], 7
0x1800152d7  mov     [rbp+57h+var_38], r15
0x1800152db  mov     word ptr [rbp+57h+var_48], r15w
0x1800152e0  mov     [rbp+57h+string], r15
0x1800152e4  mov     [rbp+57h+var_80], r15
0x1800152e8  lea     ecx, [r15+1]
0x1800152ec  call    cs:__imp_RoInitialize
0x1800152f3  nop     dword ptr [rax+rax+00h]
0x1800152f8  mov     ebx, eax
0x1800152fa  test    eax, eax
0x1800152fc  jns     short loc_18001533B
0x1800152fe  lea     rdi, WPP_GLOBAL_Control
0x180015305  mov     rcx, cs:WPP_GLOBAL_Control
0x18001530c  cmp     rcx, rdi
0x18001530f  jz      loc_18001554C
0x180015315  test    byte ptr [rcx+1Ch], 4
0x180015319  jz      loc_18001554C
0x18001531f  lea     edx, [r15+20h]
0x180015323  mov     r9d, eax
0x180015326  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x18001532d  mov     rcx, [rcx+10h]
0x180015331  call    WPP_SF_d
0x180015336  jmp     loc_18001554C
0x18001533b  lea     rcx, [rbp+57h+var_48]
0x18001533f  call    ?GetCurrentUserSid@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetCurrentUserSid(std::wstring &)
0x180015344  mov     ebx, eax
0x180015346  test    eax, eax
0x180015348  jns     short loc_180015372
0x18001534a  lea     rdi, WPP_GLOBAL_Control
0x180015351  mov     rcx, cs:WPP_GLOBAL_Control
0x180015358  cmp     rcx, rdi
0x18001535b  jz      loc_18001554C
0x180015361  test    byte ptr [rcx+1Ch], 4
0x180015365  jz      loc_18001554C
0x18001536b  mov     edx, 21h ; '!'
0x180015370  jmp     short loc_180015323
0x180015372  lea     rdi, WPP_GLOBAL_Control
0x180015379  mov     rcx, cs:WPP_GLOBAL_Control
0x180015380  cmp     rcx, rdi
0x180015383  jz      short loc_1800153C2
0x180015385  test    byte ptr [rcx+1Ch], 1
0x180015389  jz      short loc_1800153C2
0x18001538b  lea     rax, [rbp+57h+var_48]
0x18001538f  cmp     [rbp+57h+var_30], 8
0x180015394  cmovnb  rax, [rbp+57h+var_48]
0x180015399  cmp     qword ptr [rsi+18h], 8
0x18001539e  jb      short loc_1800153A5
0x1800153a0  mov     r9, [rsi]
0x1800153a3  jmp     short loc_1800153A8
0x1800153a5  mov     r9, rsi
0x1800153a8  mov     edx, 22h ; '"'
0x1800153ad  mov     [rsp+0C0h+var_A0], rax
0x1800153b2  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800153b9  mov     rcx, [rcx+10h]
0x1800153bd  call    WPP_SF_SS
0x1800153c2  lea     rax, [rbp+57h+var_48]
0x1800153c6  cmp     [rbp+57h+var_30], 8
0x1800153cb  cmovnb  rax, [rbp+57h+var_48]
0x1800153d0  mov     [rbp+57h+var_88], rax
0x1800153d4  lea     rdx, [rbp+57h+var_88]
0x1800153d8  lea     rcx, [rbp+57h+var_70]
0x1800153dc  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800153e1  cmp     qword ptr [rsi+18h], 8
0x1800153e6  jb      short loc_1800153ED
0x1800153e8  mov     rax, [rsi]
0x1800153eb  jmp     short loc_1800153F0
0x1800153ed  mov     rax, rsi
0x1800153f0  mov     [rbp+57h+var_88], rax
0x1800153f4  lea     rdx, [rbp+57h+var_88]
0x1800153f8  lea     rcx, [rbp+57h+string]
0x1800153fc  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180015401  mov     [rbp+57h+var_68], r15
0x180015405  mov     [rbp+57h+var_60], r15
0x180015409  mov     [rbp+57h+var_90], r15
0x18001540d  mov     [rbp+57h+var_58], r15
0x180015411  lea     rcx, [rbp+57h+var_80]; struct Windows::Management::Deployment::IPackageManager **
0x180015415  call    ?GetPackageManager@@YAJPEAPEAUIPackageManager@Deployment@Management@Windows@@@Z; GetPackageManager(Windows::Management::Deployment::IPackageManager * *)
0x18001541a  mov     ebx, eax
0x18001541c  test    eax, eax
0x18001541e  jns     short loc_18001546A
0x180015420  mov     rcx, cs:WPP_GLOBAL_Control
0x180015427  cmp     rcx, rdi
0x18001542a  jz      short loc_18001544B
0x18001542c  test    byte ptr [rcx+1Ch], 4
0x180015430  jz      short loc_18001544B
0x180015432  mov     edx, 23h ; '#'
0x180015437  mov     r9d, eax
0x18001543a  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180015441  mov     rcx, [rcx+10h]
0x180015445  call    WPP_SF_d
0x18001544a  nop
0x18001544b  mov     rcx, [rbp+57h+var_90]
0x18001544f  test    rcx, rcx
0x180015452  jz      short loc_180015465
0x180015454  mov     [rbp+57h+var_90], r15
0x180015458  mov     rax, [rcx]
0x18001545b  mov     rax, [rax+10h]
0x18001545f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015464  nop
0x180015465  jmp     loc_18001554C
0x18001546a  mov     rcx, [rbp+57h+var_80]
0x18001546e  mov     rax, [rcx]
0x180015471  lea     r9, [rbp+57h+var_90]
0x180015475  mov     r8, [rbp+57h+string]
0x180015479  mov     rdx, [rbp+57h+var_70]
0x18001547d  mov     rax, [rax+0A8h]
0x180015484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015489  mov     ebx, eax
0x18001548b  test    eax, eax
0x18001548d  jns     short loc_1800154D6
0x18001548f  mov     rcx, cs:WPP_GLOBAL_Control
0x180015496  cmp     rcx, rdi
0x180015499  jz      short loc_1800154BA
0x18001549b  test    byte ptr [rcx+1Ch], 4
0x18001549f  jz      short loc_1800154BA
0x1800154a1  mov     edx, 24h ; '$'
0x1800154a6  mov     r9d, eax
0x1800154a9  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800154b0  mov     rcx, [rcx+10h]
0x1800154b4  call    WPP_SF_d
0x1800154b9  nop
0x1800154ba  mov     rcx, [rbp+57h+var_90]
0x1800154be  test    rcx, rcx
0x1800154c1  jz      short loc_1800154D4
0x1800154c3  mov     [rbp+57h+var_90], r15
0x1800154c7  mov     rax, [rcx]
0x1800154ca  mov     rax, [rax+10h]
0x1800154ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154d3  nop
0x1800154d4  jmp     short loc_18001554C
0x1800154d6  mov     rcx, [rbp+57h+var_90]
0x1800154da  test    rcx, rcx
0x1800154dd  jz      short loc_180015531
0x1800154df  mov     [rbp+57h+var_88], rcx
0x1800154e3  mov     rax, [rcx]
0x1800154e6  mov     rax, [rax+8]
0x1800154ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154ef  nop
0x1800154f0  mov     rdx, r14
0x1800154f3  lea     rcx, [rbp+57h+var_88]
0x1800154f7  call    ?GetPackageInfo@@YAJV?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@AEAUPackageInfo@@@Z; GetPackageInfo(Microsoft::WRL::ComPtr<Windows::ApplicationModel::IPackage>,PackageInfo &)
0x1800154fc  mov     ebx, eax
0x1800154fe  test    eax, eax
0x180015500  jns     short loc_18001551E
0x180015502  mov     rcx, [rbp+57h+var_90]
0x180015506  test    rcx, rcx
0x180015509  jz      short loc_18001551C
0x18001550b  mov     [rbp+57h+var_90], r15
0x18001550f  mov     rax, [rcx]
0x180015512  mov     rax, [rax+10h]
0x180015516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001551b  nop
0x18001551c  jmp     short loc_18001554C
0x18001551e  lea     rcx, [r14+20h]
0x180015522  lea     rdx, [rbp+57h+var_48]
0x180015526  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18001552b  mov     rcx, [rbp+57h+var_90]
0x18001552f  jmp     short loc_180015536
0x180015531  mov     ebx, 8FFF0006h
0x180015536  test    rcx, rcx
0x180015539  jz      short loc_18001554C
0x18001553b  mov     [rbp+57h+var_90], r15
0x18001553f  mov     rax, [rcx]
0x180015542  mov     rax, [rax+10h]
0x180015546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001554b  nop
0x18001554c  mov     rcx, [rbp+57h+var_80]
0x180015550  test    rcx, rcx
0x180015553  jz      short loc_180015565
0x180015555  mov     rax, [rcx]
0x180015558  mov     rax, [rax+10h]
0x18001555c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015561  mov     [rbp+57h+var_80], r15
0x180015565  call    cs:__imp_RoUninitialize
0x18001556c  nop     dword ptr [rax+rax+00h]
0x180015571  nop
0x180015572  mov     rcx, [rbp+57h+string]; string
0x180015576  call    cs:__imp_WindowsDeleteString
0x18001557d  nop     dword ptr [rax+rax+00h]
0x180015582  mov     [rbp+57h+string], r15
0x180015586  xor     r8d, r8d
0x180015589  mov     dl, 1
0x18001558b  lea     rcx, [rbp+57h+var_48]
0x18001558f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015594  nop
0x180015595  mov     rcx, [rbp+57h+var_70]; string
0x180015599  call    cs:__imp_WindowsDeleteString
0x1800155a0  nop     dword ptr [rax+rax+00h]
0x1800155a5  mov     [rbp+57h+var_70], r15
0x1800155a9  xor     r8d, r8d
0x1800155ac  mov     dl, 1
0x1800155ae  mov     rcx, rsi
0x1800155b1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800155b6  mov     eax, ebx
0x1800155b8  mov     rcx, [rbp+57h+var_28]
0x1800155bc  xor     rcx, rsp; StackCookie
0x1800155bf  call    __security_check_cookie
0x1800155c4  mov     rbx, [rsp+0C0h+arg_10]
0x1800155cc  add     rsp, 0A0h
0x1800155d3  pop     r15
0x1800155d5  pop     r14
0x1800155d7  pop     rdi
0x1800155d8  pop     rsi
0x1800155d9  pop     rbp
0x1800155da  retn
```
