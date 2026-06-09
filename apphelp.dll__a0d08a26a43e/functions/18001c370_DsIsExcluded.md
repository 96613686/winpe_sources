# DsIsExcluded

- ea: `0x18001c370`
- end: `0x18001c484`
- name: `DsIsExcluded`
- size: `276`
- prototype: `__int64 __fastcall(wchar_t *Str, __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001bfe8`

## callees

- `0x18000f114`
- `0x18001af50`
- `0x18001c320`
- `0x18001c370`
- `0x18001c48c`
- `0x180039a5a`
- `0x180039a72`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001c3dd`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001c3dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c3d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3e7`

## pseudocode

```c
__int64 __fastcall DsIsExcluded(wchar_t *Str, __int64 a2, unsigned __int64 a3)
{
  unsigned int v4; // ebx
  DWORD CurrentProcessId; // eax
  DWORD LastError; // eax
  char *v7; // rcx
  wchar_t *v8; // rax
  DWORD pSessionId; // [rsp+50h] [rbp+18h] BYREF
  int v11; // [rsp+58h] [rbp+20h] BYREF

  pSessionId = 0;
  v11 = 0;
  v4 = 1;
  if ( a3 < 0x40 )
  {
    AslLogCallPrintf(1, "DsIsExcluded", 82, "Bad image");
    return v4;
  }
  if ( RtlpImageNtHeader(a2) )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(1, "DsIsExcluded", 97, "Failed to retrieve session id [%d]", LastError);
      return v4;
    }
    if ( !pSessionId )
    {
      v7 = "DetectorShims,Excluded,Session 0";
LABEL_10:
      DsTracePrintf(v7);
      return v4;
    }
    v8 = wcsrchr_0(Str, 0x5Cu);
    if ( !v8 || wcsicmp_0(v8 + 1, L"ntvdm.exe") )
    {
      if ( (int)CompatCacheIsSystemFile(&v11, Str) >= 0 && v11 == 1 )
      {
        v7 = "DetectorShims,Excluded,SystemFile";
        goto LABEL_10;
      }
    }
    else
    {
      DsTracePrintf("NTVDM is treated as user application");
    }
    return 0;
  }
  AslLogCallPrintf(1, "DsIsExcluded", 88, "Bad header");
  return v4;
}

```

## disassembly

```asm
0x18001c370  mov     [rsp+arg_0], rbx
0x18001c375  push    rdi
0x18001c376  sub     rsp, 30h
0x18001c37a  mov     [rsp+38h+pSessionId], 0
0x18001c382  mov     rdi, rcx
0x18001c385  mov     [rsp+38h+arg_18], 0
0x18001c38d  mov     ebx, 1
0x18001c392  cmp     r8, 40h ; '@'
0x18001c396  jnb     short loc_18001C3B6
0x18001c398  lea     r9, aBadImage; "Bad image"
0x18001c39f  lea     r8d, [rbx+51h]
0x18001c3a3  lea     rdx, aDsisexcluded; "DsIsExcluded"
0x18001c3aa  mov     ecx, ebx
0x18001c3ac  call    AslLogCallPrintf
0x18001c3b1  jmp     loc_18001C457
0x18001c3b6  mov     rcx, rdx
0x18001c3b9  call    RtlpImageNtHeader
0x18001c3be  test    rax, rax
0x18001c3c1  jnz     short loc_18001C3D0
0x18001c3c3  lea     r9, aBadHeader; "Bad header"
0x18001c3ca  lea     r8d, [rax+58h]
0x18001c3ce  jmp     short loc_18001C3A3
0x18001c3d0  call    cs:__imp_GetCurrentProcessId
0x18001c3d6  mov     ecx, eax; dwProcessId
0x18001c3d8  lea     rdx, [rsp+38h+pSessionId]; pSessionId
0x18001c3dd  call    cs:__imp_ProcessIdToSessionId
0x18001c3e3  test    eax, eax
0x18001c3e5  jnz     short loc_18001C40E
0x18001c3e7  call    cs:__imp_GetLastError
0x18001c3ed  lea     r9, aFailedToRetrie_1; "Failed to retrieve session id [%d]"
0x18001c3f4  mov     r8d, 61h ; 'a'
0x18001c3fa  lea     rdx, aDsisexcluded; "DsIsExcluded"
0x18001c401  mov     [rsp+38h+var_18], eax
0x18001c405  mov     ecx, ebx
0x18001c407  call    AslLogCallPrintf
0x18001c40c  jmp     short loc_18001C457
0x18001c40e  cmp     [rsp+38h+pSessionId], 0
0x18001c413  jnz     short loc_18001C423
0x18001c415  lea     rcx, aDetectorshimsE; "DetectorShims,Excluded,Session 0"
0x18001c41c  call    DsTracePrintf
0x18001c421  jmp     short loc_18001C457
0x18001c423  mov     edx, 5Ch ; '\'; Ch
0x18001c428  mov     rcx, rdi; Str
0x18001c42b  call    wcsrchr_0
0x18001c430  test    rax, rax
0x18001c433  jz      short loc_18001C464
0x18001c435  lea     rcx, [rax+2]; String1
0x18001c439  lea     rdx, aNtvdmExe; "ntvdm.exe"
0x18001c440  call    _wcsicmp_0
0x18001c445  test    eax, eax
0x18001c447  jnz     short loc_18001C464
0x18001c449  lea     rcx, aNtvdmIsTreated; "NTVDM is treated as user application"
0x18001c450  call    DsTracePrintf
0x18001c455  xor     ebx, ebx
0x18001c457  mov     eax, ebx
0x18001c459  mov     rbx, [rsp+38h+arg_0]
0x18001c45e  add     rsp, 30h
0x18001c462  pop     rdi
0x18001c463  retn
0x18001c464  mov     rdx, rdi
0x18001c467  lea     rcx, [rsp+38h+arg_18]
0x18001c46c  call    CompatCacheIsSystemFile
0x18001c471  test    eax, eax
0x18001c473  js      short loc_18001C455
0x18001c475  cmp     [rsp+38h+arg_18], ebx
0x18001c479  jnz     short loc_18001C455
0x18001c47b  lea     rcx, aDetectorshimsE_0; "DetectorShims,Excluded,SystemFile"
0x18001c482  jmp     short loc_18001C41C
```
