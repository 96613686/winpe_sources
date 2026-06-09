# Windows::Service::Task::Create(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x140252078`
- end: `0x14025247e`
- name: `?Create@Task@Service@Windows@@SA?AV123@V?$basic_zstring_view@_W@wil@@00@Z`
- size: `1030`
- prototype: `__int64 __fastcall(__int64, __int128 *, const OLECHAR **, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1402527c0`

## callees

- `0x14003fee4`
- `0x14003ff28`
- `0x1400413a8`
- `0x1402500f8`
- `0x140250480`
- `0x140252078`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x14025220d`
- `OLEAUT32!__imp_SysAllocString` at `0x14025225f`
- `OLEAUT32!__imp_SysAllocString` at `0x14025220d`
- `OLEAUT32!__imp_SysAllocString` at `0x14025225f`
- `OLEAUT32!__imp_SysFreeString` at `0x14025224b`
- `OLEAUT32!__imp_SysFreeString` at `0x14025229d`
- `OLEAUT32!__imp_SysFreeString` at `0x14025233d`
- `OLEAUT32!__imp_SysFreeString` at `0x14025234d`
- `OLEAUT32!__imp_SysFreeString` at `0x140252389`
- `OLEAUT32!__imp_SysFreeString` at `0x14025224b`
- `OLEAUT32!__imp_SysFreeString` at `0x14025229d`
- `OLEAUT32!__imp_SysFreeString` at `0x14025233d`
- `OLEAUT32!__imp_SysFreeString` at `0x14025234d`
- `OLEAUT32!__imp_SysFreeString` at `0x140252389`

## string_xrefs

- `0x140252433`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140252445`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x14025246c`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x1402523b5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402523ca`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402523df`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402523f4`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252409`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x14025241e`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x14025245a`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x1402520ba`: `Microsoft\Windows\UpdateOrchestrator`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Service::Task::Create(__int64 a1, __int128 *a2, const OLECHAR **a3, __int64 a4)
{
  __int64 v8; // rax
  int v9; // eax
  const OLECHAR *v10; // rdx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  int v17; // eax
  int v18; // eax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, BSTR); // r14
  BSTR v21; // rax
  const char *v22; // r9
  OLECHAR *v23; // rdi
  int v24; // eax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, BSTR); // r14
  BSTR v27; // rax
  const char *v28; // r9
  OLECHAR *v29; // rdi
  int v30; // eax
  __int64 v31; // r9
  _QWORD v33[3]; // [rsp+28h] [rbp-61h] BYREF
  __int128 v34; // [rsp+40h] [rbp-49h] BYREF
  __int64 *v35; // [rsp+50h] [rbp-39h] BYREF
  __int64 v36; // [rsp+58h] [rbp-31h] BYREF
  __int64 v37; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v38; // [rsp+68h] [rbp-21h] BYREF
  __int64 v39; // [rsp+70h] [rbp-19h] BYREF
  int v40[2]; // [rsp+78h] [rbp-11h] BYREF
  BSTR v41; // [rsp+80h] [rbp-9h] BYREF
  BSTR bstrString; // [rsp+88h] [rbp-1h] BYREF
  BSTR v43; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v41 = 0;
  wil::make_bstr(&v41, L"Microsoft\\Windows\\UpdateOrchestrator");
  v33[1] = 0;
  *(_QWORD *)v40 = 0;
  Windows::Service::Task::TaskService((int)v40);
  v35 = 0;
  v8 = **(_QWORD **)v40;
  v35 = 0;
  v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 **))(v8 + 72))(*(_QWORD *)v40, 0, &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v9,
      0);
  v43 = 0;
  wil::make_bstr(&v43, *a3);
  bstrString = 0;
  v10 = &psz;
  if ( *(_QWORD *)(a4 + 8) )
    v10 = *(const OLECHAR **)a4;
  wil::make_bstr(&bstrString, v10);
  v39 = 0;
  v11 = *v35;
  v39 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v11 + 88))(v35, &v39);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C3,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v12,
      0);
  v13 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 176LL))(v39, 0xFFFFFFFFLL);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C4,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v13,
      0);
  v38 = 0;
  v14 = *v35;
  v38 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v14 + 136))(v35, &v38);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v15,
      0);
  v37 = 0;
  v16 = *v38;
  v37 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v16 + 96))(v38, 0, &v37);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v17,
      0);
  v36 = 0;
  v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v37)(
          v37,
          &GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047,
          &v36);
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v18,
      0);
  v19 = v36;
  v20 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v36 + 88LL);
  v21 = SysAllocString(*a3);
  v23 = v21;
  v33[0] = v21;
  if ( !v21 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v22);
  v24 = v20(v19, v21);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v24,
      48);
  SysFreeString(v23);
  v25 = v36;
  v26 = *(__int64 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v36 + 104LL);
  v27 = SysAllocString(*(const OLECHAR **)a4);
  v29 = v27;
  v33[0] = v27;
  if ( !v27 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x138D,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
      v28);
  v30 = v26(v25, v27);
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v30,
      80);
  SysFreeString(v29);
  v33[0] = v35;
  if ( v35 )
    (*(void (__fastcall **)(__int64 *))(*v35 + 8))(v35);
  v34 = *a2;
  LOBYTE(v31) = 1;
  ((void (__fastcall *)(__int64, __int128 *, _QWORD *, __int64, int))Windows::Service::Task::Task)(
    a1,
    &v34,
    v33,
    v31,
    80);
  if ( v36 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64 *))(*v38 + 16))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( v43 )
    SysFreeString(v43);
  if ( v35 )
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
  if ( *(_QWORD *)v40 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
  if ( v41 )
    SysFreeString(v41);
  return a1;
}

```

## disassembly

```asm
0x140252078  push    rbp
0x14025207a  push    rbx
0x14025207b  push    rsi
0x14025207c  push    rdi
0x14025207d  push    r12
0x14025207f  push    r13
0x140252081  push    r14
0x140252083  push    r15
0x140252085  lea     rbp, [rsp-1Fh]
0x14025208a  sub     rsp, 0A8h
0x140252091  mov     rax, cs:__security_cookie
0x140252098  xor     rax, rsp
0x14025209b  mov     [rbp+57h+var_48], rax
0x14025209f  mov     rsi, r9
0x1402520a2  mov     rdi, r8
0x1402520a5  mov     r12, rdx
0x1402520a8  mov     r15, rcx
0x1402520ab  mov     [rbp+57h+var_60], rcx
0x1402520af  xor     r13d, r13d
0x1402520b2  mov     [rbp+57h+var_C0], r13d
0x1402520b6  mov     [rbp+57h+var_60], r13
0x1402520ba  lea     rdx, sourceString; "Microsoft\\Windows\\UpdateOrchestrator"
0x1402520c1  lea     rcx, [rbp+57h+var_60]
0x1402520c5  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x1402520ca  nop
0x1402520cb  mov     [rbp+57h+var_B0], r13
0x1402520cf  mov     qword ptr [rbp+57h+var_68], r13
0x1402520d3  lea     rcx, [rbp+57h+var_68]; int
0x1402520d7  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x1402520dc  nop
0x1402520dd  mov     [rbp+57h+var_90], r13
0x1402520e1  mov     rcx, qword ptr [rbp+57h+var_68]
0x1402520e5  mov     rax, [rcx]
0x1402520e8  mov     [rbp+57h+var_90], r13
0x1402520ec  lea     r8, [rbp+57h+var_90]
0x1402520f0  xor     edx, edx
0x1402520f2  mov     rax, [rax+48h]
0x1402520f6  call    _guard_dispatch_icall
0x1402520fb  mov     rcx, [rbp+5Fh]; this
0x1402520ff  test    eax, eax
0x140252101  js      loc_1402523C7
0x140252107  mov     [rbp+57h+var_50], r13
0x14025210b  mov     rdx, [rdi]
0x14025210e  lea     rcx, [rbp+57h+var_50]
0x140252112  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x140252117  nop
0x140252118  mov     [rbp+57h+bstrString], r13
0x14025211c  cmp     [rsi+8], r13
0x140252120  lea     rdx, psz
0x140252127  jz      short loc_14025212C
0x140252129  mov     rdx, [rsi]
0x14025212c  lea     rcx, [rbp+57h+bstrString]
0x140252130  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@1@PEB_W@Z; wil::make_bstr(wchar_t const *)
0x140252135  nop
0x140252136  mov     [rbp+57h+var_70], r13
0x14025213a  mov     rcx, [rbp+57h+var_90]
0x14025213e  mov     rax, [rcx]
0x140252141  mov     [rbp+57h+var_70], r13
0x140252145  lea     rdx, [rbp+57h+var_70]
0x140252149  mov     rax, [rax+58h]
0x14025214d  call    _guard_dispatch_icall
0x140252152  mov     rcx, [rbp+5Fh]; this
0x140252156  test    eax, eax
0x140252158  js      loc_1402523DC
0x14025215e  or      edx, 0FFFFFFFFh
0x140252161  mov     rcx, [rbp+57h+var_70]
0x140252165  mov     rax, [rcx]
0x140252168  mov     rax, [rax+0B0h]
0x14025216f  call    _guard_dispatch_icall
0x140252174  mov     rcx, [rbp+5Fh]; this
0x140252178  test    eax, eax
0x14025217a  js      loc_1402523F1
0x140252180  mov     [rbp+57h+var_78], r13
0x140252184  mov     rcx, [rbp+57h+var_90]
0x140252188  mov     rax, [rcx]
0x14025218b  mov     [rbp+57h+var_78], r13
0x14025218f  lea     rdx, [rbp+57h+var_78]
0x140252193  mov     rax, [rax+88h]
0x14025219a  call    _guard_dispatch_icall
0x14025219f  mov     rcx, [rbp+5Fh]; this
0x1402521a3  test    eax, eax
0x1402521a5  js      loc_140252406
0x1402521ab  mov     [rbp+57h+var_80], r13
0x1402521af  mov     rcx, [rbp+57h+var_78]
0x1402521b3  mov     rax, [rcx]
0x1402521b6  mov     [rbp+57h+var_80], r13
0x1402521ba  lea     r8, [rbp+57h+var_80]
0x1402521be  xor     edx, edx
0x1402521c0  mov     rax, [rax+60h]
0x1402521c4  call    _guard_dispatch_icall
0x1402521c9  mov     rcx, [rbp+5Fh]; this
0x1402521cd  test    eax, eax
0x1402521cf  js      loc_14025241B
0x1402521d5  mov     rcx, [rbp+57h+var_80]
0x1402521d9  mov     [rbp+57h+var_88], r13
0x1402521dd  mov     rax, [rcx]
0x1402521e0  lea     r8, [rbp+57h+var_88]
0x1402521e4  lea     rdx, _GUID_4c3d624d_fd6b_49a3_b9b7_09cb3cd3f047
0x1402521eb  mov     rax, [rax]
0x1402521ee  call    _guard_dispatch_icall
0x1402521f3  mov     rcx, [rbp+5Fh]; this
0x1402521f7  test    eax, eax
0x1402521f9  js      loc_140252430
0x1402521ff  mov     rbx, [rbp+57h+var_88]
0x140252203  mov     rax, [rbx]
0x140252206  mov     r14, [rax+58h]
0x14025220a  mov     rcx, [rdi]; psz
0x14025220d  call    cs:__imp_SysAllocString
0x140252213  mov     rdi, rax
0x140252216  mov     [rbp+57h+var_B8], rax
0x14025221a  mov     [rbp+57h+var_C0], 30h ; '0'
0x140252221  mov     rcx, [rbp+5Fh]; this
0x140252225  test    rax, rax
0x140252228  jz      loc_140252445
0x14025222e  mov     rdx, rax
0x140252231  mov     rcx, rbx
0x140252234  mov     rax, r14
0x140252237  call    _guard_dispatch_icall
0x14025223c  mov     rcx, [rbp+5Fh]; this
0x140252240  test    eax, eax
0x140252242  js      loc_140252457
0x140252248  mov     rcx, rdi; bstrString
0x14025224b  call    cs:__imp_SysFreeString
0x140252251  mov     rbx, [rbp+57h+var_88]
0x140252255  mov     rax, [rbx]
0x140252258  mov     r14, [rax+68h]
0x14025225c  mov     rcx, [rsi]; psz
0x14025225f  call    cs:__imp_SysAllocString
0x140252265  mov     rdi, rax
0x140252268  mov     [rbp+57h+var_B8], rax
0x14025226c  mov     [rbp+57h+var_C0], 50h ; 'P'
0x140252273  mov     rcx, [rbp+5Fh]; this
0x140252277  test    rax, rax
0x14025227a  jz      loc_14025246C
0x140252280  mov     rdx, rax
0x140252283  mov     rcx, rbx
0x140252286  mov     rax, r14
0x140252289  call    _guard_dispatch_icall
0x14025228e  mov     rcx, [rbp+5Fh]; this
0x140252292  test    eax, eax
0x140252294  js      loc_1402523B2
0x14025229a  mov     rcx, rdi; bstrString
0x14025229d  call    cs:__imp_SysFreeString
0x1402522a3  nop
0x1402522a4  mov     rcx, [rbp+57h+var_90]
0x1402522a8  mov     [rbp+57h+var_B8], rcx
0x1402522ac  test    rcx, rcx
0x1402522af  jz      short loc_1402522BE
0x1402522b1  mov     rax, [rcx]
0x1402522b4  mov     rax, [rax+8]
0x1402522b8  call    _guard_dispatch_icall
0x1402522bd  nop
0x1402522be  movaps  xmm0, xmmword ptr [r12]
0x1402522c3  movdqa  [rbp+57h+var_A0], xmm0
0x1402522c8  mov     r9b, 1
0x1402522cb  lea     r8, [rbp+57h+var_B8]
0x1402522cf  lea     rdx, [rbp+57h+var_A0]
0x1402522d3  mov     rcx, r15
0x1402522d6  call    ??0Task@Service@Windows@@QEAA@V?$basic_zstring_view@_W@wil@@V?$com_ptr_t@UITaskDefinition@@Uerr_exception_policy@wil@@@4@_N@Z; Windows::Service::Task::Task(wil::basic_zstring_view<wchar_t>,wil::com_ptr_t<ITaskDefinition,wil::err_exception_policy>,bool)
0x1402522db  nop
0x1402522dc  mov     rcx, [rbp+57h+var_88]
0x1402522e0  test    rcx, rcx
0x1402522e3  jz      short loc_1402522F2
0x1402522e5  mov     rax, [rcx]
0x1402522e8  mov     rax, [rax+10h]
0x1402522ec  call    _guard_dispatch_icall
0x1402522f1  nop
0x1402522f2  mov     rcx, [rbp+57h+var_80]
0x1402522f6  test    rcx, rcx
0x1402522f9  jz      short loc_140252308
0x1402522fb  mov     rax, [rcx]
0x1402522fe  mov     rax, [rax+10h]
0x140252302  call    _guard_dispatch_icall
0x140252307  nop
0x140252308  mov     rcx, [rbp+57h+var_78]
0x14025230c  test    rcx, rcx
0x14025230f  jz      short loc_14025231E
0x140252311  mov     rax, [rcx]
0x140252314  mov     rax, [rax+10h]
0x140252318  call    _guard_dispatch_icall
0x14025231d  nop
0x14025231e  mov     rcx, [rbp+57h+var_70]
0x140252322  test    rcx, rcx
0x140252325  jz      short loc_140252334
0x140252327  mov     rax, [rcx]
0x14025232a  mov     rax, [rax+10h]
0x14025232e  call    _guard_dispatch_icall
0x140252333  nop
0x140252334  mov     rcx, [rbp+57h+bstrString]; bstrString
0x140252338  test    rcx, rcx
0x14025233b  jz      short loc_140252344
0x14025233d  call    cs:__imp_SysFreeString
0x140252343  nop
0x140252344  mov     rcx, [rbp+57h+var_50]; bstrString
0x140252348  test    rcx, rcx
0x14025234b  jz      short loc_140252354
0x14025234d  call    cs:__imp_SysFreeString
0x140252353  nop
0x140252354  mov     rcx, [rbp+57h+var_90]
0x140252358  test    rcx, rcx
0x14025235b  jz      short loc_14025236A
0x14025235d  mov     rax, [rcx]
0x140252360  mov     rax, [rax+10h]
0x140252364  call    _guard_dispatch_icall
0x140252369  nop
0x14025236a  mov     rcx, qword ptr [rbp+57h+var_68]
0x14025236e  test    rcx, rcx
0x140252371  jz      short loc_140252380
0x140252373  mov     rax, [rcx]
0x140252376  mov     rax, [rax+10h]
0x14025237a  call    _guard_dispatch_icall
0x14025237f  nop
0x140252380  mov     rcx, [rbp+57h+var_60]; bstrString
0x140252384  test    rcx, rcx
0x140252387  jz      short loc_14025238F
0x140252389  call    cs:__imp_SysFreeString
0x14025238f  mov     rax, r15
0x140252392  mov     rcx, [rbp+57h+var_48]
0x140252396  xor     rcx, rsp; StackCookie
0x140252399  call    __security_check_cookie
0x14025239e  add     rsp, 0A8h
0x1402523a5  pop     r15
0x1402523a7  pop     r14
0x1402523a9  pop     r13
0x1402523ab  pop     r12
0x1402523ad  pop     rdi
0x1402523ae  pop     rsi
0x1402523af  pop     rbx
0x1402523b0  pop     rbp
0x1402523b1  retn
0x1402523b2  mov     r9d, eax; char *
0x1402523b5  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402523bc  mov     edx, 1D0h; void *
0x1402523c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402523c7  mov     r9d, eax; char *
0x1402523ca  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402523d1  mov     edx, 1BCh; void *
0x1402523d6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402523dc  mov     r9d, eax; char *
0x1402523df  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402523e6  mov     edx, 1C3h; void *
0x1402523eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1402523f1  mov     r9d, eax; char *
0x1402523f4  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1402523fb  mov     edx, 1C4h; void *
0x140252400  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140252406  mov     r9d, eax; char *
0x140252409  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140252410  mov     edx, 1C7h; void *
0x140252415  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14025241b  mov     r9d, eax; char *
0x14025241e  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140252425  mov     edx, 1CAh; void *
0x14025242a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140252430  mov     r9d, eax; char *
0x140252433  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14025243a  mov     edx, 1C96h; void *
0x14025243f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140252445  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x14025244c  mov     edx, 138Dh; void *
0x140252451  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x140252457  mov     r9d, eax; char *
0x14025245a  lea     r8, aCW1SSrcOrchest_98; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140252461  mov     edx, 1CEh; void *
0x140252466  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14025246c  lea     r8, aCW1SPackagesMi_3; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x140252473  mov     edx, 138Dh; void *
0x140252478  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
