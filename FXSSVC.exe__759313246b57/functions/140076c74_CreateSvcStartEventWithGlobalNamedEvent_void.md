# CreateSvcStartEventWithGlobalNamedEvent(void)

- ea: `0x140076c74`
- end: `0x140076dfe`
- name: `?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ`
- size: `394`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140077814`

## callees

- `0x140004c78`
- `0x140004ca8`
- `0x140076c74`
- `0x1400772c8`
- `0x140077ce4`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140076cc2`
- `KERNEL32!OpenEventW` at `0x140076cc2`
- `KERNEL32!GetLastError` at `0x140076cd7`
- `KERNEL32!GetLastError` at `0x140076d00`
- `KERNEL32!GetLastError` at `0x140076d42`
- `KERNEL32!GetLastError` at `0x140076d99`
- `KERNEL32!GetLastError` at `0x140076cd7`
- `KERNEL32!GetLastError` at `0x140076d00`
- `KERNEL32!GetLastError` at `0x140076d42`
- `KERNEL32!GetLastError` at `0x140076d99`
- `KERNEL32!SetLastError` at `0x140076de4`
- `KERNEL32!SetLastError` at `0x140076de4`
- `KERNEL32!CreateEventW` at `0x140076d83`
- `KERNEL32!CreateEventW` at `0x140076d83`

## pseudocode

```c
HANDLE CreateSvcStartEventWithGlobalNamedEvent(void)
{
  HANDLE result; // rax
  DWORD LastError; // eax
  __int64 v2; // rdx
  struct _SECURITY_ATTRIBUTES *SecurityAttributesWithThreadAsOwner; // rax
  struct _SECURITY_ATTRIBUTES *v4; // rsi
  DWORD v5; // edi
  HANDLE EventW; // rbx
  DWORD v7; // eax

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_db036311db36307996a98c23702218b2_Traceguids);
  }
  result = OpenEventW(0x100000u, 0, L"Global\\FaxSvcRPCStarted-1ed23866-f90b-4ec5-b77e-36e8709422b6");
  if ( !result )
  {
    if ( GetLastError() != 2 )
    {
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      LastError = GetLastError();
      v2 = 18;
LABEL_16:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, WPP_db036311db36307996a98c23702218b2_Traceguids, LastError);
      return 0;
    }
    SecurityAttributesWithThreadAsOwner = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner();
    v4 = SecurityAttributesWithThreadAsOwner;
    if ( !SecurityAttributesWithThreadAsOwner )
    {
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return 0;
      }
      LastError = GetLastError();
      v2 = 19;
      goto LABEL_16;
    }
    v5 = 0;
    EventW = CreateEventW(
               SecurityAttributesWithThreadAsOwner,
               1,
               0,
               L"Global\\FaxSvcRPCStarted-1ed23866-f90b-4ec5-b77e-36e8709422b6");
    if ( !EventW )
    {
      v7 = GetLastError();
      v5 = v7;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_db036311db36307996a98c23702218b2_Traceguids, v7);
      }
    }
    DestroySecurityAttributes(v4);
    if ( !EventW )
      SetLastError(v5);
    return EventW;
  }
  return result;
}

```

## disassembly

```asm
0x140076c74  push    rbx
0x140076c76  push    rsi
0x140076c77  push    rdi
0x140076c78  push    r14
0x140076c7a  sub     rsp, 28h
0x140076c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140076c85  lea     r14, WPP_GLOBAL_Control
0x140076c8c  cmp     rcx, r14
0x140076c8f  jz      short loc_140076CB2
0x140076c91  test    byte ptr [rcx+1Ch], 2
0x140076c95  jz      short loc_140076CB2
0x140076c97  cmp     byte ptr [rcx+19h], 5
0x140076c9b  jb      short loc_140076CB2
0x140076c9d  mov     rcx, [rcx+10h]
0x140076ca1  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076ca8  mov     edx, 11h
0x140076cad  call    WPP_SF_
0x140076cb2  mov     ebx, 100000h
0x140076cb7  lea     r8, aGlobalFaxsvcrp; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x140076cbe  mov     ecx, ebx; dwDesiredAccess
0x140076cc0  xor     edx, edx; bInheritHandle
0x140076cc2  call    cs:__imp_OpenEventW
0x140076cc9  nop     dword ptr [rax+rax+00h]
0x140076cce  test    rax, rax
0x140076cd1  jnz     loc_140076DF3
0x140076cd7  call    cs:__imp_GetLastError
0x140076cde  nop     dword ptr [rax+rax+00h]
0x140076ce3  cmp     eax, 2
0x140076ce6  jz      short loc_140076D13
0x140076ce8  mov     rax, cs:WPP_GLOBAL_Control
0x140076cef  cmp     rax, r14
0x140076cf2  jz      short loc_140076D6B
0x140076cf4  test    byte ptr [rax+1Ch], 2
0x140076cf8  jz      short loc_140076D6B
0x140076cfa  cmp     byte ptr [rax+19h], 2
0x140076cfe  jb      short loc_140076D6B
0x140076d00  call    cs:__imp_GetLastError
0x140076d07  nop     dword ptr [rax+rax+00h]
0x140076d0c  mov     edx, 12h
0x140076d11  jmp     short loc_140076D51
0x140076d13  mov     r8d, 1F0003h
0x140076d19  mov     edx, ebx
0x140076d1b  mov     ecx, ebx
0x140076d1d  call    CreateSecurityAttributesWithThreadAsOwner
0x140076d22  mov     rsi, rax
0x140076d25  test    rax, rax
0x140076d28  jnz     short loc_140076D72
0x140076d2a  mov     rax, cs:WPP_GLOBAL_Control
0x140076d31  cmp     rax, r14
0x140076d34  jz      short loc_140076D6B
0x140076d36  test    byte ptr [rax+1Ch], 2
0x140076d3a  jz      short loc_140076D6B
0x140076d3c  cmp     byte ptr [rax+19h], 2
0x140076d40  jb      short loc_140076D6B
0x140076d42  call    cs:__imp_GetLastError
0x140076d49  nop     dword ptr [rax+rax+00h]
0x140076d4e  lea     edx, [rsi+13h]
0x140076d51  mov     rcx, cs:WPP_GLOBAL_Control
0x140076d58  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076d5f  mov     r9d, eax
0x140076d62  mov     rcx, [rcx+10h]
0x140076d66  call    WPP_SF_d
0x140076d6b  xor     eax, eax
0x140076d6d  jmp     loc_140076DF3
0x140076d72  xor     r8d, r8d; bInitialState
0x140076d75  lea     r9, aGlobalFaxsvcrp; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x140076d7c  mov     rcx, rsi; lpEventAttributes
0x140076d7f  lea     edx, [r8+1]; bManualReset
0x140076d83  call    cs:__imp_CreateEventW
0x140076d8a  nop     dword ptr [rax+rax+00h]
0x140076d8f  xor     edi, edi
0x140076d91  mov     rbx, rax
0x140076d94  test    rax, rax
0x140076d97  jnz     short loc_140076DD5
0x140076d99  call    cs:__imp_GetLastError
0x140076da0  nop     dword ptr [rax+rax+00h]
0x140076da5  mov     edi, eax
0x140076da7  mov     rcx, cs:WPP_GLOBAL_Control
0x140076dae  cmp     rcx, r14
0x140076db1  jz      short loc_140076DD5
0x140076db3  test    byte ptr [rcx+1Ch], 2
0x140076db7  jz      short loc_140076DD5
0x140076db9  cmp     byte ptr [rcx+19h], 2
0x140076dbd  jb      short loc_140076DD5
0x140076dbf  mov     rcx, [rcx+10h]
0x140076dc3  lea     edx, [rbx+14h]
0x140076dc6  mov     r9d, eax
0x140076dc9  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140076dd0  call    WPP_SF_d
0x140076dd5  mov     rcx, rsi; lpMem
0x140076dd8  call    DestroySecurityAttributes
0x140076ddd  test    rbx, rbx
0x140076de0  jnz     short loc_140076DF0
0x140076de2  mov     ecx, edi; dwErrCode
0x140076de4  call    cs:__imp_SetLastError
0x140076deb  nop     dword ptr [rax+rax+00h]
0x140076df0  mov     rax, rbx
0x140076df3  add     rsp, 28h
0x140076df7  pop     r14
0x140076df9  pop     rdi
0x140076dfa  pop     rsi
0x140076dfb  pop     rbx
0x140076dfc  retn
```
