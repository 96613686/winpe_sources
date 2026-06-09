# WinREAgent::WorkDir::CleanupScratchDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18001ed24`
- end: `0x18001eec6`
- name: `?CleanupScratchDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `418`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180006de8`
- `0x18001eecc`
- `0x18001f4e0`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x18001ed24`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004c2b0`
- `0x18004d1fc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001ee19`
- `KERNEL32!GetLastError` at `0x18001ee19`
- `WIMGAPI!WIMUnmountImage` at `0x18001ee0f`
- `WIMGAPI!WIMUnmountImage` at `0x18001ee0f`

## string_xrefs

- `0x18001edac`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001ee59`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001ee95`: `base\diagnosis\srt\winreagent\lib\operations\src\workdir.cpp`
- `0x18001ed3d`: `Scratch directory [%s] doesn't exist, skip cleanup`
- `0x18001ed60`: `Mount`
- `0x18001ed98`: `Failed to build mount path in scratch`
- `0x18001edb3`: `WinREAgent::WorkDir::CleanupScratchDir`
- `0x18001ee60`: `WinREAgent::WorkDir::CleanupScratchDir`
- `0x18001ee9c`: `WinREAgent::WorkDir::CleanupScratchDir`
- `0x18001edf6`: `Find Mount folder [%s] in Scratch, unmount it`
- `0x18001ee29`: `%s is not a mount directory`
- `0x18001ee45`: `Failed to unmount image`
- `0x18001ee81`: `Failed to delete scratch dir`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::WorkDir::CleanupScratchDir(__int64 *a1)
{
  int v3; // ebx
  char v4; // al
  const WCHAR *v5; // rdx
  __int64 v6; // rbx
  signed int LastError; // eax
  int v8; // edi
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  if ( (unsigned __int8)PushButtonReset::Directory::Exists(a1) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v9);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v10,
      L"Mount");
    v3 = PushButtonReset::Path::Combine(a1, &v10, &v9);
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    if ( v3 >= 0 )
    {
      v4 = PushButtonReset::Directory::Exists(&v9);
      v6 = v9;
      if ( v4 )
      {
        PushButtonReset::Logging::Trace(0, L"Find Mount folder [%s] in Scratch, unmount it", v9);
        if ( !(unsigned int)WIMUnmountImage(v6, 0, 0, 0) )
        {
          LastError = GetLastError();
          if ( LastError == -1052638948 )
          {
            PushButtonReset::Logging::Trace(0, L"%s is not a mount directory", v6);
          }
          else
          {
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)LastError,
              "WinREAgent::WorkDir::CleanupScratchDir",
              "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
              145,
              L"Failed to unmount image");
          }
        }
      }
      v8 = PushButtonReset::Directory::Delete(a1, v5);
      if ( v8 < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v8,
          "WinREAgent::WorkDir::CleanupScratchDir",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
          151,
          L"Failed to delete scratch dir");
      ATL::CStringData::Release((ATL::CStringData *)(v6 - 24));
      return (unsigned int)v8;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v3,
        "WinREAgent::WorkDir::CleanupScratchDir",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\workdir.cpp",
        131,
        L"Failed to build mount path in scratch");
      ATL::CStringData::Release((ATL::CStringData *)(v9 - 24));
      return (unsigned int)v3;
    }
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"Scratch directory [%s] doesn't exist, skip cleanup", *a1);
    return 1;
  }
}

```

## disassembly

```asm
0x18001ed24  mov     [rsp+arg_0], rbx
0x18001ed29  push    rdi
0x18001ed2a  sub     rsp, 30h
0x18001ed2e  mov     rdi, rcx
0x18001ed31  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001ed36  test    al, al
0x18001ed38  jnz     short loc_18001ED55
0x18001ed3a  mov     r8, [rdi]
0x18001ed3d  lea     rdx, aScratchDirecto; "Scratch directory [%s] doesn't exist, s"...
0x18001ed44  xor     ecx, ecx
0x18001ed46  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001ed4b  mov     eax, 1
0x18001ed50  jmp     loc_18001EEBB
0x18001ed55  lea     rcx, [rsp+38h+arg_8]
0x18001ed5a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001ed5f  nop
0x18001ed60  lea     rdx, aMount; "Mount"
0x18001ed67  lea     rcx, [rsp+38h+arg_10]
0x18001ed6c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001ed71  nop
0x18001ed72  lea     r8, [rsp+38h+arg_8]
0x18001ed77  lea     rdx, [rsp+38h+arg_10]
0x18001ed7c  mov     rcx, rdi
0x18001ed7f  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001ed84  mov     ebx, eax
0x18001ed86  mov     rcx, [rsp+38h+arg_10]
0x18001ed8b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001ed8f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ed94  test    ebx, ebx
0x18001ed96  jns     short loc_18001EDDC
0x18001ed98  lea     rax, aFailedToBuildM; "Failed to build mount path in scratch"
0x18001ed9f  mov     [rsp+38h+var_10], rax
0x18001eda4  mov     [rsp+38h+var_18], 83h
0x18001edac  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001edb3  lea     r8, aWinreagentWork_1; "WinREAgent::WorkDir::CleanupScratchDir"
0x18001edba  mov     edx, ebx
0x18001edbc  mov     ecx, 2
0x18001edc1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001edc6  nop
0x18001edc7  mov     rcx, [rsp+38h+arg_8]
0x18001edcc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001edd0  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001edd5  mov     eax, ebx
0x18001edd7  jmp     loc_18001EEBB
0x18001eddc  lea     rcx, [rsp+38h+arg_8]
0x18001ede1  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001ede6  mov     rbx, [rsp+38h+arg_8]
0x18001edeb  test    al, al
0x18001eded  jz      loc_18001EE73
0x18001edf3  mov     r8, rbx
0x18001edf6  lea     rdx, aFindMountFolde; "Find Mount folder [%s] in Scratch, unmo"...
0x18001edfd  xor     ecx, ecx
0x18001edff  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001ee04  xor     r9d, r9d
0x18001ee07  xor     r8d, r8d
0x18001ee0a  xor     edx, edx
0x18001ee0c  mov     rcx, rbx
0x18001ee0f  call    cs:__imp_WIMUnmountImage
0x18001ee15  test    eax, eax
0x18001ee17  jnz     short loc_18001EE73
0x18001ee19  call    cs:__imp_GetLastError
0x18001ee1f  cmp     eax, 0C142011Ch
0x18001ee24  jnz     short loc_18001EE39
0x18001ee26  mov     r8, rbx
0x18001ee29  lea     rdx, aSIsNotAMountDi; "%s is not a mount directory"
0x18001ee30  xor     ecx, ecx
0x18001ee32  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001ee37  jmp     short loc_18001EE73
0x18001ee39  test    eax, eax
0x18001ee3b  jle     short loc_18001EE45
0x18001ee3d  movzx   eax, ax
0x18001ee40  or      eax, 80070000h
0x18001ee45  lea     rcx, aFailedToUnmoun_0; "Failed to unmount image"
0x18001ee4c  mov     [rsp+38h+var_10], rcx
0x18001ee51  mov     [rsp+38h+var_18], 91h
0x18001ee59  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001ee60  lea     r8, aWinreagentWork_1; "WinREAgent::WorkDir::CleanupScratchDir"
0x18001ee67  mov     edx, eax
0x18001ee69  mov     ecx, 1
0x18001ee6e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001ee73  mov     rcx, rdi
0x18001ee76  call    ?Delete@Directory@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUProgressCallback@2@@Z; PushButtonReset::Directory::Delete(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::ProgressCallback *)
0x18001ee7b  mov     edi, eax
0x18001ee7d  test    eax, eax
0x18001ee7f  jns     short loc_18001EEB0
0x18001ee81  lea     rax, aFailedToDelete_7; "Failed to delete scratch dir"
0x18001ee88  mov     [rsp+38h+var_10], rax
0x18001ee8d  mov     [rsp+38h+var_18], 97h
0x18001ee95  lea     r9, aBaseDiagnosisS_10; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18001ee9c  lea     r8, aWinreagentWork_1; "WinREAgent::WorkDir::CleanupScratchDir"
0x18001eea3  mov     edx, edi
0x18001eea5  mov     ecx, 2
0x18001eeaa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001eeaf  nop
0x18001eeb0  lea     rcx, [rbx-18h]; this
0x18001eeb4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001eeb9  mov     eax, edi
0x18001eebb  mov     rbx, [rsp+38h+arg_0]
0x18001eec0  add     rsp, 30h
0x18001eec4  pop     rdi
0x18001eec5  retn
```
