# WinREAgent::WinREIsKnownWinREFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool *,bool)

- ea: `0x180034480`
- end: `0x1800345b8`
- name: `?WinREIsKnownWinREFile@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N_N@Z`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180024890`
- `0x1800346cc`

## callees

- `0x180004af8`
- `0x18000d92c`
- `0x180034480`
- `0x180037344`
- `0x18004e7f8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003454b`
- `msvcrt!_wcsicmp` at `0x180034570`
- `msvcrt!_wcsicmp` at `0x18003454b`
- `msvcrt!_wcsicmp` at `0x180034570`

## string_xrefs

- `0x1800344b4`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x180034518`: `base\diagnosis\srt\winreagent\lib\api\src\enumeration.cpp`
- `0x1800344bb`: `WinREAgent::WinREIsKnownWinREFile`
- `0x18003451f`: `WinREAgent::WinREIsKnownWinREFile`
- `0x180034504`: `Failed to get volume relative path of [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WinREAgent::WinREIsKnownWinREFile(LPCWSTR *a1, _BYTE *a2, char a3)
{
  signed int VolumeRelPath; // edi
  wchar_t *v8; // rbx
  unsigned __int64 i; // rdi
  __int64 v10; // rdi
  wchar_t *String1; // [rsp+68h] [rbp+10h] BYREF

  if ( a2 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&String1);
    VolumeRelPath = PushButtonReset::Path::GetVolumeRelPath(a1, &String1);
    v8 = String1;
    if ( VolumeRelPath >= 0 )
    {
      *a2 = 0;
      for ( i = 0; i < 6; ++i )
      {
        if ( !_wcsicmp(v8, off_180073C80[i]) )
        {
          *a2 = 1;
LABEL_17:
          ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
          return 0;
        }
      }
      if ( !a3 )
      {
        v10 = 0;
        while ( _wcsicmp(v8, off_180073C70[v10]) )
        {
          if ( (unsigned __int64)++v10 >= 2 )
            goto LABEL_17;
        }
        *a2 = 1;
      }
      VolumeRelPath = 0;
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)VolumeRelPath,
        "WinREAgent::WinREIsKnownWinREFile",
        "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
        152,
        L"Failed to get volume relative path of [%s]",
        *a1);
    }
    ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
    return (unsigned int)VolumeRelPath;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::WinREIsKnownWinREFile",
      "base\\diagnosis\\srt\\winreagent\\lib\\api\\src\\enumeration.cpp",
      134,
      L"res cannot be null");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180034480  mov     [rsp+arg_0], rbx
0x180034485  mov     [rsp+arg_10], rbp
0x18003448a  push    rsi
0x18003448b  push    rdi
0x18003448c  push    r14
0x18003448e  sub     rsp, 40h
0x180034492  mov     bpl, r8b
0x180034495  mov     rsi, rdx
0x180034498  mov     r14, rcx
0x18003449b  test    rdx, rdx
0x18003449e  jnz     short loc_1800344D9
0x1800344a0  lea     rax, aResCannotBeNul; "res cannot be null"
0x1800344a7  mov     [rsp+58h+var_30], rax
0x1800344ac  mov     [rsp+58h+var_38], 86h
0x1800344b4  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800344bb  lea     r8, aWinreagentWinr_8; "WinREAgent::WinREIsKnownWinREFile"
0x1800344c2  mov     edx, 80070057h
0x1800344c7  lea     ecx, [rsi+2]
0x1800344ca  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800344cf  mov     eax, 80070057h
0x1800344d4  jmp     loc_1800345A5
0x1800344d9  lea     rcx, [rsp+58h+String1]
0x1800344de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800344e3  nop
0x1800344e4  lea     rdx, [rsp+58h+String1]
0x1800344e9  mov     rcx, r14
0x1800344ec  call    ?GetVolumeRelPath@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetVolumeRelPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800344f1  mov     edi, eax
0x1800344f3  mov     rbx, [rsp+58h+String1]
0x1800344f8  test    eax, eax
0x1800344fa  jns     short loc_180034534
0x1800344fc  mov     rcx, [r14]
0x1800344ff  mov     [rsp+58h+var_28], rcx
0x180034504  lea     rax, aFailedToGetVol_6; "Failed to get volume relative path of ["...
0x18003450b  mov     [rsp+58h+var_30], rax
0x180034510  mov     [rsp+58h+var_38], 98h
0x180034518  lea     r9, aBaseDiagnosisS_21; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18003451f  lea     r8, aWinreagentWinr_8; "WinREAgent::WinREIsKnownWinREFile"
0x180034526  mov     edx, edi
0x180034528  mov     ecx, 2
0x18003452d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180034532  jmp     short loc_18003458A
0x180034534  mov     byte ptr [rsi], 0
0x180034537  xor     edi, edi
0x180034539  lea     r14, __ImageBase
0x180034540  mov     rdx, ds:rva off_180073C80[r14+rdi*8]; String2
0x180034548  mov     rcx, rbx; String1
0x18003454b  call    cs:__imp__wcsicmp
0x180034551  test    eax, eax
0x180034553  jz      short loc_180034597
0x180034555  inc     rdi
0x180034558  cmp     rdi, 6
0x18003455c  jb      short loc_180034540
0x18003455e  test    bpl, bpl
0x180034561  jnz     short loc_180034588
0x180034563  xor     edi, edi
0x180034565  mov     rdx, ds:rva off_180073C70[r14+rdi*8]; String2
0x18003456d  mov     rcx, rbx; String1
0x180034570  call    cs:__imp__wcsicmp
0x180034576  test    eax, eax
0x180034578  jz      short loc_180034585
0x18003457a  inc     rdi
0x18003457d  cmp     rdi, 2
0x180034581  jb      short loc_180034565
0x180034583  jmp     short loc_18003459A
0x180034585  mov     byte ptr [rsi], 1
0x180034588  xor     edi, edi
0x18003458a  lea     rcx, [rbx-18h]; this
0x18003458e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180034593  mov     eax, edi
0x180034595  jmp     short loc_1800345A5
0x180034597  mov     byte ptr [rsi], 1
0x18003459a  lea     rcx, [rbx-18h]; this
0x18003459e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800345a3  xor     eax, eax
0x1800345a5  mov     rbx, [rsp+58h+arg_0]
0x1800345aa  mov     rbp, [rsp+58h+arg_10]
0x1800345af  add     rsp, 40h
0x1800345b3  pop     r14
0x1800345b5  pop     rdi
0x1800345b6  pop     rsi
0x1800345b7  retn
```
