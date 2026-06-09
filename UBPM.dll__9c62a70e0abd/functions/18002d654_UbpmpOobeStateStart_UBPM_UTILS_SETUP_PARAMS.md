# UbpmpOobeStateStart(_UBPM_UTILS_SETUP_PARAMS *)

- ea: `0x18002d654`
- end: `0x18002d75b`
- name: `?UbpmpOobeStateStart@@YAKPEAU_UBPM_UTILS_SETUP_PARAMS@@@Z`
- size: `263`
- prototype: `unsigned int __fastcall(struct _UBPM_UTILS_SETUP_PARAMS *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180036484`

## callees

- `0x1800103c0`
- `0x18002b784`
- `0x18002d654`
- `0x18003639c`
- `0x180040260`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d73a`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002d73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d698`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d6c7`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18002d684`
- `api-ms-win-oobe-notification-l1-1-0!RegisterWaitUntilOOBECompleted` at `0x18002d684`

## pseudocode

```c
__int64 __fastcall UbpmpOobeStateStart(struct _UBPM_UTILS_SETUP_PARAMS *a1)
{
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  _BYTE v5[4]; // [rsp+30h] [rbp-28h] BYREF
  DWORD LastError; // [rsp+34h] [rbp-24h] BYREF
  __int128 v7; // [rsp+38h] [rbp-20h] BYREF

  v5[0] = 0;
  v7 = 0;
  if ( !(unsigned int)RegisterWaitUntilOOBECompleted(UbpmpUserOOBECompletedCallback, 0, &qword_18004FB68) )
  {
    if ( GetLastError() != 5023 && GetLastError() != 50 && (unsigned int)dword_18004F0F0 > 2 )
    {
      LastError = GetLastError();
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v1,
        (unsigned __int8 *)&dword_180045FB4,
        v2,
        v3,
        (__int64)&LastError);
    }
    if ( (int)OOBE::CompleteTime::TryGetTime(v5, &v7) < 0 )
      v7 = 0;
    UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE((struct _UBPM_SRWLOCK *)&g_SystemSetup);
    unk_18004FB50 |= 3u;
    dword_18004FB48 = 0;
    xmmword_18004FB52 = v7;
    RtlReleaseSRWLockExclusive(&g_SystemSetup);
  }
  return 0;
}

```

## disassembly

```asm
0x18002d654  sub     rsp, 58h
0x18002d658  mov     rax, cs:__security_cookie
0x18002d65f  xor     rax, rsp
0x18002d662  mov     [rsp+58h+var_10], rax
0x18002d667  xorps   xmm0, xmm0
0x18002d66a  mov     [rsp+58h+var_28], 0
0x18002d66f  lea     r8, qword_18004FB68
0x18002d676  xor     edx, edx
0x18002d678  lea     rcx, ?UbpmpUserOOBECompletedCallback@@YAXPEAX@Z; UbpmpUserOOBECompletedCallback(void *)
0x18002d67f  movups  [rsp+58h+var_20], xmm0
0x18002d684  call    cs:__imp_RegisterWaitUntilOOBECompleted
0x18002d68b  nop     dword ptr [rax+rax+00h]
0x18002d690  test    eax, eax
0x18002d692  jnz     loc_18002D746
0x18002d698  call    cs:__imp_GetLastError
0x18002d69f  nop     dword ptr [rax+rax+00h]
0x18002d6a4  cmp     eax, 139Fh
0x18002d6a9  jz      short loc_18002D6ED
0x18002d6ab  call    cs:__imp_GetLastError
0x18002d6b2  nop     dword ptr [rax+rax+00h]
0x18002d6b7  cmp     eax, 32h ; '2'
0x18002d6ba  jz      short loc_18002D6ED
0x18002d6bc  mov     eax, cs:dword_18004F0F0
0x18002d6c2  cmp     eax, 2
0x18002d6c5  jbe     short loc_18002D6ED
0x18002d6c7  call    cs:__imp_GetLastError
0x18002d6ce  nop     dword ptr [rax+rax+00h]
0x18002d6d3  mov     [rsp+58h+var_24], eax
0x18002d6d7  lea     rdx, dword_180045FB4
0x18002d6de  lea     rax, [rsp+58h+var_24]
0x18002d6e3  mov     [rsp+58h+var_38], rax
0x18002d6e8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002d6ed  lea     rdx, [rsp+58h+var_20]
0x18002d6f2  lea     rcx, [rsp+58h+var_28]
0x18002d6f7  call    OOBE__CompleteTime__TryGetTime
0x18002d6fc  test    eax, eax
0x18002d6fe  jns     short loc_18002D708
0x18002d700  xorps   xmm0, xmm0
0x18002d703  movups  [rsp+58h+var_20], xmm0
0x18002d708  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; struct _UBPM_SRWLOCK *
0x18002d70f  call    ?UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE@@YAXAEAU_UBPM_SRWLOCK@@@Z; UBPM_ACQUIRE_SRWLOCK_EXCLUSIVE(_UBPM_SRWLOCK &)
0x18002d714  movups  xmm0, [rsp+58h+var_20]
0x18002d719  or      word ptr cs:unk_18004FB50, 3
0x18002d721  lea     rcx, ?g_SystemSetup@@3U_UBPM_UTILS_SETUP_PARAMS@@A; _UBPM_UTILS_SETUP_PARAMS g_SystemSetup
0x18002d728  mov     cs:dword_18004FB48, 0
0x18002d732  movdqu  cs:xmmword_18004FB52, xmm0
0x18002d73a  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002d741  nop     dword ptr [rax+rax+00h]
0x18002d746  xor     eax, eax
0x18002d748  mov     rcx, [rsp+58h+var_10]
0x18002d74d  xor     rcx, rsp; StackCookie
0x18002d750  call    __security_check_cookie
0x18002d755  add     rsp, 58h
0x18002d759  retn
```
