# CRepubReadWriteBaseTask::IssueRead(ulong,ulong,uchar *,_OVERLAPPED *,ulong *)

- ea: `0x18007e3a0`
- end: `0x18007e50f`
- name: `?IssueRead@CRepubReadWriteBaseTask@@IEAAKKKPEAEPEAU_OVERLAPPED@@PEAK@Z`
- size: `367`
- prototype: `unsigned int(CRepubReadWriteBaseTask *__hidden this, unsigned int, unsigned int, unsigned __int8 *, struct _OVERLAPPED *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180082170`

## callees

- `0x180008290`
- `0x18007e3a0`
- `0x180086ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e421`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e42f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e4af`
- `KERNEL32!CloseHandle` at `0x18007e4f1`
- `KERNEL32!CloseHandle` at `0x18007e4f1`
- `KERNEL32!ReadFile` at `0x18007e4a5`
- `KERNEL32!ReadFile` at `0x18007e4a5`

## pseudocode

```c
__int64 __fastcall CRepubReadWriteBaseTask::IssueRead(
        CRepubReadWriteBaseTask *this,
        DWORD a2,
        DWORD a3,
        unsigned __int8 *a4,
        struct _OVERLAPPED *lpOverlapped,
        unsigned int *a6)
{
  HANDLE EventW; // rsi
  DWORD v11; // eax
  DWORD v12; // ebx
  DWORD LastError; // eax

  *a6 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_DDq(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      83,
      WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids,
      a2,
      a3,
      *(_QWORD *)(*((_QWORD *)this + 81) + 24LL));
  }
  EventW = CreateEventW(0, 1, 0, 0);
  if ( EventW )
  {
    lpOverlapped->Offset = a2;
    lpOverlapped->OffsetHigh = 0;
    lpOverlapped->hEvent = EventW;
    if ( ReadFile(*(HANDLE *)(*((_QWORD *)this + 81) + 56LL), a4, a3, 0, lpOverlapped)
      || (LastError = GetLastError(), v12 = LastError, LastError == 997) )
    {
      *a6 = a3;
      return 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 85, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, LastError);
      }
      CloseHandle(EventW);
    }
  }
  else
  {
    v11 = GetLastError();
    v12 = v11;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 84, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v11);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18007e3a0  push    rbx
0x18007e3a2  push    rbp
0x18007e3a3  push    rsi
0x18007e3a4  push    rdi
0x18007e3a5  push    r13
0x18007e3a7  push    r14
0x18007e3a9  push    r15
0x18007e3ab  sub     rsp, 30h
0x18007e3af  mov     r14, [rsp+68h+arg_28]
0x18007e3b7  mov     r15, r9
0x18007e3ba  mov     edi, r8d
0x18007e3bd  mov     ebx, edx
0x18007e3bf  mov     rbp, rcx
0x18007e3c2  mov     dword ptr [r14], 0
0x18007e3c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e3d0  lea     r13, WPP_GLOBAL_Control
0x18007e3d7  cmp     rcx, r13
0x18007e3da  jz      short loc_18007E415
0x18007e3dc  test    byte ptr [rcx+6Ch], 4
0x18007e3e0  jz      short loc_18007E415
0x18007e3e2  cmp     byte ptr [rcx+69h], 4
0x18007e3e6  jb      short loc_18007E415
0x18007e3e8  mov     rax, [rbp+288h]
0x18007e3ef  mov     edx, 53h ; 'S'
0x18007e3f4  mov     rcx, [rcx+60h]
0x18007e3f8  mov     r9d, ebx
0x18007e3fb  mov     rax, [rax+18h]
0x18007e3ff  mov     [rsp+68h+var_40], rax
0x18007e404  mov     dword ptr [rsp+68h+lpOverlapped], r8d
0x18007e409  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e410  call    WPP_SF_DDq
0x18007e415  xor     r9d, r9d; lpName
0x18007e418  xor     r8d, r8d; bInitialState
0x18007e41b  xor     ecx, ecx; lpEventAttributes
0x18007e41d  lea     edx, [r9+1]; bManualReset
0x18007e421  call    cs:__imp_CreateEventW
0x18007e427  mov     rsi, rax
0x18007e42a  test    rax, rax
0x18007e42d  jnz     short loc_18007E476
0x18007e42f  call    cs:__imp_GetLastError
0x18007e435  mov     ebx, eax
0x18007e437  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e43e  cmp     rcx, r13
0x18007e441  jz      loc_18007E4FE
0x18007e447  test    byte ptr [rcx+6Ch], 4
0x18007e44b  jz      loc_18007E4FE
0x18007e451  cmp     byte ptr [rcx+69h], 1
0x18007e455  jb      loc_18007E4FE
0x18007e45b  mov     rcx, [rcx+60h]
0x18007e45f  lea     edx, [rsi+54h]
0x18007e462  mov     r9d, eax
0x18007e465  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e46c  call    WPP_SF_d
0x18007e471  jmp     loc_18007E4FE
0x18007e476  mov     rax, [rsp+68h+arg_20]
0x18007e47e  xor     r9d, r9d; lpNumberOfBytesRead
0x18007e481  mov     r8d, edi; nNumberOfBytesToRead
0x18007e484  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18007e489  mov     rdx, r15; lpBuffer
0x18007e48c  mov     [rax+10h], ebx
0x18007e48f  mov     dword ptr [rax+14h], 0
0x18007e496  mov     [rax+18h], rsi
0x18007e49a  mov     rcx, [rbp+288h]
0x18007e4a1  mov     rcx, [rcx+38h]; hFile
0x18007e4a5  call    cs:__imp_ReadFile
0x18007e4ab  test    eax, eax
0x18007e4ad  jnz     short loc_18007E4F9
0x18007e4af  call    cs:__imp_GetLastError
0x18007e4b5  mov     ebx, eax
0x18007e4b7  cmp     eax, 3E5h
0x18007e4bc  jz      short loc_18007E4F9
0x18007e4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e4c5  cmp     rcx, r13
0x18007e4c8  jz      short loc_18007E4EE
0x18007e4ca  test    byte ptr [rcx+6Ch], 4
0x18007e4ce  jz      short loc_18007E4EE
0x18007e4d0  cmp     byte ptr [rcx+69h], 1
0x18007e4d4  jb      short loc_18007E4EE
0x18007e4d6  mov     rcx, [rcx+60h]
0x18007e4da  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e4e1  mov     edx, 55h ; 'U'
0x18007e4e6  mov     r9d, eax
0x18007e4e9  call    WPP_SF_d
0x18007e4ee  mov     rcx, rsi; hObject
0x18007e4f1  call    cs:__imp_CloseHandle
0x18007e4f7  jmp     short loc_18007E4FE
0x18007e4f9  mov     [r14], edi
0x18007e4fc  xor     ebx, ebx
0x18007e4fe  mov     eax, ebx
0x18007e500  add     rsp, 30h
0x18007e504  pop     r15
0x18007e506  pop     r14
0x18007e508  pop     r13
0x18007e50a  pop     rdi
0x18007e50b  pop     rsi
0x18007e50c  pop     rbp
0x18007e50d  pop     rbx
0x18007e50e  retn
```
