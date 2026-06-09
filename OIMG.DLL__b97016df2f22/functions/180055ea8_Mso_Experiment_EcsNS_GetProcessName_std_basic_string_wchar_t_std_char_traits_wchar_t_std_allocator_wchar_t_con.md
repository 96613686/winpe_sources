# Mso::Experiment::EcsNS::GetProcessName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180055ea8`
- end: `0x1800561f1`
- name: `?GetProcessName@EcsNS@Experiment@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV45@00@Z`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800565ac`

## callees

- `0x1800124f0`
- `0x180012ccc`
- `0x180041f60`
- `0x180041fb8`
- `0x180055ea8`
- `0x180059fc0`
- `0x18056dc2e`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180056182`
- `KERNEL32!GetLastError` at `0x1800561a7`
- `KERNEL32!GetLastError` at `0x1800561cc`
- `KERNEL32!GetLastError` at `0x180056182`
- `KERNEL32!GetLastError` at `0x1800561a7`
- `KERNEL32!GetLastError` at `0x1800561cc`
- `KERNEL32!CompareStringEx` at `0x180055f49`
- `KERNEL32!CompareStringEx` at `0x180055f88`
- `KERNEL32!CompareStringEx` at `0x18005600c`
- `KERNEL32!CompareStringEx` at `0x18005604b`
- `KERNEL32!CompareStringEx` at `0x1800560cb`
- `KERNEL32!CompareStringEx` at `0x1800560fd`
- `KERNEL32!CompareStringEx` at `0x180055f49`
- `KERNEL32!CompareStringEx` at `0x180055f88`
- `KERNEL32!CompareStringEx` at `0x18005600c`
- `KERNEL32!CompareStringEx` at `0x18005604b`
- `KERNEL32!CompareStringEx` at `0x1800560cb`
- `KERNEL32!CompareStringEx` at `0x1800560fd`

## pseudocode

```c
__int64 __fastcall Mso::Experiment::EcsNS::GetProcessName(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  const WCHAR *v8; // rdi
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rbp
  int v11; // eax
  __int64 v12; // rcx
  unsigned __int64 v13; // rdi
  int v14; // eax
  const WCHAR *v15; // rdi
  int v16; // eax
  __int64 *v17; // rax
  __int64 *v18; // rdx
  DWORD LastError; // eax
  __int64 v21; // rdx
  DWORD v22; // eax
  __int64 v23; // rdx
  DWORD v24; // eax
  __int64 v25; // rdx
  _BYTE pExceptionObject[912]; // [rsp+50h] [rbp-3B8h] BYREF

  v8 = (const WCHAR *)a2;
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v8 = *(const WCHAR **)a2;
  if ( !v8 || !*v8 )
    goto LABEL_33;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( v8[v10] );
  if ( v10 > 0x7FFFFFFF )
    goto LABEL_36;
  v11 = CompareStringEx(&psz, 1u, v8, v10, L"sdxhelper.exe", 13, 0, 0, 0);
  if ( !v11 )
  {
    v11 = CompareStringEx(L"en-US", 1u, v8, v10, L"sdxhelper.exe", 13, 0, 0, 0);
    if ( !v11 )
    {
      LastError = GetLastError();
      OException::OException(pExceptionObject, v21, LastError);
      throw (OException *)pExceptionObject;
    }
  }
  if ( v11 != 2 )
    goto LABEL_33;
  if ( (unsigned __int64)a4[3] > 7 )
    a4 = (__int64 *)*a4;
  if ( !a4 || !*(_WORD *)a4 )
    goto LABEL_31;
  v13 = -1;
  do
    ++v13;
  while ( *((_WORD *)a4 + v13) );
  if ( v13 > 0x7FFFFFFF )
    goto LABEL_36;
  v14 = CompareStringEx(&psz, 1u, (LPCWCH)a4, v13, L"debug", 5, 0, 0, 0);
  if ( !v14 )
  {
    v14 = CompareStringEx(L"en-US", 1u, (LPCWCH)a4, v13, L"debug", 5, 0, 0, 0);
    if ( !v14 )
    {
      v22 = GetLastError();
      OException::OException(pExceptionObject, v23, v22);
      throw (OException *)pExceptionObject;
    }
  }
  if ( v14 != 2 )
    goto LABEL_31;
  v15 = (const WCHAR *)a3;
  if ( *(_QWORD *)(a3 + 24) > 7u )
    v15 = *(const WCHAR **)a3;
  if ( !v15 || !*v15 )
  {
LABEL_31:
    v17 = (__int64 *)Mso::Collections::StaticSizeMap<std::wstring,std::wstring,5,Mso::Experiment::EcsNS::Private::sdxhelperImpersonatingAppToProcessNamesMapComparator>::find(
                       v12,
                       a3);
    if ( v17 != &Mso::Experiment::vexperimentLiblet )
    {
      v18 = v17 + 4;
LABEL_34:
      std::wstring::wstring(a1, v18);
      return a1;
    }
LABEL_33:
    v18 = (__int64 *)a2;
    goto LABEL_34;
  }
  do
    ++v9;
  while ( v15[v9] );
  if ( v9 > 0x7FFFFFFF )
LABEL_36:
    OcfxSafeIntExceptionPolicy::SafeIntOnOverflow();
  v16 = CompareStringEx(&psz, 1u, v15, v9, L"Word", 4, 0, 0, 0);
  if ( !v16 )
  {
    v16 = CompareStringEx(L"en-US", 1u, v15, v9, L"Word", 4, 0, 0, 0);
    if ( !v16 )
    {
      v24 = GetLastError();
      OException::OException(pExceptionObject, v25, v24);
      throw (OException *)pExceptionObject;
    }
  }
  if ( v16 != 2 )
    goto LABEL_31;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  std::wstring::_Construct<1,wchar_t *>(a1, L"winwordd.exe", 12);
  return a1;
}

```

## disassembly

```asm
0x180055ea8  mov     [rsp+arg_0], rbx
0x180055ead  mov     [rsp+arg_8], rbp
0x180055eb2  mov     [rsp+arg_10], rsi
0x180055eb7  push    rdi
0x180055eb8  push    r12
0x180055eba  push    r13
0x180055ebc  push    r14
0x180055ebe  push    r15
0x180055ec0  sub     rsp, 3E0h
0x180055ec7  mov     rsi, r9
0x180055eca  mov     r12, r8
0x180055ecd  mov     r15, rdx
0x180055ed0  mov     rbx, rcx
0x180055ed3  mov     rdi, rdx
0x180055ed6  cmp     qword ptr [rdx+18h], 7
0x180055edb  jbe     short loc_180055EE0
0x180055edd  mov     rdi, [rdx]
0x180055ee0  xor     r13d, r13d
0x180055ee3  test    rdi, rdi
0x180055ee6  jz      loc_18005614D
0x180055eec  cmp     r13w, [rdi]
0x180055ef0  jz      loc_18005614D
0x180055ef6  or      r14, 0FFFFFFFFFFFFFFFFh
0x180055efa  mov     rbp, r14
0x180055efd  inc     rbp
0x180055f00  cmp     [rdi+rbp*2], r13w
0x180055f05  jnz     short loc_180055EFD
0x180055f07  cmp     rbp, 7FFFFFFFh
0x180055f0e  ja      loc_18005617C
0x180055f14  mov     [rsp+408h+lParam], r13; lParam
0x180055f19  mov     [rsp+408h+lpReserved], r13; lpReserved
0x180055f1e  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x180055f23  mov     [rsp+408h+cchCount2], 0Dh; cchCount2
0x180055f2b  lea     rax, aSdxhelperExe; "sdxhelper.exe"
0x180055f32  mov     [rsp+408h+lpString2], rax; lpString2
0x180055f37  mov     r9d, ebp; cchCount1
0x180055f3a  mov     r8, rdi; lpString1
0x180055f3d  mov     edx, 1; dwCmpFlags
0x180055f42  lea     rcx, psz; lpLocaleName
0x180055f49  call    cs:__imp_CompareStringEx
0x180055f4f  test    eax, eax
0x180055f51  jnz     short loc_180055F96
0x180055f53  mov     [rsp+408h+lParam], r13; lParam
0x180055f58  mov     [rsp+408h+lpReserved], r13; lpReserved
0x180055f5d  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x180055f62  mov     [rsp+408h+cchCount2], 0Dh; cchCount2
0x180055f6a  lea     rax, aSdxhelperExe; "sdxhelper.exe"
0x180055f71  mov     [rsp+408h+lpString2], rax; lpString2
0x180055f76  mov     r9d, ebp; cchCount1
0x180055f79  mov     r8, rdi; lpString1
0x180055f7c  mov     edx, 1; dwCmpFlags
0x180055f81  lea     rcx, aEnUs; "en-US"
0x180055f88  call    cs:__imp_CompareStringEx
0x180055f8e  test    eax, eax
0x180055f90  jz      loc_180056182
0x180055f96  add     eax, 0FFFFFFFEh
0x180055f99  jnz     loc_18005614D
0x180055f9f  cmp     qword ptr [rsi+18h], 7
0x180055fa4  jbe     short loc_180055FA9
0x180055fa6  mov     rsi, [rsi]
0x180055fa9  test    rsi, rsi
0x180055fac  jz      loc_180056133
0x180055fb2  cmp     r13w, [rsi]
0x180055fb6  jz      loc_180056133
0x180055fbc  mov     rdi, r14
0x180055fbf  inc     rdi
0x180055fc2  cmp     [rsi+rdi*2], r13w
0x180055fc7  jnz     short loc_180055FBF
0x180055fc9  mov     ebp, 7FFFFFFFh
0x180055fce  cmp     rdi, rbp
0x180055fd1  ja      loc_18005617C
0x180055fd7  mov     [rsp+408h+lParam], r13; lParam
0x180055fdc  mov     [rsp+408h+lpReserved], r13; lpReserved
0x180055fe1  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x180055fe6  mov     [rsp+408h+cchCount2], 5; cchCount2
0x180055fee  lea     rax, aDebug_0; "debug"
0x180055ff5  mov     [rsp+408h+lpString2], rax; lpString2
0x180055ffa  mov     r9d, edi; cchCount1
0x180055ffd  mov     r8, rsi; lpString1
0x180056000  mov     edx, 1; dwCmpFlags
0x180056005  lea     rcx, psz; lpLocaleName
0x18005600c  call    cs:__imp_CompareStringEx
0x180056012  test    eax, eax
0x180056014  jnz     short loc_180056059
0x180056016  mov     [rsp+408h+lParam], r13; lParam
0x18005601b  mov     [rsp+408h+lpReserved], r13; lpReserved
0x180056020  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x180056025  mov     [rsp+408h+cchCount2], 5; cchCount2
0x18005602d  lea     rax, aDebug_0; "debug"
0x180056034  mov     [rsp+408h+lpString2], rax; lpString2
0x180056039  mov     r9d, edi; cchCount1
0x18005603c  mov     r8, rsi; lpString1
0x18005603f  mov     edx, 1; dwCmpFlags
0x180056044  lea     rcx, aEnUs; "en-US"
0x18005604b  call    cs:__imp_CompareStringEx
0x180056051  test    eax, eax
0x180056053  jz      loc_1800561A7
0x180056059  add     eax, 0FFFFFFFEh
0x18005605c  jnz     loc_180056133
0x180056062  mov     rdi, r12
0x180056065  cmp     qword ptr [r12+18h], 7
0x18005606b  jbe     short loc_180056071
0x18005606d  mov     rdi, [r12]
0x180056071  test    rdi, rdi
0x180056074  jz      loc_180056133
0x18005607a  cmp     r13w, [rdi]
0x18005607e  jz      loc_180056133
0x180056084  inc     r14
0x180056087  cmp     [rdi+r14*2], r13w
0x18005608c  jnz     short loc_180056084
0x18005608e  cmp     r14, rbp
0x180056091  ja      loc_18005617C
0x180056097  mov     [rsp+408h+lParam], r13; lParam
0x18005609c  mov     [rsp+408h+lpReserved], r13; lpReserved
0x1800560a1  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x1800560a6  mov     esi, 4
0x1800560ab  mov     [rsp+408h+cchCount2], esi; cchCount2
0x1800560af  lea     rbp, aWord; "Word"
0x1800560b6  mov     [rsp+408h+lpString2], rbp; lpString2
0x1800560bb  mov     r9d, r14d; cchCount1
0x1800560be  mov     r8, rdi; lpString1
0x1800560c1  lea     edx, [rsi-3]; dwCmpFlags
0x1800560c4  lea     rcx, psz; lpLocaleName
0x1800560cb  call    cs:__imp_CompareStringEx
0x1800560d1  test    eax, eax
0x1800560d3  jnz     short loc_18005610B
0x1800560d5  mov     [rsp+408h+lParam], r13; lParam
0x1800560da  mov     [rsp+408h+lpReserved], r13; lpReserved
0x1800560df  mov     [rsp+408h+lpVersionInformation], r13; lpVersionInformation
0x1800560e4  mov     [rsp+408h+cchCount2], esi; cchCount2
0x1800560e8  mov     [rsp+408h+lpString2], rbp; lpString2
0x1800560ed  mov     r9d, r14d; cchCount1
0x1800560f0  mov     r8, rdi; lpString1
0x1800560f3  lea     edx, [rsi-3]; dwCmpFlags
0x1800560f6  lea     rcx, aEnUs; "en-US"
0x1800560fd  call    cs:__imp_CompareStringEx
0x180056103  test    eax, eax
0x180056105  jz      loc_1800561CC
0x18005610b  add     eax, 0FFFFFFFEh
0x18005610e  jnz     short loc_180056133
0x180056110  xorps   xmm0, xmm0
0x180056113  movups  xmmword ptr [rbx], xmm0
0x180056116  mov     [rbx+10h], r13
0x18005611a  mov     [rbx+18h], r13
0x18005611e  lea     r8d, [rax+0Ch]
0x180056122  lea     rdx, aWinworddExe; "winwordd.exe"
0x180056129  mov     rcx, rbx
0x18005612c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180056131  jmp     short loc_180056158
0x180056133  mov     rdx, r12
0x180056136  call    ?find@?$StaticSizeMap@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@$04UsdxhelperImpersonatingAppToProcessNamesMapComparator@Private@EcsNS@Experiment@Mso@@@Collections@Mso@@QEBAPEBU?$KeyValue@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Mso::Collections::StaticSizeMap<std::wstring,std::wstring,5,Mso::Experiment::EcsNS::Private::sdxhelperImpersonatingAppToProcessNamesMapComparator>::find(std::wstring const &)
0x18005613b  lea     rcx, ?vexperimentLiblet@Experiment@Mso@@3VExperimentLiblet@12@A; Mso::Experiment::ExperimentLiblet Mso::Experiment::vexperimentLiblet
0x180056142  cmp     rax, rcx
0x180056145  jz      short loc_18005614D
0x180056147  lea     rdx, [rax+20h]
0x18005614b  jmp     short loc_180056150
0x18005614d  mov     rdx, r15
0x180056150  mov     rcx, rbx
0x180056153  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180056158  mov     rax, rbx
0x18005615b  lea     r11, [rsp+408h+var_28]
0x180056163  mov     rbx, [r11+30h]
0x180056167  mov     rbp, [r11+38h]
0x18005616b  mov     rsi, [r11+40h]
0x18005616f  mov     rsp, r11
0x180056172  pop     r15
0x180056174  pop     r14
0x180056176  pop     r13
0x180056178  pop     r12
0x18005617a  pop     rdi
0x18005617b  retn
0x18005617c  call    ?SafeIntOnOverflow@OcfxSafeIntExceptionPolicy@@SAXXZ; OcfxSafeIntExceptionPolicy::SafeIntOnOverflow(void)
0x180056182  call    cs:__imp_GetLastError
0x180056188  mov     r8d, eax
0x18005618b  lea     rcx, [rsp+408h+pExceptionObject]
0x180056190  call    ??0OException@@QEAA@W4exceptionType@et@@I@Z; OException::OException(et::exceptionType,uint)
0x180056195  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18005619c  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x1800561a1  call    _CxxThrowException_0
0x1800561a7  call    cs:__imp_GetLastError
0x1800561ad  mov     r8d, eax
0x1800561b0  lea     rcx, [rsp+408h+pExceptionObject]
0x1800561b5  call    ??0OException@@QEAA@W4exceptionType@et@@I@Z; OException::OException(et::exceptionType,uint)
0x1800561ba  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800561c1  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x1800561c6  call    _CxxThrowException_0
0x1800561cc  call    cs:__imp_GetLastError
0x1800561d2  mov     r8d, eax
0x1800561d5  lea     rcx, [rsp+408h+pExceptionObject]
0x1800561da  call    ??0OException@@QEAA@W4exceptionType@et@@I@Z; OException::OException(et::exceptionType,uint)
0x1800561df  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800561e6  lea     rcx, [rsp+408h+pExceptionObject]; pExceptionObject
0x1800561eb  call    _CxxThrowException_0
```
