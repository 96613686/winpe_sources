# winreCreateOrOpenLogDir(ushort * *)

- ea: `0x18002b6f0`
- end: `0x18002b83c`
- name: `?winreCreateOrOpenLogDir@@YAKPEAPEAG@Z`
- size: `332`
- prototype: `unsigned int __fastcall(unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task`

## callers

- `0x18002bd30`
- `0x18002c280`
- `0x18002c810`

## callees

- `0x1800059fc`
- `0x180006ed8`
- `0x18000ed74`
- `0x18000ffcc`
- `0x18002b6f0`
- `0x18002bfac`
- `0x1800322a8`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002b824`
- `ole32!CoTaskMemFree` at `0x18002b824`

## string_xrefs

- `0x18002b730`: `failed to allocate path`
- `0x18002b797`: `failed to copy string`
- `0x18002b737`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b780`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b7e6`: `base\diagnosis\srt\reagent2\reagent\logfile.cpp`
- `0x18002b741`: `winreCreateOrOpenLogDir %s (0x%x) in file %S line %d`
- `0x18002b7a3`: `winreCreateOrOpenLogDir %s (0x%x) in file %S line %d`
- `0x18002b809`: `winreCreateOrOpenLogDir %s (0x%x) in file %S line %d`
- `0x18002b7c7`: `failed to get log directory path`
- `0x18002b7fd`: `failed to open directory`

## pseudocode

```c
__int64 __fastcall winreCreateOrOpenLogDir(unsigned __int16 **a1)
{
  unsigned int LogDirPathInternal; // ebx
  const wchar_t *v3; // r8
  WCHAR *v4; // rdi
  int v6; // [rsp+28h] [rbp-10h]
  LPVOID pv; // [rsp+48h] [rbp+10h] BYREF

  pv = 0;
  if ( (unsigned int)winreIsWinPE() )
  {
    LogDirPathInternal = winreAllocPath(&pv);
    if ( LogDirPathInternal )
    {
      v6 = 360;
      v3 = L"failed to allocate path";
LABEL_4:
      UnattendLogW(
        2,
        L"winreCreateOrOpenLogDir %s (0x%x) in file %S line %d",
        v3,
        LogDirPathInternal,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        v6);
      v4 = (WCHAR *)pv;
      goto LABEL_13;
    }
    v4 = (WCHAR *)pv;
    LogDirPathInternal = StringCchCopyW((unsigned __int16 *)pv, 0x12Eu, L"x:\\RecoveryLogs");
    if ( (LogDirPathInternal & 0x80000000) != 0 )
    {
      UnattendLogW(
        2,
        L"winreCreateOrOpenLogDir %s (0x%x) in file %S line %d",
        L"failed to copy string",
        LogDirPathInternal,
        "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
        362);
      LogDirPathInternal = (unsigned __int16)LogDirPathInternal;
      goto LABEL_13;
    }
  }
  else
  {
    LogDirPathInternal = WinReGetLogDirPathInternal((WCHAR **)&pv);
    if ( LogDirPathInternal )
    {
      v6 = 367;
      v3 = L"failed to get log directory path";
      goto LABEL_4;
    }
    v4 = (WCHAR *)pv;
  }
  LogDirPathInternal = winreOpenOrCreateDir(v4);
  if ( LogDirPathInternal )
  {
    UnattendLogW(
      2,
      L"winreCreateOrOpenLogDir %s (0x%x) in file %S line %d",
      L"failed to open directory",
      LogDirPathInternal,
      "base\\diagnosis\\srt\\reagent2\\reagent\\logfile.cpp",
      370);
  }
  else
  {
    *a1 = v4;
    v4 = 0;
  }
LABEL_13:
  if ( v4 )
    CoTaskMemFree(v4);
  return LogDirPathInternal;
}

```

## disassembly

```asm
0x18002b6f0  mov     [rsp+arg_0], rbx
0x18002b6f5  mov     [rsp+arg_10], rsi
0x18002b6fa  push    rdi
0x18002b6fb  sub     rsp, 30h
0x18002b6ff  mov     rsi, rcx
0x18002b702  mov     [rsp+38h+pv], 0
0x18002b70b  call    ?winreIsWinPE@@YAHXZ; winreIsWinPE(void)
0x18002b710  lea     rcx, [rsp+38h+pv]
0x18002b715  test    eax, eax
0x18002b717  jz      loc_18002B7B4
0x18002b71d  call    winreAllocPath
0x18002b722  mov     ebx, eax
0x18002b724  test    eax, eax
0x18002b726  jz      short loc_18002B761
0x18002b728  mov     [rsp+38h+var_10], 168h
0x18002b730  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002b737  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b73e  mov     r9d, ebx
0x18002b741  lea     rdx, aWinrecreateoro; "winreCreateOrOpenLogDir %s (0x%x) in fi"...
0x18002b748  mov     [rsp+38h+var_18], rax
0x18002b74d  mov     ecx, 2
0x18002b752  call    UnattendLogW
0x18002b757  mov     rdi, [rsp+38h+pv]
0x18002b75c  jmp     loc_18002B81C
0x18002b761  mov     rdi, [rsp+38h+pv]
0x18002b766  lea     r8, FileName; "x:\\RecoveryLogs"
0x18002b76d  mov     rcx, rdi; unsigned __int16 *
0x18002b770  mov     edx, 12Eh; unsigned __int64
0x18002b775  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002b77a  mov     ebx, eax
0x18002b77c  test    eax, eax
0x18002b77e  jns     short loc_18002B7D8
0x18002b780  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b787  mov     [rsp+38h+var_10], 16Ah
0x18002b78f  mov     r9d, ebx
0x18002b792  mov     [rsp+38h+var_18], rax
0x18002b797  lea     r8, aFailedToCopySt; "failed to copy string"
0x18002b79e  mov     ecx, 2
0x18002b7a3  lea     rdx, aWinrecreateoro; "winreCreateOrOpenLogDir %s (0x%x) in fi"...
0x18002b7aa  call    UnattendLogW
0x18002b7af  movzx   ebx, bx
0x18002b7b2  jmp     short loc_18002B81C
0x18002b7b4  call    WinReGetLogDirPathInternal
0x18002b7b9  mov     ebx, eax
0x18002b7bb  test    eax, eax
0x18002b7bd  jz      short loc_18002B7D3
0x18002b7bf  mov     [rsp+38h+var_10], 16Fh
0x18002b7c7  lea     r8, aFailedToGetLog_0; "failed to get log directory path"
0x18002b7ce  jmp     loc_18002B737
0x18002b7d3  mov     rdi, [rsp+38h+pv]
0x18002b7d8  mov     rcx, rdi; lpFileName
0x18002b7db  call    winreOpenOrCreateDir
0x18002b7e0  mov     ebx, eax
0x18002b7e2  test    eax, eax
0x18002b7e4  jz      short loc_18002B817
0x18002b7e6  lea     rax, aBaseDiagnosisS_6; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002b7ed  mov     [rsp+38h+var_10], 172h
0x18002b7f5  mov     r9d, ebx
0x18002b7f8  mov     [rsp+38h+var_18], rax
0x18002b7fd  lea     r8, aFailedToOpenDi; "failed to open directory"
0x18002b804  mov     ecx, 2
0x18002b809  lea     rdx, aWinrecreateoro; "winreCreateOrOpenLogDir %s (0x%x) in fi"...
0x18002b810  call    UnattendLogW
0x18002b815  jmp     short loc_18002B81C
0x18002b817  mov     [rsi], rdi
0x18002b81a  xor     edi, edi
0x18002b81c  test    rdi, rdi
0x18002b81f  jz      short loc_18002B82A
0x18002b821  mov     rcx, rdi; pv
0x18002b824  call    cs:__imp_CoTaskMemFree
0x18002b82a  mov     rsi, [rsp+38h+arg_10]
0x18002b82f  mov     eax, ebx
0x18002b831  mov     rbx, [rsp+38h+arg_0]
0x18002b836  add     rsp, 30h
0x18002b83a  pop     rdi
0x18002b83b  retn
```
