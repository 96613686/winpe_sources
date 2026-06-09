# DllMain

- ea: `0x18000a4e0`
- end: `0x18000a6d0`
- name: `DllMain`
- size: `496`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a7c`
- `0x18000a4e0`
- `0x18000a6d8`
- `0x18000a768`
- `0x18000a86c`
- `0x18000a938`
- `0x18000ac20`
- `0x18000ac58`
- `0x180013ad8`
- `0x1800160f4`

## import_xrefs

- `ntdll!LdrDisableThreadCalloutsForDll` at `0x18000a509`
- `ntdll!LdrDisableThreadCalloutsForDll` at `0x18000a509`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a66e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000a66e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000a5a9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000a5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a5b9`

## string_xrefs

- `0x18000a5ec`: `onecore\ds\security\cryptoapi\ncrypt\crypt\bcrypt\init.c`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpReserved)
{
  int v5; // edx
  int v6; // r8d
  DWORD LastError; // edx
  int v8; // r8d
  __int64 v10; // r8
  HMODULE phModule; // [rsp+50h] [rbp+8h] BYREF

  phModule = 0;
  g_hInstance = (__int64)hinstDLL;
  if ( fdwReason == 1 )
  {
    LdrDisableThreadCalloutsForDll(hinstDLL);
    DllMainCRTStartupForGS2(hinstDLL, 1, lpReserved);
    SafeAllocaInitialize();
    qword_180024BD0 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CNGTraceControlGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    qword_180024BD8 = 1;
    WppInitUm();
    McGenEventRegister_EtwEventRegister();
    v5 = InitializeCNG();
    if ( v5 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          v6,
          (unsigned int)"Status",
          v5,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\bcrypt\\init.c",
          246);
      return 0;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      GetModuleFileNameW(0, &Filename, 0x100u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v10, hinstDLL);
    }
    if ( !GetModuleHandleExW(5u, (LPCWSTR)DllMain, &phModule) )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          LastError,
          v8,
          (unsigned int)"GetLastError()",
          LastError,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\bcrypt\\init.c",
          13);
      return 0;
    }
  }
  else if ( !fdwReason )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      WPP_SF_qS(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, lpReserved, hinstDLL);
    WppCleanupUm();
    McGenEventUnregister_EtwEventUnregister();
  }
  return 1;
}

```

## disassembly

```asm
0x18000a4e0  mov     [rsp+arg_8], rbx
0x18000a4e5  push    rdi
0x18000a4e6  sub     rsp, 40h
0x18000a4ea  mov     [rsp+48h+phModule], 0
0x18000a4f3  mov     rbx, r8
0x18000a4f6  mov     cs:g_hInstance, rcx
0x18000a4fd  mov     rdi, rcx
0x18000a500  cmp     edx, 1
0x18000a503  jnz     loc_18000A605
0x18000a509  call    cs:__imp_LdrDisableThreadCalloutsForDll
0x18000a510  nop     dword ptr [rax+rax+00h]
0x18000a515  mov     r8, rbx
0x18000a518  mov     edx, 1
0x18000a51d  mov     rcx, rdi
0x18000a520  call    _DllMainCRTStartupForGS2
0x18000a525  call    SafeAllocaInitialize
0x18000a52a  lea     rax, WPP_ThisDir_CTLGUID_CNGTraceControlGuid
0x18000a531  mov     cs:qword_180024BD0, 0
0x18000a53c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000a543  lea     rax, WPP_MAIN_CB
0x18000a54a  mov     cs:WPP_GLOBAL_Control, rax
0x18000a551  mov     cs:WPP_MAIN_CB, 0
0x18000a55c  mov     cs:qword_180024BD8, 1
0x18000a567  call    WppInitUm
0x18000a56c  call    McGenEventRegister_EtwEventRegister
0x18000a571  call    InitializeCNG
0x18000a576  mov     edx, eax
0x18000a578  test    eax, eax
0x18000a57a  jnz     loc_18000A635
0x18000a580  mov     rax, cs:WPP_GLOBAL_Control
0x18000a587  lea     rbx, WPP_GLOBAL_Control
0x18000a58e  test    byte ptr [rax+1Ch], 20h
0x18000a592  jnz     loc_18000A65F
0x18000a598  lea     r8, [rsp+48h+phModule]; phModule
0x18000a59d  mov     ecx, 5; dwFlags
0x18000a5a2  lea     rdx, DllMain; lpModuleName
0x18000a5a9  call    cs:__imp_GetModuleHandleExW
0x18000a5b0  nop     dword ptr [rax+rax+00h]
0x18000a5b5  test    eax, eax
0x18000a5b7  jnz     short loc_18000A624
0x18000a5b9  call    cs:__imp_GetLastError
0x18000a5c0  nop     dword ptr [rax+rax+00h]
0x18000a5c5  mov     edx, eax
0x18000a5c7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5ce  cmp     rcx, rbx
0x18000a5d1  jz      short loc_18000A601
0x18000a5d3  test    byte ptr [rcx+1Ch], 1
0x18000a5d7  jz      short loc_18000A601
0x18000a5d9  mov     [rsp+48h+var_18], 10Dh
0x18000a5e1  lea     r9, aGetlasterror; "GetLastError()"
0x18000a5e8  mov     rcx, [rcx+10h]
0x18000a5ec  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000a5f3  mov     [rsp+48h+var_20], rax
0x18000a5f8  mov     [rsp+48h+var_28], edx
0x18000a5fc  call    WPP_SF_sDsd
0x18000a601  xor     eax, eax
0x18000a603  jmp     short loc_18000A629
0x18000a605  test    edx, edx
0x18000a607  jnz     short loc_18000A624
0x18000a609  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a610  test    byte ptr [rcx+1Ch], 20h
0x18000a614  jnz     loc_18000A6AA
0x18000a61a  call    WppCleanupUm
0x18000a61f  call    McGenEventUnregister_EtwEventUnregister
0x18000a624  mov     eax, 1
0x18000a629  mov     rbx, [rsp+48h+arg_8]
0x18000a62e  add     rsp, 40h
0x18000a632  pop     rdi
0x18000a633  retn
0x18000a635  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a63c  lea     rbx, WPP_GLOBAL_Control
0x18000a643  cmp     rcx, rbx
0x18000a646  jz      short loc_18000A601
0x18000a648  test    byte ptr [rcx+1Ch], 1
0x18000a64c  jz      short loc_18000A601
0x18000a64e  mov     [rsp+48h+var_18], 0F6h
0x18000a656  lea     r9, aStatus; "Status"
0x18000a65d  jmp     short loc_18000A5E8
0x18000a65f  mov     r8d, 100h; nSize
0x18000a665  lea     rdx, Filename; lpFilename
0x18000a66c  xor     ecx, ecx; hModule
0x18000a66e  call    cs:__imp_GetModuleFileNameW
0x18000a675  nop     dword ptr [rax+rax+00h]
0x18000a67a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a681  cmp     rcx, rbx
0x18000a684  jz      loc_18000A598
0x18000a68a  test    byte ptr [rcx+1Ch], 20h
0x18000a68e  jz      loc_18000A598
0x18000a694  mov     rcx, [rcx+10h]
0x18000a698  mov     edx, 0Ah
0x18000a69d  mov     r9, rdi
0x18000a6a0  call    WPP_SF_qS
0x18000a6a5  jmp     loc_18000A598
0x18000a6aa  lea     rbx, WPP_GLOBAL_Control
0x18000a6b1  cmp     rcx, rbx
0x18000a6b4  jz      loc_18000A61A
0x18000a6ba  mov     rcx, [rcx+10h]
0x18000a6be  mov     edx, 0Bh
0x18000a6c3  mov     r9, rdi
0x18000a6c6  call    WPP_SF_qS
0x18000a6cb  jmp     loc_18000A61A
```
