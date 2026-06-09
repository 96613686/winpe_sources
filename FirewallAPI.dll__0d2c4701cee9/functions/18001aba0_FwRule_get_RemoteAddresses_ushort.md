# FwRule::get_RemoteAddresses(ushort * *)

- ea: `0x18001aba0`
- end: `0x18001ac90`
- name: `?get_RemoteAddresses@FwRule@@UEAAJPEAPEAG@Z`
- size: `240`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012dcc`
- `0x18001aba0`
- `0x18003336c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001abcc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001abcc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac0f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ac0f`
- `fwbase!FwReportReturnError` at `0x18001ac39`
- `fwbase!FwReportReturnError` at `0x18001ac80`
- `fwbase!FwReportReturnError` at `0x18001ac39`
- `fwbase!FwReportReturnError` at `0x18001ac80`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001abf9`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001abf9`

## pseudocode

```c
__int64 __fastcall FwRule::get_RemoteAddresses(FwRule *this, unsigned __int16 **a2)
{
  int OpenPortorAuthAppAsBSTR; // eax
  int v5; // ebx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_QWORD *)this + 10)
      || (OpenPortorAuthAppAsBSTR = FwRule::CreateRule(this), v5 = OpenPortorAuthAppAsBSTR, OpenPortorAuthAppAsBSTR >= 0) )
    {
      OpenPortorAuthAppAsBSTR = GetOpenPortorAuthAppAsBSTR(*((_QWORD *)this + 10) + 176LL, a2);
      v5 = OpenPortorAuthAppAsBSTR;
      if ( OpenPortorAuthAppAsBSTR >= 0 )
        goto LABEL_7;
    }
    v7 = (unsigned int)OpenPortorAuthAppAsBSTR;
  }
  else
  {
    v5 = -2147467261;
    v7 = 2147500035LL;
  }
  FwReportReturnError("FwRule::get_RemoteAddresses", v7);
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRule::get_RemoteAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001aba0  push    rbx
0x18001aba2  push    rbp
0x18001aba3  push    rsi
0x18001aba4  push    rdi
0x18001aba5  sub     rsp, 28h
0x18001aba9  mov     rsi, rdx
0x18001abac  mov     rdi, rcx
0x18001abaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abb6  lea     rax, WPP_GLOBAL_Control
0x18001abbd  cmp     rcx, rax
0x18001abc0  jz      short loc_18001ABC8
0x18001abc2  test    byte ptr [rcx+1Ch], 8
0x18001abc6  jnz     short loc_18001AC47
0x18001abc8  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001abcc  call    cs:__imp_EnterCriticalSection
0x18001abd3  nop     dword ptr [rax+rax+00h]
0x18001abd8  test    rsi, rsi
0x18001abdb  jz      short loc_18001AC2B
0x18001abdd  mov     qword ptr [rsi], 0
0x18001abe4  cmp     qword ptr [rdi+50h], 0
0x18001abe9  jz      short loc_18001AC61
0x18001abeb  mov     rcx, [rdi+50h]
0x18001abef  mov     rdx, rsi
0x18001abf2  add     rcx, 0B0h
0x18001abf9  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18001ac00  nop     dword ptr [rax+rax+00h]
0x18001ac05  mov     ebx, eax
0x18001ac07  test    eax, eax
0x18001ac09  js      short loc_18001AC73
0x18001ac0b  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001ac0f  call    cs:__imp_LeaveCriticalSection
0x18001ac16  nop     dword ptr [rax+rax+00h]
0x18001ac1b  test    ebx, ebx
0x18001ac1d  js      short loc_18001AC77
0x18001ac1f  mov     eax, ebx
0x18001ac21  add     rsp, 28h
0x18001ac25  pop     rdi
0x18001ac26  pop     rsi
0x18001ac27  pop     rbp
0x18001ac28  pop     rbx
0x18001ac29  retn
0x18001ac2b  mov     ebx, 80004003h
0x18001ac30  mov     edx, ebx
0x18001ac32  lea     rcx, aFwruleGetRemot_2; "FwRule::get_RemoteAddresses"
0x18001ac39  call    cs:__imp_FwReportReturnError
0x18001ac40  nop     dword ptr [rax+rax+00h]
0x18001ac45  jmp     short loc_18001AC0B
0x18001ac47  mov     rcx, [rcx+10h]
0x18001ac4b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18001ac52  mov     edx, 22h ; '"'
0x18001ac57  call    WPP_SF_
0x18001ac5c  jmp     loc_18001ABC8
0x18001ac61  mov     rcx, rdi; this
0x18001ac64  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18001ac69  mov     ebx, eax
0x18001ac6b  test    eax, eax
0x18001ac6d  jns     loc_18001ABEB
0x18001ac73  mov     edx, eax
0x18001ac75  jmp     short loc_18001AC32
0x18001ac77  mov     edx, ebx
0x18001ac79  lea     rcx, aFwruleGetRemot_2; "FwRule::get_RemoteAddresses"
0x18001ac80  call    cs:__imp_FwReportReturnError
0x18001ac87  nop     dword ptr [rax+rax+00h]
0x18001ac8c  mov     ebx, eax
0x18001ac8e  jmp     short loc_18001AC1F
```
