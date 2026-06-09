# Windows::Service::Task::UpdateMaintenanceSettings(std::chrono::duration<int,std::ratio<86400,1>>,std::chrono::duration<int,std::ratio<86400,1>>,bool)

- ea: `0x1402528e0`
- end: `0x140252e64`
- name: `?UpdateMaintenanceSettings@Task@Service@Windows@@QEAAXV?$duration@HU?$ratio@$0BFBIA@$00@std@@@chrono@std@@0_N@Z`
- size: `1412`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140253680`
- `0x1402539f0`

## callees

- `0x140036d60`
- `0x14003fee4`
- `0x1400413a8`
- `0x140044b18`
- `0x140045404`
- `0x1401a2b3c`
- `0x1402528e0`
- `0x140378dc8`
- `0x140379070`
- `0x140380b50`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x140252b2a`
- `OLEAUT32!__imp_SysAllocString` at `0x140252c82`
- `OLEAUT32!__imp_SysAllocString` at `0x140252b2a`
- `OLEAUT32!__imp_SysAllocString` at `0x140252c82`
- `OLEAUT32!__imp_SysFreeString` at `0x140252b6c`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cde`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cf8`
- `OLEAUT32!__imp_SysFreeString` at `0x140252b6c`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cc1`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cde`
- `OLEAUT32!__imp_SysFreeString` at `0x140252cf8`

## string_xrefs

- `0x140252d9b`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\result_macros.h`
- `0x140252e16`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140252e52`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x140252d71`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252d86`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252db0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252dc5`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252dda`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252def`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252e04`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252e2b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`
- `0x140252e40`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall Windows::Service::Task::UpdateMaintenanceSettings(_BYTE *a1, unsigned int a2, unsigned int a3)
{
  int v6; // eax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const wchar_t *v20; // rdx
  __int64 *v21; // rbx
  __int64 (__fastcall *v22)(__int64 *, BSTR); // r12
  const OLECHAR *v23; // rcx
  BSTR v24; // rax
  const char *v25; // r9
  OLECHAR *v26; // r14
  int v27; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  const wchar_t *v33; // rdx
  __int64 *v34; // rbx
  __int64 (__fastcall *v35)(__int64 *, BSTR); // r14
  const OLECHAR *v36; // rcx
  BSTR v37; // rax
  const char *v38; // r9
  OLECHAR *v39; // rdi
  int v40; // eax
  int v41; // [rsp+28h] [rbp-E0h]
  __int128 Src_8; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v43; // [rsp+48h] [rbp-C0h]
  __int128 v44; // [rsp+58h] [rbp-B0h] BYREF
  __int128 v45; // [rsp+68h] [rbp-A0h]
  _BYTE v46[32]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v47[32]; // [rsp+98h] [rbp-70h] BYREF
  __int64 *v48; // [rsp+B8h] [rbp-50h] BYREF
  __int16 v49; // [rsp+C0h] [rbp-48h] BYREF
  BSTR bstrString; // [rsp+C8h] [rbp-40h] BYREF
  wchar_t *String1; // [rsp+D0h] [rbp-38h] BYREF
  __int64 *v52; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v53; // [rsp+E0h] [rbp-28h] BYREF
  wchar_t *psz[2]; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v55; // [rsp+F8h] [rbp-10h]
  wchar_t *String2[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v57; // [rsp+118h] [rbp+10h]
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]

  v41 = 0;
  v53 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)a1 + 88LL))(*(_QWORD *)a1, &v53);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x210,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v6,
      0);
  v52 = 0;
  v7 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 **))v53)(
         v53,
         &GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528,
         &v52);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C96,
      (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v7,
      0);
  v48 = 0;
  v8 = *v52;
  v48 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v8 + 408))(v52, &v48);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x216,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v9,
      0);
  v10 = v48;
  if ( !v48 )
  {
    v11 = *v52;
    v48 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v11 + 424))(v52, &v48);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x21B,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v12,
        0);
    v10 = v48;
  }
  v49 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int16 *))(*v10 + 96))(v10, &v49);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x221,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v13,
      0);
  if ( v49 )
  {
    v14 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v48 + 88))(v48, 0);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x224,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v14,
        0);
    a1[40] = 1;
  }
  String1 = 0;
  v15 = *v48;
  String1 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v15 + 64))(v48, &String1);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22A,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v16,
      0);
  v17 = std::to_wstring(v46, a2);
  v18 = std::wstring::insert(v17, 0);
  Src_8 = 0;
  v43 = 0;
  Src_8 = *(_OWORD *)v18;
  v43 = *(_OWORD *)(v18 + 16);
  *(_WORD *)v18 = 0;
  *(_QWORD *)(v18 + 16) = 0;
  *(_QWORD *)(v18 + 24) = 7;
  v19 = std::wstring::append(&Src_8);
  *(_OWORD *)String2 = 0;
  v57 = 0;
  *(_OWORD *)String2 = *(_OWORD *)v19;
  v57 = *(_OWORD *)(v19 + 16);
  *(_WORD *)v19 = 0;
  *(_QWORD *)(v19 + 16) = 0;
  *(_QWORD *)(v19 + 24) = 7;
  std::wstring::~wstring(&Src_8);
  std::wstring::~wstring(v46);
  v20 = (const wchar_t *)String2;
  if ( *((_QWORD *)&v57 + 1) > 7u )
    v20 = String2[0];
  if ( wcsicmp(String1, v20) )
  {
    v21 = v48;
    v22 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v48 + 56);
    v23 = (const OLECHAR *)String2;
    if ( *((_QWORD *)&v57 + 1) > 7u )
      v23 = String2[0];
    v24 = SysAllocString(v23);
    v26 = v24;
    v41 = 71;
    if ( !v24 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v25);
    v27 = v22(v21, v24);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v27,
        71);
    SysFreeString(v26);
    a1[40] = 1;
  }
  bstrString = 0;
  v28 = *v48;
  bstrString = 0;
  v29 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v28 + 80))(v48, &bstrString);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x235,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
      (const char *)(unsigned int)v29,
      v41);
  v30 = std::to_wstring(v47, a3);
  v31 = std::wstring::insert(v30, 0);
  v44 = 0;
  v45 = 0;
  v44 = *(_OWORD *)v31;
  v45 = *(_OWORD *)(v31 + 16);
  *(_WORD *)v31 = 0;
  *(_QWORD *)(v31 + 16) = 0;
  *(_QWORD *)(v31 + 24) = 7;
  v32 = std::wstring::append(&v44);
  *(_OWORD *)psz = 0;
  v55 = 0;
  *(_OWORD *)psz = *(_OWORD *)v32;
  v55 = *(_OWORD *)(v32 + 16);
  *(_WORD *)v32 = 0;
  *(_QWORD *)(v32 + 16) = 0;
  *(_QWORD *)(v32 + 24) = 7;
  std::wstring::~wstring(&v44);
  std::wstring::~wstring(v47);
  v33 = (const wchar_t *)psz;
  if ( *((_QWORD *)&v55 + 1) > 7u )
    v33 = psz[0];
  if ( wcsicmp(bstrString, v33) )
  {
    v34 = v48;
    v35 = *(__int64 (__fastcall **)(__int64 *, BSTR))(*v48 + 72);
    v36 = (const OLECHAR *)psz;
    if ( *((_QWORD *)&v55 + 1) > 7u )
      v36 = psz[0];
    v37 = SysAllocString(v36);
    v39 = v37;
    if ( !v37 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x138D,
        (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
        v38);
    v40 = v35(v34, v37);
    if ( v40 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23A,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Scheduler.cpp",
        (const char *)(unsigned int)v40,
        63);
    SysFreeString(v39);
    a1[40] = 1;
  }
  std::wstring::~wstring(psz);
  if ( bstrString )
    SysFreeString(bstrString);
  std::wstring::~wstring(String2);
  if ( String1 )
    SysFreeString(String1);
  if ( v48 )
    (*(void (__fastcall **)(__int64 *))(*v48 + 16))(v48);
  if ( v52 )
    (*(void (__fastcall **)(__int64 *))(*v52 + 16))(v52);
  if ( v53 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
}

```

## disassembly

```asm
0x1402528e0  mov     rax, rsp
0x1402528e3  mov     [rax+10h], rbx
0x1402528e7  mov     [rax+18h], rsi
0x1402528eb  mov     [rax+20h], rdi
0x1402528ef  push    rbp
0x1402528f0  push    r12
0x1402528f2  push    r13
0x1402528f4  push    r14
0x1402528f6  push    r15
0x1402528f8  lea     rbp, [rax-58h]
0x1402528fc  sub     rsp, 130h
0x140252903  mov     rax, cs:__security_cookie
0x14025290a  xor     rax, rsp
0x14025290d  mov     [rbp+50h+var_30], rax
0x140252911  mov     edi, r8d
0x140252914  mov     ebx, edx
0x140252916  mov     r15, rcx
0x140252919  xor     r13d, r13d
0x14025291c  mov     [rsp+150h+var_130], r13d; int
0x140252921  mov     [rbp+50h+var_78], r13
0x140252925  mov     rcx, [rcx]
0x140252928  mov     rax, [rcx]
0x14025292b  mov     [rbp+50h+var_78], r13
0x14025292f  lea     rdx, [rbp+50h+var_78]
0x140252933  mov     rax, [rax+58h]
0x140252937  call    _guard_dispatch_icall
0x14025293c  mov     rcx, [rbp+58h]; this
0x140252940  test    eax, eax
0x140252942  js      loc_140252D83
0x140252948  mov     rcx, [rbp+50h+var_78]
0x14025294c  mov     [rbp+50h+var_80], r13
0x140252950  mov     rax, [rcx]
0x140252953  lea     r8, [rbp+50h+var_80]
0x140252957  lea     rdx, _GUID_0ad9d0d7_0c7f_4ebb_9a5f_d1c648dca528
0x14025295e  mov     rax, [rax]
0x140252961  call    _guard_dispatch_icall
0x140252966  mov     rcx, [rbp+58h]; this
0x14025296a  test    eax, eax
0x14025296c  js      loc_140252D98
0x140252972  lea     r12d, [r13+1]
0x140252976  mov     esi, r12d
0x140252979  mov     [rbp+50h+var_A0], r13
0x14025297d  mov     rcx, [rbp+50h+var_80]
0x140252981  mov     rax, [rcx]
0x140252984  mov     [rbp+50h+var_A0], r13
0x140252988  lea     rdx, [rbp+50h+var_A0]
0x14025298c  mov     rax, [rax+198h]
0x140252993  call    _guard_dispatch_icall
0x140252998  mov     rcx, [rbp+58h]; this
0x14025299c  test    eax, eax
0x14025299e  js      loc_140252DAD
0x1402529a4  mov     rcx, [rbp+50h+var_A0]
0x1402529a8  test    rcx, rcx
0x1402529ab  jnz     short loc_1402529D8
0x1402529ad  mov     rcx, [rbp+50h+var_80]
0x1402529b1  mov     rax, [rcx]
0x1402529b4  mov     [rbp+50h+var_A0], r13
0x1402529b8  lea     rdx, [rbp+50h+var_A0]
0x1402529bc  mov     rax, [rax+1A8h]
0x1402529c3  call    _guard_dispatch_icall
0x1402529c8  mov     rcx, [rbp+58h]; this
0x1402529cc  test    eax, eax
0x1402529ce  js      loc_140252DC2
0x1402529d4  mov     rcx, [rbp+50h+var_A0]
0x1402529d8  mov     [rbp+50h+var_98], r13w
0x1402529dd  mov     rax, [rcx]
0x1402529e0  lea     rdx, [rbp+50h+var_98]
0x1402529e4  mov     rax, [rax+60h]
0x1402529e8  call    _guard_dispatch_icall
0x1402529ed  mov     rcx, [rbp+58h]; this
0x1402529f1  test    eax, eax
0x1402529f3  js      loc_140252DD7
0x1402529f9  cmp     [rbp+50h+var_98], r13w
0x1402529fe  jz      short loc_140252A22
0x140252a00  xor     edx, edx
0x140252a02  mov     rcx, [rbp+50h+var_A0]
0x140252a06  mov     rax, [rcx]
0x140252a09  mov     rax, [rax+58h]
0x140252a0d  call    _guard_dispatch_icall
0x140252a12  mov     rcx, [rbp+58h]; this
0x140252a16  test    eax, eax
0x140252a18  js      loc_140252DEC
0x140252a1e  mov     [r15+28h], r12b
0x140252a22  mov     [rbp+50h+String1], r13
0x140252a26  mov     rcx, [rbp+50h+var_A0]
0x140252a2a  mov     rax, [rcx]
0x140252a2d  mov     [rbp+50h+String1], r13
0x140252a31  lea     rdx, [rbp+50h+String1]
0x140252a35  mov     rax, [rax+40h]
0x140252a39  call    _guard_dispatch_icall
0x140252a3e  mov     rcx, [rbp+58h]; this
0x140252a42  test    eax, eax
0x140252a44  js      loc_140252E01
0x140252a4a  mov     edx, ebx
0x140252a4c  lea     rcx, [rsp+150h+var_E0]
0x140252a51  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x140252a56  nop
0x140252a57  mov     r9, r12
0x140252a5a  lea     r8, aP; "P"
0x140252a61  xor     edx, edx
0x140252a63  mov     rcx, rax
0x140252a66  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x140252a6b  xorps   xmm0, xmm0
0x140252a6e  movups  [rsp+150h+Src+8], xmm0
0x140252a73  xorps   xmm1, xmm1
0x140252a76  movdqu  [rsp+150h+var_118+8], xmm1
0x140252a7c  movups  xmm0, xmmword ptr [rax]
0x140252a7f  movups  [rsp+150h+Src+8], xmm0
0x140252a84  movups  xmm1, xmmword ptr [rax+10h]
0x140252a88  movups  [rsp+150h+var_118+8], xmm1
0x140252a8d  mov     [rax], r13w
0x140252a91  mov     [rax+10h], r13
0x140252a95  mov     r14d, 7
0x140252a9b  mov     [rax+18h], r14
0x140252a9f  or      esi, 2
0x140252aa2  mov     r8, r12
0x140252aa5  lea     rdx, aD_1; "D"
0x140252aac  lea     rcx, [rsp+150h+Src+8]; Src
0x140252ab1  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x140252ab6  xorps   xmm0, xmm0
0x140252ab9  movups  xmmword ptr [rbp+50h+String2], xmm0
0x140252abd  xorps   xmm1, xmm1
0x140252ac0  movdqu  [rbp+50h+var_40], xmm1
0x140252ac5  movups  xmm0, xmmword ptr [rax]
0x140252ac8  movups  xmmword ptr [rbp+50h+String2], xmm0
0x140252acc  movups  xmm1, xmmword ptr [rax+10h]
0x140252ad0  movups  [rbp+50h+var_40], xmm1
0x140252ad4  mov     [rax], r13w
0x140252ad8  mov     [rax+10h], r13
0x140252adc  mov     [rax+18h], r14
0x140252ae0  or      esi, 4
0x140252ae3  lea     rcx, [rsp+150h+Src+8]
0x140252ae8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252aed  nop
0x140252aee  lea     rcx, [rsp+150h+var_E0]
0x140252af3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252af8  lea     rdx, [rbp+50h+String2]
0x140252afc  cmp     qword ptr [rbp+50h+var_40+8], r14
0x140252b00  cmova   rdx, [rbp+50h+String2]; String2
0x140252b05  mov     rcx, [rbp+50h+String1]; String1
0x140252b09  call    _wcsicmp
0x140252b0e  test    eax, eax
0x140252b10  jz      short loc_140252B81
0x140252b12  mov     rbx, [rbp+50h+var_A0]
0x140252b16  mov     rax, [rbx]
0x140252b19  mov     r12, [rax+38h]
0x140252b1d  lea     rcx, [rbp+50h+String2]
0x140252b21  cmp     qword ptr [rbp+50h+var_40+8], r14
0x140252b25  cmova   rcx, [rbp+50h+String2]; psz
0x140252b2a  call    cs:__imp_SysAllocString
0x140252b30  mov     r14, rax
0x140252b33  mov     qword ptr [rsp+150h+Src], rax
0x140252b38  or      esi, 40h
0x140252b3b  mov     [rsp+150h+var_130], esi; int
0x140252b3f  mov     rcx, [rbp+58h]; this
0x140252b43  test    rax, rax
0x140252b46  jz      loc_140252E16
0x140252b4c  mov     rdx, rax
0x140252b4f  mov     rcx, rbx
0x140252b52  mov     rax, r12
0x140252b55  call    _guard_dispatch_icall
0x140252b5a  mov     rcx, [rbp+58h]; this
0x140252b5e  test    eax, eax
0x140252b60  js      loc_140252E28
0x140252b66  and     esi, 0FFFFFFBFh
0x140252b69  mov     rcx, r14; bstrString
0x140252b6c  call    cs:__imp_SysFreeString
0x140252b72  mov     r12d, 1
0x140252b78  mov     [r15+28h], r12b
0x140252b7c  lea     r14d, [r12+6]
0x140252b81  mov     [rbp+50h+bstrString], r13
0x140252b85  mov     rcx, [rbp+50h+var_A0]
0x140252b89  mov     rax, [rcx]
0x140252b8c  mov     [rbp+50h+bstrString], r13
0x140252b90  lea     rdx, [rbp+50h+bstrString]
0x140252b94  mov     rax, [rax+50h]
0x140252b98  call    _guard_dispatch_icall
0x140252b9d  mov     rcx, [rbp+58h]; this
0x140252ba1  test    eax, eax
0x140252ba3  js      loc_140252E3D
0x140252ba9  mov     edx, edi
0x140252bab  lea     rcx, [rbp+50h+var_C0]
0x140252baf  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@H@Z; std::to_wstring(int)
0x140252bb4  nop
0x140252bb5  mov     r9, r12
0x140252bb8  lea     r8, aP; "P"
0x140252bbf  xor     edx, edx
0x140252bc1  mov     rcx, rax
0x140252bc4  call    ?insert@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_KQEB_W0@Z; std::wstring::insert(unsigned __int64,wchar_t const * const,unsigned __int64)
0x140252bc9  xorps   xmm0, xmm0
0x140252bcc  movups  [rsp+150h+var_108+8], xmm0
0x140252bd1  xorps   xmm1, xmm1
0x140252bd4  movdqu  xmmword ptr [rsp+150h+var_F8+8], xmm1
0x140252bda  movups  xmm0, xmmword ptr [rax]
0x140252bdd  movups  [rsp+150h+var_108+8], xmm0
0x140252be2  movups  xmm1, xmmword ptr [rax+10h]
0x140252be6  movups  xmmword ptr [rsp+150h+var_F8+8], xmm1
0x140252beb  mov     [rax], r13w
0x140252bef  mov     [rax+10h], r13
0x140252bf3  mov     [rax+18h], r14
0x140252bf7  or      esi, 8
0x140252bfa  mov     r8, r12
0x140252bfd  lea     rdx, aD_1; "D"
0x140252c04  lea     rcx, [rsp+150h+var_108+8]; Src
0x140252c09  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x140252c0e  xorps   xmm0, xmm0
0x140252c11  movups  xmmword ptr [rbp+50h+psz], xmm0
0x140252c15  xorps   xmm1, xmm1
0x140252c18  movdqu  [rbp+50h+var_60], xmm1
0x140252c1d  movups  xmm0, xmmword ptr [rax]
0x140252c20  movups  xmmword ptr [rbp+50h+psz], xmm0
0x140252c24  movups  xmm1, xmmword ptr [rax+10h]
0x140252c28  movups  [rbp+50h+var_60], xmm1
0x140252c2c  mov     [rax], r13w
0x140252c30  mov     [rax+10h], r13
0x140252c34  mov     [rax+18h], r14
0x140252c38  or      esi, 10h
0x140252c3b  lea     rcx, [rsp+150h+var_108+8]
0x140252c40  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252c45  nop
0x140252c46  lea     rcx, [rbp+50h+var_C0]
0x140252c4a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252c4f  lea     rdx, [rbp+50h+psz]
0x140252c53  cmp     qword ptr [rbp+50h+var_60+8], r14
0x140252c57  cmova   rdx, [rbp+50h+psz]; String2
0x140252c5c  mov     rcx, [rbp+50h+bstrString]; String1
0x140252c60  call    _wcsicmp
0x140252c65  test    eax, eax
0x140252c67  jz      short loc_140252CCB
0x140252c69  mov     rbx, [rbp+50h+var_A0]
0x140252c6d  mov     rax, [rbx]
0x140252c70  mov     r14, [rax+48h]
0x140252c74  lea     rcx, [rbp+50h+psz]
0x140252c78  cmp     qword ptr [rbp+50h+var_60+8], 7
0x140252c7d  cmova   rcx, [rbp+50h+psz]; psz
0x140252c82  call    cs:__imp_SysAllocString
0x140252c88  mov     rdi, rax
0x140252c8b  mov     qword ptr [rsp+150h+Src], rax
0x140252c90  or      esi, 20h
0x140252c93  mov     [rsp+150h+var_130], esi; int
0x140252c97  mov     rcx, [rbp+58h]; this
0x140252c9b  test    rax, rax
0x140252c9e  jz      loc_140252E52
0x140252ca4  mov     rdx, rax
0x140252ca7  mov     rcx, rbx
0x140252caa  mov     rax, r14
0x140252cad  call    _guard_dispatch_icall
0x140252cb2  mov     rcx, [rbp+58h]; this
0x140252cb6  test    eax, eax
0x140252cb8  js      loc_140252D6E
0x140252cbe  mov     rcx, rdi; bstrString
0x140252cc1  call    cs:__imp_SysFreeString
0x140252cc7  mov     [r15+28h], r12b
0x140252ccb  lea     rcx, [rbp+50h+psz]
0x140252ccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252cd4  nop
0x140252cd5  mov     rcx, [rbp+50h+bstrString]; bstrString
0x140252cd9  test    rcx, rcx
0x140252cdc  jz      short loc_140252CE5
0x140252cde  call    cs:__imp_SysFreeString
0x140252ce4  nop
0x140252ce5  lea     rcx, [rbp+50h+String2]
0x140252ce9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140252cee  nop
0x140252cef  mov     rcx, [rbp+50h+String1]; bstrString
0x140252cf3  test    rcx, rcx
0x140252cf6  jz      short loc_140252CFF
0x140252cf8  call    cs:__imp_SysFreeString
0x140252cfe  nop
0x140252cff  mov     rcx, [rbp+50h+var_A0]
0x140252d03  test    rcx, rcx
0x140252d06  jz      short loc_140252D15
0x140252d08  mov     rax, [rcx]
0x140252d0b  mov     rax, [rax+10h]
0x140252d0f  call    _guard_dispatch_icall
0x140252d14  nop
0x140252d15  mov     rcx, [rbp+50h+var_80]
0x140252d19  test    rcx, rcx
0x140252d1c  jz      short loc_140252D2B
0x140252d1e  mov     rax, [rcx]
0x140252d21  mov     rax, [rax+10h]
0x140252d25  call    _guard_dispatch_icall
0x140252d2a  nop
0x140252d2b  mov     rcx, [rbp+50h+var_78]
0x140252d2f  test    rcx, rcx
0x140252d32  jz      short loc_140252D41
0x140252d34  mov     rax, [rcx]
0x140252d37  mov     rax, [rax+10h]
0x140252d3b  call    _guard_dispatch_icall
0x140252d40  nop
0x140252d41  mov     rcx, [rbp+50h+var_30]
0x140252d45  xor     rcx, rsp; StackCookie
0x140252d48  call    __security_check_cookie
0x140252d4d  lea     r11, [rsp+150h+var_20]
0x140252d55  mov     rbx, [r11+38h]
0x140252d59  mov     rsi, [r11+40h]
0x140252d5d  mov     rdi, [r11+48h]
0x140252d61  mov     rsp, r11
0x140252d64  pop     r15
0x140252d66  pop     r14
  ... truncated ...
```
