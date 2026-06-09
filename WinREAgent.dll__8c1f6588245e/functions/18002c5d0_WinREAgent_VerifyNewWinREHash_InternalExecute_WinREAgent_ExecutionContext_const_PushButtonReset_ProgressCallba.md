# WinREAgent::VerifyNewWinREHash::InternalExecute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *)

- ea: `0x18002c5d0`
- end: `0x18002c7ff`
- name: `?InternalExecute@VerifyNewWinREHash@WinREAgent@@MEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@@Z`
- size: `559`
- prototype: `__int64 __fastcall(WinREAgent::VerifyNewWinREHash *__hidden this, const struct WinREAgent::ExecutionContext *, struct PushButtonReset::ProgressCallback *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000d92c`
- `0x18002c44c`
- `0x18002c5d0`
- `0x1800304dc`
- `0x1800307e0`
- `0x18003717c`
- `0x180037344`

## string_xrefs

- `0x18002c5fa`: `BackupWimPath`
- `0x18002c6d3`: `BackupWimPath`
- `0x18002c67e`: `base\diagnosis\srt\winreagent\lib\operations\src\verifynewwinrehash.cpp`
- `0x18002c735`: `base\diagnosis\srt\winreagent\lib\operations\src\verifynewwinrehash.cpp`
- `0x18002c7a8`: `base\diagnosis\srt\winreagent\lib\operations\src\verifynewwinrehash.cpp`
- `0x18002c66a`: `Failed to generate hash of update WinRE`
- `0x18002c685`: `WinREAgent::VerifyNewWinREHash::InternalExecute`
- `0x18002c73c`: `WinREAgent::VerifyNewWinREHash::InternalExecute`
- `0x18002c7af`: `WinREAgent::VerifyNewWinREHash::InternalExecute`
- `0x18002c721`: `Failed to read saved new WinRE hash`
- `0x18002c754`: `VerifyNewWinREHash: Current update Wim hash [%s]`
- `0x18002c765`: `VerifyNewWinREHash: Saved update Wim hash   [%s]`
- `0x18002c794`: `Update WinRE hash didn't match`
- `0x18002c7e1`: `VerifyNewWinREHash: There is no saved hash of updated WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::VerifyNewWinREHash::InternalExecute(
        WinREAgent::VerifyNewWinREHash *this,
        const struct WinREAgent::ExecutionContext *a2,
        struct PushButtonReset::ProgressCallback *a3)
{
  __int64 v4; // rbx
  int v5; // ebx
  __int64 v7; // rbx
  int Key; // esi
  unsigned __int16 *v9; // rbx
  __int64 v10; // rdi
  unsigned __int16 *v11; // rax
  int v12; // edx
  int v13; // ecx
  __int64 v14; // [rsp+30h] [rbp-10h] BYREF
  __int64 v15; // [rsp+38h] [rbp-8h] BYREF
  unsigned __int16 *v16; // [rsp+68h] [rbp+28h] BYREF
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF

  v4 = *((_QWORD *)a2 + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"NewWinREHash");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v16,
    (__int64)L"BackupWimPath");
  LOBYTE(v4) = WinREAgent::RollbackHelper::HasKey(v4, &v16, &v17);
  ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  if ( (_BYTE)v4 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v16);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v17);
    v5 = GenerateEncodedHash_1((char *)a2 + 280, &v16);
    if ( v5 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v5,
        "WinREAgent::VerifyNewWinREHash::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\verifynewwinrehash.cpp",
        58,
        L"Failed to generate hash of update WinRE");
      ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
      ATL::CStringData::Release((ATL::CStringData *)(v16 - 12));
      return (unsigned int)v5;
    }
    v7 = *((_QWORD *)a2 + 56);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v15,
      (__int64)L"NewWinREHash");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v14,
      (__int64)L"BackupWimPath");
    Key = WinREAgent::RollbackHelper::GetKey(v7, &v14, &v15, &v17);
    ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
    v9 = v16;
    v10 = v17;
    if ( Key >= 0 )
    {
      PushButtonReset::Logging::Trace(0, L"VerifyNewWinREHash: Current update Wim hash [%s]", v16);
      PushButtonReset::Logging::Trace(0, L"VerifyNewWinREHash: Saved update Wim hash   [%s]", v10);
      v11 = v9;
      do
      {
        v12 = *(unsigned __int16 *)((char *)v11 + v10 - (_QWORD)v9);
        v13 = *v11 - v12;
        if ( v13 )
          break;
        ++v11;
      }
      while ( v12 );
      if ( v13 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942977LL,
          "WinREAgent::VerifyNewWinREHash::InternalExecute",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\verifynewwinrehash.cpp",
          69,
          L"Update WinRE hash didn't match");
        Key = -2147024319;
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Key,
        "WinREAgent::VerifyNewWinREHash::InternalExecute",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\verifynewwinrehash.cpp",
        63,
        L"Failed to read saved new WinRE hash");
    }
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v9 - 12));
  }
  else
  {
    Key = 0;
    PushButtonReset::Logging::Trace(1, L"VerifyNewWinREHash: There is no saved hash of updated WinRE");
  }
  return (unsigned int)Key;
}

```

## disassembly

```asm
0x18002c5d0  mov     [rsp-18h+arg_0], rbx
0x18002c5d5  push    rbp
0x18002c5d6  push    rsi
0x18002c5d7  push    rdi
0x18002c5d8  mov     rbp, rsp
0x18002c5db  sub     rsp, 40h
0x18002c5df  mov     rdi, rdx
0x18002c5e2  mov     rbx, [rdx+1C0h]
0x18002c5e9  lea     rdx, aNewwinrehash; "NewWinREHash"
0x18002c5f0  lea     rcx, [rbp+arg_18]
0x18002c5f4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002c5f9  nop
0x18002c5fa  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002c601  lea     rcx, [rbp+arg_8]
0x18002c605  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002c60a  nop
0x18002c60b  lea     r8, [rbp+arg_18]
0x18002c60f  lea     rdx, [rbp+arg_8]
0x18002c613  mov     rcx, rbx
0x18002c616  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002c61b  mov     bl, al
0x18002c61d  mov     rcx, [rbp+arg_8]
0x18002c621  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c625  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c62a  nop
0x18002c62b  mov     rcx, [rbp+arg_18]
0x18002c62f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c633  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c638  test    bl, bl
0x18002c63a  jz      loc_18002C7DF
0x18002c640  lea     rcx, [rbp+arg_8]
0x18002c644  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002c649  nop
0x18002c64a  lea     rcx, [rbp+arg_18]
0x18002c64e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18002c653  nop
0x18002c654  lea     rcx, [rdi+118h]
0x18002c65b  lea     rdx, [rbp+arg_8]
0x18002c65f  call    GenerateEncodedHash_1
0x18002c664  mov     ebx, eax
0x18002c666  test    eax, eax
0x18002c668  jns     short loc_18002C6BB
0x18002c66a  lea     rax, aFailedToGenera_1; "Failed to generate hash of update WinRE"
0x18002c671  mov     [rsp+40h+var_18], rax
0x18002c676  mov     [rsp+40h+var_20], 3Ah ; ':'
0x18002c67e  lea     r9, aBaseDiagnosisS_20; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c685  lea     r8, aWinreagentVeri; "WinREAgent::VerifyNewWinREHash::Interna"...
0x18002c68c  mov     edx, ebx
0x18002c68e  mov     ecx, 2
0x18002c693  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c698  nop
0x18002c699  mov     rcx, [rbp+arg_18]
0x18002c69d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c6a1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c6a6  nop
0x18002c6a7  mov     rcx, [rbp+arg_8]
0x18002c6ab  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c6af  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c6b4  mov     eax, ebx
0x18002c6b6  jmp     loc_18002C7F2
0x18002c6bb  mov     rbx, [rdi+1C0h]
0x18002c6c2  lea     rdx, aNewwinrehash; "NewWinREHash"
0x18002c6c9  lea     rcx, [rbp+var_8]
0x18002c6cd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002c6d2  nop
0x18002c6d3  lea     rdx, aBackupwimpath; "BackupWimPath"
0x18002c6da  lea     rcx, [rbp+var_10]
0x18002c6de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002c6e3  nop
0x18002c6e4  lea     r9, [rbp+arg_18]
0x18002c6e8  lea     r8, [rbp+var_8]
0x18002c6ec  lea     rdx, [rbp+var_10]
0x18002c6f0  mov     rcx, rbx
0x18002c6f3  call    ?GetKey@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; WinREAgent::RollbackHelper::GetKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18002c6f8  mov     esi, eax
0x18002c6fa  mov     rcx, [rbp+var_10]
0x18002c6fe  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c702  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c707  nop
0x18002c708  mov     rcx, [rbp+var_8]
0x18002c70c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002c710  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c715  mov     rbx, [rbp+arg_8]
0x18002c719  mov     rdi, [rbp+arg_18]
0x18002c71d  test    esi, esi
0x18002c71f  jns     short loc_18002C751
0x18002c721  lea     rax, aFailedToReadSa; "Failed to read saved new WinRE hash"
0x18002c728  mov     [rsp+40h+var_18], rax
0x18002c72d  mov     [rsp+40h+var_20], 3Fh ; '?'
0x18002c735  lea     r9, aBaseDiagnosisS_20; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c73c  lea     r8, aWinreagentVeri; "WinREAgent::VerifyNewWinREHash::Interna"...
0x18002c743  mov     edx, esi
0x18002c745  mov     ecx, 2
0x18002c74a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c74f  jmp     short loc_18002C7CA
0x18002c751  mov     r8, rbx
0x18002c754  lea     rdx, aVerifynewwinre; "VerifyNewWinREHash: Current update Wim "...
0x18002c75b  xor     ecx, ecx
0x18002c75d  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c762  mov     r8, rdi
0x18002c765  lea     rdx, aVerifynewwinre_0; "VerifyNewWinREHash: Saved update Wim ha"...
0x18002c76c  xor     ecx, ecx
0x18002c76e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c773  mov     rax, rbx
0x18002c776  mov     r8, rdi
0x18002c779  sub     r8, rbx
0x18002c77c  movzx   ecx, word ptr [rax]
0x18002c77f  movzx   edx, word ptr [rax+r8]
0x18002c784  sub     ecx, edx
0x18002c786  jnz     short loc_18002C790
0x18002c788  add     rax, 2
0x18002c78c  test    edx, edx
0x18002c78e  jnz     short loc_18002C77C
0x18002c790  test    ecx, ecx
0x18002c792  jz      short loc_18002C7CA
0x18002c794  lea     rax, aUpdateWinreHas_0; "Update WinRE hash didn't match"
0x18002c79b  mov     [rsp+40h+var_18], rax
0x18002c7a0  mov     [rsp+40h+var_20], 45h ; 'E'
0x18002c7a8  lea     r9, aBaseDiagnosisS_20; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002c7af  lea     r8, aWinreagentVeri; "WinREAgent::VerifyNewWinREHash::Interna"...
0x18002c7b6  mov     edx, 80070241h
0x18002c7bb  mov     ecx, 2
0x18002c7c0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002c7c5  mov     esi, 80070241h
0x18002c7ca  lea     rcx, [rdi-18h]; this
0x18002c7ce  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c7d3  nop
0x18002c7d4  lea     rcx, [rbx-18h]; this
0x18002c7d8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002c7dd  jmp     short loc_18002C7F0
0x18002c7df  xor     esi, esi
0x18002c7e1  lea     rdx, aVerifynewwinre_1; "VerifyNewWinREHash: There is no saved h"...
0x18002c7e8  lea     ecx, [rsi+1]
0x18002c7eb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002c7f0  mov     eax, esi
0x18002c7f2  mov     rbx, [rsp+40h+arg_0]
0x18002c7f7  add     rsp, 40h
0x18002c7fb  pop     rdi
0x18002c7fc  pop     rsi
0x18002c7fd  pop     rbp
0x18002c7fe  retn
```
