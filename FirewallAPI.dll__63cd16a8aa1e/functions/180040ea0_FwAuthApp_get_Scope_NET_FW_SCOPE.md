# FwAuthApp::get_Scope(NET_FW_SCOPE_ *)

- ea: `0x180040ea0`
- end: `0x180040f2f`
- name: `?get_Scope@FwAuthApp@@UEAAJPEAW4NET_FW_SCOPE_@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(FwAuthApp *__hidden this, enum NET_FW_SCOPE_ *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180001dd0`
- `0x180040ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180040eb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180040f08`
- `fwbase!FwReportReturnError` at `0x180040ecd`
- `fwbase!FwReportReturnError` at `0x180040f1b`
- `fwbase!FwReportReturnError` at `0x180040ecd`
- `fwbase!FwReportReturnError` at `0x180040f1b`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180040efb`
- `FWPolicyIOMgr!GetOpenPortOrAuthAppAddrScope` at `0x180040efb`

## pseudocode

```c
__int64 __fastcall FwAuthApp::get_Scope(FwAuthApp *this, enum NET_FW_SCOPE_ *a2)
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
LABEL_3:
    FwReportReturnError("FwAuthApp::get_Scope", v5);
    goto LABEL_9;
  }
  DefaultAuthAppRules = FwAuthApp::CreateDefaultAuthAppRules(this);
  v4 = DefaultAuthAppRules;
  if ( DefaultAuthAppRules < 0 )
  {
    v5 = (unsigned int)DefaultAuthAppRules;
    goto LABEL_3;
  }
  v7 = *((_QWORD *)this + 9);
  if ( !v7 )
    v7 = *((_QWORD *)this + 10);
  *a2 = GetOpenPortOrAuthAppAddrScope(v7 + 176);
LABEL_9:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwAuthApp::get_Scope", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180040ea0  push    rbx
0x180040ea2  push    rsi
0x180040ea3  push    rdi
0x180040ea4  push    r14
0x180040ea6  sub     rsp, 28h
0x180040eaa  mov     rdi, rcx
0x180040ead  mov     r14, rdx
0x180040eb0  add     rcx, 10h; lpCriticalSection
0x180040eb4  call    cs:__imp_EnterCriticalSection
0x180040eba  test    r14, r14
0x180040ebd  jnz     short loc_180040ED5
0x180040ebf  mov     ebx, 80004003h
0x180040ec4  mov     edx, ebx
0x180040ec6  lea     rcx, aFwauthappGetSc; "FwAuthApp::get_Scope"
0x180040ecd  call    cs:__imp_FwReportReturnError
0x180040ed3  jmp     short loc_180040F04
0x180040ed5  mov     rcx, rdi; this
0x180040ed8  call    ?CreateDefaultAuthAppRules@FwAuthApp@@AEAAJXZ; FwAuthApp::CreateDefaultAuthAppRules(void)
0x180040edd  mov     ebx, eax
0x180040edf  test    eax, eax
0x180040ee1  jns     short loc_180040EE7
0x180040ee3  mov     edx, eax
0x180040ee5  jmp     short loc_180040EC6
0x180040ee7  mov     rcx, [rdi+48h]
0x180040eeb  test    rcx, rcx
0x180040eee  jnz     short loc_180040EF4
0x180040ef0  mov     rcx, [rdi+50h]
0x180040ef4  add     rcx, 0B0h
0x180040efb  call    cs:__imp_GetOpenPortOrAuthAppAddrScope
0x180040f01  mov     [r14], eax
0x180040f04  lea     rcx, [rdi+10h]; lpCriticalSection
0x180040f08  call    cs:__imp_LeaveCriticalSection
0x180040f0e  test    ebx, ebx
0x180040f10  jns     short loc_180040F23
0x180040f12  mov     edx, ebx
0x180040f14  lea     rcx, aFwauthappGetSc; "FwAuthApp::get_Scope"
0x180040f1b  call    cs:__imp_FwReportReturnError
0x180040f21  mov     ebx, eax
0x180040f23  mov     eax, ebx
0x180040f25  add     rsp, 28h
0x180040f29  pop     r14
0x180040f2b  pop     rdi
0x180040f2c  pop     rsi
0x180040f2d  pop     rbx
0x180040f2e  retn
```
