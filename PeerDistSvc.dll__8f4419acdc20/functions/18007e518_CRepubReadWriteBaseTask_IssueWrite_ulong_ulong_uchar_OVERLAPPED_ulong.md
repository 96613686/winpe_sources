# CRepubReadWriteBaseTask::IssueWrite(ulong,ulong,uchar *,_OVERLAPPED *,ulong *)

- ea: `0x18007e518`
- end: `0x18007e687`
- name: `?IssueWrite@CRepubReadWriteBaseTask@@IEAAKKKPEAEPEAU_OVERLAPPED@@PEAK@Z`
- size: `367`
- prototype: `unsigned int(CRepubReadWriteBaseTask *__hidden this, unsigned int, unsigned int, unsigned __int8 *, struct _OVERLAPPED *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180085870`

## callees

- `0x180008290`
- `0x18007e518`
- `0x180086ea4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e599`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18007e599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e5a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007e627`
- `KERNEL32!CloseHandle` at `0x18007e669`
- `KERNEL32!CloseHandle` at `0x18007e669`
- `KERNEL32!WriteFile` at `0x18007e61d`
- `KERNEL32!WriteFile` at `0x18007e61d`

## pseudocode

```c
__int64 __fastcall CRepubReadWriteBaseTask::IssueWrite(
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
      80,
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
    if ( WriteFile(*(HANDLE *)(*((_QWORD *)this + 81) + 40LL), a4, a3, 0, lpOverlapped)
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 82, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, LastError);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 81, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids, v11);
    }
  }
  return v12;
}

```

## disassembly

```asm
0x18007e518  push    rbx
0x18007e51a  push    rbp
0x18007e51b  push    rsi
0x18007e51c  push    rdi
0x18007e51d  push    r13
0x18007e51f  push    r14
0x18007e521  push    r15
0x18007e523  sub     rsp, 30h
0x18007e527  mov     r14, [rsp+68h+arg_28]
0x18007e52f  mov     r15, r9
0x18007e532  mov     edi, r8d
0x18007e535  mov     ebx, edx
0x18007e537  mov     rbp, rcx
0x18007e53a  mov     dword ptr [r14], 0
0x18007e541  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e548  lea     r13, WPP_GLOBAL_Control
0x18007e54f  cmp     rcx, r13
0x18007e552  jz      short loc_18007E58D
0x18007e554  test    byte ptr [rcx+6Ch], 4
0x18007e558  jz      short loc_18007E58D
0x18007e55a  cmp     byte ptr [rcx+69h], 4
0x18007e55e  jb      short loc_18007E58D
0x18007e560  mov     rax, [rbp+288h]
0x18007e567  mov     edx, 50h ; 'P'
0x18007e56c  mov     rcx, [rcx+60h]
0x18007e570  mov     r9d, ebx
0x18007e573  mov     rax, [rax+18h]
0x18007e577  mov     [rsp+68h+var_40], rax
0x18007e57c  mov     dword ptr [rsp+68h+lpOverlapped], r8d
0x18007e581  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e588  call    WPP_SF_DDq
0x18007e58d  xor     r9d, r9d; lpName
0x18007e590  xor     r8d, r8d; bInitialState
0x18007e593  xor     ecx, ecx; lpEventAttributes
0x18007e595  lea     edx, [r9+1]; bManualReset
0x18007e599  call    cs:__imp_CreateEventW
0x18007e59f  mov     rsi, rax
0x18007e5a2  test    rax, rax
0x18007e5a5  jnz     short loc_18007E5EE
0x18007e5a7  call    cs:__imp_GetLastError
0x18007e5ad  mov     ebx, eax
0x18007e5af  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e5b6  cmp     rcx, r13
0x18007e5b9  jz      loc_18007E676
0x18007e5bf  test    byte ptr [rcx+6Ch], 4
0x18007e5c3  jz      loc_18007E676
0x18007e5c9  cmp     byte ptr [rcx+69h], 1
0x18007e5cd  jb      loc_18007E676
0x18007e5d3  mov     rcx, [rcx+60h]
0x18007e5d7  lea     edx, [rsi+51h]
0x18007e5da  mov     r9d, eax
0x18007e5dd  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e5e4  call    WPP_SF_d
0x18007e5e9  jmp     loc_18007E676
0x18007e5ee  mov     rax, [rsp+68h+arg_20]
0x18007e5f6  xor     r9d, r9d; lpNumberOfBytesWritten
0x18007e5f9  mov     r8d, edi; nNumberOfBytesToWrite
0x18007e5fc  mov     [rsp+68h+lpOverlapped], rax; lpOverlapped
0x18007e601  mov     rdx, r15; lpBuffer
0x18007e604  mov     [rax+10h], ebx
0x18007e607  mov     dword ptr [rax+14h], 0
0x18007e60e  mov     [rax+18h], rsi
0x18007e612  mov     rcx, [rbp+288h]
0x18007e619  mov     rcx, [rcx+28h]; hFile
0x18007e61d  call    cs:__imp_WriteFile
0x18007e623  test    eax, eax
0x18007e625  jnz     short loc_18007E671
0x18007e627  call    cs:__imp_GetLastError
0x18007e62d  mov     ebx, eax
0x18007e62f  cmp     eax, 3E5h
0x18007e634  jz      short loc_18007E671
0x18007e636  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e63d  cmp     rcx, r13
0x18007e640  jz      short loc_18007E666
0x18007e642  test    byte ptr [rcx+6Ch], 4
0x18007e646  jz      short loc_18007E666
0x18007e648  cmp     byte ptr [rcx+69h], 1
0x18007e64c  jb      short loc_18007E666
0x18007e64e  mov     rcx, [rcx+60h]
0x18007e652  lea     r8, WPP_3b231073c17c3a7554274eb2955bc7c1_Traceguids
0x18007e659  mov     edx, 52h ; 'R'
0x18007e65e  mov     r9d, eax
0x18007e661  call    WPP_SF_d
0x18007e666  mov     rcx, rsi; hObject
0x18007e669  call    cs:__imp_CloseHandle
0x18007e66f  jmp     short loc_18007E676
0x18007e671  mov     [r14], edi
0x18007e674  xor     ebx, ebx
0x18007e676  mov     eax, ebx
0x18007e678  add     rsp, 30h
0x18007e67c  pop     r15
0x18007e67e  pop     r14
0x18007e680  pop     r13
0x18007e682  pop     rdi
0x18007e683  pop     rsi
0x18007e684  pop     rbp
0x18007e685  pop     rbx
0x18007e686  retn
```
