# FwAuthApp::get_RemoteAddresses(ushort * *)

- ea: `0x180040e00`
- end: `0x180040e98`
- name: `?get_RemoteAddresses@FwAuthApp@@UEAAJPEAPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001dd0`
- `0x180040e00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040e13`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040e72`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040e72`
- `fwbase!FwReportReturnError` at `0x180040e68`
- `fwbase!FwReportReturnError` at `0x180040e85`
- `fwbase!FwReportReturnError` at `0x180040e68`
- `fwbase!FwReportReturnError` at `0x180040e85`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180040e53`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x180040e53`

## pseudocode

```c
__int64 __fastcall FwAuthApp::get_RemoteAddresses(FwAuthApp *this, unsigned __int16 **a2)
{
  int v4; // ebx
  __int64 v5; // rdx
  int DefaultAuthAppRules; // eax
  __int64 v7; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( !a2 )
  {
    v4 = -2147467261;
    v5 = 2147500035LL;
LABEL_8:
    FwReportReturnError("FwAuthApp::get_RemoteAddresses", v5);
    goto LABEL_9;
  }
  *a2 = 0;
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
    goto LABEL_7;
  v7 = *((_QWORD *)this + 9);
  if ( !v7 )
    v7 = *((_QWORD *)this + 10);
  DefaultAuthAppRules = GetOpenPortorAuthAppAsBSTR(v7 + 176, a2);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
  {
LABEL_7:
    v5 = (unsigned int)DefaultAuthAppRules;
    goto LABEL_8;
  }
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::get_RemoteAddresses", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180040e00  push    rbx
0x180040e02  push    rbp
0x180040e03  push    rsi
0x180040e04  push    rdi
0x180040e05  sub     rsp, 28h
0x180040e09  mov     rdi, rcx
0x180040e0c  mov     rsi, rdx
0x180040e0f  add     rcx, 10h; lpCriticalSection
0x180040e13  call    cs:__imp_EnterCriticalSection
0x180040e19  test    rsi, rsi
0x180040e1c  jnz     short loc_180040E27
0x180040e1e  mov     ebx, 80004003h
0x180040e23  mov     edx, ebx
0x180040e25  jmp     short loc_180040E61
0x180040e27  mov     rcx, rdi; this
0x180040e2a  mov     qword ptr [rsi], 0
0x180040e31  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180040e36  mov     ebx, eax
0x180040e38  test    eax, eax
0x180040e3a  js      short loc_180040E5F
0x180040e3c  mov     rcx, [rdi+48h]
0x180040e40  test    rcx, rcx
0x180040e43  jnz     short loc_180040E49
0x180040e45  mov     rcx, [rdi+50h]
0x180040e49  add     rcx, 0B0h
0x180040e50  mov     rdx, rsi
0x180040e53  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x180040e59  mov     ebx, eax
0x180040e5b  test    eax, eax
0x180040e5d  jns     short loc_180040E6E
0x180040e5f  mov     edx, eax
0x180040e61  lea     rcx, aFwauthappGetRe; "FwAuthApp::get_RemoteAddresses"
0x180040e68  call    cs:__imp_FwReportReturnError
0x180040e6e  lea     rcx, [rdi+10h]; lpCriticalSection
0x180040e72  call    cs:__imp_LeaveCriticalSection
0x180040e78  test    ebx, ebx
0x180040e7a  jns     short loc_180040E8D
0x180040e7c  mov     edx, ebx
0x180040e7e  lea     rcx, aFwauthappGetRe; "FwAuthApp::get_RemoteAddresses"
0x180040e85  call    cs:__imp_FwReportReturnError
0x180040e8b  mov     ebx, eax
0x180040e8d  mov     eax, ebx
0x180040e8f  add     rsp, 28h
0x180040e93  pop     rdi
0x180040e94  pop     rsi
0x180040e95  pop     rbp
0x180040e96  pop     rbx
0x180040e97  retn
```
