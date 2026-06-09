# GetTsAudioProtocol(ulong)

- ea: `0x18000a3a8`
- end: `0x18000a573`
- name: `?GetTsAudioProtocol@@YAIK@Z`
- size: `459`
- prototype: `unsigned int __fastcall(DWORD SessionId)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006fdc`
- `0x180009a30`
- `0x1800425ac`

## callees

- `0x18000a3a8`
- `0x180031960`
- `0x1800327f8`
- `0x1800330e4`
- `0x18003320c`

## import_xrefs

- `ntdll!RtlGetActiveConsoleId` at `0x18000a45b`
- `ntdll!RtlGetActiveConsoleId` at `0x18000a45b`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000a48c`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18000a48c`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18000a538`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18000a538`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18000a447`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x18000a447`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000a4b9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000a4f3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000a4b9`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000a4f3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000a4d3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000a504`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000a4d3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000a504`

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
  if ( !(unsigned __int8)IsWinStationIsSessionRemoteablePresent()
    || !(unsigned __int8)IsWTSQuerySessionInformationWPresent() )
  {
    return 0;
  }
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
0x18000a3a8  push    rbp
0x18000a3aa  push    rbx
0x18000a3ab  push    rsi
0x18000a3ac  push    rdi
0x18000a3ad  push    r12
0x18000a3af  push    r14
0x18000a3b1  lea     rbp, [rsp-868h]
0x18000a3b9  sub     rsp, 968h
0x18000a3c0  mov     rax, cs:__security_cookie
0x18000a3c7  xor     rax, rsp
0x18000a3ca  mov     [rbp+890h+var_40], rax
0x18000a3d1  mov     r14d, ecx
0x18000a3d4  mov     [rsp+990h+var_948], 0
0x18000a3dd  lea     rcx, [rsp+990h+var_940]; void *
0x18000a3e2  mov     [rsp+990h+ppBuffer], 0
0x18000a3eb  xor     edx, edx; Val
0x18000a3ed  mov     [rsp+990h+var_95C], 0
0x18000a3f5  mov     r8d, 8F8h; Size
0x18000a3fb  call    memset_0
0x18000a400  mov     [rsp+990h+var_958], 0
0x18000a408  mov     [rsp+990h+var_960], 0
0x18000a40d  call    IsWinStationIsSessionRemoteablePresent
0x18000a412  test    al, al
0x18000a414  jz      loc_18000A54C
0x18000a41a  call    IsWTSQuerySessionInformationWPresent
0x18000a41f  test    al, al
0x18000a421  jz      loc_18000A54C
0x18000a427  cmp     r14d, 0FFFFFFFFh
0x18000a42b  jnz     short loc_18000A43D
0x18000a42d  mov     rax, gs:60h
0x18000a436  mov     r14d, [rax+2C0h]
0x18000a43d  lea     r8, [rsp+990h+var_960]
0x18000a442  mov     edx, r14d
0x18000a445  xor     ecx, ecx
0x18000a447  call    cs:__imp_WinStationIsSessionRemoteable
0x18000a44d  test    al, al
0x18000a44f  jnz     short loc_18000A45B
0x18000a451  mov     edi, 0FFFFh
0x18000a456  jmp     loc_18000A551
0x18000a45b  call    cs:__imp_RtlGetActiveConsoleId
0x18000a461  mov     esi, 0FFFFh
0x18000a466  mov     r12d, 2
0x18000a46c  cmp     eax, r14d
0x18000a46f  jnz     short loc_18000A487
0x18000a471  cmp     [rsp+990h+var_960], 0
0x18000a476  jnz     short loc_18000A47F
0x18000a478  xor     edi, edi
0x18000a47a  jmp     loc_18000A551
0x18000a47f  mov     bl, 1
0x18000a481  movzx   edi, r12w
0x18000a485  jmp     short loc_18000A48C
0x18000a487  movzx   edi, si
0x18000a48a  xor     bl, bl
0x18000a48c  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18000a492  cmp     eax, r14d
0x18000a495  jz      loc_18000A54C
0x18000a49b  test    bl, bl
0x18000a49d  jnz     short loc_18000A4D9
0x18000a49f  lea     rax, [rsp+990h+var_95C]
0x18000a4a4  mov     r8d, 10h; WTSInfoClass
0x18000a4aa  lea     r9, [rsp+990h+ppBuffer]; ppBuffer
0x18000a4af  mov     [rsp+990h+pBytesReturned], rax; pBytesReturned
0x18000a4b4  mov     edx, r14d; SessionId
0x18000a4b7  xor     ecx, ecx; hServer
0x18000a4b9  call    cs:__imp_WTSQuerySessionInformationW
0x18000a4bf  test    eax, eax
0x18000a4c1  jnz     short loc_18000A4CB
0x18000a4c3  movzx   edi, si
0x18000a4c6  jmp     loc_18000A551
0x18000a4cb  mov     rcx, [rsp+990h+ppBuffer]; pMemory
0x18000a4d0  movzx   edi, word ptr [rcx]
0x18000a4d3  call    cs:__imp_WTSFreeMemory
0x18000a4d9  lea     rax, [rsp+990h+var_95C]
0x18000a4de  mov     r8d, 8; WTSInfoClass
0x18000a4e4  lea     r9, [rsp+990h+var_948]; ppBuffer
0x18000a4e9  mov     [rsp+990h+pBytesReturned], rax; pBytesReturned
0x18000a4ee  mov     edx, r14d; SessionId
0x18000a4f1  xor     ecx, ecx; hServer
0x18000a4f3  call    cs:__imp_WTSQuerySessionInformationW
0x18000a4f9  test    eax, eax
0x18000a4fb  jz      short loc_18000A4C3
0x18000a4fd  mov     rcx, [rsp+990h+var_948]; pMemory
0x18000a502  mov     ebx, [rcx]
0x18000a504  call    cs:__imp_WTSFreeMemory
0x18000a50a  cmp     ebx, r12d
0x18000a50d  ja      short loc_18000A4C3
0x18000a50f  xor     eax, eax
0x18000a511  cmp     ax, di
0x18000a514  jz      short loc_18000A551
0x18000a516  lea     rax, [rsp+990h+var_958]
0x18000a51b  mov     r8d, 6
0x18000a521  mov     [rsp+990h+var_968], rax
0x18000a526  lea     r9, [rsp+990h+var_940]
0x18000a52b  mov     edx, r14d
0x18000a52e  mov     dword ptr [rsp+990h+pBytesReturned], 8F8h
0x18000a536  xor     ecx, ecx
0x18000a538  call    cs:__imp_WinStationQueryInformationW
0x18000a53e  test    al, al
0x18000a540  jz      short loc_18000A4C3
0x18000a542  test    dword ptr [rsp+990h+var_940], 100h
0x18000a54a  jz      short loc_18000A551
0x18000a54c  xor     eax, eax
0x18000a54e  movzx   edi, ax
0x18000a551  movzx   eax, di
0x18000a554  mov     rcx, [rbp+890h+var_40]
0x18000a55b  xor     rcx, rsp; StackCookie
0x18000a55e  call    __security_check_cookie
0x18000a563  add     rsp, 968h
0x18000a56a  pop     r14
0x18000a56c  pop     r12
0x18000a56e  pop     rdi
0x18000a56f  pop     rsi
0x18000a570  pop     rbx
0x18000a571  pop     rbp
0x18000a572  retn
```
