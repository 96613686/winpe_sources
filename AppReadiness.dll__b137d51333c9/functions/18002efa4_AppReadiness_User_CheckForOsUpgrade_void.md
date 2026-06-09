# AppReadiness::User::CheckForOsUpgrade(void)

- ea: `0x18002efa4`
- end: `0x18002f12a`
- name: `?CheckForOsUpgrade@User@AppReadiness@@IEAAJXZ`
- size: `390`
- prototype: `__int64 __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180024130`
- `0x18002efa4`
- `0x180030914`
- `0x180039eec`
- `0x1800473d8`
- `0x1800483c4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f05f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002f05f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002efd2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002efd2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f040`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f116`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f040`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002f116`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f0f8`

## string_xrefs

- `0x18002eff5`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18002f07b`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18002efcb`: `PreinstalledVolumeServicing.dll`
- `0x18002f058`: `PreinstalledVolumeServicing_ApplySuccess`

## pseudocode

```c
__int64 __fastcall AppReadiness::User::CheckForOsUpgrade(AppReadiness::User *this)
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
        (void *)0xB00,
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
    v7 = 65;
    goto LABEL_14;
  }
  ProcAddress = GetProcAddress(hModule, "PreinstalledVolumeServicing_ApplySuccess");
  if ( ProcAddress )
  {
    v5 = ProcAddress();
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v5,
        v9[0]);
    goto LABEL_15;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v7 = 64;
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
0x18002efa4  mov     [rsp+arg_0], rbx
0x18002efa9  push    rsi
0x18002efaa  sub     rsp, 30h
0x18002efae  lea     rsi, ??_7?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable'
0x18002efb5  mov     qword ptr [rsp+38h+var_18], rsi; int
0x18002efba  mov     [rsp+38h+hModule], 0
0x18002efc3  xor     edx, edx; hFile
0x18002efc5  mov     r8d, 800h; dwFlags
0x18002efcb  lea     rcx, aPreinstalledvo; "PreinstalledVolumeServicing.dll"
0x18002efd2  call    cs:__imp_LoadLibraryExW
0x18002efd8  mov     [rsp+38h+hModule], rax
0x18002efdd  test    rax, rax
0x18002efe0  jnz     short loc_18002F04E
0x18002efe2  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18002efe7  mov     ebx, eax
0x18002efe9  test    eax, eax
0x18002efeb  jns     short loc_18002F04E
0x18002efed  mov     rcx, [rsp+38h]; this
0x18002eff2  mov     r9d, eax; char *
0x18002eff5  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002effc  mov     edx, 0B00h; void *
0x18002f001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f006  nop
0x18002f007  mov     qword ptr [rsp+38h+var_18], rsi
0x18002f00c  cmp     [rsp+38h+hModule], 0
0x18002f012  jz      short loc_18002F047
0x18002f014  lea     rcx, [rsp+38h+var_18]
0x18002f019  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x18002f01e  test    al, al
0x18002f020  jnz     short loc_18002F047
0x18002f022  call    cs:__imp_GetLastError
0x18002f028  test    eax, eax
0x18002f02a  jle     short loc_18002F034
0x18002f02c  movzx   eax, ax
0x18002f02f  or      eax, 80070000h
0x18002f034  xor     r9d, r9d; lpArguments
0x18002f037  xor     r8d, r8d; nNumberOfArguments
0x18002f03a  lea     edx, [r9+1]; dwExceptionFlags
0x18002f03e  mov     ecx, eax; dwExceptionCode
0x18002f040  call    cs:__imp_RaiseException
0x18002f046  int     3; Trap to Debugger
0x18002f047  mov     eax, ebx
0x18002f049  jmp     loc_18002F11F
0x18002f04e  mov     rcx, [rsp+38h+hModule]; hModule
0x18002f053  test    rcx, rcx
0x18002f056  jz      short loc_18002F0AE
0x18002f058  lea     rdx, aPreinstalledvo_1; "PreinstalledVolumeServicing_ApplySucces"...
0x18002f05f  call    cs:__imp_GetProcAddress
0x18002f065  test    rax, rax
0x18002f068  jz      short loc_18002F08E
0x18002f06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f06f  mov     rcx, [rsp+38h]; this
0x18002f074  test    eax, eax
0x18002f076  jns     short loc_18002F0DD
0x18002f078  mov     r9d, eax; char *
0x18002f07b  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18002f082  mov     edx, 0B07h; void *
0x18002f087  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002f08c  jmp     short loc_18002F0DD
0x18002f08e  lea     rax, WPP_GLOBAL_Control
0x18002f095  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f09c  cmp     rcx, rax
0x18002f09f  jz      short loc_18002F0DD
0x18002f0a1  test    byte ptr [rcx+1Ch], 4
0x18002f0a5  jz      short loc_18002F0DD
0x18002f0a7  mov     edx, 40h ; '@'
0x18002f0ac  jmp     short loc_18002F0CC
0x18002f0ae  lea     rax, WPP_GLOBAL_Control
0x18002f0b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0bc  cmp     rcx, rax
0x18002f0bf  jz      short loc_18002F0DD
0x18002f0c1  test    byte ptr [rcx+1Ch], 4
0x18002f0c5  jz      short loc_18002F0DD
0x18002f0c7  mov     edx, 41h ; 'A'
0x18002f0cc  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x18002f0d3  mov     rcx, [rcx+10h]
0x18002f0d7  call    WPP_SF_
0x18002f0dc  nop
0x18002f0dd  mov     qword ptr [rsp+38h+var_18], rsi
0x18002f0e2  cmp     [rsp+38h+hModule], 0
0x18002f0e8  jz      short loc_18002F11D
0x18002f0ea  lea     rcx, [rsp+38h+var_18]
0x18002f0ef  call    ?InternalClose@?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::InternalClose(void)
0x18002f0f4  test    al, al
0x18002f0f6  jnz     short loc_18002F11D
0x18002f0f8  call    cs:__imp_GetLastError
0x18002f0fe  test    eax, eax
0x18002f100  jle     short loc_18002F10A
0x18002f102  movzx   eax, ax
0x18002f105  or      eax, 80070000h
0x18002f10a  xor     r9d, r9d; lpArguments
0x18002f10d  xor     r8d, r8d; nNumberOfArguments
0x18002f110  lea     edx, [r9+1]; dwExceptionFlags
0x18002f114  mov     ecx, eax; dwExceptionCode
0x18002f116  call    cs:__imp_RaiseException
0x18002f11c  int     3; Trap to Debugger
0x18002f11d  xor     eax, eax
0x18002f11f  mov     rbx, [rsp+38h+arg_0]
0x18002f124  add     rsp, 30h
0x18002f128  pop     rsi
0x18002f129  retn
```
