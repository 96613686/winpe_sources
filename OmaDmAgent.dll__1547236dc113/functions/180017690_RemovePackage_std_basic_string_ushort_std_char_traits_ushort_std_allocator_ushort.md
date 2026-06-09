# RemovePackage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180017690`
- end: `0x1800178ba`
- name: `?RemovePackage@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c354`

## callees

- `0x1800062ac`
- `0x18000a290`
- `0x18000a2c0`
- `0x18000a358`
- `0x180014fc4`
- `0x180016734`
- `0x180017690`
- `0x18001f420`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017881`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180017881`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800176bc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x1800176bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017875`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017875`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RemovePackage(_QWORD *a1)
{
  int PackageManager; // edi
  _QWORD *v3; // rax
  __int64 v4; // rcx
  _QWORD *v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v9; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  struct Windows::Management::Deployment::IPackageManager *v11; // [rsp+30h] [rbp-20h] BYREF
  _QWORD v12[2]; // [rsp+38h] [rbp-18h] BYREF

  v12[1] = a1;
  PackageManager = RoInitialize(1);
  if ( PackageManager >= 0 )
  {
    string = 0;
    if ( a1[3] < 8u )
      v3 = a1;
    else
      v3 = (_QWORD *)*a1;
    v12[0] = v3;
    Microsoft::WRL::Wrappers::HString::Set<unsigned short const *>(&string, v12);
    v11 = 0;
    v9 = 0;
    PackageManager = GetPackageManager(&v11);
    if ( PackageManager >= 0 )
    {
      PackageManager = (*(__int64 (__fastcall **)(struct Windows::Management::Deployment::IPackageManager *, HSTRING, __int64 *))(*(_QWORD *)v11 + 64LL))(
                         v11,
                         string,
                         &v9);
      if ( PackageManager >= 0 )
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          if ( a1[3] < 8u )
            v5 = a1;
          else
            v5 = (_QWORD *)*a1;
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids, v5);
        }
        v6 = v9;
        if ( v9 )
        {
          v9 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, &WPP_17887b334fcf349edf3df6ab34803119_Traceguids);
        v4 = v9;
        if ( v9 )
        {
          v9 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        }
      }
    }
    else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        80,
        &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
        (unsigned int)PackageManager);
    }
    WindowsDeleteString(string);
  }
  else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      79,
      &WPP_17887b334fcf349edf3df6ab34803119_Traceguids,
      (unsigned int)PackageManager);
  }
  RoUninitialize();
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(a1, v7, 0);
  return (unsigned int)PackageManager;
}

```

## disassembly

```asm
0x180017690  mov     [rsp-8+arg_8], rbx
0x180017695  mov     [rsp-8+arg_10], rdi
0x18001769a  push    rbp
0x18001769b  mov     rbp, rsp
0x18001769e  sub     rsp, 50h
0x1800176a2  mov     rax, cs:__security_cookie
0x1800176a9  xor     rax, rsp
0x1800176ac  mov     [rbp+var_8], rax
0x1800176b0  mov     rbx, rcx
0x1800176b3  mov     [rbp+var_10], rcx
0x1800176b7  mov     ecx, 1
0x1800176bc  call    cs:__imp_RoInitialize
0x1800176c3  nop     dword ptr [rax+rax+00h]
0x1800176c8  mov     edi, eax
0x1800176ca  test    eax, eax
0x1800176cc  jns     short loc_18001770C
0x1800176ce  lea     rcx, WPP_GLOBAL_Control
0x1800176d5  mov     rax, cs:WPP_GLOBAL_Control
0x1800176dc  cmp     rax, rcx
0x1800176df  jz      loc_180017881
0x1800176e5  test    byte ptr [rax+1Ch], 4
0x1800176e9  jz      loc_180017881
0x1800176ef  mov     edx, 4Fh ; 'O'
0x1800176f4  mov     r9d, edi
0x1800176f7  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800176fe  mov     rcx, [rax+10h]
0x180017702  call    WPP_SF_d
0x180017707  jmp     loc_180017881
0x18001770c  mov     [rbp+string], 0
0x180017714  cmp     qword ptr [rbx+18h], 8
0x180017719  jb      short loc_180017720
0x18001771b  mov     rax, [rbx]
0x18001771e  jmp     short loc_180017723
0x180017720  mov     rax, rbx
0x180017723  mov     [rbp+var_18], rax
0x180017727  lea     rdx, [rbp+var_18]
0x18001772b  lea     rcx, [rbp+string]
0x18001772f  call    ??$Set@PEBG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort const *>(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180017734  mov     [rbp+var_20], 0
0x18001773c  mov     [rbp+var_30], 0
0x180017744  lea     rcx, [rbp+var_20]; struct Windows::Management::Deployment::IPackageManager **
0x180017748  call    ?GetPackageManager@@YAJPEAPEAUIPackageManager@Deployment@Management@Windows@@@Z; GetPackageManager(Windows::Management::Deployment::IPackageManager * *)
0x18001774d  mov     edi, eax
0x18001774f  test    eax, eax
0x180017751  jns     short loc_1800177A8
0x180017753  lea     rcx, WPP_GLOBAL_Control
0x18001775a  mov     rax, cs:WPP_GLOBAL_Control
0x180017761  cmp     rax, rcx
0x180017764  jz      short loc_180017785
0x180017766  test    byte ptr [rax+1Ch], 4
0x18001776a  jz      short loc_180017785
0x18001776c  mov     edx, 50h ; 'P'
0x180017771  mov     r9d, edi
0x180017774  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x18001777b  mov     rcx, [rax+10h]
0x18001777f  call    WPP_SF_d
0x180017784  nop
0x180017785  mov     rcx, [rbp+var_30]
0x180017789  test    rcx, rcx
0x18001778c  jz      short loc_1800177A3
0x18001778e  mov     [rbp+var_30], 0
0x180017796  mov     rax, [rcx]
0x180017799  mov     rax, [rax+10h]
0x18001779d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177a2  nop
0x1800177a3  jmp     loc_180017871
0x1800177a8  mov     rcx, [rbp+var_20]
0x1800177ac  mov     rax, [rcx]
0x1800177af  lea     r8, [rbp+var_30]
0x1800177b3  mov     rdx, [rbp+string]
0x1800177b7  mov     rax, [rax+40h]
0x1800177bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177c0  mov     edi, eax
0x1800177c2  test    eax, eax
0x1800177c4  jns     short loc_180017815
0x1800177c6  lea     rcx, WPP_GLOBAL_Control
0x1800177cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800177d4  cmp     rax, rcx
0x1800177d7  jz      short loc_1800177F5
0x1800177d9  test    byte ptr [rax+1Ch], 4
0x1800177dd  jz      short loc_1800177F5
0x1800177df  mov     edx, 51h ; 'Q'
0x1800177e4  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x1800177eb  mov     rcx, [rax+10h]
0x1800177ef  call    WPP_SF_
0x1800177f4  nop
0x1800177f5  mov     rcx, [rbp+var_30]
0x1800177f9  test    rcx, rcx
0x1800177fc  jz      short loc_180017813
0x1800177fe  mov     [rbp+var_30], 0
0x180017806  mov     rax, [rcx]
0x180017809  mov     rax, [rax+10h]
0x18001780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017812  nop
0x180017813  jmp     short loc_180017871
0x180017815  lea     rcx, WPP_GLOBAL_Control
0x18001781c  mov     rax, cs:WPP_GLOBAL_Control
0x180017823  cmp     rax, rcx
0x180017826  jz      short loc_180017853
0x180017828  test    byte ptr [rax+1Ch], 1
0x18001782c  jz      short loc_180017853
0x18001782e  cmp     qword ptr [rbx+18h], 8
0x180017833  jb      short loc_18001783A
0x180017835  mov     r9, [rbx]
0x180017838  jmp     short loc_18001783D
0x18001783a  mov     r9, rbx
0x18001783d  mov     edx, 52h ; 'R'
0x180017842  lea     r8, WPP_17887b334fcf349edf3df6ab34803119_Traceguids
0x180017849  mov     rcx, [rax+10h]
0x18001784d  call    WPP_SF_S
0x180017852  nop
0x180017853  mov     rcx, [rbp+var_30]
0x180017857  test    rcx, rcx
0x18001785a  jz      short loc_180017871
0x18001785c  mov     [rbp+var_30], 0
0x180017864  mov     rax, [rcx]
0x180017867  mov     rax, [rax+10h]
0x18001786b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017870  nop
0x180017871  mov     rcx, [rbp+string]; string
0x180017875  call    cs:__imp_WindowsDeleteString
0x18001787c  nop     dword ptr [rax+rax+00h]
0x180017881  call    cs:__imp_RoUninitialize
0x180017888  nop     dword ptr [rax+rax+00h]
0x18001788d  nop
0x18001788e  xor     r8d, r8d
0x180017891  mov     dl, 1
0x180017893  mov     rcx, rbx
0x180017896  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001789b  mov     eax, edi
0x18001789d  mov     rcx, [rbp+var_8]
0x1800178a1  xor     rcx, rsp; StackCookie
0x1800178a4  call    __security_check_cookie
0x1800178a9  mov     rbx, [rsp+50h+arg_8]
0x1800178ae  mov     rdi, [rsp+50h+arg_10]
0x1800178b3  add     rsp, 50h
0x1800178b7  pop     rbp
0x1800178b8  retn
```
