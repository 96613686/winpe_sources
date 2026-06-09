# GetTsAudioProtocol(ulong)

- ea: `0x180006fc8`
- end: `0x180007193`
- name: `?GetTsAudioProtocol@@YAIK@Z`
- size: `459`
- prototype: `unsigned int __fastcall(DWORD SessionId)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006c04`
- `0x180008eb4`

## callees

- `0x180006fc8`
- `0x18003e920`
- `0x18003f7a4`
- `0x1800408d8`
- `0x180040d98`

## import_xrefs

- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800070ac`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800070ac`
- `ntdll!RtlGetActiveConsoleId` at `0x18000707b`
- `ntdll!RtlGetActiveConsoleId` at `0x18000707b`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800070d9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180007113`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x1800070d9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x180007113`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800070f3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180007124`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x1800070f3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180007124`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180007067`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180007067`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180007158`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x180007158`

## pseudocode

```c
__int64 __fastcall GetTsAudioProtocol(DWORD SessionId)
{
  WCHAR v2; // di
  char v3; // bl
  unsigned int v4; // ebx
  _BYTE v6[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pBytesReturned; // [rsp+34h] [rbp-CCh] BYREF
  int v8; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR ppBuffer; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR v10; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v11[1152]; // [rsp+50h] [rbp-B0h] BYREF

  v10 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  memset_0(v11, 0, 0x8F8u);
  v8 = 0;
  v6[0] = 0;
  if ( !(unsigned __int8)IsWinStationFreePropertyValuePresent() || !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
    return 0;
  if ( SessionId == -1 )
    SessionId = NtCurrentPeb()->SessionId;
  if ( (unsigned __int8)WinStationIsSessionRemoteable(0, SessionId, v6) )
  {
    if ( (unsigned int)RtlGetActiveConsoleId() == SessionId )
    {
      if ( !v6[0] )
        return 0;
      v3 = 1;
      v2 = 2;
    }
    else
    {
      v2 = -1;
      v3 = 0;
    }
    if ( (unsigned int)RtlGetCurrentServiceSessionId() != SessionId )
    {
      if ( !v3 )
      {
        if ( !WTSQuerySessionInformationW(0, SessionId, WTSClientProtocolType, &ppBuffer, &pBytesReturned) )
          return (WCHAR)-1;
        v2 = *ppBuffer;
        WTSFreeMemory(ppBuffer);
      }
      if ( !WTSQuerySessionInformationW(0, SessionId, WTSConnectState, &v10, &pBytesReturned) )
        return (WCHAR)-1;
      v4 = *(_DWORD *)v10;
      WTSFreeMemory(v10);
      if ( v4 > 2 )
        return (WCHAR)-1;
      if ( !v2 )
        return v2;
      if ( !(unsigned __int8)WinStationQueryInformationW(0, SessionId, 6, v11, 2296, &v8) )
        return (WCHAR)-1;
      if ( (v11[0] & 0x100) == 0 )
        return v2;
    }
    return 0;
  }
  return (WCHAR)-1;
}

```

## disassembly

```asm
0x180006fc8  push    rbp
0x180006fca  push    rbx
0x180006fcb  push    rsi
0x180006fcc  push    rdi
0x180006fcd  push    r12
0x180006fcf  push    r14
0x180006fd1  lea     rbp, [rsp-868h]
0x180006fd9  sub     rsp, 968h
0x180006fe0  mov     rax, cs:__security_cookie
0x180006fe7  xor     rax, rsp
0x180006fea  mov     [rbp+890h+var_40], rax
0x180006ff1  mov     r14d, ecx
0x180006ff4  mov     [rsp+990h+var_948], 0
0x180006ffd  lea     rcx, [rsp+990h+var_940]; void *
0x180007002  mov     [rsp+990h+ppBuffer], 0
0x18000700b  xor     edx, edx; Val
0x18000700d  mov     [rsp+990h+var_95C], 0
0x180007015  mov     r8d, 8F8h; Size
0x18000701b  call    memset_0
0x180007020  mov     [rsp+990h+var_958], 0
0x180007028  mov     [rsp+990h+var_960], 0
0x18000702d  call    IsWinStationFreePropertyValuePresent
0x180007032  test    al, al
0x180007034  jz      loc_18000716C
0x18000703a  call    IsWTSEnumerateSessionsWPresent
0x18000703f  test    al, al
0x180007041  jz      loc_18000716C
0x180007047  cmp     r14d, 0FFFFFFFFh
0x18000704b  jnz     short loc_18000705D
0x18000704d  mov     rax, gs:60h
0x180007056  mov     r14d, [rax+2C0h]
0x18000705d  lea     r8, [rsp+990h+var_960]
0x180007062  mov     edx, r14d
0x180007065  xor     ecx, ecx
0x180007067  call    cs:__imp_WinStationIsSessionRemoteable
0x18000706d  test    al, al
0x18000706f  jnz     short loc_18000707B
0x180007071  mov     edi, 0FFFFh
0x180007076  jmp     loc_180007171
0x18000707b  call    cs:__imp_RtlGetActiveConsoleId
0x180007081  mov     esi, 0FFFFh
0x180007086  mov     r12d, 2
0x18000708c  cmp     eax, r14d
0x18000708f  jnz     short loc_1800070A7
0x180007091  cmp     [rsp+990h+var_960], 0
0x180007096  jnz     short loc_18000709F
0x180007098  xor     edi, edi
0x18000709a  jmp     loc_180007171
0x18000709f  mov     bl, 1
0x1800070a1  movzx   edi, r12w
0x1800070a5  jmp     short loc_1800070AC
0x1800070a7  movzx   edi, si
0x1800070aa  xor     bl, bl
0x1800070ac  call    cs:__imp_RtlGetCurrentServiceSessionId
0x1800070b2  cmp     eax, r14d
0x1800070b5  jz      loc_18000716C
0x1800070bb  test    bl, bl
0x1800070bd  jnz     short loc_1800070F9
0x1800070bf  lea     rax, [rsp+990h+var_95C]
0x1800070c4  mov     r8d, 10h; WTSInfoClass
0x1800070ca  lea     r9, [rsp+990h+ppBuffer]; ppBuffer
0x1800070cf  mov     [rsp+990h+pBytesReturned], rax; pBytesReturned
0x1800070d4  mov     edx, r14d; SessionId
0x1800070d7  xor     ecx, ecx; hServer
0x1800070d9  call    cs:__imp_WTSQuerySessionInformationW
0x1800070df  test    eax, eax
0x1800070e1  jnz     short loc_1800070EB
0x1800070e3  movzx   edi, si
0x1800070e6  jmp     loc_180007171
0x1800070eb  mov     rcx, [rsp+990h+ppBuffer]; pMemory
0x1800070f0  movzx   edi, word ptr [rcx]
0x1800070f3  call    cs:__imp_WTSFreeMemory
0x1800070f9  lea     rax, [rsp+990h+var_95C]
0x1800070fe  mov     r8d, 8; WTSInfoClass
0x180007104  lea     r9, [rsp+990h+var_948]; ppBuffer
0x180007109  mov     [rsp+990h+pBytesReturned], rax; pBytesReturned
0x18000710e  mov     edx, r14d; SessionId
0x180007111  xor     ecx, ecx; hServer
0x180007113  call    cs:__imp_WTSQuerySessionInformationW
0x180007119  test    eax, eax
0x18000711b  jz      short loc_1800070E3
0x18000711d  mov     rcx, [rsp+990h+var_948]; pMemory
0x180007122  mov     ebx, [rcx]
0x180007124  call    cs:__imp_WTSFreeMemory
0x18000712a  cmp     ebx, r12d
0x18000712d  ja      short loc_1800070E3
0x18000712f  xor     eax, eax
0x180007131  cmp     ax, di
0x180007134  jz      short loc_180007171
0x180007136  lea     rax, [rsp+990h+var_958]
0x18000713b  mov     r8d, 6
0x180007141  mov     [rsp+990h+var_968], rax
0x180007146  lea     r9, [rsp+990h+var_940]
0x18000714b  mov     edx, r14d
0x18000714e  mov     dword ptr [rsp+990h+pBytesReturned], 8F8h
0x180007156  xor     ecx, ecx
0x180007158  call    cs:__imp_WinStationQueryInformationW
0x18000715e  test    al, al
0x180007160  jz      short loc_1800070E3
0x180007162  test    dword ptr [rsp+990h+var_940], 100h
0x18000716a  jz      short loc_180007171
0x18000716c  xor     eax, eax
0x18000716e  movzx   edi, ax
0x180007171  movzx   eax, di
0x180007174  mov     rcx, [rbp+890h+var_40]
0x18000717b  xor     rcx, rsp; StackCookie
0x18000717e  call    __security_check_cookie
0x180007183  add     rsp, 968h
0x18000718a  pop     r14
0x18000718c  pop     r12
0x18000718e  pop     rdi
0x18000718f  pop     rsi
0x180007190  pop     rbx
0x180007191  pop     rbp
0x180007192  retn
```
