# ShouldExecuteSearchForUser(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)

- ea: `0x180018c14`
- end: `0x180018ce2`
- name: `?ShouldExecuteSearchForUser@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z`
- size: `206`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180018a10`

## callees

- `0x180012f10`
- `0x180017060`
- `0x18001719c`
- `0x1800186d0`
- `0x180018c14`
- `0x18001913c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018c87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018c30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180018c30`

## string_xrefs

- `0x180018c6e`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180018c4d`: `Checking if update scan required for User :%s`

## pseudocode

```c
__int64 __fastcall ShouldExecuteSearchForUser(__int64 a1)
{
  HSTRING *TokenSid; // rax
  PCWSTR StringRawBuffer; // rax
  unsigned __int16 *p_string; // rcx
  _BYTE v6[24]; // [rsp+60h] [rbp-18h] BYREF
  HSTRING string; // [rsp+88h] [rbp+10h] BYREF

  TokenSid = (HSTRING *)TokenHelpers::GetTokenSid(&string, a1);
  StringRawBuffer = WindowsGetStringRawBuffer(*TokenSid, 0);
  LogMessage(
    3u,
    "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
    0x1BFu,
    "ShouldExecuteSearchForUser",
    -1,
    L"Checking if update scan required for User :%s",
    0,
    0,
    StringRawBuffer);
  WindowsDeleteString(string);
  string = 0;
  if ( (unsigned __int8)TryGetLastSuccesTimeForUser(a1, &string) )
  {
    GetSearchIntervalDurationsForUsers(v6);
    p_string = (unsigned __int16 *)&string;
  }
  else
  {
    GetSearchIntervalDurationsForUsers(v6);
    p_string = 0;
  }
  return ShouldExecuteSearchForAllUpdates(p_string);
}

```

## disassembly

```asm
0x180018c14  mov     rax, rsp
0x180018c17  push    rbx
0x180018c18  sub     rsp, 70h
0x180018c1c  mov     rbx, rcx
0x180018c1f  mov     rdx, rcx
0x180018c22  lea     rcx, [rax+10h]
0x180018c26  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180018c2b  xor     edx, edx; length
0x180018c2d  mov     rcx, [rax]; string
0x180018c30  call    cs:__imp_WindowsGetStringRawBuffer
0x180018c36  mov     [rsp+78h+var_38], rax
0x180018c3b  mov     [rsp+78h+var_40], 0; unsigned __int16 *
0x180018c44  mov     [rsp+78h+var_48], 0; char *
0x180018c4d  lea     rax, aCheckingIfUpda; "Checking if update scan required for Us"...
0x180018c54  mov     [rsp+78h+var_50], rax; unsigned __int16 *
0x180018c59  mov     [rsp+78h+var_58], 0FFFFFFFFh; int
0x180018c61  lea     r9, aShouldexecutes_0; "ShouldExecuteSearchForUser"
0x180018c68  mov     r8d, 1BFh; unsigned int
0x180018c6e  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180018c75  mov     ecx, 3; unsigned int
0x180018c7a  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x180018c7f  mov     rcx, [rsp+78h+string]; string
0x180018c87  call    cs:__imp_WindowsDeleteString
0x180018c8d  mov     [rsp+78h+string], 0
0x180018c99  lea     rdx, [rsp+78h+string]
0x180018ca1  mov     rcx, rbx
0x180018ca4  call    ?TryGetLastSuccesTimeForUser@@YA_NAEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@AEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; TryGetLastSuccesTimeForUser(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> &)
0x180018ca9  lea     rcx, [rsp+78h+var_18]
0x180018cae  test    al, al
0x180018cb0  jz      short loc_180018CC1
0x180018cb2  call    ?GetSearchIntervalDurationsForUsers@@YA?AUSearchIntervalDurationsInMs@@XZ; GetSearchIntervalDurationsForUsers(void)
0x180018cb7  lea     rcx, [rsp+78h+string]
0x180018cbf  jmp     short loc_180018CC8
0x180018cc1  call    ?GetSearchIntervalDurationsForUsers@@YA?AUSearchIntervalDurationsInMs@@XZ; GetSearchIntervalDurationsForUsers(void)
0x180018cc6  xor     ecx, ecx; unsigned __int16 *
0x180018cc8  movups  xmm0, xmmword ptr [rax]
0x180018ccb  movdqu  [rsp+78h+var_28], xmm0
0x180018cd1  lea     rdx, [rsp+78h+var_28]
0x180018cd6  call    ?ShouldExecuteSearchForAllUpdates@@YA_NPEAV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@USearchIntervalDurationsInMs@@@Z; ShouldExecuteSearchForAllUpdates(std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> *,SearchIntervalDurationsInMs)
0x180018cdb  nop
0x180018cdc  add     rsp, 70h
0x180018ce0  pop     rbx
0x180018ce1  retn
```
