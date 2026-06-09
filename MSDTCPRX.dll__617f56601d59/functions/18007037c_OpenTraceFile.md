# OpenTraceFile

- ea: `0x18007037c`
- end: `0x180070471`
- name: `OpenTraceFile`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180070478`

## callees

- `0x180058a38`
- `0x180070290`
- `0x18007037c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800703cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007045d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800703cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007045d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800703d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007040a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800703d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007040a`
- `msvcrt!_wfopen` at `0x180070445`
- `msvcrt!_wfopen` at `0x180070445`

## pseudocode

```c
FILE *OpenTraceFile()
{
  void *v0; // rbx
  FILE *v1; // rdi
  int ImageName; // eax
  __int64 v4; // [rsp+20h] [rbp-18h]
  DWORD CurrentProcessId; // [rsp+28h] [rbp-10h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  v0 = 0;
  v1 = 0;
  pv = 0;
  if ( !TraceOutputSettings::TraceFilePath )
    return v1;
  if ( byte_1800D581C )
  {
    if ( TraceOutputSettings::ImageNameInTraceFileNameEnabled )
    {
      ImageName = GetImageName((unsigned __int16 **)&pv);
      v0 = pv;
      if ( ImageName < 0 )
      {
        if ( !pv )
          goto LABEL_9;
        CoTaskMemFree(pv);
        v0 = 0;
      }
    }
    if ( !v0
      || (CurrentProcessId = GetCurrentProcessId(),
          (int)StringCbPrintfW(
                 &word_1800D98C0,
                 0x20Au,
                 L"%s\\MSDTC-%s-%d.log",
                 TraceOutputSettings::TraceFilePath,
                 v0,
                 CurrentProcessId) < 0) )
    {
LABEL_9:
      LODWORD(v4) = GetCurrentProcessId();
      if ( (int)StringCbPrintfW(&word_1800D98C0, 0x20Au, L"%s\\MSDTC-%d.log", TraceOutputSettings::TraceFilePath, v4) < 0 )
        goto LABEL_11;
    }
  }
  v1 = _wfopen(&word_1800D98C0, L"a+");
  byte_1800D581C = 0;
LABEL_11:
  if ( v0 )
    CoTaskMemFree(v0);
  return v1;
}

```

## disassembly

```asm
0x18007037c  mov     [rsp+arg_8], rbx
0x180070381  push    rdi
0x180070382  sub     rsp, 30h
0x180070386  xor     ebx, ebx
0x180070388  xor     edi, edi
0x18007038a  cmp     cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA, rbx; ushort * TraceOutputSettings::TraceFilePath
0x180070391  mov     [rsp+38h+pv], rbx
0x180070396  jz      loc_180070463
0x18007039c  cmp     cs:byte_1800D581C, bl
0x1800703a2  jz      loc_180070437
0x1800703a8  cmp     cs:?ImageNameInTraceFileNameEnabled@TraceOutputSettings@@2_NA, bl; bool TraceOutputSettings::ImageNameInTraceFileNameEnabled
0x1800703ae  jz      short loc_1800703D3
0x1800703b0  lea     rcx, [rsp+38h+pv]; unsigned __int16 **
0x1800703b5  call    ?GetImageName@@YAJPEAPEAG@Z; GetImageName(ushort * *)
0x1800703ba  mov     rbx, [rsp+38h+pv]
0x1800703bf  test    eax, eax
0x1800703c1  jns     short loc_1800703D3
0x1800703c3  test    rbx, rbx
0x1800703c6  jz      short loc_18007040A
0x1800703c8  mov     rcx, rbx; pv
0x1800703cb  call    cs:__imp_CoTaskMemFree
0x1800703d1  xor     ebx, ebx
0x1800703d3  test    rbx, rbx
0x1800703d6  jz      short loc_18007040A
0x1800703d8  call    cs:__imp_GetCurrentProcessId
0x1800703de  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x1800703e5  lea     r8, aSMsdtcSDLog; "%s\\MSDTC-%s-%d.log"
0x1800703ec  mov     [rsp+38h+var_10], eax
0x1800703f0  lea     rcx, word_1800D98C0; unsigned __int16 *
0x1800703f7  mov     edx, 20Ah; unsigned __int64
0x1800703fc  mov     [rsp+38h+var_18], rbx
0x180070401  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070406  test    eax, eax
0x180070408  jns     short loc_180070437
0x18007040a  call    cs:__imp_GetCurrentProcessId
0x180070410  mov     r9, cs:?TraceFilePath@TraceOutputSettings@@2PEAGEA; ushort * TraceOutputSettings::TraceFilePath
0x180070417  lea     r8, aSMsdtcDLog; "%s\\MSDTC-%d.log"
0x18007041e  mov     edx, 20Ah; unsigned __int64
0x180070423  mov     dword ptr [rsp+38h+var_18], eax
0x180070427  lea     rcx, word_1800D98C0; unsigned __int16 *
0x18007042e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070433  test    eax, eax
0x180070435  js      short loc_180070455
0x180070437  lea     rdx, aA; "a+"
0x18007043e  lea     rcx, word_1800D98C0; FileName
0x180070445  call    cs:__imp__wfopen
0x18007044b  mov     rdi, rax
0x18007044e  mov     cs:byte_1800D581C, 0
0x180070455  test    rbx, rbx
0x180070458  jz      short loc_180070463
0x18007045a  mov     rcx, rbx; pv
0x18007045d  call    cs:__imp_CoTaskMemFree
0x180070463  mov     rbx, [rsp+38h+arg_8]
0x180070468  mov     rax, rdi
0x18007046b  add     rsp, 30h
0x18007046f  pop     rdi
0x180070470  retn
```
