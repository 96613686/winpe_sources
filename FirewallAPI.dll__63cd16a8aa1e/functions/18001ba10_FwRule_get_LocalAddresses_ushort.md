# FwRule::get_LocalAddresses(ushort * *)

- ea: `0x18001ba10`
- end: `0x18001bad7`
- name: `?get_LocalAddresses@FwRule@@UEAAJPEAPEAG@Z`
- size: `199`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012e88`
- `0x18001ba10`
- `0x18003104c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba3c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ba3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ba70`
- `fwbase!FwReportReturnError` at `0x18001babc`
- `fwbase!FwReportReturnError` at `0x18001bacd`
- `fwbase!FwReportReturnError` at `0x18001babc`
- `fwbase!FwReportReturnError` at `0x18001bacd`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001ba60`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001ba60`

## pseudocode

```c
__int64 __fastcall FwRule::get_LocalAddresses(FwRule *this, unsigned __int16 **a2)
{
  int OpenPortorAuthAppAsBSTR; // eax
  int v5; // ebx
  __int64 v7; // rdx

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( a2 )
  {
    *a2 = 0;
    if ( *((_QWORD *)this + 10)
      || (OpenPortorAuthAppAsBSTR = FwRule::CreateRule(this), v5 = OpenPortorAuthAppAsBSTR, OpenPortorAuthAppAsBSTR >= 0) )
    {
      OpenPortorAuthAppAsBSTR = GetOpenPortorAuthAppAsBSTR(*((_QWORD *)this + 10) + 104LL, a2);
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
  FwReportReturnError("FwRule::get_LocalAddresses", v7);
LABEL_7:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( v5 < 0 )
    return (unsigned int)FwReportReturnError("FwRule::get_LocalAddresses", (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001ba10  push    rbx
0x18001ba12  push    rbp
0x18001ba13  push    rsi
0x18001ba14  push    rdi
0x18001ba15  sub     rsp, 28h
0x18001ba19  mov     rsi, rdx
0x18001ba1c  mov     rdi, rcx
0x18001ba1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba26  lea     rax, WPP_GLOBAL_Control
0x18001ba2d  cmp     rcx, rax
0x18001ba30  jz      short loc_18001BA38
0x18001ba32  test    byte ptr [rcx+1Ch], 8
0x18001ba36  jnz     short loc_18001BA85
0x18001ba38  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001ba3c  call    cs:__imp_EnterCriticalSection
0x18001ba42  test    rsi, rsi
0x18001ba45  jz      short loc_18001BA9C
0x18001ba47  mov     qword ptr [rsi], 0
0x18001ba4e  cmp     qword ptr [rdi+50h], 0
0x18001ba53  jz      short loc_18001BAA5
0x18001ba55  mov     rcx, [rdi+50h]
0x18001ba59  mov     rdx, rsi
0x18001ba5c  add     rcx, 68h ; 'h'
0x18001ba60  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18001ba66  mov     ebx, eax
0x18001ba68  test    eax, eax
0x18001ba6a  js      short loc_18001BAB3
0x18001ba6c  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001ba70  call    cs:__imp_LeaveCriticalSection
0x18001ba76  test    ebx, ebx
0x18001ba78  js      short loc_18001BAC4
0x18001ba7a  mov     eax, ebx
0x18001ba7c  add     rsp, 28h
0x18001ba80  pop     rdi
0x18001ba81  pop     rsi
0x18001ba82  pop     rbp
0x18001ba83  pop     rbx
0x18001ba84  retn
0x18001ba85  mov     rcx, [rcx+10h]
0x18001ba89  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18001ba90  mov     edx, 1Fh
0x18001ba95  call    WPP_SF_
0x18001ba9a  jmp     short loc_18001BA38
0x18001ba9c  mov     ebx, 80004003h
0x18001baa1  mov     edx, ebx
0x18001baa3  jmp     short loc_18001BAB5
0x18001baa5  mov     rcx, rdi; this
0x18001baa8  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18001baad  mov     ebx, eax
0x18001baaf  test    eax, eax
0x18001bab1  jns     short loc_18001BA55
0x18001bab3  mov     edx, eax
0x18001bab5  lea     rcx, aFwruleGetLocal; "FwRule::get_LocalAddresses"
0x18001babc  call    cs:__imp_FwReportReturnError
0x18001bac2  jmp     short loc_18001BA6C
0x18001bac4  mov     edx, ebx
0x18001bac6  lea     rcx, aFwruleGetLocal; "FwRule::get_LocalAddresses"
0x18001bacd  call    cs:__imp_FwReportReturnError
0x18001bad3  mov     ebx, eax
0x18001bad5  jmp     short loc_18001BA7A
```
