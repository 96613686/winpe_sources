# WmiRefresherStuff::LodCtrUnlodCtr(ushort const *,int)

- ea: `0x1400083dc`
- end: `0x14000873a`
- name: `?LodCtrUnlodCtr@WmiRefresherStuff@@AEAAJPEBGH@Z`
- size: `862`
- prototype: `__int64 __fastcall(HMODULE *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140007c10`

## callees

- `0x140005810`
- `0x140006918`
- `0x140006a78`
- `0x140006df0`
- `0x14000723c`
- `0x1400083dc`
- `0x140017010`

## import_xrefs

- `msvcrt!wcslen` at `0x140008565`
- `msvcrt!wcslen` at `0x140008571`
- `msvcrt!wcslen` at `0x140008663`
- `msvcrt!wcslen` at `0x140008565`
- `msvcrt!wcslen` at `0x140008571`
- `msvcrt!wcslen` at `0x140008663`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000860a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140008613`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400086e0`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x14000860a`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140008613`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400086e0`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000859e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140008683`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x14000859e`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140008683`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008511`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008635`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008511`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008635`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400086fa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400086fa`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140008419`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140008435`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140008419`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x140008435`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008458`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140008458`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000851f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000851f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008643`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400086c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400085e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400086c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084f6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084c6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084d6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1400084f6`

## string_xrefs

- `0x1400084a2`: `SYSTEM\CurrentControlSet\Services\WmiApRpl\Performance`

## pseudocode

```c
__int64 __fastcall WmiRefresherStuff::LodCtrUnlodCtr(HMODULE *this, const unsigned __int16 *a2, int a3)
{
  HANDLE v5; // rbx
  HANDLE v6; // rax
  HKEY v7; // rdx
  DWORD LastError; // esi
  HKEY v9; // rbx
  HKEY v10; // rdx
  FARPROC ProcAddress; // r13
  unsigned __int16 *WbemDirectory; // r14
  int v13; // ebx
  unsigned __int64 v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rbx
  DWORD v17; // eax
  FARPROC v18; // r14
  unsigned __int64 v19; // r13
  unsigned __int16 *v20; // rax
  unsigned __int16 *v21; // rbx
  DWORD v22; // eax
  unsigned int v24; // [rsp+20h] [rbp-78h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-68h]
  unsigned __int16 *v26; // [rsp+30h] [rbp-68h]
  void **v27; // [rsp+40h] [rbp-58h] BYREF
  HANDLE hHandle; // [rsp+48h] [rbp-50h]
  _QWORD v29[2]; // [rsp+50h] [rbp-48h] BYREF
  HKEY hKey[4]; // [rsp+60h] [rbp-38h] BYREF
  unsigned __int64 v31; // [rsp+A8h] [rbp+10h]
  int v32; // [rsp+B8h] [rbp+20h]

  v29[0] = &__SmartHANDLE::`vftable';
  v27 = &__SmartHANDLE::`vftable';
  v5 = OpenEventW(2u, 0, L"Global\\WMI_RevAdap_Set");
  v29[1] = v5;
  v6 = OpenEventW(0x100000u, 0, L"Global\\WMI_RevAdap_ACK");
  hHandle = v6;
  if ( v5 && v6 )
  {
    v32 = 1;
    if ( !SetEvent(v5) )
    {
LABEL_31:
      LastError = -2147467259;
      goto LABEL_32;
    }
  }
  else
  {
    v32 = 0;
  }
  LastError = -2147024882;
  if ( a3 )
  {
    memset(hKey, 0, 24);
    if ( !(unsigned int)ATL::CRegKey::Open(
                          (ATL::CRegKey *)hKey,
                          v7,
                          L"SYSTEM\\CurrentControlSet\\Services\\WmiApRpl\\Performance",
                          0x10002u,
                          v24) )
    {
      v9 = hKey[0];
      RegDeleteValueW(hKey[0], L"First Counter");
      RegDeleteValueW(v9, L"First Help");
      RegDeleteValueW(v9, L"Last Counter");
      RegDeleteValueW(v9, L"Last Help");
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
    ProcAddress = GetProcAddress(this[15], "LoadPerfCounterTextStringsW");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      goto LABEL_32;
    }
    WbemDirectory = GetWbemDirectory(1, v10);
    if ( WbemDirectory )
    {
      v13 = wcslen(L"WmiApRpl");
      v31 = (unsigned int)wcslen(WbemDirectory) + v13 + 8;
      v14 = 2 * v31;
      if ( !is_mul_ok(v31, 2u) )
        v14 = -1;
      try
      {
        v15 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(v14);
        v16 = v15;
        v25 = v15;
        if ( v15 )
        {
          StringCchPrintfW(v15, v31, L"xx %s%s.ini", WbemDirectory, L"WmiApRpl");
          v17 = ((__int64 (__fastcall *)(unsigned __int16 *, __int64))ProcAddress)(v16, 1);
          LastError = v17;
          if ( v17 )
            SetLastError(v17);
        }
      }
      catch ( ... )
      {
        LastError = -2147418113;
        v16 = v25;
      }
      if ( v16 )
        CWin32DefaultArena::WbemMemFree(v16);
      CWin32DefaultArena::WbemMemFree(WbemDirectory);
    }
    ATL::CRegKey::Close((ATL::CRegKey *)hKey);
  }
  else
  {
    v18 = GetProcAddress(this[15], "UnloadPerfCounterTextStringsW");
    if ( !v18 )
    {
      LastError = GetLastError();
      goto LABEL_32;
    }
    try
    {
      v19 = (unsigned int)wcslen(L"WmiApRpl") + 4;
      v20 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v19, 2u));
      v21 = v20;
      v26 = v20;
      if ( v20 )
      {
        StringCchPrintfW(v20, (unsigned int)v19, L"xx %s", L"WmiApRpl");
        v22 = ((__int64 (__fastcall *)(unsigned __int16 *, __int64))v18)(v21, 1);
        LastError = v22;
        if ( v22 )
          SetLastError(v22);
      }
    }
    catch ( ... )
    {
      LastError = -2147418113;
      v21 = v26;
    }
    if ( v21 )
      CWin32DefaultArena::WbemMemFree(v21);
  }
  if ( v32 && WaitForSingleObject(hHandle, 0xBB8u) )
    goto LABEL_31;
LABEL_32:
  __SmartHANDLE::~__SmartHANDLE((__SmartHANDLE *)&v27);
  __SmartHANDLE::~__SmartHANDLE((__SmartHANDLE *)v29);
  return LastError;
}

```

## disassembly

```asm
0x1400083dc  mov     r11, rsp
0x1400083df  mov     [r11+8], rbx
0x1400083e3  mov     [r11+18h], rsi
0x1400083e7  mov     [r11+10h], rdx
0x1400083eb  push    r12
0x1400083ed  push    r13
0x1400083ef  push    r14
0x1400083f1  sub     rsp, 80h
0x1400083f8  mov     r12d, r8d
0x1400083fb  mov     r14, rcx
0x1400083fe  lea     rax, ??_7__SmartHANDLE@@6B@; const __SmartHANDLE::`vftable'
0x140008405  mov     [r11-48h], rax
0x140008409  mov     [r11-58h], rax
0x14000840d  lea     r8, aGlobalWmiRevad_0; "Global\\WMI_RevAdap_Set"
0x140008414  xor     edx, edx; bInheritHandle
0x140008416  lea     ecx, [rdx+2]; dwDesiredAccess
0x140008419  call    cs:__imp_OpenEventW
0x14000841f  mov     rbx, rax
0x140008422  mov     [rsp+98h+var_40], rax
0x140008427  lea     r8, aGlobalWmiRevad; "Global\\WMI_RevAdap_ACK"
0x14000842e  xor     edx, edx; bInheritHandle
0x140008430  mov     ecx, 100000h; dwDesiredAccess
0x140008435  call    cs:__imp_OpenEventW
0x14000843b  mov     [rsp+98h+hHandle], rax
0x140008440  test    rbx, rbx
0x140008443  jz      short loc_140008468
0x140008445  test    rax, rax
0x140008448  jz      short loc_140008468
0x14000844a  mov     [rsp+98h+arg_18], 1
0x140008455  mov     rcx, rbx; hEvent
0x140008458  call    cs:__imp_SetEvent
0x14000845e  cmp     eax, 1
0x140008461  jz      short loc_140008473
0x140008463  jmp     loc_140008704
0x140008468  mov     [rsp+98h+arg_18], 0
0x140008473  mov     esi, 8007000Eh
0x140008478  test    r12d, r12d
0x14000847b  jz      loc_14000862A
0x140008481  mov     [rsp+98h+hKey], 0
0x14000848a  mov     [rsp+98h+var_30], 0
0x140008493  mov     [rsp+98h+var_28], 0
0x14000849c  mov     r9d, 10002h; unsigned int
0x1400084a2  lea     r8, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Wm"...
0x1400084a9  lea     rcx, [rsp+98h+hKey]; this
0x1400084ae  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGKK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong,ulong)
0x1400084b3  test    eax, eax
0x1400084b5  jnz     short loc_1400084FC
0x1400084b7  lea     rdx, aFirstCounter; "First Counter"
0x1400084be  mov     rbx, [rsp+98h+hKey]
0x1400084c3  mov     rcx, rbx; hKey
0x1400084c6  call    cs:__imp_RegDeleteValueW
0x1400084cc  lea     rdx, aFirstHelp; "First Help"
0x1400084d3  mov     rcx, rbx; hKey
0x1400084d6  call    cs:__imp_RegDeleteValueW
0x1400084dc  lea     rdx, aLastCounter; "Last Counter"
0x1400084e3  mov     rcx, rbx; hKey
0x1400084e6  call    cs:__imp_RegDeleteValueW
0x1400084ec  lea     rdx, aLastHelp; "Last Help"
0x1400084f3  mov     rcx, rbx; hKey
0x1400084f6  call    cs:__imp_RegDeleteValueW
0x1400084fc  lea     rcx, [rsp+98h+hKey]; this
0x140008501  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140008506  lea     rdx, ProcName; "LoadPerfCounterTextStringsW"
0x14000850d  mov     rcx, [r14+78h]; hModule
0x140008511  call    cs:__imp_GetProcAddress
0x140008517  mov     r13, rax
0x14000851a  test    rax, rax
0x14000851d  jnz     short loc_140008537
0x14000851f  call    cs:__imp_GetLastError
0x140008525  mov     esi, eax
0x140008527  lea     rcx, [rsp+98h+hKey]; this
0x14000852c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140008531  nop
0x140008532  jmp     loc_140008709
0x140008537  mov     ecx, 1; int
0x14000853c  call    ?GetWbemDirectory@@YAPEAGH@Z; GetWbemDirectory(int)
0x140008541  mov     r14, rax
0x140008544  mov     [rsp+98h+var_60], rax
0x140008549  test    rax, rax
0x14000854c  jz      loc_14000861A
0x140008552  mov     [rsp+98h+var_68], 0
0x14000855b  lea     r12, aWmiaprpl; "WmiApRpl"
0x140008562  mov     rcx, r12; String
0x140008565  call    cs:__imp_wcslen
0x14000856b  mov     rbx, rax
0x14000856e  mov     rcx, r14; String
0x140008571  call    cs:__imp_wcslen
0x140008577  lea     rcx, [rbx+8]
0x14000857b  add     rcx, rax
0x14000857e  mov     ecx, ecx
0x140008580  mov     [rsp+98h+arg_8], rcx
0x140008588  mov     eax, 2
0x14000858d  mul     rcx
0x140008590  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140008597  cmovb   rax, rcx
0x14000859b  mov     rcx, rax
0x14000859e  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1400085a4  mov     rbx, rax
0x1400085a7  mov     [rsp+98h+var_68], rax
0x1400085ac  test    rax, rax
0x1400085af  jz      short loc_1400085EF
0x1400085b1  mov     qword ptr [rsp+98h+var_78], r12
0x1400085b6  mov     r9, r14
0x1400085b9  lea     r8, aXxSSIni; "xx %s%s.ini"
0x1400085c0  mov     rdx, [rsp+98h+arg_8]; unsigned __int64
0x1400085c8  mov     rcx, rax; unsigned __int16 *
0x1400085cb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400085d0  mov     edx, 1
0x1400085d5  mov     rcx, rbx
0x1400085d8  mov     rax, r13
0x1400085db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085e0  mov     esi, eax
0x1400085e2  test    eax, eax
0x1400085e4  jz      short loc_1400085EF
0x1400085e6  mov     ecx, eax; dwErrCode
0x1400085e8  call    cs:__imp_SetLastError
0x1400085ee  nop
0x1400085ef  jmp     short loc_140008602
0x1400085f1  mov     esi, dword ptr [rsp+98h+arg_8]
0x1400085f8  mov     r14, [rsp+98h+var_60]
0x1400085fd  mov     rbx, [rsp+98h+var_68]
0x140008602  test    rbx, rbx
0x140008605  jz      short loc_140008610
0x140008607  mov     rcx, rbx
0x14000860a  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140008610  mov     rcx, r14
0x140008613  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140008619  nop
0x14000861a  lea     rcx, [rsp+98h+hKey]; this
0x14000861f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140008624  nop
0x140008625  jmp     loc_1400086E6
0x14000862a  lea     rdx, aUnloadperfcoun; "UnloadPerfCounterTextStringsW"
0x140008631  mov     rcx, [r14+78h]; hModule
0x140008635  call    cs:__imp_GetProcAddress
0x14000863b  mov     r14, rax
0x14000863e  test    rax, rax
0x140008641  jnz     short loc_140008650
0x140008643  call    cs:__imp_GetLastError
0x140008649  mov     esi, eax
0x14000864b  jmp     loc_140008709
0x140008650  mov     [rsp+98h+var_68], 0
0x140008659  lea     r12, aWmiaprpl; "WmiApRpl"
0x140008660  mov     rcx, r12; String
0x140008663  call    cs:__imp_wcslen
0x140008669  lea     r13d, [rax+4]
0x14000866d  mov     eax, 2
0x140008672  mul     r13
0x140008675  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14000867c  cmovb   rax, rcx
0x140008680  mov     rcx, rax
0x140008683  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140008689  mov     rbx, rax
0x14000868c  mov     [rsp+98h+var_68], rax
0x140008691  test    rax, rax
0x140008694  jz      short loc_1400086CA
0x140008696  mov     r9, r12
0x140008699  lea     r8, aXxS; "xx %s"
0x1400086a0  mov     edx, r13d; unsigned __int64
0x1400086a3  mov     rcx, rax; unsigned __int16 *
0x1400086a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400086ab  mov     edx, 1
0x1400086b0  mov     rcx, rbx
0x1400086b3  mov     rax, r14
0x1400086b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086bb  mov     esi, eax
0x1400086bd  test    eax, eax
0x1400086bf  jz      short loc_1400086CA
0x1400086c1  mov     ecx, eax; dwErrCode
0x1400086c3  call    cs:__imp_SetLastError
0x1400086c9  nop
0x1400086ca  jmp     short loc_1400086D8
0x1400086cc  mov     esi, dword ptr [rsp+98h+arg_8]
0x1400086d3  mov     rbx, [rsp+98h+var_68]
0x1400086d8  test    rbx, rbx
0x1400086db  jz      short loc_1400086E6
0x1400086dd  mov     rcx, rbx
0x1400086e0  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400086e6  cmp     [rsp+98h+arg_18], 0
0x1400086ee  jz      short loc_140008709
0x1400086f0  mov     edx, 0BB8h; dwMilliseconds
0x1400086f5  mov     rcx, [rsp+98h+hHandle]; hHandle
0x1400086fa  call    cs:__imp_WaitForSingleObject
0x140008700  test    eax, eax
0x140008702  jz      short loc_140008709
0x140008704  mov     esi, 80004005h
0x140008709  lea     rcx, [rsp+98h+var_58]; this
0x14000870e  call    ??1__SmartHANDLE@@UEAA@XZ; __SmartHANDLE::~__SmartHANDLE(void)
0x140008713  nop
0x140008714  lea     rcx, [rsp+98h+var_48]; this
0x140008719  call    ??1__SmartHANDLE@@UEAA@XZ; __SmartHANDLE::~__SmartHANDLE(void)
0x14000871e  mov     eax, esi
0x140008720  lea     r11, [rsp+98h+var_18]
0x140008728  mov     rbx, [r11+20h]
0x14000872c  mov     rsi, [r11+30h]
0x140008730  mov     rsp, r11
0x140008733  pop     r14
0x140008735  pop     r13
0x140008737  pop     r12
0x140008739  retn
```
