# DllCanUnloadNow

- ea: `0x18000ad10`
- end: `0x18000ae96`
- name: `DllCanUnloadNow`
- size: `390`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800032a0`
- `0x180004a78`
- `0x180004b14`
- `0x180009eb0`
- `0x18000ad10`
- `0x18000b274`
- `0x18000b29c`
- `0x1800194d4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae19`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ad74`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ae19`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000ad33`
- `RPCRT4!NdrDllCanUnloadNow` at `0x18000ad33`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  unsigned int CanUnloadNow; // ebx
  struct Microsoft::WRL::Details::ModuleBase *v1; // rdx
  bool v2; // r9
  __int64 *v3; // rdx
  bool v4; // di
  __int64 v5; // rcx
  __int64 *v6; // rdx
  _QWORD v8[2]; // [rsp+20h] [rbp-88h] BYREF
  _BYTE v9[64]; // [rsp+30h] [rbp-78h] BYREF

  CanUnloadNow = NdrDllCanUnloadNow(&gPFactory);
  if ( CanUnloadNow
    && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 15, &WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids);
  }
  EnterCriticalSection(&CriticalSection);
  v8[0] = &WpcDesktop::OTS::ManagerDLL::InProcComServerModule;
  ScopeGuard::ScopeGuard(v9, v8);
  v4 = Microsoft::WRL::Details::TerminateMap(
         (Microsoft::WRL::Details *)&WpcDesktop::OTS::ManagerDLL::InProcComServerModule,
         v1,
         0,
         v2)
    && ((unsigned __int8 (__fastcall *)(void ***))(*off_180044098)[1])(off_180044098);
  ScopeGuard::~ScopeGuard((ScopeGuard *)v9, v3);
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
  }
  else
  {
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 16, &WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids);
      v5 = WPP_GLOBAL_Control;
    }
    CanUnloadNow = 1;
  }
  if ( !CanUnloadNow )
  {
    EnterCriticalSection(&CriticalSection);
    v8[0] = &WpcDesktop::OTS::ManagerDLL::InProcComServerModule;
    ScopeGuard::ScopeGuard(v9, v8);
    ((void (__fastcall *)(void ***))(*off_180044098)[2])(off_180044098);
    ScopeGuard::~ScopeGuard((ScopeGuard *)v9, v6);
    v5 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v5 != &WPP_GLOBAL_Control && (*(_BYTE *)(v5 + 28) & 8) != 0 )
    WPP_SF_d(*(_QWORD *)(v5 + 16), 17, &WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids, CanUnloadNow);
  return CanUnloadNow;
}

```

## disassembly

```asm
0x18000ad10  push    rbx
0x18000ad12  push    rsi
0x18000ad13  push    rdi
0x18000ad14  push    r14
0x18000ad16  sub     rsp, 88h
0x18000ad1d  mov     rax, cs:__security_cookie
0x18000ad24  xor     rax, rsp
0x18000ad27  mov     [rsp+0A8h+var_38], rax
0x18000ad2c  lea     rcx, gPFactory; pPSFactoryBuffer
0x18000ad33  call    cs:__imp_NdrDllCanUnloadNow
0x18000ad39  lea     rsi, WPP_GLOBAL_Control
0x18000ad40  mov     ebx, eax
0x18000ad42  test    eax, eax
0x18000ad44  jz      short loc_18000AD6D
0x18000ad46  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ad4d  cmp     rcx, rsi
0x18000ad50  jz      short loc_18000AD6D
0x18000ad52  test    byte ptr [rcx+1Ch], 2
0x18000ad56  jz      short loc_18000AD6D
0x18000ad58  mov     rcx, [rcx+10h]
0x18000ad5c  lea     r8, WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids
0x18000ad63  mov     edx, 0Fh
0x18000ad68  call    WPP_SF_
0x18000ad6d  lea     rcx, CriticalSection; lpCriticalSection
0x18000ad74  call    cs:__imp_EnterCriticalSection
0x18000ad7a  lea     r14, ?InProcComServerModule@ManagerDLL@OTS@WpcDesktop@@3VWrlModule@WpcBase@@A; WpcBase::WrlModule WpcDesktop::OTS::ManagerDLL::InProcComServerModule
0x18000ad81  lea     rdx, [rsp+0A8h+var_88]
0x18000ad86  mov     [rsp+0A8h+var_88], r14
0x18000ad8b  lea     rcx, [rsp+0A8h+var_78]
0x18000ad90  call    ??$?0V_lambda_6e2e748093b35e85031adbb7a778d708_@@@ScopeGuard@@QEAA@$$QEAV_lambda_6e2e748093b35e85031adbb7a778d708_@@@Z; ScopeGuard::ScopeGuard(_lambda_6e2e748093b35e85031adbb7a778d708_ &&)
0x18000ad95  xor     r8d, r8d; unsigned __int16 *
0x18000ad98  mov     rcx, r14; this
0x18000ad9b  call    ?TerminateMap@Details@WRL@Microsoft@@YA_NPEAVModuleBase@123@PEBG_N@Z; Microsoft::WRL::Details::TerminateMap(Microsoft::WRL::Details::ModuleBase *,ushort const *,bool)
0x18000ada0  test    al, al
0x18000ada2  jz      short loc_18000ADC0
0x18000ada4  mov     rcx, cs:off_180044098
0x18000adab  mov     rax, [rcx]
0x18000adae  mov     rax, [rax+8]
0x18000adb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adb7  test    al, al
0x18000adb9  jz      short loc_18000ADC0
0x18000adbb  mov     dil, 1
0x18000adbe  jmp     short loc_18000ADC3
0x18000adc0  xor     dil, dil
0x18000adc3  lea     rcx, [rsp+0A8h+var_78]; this
0x18000adc8  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18000adcd  test    dil, dil
0x18000add0  jnz     short loc_18000AE07
0x18000add2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000add9  cmp     rcx, rsi
0x18000addc  jz      short loc_18000AE00
0x18000adde  test    byte ptr [rcx+1Ch], 2
0x18000ade2  jz      short loc_18000AE00
0x18000ade4  mov     rcx, [rcx+10h]
0x18000ade8  lea     r8, WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids
0x18000adef  mov     edx, 10h
0x18000adf4  call    WPP_SF_
0x18000adf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae00  mov     ebx, 1
0x18000ae05  jmp     short loc_18000AE0E
0x18000ae07  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae0e  test    ebx, ebx
0x18000ae10  jnz     short loc_18000AE57
0x18000ae12  lea     rcx, CriticalSection; lpCriticalSection
0x18000ae19  call    cs:__imp_EnterCriticalSection
0x18000ae1f  lea     rdx, [rsp+0A8h+var_88]
0x18000ae24  mov     [rsp+0A8h+var_88], r14
0x18000ae29  lea     rcx, [rsp+0A8h+var_78]
0x18000ae2e  call    ??$?0V_lambda_9fa10ce64345b41dbc4fc3c1fc27b1d6_@@@ScopeGuard@@QEAA@$$QEAV_lambda_9fa10ce64345b41dbc4fc3c1fc27b1d6_@@@Z; ScopeGuard::ScopeGuard(_lambda_9fa10ce64345b41dbc4fc3c1fc27b1d6_ &&)
0x18000ae33  mov     rcx, cs:off_180044098
0x18000ae3a  mov     rax, [rcx]
0x18000ae3d  mov     rax, [rax+10h]
0x18000ae41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae46  lea     rcx, [rsp+0A8h+var_78]; this
0x18000ae4b  call    ??1ScopeGuard@@QEAA@XZ; ScopeGuard::~ScopeGuard(void)
0x18000ae50  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ae57  cmp     rcx, rsi
0x18000ae5a  jz      short loc_18000AE7A
0x18000ae5c  test    byte ptr [rcx+1Ch], 8
0x18000ae60  jz      short loc_18000AE7A
0x18000ae62  mov     rcx, [rcx+10h]
0x18000ae66  lea     r8, WPP_1255abf0ecc2316176ef827e071b6c4e_Traceguids
0x18000ae6d  mov     edx, 11h
0x18000ae72  mov     r9d, ebx
0x18000ae75  call    WPP_SF_d
0x18000ae7a  mov     eax, ebx
0x18000ae7c  mov     rcx, [rsp+0A8h+var_38]
0x18000ae81  xor     rcx, rsp; StackCookie
0x18000ae84  call    __security_check_cookie
0x18000ae89  add     rsp, 88h
0x18000ae90  pop     r14
0x18000ae92  pop     rdi
0x18000ae93  pop     rsi
0x18000ae94  pop     rbx
0x18000ae95  retn
```
