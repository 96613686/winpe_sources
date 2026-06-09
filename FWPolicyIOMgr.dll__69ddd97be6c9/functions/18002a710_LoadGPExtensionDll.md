# LoadGPExtensionDll

- ea: `0x18002a710`
- end: `0x18002a863`
- name: `LoadGPExtensionDll`
- size: `339`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002a6b0`

## callees

- `0x1800041d0`
- `0x1800042c4`
- `0x18001e9ac`
- `0x18001eb5c`
- `0x18002a4d8`
- `0x18002a710`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a7e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002a7e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a7fb`
- `fwbase!FwCriticalSectionEnter` at `0x18002a725`
- `fwbase!FwCriticalSectionEnter` at `0x18002a725`
- `fwbase!FwCriticalSectionLeave` at `0x18002a851`
- `fwbase!FwCriticalSectionLeave` at `0x18002a851`
- `fwbase!FwHResultToWindowsError` at `0x18002a798`
- `fwbase!FwHResultToWindowsError` at `0x18002a798`

## string_xrefs

- `0x18002a76f`: `wfapigp.dll`
- `0x18002a787`: `wfapigp.dll`

## pseudocode

```c
__int64 LoadGPExtensionDll()
{
  DWORD v0; // ebx
  __int64 v1; // rax
  unsigned __int64 v2; // rdx
  unsigned int v3; // eax
  DWORD LastError; // eax
  LPCOLESTR v5; // rcx
  __int64 v6; // rdx

  v0 = 0;
  FwCriticalSectionEnter(&g_fwExtensionDllLock);
  v1 = -1;
  do
    ++v1;
  while ( *(&g_wszWfApiGp + v1) );
  if ( v1 || (int)ReadGPDllNameFromReg() >= 0 )
    goto LABEL_28;
  if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids, L"wfapigp.dll");
  v3 = StringCchCopyW(&g_wszWfApiGp, v2, L"wfapigp.dll");
  LastError = FwHResultToWindowsError(v3);
  v0 = LastError;
  if ( !LastError )
  {
LABEL_28:
    if ( g_hWfApiGpDll
      || (g_hWfApiGpDll = LoadLibraryExW(&g_wszWfApiGp, 0, 0)) != 0
      || (LastError = GetLastError(), (v0 = LastError) == 0) )
    {
      if ( !g_pfnResolveGPONames )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !g_pFwGPLockFn )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !g_pFwGPUnlockFn )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    else
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 17;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (LPCOLESTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v6 = 16;
LABEL_12:
      WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids, LastError);
    }
  }
  FwCriticalSectionLeave(&g_fwExtensionDllLock);
  return v0;
}

```

## disassembly

```asm
0x18002a710  push    rbx
0x18002a712  push    rsi
0x18002a713  push    rdi
0x18002a714  push    r14
0x18002a716  sub     rsp, 28h
0x18002a71a  xor     edi, edi
0x18002a71c  lea     rcx, ?g_fwExtensionDllLock@@3UFW_CRITICAL_SECTION_@@A; FW_CRITICAL_SECTION_ g_fwExtensionDllLock
0x18002a723  mov     ebx, edi
0x18002a725  call    cs:__imp_FwCriticalSectionEnter
0x18002a72b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a72f  lea     r14, ?g_wszWfApiGp@@3PAGA; ushort near * g_wszWfApiGp
0x18002a736  inc     rax
0x18002a739  cmp     [r14+rax*2], di
0x18002a73e  jnz     short loc_18002A736
0x18002a740  lea     rsi, WPP_GLOBAL_Control
0x18002a747  test    rax, rax
0x18002a74a  jnz     loc_18002A7D8
0x18002a750  call    ?ReadGPDllNameFromReg@@YAJXZ; ReadGPDllNameFromReg(void)
0x18002a755  test    eax, eax
0x18002a757  jns     short loc_18002A7D8
0x18002a759  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a760  cmp     rcx, rsi
0x18002a763  jz      short loc_18002A787
0x18002a765  test    byte ptr [rcx+1Ch], 2
0x18002a769  jz      short loc_18002A787
0x18002a76b  mov     rcx, [rcx+10h]
0x18002a76f  lea     r9, aWfapigpDll; "wfapigp.dll"
0x18002a776  mov     edx, 0Fh
0x18002a77b  lea     r8, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids
0x18002a782  call    WPP_SF_S
0x18002a787  lea     r8, aWfapigpDll; "wfapigp.dll"
0x18002a78e  mov     rcx, r14; unsigned __int16 *
0x18002a791  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002a796  mov     ecx, eax
0x18002a798  call    cs:__imp_FwHResultToWindowsError
0x18002a79e  mov     ebx, eax
0x18002a7a0  test    eax, eax
0x18002a7a2  jz      short loc_18002A7D8
0x18002a7a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a7ab  cmp     rcx, rsi
0x18002a7ae  jz      loc_18002A84A
0x18002a7b4  test    byte ptr [rcx+1Ch], 1
0x18002a7b8  jz      loc_18002A84A
0x18002a7be  mov     edx, 10h
0x18002a7c3  mov     rcx, [rcx+10h]
0x18002a7c7  lea     r8, WPP_88e33fc0e55e3e954748c6f3ec37876e_Traceguids
0x18002a7ce  mov     r9d, eax
0x18002a7d1  call    WPP_SF_d
0x18002a7d6  jmp     short loc_18002A84A
0x18002a7d8  cmp     cs:?g_hWfApiGpDll@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hWfApiGpDll
0x18002a7df  jnz     short loc_18002A820
0x18002a7e1  xor     r8d, r8d; dwFlags
0x18002a7e4  xor     edx, edx; hFile
0x18002a7e6  mov     rcx, r14; lpLibFileName
0x18002a7e9  call    cs:__imp_LoadLibraryExW
0x18002a7ef  mov     cs:?g_hWfApiGpDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hWfApiGpDll
0x18002a7f6  test    rax, rax
0x18002a7f9  jnz     short loc_18002A820
0x18002a7fb  call    cs:__imp_GetLastError
0x18002a801  mov     ebx, eax
0x18002a803  test    eax, eax
0x18002a805  jz      short loc_18002A820
0x18002a807  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a80e  cmp     rcx, rsi
0x18002a811  jz      short loc_18002A84A
0x18002a813  test    byte ptr [rcx+1Ch], 1
0x18002a817  jz      short loc_18002A84A
0x18002a819  mov     edx, 11h
0x18002a81e  jmp     short loc_18002A7C3
0x18002a820  cmp     cs:?g_pfnResolveGPONames@@3P6AJPEAXU_tag_FW_BLOB_TYPE@@PEAU_tag_FW_BLOB_RULE@@@ZEA, rdi; long (*g_pfnResolveGPONames)(void *,_tag_FW_BLOB_TYPE,_tag_FW_BLOB_RULE *)
0x18002a827  jnz     short loc_18002A82E
0x18002a829  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a82e  cmp     cs:?g_pFwGPLockFn@@3P6APEAXXZEA, rdi; void * (*g_pFwGPLockFn)(void)
0x18002a835  jnz     short loc_18002A83C
0x18002a837  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a83c  cmp     cs:?g_pFwGPUnlockFn@@3P6AXPEAX@ZEA, rdi; void (*g_pFwGPUnlockFn)(void *)
0x18002a843  jnz     short loc_18002A84A
0x18002a845  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002a84a  lea     rcx, ?g_fwExtensionDllLock@@3UFW_CRITICAL_SECTION_@@A; FW_CRITICAL_SECTION_ g_fwExtensionDllLock
0x18002a851  call    cs:__imp_FwCriticalSectionLeave
0x18002a857  mov     eax, ebx
0x18002a859  add     rsp, 28h
0x18002a85d  pop     r14
0x18002a85f  pop     rdi
0x18002a860  pop     rsi
0x18002a861  pop     rbx
0x18002a862  retn
```
