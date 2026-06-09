# winreFindMainOsConfigDir

- ea: `0x18001051c`
- end: `0x1800106cd`
- name: `winreFindMainOsConfigDir`
- size: `433`
- prototype: ``
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x1800109f8`
- `0x180011074`
- `0x180018870`
- `0x180038120`
- `0x18003a248`
- `0x18003add0`
- `0x18003bea8`
- `0x18003bfbc`

## callees

- `0x180001f94`
- `0x1800059fc`
- `0x18000c658`
- `0x18000c6f0`
- `0x18000ff68`
- `0x18000ffcc`
- `0x18001051c`
- `0x180051dc8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800105a5`
- `KERNEL32!GetLastError` at `0x1800105a5`
- `KERNEL32!GetSystemDirectoryW` at `0x180010597`
- `KERNEL32!GetSystemDirectoryW` at `0x180010597`
- `ole32!CoTaskMemFree` at `0x1800106b7`
- `ole32!CoTaskMemFree` at `0x1800106b7`

## string_xrefs

- `0x18001054e`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x1800105cc`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010650`: `base\diagnosis\srt\reagent2\reinfo\shared.cpp`
- `0x180010565`: `failed to allocate path`
- `0x18001056c`: `winreFindMainOsConfigDir %s (0x%x) in file %S line %d`
- `0x1800105ef`: `winreFindMainOsConfigDir %s (0x%x) in file %S line %d`
- `0x180010673`: `winreFindMainOsConfigDir %s (0x%x) in file %S line %d`
- `0x18001060f`: `system32`

## pseudocode

```c
__int64 __fastcall winreFindMainOsConfigDir(struct _GUID *a1, unsigned __int16 **a2)
{
  void *v3; // rsi
  DWORD OsInfoForBootEntry; // ebx
  unsigned __int16 *v6; // rdi
  LPWSTR lpBuffer; // [rsp+60h] [rbp+18h] BYREF
  void *Block; // [rsp+68h] [rbp+20h] BYREF

  lpBuffer = 0;
  v3 = 0;
  Block = 0;
  OsInfoForBootEntry = winreAllocPath(&lpBuffer);
  if ( !OsInfoForBootEntry )
  {
    if ( a1 )
    {
      OsInfoForBootEntry = CBootCfg::GetOsInfoForBootEntry(
                             (CBootCfg *)CBootCfg::m_instance,
                             a1,
                             (struct _SRT_OS_INFO **)&Block);
      if ( OsInfoForBootEntry )
      {
        UnattendLogW(
          2,
          L"winreFindMainOsConfigDir %s (0x%x) in file %S line %d",
          L"failed to get os info for boot entry",
          OsInfoForBootEntry,
          "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
          1329);
        v6 = lpBuffer;
        v3 = Block;
        goto LABEL_14;
      }
      v3 = Block;
      v6 = lpBuffer;
      if ( StringCchPrintfW(lpBuffer, 0x12Eu, L"%s\\%s", Block, L"system32") < 0 )
        goto LABEL_9;
    }
    else
    {
      v6 = lpBuffer;
      if ( !GetSystemDirectoryW(lpBuffer, 0x12Eu) )
      {
        OsInfoForBootEntry = GetLastError();
        goto LABEL_16;
      }
    }
    OsInfoForBootEntry = winreAddTrailingBackslash(v6);
    if ( OsInfoForBootEntry )
    {
      UnattendLogW(
        2,
        L"winreFindMainOsConfigDir %s (0x%x) in file %S line %d",
        L"failed to add trailing back slash",
        OsInfoForBootEntry,
        "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
        1346);
      goto LABEL_14;
    }
    if ( StringCchCatW(v6, 0x12Eu, L"Recovery") >= 0 )
    {
      *a2 = v6;
      v6 = 0;
LABEL_14:
      if ( v3 )
        operator delete(v3);
LABEL_16:
      if ( !OsInfoForBootEntry )
        return OsInfoForBootEntry;
      goto LABEL_17;
    }
LABEL_9:
    OsInfoForBootEntry = 87;
    goto LABEL_14;
  }
  UnattendLogW(
    2,
    L"winreFindMainOsConfigDir %s (0x%x) in file %S line %d",
    L"failed to allocate path",
    OsInfoForBootEntry,
    "base\\diagnosis\\srt\\reagent2\\reinfo\\shared.cpp",
    1313);
  v6 = lpBuffer;
LABEL_17:
  if ( v6 )
    CoTaskMemFree(v6);
  return OsInfoForBootEntry;
}

```

## disassembly

```asm
0x18001051c  mov     rax, rsp
0x18001051f  mov     [rax+8], rbx
0x180010523  push    rsi
0x180010524  push    rdi
0x180010525  push    r14
0x180010527  sub     rsp, 30h
0x18001052b  mov     rdi, rcx
0x18001052e  mov     qword ptr [rax+18h], 0
0x180010536  xor     esi, esi
0x180010538  lea     rcx, [rax+18h]
0x18001053c  mov     [rax+20h], rsi
0x180010540  mov     r14, rdx
0x180010543  call    winreAllocPath
0x180010548  mov     ebx, eax
0x18001054a  test    eax, eax
0x18001054c  jz      short loc_180010585
0x18001054e  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010555  mov     [rsp+48h+var_20], 521h
0x18001055d  mov     r9d, ebx
0x180010560  mov     [rsp+48h+var_28], rax
0x180010565  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18001056c  lea     rdx, aWinrefindmaino; "winreFindMainOsConfigDir %s (0x%x) in f"...
0x180010573  lea     ecx, [rsi+2]
0x180010576  call    UnattendLogW
0x18001057b  mov     rdi, [rsp+48h+lpBuffer]
0x180010580  jmp     loc_1800106AF
0x180010585  test    rdi, rdi
0x180010588  jnz     short loc_1800105B2
0x18001058a  mov     rdi, [rsp+48h+lpBuffer]
0x18001058f  mov     edx, 12Eh; uSize
0x180010594  mov     rcx, rdi; lpBuffer
0x180010597  call    cs:__imp_GetSystemDirectoryW
0x18001059d  test    eax, eax
0x18001059f  jnz     loc_180010642
0x1800105a5  call    cs:__imp_GetLastError
0x1800105ab  mov     ebx, eax
0x1800105ad  jmp     loc_1800106AB
0x1800105b2  lea     r8, [rsp+48h+Block]; struct _SRT_OS_INFO **
0x1800105b7  mov     rdx, rdi; struct _GUID *
0x1800105ba  lea     rcx, ?m_instance@CBootCfg@@0V1@A; this
0x1800105c1  call    ?GetOsInfoForBootEntry@CBootCfg@@QEAAKPEBU_GUID@@PEAPEAU_SRT_OS_INFO@@@Z; CBootCfg::GetOsInfoForBootEntry(_GUID const *,_SRT_OS_INFO * *)
0x1800105c6  mov     ebx, eax
0x1800105c8  test    eax, eax
0x1800105ca  jz      short loc_18001060A
0x1800105cc  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x1800105d3  mov     [rsp+48h+var_20], 531h
0x1800105db  mov     r9d, ebx
0x1800105de  mov     [rsp+48h+var_28], rax
0x1800105e3  lea     r8, aFailedToGetOsI_0; "failed to get os info for boot entry"
0x1800105ea  mov     ecx, 2
0x1800105ef  lea     rdx, aWinrefindmaino; "winreFindMainOsConfigDir %s (0x%x) in f"...
0x1800105f6  call    UnattendLogW
0x1800105fb  mov     rdi, [rsp+48h+lpBuffer]
0x180010600  mov     rsi, [rsp+48h+Block]
0x180010605  jmp     loc_18001069E
0x18001060a  mov     rsi, [rsp+48h+Block]
0x18001060f  lea     rax, aSystem32; "system32"
0x180010616  mov     rdi, [rsp+48h+lpBuffer]
0x18001061b  lea     r8, aSS_1; "%s\\%s"
0x180010622  mov     r9, rsi
0x180010625  mov     [rsp+48h+var_28], rax
0x18001062a  mov     rcx, rdi; unsigned __int16 *
0x18001062d  mov     edx, 12Eh; unsigned __int64
0x180010632  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010637  test    eax, eax
0x180010639  jns     short loc_180010642
0x18001063b  mov     ebx, 57h ; 'W'
0x180010640  jmp     short loc_18001069E
0x180010642  mov     rcx, rdi
0x180010645  call    winreAddTrailingBackslash
0x18001064a  mov     ebx, eax
0x18001064c  test    eax, eax
0x18001064e  jz      short loc_180010681
0x180010650  lea     rax, aBaseDiagnosisS_7; "base\\diagnosis\\srt\\reagent2\\reinfo"...
0x180010657  mov     [rsp+48h+var_20], 542h
0x18001065f  mov     r9d, ebx
0x180010662  mov     [rsp+48h+var_28], rax
0x180010667  lea     r8, aFailedToAddTra_0; "failed to add trailing back slash"
0x18001066e  mov     ecx, 2
0x180010673  lea     rdx, aWinrefindmaino; "winreFindMainOsConfigDir %s (0x%x) in f"...
0x18001067a  call    UnattendLogW
0x18001067f  jmp     short loc_18001069E
0x180010681  lea     r8, AppName; "Recovery"
0x180010688  mov     edx, 12Eh; unsigned __int64
0x18001068d  mov     rcx, rdi; unsigned __int16 *
0x180010690  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010695  test    eax, eax
0x180010697  js      short loc_18001063B
0x180010699  mov     [r14], rdi
0x18001069c  xor     edi, edi
0x18001069e  test    rsi, rsi
0x1800106a1  jz      short loc_1800106AB
0x1800106a3  mov     rcx, rsi; Block
0x1800106a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800106ab  test    ebx, ebx
0x1800106ad  jz      short loc_1800106BD
0x1800106af  test    rdi, rdi
0x1800106b2  jz      short loc_1800106BD
0x1800106b4  mov     rcx, rdi; pv
0x1800106b7  call    cs:__imp_CoTaskMemFree
0x1800106bd  mov     eax, ebx
0x1800106bf  mov     rbx, [rsp+48h+arg_0]
0x1800106c4  add     rsp, 30h
0x1800106c8  pop     r14
0x1800106ca  pop     rdi
0x1800106cb  pop     rsi
0x1800106cc  retn
```
