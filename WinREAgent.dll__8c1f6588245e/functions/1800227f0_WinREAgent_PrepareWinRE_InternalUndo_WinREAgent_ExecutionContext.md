# WinREAgent::PrepareWinRE::InternalUndo(WinREAgent::ExecutionContext *)

- ea: `0x1800227f0`
- end: `0x1800229f6`
- name: `?InternalUndo@PrepareWinRE@WinREAgent@@MEAAJPEAVExecutionContext@2@@Z`
- size: `518`
- prototype: `__int64 __fastcall(WinREAgent::PrepareWinRE *__hidden this, struct WinREAgent::ExecutionContext *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x1800227f0`
- `0x180037344`
- `0x18004a898`
- `0x18004c418`
- `0x18004d1fc`
- `0x18004d2ac`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002296d`
- `KERNEL32!GetLastError` at `0x18002296d`
- `WIMGAPI!WIMUnmountImage` at `0x180022963`
- `WIMGAPI!WIMUnmountImage` at `0x180022963`

## string_xrefs

- `0x1800228d8`: `Mount`
- `0x180022910`: `Failed to build mount path in scratch`
- `0x18002299d`: `Failed to unmount image`
- `0x180022857`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800228b4`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022924`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x1800229b1`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022843`: `Failed to build path to exported.wim`
- `0x18002285e`: `WinREAgent::PrepareWinRE::InternalUndo`
- `0x1800228bb`: `WinREAgent::PrepareWinRE::InternalUndo`
- `0x18002292b`: `WinREAgent::PrepareWinRE::InternalUndo`
- `0x1800229b8`: `WinREAgent::PrepareWinRE::InternalUndo`
- `0x1800228a0`: `Failed to delete exported.wim`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::PrepareWinRE::InternalUndo(
        WinREAgent::PrepareWinRE *this,
        struct WinREAgent::ExecutionContext *a2)
{
  int v3; // ebx
  int v5; // eax
  int v6; // esi
  __int64 v7; // rbx
  char v8; // al
  signed int LastError; // eax
  int v10; // edi
  unsigned int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v13);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v14,
    (__int64)L"exported.wim");
  v3 = PushButtonReset::Path::Combine((char *)a2 + 184, &v14, &v13);
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
  if ( v3 >= 0 )
  {
    if ( (unsigned __int8)PushButtonReset::File::Exists(&v13) )
    {
      v5 = PushButtonReset::File::Delete(&v13);
      if ( v5 < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "WinREAgent::PrepareWinRE::InternalUndo",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
          739,
          L"Failed to delete exported.wim");
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v14);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v15,
      (__int64)L"Mount");
    v6 = PushButtonReset::Path::Combine((char *)a2 + 184, &v15, &v14);
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    if ( v6 >= 0 )
    {
      v8 = PushButtonReset::Directory::Exists(&v14);
      v7 = v14;
      if ( v8 )
      {
        if ( !(unsigned int)WIMUnmountImage(v14, 0, 0, 0) )
        {
          LastError = GetLastError();
          v10 = LastError;
          if ( LastError != -1052638948 )
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            if ( LastError < 0 )
            {
              v11 = (unsigned __int16)v10 | 0x80070000;
              v12 = v11;
              if ( v10 <= 0 )
                v12 = (unsigned int)v10;
              PushButtonReset::Logging::TraceErr(
                2,
                v12,
                "WinREAgent::PrepareWinRE::InternalUndo",
                "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
                755,
                L"Failed to unmount image");
              if ( v10 <= 0 )
                v11 = v10;
              v6 = v11;
            }
          }
        }
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v6,
        "WinREAgent::PrepareWinRE::InternalUndo",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        746,
        L"Failed to build mount path in scratch");
      v7 = v14;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v7 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
    return (unsigned int)v6;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v3,
      "WinREAgent::PrepareWinRE::InternalUndo",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      732,
      L"Failed to build path to exported.wim");
    ATL::CStringData::Release((ATL::CStringData *)(v13 - 24));
    return (unsigned int)v3;
  }
}

```

## disassembly

```asm
0x1800227f0  push    rbp
0x1800227f2  push    rbx
0x1800227f3  push    rsi
0x1800227f4  push    rdi
0x1800227f5  push    r15
0x1800227f7  mov     rbp, rsp
0x1800227fa  sub     rsp, 30h
0x1800227fe  mov     rdi, rdx
0x180022801  lea     rcx, [rbp+arg_8]
0x180022805  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002280a  nop
0x18002280b  lea     rdx, aExportedWim; "exported.wim"
0x180022812  lea     rcx, [rbp+arg_10]
0x180022816  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002281b  nop
0x18002281c  lea     r8, [rbp+arg_8]
0x180022820  lea     rdx, [rbp+arg_10]
0x180022824  lea     rcx, [rdi+0B8h]
0x18002282b  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180022830  mov     ebx, eax
0x180022832  mov     rcx, [rbp+arg_10]
0x180022836  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002283a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002283f  test    ebx, ebx
0x180022841  jns     short loc_180022886
0x180022843  lea     rax, aFailedToBuildP_2; "Failed to build path to exported.wim"
0x18002284a  mov     [rsp+30h+var_8], rax
0x18002284f  mov     [rsp+30h+var_10], 2DCh
0x180022857  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002285e  lea     r8, aWinreagentPrep; "WinREAgent::PrepareWinRE::InternalUndo"
0x180022865  mov     edx, ebx
0x180022867  mov     ecx, 2
0x18002286c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022871  nop
0x180022872  mov     rcx, [rbp+arg_8]
0x180022876  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002287a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002287f  mov     eax, ebx
0x180022881  jmp     loc_1800229EB
0x180022886  lea     rcx, [rbp+arg_8]
0x18002288a  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002288f  test    al, al
0x180022891  jz      short loc_1800228CE
0x180022893  lea     rcx, [rbp+arg_8]
0x180022897  call    ?Delete@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z; PushButtonReset::File::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,int)
0x18002289c  test    eax, eax
0x18002289e  jns     short loc_1800228CE
0x1800228a0  lea     rcx, aFailedToDelete_15; "Failed to delete exported.wim"
0x1800228a7  mov     [rsp+30h+var_8], rcx
0x1800228ac  mov     [rsp+30h+var_10], 2E3h
0x1800228b4  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800228bb  lea     r8, aWinreagentPrep; "WinREAgent::PrepareWinRE::InternalUndo"
0x1800228c2  mov     edx, eax
0x1800228c4  mov     ecx, 2
0x1800228c9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800228ce  lea     rcx, [rbp+arg_10]
0x1800228d2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800228d7  nop
0x1800228d8  lea     rdx, aMount; "Mount"
0x1800228df  lea     rcx, [rbp+arg_18]
0x1800228e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800228e8  nop
0x1800228e9  lea     r8, [rbp+arg_10]
0x1800228ed  lea     rdx, [rbp+arg_18]
0x1800228f1  lea     rcx, [rdi+0B8h]
0x1800228f8  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800228fd  mov     esi, eax
0x1800228ff  mov     rcx, [rbp+arg_18]
0x180022903  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022907  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002290c  test    esi, esi
0x18002290e  jns     short loc_180022947
0x180022910  lea     rax, aFailedToBuildM; "Failed to build mount path in scratch"
0x180022917  mov     [rsp+30h+var_8], rax
0x18002291c  mov     [rsp+30h+var_10], 2EAh
0x180022924  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002292b  lea     r8, aWinreagentPrep; "WinREAgent::PrepareWinRE::InternalUndo"
0x180022932  mov     edx, esi
0x180022934  mov     ecx, 2
0x180022939  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002293e  mov     rbx, [rbp+arg_10]
0x180022942  jmp     loc_1800229D2
0x180022947  lea     rcx, [rbp+arg_10]
0x18002294b  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180022950  mov     rbx, [rbp+arg_10]
0x180022954  test    al, al
0x180022956  jz      short loc_1800229D2
0x180022958  xor     r9d, r9d
0x18002295b  xor     r8d, r8d
0x18002295e  xor     edx, edx
0x180022960  mov     rcx, rbx
0x180022963  call    cs:__imp_WIMUnmountImage
0x180022969  test    eax, eax
0x18002296b  jnz     short loc_1800229D2
0x18002296d  call    cs:__imp_GetLastError
0x180022973  mov     edi, eax
0x180022975  cmp     eax, 0C142011Ch
0x18002297a  jz      short loc_1800229D2
0x18002297c  movzx   r15d, di
0x180022980  mov     ecx, 80070000h
0x180022985  test    eax, eax
0x180022987  jle     short loc_18002298E
0x180022989  mov     eax, r15d
0x18002298c  or      eax, ecx
0x18002298e  test    eax, eax
0x180022990  jns     short loc_1800229D2
0x180022992  or      r15d, ecx
0x180022995  mov     edx, r15d
0x180022998  test    edi, edi
0x18002299a  cmovle  edx, edi
0x18002299d  lea     rax, aFailedToUnmoun_0; "Failed to unmount image"
0x1800229a4  mov     [rsp+30h+var_8], rax
0x1800229a9  mov     [rsp+30h+var_10], 2F3h
0x1800229b1  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800229b8  lea     r8, aWinreagentPrep; "WinREAgent::PrepareWinRE::InternalUndo"
0x1800229bf  mov     ecx, 2
0x1800229c4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800229c9  test    edi, edi
0x1800229cb  cmovle  r15d, edi
0x1800229cf  mov     esi, r15d
0x1800229d2  lea     rcx, [rbx-18h]; this
0x1800229d6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800229db  nop
0x1800229dc  mov     rcx, [rbp+arg_8]
0x1800229e0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800229e4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800229e9  mov     eax, esi
0x1800229eb  add     rsp, 30h
0x1800229ef  pop     r15
0x1800229f1  pop     rdi
0x1800229f2  pop     rsi
0x1800229f3  pop     rbx
0x1800229f4  pop     rbp
0x1800229f5  retn
```
