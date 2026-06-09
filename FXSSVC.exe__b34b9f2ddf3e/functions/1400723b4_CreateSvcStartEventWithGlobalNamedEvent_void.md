# CreateSvcStartEventWithGlobalNamedEvent(void)

- ea: `0x1400723b4`
- end: `0x140072510`
- name: `?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ`
- size: `348`
- prototype: `HANDLE(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140072e44`

## callees

- `0x140004b30`
- `0x140004b58`
- `0x1400723b4`
- `0x140072970`
- `0x1400732cc`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x140072402`
- `KERNEL32!OpenEventW` at `0x140072402`
- `KERNEL32!GetLastError` at `0x140072411`
- `KERNEL32!GetLastError` at `0x140072434`
- `KERNEL32!GetLastError` at `0x140072470`
- `KERNEL32!GetLastError` at `0x1400724b8`
- `KERNEL32!GetLastError` at `0x140072411`
- `KERNEL32!GetLastError` at `0x140072434`
- `KERNEL32!GetLastError` at `0x140072470`
- `KERNEL32!GetLastError` at `0x1400724b8`
- `KERNEL32!SetLastError` at `0x1400724fd`
- `KERNEL32!SetLastError` at `0x1400724fd`
- `KERNEL32!CreateEventW` at `0x1400724a8`
- `KERNEL32!CreateEventW` at `0x1400724a8`

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
    SecurityAttributesWithThreadAsOwner = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner(
                                                                           0x100000,
                                                                           0x100000,
                                                                           2031619);
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
0x1400723b4  push    rbx
0x1400723b6  push    rsi
0x1400723b7  push    rdi
0x1400723b8  push    r14
0x1400723ba  sub     rsp, 28h
0x1400723be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400723c5  lea     r14, WPP_GLOBAL_Control
0x1400723cc  cmp     rcx, r14
0x1400723cf  jz      short loc_1400723F2
0x1400723d1  test    byte ptr [rcx+1Ch], 2
0x1400723d5  jz      short loc_1400723F2
0x1400723d7  cmp     byte ptr [rcx+19h], 5
0x1400723db  jb      short loc_1400723F2
0x1400723dd  mov     rcx, [rcx+10h]
0x1400723e1  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400723e8  mov     edx, 11h
0x1400723ed  call    WPP_SF_
0x1400723f2  mov     ebx, 100000h
0x1400723f7  lea     r8, aGlobalFaxsvcrp; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x1400723fe  mov     ecx, ebx; dwDesiredAccess
0x140072400  xor     edx, edx; bInheritHandle
0x140072402  call    cs:__imp_OpenEventW
0x140072408  test    rax, rax
0x14007240b  jnz     loc_140072506
0x140072411  call    cs:__imp_GetLastError
0x140072417  cmp     eax, 2
0x14007241a  jz      short loc_140072441
0x14007241c  mov     rax, cs:WPP_GLOBAL_Control
0x140072423  cmp     rax, r14
0x140072426  jz      short loc_140072493
0x140072428  test    byte ptr [rax+1Ch], 2
0x14007242c  jz      short loc_140072493
0x14007242e  cmp     byte ptr [rax+19h], 2
0x140072432  jb      short loc_140072493
0x140072434  call    cs:__imp_GetLastError
0x14007243a  mov     edx, 12h
0x14007243f  jmp     short loc_140072479
0x140072441  mov     r8d, 1F0003h
0x140072447  mov     edx, ebx
0x140072449  mov     ecx, ebx
0x14007244b  call    CreateSecurityAttributesWithThreadAsOwner
0x140072450  mov     rsi, rax
0x140072453  test    rax, rax
0x140072456  jnz     short loc_140072497
0x140072458  mov     rax, cs:WPP_GLOBAL_Control
0x14007245f  cmp     rax, r14
0x140072462  jz      short loc_140072493
0x140072464  test    byte ptr [rax+1Ch], 2
0x140072468  jz      short loc_140072493
0x14007246a  cmp     byte ptr [rax+19h], 2
0x14007246e  jb      short loc_140072493
0x140072470  call    cs:__imp_GetLastError
0x140072476  lea     edx, [rsi+13h]
0x140072479  mov     rcx, cs:WPP_GLOBAL_Control
0x140072480  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x140072487  mov     r9d, eax
0x14007248a  mov     rcx, [rcx+10h]
0x14007248e  call    WPP_SF_d
0x140072493  xor     eax, eax
0x140072495  jmp     short loc_140072506
0x140072497  xor     r8d, r8d; bInitialState
0x14007249a  lea     r9, aGlobalFaxsvcrp; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x1400724a1  mov     rcx, rsi; lpEventAttributes
0x1400724a4  lea     edx, [r8+1]; bManualReset
0x1400724a8  call    cs:__imp_CreateEventW
0x1400724ae  xor     edi, edi
0x1400724b0  mov     rbx, rax
0x1400724b3  test    rax, rax
0x1400724b6  jnz     short loc_1400724EE
0x1400724b8  call    cs:__imp_GetLastError
0x1400724be  mov     edi, eax
0x1400724c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400724c7  cmp     rcx, r14
0x1400724ca  jz      short loc_1400724EE
0x1400724cc  test    byte ptr [rcx+1Ch], 2
0x1400724d0  jz      short loc_1400724EE
0x1400724d2  cmp     byte ptr [rcx+19h], 2
0x1400724d6  jb      short loc_1400724EE
0x1400724d8  mov     rcx, [rcx+10h]
0x1400724dc  lea     edx, [rbx+14h]
0x1400724df  mov     r9d, eax
0x1400724e2  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x1400724e9  call    WPP_SF_d
0x1400724ee  mov     rcx, rsi; lpMem
0x1400724f1  call    DestroySecurityAttributes
0x1400724f6  test    rbx, rbx
0x1400724f9  jnz     short loc_140072503
0x1400724fb  mov     ecx, edi; dwErrCode
0x1400724fd  call    cs:__imp_SetLastError
0x140072503  mov     rax, rbx
0x140072506  add     rsp, 28h
0x14007250a  pop     r14
0x14007250c  pop     rdi
0x14007250d  pop     rsi
0x14007250e  pop     rbx
0x14007250f  retn
```
