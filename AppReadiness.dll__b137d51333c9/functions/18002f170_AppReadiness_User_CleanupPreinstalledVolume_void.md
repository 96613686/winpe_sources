# AppReadiness::User::CleanupPreinstalledVolume(void)

- ea: `0x18002f170`
- end: `0x18002f2f6`
- name: `?CleanupPreinstalledVolume@User@AppReadiness@@IEAAJXZ`
- size: `390`
- prototype: `__int64 __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180024130`
- `0x18002f170`
- `0x180030914`
- `0x180039eec`
- `0x1800473d8`
- `0x1800483c4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f22b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f22b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f19e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002f19e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f20c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f2e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f20c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f2e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f1ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f2c4`

## string_xrefs

- `0x18002f1c1`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18002f247`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18002f197`: `PreinstalledVolumeServicing.dll`
- `0x18002f224`: `PreinstalledVolumeServicing_ResetCleanup`

## pseudocode

```c
__int64 __fastcall AppReadiness::User::CleanupPreinstalledVolume(AppReadiness::User *this)
{
  int Error; // eax
  unsigned int v2; // ebx
  __int64 (*ProcAddress)(void); // rax
  int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  int LastError; // eax
  int v9[2]; // [rsp+20h] [rbp-18h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)v9 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  hModule = LoadLibraryExW(L"PreinstalledVolumeServicing.dll", 0, 0x800u);
  if ( !hModule )
  {
    Error = ResultFromKnownLastError();
    v2 = Error;
    if ( Error < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB1B,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)Error,
        v9[0]);
      *(_QWORD *)v9 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
      return v2;
    }
  }
  if ( !hModule )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_15;
    v7 = 67;
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(hModule, "PreinstalledVolumeServicing_ResetCleanup");
  if ( ProcAddress )
  {
    v5 = ProcAddress();
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB22,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v5,
        v9[0]);
    goto LABEL_15;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v7 = 66;
LABEL_14:
    WPP_SF_(v6[2], v7, &WPP_2779cad321383337b9ccea6dca676a06_Traceguids);
  }
LABEL_15:
  *(_QWORD *)v9 = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  if ( hModule
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(v9) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RaiseException(LastError, 1u, 0, 0);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x18002f170  mov     [rsp+arg_0], rbx
0x18002f175  push    rsi
0x18002f176  sub     rsp, 30h
0x18002f17a  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable'
0x18002f181  mov     qword ptr [rsp+38h+var_18], rsi; int
0x18002f186  mov     [rsp+38h+hModule], 0
0x18002f18f  xor     edx, edx; hFile
0x18002f191  mov     r8d, 800h; dwFlags
0x18002f197  lea     rcx, aPreinstalledvo; "PreinstalledVolumeServicing.dll"
0x18002f19e  call    cs:__imp_LoadLibraryExW
0x18002f1a4  mov     [rsp+38h+hModule], rax
0x18002f1a9  test    rax, rax
0x18002f1ac  jnz     short loc_18002F21A
0x18002f1ae  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002f1b3  mov     ebx, eax
0x18002f1b5  test    eax, eax
0x18002f1b7  jns     short loc_18002F21A
0x18002f1b9  mov     rcx, [rsp+38h]; this
0x18002f1be  mov     r9d, eax; char *
0x18002f1c1  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002f1c8  mov     edx, 0B1Bh; void *
0x18002f1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f1d2  nop
0x18002f1d3  mov     qword ptr [rsp+38h+var_18], rsi
0x18002f1d8  cmp     [rsp+38h+hModule], 0
0x18002f1de  jz      short loc_18002F213
0x18002f1e0  lea     rcx, [rsp+38h+var_18]
0x18002f1e5  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x18002f1ea  test    al, al
0x18002f1ec  jnz     short loc_18002F213
0x18002f1ee  call    cs:__imp_GetLastError
0x18002f1f4  test    eax, eax
0x18002f1f6  jle     short loc_18002F200
0x18002f1f8  movzx   eax, ax
0x18002f1fb  or      eax, 80070000h
0x18002f200  xor     r9d, r9d; lpArguments
0x18002f203  xor     r8d, r8d; nNumberOfArguments
0x18002f206  lea     edx, [r9+1]; dwExceptionFlags
0x18002f20a  mov     ecx, eax; dwExceptionCode
0x18002f20c  call    cs:__imp_RaiseException
0x18002f212  int     3; Trap to Debugger
0x18002f213  mov     eax, ebx
0x18002f215  jmp     loc_18002F2EB
0x18002f21a  mov     rcx, [rsp+38h+hModule]; hModule
0x18002f21f  test    rcx, rcx
0x18002f222  jz      short loc_18002F27A
0x18002f224  lea     rdx, aPreinstalledvo_0; "PreinstalledVolumeServicing_ResetCleanu"...
0x18002f22b  call    cs:__imp_GetProcAddress
0x18002f231  test    rax, rax
0x18002f234  jz      short loc_18002F25A
0x18002f236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f23b  mov     rcx, [rsp+38h]; this
0x18002f240  test    eax, eax
0x18002f242  jns     short loc_18002F2A9
0x18002f244  mov     r9d, eax; char *
0x18002f247  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002f24e  mov     edx, 0B22h; void *
0x18002f253  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f258  jmp     short loc_18002F2A9
0x18002f25a  lea     rax, WPP_GLOBAL_Control
0x18002f261  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f268  cmp     rcx, rax
0x18002f26b  jz      short loc_18002F2A9
0x18002f26d  test    byte ptr [rcx+1Ch], 4
0x18002f271  jz      short loc_18002F2A9
0x18002f273  mov     edx, 42h ; 'B'
0x18002f278  jmp     short loc_18002F298
0x18002f27a  lea     rax, WPP_GLOBAL_Control
0x18002f281  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f288  cmp     rcx, rax
0x18002f28b  jz      short loc_18002F2A9
0x18002f28d  test    byte ptr [rcx+1Ch], 4
0x18002f291  jz      short loc_18002F2A9
0x18002f293  mov     edx, 43h ; 'C'
0x18002f298  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x18002f29f  mov     rcx, [rcx+10h]
0x18002f2a3  call    WPP_SF_
0x18002f2a8  nop
0x18002f2a9  mov     qword ptr [rsp+38h+var_18], rsi
0x18002f2ae  cmp     [rsp+38h+hModule], 0
0x18002f2b4  jz      short loc_18002F2E9
0x18002f2b6  lea     rcx, [rsp+38h+var_18]
0x18002f2bb  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x18002f2c0  test    al, al
0x18002f2c2  jnz     short loc_18002F2E9
0x18002f2c4  call    cs:__imp_GetLastError
0x18002f2ca  test    eax, eax
0x18002f2cc  jle     short loc_18002F2D6
0x18002f2ce  movzx   eax, ax
0x18002f2d1  or      eax, 80070000h
0x18002f2d6  xor     r9d, r9d; lpArguments
0x18002f2d9  xor     r8d, r8d; nNumberOfArguments
0x18002f2dc  lea     edx, [r9+1]; dwExceptionFlags
0x18002f2e0  mov     ecx, eax; dwExceptionCode
0x18002f2e2  call    cs:__imp_RaiseException
0x18002f2e8  int     3; Trap to Debugger
0x18002f2e9  xor     eax, eax
0x18002f2eb  mov     rbx, [rsp+38h+arg_0]
0x18002f2f0  add     rsp, 30h
0x18002f2f4  pop     rsi
0x18002f2f5  retn
```
