# FwRule::get_RemoteAddresses(ushort * *)

- ea: `0x18001a8b0`
- end: `0x18001a97a`
- name: `?get_RemoteAddresses@FwRule@@UEAAJPEAPEAG@Z`
- size: `202`
- prototype: `__int64 __fastcall(FwRule *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180012e88`
- `0x18001a8b0`
- `0x18003104c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a8dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a913`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a913`
- `fwbase!FwReportReturnError` at `0x18001a936`
- `fwbase!FwReportReturnError` at `0x18001a970`
- `fwbase!FwReportReturnError` at `0x18001a936`
- `fwbase!FwReportReturnError` at `0x18001a970`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001a903`
- `FWPolicyIOMgr!GetOpenPortorAuthAppAsBSTR` at `0x18001a903`

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
0x18001a8b0  push    rbx
0x18001a8b2  push    rbp
0x18001a8b3  push    rsi
0x18001a8b4  push    rdi
0x18001a8b5  sub     rsp, 28h
0x18001a8b9  mov     rsi, rdx
0x18001a8bc  mov     rdi, rcx
0x18001a8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8c6  lea     rax, WPP_GLOBAL_Control
0x18001a8cd  cmp     rcx, rax
0x18001a8d0  jz      short loc_18001A8D8
0x18001a8d2  test    byte ptr [rcx+1Ch], 8
0x18001a8d6  jnz     short loc_18001A93E
0x18001a8d8  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001a8dc  call    cs:__imp_EnterCriticalSection
0x18001a8e2  test    rsi, rsi
0x18001a8e5  jz      short loc_18001A928
0x18001a8e7  mov     qword ptr [rsi], 0
0x18001a8ee  cmp     qword ptr [rdi+50h], 0
0x18001a8f3  jz      short loc_18001A955
0x18001a8f5  mov     rcx, [rdi+50h]
0x18001a8f9  mov     rdx, rsi
0x18001a8fc  add     rcx, 0B0h
0x18001a903  call    cs:__imp_GetOpenPortorAuthAppAsBSTR
0x18001a909  mov     ebx, eax
0x18001a90b  test    eax, eax
0x18001a90d  js      short loc_18001A963
0x18001a90f  lea     rcx, [rdi+10h]; lpCriticalSection
0x18001a913  call    cs:__imp_LeaveCriticalSection
0x18001a919  test    ebx, ebx
0x18001a91b  js      short loc_18001A967
0x18001a91d  mov     eax, ebx
0x18001a91f  add     rsp, 28h
0x18001a923  pop     rdi
0x18001a924  pop     rsi
0x18001a925  pop     rbp
0x18001a926  pop     rbx
0x18001a927  retn
0x18001a928  mov     ebx, 80004003h
0x18001a92d  mov     edx, ebx
0x18001a92f  lea     rcx, aFwruleGetRemot_2; "FwRule::get_RemoteAddresses"
0x18001a936  call    cs:__imp_FwReportReturnError
0x18001a93c  jmp     short loc_18001A90F
0x18001a93e  mov     rcx, [rcx+10h]
0x18001a942  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x18001a949  mov     edx, 22h ; '"'
0x18001a94e  call    WPP_SF_
0x18001a953  jmp     short loc_18001A8D8
0x18001a955  mov     rcx, rdi; this
0x18001a958  call    ?CreateRule@FwRule@@AEAAJXZ; FwRule::CreateRule(void)
0x18001a95d  mov     ebx, eax
0x18001a95f  test    eax, eax
0x18001a961  jns     short loc_18001A8F5
0x18001a963  mov     edx, eax
0x18001a965  jmp     short loc_18001A92F
0x18001a967  mov     edx, ebx
0x18001a969  lea     rcx, aFwruleGetRemot_2; "FwRule::get_RemoteAddresses"
0x18001a970  call    cs:__imp_FwReportReturnError
0x18001a976  mov     ebx, eax
0x18001a978  jmp     short loc_18001A91D
```
