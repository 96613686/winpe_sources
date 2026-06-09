# Windows::AI::IsolationEnvironment::ProvisionResult::RuntimeClassInitialize(std::shared_ptr<AgentUser> const &,std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>>> const &)

- ea: `0x180047e00`
- end: `0x180047ffa`
- name: `?RuntimeClassInitialize@ProvisionResult@IsolationEnvironment@AI@Windows@@QEAAJAEBV?$shared_ptr@VAgentUser@@@std@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@6@@Z`
- size: `506`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800142c4`

## callees

- `0x18000a464`
- `0x18003c79c`
- `0x180047b38`
- `0x180047bac`
- `0x180047e00`
- `0x180048478`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180047fee`

## string_xrefs

- `0x180047e86`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\provisionresult.cpp`
- `0x180047fd8`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\provisionresult.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::AI::IsolationEnvironment::ProvisionResult::RuntimeClassInitialize(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  HSTRING v6; // rax
  HSTRING v7; // rax
  int AppConnection; // eax
  unsigned int v9; // esi
  __int64 v11; // rcx
  __int64 v12; // rsi
  HSTRING v13; // rax
  HSTRING v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rbx
  _QWORD *v17; // r14
  const WCHAR *v18; // rax
  HRESULT v19; // eax
  HSTRING *v20; // rdx
  HSTRING v21; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  __int64 v25; // [rsp+58h] [rbp+38h] BYREF
  const WCHAR *v26; // [rsp+68h] [rbp+48h] BYREF

  *(_QWORD *)(a1 + 48) = 0;
  v6 = (HSTRING)(*a2 + 80LL);
  if ( *(_QWORD *)(*a2 + 104LL) > 7u )
    v6 = *(HSTRING *)v6;
  string = v6;
  Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)(a1 + 56), (const WCHAR **)&string);
  v7 = (HSTRING)(*a2 + 144LL);
  if ( *(_QWORD *)(*a2 + 168LL) > 7u )
    v7 = *(HSTRING *)v7;
  string = v7;
  Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)(a1 + 64), (const WCHAR **)&string);
  v25 = 0;
  AppConnection = AgentUser::GetAppConnection(*a2, &v25);
  v9 = AppConnection;
  if ( AppConnection >= 0 )
  {
    v11 = v25;
    v25 = 0;
    v12 = *(_QWORD *)(a1 + 72);
    *(_QWORD *)(a1 + 72) = v11;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    v13 = (HSTRING)(*a2 + 248LL);
    if ( *(_QWORD *)(*a2 + 272LL) > 7u )
      v13 = *(HSTRING *)v13;
    string = v13;
    Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)(a1 + 88), (const WCHAR **)&string);
    v14 = (HSTRING)(*(_QWORD *)(*a2 + 48LL) + 80LL);
    if ( *(_QWORD *)(*(_QWORD *)(*a2 + 48LL) + 104LL) > 7u )
      v14 = *(HSTRING *)v14;
    string = v14;
    Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>((HSTRING *)(a1 + 80), (const WCHAR **)&string);
    v15 = a1 + 104;
    std::vector<Microsoft::WRL::Wrappers::HString>::reserve(a1 + 104, (__int64)(a3[1] - *a3) >> 5);
    v16 = (_QWORD *)*a3;
    v17 = (_QWORD *)a3[1];
    while ( 1 )
    {
      if ( v16 == v17 )
        return 0;
      string = 0;
      v18 = v16[3] <= 7u ? (const WCHAR *)v16 : (const WCHAR *)*v16;
      v26 = v18;
      v19 = Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(&string, &v26);
      v9 = v19;
      if ( v19 < 0 )
        break;
      v20 = *(HSTRING **)(v15 + 8);
      if ( v20 == *(HSTRING **)(v15 + 16) )
      {
        std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(
          v15,
          v20,
          &string);
        v21 = string;
      }
      else
      {
        *v20 = string;
        v21 = 0;
        string = 0;
        *(_QWORD *)(v15 + 8) += 8LL;
      }
      WindowsDeleteString(v21);
      v16 += 4;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\provisionresult.cpp",
      (const char *)(unsigned int)v19,
      savedregs);
    WindowsDeleteString(string);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\provisionresult.cpp",
      (const char *)(unsigned int)AppConnection,
      savedregs);
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return v9;
}

```

## disassembly

```asm
0x180047e00  push    rbp
0x180047e02  push    rbx
0x180047e03  push    rsi
0x180047e04  push    rdi
0x180047e05  push    r14; int
0x180047e07  mov     rbp, rsp
0x180047e0a  sub     rsp, 20h
0x180047e0e  mov     r14, r8
0x180047e11  mov     rdi, rdx
0x180047e14  mov     rbx, rcx
0x180047e17  mov     qword ptr [rcx+30h], 0
0x180047e1f  mov     rax, [rdx]
0x180047e22  add     rax, 50h ; 'P'
0x180047e26  cmp     qword ptr [rax+18h], 7
0x180047e2b  jbe     short loc_180047E30
0x180047e2d  mov     rax, [rax]
0x180047e30  mov     [rbp+string], rax
0x180047e34  add     rcx, 38h ; '8'; string
0x180047e38  lea     rdx, [rbp+string]
0x180047e3c  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180047e41  mov     rax, [rdi]
0x180047e44  add     rax, 90h
0x180047e4a  cmp     qword ptr [rax+18h], 7
0x180047e4f  jbe     short loc_180047E54
0x180047e51  mov     rax, [rax]
0x180047e54  mov     [rbp+string], rax
0x180047e58  lea     rcx, [rbx+40h]; string
0x180047e5c  lea     rdx, [rbp+string]
0x180047e60  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180047e65  mov     [rbp+arg_8], 0
0x180047e6d  lea     rdx, [rbp+arg_8]
0x180047e71  mov     rcx, [rdi]
0x180047e74  call    ?GetAppConnection@AgentUser@@QEAAJAEAV?$com_ptr_t@VAppConnection@IsolationEnvironment@AI@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; AgentUser::GetAppConnection(wil::com_ptr_t<Windows::AI::IsolationEnvironment::AppConnection,wil::err_returncode_policy> &)
0x180047e79  mov     esi, eax
0x180047e7b  test    eax, eax
0x180047e7d  jns     short loc_180047EB5
0x180047e7f  mov     rcx, [rbp+28h]; this
0x180047e83  mov     r9d, eax; char *
0x180047e86  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180047e8d  mov     edx, 24h ; '$'; void *
0x180047e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047e97  nop
0x180047e98  mov     rcx, [rbp+arg_8]
0x180047e9c  test    rcx, rcx
0x180047e9f  jz      short loc_180047EAE
0x180047ea1  mov     rax, [rcx]
0x180047ea4  mov     rax, [rax+10h]
0x180047ea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047ead  nop
0x180047eae  mov     eax, esi
0x180047eb0  jmp     loc_180047FC6
0x180047eb5  mov     rcx, [rbp+arg_8]
0x180047eb9  mov     [rbp+arg_8], 0
0x180047ec1  mov     rsi, [rbx+48h]
0x180047ec5  mov     [rbx+48h], rcx
0x180047ec9  test    rcx, rcx
0x180047ecc  jz      short loc_180047EDA
0x180047ece  mov     rax, [rcx]
0x180047ed1  mov     rax, [rax+8]
0x180047ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eda  test    rsi, rsi
0x180047edd  jz      short loc_180047EEF
0x180047edf  mov     rax, [rsi]
0x180047ee2  mov     rcx, rsi
0x180047ee5  mov     rax, [rax+10h]
0x180047ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047eee  nop
0x180047eef  mov     rax, [rdi]
0x180047ef2  add     rax, 0F8h
0x180047ef8  cmp     qword ptr [rax+18h], 7
0x180047efd  jbe     short loc_180047F02
0x180047eff  mov     rax, [rax]
0x180047f02  mov     [rbp+string], rax
0x180047f06  lea     rcx, [rbx+58h]; string
0x180047f0a  lea     rdx, [rbp+string]
0x180047f0e  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180047f13  mov     rax, [rdi]
0x180047f16  mov     rcx, [rax+30h]
0x180047f1a  add     rcx, 50h ; 'P'
0x180047f1e  cmp     qword ptr [rcx+18h], 7
0x180047f23  jbe     short loc_180047F28
0x180047f25  mov     rcx, [rcx]
0x180047f28  mov     [rbp+string], rcx
0x180047f2c  lea     rcx, [rbx+50h]; string
0x180047f30  lea     rdx, [rbp+string]
0x180047f34  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180047f39  lea     rdi, [rbx+68h]
0x180047f3d  mov     rdx, [r14+8]
0x180047f41  sub     rdx, [r14]
0x180047f44  sar     rdx, 5
0x180047f48  mov     rcx, rdi
0x180047f4b  call    ?reserve@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAAX_K@Z; std::vector<Microsoft::WRL::Wrappers::HString>::reserve(unsigned __int64)
0x180047f50  mov     rbx, [r14]
0x180047f53  mov     r14, [r14+8]
0x180047f57  jmp     short loc_180047FBF
0x180047f59  mov     [rbp+string], 0
0x180047f61  cmp     qword ptr [rbx+18h], 7
0x180047f66  jbe     short loc_180047F6D
0x180047f68  mov     rax, [rbx]
0x180047f6b  jmp     short loc_180047F70
0x180047f6d  mov     rax, rbx
0x180047f70  mov     [rbp+arg_18], rax
0x180047f74  lea     rdx, [rbp+arg_18]
0x180047f78  lea     rcx, [rbp+string]; string
0x180047f7c  call    ??$Set@PEB_W@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEB_WUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<wchar_t const *>(wchar_t const * const &,Microsoft::WRL::Details::Dummy)
0x180047f81  mov     esi, eax
0x180047f83  test    eax, eax
0x180047f85  js      short loc_180047FD1
0x180047f87  mov     rdx, [rdi+8]
0x180047f8b  cmp     rdx, [rdi+10h]
0x180047f8f  jz      short loc_180047FA5
0x180047f91  mov     rax, [rbp+string]
0x180047f95  mov     [rdx], rax
0x180047f98  xor     ecx, ecx
0x180047f9a  mov     [rbp+string], rcx
0x180047f9e  add     qword ptr [rdi+8], 8
0x180047fa3  jmp     short loc_180047FB5
0x180047fa5  lea     r8, [rbp+string]
0x180047fa9  mov     rcx, rdi
0x180047fac  call    ??$_Emplace_reallocate@VHString@Wrappers@WRL@Microsoft@@@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@AEAAPEAVHString@Wrappers@WRL@Microsoft@@QEAV2345@$$QEAV2345@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::_Emplace_reallocate<Microsoft::WRL::Wrappers::HString>(Microsoft::WRL::Wrappers::HString * const,Microsoft::WRL::Wrappers::HString &&)
0x180047fb1  mov     rcx, [rbp+string]; string
0x180047fb5  call    cs:__imp_WindowsDeleteString
0x180047fbb  add     rbx, 20h ; ' '
0x180047fbf  cmp     rbx, r14
0x180047fc2  jnz     short loc_180047F59
0x180047fc4  xor     eax, eax
0x180047fc6  add     rsp, 20h
0x180047fca  pop     r14
0x180047fcc  pop     rdi
0x180047fcd  pop     rsi
0x180047fce  pop     rbx
0x180047fcf  pop     rbp
0x180047fd0  retn
0x180047fd1  mov     rcx, [rbp+28h]; this
0x180047fd5  mov     r9d, esi; char *
0x180047fd8  lea     r8, aOnecoreuapWind_3; "onecoreuap\\windows\\core\\isoenvbroker"...
0x180047fdf  mov     edx, 2Eh ; '.'; void *
0x180047fe4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047fe9  nop
0x180047fea  mov     rcx, [rbp+string]; string
0x180047fee  call    cs:__imp_WindowsDeleteString
0x180047ff4  nop
0x180047ff5  jmp     loc_180047EAE
```
