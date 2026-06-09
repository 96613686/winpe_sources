# DavWriteDataToServerRawCallback

- ea: `0x1800214b0`
- end: `0x180021588`
- name: `DavWriteDataToServerRawCallback`
- size: `216`
- prototype: `__int64 __fastcall(PBYTE pbData, _QWORD *pvCallbackContext, ULONG ulLength)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000b7dc`
- `0x1800214b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021541`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021541`
- `WINHTTP!WinHttpWriteData` at `0x180021537`
- `WINHTTP!WinHttpWriteData` at `0x180021537`

## pseudocode

```c
__int64 __fastcall DavWriteDataToServerRawCallback(PBYTE pbData, _QWORD *pvCallbackContext, ULONG ulLength)
{
  DWORD v7; // ebx
  void *v8; // rcx
  DWORD LastError; // eax
  DWORD dwNumberOfBytesWritten; // [rsp+50h] [rbp+18h] BYREF

  dwNumberOfBytesWritten = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, ulLength);
  if ( !ulLength )
    return 0;
  v7 = 0;
  if ( *((_DWORD *)pvCallbackContext + 12) == 3 )
  {
    v8 = (void *)pvCallbackContext[68];
  }
  else
  {
    v8 = 0;
    if ( *((_DWORD *)pvCallbackContext + 12) == 13 )
      v8 = (void *)pvCallbackContext[70];
  }
  if ( !WinHttpWriteData(v8, pbData, ulLength, &dwNumberOfBytesWritten) )
  {
    LastError = GetLastError();
    v7 = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x1800214b0  mov     [rsp+arg_0], rbx
0x1800214b5  mov     [rsp+arg_8], rbp
0x1800214ba  push    rsi
0x1800214bb  push    rdi
0x1800214bc  push    r14
0x1800214be  sub     rsp, 20h
0x1800214c2  mov     esi, r8d
0x1800214c5  mov     [rsp+38h+dwNumberOfBytesWritten], 0
0x1800214cd  mov     rdi, rdx
0x1800214d0  mov     rbp, rcx
0x1800214d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800214da  lea     r14, WPP_GLOBAL_Control
0x1800214e1  cmp     rcx, r14
0x1800214e4  jz      short loc_180021504
0x1800214e6  test    byte ptr [rcx+1Ch], 2
0x1800214ea  jz      short loc_180021504
0x1800214ec  mov     rcx, [rcx+10h]
0x1800214f0  mov     r9d, r8d
0x1800214f3  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x1800214fa  mov     edx, 36h ; '6'
0x1800214ff  call    WPP_SF_d
0x180021504  test    esi, esi
0x180021506  jnz     short loc_18002150C
0x180021508  xor     eax, eax
0x18002150a  jmp     short loc_180021575
0x18002150c  xor     ebx, ebx
0x18002150e  cmp     dword ptr [rdi+30h], 3
0x180021512  jz      short loc_180021525
0x180021514  xor     ecx, ecx
0x180021516  cmp     dword ptr [rdi+30h], 0Dh
0x18002151a  jnz     short loc_18002152C
0x18002151c  mov     rcx, [rdi+230h]
0x180021523  jmp     short loc_18002152C
0x180021525  mov     rcx, [rdi+220h]; hRequest
0x18002152c  lea     r9, [rsp+38h+dwNumberOfBytesWritten]; lpdwNumberOfBytesWritten
0x180021531  mov     r8d, esi; dwNumberOfBytesToWrite
0x180021534  mov     rdx, rbp; lpBuffer
0x180021537  call    cs:__imp_WinHttpWriteData
0x18002153d  test    eax, eax
0x18002153f  jnz     short loc_180021573
0x180021541  call    cs:__imp_GetLastError
0x180021547  mov     ebx, eax
0x180021549  mov     rcx, cs:WPP_GLOBAL_Control
0x180021550  cmp     rcx, r14
0x180021553  jz      short loc_180021573
0x180021555  test    byte ptr [rcx+1Ch], 1
0x180021559  jz      short loc_180021573
0x18002155b  mov     rcx, [rcx+10h]
0x18002155f  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x180021566  mov     edx, 37h ; '7'
0x18002156b  mov     r9d, eax
0x18002156e  call    WPP_SF_d
0x180021573  mov     eax, ebx
0x180021575  mov     rbx, [rsp+38h+arg_0]
0x18002157a  mov     rbp, [rsp+38h+arg_8]
0x18002157f  add     rsp, 20h
0x180021583  pop     r14
0x180021585  pop     rdi
0x180021586  pop     rsi
0x180021587  retn
```
