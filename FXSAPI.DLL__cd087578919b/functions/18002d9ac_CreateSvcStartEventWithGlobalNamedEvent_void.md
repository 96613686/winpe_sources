# CreateSvcStartEventWithGlobalNamedEvent(void)

- ea: `0x18002d9ac`
- end: `0x18002db36`
- name: `?CreateSvcStartEventWithGlobalNamedEvent@@YAPEAXXZ`
- size: `394`
- prototype: `void *(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002e5ac`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x18002d9ac`
- `0x18002dff4`
- `0x18002ea78`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x18002d9fa`
- `KERNEL32!OpenEventW` at `0x18002d9fa`
- `KERNEL32!CreateEventW` at `0x18002dabb`
- `KERNEL32!CreateEventW` at `0x18002dabb`
- `KERNEL32!SetLastError` at `0x18002db1c`
- `KERNEL32!SetLastError` at `0x18002db1c`
- `KERNEL32!GetLastError` at `0x18002da0f`
- `KERNEL32!GetLastError` at `0x18002da38`
- `KERNEL32!GetLastError` at `0x18002da7a`
- `KERNEL32!GetLastError` at `0x18002dad1`
- `KERNEL32!GetLastError` at `0x18002da0f`
- `KERNEL32!GetLastError` at `0x18002da38`
- `KERNEL32!GetLastError` at `0x18002da7a`
- `KERNEL32!GetLastError` at `0x18002dad1`

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

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
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
                                                                           0x100000u,
                                                                           0x100000u,
                                                                           2031619);
    v4 = SecurityAttributesWithThreadAsOwner;
    if ( !SecurityAttributesWithThreadAsOwner )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
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
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
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
0x18002d9ac  push    rbx
0x18002d9ae  push    rsi
0x18002d9af  push    rdi
0x18002d9b0  push    r14
0x18002d9b2  sub     rsp, 28h
0x18002d9b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d9bd  lea     r14, WPP_GLOBAL_Control
0x18002d9c4  cmp     rcx, r14
0x18002d9c7  jz      short loc_18002D9EA
0x18002d9c9  test    byte ptr [rcx+1Ch], 2
0x18002d9cd  jz      short loc_18002D9EA
0x18002d9cf  cmp     byte ptr [rcx+19h], 5
0x18002d9d3  jb      short loc_18002D9EA
0x18002d9d5  mov     rcx, [rcx+10h]
0x18002d9d9  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002d9e0  mov     edx, 11h
0x18002d9e5  call    WPP_SF_
0x18002d9ea  mov     ebx, 100000h
0x18002d9ef  lea     r8, Name; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x18002d9f6  mov     ecx, ebx; dwDesiredAccess
0x18002d9f8  xor     edx, edx; bInheritHandle
0x18002d9fa  call    cs:__imp_OpenEventW
0x18002da01  nop     dword ptr [rax+rax+00h]
0x18002da06  test    rax, rax
0x18002da09  jnz     loc_18002DB2B
0x18002da0f  call    cs:__imp_GetLastError
0x18002da16  nop     dword ptr [rax+rax+00h]
0x18002da1b  cmp     eax, 2
0x18002da1e  jz      short loc_18002DA4B
0x18002da20  mov     rax, cs:WPP_GLOBAL_Control
0x18002da27  cmp     rax, r14
0x18002da2a  jz      short loc_18002DAA3
0x18002da2c  test    byte ptr [rax+1Ch], 2
0x18002da30  jz      short loc_18002DAA3
0x18002da32  cmp     byte ptr [rax+19h], 2
0x18002da36  jb      short loc_18002DAA3
0x18002da38  call    cs:__imp_GetLastError
0x18002da3f  nop     dword ptr [rax+rax+00h]
0x18002da44  mov     edx, 12h
0x18002da49  jmp     short loc_18002DA89
0x18002da4b  mov     r8d, 1F0003h
0x18002da51  mov     edx, ebx
0x18002da53  mov     ecx, ebx
0x18002da55  call    CreateSecurityAttributesWithThreadAsOwner
0x18002da5a  mov     rsi, rax
0x18002da5d  test    rax, rax
0x18002da60  jnz     short loc_18002DAAA
0x18002da62  mov     rax, cs:WPP_GLOBAL_Control
0x18002da69  cmp     rax, r14
0x18002da6c  jz      short loc_18002DAA3
0x18002da6e  test    byte ptr [rax+1Ch], 2
0x18002da72  jz      short loc_18002DAA3
0x18002da74  cmp     byte ptr [rax+19h], 2
0x18002da78  jb      short loc_18002DAA3
0x18002da7a  call    cs:__imp_GetLastError
0x18002da81  nop     dword ptr [rax+rax+00h]
0x18002da86  lea     edx, [rsi+13h]
0x18002da89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002da90  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002da97  mov     r9d, eax
0x18002da9a  mov     rcx, [rcx+10h]
0x18002da9e  call    WPP_SF_d
0x18002daa3  xor     eax, eax
0x18002daa5  jmp     loc_18002DB2B
0x18002daaa  xor     r8d, r8d; bInitialState
0x18002daad  lea     r9, Name; "Global\\FaxSvcRPCStarted-1ed23866-f90b-"...
0x18002dab4  mov     rcx, rsi; lpEventAttributes
0x18002dab7  lea     edx, [r8+1]; bManualReset
0x18002dabb  call    cs:__imp_CreateEventW
0x18002dac2  nop     dword ptr [rax+rax+00h]
0x18002dac7  xor     edi, edi
0x18002dac9  mov     rbx, rax
0x18002dacc  test    rax, rax
0x18002dacf  jnz     short loc_18002DB0D
0x18002dad1  call    cs:__imp_GetLastError
0x18002dad8  nop     dword ptr [rax+rax+00h]
0x18002dadd  mov     edi, eax
0x18002dadf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dae6  cmp     rcx, r14
0x18002dae9  jz      short loc_18002DB0D
0x18002daeb  test    byte ptr [rcx+1Ch], 2
0x18002daef  jz      short loc_18002DB0D
0x18002daf1  cmp     byte ptr [rcx+19h], 2
0x18002daf5  jb      short loc_18002DB0D
0x18002daf7  mov     rcx, [rcx+10h]
0x18002dafb  lea     edx, [rbx+14h]
0x18002dafe  mov     r9d, eax
0x18002db01  lea     r8, WPP_db036311db36307996a98c23702218b2_Traceguids
0x18002db08  call    WPP_SF_d
0x18002db0d  mov     rcx, rsi; lpMem
0x18002db10  call    DestroySecurityAttributes
0x18002db15  test    rbx, rbx
0x18002db18  jnz     short loc_18002DB28
0x18002db1a  mov     ecx, edi; dwErrCode
0x18002db1c  call    cs:__imp_SetLastError
0x18002db23  nop     dword ptr [rax+rax+00h]
0x18002db28  mov     rax, rbx
0x18002db2b  add     rsp, 28h
0x18002db2f  pop     r14
0x18002db31  pop     rdi
0x18002db32  pop     rsi
0x18002db33  pop     rbx
0x18002db34  retn
```
