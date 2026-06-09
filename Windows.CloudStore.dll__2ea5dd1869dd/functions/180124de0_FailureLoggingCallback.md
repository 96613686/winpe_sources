# FailureLoggingCallback

- ea: `0x180124de0`
- end: `0x180124f48`
- name: `FailureLoggingCallback`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180054714`
- `0x18005b3cc`
- `0x180087ae0`
- `0x1800a03bc`
- `0x1800a12d4`
- `0x1800e0c20`
- `0x180124de0`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180124f36`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180124f36`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180124e21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180124e49`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180124e21`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180124e49`

## pseudocode

```c
void __fastcall FailureLoggingCallback(__int64 a1)
{
  char IsEnabled; // al
  const WCHAR *v3; // rcx
  int v4; // edx
  const WCHAR *v5; // r8
  unsigned int ProcessExeNameForLogging; // edi
  __int64 v7; // r8
  __int64 v8; // rdx
  int v9; // edx
  int v10; // ecx
  unsigned int v11; // eax
  unsigned int v12; // [rsp+58h] [rbp+10h] BYREF

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl'::`2'::impl);
  v3 = *(const WCHAR **)(a1 + 24);
  if ( !v3
    || (!IsEnabled ? (v4 = 10, v5 = L"**!!##!!**") : (v4 = 15, v5 = L"**!!##!!**NoLog"),
        CompareStringOrdinal(v3, v4, v5, v4, 0) != 2
     && CompareStringOrdinal(*(LPCWCH *)(a1 + 24), -1, L"TelemetryOnly", -1, 0) != 2) )
  {
    ProcessExeNameForLogging = (unsigned int)GetProcessExeNameForLogging();
    LOBYTE(v7) = 3;
    LOBYTE(v8) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::GetImpl'::`2'::impl,
      v8,
      v7);
    if ( *(_QWORD *)(a1 + 24) )
    {
      if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
        McTemplateU0zqqsqz_EventWriteTransfer(
          v10,
          v9,
          ProcessExeNameForLogging,
          *(_DWORD *)a1,
          *(_DWORD *)(a1 + 8),
          *(_QWORD *)(a1 + 56),
          *(_DWORD *)(a1 + 64),
          *(_QWORD *)(a1 + 24));
    }
    else if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
    {
      McTemplateU0zqqsq_EventWriteTransfer(
        v10,
        v9,
        ProcessExeNameForLogging,
        *(_DWORD *)a1,
        *(_DWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 56),
        *(_DWORD *)(a1 + 64));
    }
    LOBYTE(v11) = g_debugFlags;
    if ( g_debugFlags == 0x8000 )
    {
      v12 = 0;
      if ( (int)SHRegGetDWORD(
                  HKEY_LOCAL_MACHINE,
                  L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\CloudStore",
                  L"DebugFlags",
                  &v12) < 0 )
        v11 = 0;
      else
        v11 = v12 & 0xFFFF7FFF;
      g_debugFlags = v11;
    }
    if ( (v11 & 1) != 0 )
      DebugBreak();
  }
}

```

## disassembly

```asm
0x180124de0  mov     [rsp+arg_0], rbx
0x180124de5  push    rdi
0x180124de6  sub     rsp, 40h
0x180124dea  mov     rbx, rcx
0x180124ded  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DirectCloudSync@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync> `wil::Feature<__WilFeatureTraits_Feature_DirectCloudSync>::GetImpl(void)'::`2'::impl
0x180124df4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DirectCloudSync@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DirectCloudSync>::__private_IsEnabled(void)
0x180124df9  mov     rcx, [rbx+18h]; lpString1
0x180124dfd  test    rcx, rcx
0x180124e00  jz      short loc_180124E58
0x180124e02  mov     [rsp+48h+bIgnoreCase], 0; bIgnoreCase
0x180124e0a  test    al, al
0x180124e0c  jz      loc_180124EAC
0x180124e12  mov     edx, 0Fh; cchCount1
0x180124e17  lea     r8, aNolog_1; "**!!##!!**NoLog"
0x180124e1e  mov     r9d, edx; cchCount2
0x180124e21  call    cs:__imp_CompareStringOrdinal
0x180124e27  cmp     eax, 2
0x180124e2a  jz      loc_180124F3D
0x180124e30  or      edx, 0FFFFFFFFh; cchCount1
0x180124e33  mov     [rsp+48h+bIgnoreCase], 0; bIgnoreCase
0x180124e3b  mov     r9d, edx; cchCount2
0x180124e3e  lea     r8, aTelemetryonly; "TelemetryOnly"
0x180124e45  mov     rcx, [rbx+18h]; lpString1
0x180124e49  call    cs:__imp_CompareStringOrdinal
0x180124e4f  cmp     eax, 2
0x180124e52  jz      loc_180124F3D
0x180124e58  call    ?GetProcessExeNameForLogging@@YAPEBGXZ; GetProcessExeNameForLogging(void)
0x180124e5d  mov     rdi, rax
0x180124e60  mov     r8b, 3
0x180124e63  mov     dl, 1
0x180124e65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore> `wil::Feature<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::GetImpl(void)'::`2'::impl
0x180124e6c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudDataStoreDirectRestore@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudDataStoreDirectRestore>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180124e71  mov     rax, [rbx+18h]
0x180124e75  test    rax, rax
0x180124e78  jz      short loc_180124EBD
0x180124e7a  test    cs:Microsoft_Windows_CloudStoreEnableBits, 1
0x180124e81  jz      short loc_180124EE8
0x180124e83  mov     [rsp+48h+var_10], rax
0x180124e88  mov     eax, [rbx+40h]
0x180124e8b  mov     [rsp+48h+var_18], eax
0x180124e8f  mov     rax, [rbx+38h]
0x180124e93  mov     [rsp+48h+var_20], rax
0x180124e98  mov     eax, [rbx+8]
0x180124e9b  mov     [rsp+48h+bIgnoreCase], eax
0x180124e9f  mov     r9d, [rbx]
0x180124ea2  mov     r8, rdi
0x180124ea5  call    McTemplateU0zqqsqz_EventWriteTransfer
0x180124eaa  jmp     short loc_180124EE8
0x180124eac  mov     edx, 0Ah
0x180124eb1  lea     r8, asc_180233BF8; "**!!##!!**"
0x180124eb8  jmp     loc_180124E1E
0x180124ebd  test    cs:Microsoft_Windows_CloudStoreEnableBits, 1
0x180124ec4  jz      short loc_180124EE8
0x180124ec6  mov     eax, [rbx+40h]
0x180124ec9  mov     [rsp+48h+var_18], eax
0x180124ecd  mov     rax, [rbx+38h]
0x180124ed1  mov     [rsp+48h+var_20], rax
0x180124ed6  mov     eax, [rbx+8]
0x180124ed9  mov     [rsp+48h+bIgnoreCase], eax
0x180124edd  mov     r9d, [rbx]
0x180124ee0  mov     r8, rdi
0x180124ee3  call    McTemplateU0zqqsq_EventWriteTransfer
0x180124ee8  mov     eax, cs:?g_debugFlags@@3W4CloudStoreGlobalDebugFlags@@A; CloudStoreGlobalDebugFlags g_debugFlags
0x180124eee  cmp     eax, 8000h
0x180124ef3  jnz     short loc_180124F32
0x180124ef5  mov     [rsp+48h+arg_8], 0
0x180124efd  lea     r9, [rsp+48h+arg_8]; unsigned int *
0x180124f02  lea     r8, aDebugflags; "DebugFlags"
0x180124f09  lea     rdx, pszPathIn; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180124f10  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180124f17  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180124f1c  test    eax, eax
0x180124f1e  js      short loc_180124F2A
0x180124f20  mov     eax, [rsp+48h+arg_8]
0x180124f24  btr     eax, 0Fh
0x180124f28  jmp     short loc_180124F2C
0x180124f2a  xor     eax, eax
0x180124f2c  mov     cs:?g_debugFlags@@3W4CloudStoreGlobalDebugFlags@@A, eax; CloudStoreGlobalDebugFlags g_debugFlags
0x180124f32  test    al, 1
0x180124f34  jz      short loc_180124F3D
0x180124f36  call    cs:__imp_DebugBreak
0x180124f3c  nop
0x180124f3d  mov     rbx, [rsp+48h+arg_0]
0x180124f42  add     rsp, 40h
0x180124f46  pop     rdi
0x180124f47  retn
```
