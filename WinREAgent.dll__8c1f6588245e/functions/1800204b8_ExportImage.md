# ExportImage

- ea: `0x1800204b8`
- end: `0x180020a41`
- name: `ExportImage`
- size: `1417`
- prototype: `__int64 __fastcall(__int64, __int64, struct PushButtonReset::ProgressCallback *)`
- caller_count: `1`
- callee_count: `23`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180021590`

## callees

- `0x180004978`
- `0x1800049a4`
- `0x180004af8`
- `0x180005cc0`
- `0x18000d92c`
- `0x1800204b8`
- `0x180023560`
- `0x1800235c0`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004bb04`
- `0x18004d1fc`
- `0x180053e40`
- `0x180053e6c`
- `0x180053f04`
- `0x180054244`
- `0x180054390`
- `0x18005451c`
- `0x180054658`
- `0x1800549c4`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x18002053c`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800205c8`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x18002063d`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800206bd`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800207ce`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020838`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800208b4`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020921`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800209b0`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180020528`: `Failed to build path to wimgapi log`
- `0x1800205b4`: `Failed to open image file %s`
- `0x1800205f1`: `WimTempPath`
- `0x180020629`: `Failed to build path to wim temp path`
- `0x1800206a9`: `Failed to create wim temp path %s`
- `0x18002070e`: `Wim temp path directory already exists`
- `0x1800207ba`: `Failed to open image [%u] from [%s]`
- `0x180020824`: `Failed to get compression type for [%s]`
- `0x1800208a0`: `Failed to create new WIM file %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ExportImage(__int64 a1, __int64 a2, struct PushButtonReset::ProgressCallback *a3)
{
  int Image; // ebx
  __int64 *v7; // rax
  _QWORD *v8; // rsi
  __int64 v9; // rdx
  int v10; // edi
  __int64 v11; // rbx
  __int64 v13; // rax
  PushButtonReset::WimArchive *v14; // rbx
  struct PushButtonReset::WimImage **v15; // rax
  unsigned int v16; // edx
  PushButtonReset::WimArchive *v17; // rax
  __int64 *v18; // rbx
  __int64 v19; // rax
  PushButtonReset::WimArchive *v20; // rbx
  struct PushButtonReset::WimImage *v21; // rax
  int v22; // [rsp+30h] [rbp-59h]
  __int64 v23; // [rsp+40h] [rbp-49h] BYREF
  __int64 v24; // [rsp+48h] [rbp-41h] BYREF
  __int64 v25; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v26[16]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v27; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v28[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v30[2]; // [rsp+90h] [rbp+7h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v24);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v23,
    L"SetupAct.log");
  Image = PushButtonReset::Path::Combine(a2 + 216, &v23, &v24);
  ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
  if ( Image >= 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v26,
      &v24);
    v26[8] = (int)PushButtonReset::WimLogging::Begin(v26) >= 0;
    v28[1] = 0;
    v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
    v7 = (__int64 *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v28);
    v8 = (_QWORD *)(a2 + 280);
    Image = PushButtonReset::WimArchive::Open((__int64 *)(a2 + 280), v9, v7);
    if ( Image < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Image,
        "ExportImage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        501,
        L"Failed to open image file %s",
        *v8);
LABEL_28:
      v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
      RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(v28);
      PushButtonReset::WimLogging::~WimLogging((PushButtonReset::WimLogging *)v26);
      goto LABEL_29;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v23);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v25,
      L"WimTempPath");
    Image = PushButtonReset::Path::Combine(a2 + 184, &v25, &v23);
    ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
    if ( Image < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Image,
        "ExportImage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        505,
        L"Failed to build path to wim temp path");
LABEL_27:
      ATL::CStringData::Release((ATL::CStringData *)(v23 - 24));
      goto LABEL_28;
    }
    if ( (unsigned __int8)PushButtonReset::Directory::Exists(&v23) )
    {
      PushButtonReset::Logging::Trace(0, L"Wim temp path directory already exists");
    }
    else
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v25,
        &pszFormat);
      v10 = PushButtonReset::Directory::Create(&v23, 0, &v25);
      ATL::CStringData::Release((ATL::CStringData *)(v25 - 24));
      if ( v10 < 0 )
      {
        v11 = v23;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v10,
          "ExportImage",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          510,
          L"Failed to create wim temp path %s",
          v23);
LABEL_10:
        ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
        v28[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(v28);
        PushButtonReset::WimLogging::~WimLogging((PushButtonReset::WimLogging *)v26);
        ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
        return (unsigned int)v10;
      }
    }
    v13 = (*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
    v10 = PushButtonReset::WimArchive::SetScratchPath(v13, &v23);
    if ( v10 < 0 )
    {
      v11 = v23;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v10,
        "ExportImage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        518,
        L"Failed to set WIM scratch dir to [%s]",
        v23);
      goto LABEL_10;
    }
    v29[1] = 0;
    v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable';
    v14 = (PushButtonReset::WimArchive *)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
    v15 = (struct PushButtonReset::WimImage **)(*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 8LL))(v29);
    Image = PushButtonReset::WimArchive::GetImage(v14, v16, v15);
    if ( Image >= 0 )
    {
      LODWORD(v25) = 0;
      v17 = (PushButtonReset::WimArchive *)(*(__int64 (__fastcall **)(_QWORD *))(v28[0] + 24LL))(v28);
      Image = PushButtonReset::WimArchive::GetCompressionType(
                v17,
                (enum PushButtonReset::WimArchive::Compression *)&v25);
      if ( Image >= 0 )
      {
        v30[1] = 0;
        v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
        v18 = (__int64 *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v30);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v27,
          a1);
        Image = PushButtonReset::WimArchive::Create(&v27, v25, v18);
        ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
        if ( Image >= 0 )
        {
          v19 = (*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
          v10 = PushButtonReset::WimArchive::SetScratchPath(v19, &v23);
          if ( v10 < 0 )
          {
            v11 = v23;
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v10,
              "ExportImage",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              533,
              L"Failed to set WIM scratch dir to [%s]",
              v23);
            v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(v30);
            v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable';
            RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::Release(v29);
            goto LABEL_10;
          }
          v20 = (PushButtonReset::WimArchive *)(*(__int64 (__fastcall **)(_QWORD *))(v30[0] + 24LL))(v30);
          v21 = (struct PushButtonReset::WimImage *)(*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 32LL))(v29);
          Image = PushButtonReset::WimArchive::ImportImage(v20, v21, a3);
          if ( Image < 0 )
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Image,
              "ExportImage",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
              536,
              L"Failed to export image");
          v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
          RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(v30);
          v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable';
LABEL_26:
          RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::Release(v29);
          goto LABEL_27;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Image,
          "ExportImage",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          530,
          L"Failed to create new WIM file %s",
          a1);
        v30[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable';
        RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(v30);
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Image,
          "ExportImage",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          526,
          L"Failed to get compression type for [%s]",
          *v8);
      }
    }
    else
    {
      v22 = 1;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Image,
        "ExportImage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        522,
        L"Failed to open image [%u] from [%s]",
        v22,
        *v8);
    }
    v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable';
    goto LABEL_26;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Image,
    "ExportImage",
    "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
    495,
    L"Failed to build path to wimgapi log");
LABEL_29:
  ATL::CStringData::Release((ATL::CStringData *)(v24 - 24));
  return (unsigned int)Image;
}

```

## disassembly

```asm
0x1800204b8  push    rbp
0x1800204ba  push    rbx
0x1800204bb  push    rsi
0x1800204bc  push    rdi
0x1800204bd  push    r13
0x1800204bf  push    r14
0x1800204c1  push    r15
0x1800204c3  lea     rbp, [rsp-27h]
0x1800204c8  sub     rsp, 0B0h
0x1800204cf  mov     rax, cs:__security_cookie
0x1800204d6  xor     rax, rsp
0x1800204d9  mov     [rbp+57h+var_40], rax
0x1800204dd  mov     r15, r8
0x1800204e0  mov     rdi, rdx
0x1800204e3  mov     r14, rcx
0x1800204e6  lea     rcx, [rbp+57h+var_98]
0x1800204ea  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800204ef  nop
0x1800204f0  lea     rdx, aSetupactLog_0; "SetupAct.log"
0x1800204f7  lea     rcx, [rbp+57h+var_A0]
0x1800204fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180020500  nop
0x180020501  lea     rcx, [rdi+0D8h]
0x180020508  lea     r8, [rbp+57h+var_98]
0x18002050c  lea     rdx, [rbp+57h+var_A0]
0x180020510  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180020515  mov     ebx, eax
0x180020517  mov     rcx, [rbp+57h+var_A0]
0x18002051b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002051f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020524  test    ebx, ebx
0x180020526  jns     short loc_18002055B
0x180020528  lea     rax, aFailedToBuildP_0; "Failed to build path to wimgapi log"
0x18002052f  mov     [rsp+0E0h+var_B8], rax
0x180020534  mov     [rsp+0E0h+var_C0], 1EFh
0x18002053c  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020543  lea     r8, aExportimage; "ExportImage"
0x18002054a  mov     edx, ebx
0x18002054c  mov     ecx, 2
0x180020551  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020556  jmp     loc_180020A14
0x18002055b  lea     rdx, [rbp+57h+var_98]
0x18002055f  lea     rcx, [rbp+57h+var_88]
0x180020563  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180020568  nop
0x180020569  lea     rcx, [rbp+57h+var_88]
0x18002056d  call    ?Begin@WimLogging@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WimLogging::Begin(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180020572  test    eax, eax
0x180020574  setns   [rbp+57h+var_80]
0x180020578  mov     [rbp+57h+var_68], 0
0x180020580  lea     r13, ??_7?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::`vftable'
0x180020587  mov     [rbp+57h+var_70], r13
0x18002058b  lea     rcx, [rbp+57h+var_70]
0x18002058f  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020594  lea     rsi, [rdi+118h]
0x18002059b  mov     r8, rax
0x18002059e  mov     rcx, rsi
0x1800205a1  call    ?Open@WimArchive@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4Access@12@PEAPEAV12@@Z; PushButtonReset::WimArchive::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WimArchive::Access,PushButtonReset::WimArchive * *)
0x1800205a6  mov     ebx, eax
0x1800205a8  test    eax, eax
0x1800205aa  jns     short loc_1800205E7
0x1800205ac  mov     rcx, [rsi]
0x1800205af  mov     [rsp+0E0h+var_B0], rcx
0x1800205b4  lea     rax, aFailedToOpenIm; "Failed to open image file %s"
0x1800205bb  mov     [rsp+0E0h+var_B8], rax
0x1800205c0  mov     [rsp+0E0h+var_C0], 1F5h
0x1800205c8  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800205cf  lea     r8, aExportimage; "ExportImage"
0x1800205d6  mov     edx, ebx
0x1800205d8  mov     ecx, 2
0x1800205dd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800205e2  jmp     loc_1800209FC
0x1800205e7  lea     rcx, [rbp+57h+var_A0]
0x1800205eb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800205f0  nop
0x1800205f1  lea     rdx, aWimtemppath; "WimTempPath"
0x1800205f8  lea     rcx, [rbp+57h+var_90]
0x1800205fc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180020601  nop
0x180020602  lea     rcx, [rdi+0B8h]
0x180020609  lea     r8, [rbp+57h+var_A0]
0x18002060d  lea     rdx, [rbp+57h+var_90]
0x180020611  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180020616  mov     ebx, eax
0x180020618  mov     rcx, [rbp+57h+var_90]
0x18002061c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020620  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020625  test    ebx, ebx
0x180020627  jns     short loc_18002065C
0x180020629  lea     rax, aFailedToBuildP_3; "Failed to build path to wim temp path"
0x180020630  mov     [rsp+0E0h+var_B8], rax
0x180020635  mov     [rsp+0E0h+var_C0], 1F9h
0x18002063d  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020644  lea     r8, aExportimage; "ExportImage"
0x18002064b  mov     edx, ebx
0x18002064d  mov     ecx, 2
0x180020652  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020657  jmp     loc_1800209EE
0x18002065c  lea     rcx, [rbp+57h+var_A0]
0x180020660  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180020665  test    al, al
0x180020667  jnz     loc_18002070E
0x18002066d  lea     rdx, pszFormat
0x180020674  lea     rcx, [rbp+57h+var_90]
0x180020678  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002067d  nop
0x18002067e  lea     r8, [rbp+57h+var_90]
0x180020682  xor     edx, edx
0x180020684  lea     rcx, [rbp+57h+var_A0]
0x180020688  call    ?Create@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N0@Z; PushButtonReset::Directory::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002068d  mov     edi, eax
0x18002068f  mov     rcx, [rbp+57h+var_90]
0x180020693  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020697  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002069c  test    edi, edi
0x18002069e  jns     short loc_18002071C
0x1800206a0  mov     rbx, [rbp+57h+var_A0]
0x1800206a4  mov     [rsp+0E0h+var_B0], rbx
0x1800206a9  lea     rax, aFailedToCreate_25; "Failed to create wim temp path %s"
0x1800206b0  mov     [rsp+0E0h+var_B8], rax
0x1800206b5  mov     [rsp+0E0h+var_C0], 1FEh
0x1800206bd  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800206c4  lea     r8, aExportimage; "ExportImage"
0x1800206cb  mov     edx, edi
0x1800206cd  mov     ecx, 2
0x1800206d2  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800206d7  nop
0x1800206d8  lea     rcx, [rbx-18h]; this
0x1800206dc  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800206e1  nop
0x1800206e2  mov     [rbp+57h+var_70], r13
0x1800206e6  lea     rcx, [rbp+57h+var_70]
0x1800206ea  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x1800206ef  nop
0x1800206f0  lea     rcx, [rbp+57h+var_88]; this
0x1800206f4  call    ??1WimLogging@PushButtonReset@@QEAA@XZ; PushButtonReset::WimLogging::~WimLogging(void)
0x1800206f9  nop
0x1800206fa  mov     rcx, [rbp+57h+var_98]
0x1800206fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020702  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020707  mov     eax, edi
0x180020709  jmp     loc_180020A23
0x18002070e  lea     rdx, aWimTempPathDir; "Wim temp path directory already exists"
0x180020715  xor     ecx, ecx
0x180020717  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002071c  mov     rax, [rbp+57h+var_70]
0x180020720  lea     rcx, [rbp+57h+var_70]
0x180020724  mov     rax, [rax+18h]
0x180020728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002072d  lea     rdx, [rbp+57h+var_A0]
0x180020731  mov     rcx, rax
0x180020734  call    ?SetScratchPath@WimArchive@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WimArchive::SetScratchPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180020739  mov     edi, eax
0x18002073b  test    eax, eax
0x18002073d  jns     short loc_180020761
0x18002073f  mov     rbx, [rbp+57h+var_A0]
0x180020743  mov     [rsp+0E0h+var_B0], rbx
0x180020748  lea     rax, aFailedToSetWim; "Failed to set WIM scratch dir to [%s]"
0x18002074f  mov     [rsp+0E0h+var_B8], rax
0x180020754  mov     [rsp+0E0h+var_C0], 206h
0x18002075c  jmp     loc_1800206BD
0x180020761  mov     [rbp+57h+var_58], 0
0x180020769  lea     rdi, ??_7?$CAutoPbrDelete@PEAVWimImage@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable'
0x180020770  mov     [rbp+57h+var_60], rdi
0x180020774  mov     rax, [rbp+57h+var_70]
0x180020778  lea     rcx, [rbp+57h+var_70]
0x18002077c  mov     rax, [rax+18h]
0x180020780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020785  mov     rbx, rax
0x180020788  mov     rcx, [rbp+57h+var_60]
0x18002078c  mov     rax, [rcx+8]
0x180020790  lea     rcx, [rbp+57h+var_60]
0x180020794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020799  mov     r8, rax; struct PushButtonReset::WimImage **
0x18002079c  mov     rcx, rbx; this
0x18002079f  call    ?GetImage@WimArchive@PushButtonReset@@QEAAJKPEAPEAVWimImage@2@@Z; PushButtonReset::WimArchive::GetImage(ulong,PushButtonReset::WimImage * *)
0x1800207a4  mov     ebx, eax
0x1800207a6  test    eax, eax
0x1800207a8  jns     short loc_1800207F2
0x1800207aa  mov     rcx, [rsi]
0x1800207ad  mov     [rsp+0E0h+var_A8], rcx
0x1800207b2  mov     dword ptr [rsp+0E0h+var_B0], 1
0x1800207ba  lea     rax, aFailedToOpenIm_0; "Failed to open image [%u] from [%s]"
0x1800207c1  mov     [rsp+0E0h+var_B8], rax
0x1800207c6  mov     [rsp+0E0h+var_C0], 20Ah
0x1800207ce  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800207d5  lea     r8, aExportimage; "ExportImage"
0x1800207dc  mov     edx, ebx
0x1800207de  mov     ecx, 2
0x1800207e3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800207e8  nop
0x1800207e9  mov     [rbp+57h+var_60], rdi
0x1800207ed  jmp     loc_1800209E4
0x1800207f2  mov     dword ptr [rbp+57h+var_90], 0
0x1800207f9  mov     rax, [rbp+57h+var_70]
0x1800207fd  lea     rcx, [rbp+57h+var_70]
0x180020801  mov     rax, [rax+18h]
0x180020805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002080a  lea     rdx, [rbp+57h+var_90]; enum PushButtonReset::WimArchive::Compression *
0x18002080e  mov     rcx, rax; this
0x180020811  call    ?GetCompressionType@WimArchive@PushButtonReset@@QEAAJAEAW4Compression@12@@Z; PushButtonReset::WimArchive::GetCompressionType(PushButtonReset::WimArchive::Compression &)
0x180020816  mov     ebx, eax
0x180020818  test    eax, eax
0x18002081a  jns     short loc_180020854
0x18002081c  mov     rcx, [rsi]
0x18002081f  mov     [rsp+0E0h+var_B0], rcx
0x180020824  lea     rax, aFailedToGetCom; "Failed to get compression type for [%s]"
0x18002082b  mov     [rsp+0E0h+var_B8], rax
0x180020830  mov     [rsp+0E0h+var_C0], 20Eh
0x180020838  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002083f  lea     r8, aExportimage; "ExportImage"
0x180020846  mov     edx, ebx
0x180020848  mov     ecx, 2
0x18002084d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180020852  jmp     short loc_1800207E9
0x180020854  mov     [rbp+57h+var_48], 0
0x18002085c  mov     [rbp+57h+var_50], r13
0x180020860  lea     rcx, [rbp+57h+var_50]
0x180020864  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180020869  mov     rbx, rax
0x18002086c  mov     rdx, r14
0x18002086f  lea     rcx, [rbp+57h+var_78]
0x180020873  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180020878  nop
0x180020879  mov     r8, rbx
0x18002087c  mov     edx, dword ptr [rbp+57h+var_90]
0x18002087f  lea     rcx, [rbp+57h+var_78]
0x180020883  call    ?Create@WimArchive@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@W4Compression@12@PEAPEAV12@@Z; PushButtonReset::WimArchive::Create(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WimArchive::Compression,PushButtonReset::WimArchive * *)
0x180020888  mov     ebx, eax
0x18002088a  mov     rcx, [rbp+57h+var_78]
0x18002088e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020892  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020897  test    ebx, ebx
0x180020899  jns     short loc_1800208E1
0x18002089b  mov     [rsp+0E0h+var_B0], r14
0x1800208a0  lea     rax, aFailedToCreate_28; "Failed to create new WIM file %s"
0x1800208a7  mov     [rsp+0E0h+var_B8], rax
0x1800208ac  mov     [rsp+0E0h+var_C0], 212h
0x1800208b4  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800208bb  lea     r8, aExportimage; "ExportImage"
0x1800208c2  mov     edx, ebx
0x1800208c4  mov     ecx, 2
0x1800208c9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800208ce  nop
0x1800208cf  mov     [rbp+57h+var_50], r13
0x1800208d3  lea     rcx, [rbp+57h+var_50]
0x1800208d7  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x1800208dc  jmp     loc_1800207E9
0x1800208e1  mov     rax, [rbp+57h+var_50]
0x1800208e5  lea     rcx, [rbp+57h+var_50]
0x1800208e9  mov     rax, [rax+18h]
0x1800208ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800208f2  lea     rdx, [rbp+57h+var_A0]
0x1800208f6  mov     rcx, rax
0x1800208f9  call    ?SetScratchPath@WimArchive@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::WimArchive::SetScratchPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800208fe  mov     edi, eax
0x180020900  test    eax, eax
0x180020902  jns     short loc_180020963
0x180020904  mov     rbx, [rbp+57h+var_A0]
0x180020908  mov     [rsp+0E0h+var_B0], rbx
0x18002090d  lea     rax, aFailedToSetWim; "Failed to set WIM scratch dir to [%s]"
0x180020914  mov     [rsp+0E0h+var_B8], rax
0x180020919  mov     [rsp+0E0h+var_C0], 215h
0x180020921  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180020928  lea     r8, aExportimage; "ExportImage"
0x18002092f  mov     edx, edi
0x180020931  mov     ecx, 2
0x180020936  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002093b  nop
0x18002093c  mov     [rbp+57h+var_50], r13
0x180020940  lea     rcx, [rbp+57h+var_50]
0x180020944  call    ?Release@?$CAutoPbrDelete@PEAVWimArchive@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimArchive *>::Release(void)
0x180020949  nop
0x18002094a  lea     rax, ??_7?$CAutoPbrDelete@PEAVWimImage@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::`vftable'
0x180020951  mov     [rbp+57h+var_60], rax
0x180020955  lea     rcx, [rbp+57h+var_60]
0x180020959  call    ?Release@?$CAutoPbrDelete@PEAVWimImage@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::WimImage *>::Release(void)
0x18002095e  jmp     loc_1800206D8
0x180020963  mov     rax, [rbp+57h+var_50]
0x180020967  lea     rcx, [rbp+57h+var_50]
0x18002096b  mov     rax, [rax+18h]
0x18002096f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020974  mov     rbx, rax
0x180020977  mov     rcx, [rbp+57h+var_60]
0x18002097b  mov     rax, [rcx+20h]
0x18002097f  lea     rcx, [rbp+57h+var_60]
0x180020983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020988  mov     r8, r15; struct PushButtonReset::ProgressCallback *
0x18002098b  mov     rdx, rax; struct PushButtonReset::WimImage *
0x18002098e  mov     rcx, rbx; this
0x180020991  call    ?ImportImage@WimArchive@PushButtonReset@@QEAAJPEAVWimImage@2@PEAUProgressCallback@2@@Z; PushButtonReset::WimArchive::ImportImage(PushButtonReset::WimImage *,PushButtonReset::ProgressCallback *)
0x180020996  mov     ebx, eax
0x180020998  test    eax, eax
0x18002099a  jns     short loc_1800209CB
0x18002099c  lea     rax, aFailedToExport; "Failed to export image"
0x1800209a3  mov     [rsp+0E0h+var_B8], rax
0x1800209a8  mov     [rsp+0E0h+var_C0], 218h
0x1800209b0  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800209b7  lea     r8, aExportimage; "ExportImage"
0x1800209be  mov     edx, ebx
  ... truncated ...
```
