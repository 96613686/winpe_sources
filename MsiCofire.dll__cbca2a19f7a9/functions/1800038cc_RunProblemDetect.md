# RunProblemDetect

- ea: `0x1800038cc`
- end: `0x180003ac2`
- name: `RunProblemDetect`
- size: `502`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002770`

## callees

- `0x180002590`
- `0x180002a88`
- `0x1800032a8`
- `0x1800033f4`
- `0x1800038cc`
- `0x18000465c`
- `0x180004f1c`
- `0x180005784`
- `0x180005b1c`
- `0x180005b78`
- `0x180005bd4`
- `0x180006530`

## import_xrefs

- `wdi!WdiSetFeedback` at `0x180003a0f`
- `wdi!WdiSetFeedback` at `0x180003a0f`
- `wdi!WdiSetProblemDetectionResult` at `0x1800039fa`
- `wdi!WdiSetProblemDetectionResult` at `0x180003a8b`
- `wdi!WdiSetProblemDetectionResult` at `0x1800039fa`
- `wdi!WdiSetProblemDetectionResult` at `0x180003a8b`

## string_xrefs

- `0x180003932`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`
- `0x1800038db`: `Software\Microsoft\Windows NT\CurrentVersion\MsiCorruptedFileRecovery\CorruptedFiles`

## pseudocode

```c
__int64 __fastcall RunProblemDetect(void *a1)
{
  int FileCorruptionEvent; // eax
  int v3; // ebx
  int v4; // r9d
  __int64 v5; // rdx
  int v6; // eax
  unsigned int v7; // esi
  int v8; // eax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  _BYTE v13[24]; // [rsp+30h] [rbp-48h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v15; // [rsp+58h] [rbp-20h]
  __int64 v16; // [rsp+60h] [rbp-18h]
  int v17; // [rsp+68h] [rbp-10h]
  unsigned int v18; // [rsp+A8h] [rbp+30h] BYREF

  Throttler::Throttler(
    (Throttler *)v13,
    L"Software\\Microsoft\\Windows NT\\CurrentVersion\\MsiCorruptedFileRecovery\\CorruptedFiles",
    0);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  *(_OWORD *)lpFileName = 0;
  FileCorruptionEvent = GetFileCorruptionEvent((__int64)a1, (__int64)lpFileName);
  v3 = FileCorruptionEvent;
  if ( FileCorruptionEvent < 0 )
  {
    v4 = 288;
LABEL_3:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunProblemDetect", v4, FileCorruptionEvent);
LABEL_25:
    SetScenarioResultParameter(a1, 3);
    SetScenarioDMError(a1, (unsigned int)v3);
    goto LABEL_26;
  }
  FileCorruptionEvent = CrashEventData::StoreInWdi((CrashEventData *)lpFileName, a1);
  v3 = FileCorruptionEvent;
  if ( FileCorruptionEvent < 0 )
  {
    v4 = 291;
    goto LABEL_3;
  }
  v18 = 0;
  FileCorruptionEvent = IsPEImage(lpFileName[0], &v18);
  v3 = FileCorruptionEvent;
  if ( FileCorruptionEvent < 0 )
  {
    v4 = 299;
    goto LABEL_3;
  }
  if ( !v18 )
  {
    WriteServerFileAppEvent(&MSIRE_DM_ETW_EVENT_FILE_NOT_PE_IMAGE, lpFileName[0], lpFileName[1]);
    v5 = 21;
LABEL_14:
    SetScenarioResultParameter(a1, v5);
    v3 = WdiSetProblemDetectionResult(a1, 0);
    goto LABEL_26;
  }
  v18 = 0;
  v6 = IsImageCorrupted(lpFileName[0], &v18);
  v3 = v6;
  if ( v6 < 0 )
  {
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "RunProblemDetect", 319, v6);
    goto LABEL_25;
  }
  v7 = v18;
  if ( !v18 )
  {
    WriteServerFileAppEvent(&MSIRE_DM_ETW_EVENT_FILE_NOT_CORRUPTED, lpFileName[0], lpFileName[1]);
    v5 = 7 - (unsigned int)(v3 != 1);
    goto LABEL_14;
  }
  WdiSetFeedback(a1, 3);
  v8 = Throttler::ProcessOccurrence((Throttler *)v13, (WCHAR *)lpFileName[0]);
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        if ( (unsigned int)(v10 - 1) > 1 )
          goto LABEL_24;
        v11 = 8;
      }
      else
      {
        WriteServerFileAppEvent(&CFR_DM_ETW_EVENT_THROTTLED_FREQUENT_INVOCATION, lpFileName[0], lpFileName[1]);
        v11 = 9;
      }
    }
    else
    {
      WriteServerFileAppEvent(&CFR_DM_ETW_EVENT_THROTTLED_REPEATED_INVOCATION, lpFileName[0], lpFileName[1]);
      v11 = 10;
    }
    SetScenarioResultParameter(a1, v11);
    v7 = 0;
  }
  else
  {
    v7 = 1;
  }
LABEL_24:
  v3 = WdiSetProblemDetectionResult(a1, v7);
  if ( v3 < 0 )
    goto LABEL_25;
LABEL_26:
  CrashEventData::Free((CrashEventData *)lpFileName);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800038cc  push    rbp
0x1800038ce  push    rbx
0x1800038cf  push    rsi
0x1800038d0  push    rdi
0x1800038d1  mov     rbp, rsp
0x1800038d4  sub     rsp, 78h
0x1800038d8  mov     rdi, rcx
0x1800038db  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800038e2  lea     rcx, [rbp+var_48]; this
0x1800038e6  xor     r8d, r8d; int
0x1800038e9  call    ??0Throttler@@QEAA@PEBGH@Z; Throttler::Throttler(ushort const *,int)
0x1800038ee  xorps   xmm0, xmm0
0x1800038f1  mov     [rbp+var_20], 0
0x1800038f9  lea     rdx, [rbp+lpFileName]
0x1800038fd  mov     [rbp+var_18], 0
0x180003905  mov     rcx, rdi
0x180003908  mov     [rbp+var_10], 0
0x18000390f  movdqu  xmmword ptr [rbp+lpFileName], xmm0
0x180003914  call    GetFileCorruptionEvent
0x180003919  mov     ebx, eax
0x18000391b  test    eax, eax
0x18000391d  jns     short loc_180003943
0x18000391f  mov     r9d, 120h
0x180003925  mov     [rsp+78h+var_58], eax
0x180003929  lea     r8, aRunproblemdete; "RunProblemDetect"
0x180003930  xor     ecx, ecx; Level
0x180003932  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180003939  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x18000393e  jmp     loc_180003A97
0x180003943  mov     rdx, rdi; void *
0x180003946  lea     rcx, [rbp+lpFileName]; this
0x18000394a  call    ?StoreInWdi@CrashEventData@@QEAAJPEAX@Z; CrashEventData::StoreInWdi(void *)
0x18000394f  mov     ebx, eax
0x180003951  test    eax, eax
0x180003953  jns     short loc_18000395D
0x180003955  mov     r9d, 123h
0x18000395b  jmp     short loc_180003925
0x18000395d  mov     rcx, [rbp+lpFileName]
0x180003961  lea     rdx, [rbp+arg_8]
0x180003965  mov     [rbp+arg_8], 0
0x18000396c  call    IsPEImage
0x180003971  mov     ebx, eax
0x180003973  test    eax, eax
0x180003975  jns     short loc_18000397F
0x180003977  mov     r9d, 12Bh
0x18000397d  jmp     short loc_180003925
0x18000397f  cmp     [rbp+arg_8], 0
0x180003983  jnz     short loc_1800039A0
0x180003985  mov     r8, [rbp+lpFileName+8]
0x180003989  lea     rcx, MSIRE_DM_ETW_EVENT_FILE_NOT_PE_IMAGE; EventDescriptor
0x180003990  mov     rdx, [rbp+lpFileName]
0x180003994  call    WriteServerFileAppEvent
0x180003999  mov     edx, 15h
0x18000399e  jmp     short loc_1800039ED
0x1800039a0  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800039a4  lea     rdx, [rbp+arg_8]
0x1800039a8  mov     [rbp+arg_8], 0
0x1800039af  call    IsImageCorrupted
0x1800039b4  mov     ebx, eax
0x1800039b6  test    eax, eax
0x1800039b8  jns     short loc_1800039C9
0x1800039ba  mov     [rsp+78h+var_58], eax
0x1800039be  mov     r9d, 13Fh
0x1800039c4  jmp     loc_180003929
0x1800039c9  mov     esi, [rbp+arg_8]
0x1800039cc  test    esi, esi
0x1800039ce  jnz     short loc_180003A07
0x1800039d0  mov     r8, [rbp+lpFileName+8]
0x1800039d4  lea     rcx, MSIRE_DM_ETW_EVENT_FILE_NOT_CORRUPTED; EventDescriptor
0x1800039db  mov     rdx, [rbp+lpFileName]
0x1800039df  call    WriteServerFileAppEvent
0x1800039e4  dec     ebx
0x1800039e6  neg     ebx
0x1800039e8  sbb     edx, edx
0x1800039ea  add     edx, 7
0x1800039ed  mov     rcx, rdi
0x1800039f0  call    SetScenarioResultParameter
0x1800039f5  xor     edx, edx
0x1800039f7  mov     rcx, rdi
0x1800039fa  call    cs:__imp_WdiSetProblemDetectionResult
0x180003a00  mov     ebx, eax
0x180003a02  jmp     loc_180003AAE
0x180003a07  mov     edx, 3
0x180003a0c  mov     rcx, rdi
0x180003a0f  call    cs:__imp_WdiSetFeedback
0x180003a15  mov     rdx, [rbp+lpFileName]
0x180003a19  lea     rcx, [rbp+var_48]
0x180003a1d  call    ?ProcessOccurrence@Throttler@@QEAA?AW4ThrottleResult@1@PEBG@Z; Throttler::ProcessOccurrence(ushort const *)
0x180003a22  test    eax, eax
0x180003a24  jz      short loc_180003A81
0x180003a26  sub     eax, 1
0x180003a29  jz      short loc_180003A5C
0x180003a2b  sub     eax, 1
0x180003a2e  jz      short loc_180003A41
0x180003a30  sub     eax, 1
0x180003a33  jz      short loc_180003A3A
0x180003a35  cmp     eax, 1
0x180003a38  jnz     short loc_180003A86
0x180003a3a  mov     edx, 8
0x180003a3f  jmp     short loc_180003A75
0x180003a41  mov     r8, [rbp+lpFileName+8]
0x180003a45  lea     rcx, CFR_DM_ETW_EVENT_THROTTLED_FREQUENT_INVOCATION; EventDescriptor
0x180003a4c  mov     rdx, [rbp+lpFileName]
0x180003a50  call    WriteServerFileAppEvent
0x180003a55  mov     edx, 9
0x180003a5a  jmp     short loc_180003A75
0x180003a5c  mov     r8, [rbp+lpFileName+8]
0x180003a60  lea     rcx, CFR_DM_ETW_EVENT_THROTTLED_REPEATED_INVOCATION; EventDescriptor
0x180003a67  mov     rdx, [rbp+lpFileName]
0x180003a6b  call    WriteServerFileAppEvent
0x180003a70  mov     edx, 0Ah
0x180003a75  mov     rcx, rdi
0x180003a78  call    SetScenarioResultParameter
0x180003a7d  xor     esi, esi
0x180003a7f  jmp     short loc_180003A86
0x180003a81  mov     esi, 1
0x180003a86  mov     edx, esi
0x180003a88  mov     rcx, rdi
0x180003a8b  call    cs:__imp_WdiSetProblemDetectionResult
0x180003a91  mov     ebx, eax
0x180003a93  test    eax, eax
0x180003a95  jns     short loc_180003AAE
0x180003a97  mov     edx, 3
0x180003a9c  mov     rcx, rdi
0x180003a9f  call    SetScenarioResultParameter
0x180003aa4  mov     edx, ebx
0x180003aa6  mov     rcx, rdi
0x180003aa9  call    SetScenarioDMError
0x180003aae  lea     rcx, [rbp+lpFileName]; this
0x180003ab2  call    ?Free@CrashEventData@@QEAAXXZ; CrashEventData::Free(void)
0x180003ab7  mov     eax, ebx
0x180003ab9  add     rsp, 78h
0x180003abd  pop     rdi
0x180003abe  pop     rsi
0x180003abf  pop     rbx
0x180003ac0  pop     rbp
0x180003ac1  retn
```
