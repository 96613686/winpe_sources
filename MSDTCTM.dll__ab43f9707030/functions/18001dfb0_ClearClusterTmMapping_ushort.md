# ClearClusterTmMapping(ushort *)

- ea: `0x18001dfb0`
- end: `0x18001e1b0`
- name: `?ClearClusterTmMapping@@YAJPEAG@Z`
- size: `512`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800830c4`

## callees

- `0x1800063b0`
- `0x18001a134`
- `0x18001dfb0`
- `0x180023b7c`
- `0x1800846c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e08a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e00e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e08a`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001e033`
- `MTXCLU!FailedClusterAPIToEventLog` at `0x18001e033`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001e192`
- `CLUSAPI!ClusterRegCloseKey` at `0x18001e192`
- `CLUSAPI!OpenClusterEx` at `0x18001e000`
- `CLUSAPI!OpenClusterEx` at `0x18001e000`
- `CLUSAPI!CloseCluster` at `0x18001e19b`
- `CLUSAPI!CloseCluster` at `0x18001e19b`
- `CLUSAPI!GetClusterKey` at `0x18001e07c`
- `CLUSAPI!GetClusterKey` at `0x18001e07c`

## string_xrefs

- `0x18001e04a`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001e0b0`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001e123`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001e168`: `com\complus\dtc\dtc\msdtc\src\msdtc.cpp`
- `0x18001e03e`: `OpenClusterEx failed`
- `0x18001e02c`: `OpenClusterEx`
- `0x18001dfcc`: `Service`
- `0x18001dfd8`: `ComplusApp`
- `0x18001e117`: `DeleteTmMappingRegKey failed`
- `0x18001dfe9`: `ClearClusterTmMapping (com\complus\dtc\dtc\msdtc\src\msdtc.cpp@3042): ClearClusterTmMapping: NULL != pwszMappingName`

## pseudocode

```c
__int64 __fastcall ClearClusterTmMapping(unsigned __int16 *a1)
{
  struct _HCLUSTER *v2; // rax
  struct _HCLUSTER *v3; // rbp
  signed int v4; // eax
  unsigned int v5; // ebx
  HKEY ClusterKey; // r14
  signed int LastError; // eax
  int v8; // esi
  int i; // edi
  int v10; // eax
  __int64 v12; // [rsp+28h] [rbp-70h]
  unsigned __int16 *v13[11]; // [rsp+40h] [rbp-58h]

  v13[0] = L"Exe";
  v13[1] = L"Service";
  v13[2] = L"ComplusApp";
  if ( !a1 )
    DtcInternalErrorW(
      L"ClearClusterTmMapping (com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp@3042): ClearClusterTmMapping: NULL != pwszMappingName");
  v2 = OpenClusterEx(0, 0x2000000u, 0);
  v3 = v2;
  if ( v2 )
  {
    ClusterKey = GetClusterKey(v2, 0x20119u);
    if ( ClusterKey )
    {
      v5 = 0;
      v8 = 0;
      for ( i = 0; i < 3; ++i )
      {
        v10 = DeleteTmMappingRegKey(ClusterKey, v13[i], a1, 0);
        v5 = v10;
        if ( v10 >= 0 )
        {
          ++v8;
        }
        else
        {
          if ( v10 != -2147024894 )
          {
            LODWORD(v12) = v10;
            TraceStringInline(
              3,
              1,
              L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
              3074,
              L"ClearClusterTmMapping",
              v12,
              L"DeleteTmMappingRegKey failed");
            goto LABEL_21;
          }
          v5 = 0;
        }
      }
      if ( !v8 )
      {
        DisplayLocMessageToConsole(0x69u);
        LODWORD(v12) = v5;
        TraceStringInline(
          3,
          1,
          L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
          3085,
          L"ClearClusterTmMapping",
          v12,
          L"No such transaction mapping found");
        v5 = -2147467259;
      }
LABEL_21:
      ClusterRegCloseKey(ClusterKey);
    }
    else
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v12) = v5;
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
        3057,
        L"ClearClusterTmMapping",
        v12,
        L"GetClusterKey failed");
    }
    CloseCluster(v3);
  }
  else
  {
    v4 = GetLastError();
    v5 = v4;
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    FailedClusterAPIToEventLog(L"OpenClusterEx", v5, L" ");
    LODWORD(v12) = v5;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\msdtc\\src\\msdtc.cpp",
      3049,
      L"ClearClusterTmMapping",
      v12,
      L"OpenClusterEx failed");
  }
  return v5;
}

```

## disassembly

```asm
0x18001dfb0  push    rbx
0x18001dfb2  push    rbp
0x18001dfb3  push    rsi
0x18001dfb4  push    rdi
0x18001dfb5  push    r14
0x18001dfb7  push    r15
0x18001dfb9  sub     rsp, 68h
0x18001dfbd  lea     rax, aExe; "Exe"
0x18001dfc4  mov     r15, rcx
0x18001dfc7  mov     [rsp+98h+var_58], rax
0x18001dfcc  lea     rax, aService; "Service"
0x18001dfd3  mov     [rsp+98h+var_50], rax
0x18001dfd8  lea     rax, aComplusapp; "ComplusApp"
0x18001dfdf  mov     [rsp+98h+var_48], rax
0x18001dfe4  test    rcx, rcx
0x18001dfe7  jnz     short loc_18001DFF6
0x18001dfe9  lea     rcx, aClearclustertm_0; "ClearClusterTmMapping (com\\complus\\dt"...
0x18001dff0  call    ?DtcInternalErrorW@@YAXPEBG@Z; DtcInternalErrorW(ushort const *)
0x18001dff6  xor     r8d, r8d; GrantedAccess
0x18001dff9  mov     edx, 2000000h; DesiredAccess
0x18001dffe  xor     ecx, ecx; lpszClusterName
0x18001e000  call    cs:__imp_OpenClusterEx
0x18001e006  mov     rbp, rax
0x18001e009  test    rax, rax
0x18001e00c  jnz     short loc_18001E074
0x18001e00e  call    cs:__imp_GetLastError
0x18001e014  mov     ebx, eax
0x18001e016  test    eax, eax
0x18001e018  jle     short loc_18001E023
0x18001e01a  movzx   ebx, ax
0x18001e01d  or      ebx, 80070000h
0x18001e023  lea     r8, asc_180127724; " "
0x18001e02a  mov     edx, ebx
0x18001e02c  lea     rcx, aOpenclusterex; "OpenClusterEx"
0x18001e033  call    cs:__imp_FailedClusterAPIToEventLog
0x18001e039  mov     edx, 1
0x18001e03e  lea     rax, aOpenclusterexF; "OpenClusterEx failed"
0x18001e045  mov     [rsp+98h+var_68], rax
0x18001e04a  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001e051  lea     rax, aClearclustertm; "ClearClusterTmMapping"
0x18001e058  mov     dword ptr [rsp+98h+var_70], ebx
0x18001e05c  mov     r9d, 0BE9h
0x18001e062  mov     [rsp+98h+var_78], rax
0x18001e067  lea     ecx, [rdx+2]
0x18001e06a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e06f  jmp     loc_18001E1A1
0x18001e074  mov     edx, 20119h; samDesired
0x18001e079  mov     rcx, rbp; hCluster
0x18001e07c  call    cs:__imp_GetClusterKey
0x18001e082  mov     r14, rax
0x18001e085  test    rax, rax
0x18001e088  jnz     short loc_18001E0DA
0x18001e08a  call    cs:__imp_GetLastError
0x18001e090  mov     ebx, eax
0x18001e092  test    eax, eax
0x18001e094  jle     short loc_18001E09F
0x18001e096  movzx   ebx, ax
0x18001e099  or      ebx, 80070000h
0x18001e09f  mov     edx, 1
0x18001e0a4  lea     rax, aGetclusterkeyF; "GetClusterKey failed"
0x18001e0ab  mov     [rsp+98h+var_68], rax
0x18001e0b0  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001e0b7  lea     rax, aClearclustertm; "ClearClusterTmMapping"
0x18001e0be  mov     dword ptr [rsp+98h+var_70], ebx
0x18001e0c2  mov     r9d, 0BF1h
0x18001e0c8  mov     [rsp+98h+var_78], rax
0x18001e0cd  lea     ecx, [rdx+2]
0x18001e0d0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e0d5  jmp     loc_18001E198
0x18001e0da  xor     ebx, ebx
0x18001e0dc  xor     esi, esi
0x18001e0de  xor     edi, edi
0x18001e0e0  cmp     edi, 3
0x18001e0e3  jge     short loc_18001E14A
0x18001e0e5  movsxd  rdx, edi
0x18001e0e8  xor     r9d, r9d; int
0x18001e0eb  mov     r8, r15; unsigned __int16 *
0x18001e0ee  mov     rcx, r14; hKey
0x18001e0f1  mov     rdx, [rsp+rdx*8+98h+var_58]; unsigned __int16 *
0x18001e0f6  call    ?DeleteTmMappingRegKey@@YAJPEAUHKEY__@@PEAG1H@Z; DeleteTmMappingRegKey(HKEY__ *,ushort *,ushort *,int)
0x18001e0fb  mov     ebx, eax
0x18001e0fd  test    eax, eax
0x18001e0ff  jns     short loc_18001E10C
0x18001e101  cmp     eax, 80070002h
0x18001e106  jnz     short loc_18001E112
0x18001e108  xor     ebx, ebx
0x18001e10a  jmp     short loc_18001E10E
0x18001e10c  inc     esi
0x18001e10e  inc     edi
0x18001e110  jmp     short loc_18001E0E0
0x18001e112  mov     edx, 1
0x18001e117  lea     rax, aDeletetmmappin_2; "DeleteTmMappingRegKey failed"
0x18001e11e  mov     [rsp+98h+var_68], rax
0x18001e123  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001e12a  lea     rax, aClearclustertm; "ClearClusterTmMapping"
0x18001e131  mov     dword ptr [rsp+98h+var_70], ebx
0x18001e135  mov     r9d, 0C02h
0x18001e13b  mov     [rsp+98h+var_78], rax
0x18001e140  lea     ecx, [rdx+2]
0x18001e143  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e148  jmp     short loc_18001E18F
0x18001e14a  test    esi, esi
0x18001e14c  jnz     short loc_18001E18F
0x18001e14e  lea     ecx, [rsi+69h]; uID
0x18001e151  call    ?DisplayLocMessageToConsole@@YAXI@Z; DisplayLocMessageToConsole(uint)
0x18001e156  lea     rax, aNoSuchTransact; "No such transaction mapping found"
0x18001e15d  mov     r9d, 0C0Dh
0x18001e163  mov     [rsp+98h+var_68], rax
0x18001e168  lea     r8, aComComplusDtcD_88; "com\\complus\\dtc\\dtc\\msdtc\\src\\msd"...
0x18001e16f  lea     rax, aClearclustertm; "ClearClusterTmMapping"
0x18001e176  mov     dword ptr [rsp+98h+var_70], ebx
0x18001e17a  lea     edx, [rsi+1]
0x18001e17d  mov     [rsp+98h+var_78], rax
0x18001e182  lea     ecx, [rsi+3]
0x18001e185  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001e18a  mov     ebx, 80004005h
0x18001e18f  mov     rcx, r14; hKey
0x18001e192  call    cs:__imp_ClusterRegCloseKey
0x18001e198  mov     rcx, rbp; hCluster
0x18001e19b  call    cs:__imp_CloseCluster
0x18001e1a1  mov     eax, ebx
0x18001e1a3  add     rsp, 68h
0x18001e1a7  pop     r15
0x18001e1a9  pop     r14
0x18001e1ab  pop     rdi
0x18001e1ac  pop     rsi
0x18001e1ad  pop     rbp
0x18001e1ae  pop     rbx
0x18001e1af  retn
```
