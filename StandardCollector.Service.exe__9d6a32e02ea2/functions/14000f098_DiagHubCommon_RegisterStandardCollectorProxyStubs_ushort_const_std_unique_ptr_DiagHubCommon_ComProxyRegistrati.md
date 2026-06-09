# DiagHubCommon::RegisterStandardCollectorProxyStubs(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration,std::default_delete<DiagHubCommon::ComProxyRegistration>> &)

- ea: `0x14000f098`
- end: `0x14000f1ce`
- name: `?RegisterStandardCollectorProxyStubs@DiagHubCommon@@YAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140001388`
- `0x140005b70`
- `0x14000f9d4`
- `0x14000fcfc`

## callees

- `0x140002600`
- `0x140002b4c`
- `0x140002e74`
- `0x14000edcc`
- `0x14000f098`
- `0x14000f1d0`
- `0x140014c70`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x14000f0ff`
- `KERNEL32!GetFileAttributesW` at `0x14000f130`
- `KERNEL32!GetFileAttributesW` at `0x14000f168`
- `KERNEL32!GetFileAttributesW` at `0x14000f0ff`
- `KERNEL32!GetFileAttributesW` at `0x14000f130`
- `KERNEL32!GetFileAttributesW` at `0x14000f168`

## string_xrefs

- `0x14000f0e6`: `%s\DiagnosticsHub.StandardCollector.Proxy.dll`
- `0x14000f117`: `%s\amd64\DiagnosticsHub.StandardCollector.Proxy.dll`
- `0x14000f14f`: `%s\%s\amd64\DiagnosticsHub.StandardCollector.Proxy.dll`

## pseudocode

```c
__int64 __fastcall DiagHubCommon::RegisterStandardCollectorProxyStubs(__int64 a1)
{
  struct ATL::IAtlStringMgr *Instance; // rax
  unsigned __int16 *v4; // rbx
  int v5; // edi
  LPCWSTR lpFileName[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( !a1 )
    return 2147500035LL;
  Instance = ATL::CAtlStringMgr::GetInstance();
  if ( !Instance )
    ATL::AtlThrowImpl(-2147467259);
  lpFileName[0] = (LPCWSTR)((*(__int64 (__fastcall **)(struct ATL::IAtlStringMgr *))(*(_QWORD *)Instance + 24LL))(Instance)
                          + 24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    lpFileName,
    L"%s\\DiagnosticsHub.StandardCollector.Proxy.dll",
    a1);
  v4 = (unsigned __int16 *)lpFileName[0];
  if ( GetFileAttributesW(lpFileName[0]) == -1
    && (ATL::CSimpleStringT<unsigned short,0>::Empty(lpFileName),
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          lpFileName,
          L"%s\\amd64\\DiagnosticsHub.StandardCollector.Proxy.dll",
          a1),
        v4 = (unsigned __int16 *)lpFileName[0],
        GetFileAttributesW(lpFileName[0]) == -1)
    && (ATL::CSimpleStringT<unsigned short,0>::Empty(lpFileName),
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
          lpFileName,
          L"%s\\%s\\amd64\\DiagnosticsHub.StandardCollector.Proxy.dll",
          a1,
          L"\\Team Tools\\DiagnosticsHub\\Collector"),
        v4 = (unsigned __int16 *)lpFileName[0],
        GetFileAttributesW(lpFileName[0]) == -1) )
  {
    v5 = -2147024809;
  }
  else
  {
    v5 = ManualInterfaceRegistration::CreateInstance(v4);
    if ( v5 >= 0 )
      v5 = 0;
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000f098  mov     [rsp+arg_10], rbx
0x14000f09d  mov     [rsp+arg_18], rsi
0x14000f0a2  push    rdi
0x14000f0a3  sub     rsp, 30h
0x14000f0a7  mov     rsi, rdx
0x14000f0aa  mov     rdi, rcx
0x14000f0ad  test    rcx, rcx
0x14000f0b0  jnz     short loc_14000F0BC
0x14000f0b2  mov     eax, 80004003h
0x14000f0b7  jmp     loc_14000F1B3
0x14000f0bc  call    ?GetInstance@CAtlStringMgr@ATL@@SAPEAUIAtlStringMgr@2@XZ; ATL::CAtlStringMgr::GetInstance(void)
0x14000f0c1  mov     rcx, rax
0x14000f0c4  test    rax, rax
0x14000f0c7  jz      loc_14000F1C3
0x14000f0cd  mov     rax, [rax]
0x14000f0d0  mov     rax, [rax+18h]
0x14000f0d4  call    cs:__guard_dispatch_icall_fptr
0x14000f0da  add     rax, 18h
0x14000f0de  mov     [rsp+38h+lpFileName], rax
0x14000f0e3  mov     r8, rdi
0x14000f0e6  lea     rdx, aSDiagnosticshu; "%s\\DiagnosticsHub.StandardCollector.Pr"...
0x14000f0ed  lea     rcx, [rsp+38h+lpFileName]
0x14000f0f2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000f0f7  mov     rbx, [rsp+38h+lpFileName]
0x14000f0fc  mov     rcx, rbx; lpFileName
0x14000f0ff  call    cs:__imp_GetFileAttributesW
0x14000f105  cmp     eax, 0FFFFFFFFh
0x14000f108  jnz     short loc_14000F17A
0x14000f10a  lea     rcx, [rsp+38h+lpFileName]
0x14000f10f  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000f114  mov     r8, rdi
0x14000f117  lea     rdx, aSAmd64Diagnost; "%s\\amd64\\DiagnosticsHub.StandardColle"...
0x14000f11e  lea     rcx, [rsp+38h+lpFileName]
0x14000f123  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000f128  mov     rbx, [rsp+38h+lpFileName]
0x14000f12d  mov     rcx, rbx; lpFileName
0x14000f130  call    cs:__imp_GetFileAttributesW
0x14000f136  cmp     eax, 0FFFFFFFFh
0x14000f139  jnz     short loc_14000F17A
0x14000f13b  lea     rcx, [rsp+38h+lpFileName]
0x14000f140  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14000f145  lea     r9, aTeamToolsDiagn; "\\Team Tools\\DiagnosticsHub\\Collector"
0x14000f14c  mov     r8, rdi
0x14000f14f  lea     rdx, aSSAmd64Diagnos; "%s\\%s\\amd64\\DiagnosticsHub.StandardC"...
0x14000f156  lea     rcx, [rsp+38h+lpFileName]
0x14000f15b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x14000f160  mov     rbx, [rsp+38h+lpFileName]
0x14000f165  mov     rcx, rbx; lpFileName
0x14000f168  call    cs:__imp_GetFileAttributesW
0x14000f16e  cmp     eax, 0FFFFFFFFh
0x14000f171  jnz     short loc_14000F17A
0x14000f173  mov     edi, 80070057h
0x14000f178  jmp     short loc_14000F18D
0x14000f17a  mov     rdx, rsi
0x14000f17d  mov     rcx, rbx; unsigned __int16 *
0x14000f180  call    ?CreateInstance@ManualInterfaceRegistration@@SAJPEBGAEAV?$unique_ptr@VComProxyRegistration@DiagHubCommon@@U?$default_delete@VComProxyRegistration@DiagHubCommon@@@std@@@std@@@Z; ManualInterfaceRegistration::CreateInstance(ushort const *,std::unique_ptr<DiagHubCommon::ComProxyRegistration> &)
0x14000f185  mov     edi, eax
0x14000f187  test    eax, eax
0x14000f189  js      short loc_14000F18D
0x14000f18b  xor     edi, edi
0x14000f18d  lea     rdx, [rbx-18h]
0x14000f191  or      ecx, 0FFFFFFFFh
0x14000f194  lock xadd [rdx+10h], ecx
0x14000f199  sub     ecx, 1
0x14000f19c  jg      short loc_14000F1B1
0x14000f19e  lfence
0x14000f1a1  mov     rcx, [rdx]
0x14000f1a4  mov     r8, [rcx]
0x14000f1a7  mov     rax, [r8+8]
0x14000f1ab  call    cs:__guard_dispatch_icall_fptr
0x14000f1b1  mov     eax, edi
0x14000f1b3  mov     rbx, [rsp+38h+arg_10]
0x14000f1b8  mov     rsi, [rsp+38h+arg_18]
0x14000f1bd  add     rsp, 30h
0x14000f1c1  pop     rdi
0x14000f1c2  retn
0x14000f1c3  mov     ecx, 80004005h; int
0x14000f1c8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
