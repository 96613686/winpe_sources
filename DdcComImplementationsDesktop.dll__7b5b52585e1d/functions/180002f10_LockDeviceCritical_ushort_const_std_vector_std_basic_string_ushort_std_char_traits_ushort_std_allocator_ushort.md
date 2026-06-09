# LockDeviceCritical(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180002f10`
- end: `0x180003093`
- name: `?LockDeviceCritical@@YAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `387`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002c50`

## callees

- `0x1800021d8`
- `0x1800026ac`
- `0x180002f10`
- `0x180004218`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002f86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002fd0`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000307e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000307e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x180002fc6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSLogoffSession` at `0x180002fc6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x180002f7c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x180002f7c`

## string_xrefs

- `0x180003068`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\ddccomimplementationsdesktop\ddccommandhandlerdesktop.cpp`
- `0x18000302a`: `CHR(hrSidsLock)`

## pseudocode

```c
__int64 __fastcall LockDeviceCritical(__int64 a1, __int64 a2)
{
  int v4; // edx
  int v5; // ecx
  signed int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  signed int LastError; // eax
  DWORD i; // edi
  signed int v11; // eax
  int v12; // eax
  char pCount; // [rsp+20h] [rbp-38h]
  const char *v15; // [rsp+28h] [rbp-30h]
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+30h] [rbp-28h] BYREF
  DWORD v17; // [rsp+70h] [rbp+18h] BYREF
  DWORD pLevel; // [rsp+78h] [rbp+20h] BYREF

  ppSessionInfo = 0;
  v17 = 0;
  pLevel = 1;
  if ( !(unsigned __int8)IsWTSFreeMemoryPresent()
    || !(unsigned __int8)IsWTSFreeMemoryPresent()
    || !(unsigned __int8)IsWTSFreeMemoryPresent() )
  {
    v6 = -2147467263;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_23;
    v15 = "CBR(IsWTSEnumerateSessionsExWPresent() && IsWTSLogoffSessionPresent() && IsWTSFreeMemoryPresent())";
    pCount = -59;
    goto LABEL_22;
  }
  v6 = 0;
  if ( WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &v17) )
    goto LABEL_8;
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( v6 >= 0 )
  {
LABEL_8:
    for ( i = 0; i < v17; ++i )
    {
      v7 = i;
      if ( ppSessionInfo[v7].pUserName )
      {
        if ( !WTSLogoffSession(0, ppSessionInfo[v7].SessionId, 1) )
        {
          v11 = GetLastError();
          v6 = v11;
          if ( v11 > 0 )
            v6 = (unsigned __int16)v11 | 0x80070000;
        }
      }
    }
  }
  v12 = DdcRegistry::LockToSids(v8, v7 * 56, a1, a2);
  if ( v6 < 0 )
  {
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
      goto LABEL_23;
    v15 = "CHR(hrSignOut)";
    pCount = -40;
LABEL_22:
    McTemplateU0dsqs_EventWriteTransfer(
      v5,
      v4,
      v6,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccommandh"
                    "andlerdesktop.cpp",
      pCount,
      (__int64)v15);
    goto LABEL_23;
  }
  v6 = v12;
  if ( v12 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      (unsigned int)"CHR(hrSidsLock)",
      v4,
      v12,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\ddccomimplementationsdesktop\\ddccommandh"
                    "andlerdesktop.cpp",
      217,
      (__int64)"CHR(hrSidsLock)");
LABEL_23:
  if ( ppSessionInfo )
    WTSFreeMemory(ppSessionInfo);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180002f10  mov     rax, rsp
0x180002f13  mov     [rax+8], rbx
0x180002f17  push    rbp
0x180002f18  push    rsi
0x180002f19  push    rdi
0x180002f1a  sub     rsp, 40h
0x180002f1e  mov     rsi, rdx
0x180002f21  mov     qword ptr [rax-28h], 0
0x180002f29  mov     rbp, rcx
0x180002f2c  mov     dword ptr [rax+18h], 0
0x180002f33  mov     dword ptr [rax+20h], 1
0x180002f3a  call    IsWTSFreeMemoryPresent
0x180002f3f  test    al, al
0x180002f41  jz      loc_180003043
0x180002f47  call    IsWTSFreeMemoryPresent
0x180002f4c  test    al, al
0x180002f4e  jz      loc_180003043
0x180002f54  call    IsWTSFreeMemoryPresent
0x180002f59  test    al, al
0x180002f5b  jz      loc_180003043
0x180002f61  lea     rax, [rsp+58h+arg_10]
0x180002f66  xor     r8d, r8d; Filter
0x180002f69  lea     r9, [rsp+58h+ppSessionInfo]; ppSessionInfo
0x180002f6e  mov     [rsp+58h+pCount], rax; pCount
0x180002f73  lea     rdx, [rsp+58h+pLevel]; pLevel
0x180002f78  xor     ecx, ecx; hServer
0x180002f7a  xor     ebx, ebx
0x180002f7c  call    cs:__imp_WTSEnumerateSessionsExW
0x180002f82  test    eax, eax
0x180002f84  jnz     short loc_180002F9F
0x180002f86  call    cs:__imp_GetLastError
0x180002f8c  mov     ebx, eax
0x180002f8e  test    eax, eax
0x180002f90  jle     short loc_180002F9B
0x180002f92  movzx   ebx, ax
0x180002f95  or      ebx, 80070000h
0x180002f9b  test    ebx, ebx
0x180002f9d  js      short loc_180002FED
0x180002f9f  xor     edi, edi
0x180002fa1  cmp     [rsp+58h+arg_10], edi
0x180002fa5  jbe     short loc_180002FED
0x180002fa7  mov     eax, edi
0x180002fa9  imul    rdx, rax, 38h ; '8'
0x180002fad  mov     rax, [rsp+58h+ppSessionInfo]
0x180002fb2  cmp     qword ptr [rdx+rax+20h], 0
0x180002fb8  jz      short loc_180002FE5
0x180002fba  mov     edx, [rdx+rax+8]; SessionId
0x180002fbe  mov     r8d, 1; bWait
0x180002fc4  xor     ecx, ecx; hServer
0x180002fc6  call    cs:__imp_WTSLogoffSession
0x180002fcc  test    eax, eax
0x180002fce  jnz     short loc_180002FE5
0x180002fd0  call    cs:__imp_GetLastError
0x180002fd6  mov     ebx, eax
0x180002fd8  test    eax, eax
0x180002fda  jle     short loc_180002FE5
0x180002fdc  movzx   ebx, ax
0x180002fdf  or      ebx, 80070000h
0x180002fe5  inc     edi
0x180002fe7  cmp     edi, [rsp+58h+arg_10]
0x180002feb  jb      short loc_180002FA7
0x180002fed  mov     r9, rsi
0x180002ff0  mov     r8, rbp
0x180002ff3  call    ?LockToSids@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; DdcRegistry::LockToSids(HKEY__ *,ushort const *,ushort const *,std::vector<std::wstring> &)
0x180002ff8  test    ebx, ebx
0x180002ffa  jns     short loc_18000301B
0x180002ffc  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003003  jz      short loc_180003074
0x180003005  lea     rax, aChrHrsignout; "CHR(hrSignOut)"
0x18000300c  mov     [rsp+58h+var_30], rax
0x180003011  mov     dword ptr [rsp+58h+pCount], 0D8h
0x180003019  jmp     short loc_180003065
0x18000301b  mov     ebx, eax
0x18000301d  test    eax, eax
0x18000301f  jns     short loc_180003074
0x180003021  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180003028  jz      short loc_180003074
0x18000302a  lea     rcx, aChrHrsidslock; "CHR(hrSidsLock)"
0x180003031  mov     r8d, eax
0x180003034  mov     [rsp+58h+var_30], rcx
0x180003039  mov     dword ptr [rsp+58h+pCount], 0D9h
0x180003041  jmp     short loc_180003068
0x180003043  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000304a  mov     ebx, 80004001h
0x18000304f  jz      short loc_180003074
0x180003051  lea     rax, aCbrIswtsenumer; "CBR(IsWTSEnumerateSessionsExWPresent() "...
0x180003058  mov     [rsp+58h+var_30], rax
0x18000305d  mov     dword ptr [rsp+58h+pCount], 0C5h
0x180003065  mov     r8d, ebx
0x180003068  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000306f  call    McTemplateU0dsqs_EventWriteTransfer
0x180003074  mov     rcx, [rsp+58h+ppSessionInfo]; pMemory
0x180003079  test    rcx, rcx
0x18000307c  jz      short loc_180003084
0x18000307e  call    cs:__imp_WTSFreeMemory
0x180003084  mov     eax, ebx
0x180003086  mov     rbx, [rsp+58h+arg_0]
0x18000308b  add     rsp, 40h
0x18000308f  pop     rdi
0x180003090  pop     rsi
0x180003091  pop     rbp
0x180003092  retn
```
