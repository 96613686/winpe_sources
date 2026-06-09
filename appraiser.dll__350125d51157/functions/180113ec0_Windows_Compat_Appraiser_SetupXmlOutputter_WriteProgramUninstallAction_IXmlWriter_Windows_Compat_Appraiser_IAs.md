# Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction(IXmlWriter *,Windows::Compat::Appraiser::IAsset *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)

- ea: `0x180113ec0`
- end: `0x180114424`
- name: `?WriteProgramUninstallAction@SetupXmlOutputter@Appraiser@Compat@Windows@@AEAAJPEAUIXmlWriter@@PEAVIAsset@234@PEBGPEAVIPropertyListEnumerator@234@@Z`
- size: `1380`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::SetupXmlOutputter *this, struct IXmlWriter *, __int64 (__fastcall ***)(struct Windows::Compat::Appraiser::IAsset *, __int64 *, __int64), const char *, struct Windows::Compat::Appraiser::IPropertyListEnumerator *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1801121a4`
- `0x180112ed0`

## callees

- `0x180001b94`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800ad88c`
- `0x1800f219c`
- `0x1801114c8`
- `0x180112594`
- `0x180113ec0`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1801140f6`
- `KERNEL32!GetSystemTime` at `0x1801142f9`
- `KERNEL32!GetSystemTime` at `0x1801140f6`
- `KERNEL32!GetSystemTime` at `0x1801142f9`
- `KERNEL32!GetProcessHeap` at `0x1801143eb`
- `KERNEL32!GetProcessHeap` at `0x1801143eb`
- `KERNEL32!HeapFree` at `0x1801143f9`
- `KERNEL32!HeapFree` at `0x1801143f9`

## string_xrefs

- `0x180113f1d`: `ResolveAttempted`
- `0x180114217`: `Error saving uninstall string: [0x%x].`
- `0x180114233`: `Error saving uninstall string: [0x%x].`
- `0x180113f44`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180113f89`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180113fd6`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180114020`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180114160`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x1801141a6`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x1801141e4`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x18011423f`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180114363`: `onecore\base\appcompat\appraiser\outputters\setupxml_app.cpp`
- `0x180113f4b`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction`
- `0x180113f7d`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction`
- `0x180113fdd`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction`
- `0x180114007`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction`
- `0x18011436a`: `Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction`
- `0x18011419a`: `Failed to write named program action: [0x%x].`
- `0x1801141d6`: `Failed to write named program action: [0x%x].`
- `0x180114182`: `AutoUninstall`
- `0x18011414f`: `Have uninstall info for %ls.`
- `0x180113fca`: `Error trying to create uninstall string: [0x%x].`
- `0x180114012`: `Error trying to create uninstall string: [0x%x].`
- `0x1801143ab`: `Failed to write action node: [0x%x].`
- `0x1801143c9`: `Failed to write action node: [0x%x].`
- `0x180114396`: `ManualUninstall`
- `0x180114357`: `Manual uninstall required for %ls.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction(
        Windows::Compat::Appraiser::SetupXmlOutputter *this,
        struct IXmlWriter *a2,
        __int64 (__fastcall ***a3)(struct Windows::Compat::Appraiser::IAsset *, __int64 *, __int64),
        const char *a4,
        struct Windows::Compat::Appraiser::IPropertyListEnumerator *a5)
{
  void *v5; // rdi
  int SingleValue; // eax
  int v11; // ebx
  int UninstallStringAlloc; // eax
  volatile signed __int64 *v13; // rcx
  void **v14; // rdx
  int v15; // ebx
  int v16; // r8d
  int v17; // r9d
  const char *v18; // r9
  char v19; // dl
  __int64 (__fastcall *v20)(const char *, void *, _QWORD); // rax
  const char *v21; // r9
  unsigned int v22; // ecx
  volatile signed __int64 *v23; // rcx
  void **v24; // rdx
  int v25; // ebx
  int v26; // r8d
  int v27; // r9d
  HANDLE ProcessHeap; // rax
  char *v30; // [rsp+20h] [rbp-E0h]
  char *v31; // [rsp+20h] [rbp-E0h]
  char *v32; // [rsp+20h] [rbp-E0h]
  char *v33; // [rsp+30h] [rbp-D0h]
  char *v34; // [rsp+30h] [rbp-D0h]
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *String1; // [rsp+58h] [rbp-A8h] BYREF
  const char *v37; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v38; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v39[2]; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  struct _SYSTEMTIME v41; // [rsp+90h] [rbp-70h] BYREF
  char v42[144]; // [rsp+A0h] [rbp-60h] BYREF
  char v43[144]; // [rsp+130h] [rbp+30h] BYREF

  v5 = 0;
  String1 = 0;
  lpMem = 0;
  if ( !a3 )
    goto LABEL_33;
  SingleValue = Windows::Compat::Appraiser::AssetUtils::GetSingleValue(&String1, L"ResolveAttempted", a3, 2);
  v11 = SingleValue;
  if ( SingleValue < 0 )
  {
    LODWORD(v33) = SingleValue;
    LODWORD(v30) = SingleValue;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      131,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      v30,
      (int)"Error getting single value: [0x%x].",
      v33);
    return (unsigned int)v11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x283u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      "Error getting single value: [0x%x].",
      SingleValue);
  if ( String1 && !wcscmp_0(String1, L"TRUE") )
    goto LABEL_33;
  UninstallStringAlloc = Windows::Compat::Appraiser::SetupXmlOutputter::GetUninstallStringAlloc(
                           (const unsigned __int16 **)&lpMem,
                           a3);
  v11 = UninstallStringAlloc;
  if ( UninstallStringAlloc < 0 )
  {
    LODWORD(v33) = UninstallStringAlloc;
    LODWORD(v30) = UninstallStringAlloc;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      139,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      v30,
      (int)"Error trying to create uninstall string: [0x%x].",
      v33);
    v5 = lpMem;
    goto LABEL_47;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x28Bu,
      "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      "Error trying to create uninstall string: [0x%x].",
      UninstallStringAlloc);
  v5 = lpMem;
  if ( v11 == 1 )
    v5 = 0;
  if ( !v5 )
  {
LABEL_33:
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v42);
    v23 = (volatile signed __int64 *)v42;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v23 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v23,
      _InterlockedExchangeAdd64(v23 + 17, 0),
      v43);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v24);
    v25 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v38 = 0x1000000;
      v39[0] = v43;
      v37 = a4;
      String1 = (wchar_t *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      lpMem = &v41;
      v41 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v25,
        (unsigned int)byte_1802A50ED,
        v26,
        v27,
        (__int64)&lpMem,
        (__int64)&String1,
        (__int64)&v37,
        (__int64)&v38,
        (__int64)v39);
    }
    Windows::Compat::Appraiser::WriteLog(
      0,
      162,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      0,
      (int)"Manual uninstall required for %ls.",
      a4);
    v11 = Windows::Compat::Appraiser::SetupXmlOutputter::WriteActionNode(
            a2,
            L"ManualUninstall",
            0,
            L"Text",
            (const unsigned __int16 *)v32);
    if ( v11 < 0 )
    {
      v18 = "Failed to write action node: [0x%x].";
      v19 = -91;
      goto LABEL_25;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v21 = "Failed to write action node: [0x%x].";
      v22 = 677;
      goto LABEL_45;
    }
  }
  else
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v42);
    v13 = (volatile signed __int64 *)v42;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v13 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v13,
      _InterlockedExchangeAdd64(v13 + 17, 0),
      v43);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v14);
    v15 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000020LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000020LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      lpMem = (LPVOID)0x1000000;
      String1 = (wchar_t *)v43;
      v37 = a4;
      v38 = (__int64)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v39[0] = &v41;
      v41 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)byte_1802A519D,
        v16,
        v17,
        (__int64)v39,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)&lpMem,
        (__int64)&String1);
    }
    Windows::Compat::Appraiser::WriteLog(
      0,
      148,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
      "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
      0,
      (int)"Have uninstall info for %ls.",
      a4);
    v11 = Windows::Compat::Appraiser::SetupXmlOutputter::WriteNamedProgramAction(
            a2,
            (const unsigned __int16 *)a4,
            L"AutoUninstall",
            a5);
    if ( v11 < 0 )
    {
      v18 = "Failed to write named program action: [0x%x].";
      v19 = -104;
LABEL_25:
      LODWORD(v34) = v11;
      LODWORD(v31) = v11;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v19,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
        v31,
        (int)v18,
        v34);
      goto LABEL_47;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x298u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
        "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
        "Failed to write named program action: [0x%x].",
        v11);
    v20 = (__int64 (__fastcall *)(const char *, void *, _QWORD))*((_QWORD *)this + 13);
    if ( v20 )
    {
      v11 = v20(a4, v5, *((_QWORD *)this + 7));
      if ( v11 < 0 )
      {
        v18 = "Error saving uninstall string: [0x%x].";
        v19 = -99;
        goto LABEL_25;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      {
        v21 = "Error saving uninstall string: [0x%x].";
        v22 = 669;
LABEL_45:
        LODWORD(v31) = v11;
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          v22,
          "onecore\\base\\appcompat\\appraiser\\outputters\\setupxml_app.cpp",
          "Windows::Compat::Appraiser::SetupXmlOutputter::WriteProgramUninstallAction",
          v21,
          v31);
      }
    }
  }
  v11 = 0;
LABEL_47:
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180113ec0  push    rbp
0x180113ec2  push    rbx
0x180113ec3  push    rsi
0x180113ec4  push    rdi
0x180113ec5  push    r12
0x180113ec7  push    r13
0x180113ec9  push    r14
0x180113ecb  push    r15
0x180113ecd  lea     rbp, [rsp-0D8h]
0x180113ed5  sub     rsp, 1D8h
0x180113edc  mov     rax, cs:__security_cookie
0x180113ee3  xor     rax, rsp
0x180113ee6  mov     [rbp+110h+var_50], rax
0x180113eed  mov     r12, [rbp+110h+arg_20]
0x180113ef4  xor     edi, edi
0x180113ef6  mov     [rsp+210h+String1], 0
0x180113eff  mov     r14, r9
0x180113f02  mov     [rsp+210h+lpMem], rdi
0x180113f07  mov     rsi, r8
0x180113f0a  mov     r13, rdx
0x180113f0d  mov     r15, rcx
0x180113f10  test    r8, r8
0x180113f13  jz      loc_18011424B
0x180113f19  lea     r9d, [rdi+2]
0x180113f1d  lea     rdx, aResolveattempt; "ResolveAttempted"
0x180113f24  lea     rcx, [rsp+210h+String1]
0x180113f29  call    ?GetSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIAsset@234@W4Tier@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IAsset *,Windows::Compat::Appraiser::Tier)
0x180113f2e  mov     ebx, eax
0x180113f30  test    eax, eax
0x180113f32  jns     short loc_180113F68
0x180113f34  mov     dword ptr [rsp+210h+var_1E0], eax; char *
0x180113f38  lea     r9, aErrorGettingSi; "Error getting single value: [0x%x]."
0x180113f3f  mov     qword ptr [rsp+210h+var_1E8], r9; int
0x180113f44  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180113f4b  lea     r9, aWindowsCompatA_49; "Windows::Compat::Appraiser::SetupXmlOut"...
0x180113f52  mov     dword ptr [rsp+210h+var_1F0], eax; char *
0x180113f56  mov     edx, 283h; bool
0x180113f5b  lea     ecx, [rdi+1]; this
0x180113f5e  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180113f63  jmp     loc_1801143FF
0x180113f68  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180113f6e  test    al, 1
0x180113f70  jz      short loc_180113F95
0x180113f72  lea     r9, aErrorGettingSi; "Error getting single value: [0x%x]."
0x180113f79  mov     dword ptr [rsp+210h+var_1F0], ebx
0x180113f7d  lea     r8, aWindowsCompatA_49; "Windows::Compat::Appraiser::SetupXmlOut"...
0x180113f84  mov     ecx, 283h; unsigned int
0x180113f89  lea     rdx, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180113f90  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180113f95  mov     rcx, [rsp+210h+String1]; String1
0x180113f9a  test    rcx, rcx
0x180113f9d  jz      short loc_180113FB3
0x180113f9f  lea     rdx, aTrue_2; "TRUE"
0x180113fa6  call    wcscmp_0
0x180113fab  test    eax, eax
0x180113fad  jz      loc_18011424B
0x180113fb3  mov     rdx, rsi; struct Windows::Compat::Appraiser::IAsset *
0x180113fb6  lea     rcx, [rsp+210h+lpMem]; unsigned __int16 **
0x180113fbb  call    ?GetUninstallStringAlloc@SetupXmlOutputter@Appraiser@Compat@Windows@@CAJPEAPEBGPEAVIAsset@234@@Z; Windows::Compat::Appraiser::SetupXmlOutputter::GetUninstallStringAlloc(ushort const * *,Windows::Compat::Appraiser::IAsset *)
0x180113fc0  mov     ebx, eax
0x180113fc2  test    eax, eax
0x180113fc4  jns     short loc_180114001
0x180113fc6  mov     dword ptr [rsp+210h+var_1E0], eax; char *
0x180113fca  lea     r9, aErrorTryingToC; "Error trying to create uninstall string"...
0x180113fd1  mov     qword ptr [rsp+210h+var_1E8], r9; int
0x180113fd6  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180113fdd  lea     r9, aWindowsCompatA_49; "Windows::Compat::Appraiser::SetupXmlOut"...
0x180113fe4  mov     dword ptr [rsp+210h+var_1F0], eax; char *
0x180113fe8  mov     edx, 28Bh; bool
0x180113fed  mov     ecx, 1; this
0x180113ff2  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180113ff7  mov     rdi, [rsp+210h+lpMem]
0x180113ffc  jmp     loc_1801143E6
0x180114001  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180114007  lea     rsi, aWindowsCompatA_49; "Windows::Compat::Appraiser::SetupXmlOut"...
0x18011400e  test    al, 1
0x180114010  jz      short loc_180114031
0x180114012  lea     r9, aErrorTryingToC; "Error trying to create uninstall string"...
0x180114019  mov     dword ptr [rsp+210h+var_1F0], ebx
0x18011401d  mov     r8, rsi; char *
0x180114020  lea     rdx, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180114027  mov     ecx, 28Bh; unsigned int
0x18011402c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180114031  mov     rdi, [rsp+210h+lpMem]
0x180114036  xor     eax, eax
0x180114038  cmp     ebx, 1
0x18011403b  cmovz   rdi, rax
0x18011403f  test    rdi, rdi
0x180114042  jz      loc_18011424B
0x180114048  lea     rcx, [rbp+110h+var_170]; this
0x18011404c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180114051  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180114058  lea     rcx, [rbp+110h+var_170]
0x18011405c  test    rax, rax
0x18011405f  cmovnz  rcx, rax; this
0x180114063  xor     edx, edx
0x180114065  lock xadd [rcx+88h], rdx; unsigned __int64
0x18011406e  lea     r8, [rbp+110h+var_E0]; char *
0x180114072  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180114077  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18011407e  jz      short loc_18011408C
0x180114080  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180114087  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18011408c  mov     rbx, cs:qword_1802C9628
0x180114093  mov     eax, [rbx]
0x180114095  cmp     eax, 5
0x180114098  jbe     loc_18011414F
0x18011409e  mov     rdx, [rbx+18h]
0x1801140a2  mov     rcx, 200000000020h
0x1801140ac  mov     rax, [rbx+10h]
0x1801140b0  test    rcx, rax
0x1801140b3  jz      loc_18011414F
0x1801140b9  mov     rax, rdx
0x1801140bc  and     rax, rcx
0x1801140bf  cmp     rax, rdx
0x1801140c2  jnz     loc_18011414F
0x1801140c8  lea     rax, [rbp+110h+var_E0]
0x1801140cc  mov     [rsp+210h+lpMem], 1000000h
0x1801140d5  mov     [rsp+210h+String1], rax
0x1801140da  lea     rcx, [rbp+110h+SystemTime]; lpSystemTime
0x1801140de  lea     rax, szValueBuf
0x1801140e5  mov     [rsp+210h+var_1B0], r14
0x1801140ea  xorps   xmm0, xmm0
0x1801140ed  mov     [rsp+210h+var_1A8], rax
0x1801140f2  movups  xmmword ptr [rbp+110h+SystemTime.wYear], xmm0
0x1801140f6  call    cs:__imp_GetSystemTime
0x1801140fc  movaps  xmm0, xmmword ptr [rbp+110h+SystemTime.wYear]
0x180114100  lea     rax, [rbp+110h+var_180]
0x180114104  mov     [rsp+210h+var_1A0], rax
0x180114109  lea     rdx, byte_1802A519D
0x180114110  lea     rax, [rsp+210h+String1]
0x180114115  movdqa  [rbp+110h+var_180], xmm0
0x18011411a  mov     [rsp+210h+var_1D0], rax
0x18011411f  mov     rcx, rbx
0x180114122  lea     rax, [rsp+210h+lpMem]
0x180114127  mov     [rsp+210h+var_1D8], rax
0x18011412c  lea     rax, [rsp+210h+var_1B0]
0x180114131  mov     [rsp+210h+var_1E0], rax
0x180114136  lea     rax, [rsp+210h+var_1A8]
0x18011413b  mov     qword ptr [rsp+210h+var_1E8], rax
0x180114140  lea     rax, [rsp+210h+var_1A0]
0x180114145  mov     [rsp+210h+var_1F0], rax
0x18011414a  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x18011414f  lea     rax, aHaveUninstallI; "Have uninstall info for %ls."
0x180114156  mov     [rsp+210h+var_1E0], r14; char *
0x18011415b  mov     qword ptr [rsp+210h+var_1E8], rax; int
0x180114160  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180114167  mov     r9, rsi; char *
0x18011416a  mov     [rsp+210h+var_1F0], 0; char *
0x180114173  mov     edx, 294h; bool
0x180114178  xor     ecx, ecx; this
0x18011417a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18011417f  mov     r9, r12; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x180114182  lea     r8, aAutouninstall; "AutoUninstall"
0x180114189  mov     rdx, r14; unsigned __int16 *
0x18011418c  mov     rcx, r13; struct IXmlWriter *
0x18011418f  call    ?WriteNamedProgramAction@SetupXmlOutputter@Appraiser@Compat@Windows@@CAJPEAUIXmlWriter@@PEBG1PEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::SetupXmlOutputter::WriteNamedProgramAction(IXmlWriter *,ushort const *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x180114194  mov     ebx, eax
0x180114196  test    eax, eax
0x180114198  jns     short loc_1801141CC
0x18011419a  lea     r9, aFailedToWriteN_2; "Failed to write named program action: ["...
0x1801141a1  mov     edx, 298h; bool
0x1801141a6  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1801141ad  mov     dword ptr [rsp+210h+var_1E0], ebx; char *
0x1801141b1  mov     ecx, 1; this
0x1801141b6  mov     qword ptr [rsp+210h+var_1E8], r9; int
0x1801141bb  mov     r9, rsi; char *
0x1801141be  mov     dword ptr [rsp+210h+var_1F0], ebx; char *
0x1801141c2  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801141c7  jmp     loc_1801143E6
0x1801141cc  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801141d2  test    al, 1
0x1801141d4  jz      short loc_1801141F5
0x1801141d6  lea     r9, aFailedToWriteN_2; "Failed to write named program action: ["...
0x1801141dd  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1801141e1  mov     r8, rsi; char *
0x1801141e4  lea     rdx, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1801141eb  mov     ecx, 298h; unsigned int
0x1801141f0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801141f5  mov     rax, [r15+68h]
0x1801141f9  test    rax, rax
0x1801141fc  jz      loc_1801143E4
0x180114202  mov     r8, [r15+38h]
0x180114206  mov     rdx, rdi
0x180114209  mov     rcx, r14
0x18011420c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180114211  mov     ebx, eax
0x180114213  test    eax, eax
0x180114215  jns     short loc_180114225
0x180114217  lea     r9, aErrorSavingUni; "Error saving uninstall string: [0x%x]."
0x18011421e  mov     edx, 29Dh
0x180114223  jmp     short loc_1801141A6
0x180114225  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18011422b  test    al, 1
0x18011422d  jz      loc_1801143E4
0x180114233  lea     r9, aErrorSavingUni; "Error saving uninstall string: [0x%x]."
0x18011423a  mov     ecx, 29Dh
0x18011423f  lea     rdx, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x180114246  jmp     loc_1801143D8
0x18011424b  lea     rcx, [rbp+110h+var_170]; this
0x18011424f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180114254  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18011425b  lea     rcx, [rbp+110h+var_170]
0x18011425f  test    rax, rax
0x180114262  cmovnz  rcx, rax; this
0x180114266  xor     edx, edx
0x180114268  lock xadd [rcx+88h], rdx; unsigned __int64
0x180114271  lea     r8, [rbp+110h+var_E0]; char *
0x180114275  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18011427a  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180114281  jz      short loc_18011428F
0x180114283  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18011428a  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18011428f  mov     rbx, cs:qword_1802C9628
0x180114296  mov     eax, [rbx]
0x180114298  cmp     eax, 5
0x18011429b  jbe     loc_180114352
0x1801142a1  mov     rdx, [rbx+18h]
0x1801142a5  mov     rcx, 200000000020h
0x1801142af  mov     rax, [rbx+10h]
0x1801142b3  test    rcx, rax
0x1801142b6  jz      loc_180114352
0x1801142bc  mov     rax, rdx
0x1801142bf  and     rax, rcx
0x1801142c2  cmp     rax, rdx
0x1801142c5  jnz     loc_180114352
0x1801142cb  lea     rax, [rbp+110h+var_E0]
0x1801142cf  mov     [rsp+210h+var_1A8], 1000000h
0x1801142d8  mov     [rsp+210h+var_1A0], rax
0x1801142dd  lea     rcx, [rbp+110h+SystemTime]; lpSystemTime
0x1801142e1  lea     rax, szValueBuf
0x1801142e8  mov     [rsp+210h+var_1B0], r14
0x1801142ed  xorps   xmm0, xmm0
0x1801142f0  mov     [rsp+210h+String1], rax
0x1801142f5  movups  xmmword ptr [rbp+110h+SystemTime.wYear], xmm0
0x1801142f9  call    cs:__imp_GetSystemTime
0x1801142ff  movaps  xmm0, xmmword ptr [rbp+110h+SystemTime.wYear]
0x180114303  lea     rax, [rbp+110h+var_180]
0x180114307  mov     [rsp+210h+lpMem], rax
0x18011430c  lea     rdx, byte_1802A50ED
0x180114313  lea     rax, [rsp+210h+var_1A0]
0x180114318  movdqa  [rbp+110h+var_180], xmm0
0x18011431d  mov     [rsp+210h+var_1D0], rax
0x180114322  mov     rcx, rbx
0x180114325  lea     rax, [rsp+210h+var_1A8]
0x18011432a  mov     [rsp+210h+var_1D8], rax
0x18011432f  lea     rax, [rsp+210h+var_1B0]
0x180114334  mov     [rsp+210h+var_1E0], rax
0x180114339  lea     rax, [rsp+210h+String1]
0x18011433e  mov     qword ptr [rsp+210h+var_1E8], rax
0x180114343  lea     rax, [rsp+210h+lpMem]
0x180114348  mov     [rsp+210h+var_1F0], rax
0x18011434d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x180114352  mov     [rsp+210h+var_1E0], r14; char *
0x180114357  lea     rax, aManualUninstal; "Manual uninstall required for %ls."
0x18011435e  mov     qword ptr [rsp+210h+var_1E8], rax; int
0x180114363  lea     r14, aOnecoreBaseApp_88; "onecore\\base\\appcompat\\appraiser\\ou"...
0x18011436a  lea     rsi, aWindowsCompatA_49; "Windows::Compat::Appraiser::SetupXmlOut"...
0x180114371  mov     [rsp+210h+var_1F0], 0; unsigned __int16 *
0x18011437a  mov     r8, r14; unsigned int
0x18011437d  mov     r9, rsi; char *
0x180114380  mov     edx, 2A2h; bool
0x180114385  xor     ecx, ecx; this
0x180114387  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18011438c  lea     r9, aText_2; "Text"
0x180114393  xor     r8d, r8d; unsigned __int16 *
0x180114396  lea     rdx, aManualuninstal; "ManualUninstall"
0x18011439d  mov     rcx, r13; struct IXmlWriter *
0x1801143a0  call    ?WriteActionNode@SetupXmlOutputter@Appraiser@Compat@Windows@@CAJPEAUIXmlWriter@@PEBG111@Z; Windows::Compat::Appraiser::SetupXmlOutputter::WriteActionNode(IXmlWriter *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1801143a5  mov     ebx, eax
0x1801143a7  test    eax, eax
0x1801143a9  jns     short loc_1801143BF
0x1801143ab  lea     r9, aFailedToWriteA_5; "Failed to write action node: [0x%x]."
0x1801143b2  mov     r8, r14
0x1801143b5  mov     edx, 2A5h
0x1801143ba  jmp     loc_1801141AD
0x1801143bf  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801143c5  test    al, 1
0x1801143c7  jz      short loc_1801143E4
0x1801143c9  lea     r9, aFailedToWriteA_5; "Failed to write action node: [0x%x]."
0x1801143d0  mov     rdx, r14; char *
0x1801143d3  mov     ecx, 2A5h; unsigned int
0x1801143d8  mov     r8, rsi; char *
0x1801143db  mov     dword ptr [rsp+210h+var_1F0], ebx
0x1801143df  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801143e4  xor     ebx, ebx
0x1801143e6  test    rdi, rdi
0x1801143e9  jz      short loc_1801143FF
0x1801143eb  call    cs:__imp_GetProcessHeap
0x1801143f1  mov     r8, rdi; lpMem
0x1801143f4  xor     edx, edx; dwFlags
0x1801143f6  mov     rcx, rax; hHeap
0x1801143f9  call    cs:__imp_HeapFree
0x1801143ff  mov     eax, ebx
0x180114401  mov     rcx, [rbp+110h+var_50]
0x180114408  xor     rcx, rsp; StackCookie
0x18011440b  call    __security_check_cookie
0x180114410  add     rsp, 1D8h
0x180114417  pop     r15
0x180114419  pop     r14
  ... truncated ...
```
