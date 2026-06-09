# PushApphelpp_ShowApphelp(_PUSHAPPHELP_PAYLOAD *)

- ea: `0x1800b1f44`
- end: `0x1800b22e4`
- name: `?PushApphelpp_ShowApphelp@@YAKPEAU_PUSHAPPHELP_PAYLOAD@@@Z`
- size: `928`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800b15f0`

## callees

- `0x180012920`
- `0x180019c84`
- `0x180038674`
- `0x18007a9cf`
- `0x1800b1f44`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800b21a6`
- `msvcrt!swprintf_s` at `0x1800b21e1`
- `msvcrt!swprintf_s` at `0x1800b21a6`
- `msvcrt!swprintf_s` at `0x1800b21e1`
- `msvcrt!wcscat_s` at `0x1800b20c1`
- `msvcrt!wcscat_s` at `0x1800b20d3`
- `msvcrt!wcscat_s` at `0x1800b20e5`
- `msvcrt!wcscat_s` at `0x1800b20f7`
- `msvcrt!wcscat_s` at `0x1800b2109`
- `msvcrt!wcscat_s` at `0x1800b211b`
- `msvcrt!wcscat_s` at `0x1800b212d`
- `msvcrt!wcscat_s` at `0x1800b213f`
- `msvcrt!wcscat_s` at `0x1800b2151`
- `msvcrt!wcscat_s` at `0x1800b2163`
- `msvcrt!wcscat_s` at `0x1800b2175`
- `msvcrt!wcscat_s` at `0x1800b2187`
- `msvcrt!wcscat_s` at `0x1800b21b5`
- `msvcrt!wcscat_s` at `0x1800b21c7`
- `msvcrt!wcscat_s` at `0x1800b21f0`
- `msvcrt!wcscat_s` at `0x1800b20c1`
- `msvcrt!wcscat_s` at `0x1800b20d3`
- `msvcrt!wcscat_s` at `0x1800b20e5`
- `msvcrt!wcscat_s` at `0x1800b20f7`
- `msvcrt!wcscat_s` at `0x1800b2109`
- `msvcrt!wcscat_s` at `0x1800b211b`
- `msvcrt!wcscat_s` at `0x1800b212d`
- `msvcrt!wcscat_s` at `0x1800b213f`
- `msvcrt!wcscat_s` at `0x1800b2151`
- `msvcrt!wcscat_s` at `0x1800b2163`
- `msvcrt!wcscat_s` at `0x1800b2175`
- `msvcrt!wcscat_s` at `0x1800b2187`
- `msvcrt!wcscat_s` at `0x1800b21b5`
- `msvcrt!wcscat_s` at `0x1800b21c7`
- `msvcrt!wcscat_s` at `0x1800b21f0`
- `msvcrt!wcscpy_s` at `0x1800b20af`
- `msvcrt!wcscpy_s` at `0x1800b20af`
- `ntdll!RtlGetNtSystemRoot` at `0x1800b209c`
- `ntdll!RtlGetNtSystemRoot` at `0x1800b209c`
- `ntdll!RtlAllocateHeap` at `0x1800b1fcd`
- `ntdll!RtlAllocateHeap` at `0x1800b1fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b206d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b224b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2027`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b206d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b224b`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800b2241`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessAsUserW` at `0x1800b2241`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b226f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b227e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b229e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b226f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b227e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b229e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b228e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b228e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b2063`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800b2063`
- `WTSAPI32!WTSQueryUserToken` at `0x1800b201d`
- `WTSAPI32!WTSQueryUserToken` at `0x1800b201d`

## string_xrefs

- `0x1800b2031`: `Failed to get user token information from Session=%d [%d]`
- `0x1800b2073`: `Failed to get Active sessions user SID [%d]`
- `0x1800b20b5`: `\System32\pcaui.exe`

## pseudocode

```c
__int64 __fastcall PushApphelpp_ShowApphelp(const wchar_t *a1)
{
  DWORD LastError; // ebx
  wchar_t *Heap; // rdi
  ULONG v4; // esi
  DWORD v5; // eax
  const char *v6; // r9
  int v7; // r8d
  const wchar_t *NtSystemRoot; // rax
  LPSECURITY_ATTRIBUTES lpThreadAttributes; // [rsp+20h] [rbp-E0h]
  ULONG SessionId; // [rsp+60h] [rbp-A0h] BYREF
  void *phToken; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR StringSid; // [rsp+70h] [rbp-90h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+78h] [rbp-88h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Buffer[16]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int8 Sid[80]; // [rsp+120h] [rbp+20h] BYREF

  StringSid = 0;
  SessionId = 0;
  phToken = 0;
  memset_0(Sid, 0, 0x44u);
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  LastError = 8;
  Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2000u);
  if ( !Heap )
  {
    AslLogCallPrintf(1, (unsigned int)"PushApphelpp_ShowApphelp", 440, (unsigned int)"Out of memory");
    goto LABEL_12;
  }
  if ( !PcaUtilityGetActiveUserSessionSid(&SessionId, Sid) )
  {
    v4 = SessionId;
    if ( !WTSQueryUserToken(SessionId, &phToken) )
    {
      LastError = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"PushApphelpp_ShowApphelp",
        461,
        (unsigned int)"Failed to get user token information from Session=%d [%d]",
        v4,
        LastError);
      goto LABEL_12;
    }
    if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    {
      v5 = GetLastError();
      v6 = "Failed to get Active sessions user SID [%d]";
      v7 = 471;
LABEL_8:
      LODWORD(lpThreadAttributes) = v5;
      LastError = v5;
      AslLogCallPrintf(1, (unsigned int)"PushApphelpp_ShowApphelp", v7, (_DWORD)v6, lpThreadAttributes);
      goto LABEL_12;
    }
    NtSystemRoot = (const wchar_t *)RtlGetNtSystemRoot();
    wcscpy_s(Heap, 0x1000u, NtSystemRoot);
    wcscat_s(Heap, 0x1000u, L"\\System32\\pcaui.exe");
    wcscat_s(Heap, 0x1000u, L" /a \"");
    wcscat_s(Heap, 0x1000u, a1 + 878);
    wcscat_s(Heap, 0x1000u, L"\"");
    wcscat_s(Heap, 0x1000u, L" /v \"");
    wcscat_s(Heap, 0x1000u, a1 + 350);
    wcscat_s(Heap, 0x1000u, L"\"");
    wcscat_s(Heap, 0x1000u, L" /g ");
    wcscat_s(Heap, 0x1000u, L"{11111111-1111-1111-1111-111111111111}");
    wcscat_s(Heap, 0x1000u, L" /x ");
    wcscat_s(Heap, 0x1000u, L"{00000000-0000-0000-0000-000000000000}");
    wcscat_s(Heap, 0x1000u, L" /f ");
    swprintf_s(Buffer, 0x10u, L"%d", *((unsigned int *)a1 + 436));
    wcscat_s(Heap, 0x1000u, Buffer);
    wcscat_s(Heap, 0x1000u, L" /b ");
    swprintf_s(Buffer, 0x10u, L"%d", *((unsigned int *)a1 + 437));
    wcscat_s(Heap, 0x1000u, Buffer);
    if ( !CreateProcessAsUserW(phToken, 0, Heap, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v5 = GetLastError();
      v6 = "Could not launch process %d";
      v7 = 544;
      goto LABEL_8;
    }
  }
  LastError = 0;
LABEL_12:
  if ( ProcessInformation.hProcess )
    CloseHandle(ProcessInformation.hProcess);
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  if ( StringSid )
    LocalFree(StringSid);
  if ( phToken )
    CloseHandle(phToken);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return LastError;
}

```

## disassembly

```asm
0x1800b1f44  mov     [rsp-8+arg_8], rbx
0x1800b1f49  mov     [rsp-8+arg_10], rsi
0x1800b1f4e  push    rbp
0x1800b1f4f  push    rdi
0x1800b1f50  push    r14
0x1800b1f52  lea     rbp, [rsp-80h]
0x1800b1f57  sub     rsp, 180h
0x1800b1f5e  mov     rax, cs:__security_cookie
0x1800b1f65  xor     rax, rsp
0x1800b1f68  mov     [rbp+90h+var_20], rax
0x1800b1f6c  xor     edx, edx; Val
0x1800b1f6e  mov     [rsp+190h+StringSid], 0
0x1800b1f77  mov     r14, rcx
0x1800b1f7a  mov     [rsp+190h+SessionId], 0
0x1800b1f82  lea     rcx, [rbp+90h+Sid]; void *
0x1800b1f86  mov     [rsp+190h+phToken], 0
0x1800b1f8f  lea     r8d, [rdx+44h]; Size
0x1800b1f93  call    memset_0
0x1800b1f98  xor     edx, edx; Val
0x1800b1f9a  lea     rcx, [rbp+90h+StartupInfo]; void *
0x1800b1f9e  lea     r8d, [rdx+68h]; Size
0x1800b1fa2  call    memset_0
0x1800b1fa7  xor     eax, eax
0x1800b1fa9  xorps   xmm0, xmm0
0x1800b1fac  movups  xmmword ptr [rsp+190h+ProcessInformation.hProcess], xmm0
0x1800b1fb1  mov     qword ptr [rbp+90h+ProcessInformation.dwProcessId], rax
0x1800b1fb5  mov     r8d, 2000h; Size
0x1800b1fbb  mov     rcx, gs:60h
0x1800b1fc4  lea     ebx, [rax+8]
0x1800b1fc7  mov     edx, ebx; Flags
0x1800b1fc9  mov     rcx, [rcx+30h]; HeapHandle
0x1800b1fcd  call    cs:__imp_RtlAllocateHeap
0x1800b1fd3  mov     rdi, rax
0x1800b1fd6  test    rax, rax
0x1800b1fd9  jnz     short loc_1800B1FFC
0x1800b1fdb  lea     r9, aOutOfMemory; "Out of memory"
0x1800b1fe2  mov     r8d, 1B8h
0x1800b1fe8  lea     rdx, aPushapphelppSh; "PushApphelpp_ShowApphelp"
0x1800b1fef  lea     ecx, [rbx-7]
0x1800b1ff2  call    AslLogCallPrintf
0x1800b1ff7  jmp     loc_1800B2265
0x1800b1ffc  lea     rdx, [rbp+90h+Sid]; unsigned __int8 *
0x1800b2000  lea     rcx, [rsp+190h+SessionId]; unsigned int *
0x1800b2005  call    ?PcaUtilityGetActiveUserSessionSid@@YAKPEAKPEAE@Z; PcaUtilityGetActiveUserSessionSid(ulong *,uchar *)
0x1800b200a  test    eax, eax
0x1800b200c  jnz     loc_1800B2263
0x1800b2012  mov     esi, [rsp+190h+SessionId]
0x1800b2016  lea     rdx, [rsp+190h+phToken]; phToken
0x1800b201b  mov     ecx, esi; SessionId
0x1800b201d  call    cs:__imp_WTSQueryUserToken
0x1800b2023  test    eax, eax
0x1800b2025  jnz     short loc_1800B205A
0x1800b2027  call    cs:__imp_GetLastError
0x1800b202d  mov     [rsp+190h+bInheritHandles], eax
0x1800b2031  lea     r9, aFailedToGetUse; "Failed to get user token information fr"...
0x1800b2038  mov     r8d, 1CDh
0x1800b203e  mov     dword ptr [rsp+190h+lpThreadAttributes], esi
0x1800b2042  lea     rdx, aPushapphelppSh; "PushApphelpp_ShowApphelp"
0x1800b2049  mov     ecx, 1
0x1800b204e  mov     ebx, eax
0x1800b2050  call    AslLogCallPrintf
0x1800b2055  jmp     loc_1800B2265
0x1800b205a  lea     rdx, [rsp+190h+StringSid]; StringSid
0x1800b205f  lea     rcx, [rbp+90h+Sid]; Sid
0x1800b2063  call    cs:__imp_ConvertSidToStringSidW
0x1800b2069  test    eax, eax
0x1800b206b  jnz     short loc_1800B209C
0x1800b206d  call    cs:__imp_GetLastError
0x1800b2073  lea     r9, aFailedToGetAct_1; "Failed to get Active sessions user SID "...
0x1800b207a  mov     r8d, 1D7h
0x1800b2080  lea     rdx, aPushapphelppSh; "PushApphelpp_ShowApphelp"
0x1800b2087  mov     dword ptr [rsp+190h+lpThreadAttributes], eax
0x1800b208b  mov     ecx, 1
0x1800b2090  mov     ebx, eax
0x1800b2092  call    AslLogCallPrintf
0x1800b2097  jmp     loc_1800B2265
0x1800b209c  call    cs:__imp_RtlGetNtSystemRoot
0x1800b20a2  mov     esi, 1000h
0x1800b20a7  mov     rcx, rdi; Destination
0x1800b20aa  mov     r8, rax; Source
0x1800b20ad  mov     edx, esi; SizeInWords
0x1800b20af  call    cs:__imp_wcscpy_s
0x1800b20b5  lea     r8, aSystem32PcauiE; "\\System32\\pcaui.exe"
0x1800b20bc  mov     edx, esi; SizeInWords
0x1800b20be  mov     rcx, rdi; Destination
0x1800b20c1  call    cs:__imp_wcscat_s
0x1800b20c7  lea     r8, aA; " /a \""
0x1800b20ce  mov     edx, esi; SizeInWords
0x1800b20d0  mov     rcx, rdi; Destination
0x1800b20d3  call    cs:__imp_wcscat_s
0x1800b20d9  lea     r8, [r14+6DCh]; Source
0x1800b20e0  mov     edx, esi; SizeInWords
0x1800b20e2  mov     rcx, rdi; Destination
0x1800b20e5  call    cs:__imp_wcscat_s
0x1800b20eb  lea     r8, asc_18011A888; "\""
0x1800b20f2  mov     edx, esi; SizeInWords
0x1800b20f4  mov     rcx, rdi; Destination
0x1800b20f7  call    cs:__imp_wcscat_s
0x1800b20fd  lea     r8, aV_0; " /v \""
0x1800b2104  mov     edx, esi; SizeInWords
0x1800b2106  mov     rcx, rdi; Destination
0x1800b2109  call    cs:__imp_wcscat_s
0x1800b210f  lea     r8, [r14+2BCh]; Source
0x1800b2116  mov     edx, esi; SizeInWords
0x1800b2118  mov     rcx, rdi; Destination
0x1800b211b  call    cs:__imp_wcscat_s
0x1800b2121  lea     r8, asc_18011A888; "\""
0x1800b2128  mov     edx, esi; SizeInWords
0x1800b212a  mov     rcx, rdi; Destination
0x1800b212d  call    cs:__imp_wcscat_s
0x1800b2133  lea     r8, aG; " /g "
0x1800b213a  mov     edx, esi; SizeInWords
0x1800b213c  mov     rcx, rdi; Destination
0x1800b213f  call    cs:__imp_wcscat_s
0x1800b2145  lea     r8, a11111111111111; "{11111111-1111-1111-1111-111111111111}"
0x1800b214c  mov     edx, esi; SizeInWords
0x1800b214e  mov     rcx, rdi; Destination
0x1800b2151  call    cs:__imp_wcscat_s
0x1800b2157  lea     r8, asc_18011FA00; " /x "
0x1800b215e  mov     edx, esi; SizeInWords
0x1800b2160  mov     rcx, rdi; Destination
0x1800b2163  call    cs:__imp_wcscat_s
0x1800b2169  lea     r8, a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x1800b2170  mov     edx, esi; SizeInWords
0x1800b2172  mov     rcx, rdi; Destination
0x1800b2175  call    cs:__imp_wcscat_s
0x1800b217b  lea     r8, asc_18011FB50; " /f "
0x1800b2182  mov     edx, esi; SizeInWords
0x1800b2184  mov     rcx, rdi; Destination
0x1800b2187  call    cs:__imp_wcscat_s
0x1800b218d  mov     r9d, [r14+6D0h]
0x1800b2194  lea     r8, aD; "%d"
0x1800b219b  mov     ebx, 10h
0x1800b21a0  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800b21a4  mov     edx, ebx; BufferCount
0x1800b21a6  call    cs:__imp_swprintf_s
0x1800b21ac  lea     r8, [rbp+90h+Buffer]; Source
0x1800b21b0  mov     edx, esi; SizeInWords
0x1800b21b2  mov     rcx, rdi; Destination
0x1800b21b5  call    cs:__imp_wcscat_s
0x1800b21bb  lea     r8, aB; " /b "
0x1800b21c2  mov     edx, esi; SizeInWords
0x1800b21c4  mov     rcx, rdi; Destination
0x1800b21c7  call    cs:__imp_wcscat_s
0x1800b21cd  mov     r9d, [r14+6D4h]
0x1800b21d4  lea     r8, aD; "%d"
0x1800b21db  mov     edx, ebx; BufferCount
0x1800b21dd  lea     rcx, [rbp+90h+Buffer]; Buffer
0x1800b21e1  call    cs:__imp_swprintf_s
0x1800b21e7  lea     r8, [rbp+90h+Buffer]; Source
0x1800b21eb  mov     edx, esi; SizeInWords
0x1800b21ed  mov     rcx, rdi; Destination
0x1800b21f0  call    cs:__imp_wcscat_s
0x1800b21f6  lea     rax, [rsp+190h+ProcessInformation]
0x1800b21fb  mov     [rsp+190h+lpProcessInformation], rax; lpProcessInformation
0x1800b2200  lea     rax, [rbp+90h+StartupInfo]
0x1800b2204  mov     [rsp+190h+lpStartupInfo], rax; lpStartupInfo
0x1800b2209  mov     rcx, [rsp+190h+phToken]; hToken
0x1800b220e  xor     r9d, r9d; lpProcessAttributes
0x1800b2211  mov     [rsp+190h+lpCurrentDirectory], 0; lpCurrentDirectory
0x1800b221a  mov     r8, rdi; lpCommandLine
0x1800b221d  mov     [rsp+190h+lpEnvironment], 0; lpEnvironment
0x1800b2226  xor     edx, edx; lpApplicationName
0x1800b2228  mov     [rsp+190h+dwCreationFlags], 0; dwCreationFlags
0x1800b2230  mov     [rsp+190h+bInheritHandles], 0; bInheritHandles
0x1800b2238  mov     [rsp+190h+lpThreadAttributes], 0; lpThreadAttributes
0x1800b2241  call    cs:__imp_CreateProcessAsUserW
0x1800b2247  test    eax, eax
0x1800b2249  jnz     short loc_1800B2263
0x1800b224b  call    cs:__imp_GetLastError
0x1800b2251  lea     r9, aCouldNotLaunch; "Could not launch process %d"
0x1800b2258  mov     r8d, 220h
0x1800b225e  jmp     loc_1800B2080
0x1800b2263  xor     ebx, ebx
0x1800b2265  mov     rcx, [rsp+190h+ProcessInformation.hProcess]; hObject
0x1800b226a  test    rcx, rcx
0x1800b226d  jz      short loc_1800B2275
0x1800b226f  call    cs:__imp_CloseHandle
0x1800b2275  mov     rcx, [rbp+90h+ProcessInformation.hThread]; hObject
0x1800b2279  test    rcx, rcx
0x1800b227c  jz      short loc_1800B2284
0x1800b227e  call    cs:__imp_CloseHandle
0x1800b2284  mov     rcx, [rsp+190h+StringSid]; hMem
0x1800b2289  test    rcx, rcx
0x1800b228c  jz      short loc_1800B2294
0x1800b228e  call    cs:__imp_LocalFree
0x1800b2294  mov     rcx, [rsp+190h+phToken]; hObject
0x1800b2299  test    rcx, rcx
0x1800b229c  jz      short loc_1800B22A4
0x1800b229e  call    cs:__imp_CloseHandle
0x1800b22a4  test    rdi, rdi
0x1800b22a7  jz      short loc_1800B22BE
0x1800b22a9  mov     rcx, gs:60h
0x1800b22b2  mov     rdx, rdi
0x1800b22b5  mov     rcx, [rcx+30h]
0x1800b22b9  call    AslFree
0x1800b22be  mov     eax, ebx
0x1800b22c0  mov     rcx, [rbp+90h+var_20]
0x1800b22c4  xor     rcx, rsp; StackCookie
0x1800b22c7  call    __security_check_cookie
0x1800b22cc  lea     r11, [rsp+190h+var_10]
0x1800b22d4  mov     rbx, [r11+28h]
0x1800b22d8  mov     rsi, [r11+30h]
0x1800b22dc  mov     rsp, r11
0x1800b22df  pop     r14
0x1800b22e1  pop     rdi
0x1800b22e2  pop     rbp
0x1800b22e3  retn
```
