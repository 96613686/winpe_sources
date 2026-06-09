# EstimateReconstructWindowsDiskNeeds

- ea: `0x180043520`
- end: `0x1800437a7`
- name: `EstimateReconstructWindowsDiskNeeds`
- size: `647`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18001f708`
- `0x180022d80`
- `0x1800293a0`
- `0x180041f78`
- `0x180042434`
- `0x180042464`
- `0x18004255c`
- `0x18004291c`
- `0x180042e2c`
- `0x180043520`
- `0x180044780`
- `0x18004b5d4`
- `0x18004c660`
- `0x18004d3a0`
- `0x18004d850`

## string_xrefs

- `0x1800435cf`: `No new Windows root path specified`
- `0x18004359a`: `No old Windows root path specified`
- `0x18004363d`: `Unable to allocate old windows root path.`
- `0x180043676`: `Unable to backslash-terminate path.`
- `0x180043683`: `System32\ssshim.dll`
- `0x180043697`: `Unable to append ssshim.dll to offline windows directory path.`
- `0x1800436b1`: `Unable to get architecture from ssshim.dll.`

## pseudocode

```c
unsigned __int64 __fastcall EstimateReconstructWindowsDiskNeeds(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct ICbsUIHandler *a4)
{
  unsigned int v7; // r15d
  __int64 v8; // rcx
  const char *v9; // r8
  int v10; // edx
  int v11; // ecx
  unsigned __int64 v12; // rbx
  int ProcessorArchitectureFromImageArchitecture; // eax
  const char *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned __int16 v18[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-4Ch] BYREF
  __int64 v20; // [rsp+38h] [rbp-48h] BYREF
  __int64 v21; // [rsp+40h] [rbp-40h] BYREF
  LPCWSTR lpFileName; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v23; // [rsp+50h] [rbp-30h] BYREF
  __int64 v24; // [rsp+58h] [rbp-28h] BYREF
  int v25; // [rsp+60h] [rbp-20h]
  int v26; // [rsp+64h] [rbp-1Ch]
  __int64 v27; // [rsp+68h] [rbp-18h] BYREF
  char v28; // [rsp+70h] [rbp-10h]

  lpFileName = 0;
  v18[0] = 0;
  v20 = 0;
  v23 = 0;
  v21 = 0;
  v24 = 0;
  v7 = a1;
  v27 = 0;
  v28 = 0;
  v19 = 0xFFFF;
  v25 = 1000;
  v26 = 10;
  LogAdapter::TraceAtLevel<>(a1, "pbr: Estimating disk space requirements...");
  if ( !a2 )
  {
    v9 = "No old Windows root path specified";
    goto LABEL_3;
  }
  if ( !a3 )
  {
    v9 = "No new Windows root path specified";
LABEL_3:
    LogAdapter::TraceAtLevelIfFailed<long,>(v8, 2147942487LL, v9);
    v11 = (int)LogAdapter::g_Logger;
    v12 = v23;
    if ( LogAdapter::g_Logger )
      goto LABEL_30;
    goto LABEL_31;
  }
  CEstimateDiskspaceProgressTracker::Initialize(
    (CEstimateDiskspaceProgressTracker *)&v24,
    a4,
    (v7 & 1) != 0 ? 38400 : 81139);
  v23 = (-(__int64)((v7 & 1) != 0) & 0xFFFFFFFEC0000000uLL) + 0x240000000LL;
  ProcessorArchitectureFromImageArchitecture = SczAllocConcat2Sz(&v20, a2, L"\\Windows\\");
  if ( ProcessorArchitectureFromImageArchitecture >= 0 )
  {
    if ( (int)SczAllocFromSz(&v21, a3) < 0 )
      goto LABEL_10;
    ProcessorArchitectureFromImageArchitecture = SczEnsureBackslashTerminated(&v21);
    if ( ProcessorArchitectureFromImageArchitecture >= 0 )
    {
      ProcessorArchitectureFromImageArchitecture = SczAllocConcat2Sz(&lpFileName, v20, L"System32\\ssshim.dll");
      if ( ProcessorArchitectureFromImageArchitecture >= 0 )
      {
        ProcessorArchitectureFromImageArchitecture = FileExecutableArchitecture(lpFileName, v18);
        if ( ProcessorArchitectureFromImageArchitecture >= 0 )
        {
          ProcessorArchitectureFromImageArchitecture = GetProcessorArchitectureFromImageArchitecture(v18[0], &v19);
          if ( ProcessorArchitectureFromImageArchitecture >= 0 )
          {
            v15 = EstimateDiskNeedsHelper(v7, v20, a3, &v24);
            if ( v28 )
            {
              v23 = 0;
              if ( LogAdapter::g_Logger )
                LogAdapter::Logger::LogNumObjects<unsigned __int64>(
                  (_DWORD)LogAdapter::g_Logger,
                  v10,
                  1,
                  (unsigned int)"pbr: Estimated reconstruction disk space needed: {}",
                  (__int64)&v23);
              v12 = 0;
              goto LABEL_31;
            }
            if ( !v19 || v19 == 5 )
              v16 = 157286400;
            else
              v16 = 209715200;
            v12 = v16 + v15;
            v23 = v16 + v15;
            goto LABEL_29;
          }
          v14 = "Unable to get processor architecture.";
        }
        else
        {
          v14 = "Unable to get architecture from ssshim.dll.";
        }
      }
      else
      {
        v14 = "Unable to append ssshim.dll to offline windows directory path.";
      }
    }
    else
    {
      v14 = "Unable to backslash-terminate path.";
    }
  }
  else
  {
    v14 = "Unable to allocate old windows root path.";
  }
  LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)ProcessorArchitectureFromImageArchitecture, v14);
LABEL_10:
  v12 = v23;
LABEL_29:
  v11 = (int)LogAdapter::g_Logger;
  if ( LogAdapter::g_Logger )
LABEL_30:
    LogAdapter::Logger::LogNumObjects<unsigned __int64>(
      v11,
      v10,
      1,
      (unsigned int)"pbr: Estimated reconstruction disk space needed: {}",
      (__int64)&v23);
LABEL_31:
  Windows::AutoComPtr<IClassFactory>::Close(&v27);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v21);
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v20);
  return v12;
}

```

## disassembly

```asm
0x180043520  push    rbp
0x180043522  push    rbx
0x180043523  push    rsi
0x180043524  push    rdi
0x180043525  push    r12
0x180043527  push    r14
0x180043529  push    r15
0x18004352b  mov     rbp, rsp
0x18004352e  sub     rsp, 80h
0x180043535  mov     rax, cs:__security_cookie
0x18004353c  xor     rax, rsp
0x18004353f  mov     [rbp+var_8], rax
0x180043543  xor     eax, eax
0x180043545  mov     [rbp+lpFileName], 0
0x18004354d  mov     r14, rdx
0x180043550  mov     [rbp+var_50], ax
0x180043554  lea     rdx, aPbrEstimatingD; "pbr: Estimating disk space requirements"...
0x18004355b  mov     [rbp+var_48], rax
0x18004355f  mov     [rbp+var_30], rax
0x180043563  mov     r12, r9
0x180043566  mov     [rbp+var_40], rax
0x18004356a  mov     rsi, r8
0x18004356d  mov     [rbp+var_28], rax
0x180043571  mov     r15d, ecx
0x180043574  mov     [rbp+var_18], rax
0x180043578  mov     [rbp+var_10], al
0x18004357b  mov     [rbp+var_4C], 0FFFFh
0x180043582  mov     [rbp+var_20], 3E8h
0x180043589  mov     [rbp+var_1C], 0Ah
0x180043590  call    ??$TraceAtLevel@$$V@LogAdapter@@YAXW4LogLevel@0@QEBD@Z; LogAdapter::TraceAtLevel<>(LogAdapter::LogLevel,char const * const)
0x180043595  test    r14, r14
0x180043598  jnz     short loc_1800435CA
0x18004359a  lea     r8, aNoOldWindowsRo; "No old Windows root path specified"
0x1800435a1  mov     edx, 80070057h
0x1800435a6  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800435ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800435b2  mov     rbx, [rbp+var_30]
0x1800435b6  test    rcx, rcx
0x1800435b9  jz      loc_18004376A
0x1800435bf  mov     r8d, 1
0x1800435c5  jmp     loc_180043755
0x1800435ca  test    rsi, rsi
0x1800435cd  jnz     short loc_1800435D8
0x1800435cf  lea     r8, aNoNewWindowsRo; "No new Windows root path specified"
0x1800435d6  jmp     short loc_1800435A1
0x1800435d8  mov     ebx, r15d
0x1800435db  lea     rcx, [rbp+var_28]; this
0x1800435df  mov     edi, 1
0x1800435e4  mov     rdx, r12; struct ICbsUIHandler *
0x1800435e7  and     ebx, edi
0x1800435e9  mov     eax, ebx
0x1800435eb  neg     eax
0x1800435ed  sbb     r8d, r8d
0x1800435f0  and     r8d, 0FFFF590Dh
0x1800435f7  add     r8d, 13CF3h; unsigned int
0x1800435fe  call    ?Initialize@CEstimateDiskspaceProgressTracker@@QEAAJPEAUICbsUIHandler@@K@Z; CEstimateDiskspaceProgressTracker::Initialize(ICbsUIHandler *,ulong)
0x180043603  mov     rcx, 0FFFFFFFEC0000000h
0x18004360d  lea     r8, aWindows_0; "\\Windows\\"
0x180043614  neg     ebx
0x180043616  mov     rdx, r14
0x180043619  sbb     rax, rax
0x18004361c  and     rax, rcx
0x18004361f  mov     rcx, 240000000h
0x180043629  add     rax, rcx
0x18004362c  lea     rcx, [rbp+var_48]
0x180043630  mov     [rbp+var_30], rax
0x180043634  call    SczAllocConcat2Sz
0x180043639  test    eax, eax
0x18004363b  jns     short loc_180043659
0x18004363d  lea     r8, aUnableToAlloca; "Unable to allocate old windows root pat"...
0x180043644  mov     edx, eax
0x180043646  mov     ecx, 2
0x18004364b  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x180043650  mov     rbx, [rbp+var_30]
0x180043654  jmp     loc_180043746
0x180043659  mov     rdx, rsi
0x18004365c  lea     rcx, [rbp+var_40]
0x180043660  call    SczAllocFromSz
0x180043665  test    eax, eax
0x180043667  js      short loc_180043650
0x180043669  lea     rcx, [rbp+var_40]
0x18004366d  call    SczEnsureBackslashTerminated
0x180043672  test    eax, eax
0x180043674  jns     short loc_18004367F
0x180043676  lea     r8, aUnableToBacksl; "Unable to backslash-terminate path."
0x18004367d  jmp     short loc_180043644
0x18004367f  mov     rdx, [rbp+var_48]
0x180043683  lea     r8, aSystem32Ssshim; "System32\\ssshim.dll"
0x18004368a  lea     rcx, [rbp+lpFileName]
0x18004368e  call    SczAllocConcat2Sz
0x180043693  test    eax, eax
0x180043695  jns     short loc_1800436A0
0x180043697  lea     r8, aUnableToAppend; "Unable to append ssshim.dll to offline "...
0x18004369e  jmp     short loc_180043644
0x1800436a0  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800436a4  lea     rdx, [rbp+var_50]
0x1800436a8  call    FileExecutableArchitecture
0x1800436ad  test    eax, eax
0x1800436af  jns     short loc_1800436BA
0x1800436b1  lea     r8, aUnableToGetArc; "Unable to get architecture from ssshim."...
0x1800436b8  jmp     short loc_180043644
0x1800436ba  movzx   ecx, [rbp+var_50]; unsigned __int16
0x1800436be  lea     rdx, [rbp+var_4C]; unsigned int *
0x1800436c2  call    ?GetProcessorArchitectureFromImageArchitecture@@YAJGPEAK@Z; GetProcessorArchitectureFromImageArchitecture(ushort,ulong *)
0x1800436c7  test    eax, eax
0x1800436c9  jns     short loc_1800436D7
0x1800436cb  lea     r8, aUnableToGetPro_8; "Unable to get processor architecture."
0x1800436d2  jmp     loc_180043644
0x1800436d7  mov     rdx, [rbp+var_48]
0x1800436db  lea     r9, [rbp+var_28]
0x1800436df  mov     r8, rsi
0x1800436e2  mov     ecx, r15d
0x1800436e5  call    EstimateDiskNeedsHelper
0x1800436ea  cmp     [rbp+var_10], 0
0x1800436ee  mov     rcx, rax
0x1800436f1  jz      short loc_180043723
0x1800436f3  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800436fa  mov     [rbp+var_30], 0
0x180043702  test    rcx, rcx
0x180043705  jz      short loc_18004371F
0x180043707  lea     rax, [rbp+var_30]
0x18004370b  mov     r8d, edi
0x18004370e  lea     r9, aPbrEstimatedRe_0; "pbr: Estimated reconstruction disk spac"...
0x180043715  mov     [rsp+80h+var_60], rax
0x18004371a  call    ??$LogNumObjects@_K@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEB_K@Z; LogAdapter::Logger::LogNumObjects<unsigned __int64>(bool,LogAdapter::LogLevel,char const * const,unsigned __int64 const &)
0x18004371f  xor     ebx, ebx
0x180043721  jmp     short loc_18004376A
0x180043723  mov     eax, [rbp+var_4C]
0x180043726  test    eax, eax
0x180043728  jz      short loc_180043739
0x18004372a  cmp     eax, 5
0x18004372d  jz      short loc_180043739
0x18004372f  cmp     eax, 9
0x180043732  mov     eax, 0C800000h
0x180043737  jmp     short loc_18004373E
0x180043739  mov     eax, 9600000h
0x18004373e  lea     rbx, [rax+rcx]
0x180043742  mov     [rbp+var_30], rbx
0x180043746  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18004374d  test    rcx, rcx
0x180043750  jz      short loc_18004376A
0x180043752  mov     r8d, edi
0x180043755  lea     rax, [rbp+var_30]
0x180043759  lea     r9, aPbrEstimatedRe_0; "pbr: Estimated reconstruction disk spac"...
0x180043760  mov     [rsp+80h+var_60], rax
0x180043765  call    ??$LogNumObjects@_K@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEB_K@Z; LogAdapter::Logger::LogNumObjects<unsigned __int64>(bool,LogAdapter::LogLevel,char const * const,unsigned __int64 const &)
0x18004376a  lea     rcx, [rbp+var_18]
0x18004376e  call    ?Close@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAXXZ; Windows::AutoComPtr<IClassFactory>::Close(void)
0x180043773  lea     rcx, [rbp+var_40]
0x180043777  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18004377c  lea     rcx, [rbp+var_48]
0x180043780  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x180043785  mov     rax, rbx
0x180043788  mov     rcx, [rbp+var_8]
0x18004378c  xor     rcx, rsp; StackCookie
0x18004378f  call    __security_check_cookie
0x180043794  add     rsp, 80h
0x18004379b  pop     r15
0x18004379d  pop     r14
0x18004379f  pop     r12
0x1800437a1  pop     rdi
0x1800437a2  pop     rsi
0x1800437a3  pop     rbx
0x1800437a4  pop     rbp
0x1800437a5  retn
```
