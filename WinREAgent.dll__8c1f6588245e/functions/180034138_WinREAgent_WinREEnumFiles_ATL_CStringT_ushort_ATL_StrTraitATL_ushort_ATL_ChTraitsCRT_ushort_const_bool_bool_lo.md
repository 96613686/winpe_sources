# WinREAgent::WinREEnumFiles(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,bool,long (*)(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *),void *)

- ea: `0x180034138`
- end: `0x180034479`
- name: `?WinREEnumFiles@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1P6AJ00PEAX@Z2@Z`
- size: `833`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180024a40`
- `0x180034138`

## callees

- `0x180004af8`
- `0x1800050bc`
- `0x180005c70`
- `0x18000d92c`
- `0x180024890`
- `0x180034138`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004c914`
- `0x18004cef4`
- `0x18004e9dc`
- `0x18004eb3c`
- `0x18006c690`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003433f`
- `msvcrt!_wcsicmp` at `0x18003433f`

## string_xrefs

- `0x180034173`: `Path [%s] is not a directory`
- `0x180034187`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180034222`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x18003427e`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x1800342fb`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x1800343b5`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x18003441f`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x18003418e`: `WinREAgent::WinREEnumFiles`
- `0x180034229`: `WinREAgent::WinREEnumFiles`
- `0x180034285`: `WinREAgent::WinREEnumFiles`
- `0x180034302`: `WinREAgent::WinREEnumFiles`
- `0x1800343bc`: `WinREAgent::WinREEnumFiles`
- `0x180034426`: `WinREAgent::WinREEnumFiles`
- `0x1800341bd`: `WinREEnumFiles: skip [%s] as it's reparse point`
- `0x18003440b`: `Failed to construct full path to subdir [%s] in [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::WinREEnumFiles(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  int v7; // edi
  __int64 v8; // r8
  unsigned __int64 v9; // rdi
  unsigned __int64 i; // rsi
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r8
  unsigned __int64 j; // rsi
  const wchar_t **v15; // r14
  int v16; // edx
  int v17; // r8d
  __int64 v18; // [rsp+40h] [rbp-31h] BYREF
  unsigned __int64 v19; // [rsp+48h] [rbp-29h]
  __int64 v20; // [rsp+50h] [rbp-21h]
  int v21; // [rsp+58h] [rbp-19h]
  __int64 v22; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int64 v23; // [rsp+68h] [rbp-9h]
  __int64 v24; // [rsp+70h] [rbp-1h]
  int v25; // [rsp+78h] [rbp+7h]
  __int64 v26; // [rsp+80h] [rbp+Fh] BYREF

  if ( (unsigned __int8)PushButtonReset::Path::IsDirectory(a1) )
  {
    if ( (unsigned __int8)PushButtonReset::Path::IsReparsePoint(a1) )
    {
      PushButtonReset::Logging::Trace(0, L"WinREEnumFiles: skip [%s] as it's reparse point", *a1);
      return 1;
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v7 = PushButtonReset::Directory::EnumFiles(a1, &v22);
      if ( v7 >= 0 )
      {
        v9 = 0;
        for ( i = v23; v9 < i; ++v9 )
        {
          v11 = ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                  &v22,
                  v9,
                  v8);
          v12 = DeleteNonWinREFileCallback(a1, v11, a5);
          if ( v12 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v12,
              "WinREAgent::WinREEnumFiles",
              "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
              67,
              L"WinREEnumFiles: Callback failed or request enumeration interruption");
            PushButtonReset::Logging::Trace(0, L"WinREEnumFiles: Ignore the error and continue enumeration");
          }
        }
        v18 = 0;
        v19 = 0;
        v20 = 0;
        v21 = 0;
        v7 = PushButtonReset::Directory::EnumSubdirs(a1, &v18);
        if ( v7 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v7,
            "WinREAgent::WinREEnumFiles",
            "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
            88,
            L"Failed to enumerate subdirectories in [%s]",
            *a1);
          goto LABEL_22;
        }
        for ( j = 0; j < v19; ++j )
        {
          v15 = (const wchar_t **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                    &v18,
                                    j,
                                    v13);
          if ( _wcsicmp(*v15, L"System Volume Information") )
          {
            ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
            v7 = PushButtonReset::Path::Combine(a1, v15, &v26);
            if ( v7 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v7,
                "WinREAgent::WinREEnumFiles",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                104,
                L"Failed to construct full path to subdir [%s] in [%s]",
                *v15,
                *a1);
              ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
              break;
            }
            LOBYTE(v17) = 1;
            LOBYTE(v16) = 1;
            v7 = WinREAgent::WinREEnumFiles((unsigned int)&v26, v16, v17, (unsigned int)DeleteNonWinREFileCallback, a5);
            if ( v7 < 0 )
            {
              PushButtonReset::Logging::TraceErr(
                1,
                (unsigned int)v7,
                "WinREAgent::WinREEnumFiles",
                "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
                111,
                L"WinREEnumFiles: Failed to enum sub folder [%s] in [%s]",
                *v15,
                *a1);
              PushButtonReset::Logging::Trace(0, L"WinREEnumFiles: Ignore the error and continue enumeration");
              v7 = 0;
            }
            ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
          }
        }
LABEL_22:
        ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v18);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v7,
          "WinREAgent::WinREEnumFiles",
          "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
          57,
          L"Failed to enumerate [%s]",
          *a1);
      }
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v22);
      return (unsigned int)v7;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREEnumFiles",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      46,
      L"Path [%s] is not a directory",
      *a1);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180034138  push    rbp
0x18003413a  push    rbx
0x18003413b  push    rsi
0x18003413c  push    rdi
0x18003413d  push    r12
0x18003413f  push    r14
0x180034141  lea     rbp, [rsp-27h]
0x180034146  sub     rsp, 98h
0x18003414d  mov     rax, cs:__security_cookie
0x180034154  xor     rax, rsp
0x180034157  mov     [rbp+4Fh+var_38], rax
0x18003415b  mov     rbx, rcx
0x18003415e  mov     r12, [rbp+4Fh+arg_20]
0x180034162  call    ?IsDirectory@Path@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Path::IsDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180034167  test    al, al
0x180034169  jnz     short loc_1800341AE
0x18003416b  mov     rax, [rbx]
0x18003416e  mov     [rsp+0C0h+var_90], rax
0x180034173  lea     rax, aPathSIsNotADir; "Path [%s] is not a directory"
0x18003417a  mov     [rsp+0C0h+var_98], rax
0x18003417f  mov     dword ptr [rsp+0C0h+var_A0], 2Eh ; '.'
0x180034187  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003418e  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x180034195  mov     edx, 80070057h
0x18003419a  mov     ecx, 2
0x18003419f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800341a4  mov     eax, 80070057h
0x1800341a9  jmp     loc_18003445D
0x1800341ae  mov     rcx, rbx
0x1800341b1  call    ?IsReparsePoint@Path@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Path::IsReparsePoint(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800341b6  test    al, al
0x1800341b8  jz      short loc_1800341D5
0x1800341ba  mov     r8, [rbx]
0x1800341bd  lea     rdx, aWinreenumfiles_0; "WinREEnumFiles: skip [%s] as it's repar"...
0x1800341c4  xor     ecx, ecx
0x1800341c6  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800341cb  mov     eax, 1
0x1800341d0  jmp     loc_18003445D
0x1800341d5  mov     [rbp+4Fh+var_60], 0
0x1800341dd  mov     [rbp+4Fh+var_58], 0
0x1800341e5  mov     [rbp+4Fh+var_50], 0
0x1800341ed  mov     [rbp+4Fh+var_48], 0
0x1800341f4  lea     rdx, [rbp+4Fh+var_60]
0x1800341f8  mov     rcx, rbx
0x1800341fb  call    ?EnumFiles@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; PushButtonReset::Directory::EnumFiles(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x180034200  mov     edi, eax
0x180034202  test    eax, eax
0x180034204  jns     short loc_180034241
0x180034206  mov     rcx, [rbx]
0x180034209  mov     [rsp+0C0h+var_90], rcx
0x18003420e  lea     rax, aFailedToEnumer_9; "Failed to enumerate [%s]"
0x180034215  mov     [rsp+0C0h+var_98], rax
0x18003421a  mov     dword ptr [rsp+0C0h+var_A0], 39h ; '9'
0x180034222  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180034229  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x180034230  mov     edx, edi
0x180034232  mov     ecx, 2
0x180034237  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18003423c  jmp     loc_180034452
0x180034241  xor     edi, edi
0x180034243  mov     rsi, [rbp+4Fh+var_58]
0x180034247  test    rsi, rsi
0x18003424a  jz      short loc_1800342AE
0x18003424c  mov     rdx, rdi
0x18003424f  lea     rcx, [rbp+4Fh+var_60]
0x180034253  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180034258  mov     rdx, rax
0x18003425b  mov     r8, r12
0x18003425e  mov     rcx, rbx
0x180034261  call    ?DeleteNonWinREFileCallback@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAX@Z; DeleteNonWinREFileCallback(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *)
0x180034266  test    eax, eax
0x180034268  jns     short loc_1800342A6
0x18003426a  lea     rcx, aWinreenumfiles_1; "WinREEnumFiles: Callback failed or requ"...
0x180034271  mov     [rsp+0C0h+var_98], rcx
0x180034276  mov     dword ptr [rsp+0C0h+var_A0], 43h ; 'C'
0x18003427e  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180034285  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x18003428c  mov     edx, eax
0x18003428e  mov     ecx, 1
0x180034293  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034298  lea     rdx, aWinreenumfiles_2; "WinREEnumFiles: Ignore the error and co"...
0x18003429f  xor     ecx, ecx
0x1800342a1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800342a6  inc     rdi
0x1800342a9  cmp     rdi, rsi
0x1800342ac  jb      short loc_18003424C
0x1800342ae  mov     [rbp+4Fh+var_80], 0
0x1800342b6  mov     [rbp+4Fh+var_78], 0
0x1800342be  mov     [rbp+4Fh+var_70], 0
0x1800342c6  mov     [rbp+4Fh+var_68], 0
0x1800342cd  lea     rdx, [rbp+4Fh+var_80]
0x1800342d1  mov     rcx, rbx
0x1800342d4  call    ?EnumSubdirs@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@4@@Z; PushButtonReset::Directory::EnumSubdirs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x1800342d9  mov     edi, eax
0x1800342db  test    eax, eax
0x1800342dd  jns     short loc_18003431A
0x1800342df  mov     rcx, [rbx]
0x1800342e2  mov     [rsp+0C0h+var_90], rcx
0x1800342e7  lea     rax, aFailedToEnumer_12; "Failed to enumerate subdirectories in ["...
0x1800342ee  mov     [rsp+0C0h+var_98], rax
0x1800342f3  mov     dword ptr [rsp+0C0h+var_A0], 58h ; 'X'
0x1800342fb  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180034302  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x180034309  mov     edx, edi
0x18003430b  mov     ecx, 2
0x180034310  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034315  jmp     loc_180034448
0x18003431a  xor     esi, esi
0x18003431c  cmp     [rbp+4Fh+var_78], rsi
0x180034320  jbe     loc_180034448
0x180034326  mov     rdx, rsi
0x180034329  lea     rcx, [rbp+4Fh+var_80]
0x18003432d  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180034332  mov     r14, rax
0x180034335  lea     rdx, aSystemVolumeIn; "System Volume Information"
0x18003433c  mov     rcx, [rax]; String1
0x18003433f  call    cs:__imp__wcsicmp
0x180034345  test    eax, eax
0x180034347  jz      loc_1800343EC
0x18003434d  lea     rcx, [rbp+4Fh+var_40]
0x180034351  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180034356  nop
0x180034357  lea     r8, [rbp+4Fh+var_40]
0x18003435b  mov     rdx, r14
0x18003435e  mov     rcx, rbx
0x180034361  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180034366  mov     edi, eax
0x180034368  test    eax, eax
0x18003436a  js      loc_1800343FB
0x180034370  mov     [rsp+0C0h+var_A0], r12
0x180034375  lea     r9, ?DeleteNonWinREFileCallback@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAX@Z; DeleteNonWinREFileCallback(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *)
0x18003437c  mov     r8b, 1
0x18003437f  mov     dl, r8b
0x180034382  lea     rcx, [rbp+4Fh+var_40]
0x180034386  call    ?WinREEnumFiles@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N1P6AJ00PEAX@Z2@Z; WinREAgent::WinREEnumFiles(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,bool,long (*)(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,void *),void *)
0x18003438b  mov     edi, eax
0x18003438d  test    eax, eax
0x18003438f  jns     short loc_1800343DF
0x180034391  mov     rax, [rbx]
0x180034394  mov     [rsp+0C0h+var_88], rax
0x180034399  mov     rax, [r14]
0x18003439c  mov     [rsp+0C0h+var_90], rax
0x1800343a1  lea     rax, aWinreenumfiles; "WinREEnumFiles: Failed to enum sub fold"...
0x1800343a8  mov     [rsp+0C0h+var_98], rax
0x1800343ad  mov     dword ptr [rsp+0C0h+var_A0], 6Fh ; 'o'
0x1800343b5  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800343bc  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x1800343c3  mov     edx, edi
0x1800343c5  mov     ecx, 1
0x1800343ca  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800343cf  lea     rdx, aWinreenumfiles_2; "WinREEnumFiles: Ignore the error and co"...
0x1800343d6  xor     ecx, ecx
0x1800343d8  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800343dd  xor     edi, edi
0x1800343df  mov     rcx, [rbp+4Fh+var_40]
0x1800343e3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800343e7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800343ec  inc     rsi
0x1800343ef  cmp     rsi, [rbp+4Fh+var_78]
0x1800343f3  jb      loc_180034326
0x1800343f9  jmp     short loc_180034448
0x1800343fb  mov     rax, [rbx]
0x1800343fe  mov     [rsp+0C0h+var_88], rax
0x180034403  mov     rax, [r14]
0x180034406  mov     [rsp+0C0h+var_90], rax
0x18003440b  lea     rax, aFailedToConstr_13; "Failed to construct full path to subdir"...
0x180034412  mov     [rsp+0C0h+var_98], rax
0x180034417  mov     dword ptr [rsp+0C0h+var_A0], 68h ; 'h'
0x18003441f  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180034426  lea     r8, aWinreagentWinr_19; "WinREAgent::WinREEnumFiles"
0x18003442d  mov     edx, edi
0x18003442f  mov     ecx, 2
0x180034434  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034439  nop
0x18003443a  mov     rcx, [rbp+4Fh+var_40]
0x18003443e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180034442  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034447  nop
0x180034448  lea     rcx, [rbp+4Fh+var_80]
0x18003444c  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x180034451  nop
0x180034452  lea     rcx, [rbp+4Fh+var_60]
0x180034456  call    ??1?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAA@XZ; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::~CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>(void)
0x18003445b  mov     eax, edi
0x18003445d  mov     rcx, [rbp+4Fh+var_38]
0x180034461  xor     rcx, rsp; StackCookie
0x180034464  call    __security_check_cookie
0x180034469  add     rsp, 98h
0x180034470  pop     r14
0x180034472  pop     r12
0x180034474  pop     rdi
0x180034475  pop     rsi
0x180034476  pop     rbx
0x180034477  pop     rbp
0x180034478  retn
```
