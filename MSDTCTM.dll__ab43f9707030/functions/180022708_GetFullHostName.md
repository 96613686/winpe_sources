# GetFullHostName

- ea: `0x180022708`
- end: `0x180022812`
- name: `GetFullHostName`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b1270`

## callees

- `0x1800063b0`
- `0x180022708`
- `0x1800846c0`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800227ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227aa`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800227a0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800227a0`

## string_xrefs

- `0x1800227d1`: `com\complus\dtc\dtc\tipgw\tipconn\src\tipconnection.cpp`
- `0x180022741`: `GetFullHostName (com\complus\dtc\dtc\tipgw\tipconn\src\tipconnection.cpp@745): GetFullyQualitifedHostName, pszFullName != NULL`
- `0x18002272f`: `GetFullHostName (com\complus\dtc\dtc\tipgw\tipconn\src\tipconnection.cpp@744): GetFullyQualitifedHostName, i_pTmInstance != NULL`

## pseudocode

```c
__int64 __fastcall GetFullHostName(__int64 a1, CHAR *a2)
{
  signed int v3; // ebx
  const wchar_t *v4; // rax
  __int64 v5; // r9
  signed int LastError; // eax
  __int64 cbMultiByte; // [rsp+28h] [rbp-20h]
  LPCWCH lpWideCharStr; // [rsp+50h] [rbp+8h] BYREF

  lpWideCharStr = 0;
  if ( !g_pTipTmInstance )
    DtcInternalErrorW(
      L"GetFullHostName (com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp@744): GetFullyQualitifedHostName, "
       "i_pTmInstance != NULL");
  if ( !a2 )
    DtcInternalErrorW(
      L"GetFullHostName (com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp@745): GetFullyQualitifedHostName, "
       "pszFullName != NULL");
  v3 = (*(__int64 (__fastcall **)(struct ITmInstance *, LPCWCH *))(*(_QWORD *)g_pTipTmInstance + 48LL))(
         g_pTipTmInstance,
         &lpWideCharStr);
  if ( v3 >= 0 )
  {
    if ( WideCharToMultiByte(0, 0, lpWideCharStr, -1, a2, 1025, 0, 0) )
      goto LABEL_12;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = L"failed WideCharToMultiByte";
    v5 = 765;
  }
  else
  {
    v4 = L"failed i_pTmInstance->GetFullyQualifiedHostName";
    v5 = 751;
  }
  LODWORD(cbMultiByte) = v3;
  TraceStringInline(
    10,
    1,
    L"com\\complus\\dtc\\dtc\\tipgw\\tipconn\\src\\tipconnection.cpp",
    v5,
    L"GetFullHostName",
    cbMultiByte,
    v4);
LABEL_12:
  if ( lpWideCharStr )
    CoTaskMemFree((LPVOID)lpWideCharStr);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180022708  mov     [rsp+arg_8], rbx
0x18002270d  mov     [rsp+lpWideCharStr], rcx
0x180022712  push    rdi
0x180022713  sub     rsp, 40h
0x180022717  mov     rcx, cs:?g_pTipTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pTipTmInstance
0x18002271e  mov     rdi, rdx
0x180022721  mov     [rsp+48h+lpWideCharStr], 0
0x18002272a  test    rcx, rcx
0x18002272d  jnz     short loc_18002273C
0x18002272f  lea     rcx, aGetfullhostnam_1; "GetFullHostName (com\\complus\\dtc\\dtc"...
0x180022736  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002273c  test    rdi, rdi
0x18002273f  jnz     short loc_18002274E
0x180022741  lea     rcx, aGetfullhostnam_0; "GetFullHostName (com\\complus\\dtc\\dtc"...
0x180022748  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18002274e  mov     rax, [rcx]
0x180022751  lea     rdx, [rsp+48h+lpWideCharStr]
0x180022756  mov     rax, [rax+30h]
0x18002275a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002275f  mov     ebx, eax
0x180022761  test    eax, eax
0x180022763  jns     short loc_180022774
0x180022765  lea     rax, aFailedIPtminst; "failed i_pTmInstance->GetFullyQualified"...
0x18002276c  mov     r9d, 2EFh
0x180022772  jmp     short loc_1800227CC
0x180022774  mov     r8, [rsp+48h+lpWideCharStr]; lpWideCharStr
0x180022779  or      r9d, 0FFFFFFFFh; cchWideChar
0x18002277d  mov     [rsp+48h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180022786  xor     edx, edx; dwFlags
0x180022788  mov     [rsp+48h+lpDefaultChar], 0; lpDefaultChar
0x180022791  xor     ecx, ecx; CodePage
0x180022793  mov     dword ptr [rsp+48h+cbMultiByte], 401h; cbMultiByte
0x18002279b  mov     [rsp+48h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800227a0  call    cs:__imp_WideCharToMultiByte
0x1800227a6  test    eax, eax
0x1800227a8  jnz     short loc_1800227F5
0x1800227aa  call    cs:__imp_GetLastError
0x1800227b0  mov     ebx, eax
0x1800227b2  test    eax, eax
0x1800227b4  jle     short loc_1800227BF
0x1800227b6  movzx   ebx, ax
0x1800227b9  or      ebx, 80070000h
0x1800227bf  lea     rax, aFailedWidechar; "failed WideCharToMultiByte"
0x1800227c6  mov     r9d, 2FDh
0x1800227cc  mov     [rsp+48h+lpDefaultChar], rax
0x1800227d1  lea     r8, aComComplusDtcD_30; "com\\complus\\dtc\\dtc\\tipgw\\tipconn"...
0x1800227d8  mov     edx, 1
0x1800227dd  mov     dword ptr [rsp+48h+cbMultiByte], ebx
0x1800227e1  lea     rax, aGetfullhostnam; "GetFullHostName"
0x1800227e8  mov     [rsp+48h+lpMultiByteStr], rax
0x1800227ed  lea     ecx, [rdx+9]
0x1800227f0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800227f5  mov     rcx, [rsp+48h+lpWideCharStr]; pv
0x1800227fa  test    rcx, rcx
0x1800227fd  jz      short loc_180022805
0x1800227ff  call    cs:__imp_CoTaskMemFree
0x180022805  mov     eax, ebx
0x180022807  mov     rbx, [rsp+48h+arg_8]
0x18002280c  add     rsp, 40h
0x180022810  pop     rdi
0x180022811  retn
```
