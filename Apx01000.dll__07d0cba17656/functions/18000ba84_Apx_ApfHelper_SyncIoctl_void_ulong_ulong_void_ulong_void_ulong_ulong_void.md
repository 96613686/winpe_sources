# Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)

- ea: `0x18000ba84`
- end: `0x18000bd8d`
- name: `?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z`
- size: `777`
- prototype: `__int64 __fastcall(void *, unsigned int, DWORD, void *, DWORD nInBufferSize, void *lpOutBuffer, DWORD nOutBufferSize, LPDWORD lpNumberOfBytesTransferred, void *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ba84`
- `0x180025b00`
- `0x180026c98`
- `0x180027990`
- `0x1800281bc`
- `0x180028850`
- `0x180028d90`

## callees

- `0x18000a12c`
- `0x18000ba84`
- `0x18000bec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bb17`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000bb17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000bd33`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bb79`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18000bb79`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000bc12`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x18000bc12`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000bc31`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18000bc31`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bbcc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000bbcc`

## pseudocode

```c
__int64 __fastcall Apx::ApfHelper::SyncIoctl(
        void *a1,
        unsigned int a2,
        DWORD a3,
        void *a4,
        DWORD nInBufferSize,
        void *lpOutBuffer,
        DWORD nOutBufferSize,
        LPDWORD lpNumberOfBytesTransferred,
        void *a9)
{
  LPDWORD lpBytesReturned; // rsi
  unsigned __int64 EventW; // rax
  signed int v14; // eax
  signed int v15; // ebx
  signed int LastError; // eax
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  signed int v20; // eax
  DWORD v22; // [rsp+58h] [rbp-31h] BYREF
  int v23; // [rsp+5Ch] [rbp-2Dh] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-29h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+70h] [rbp-19h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
  }
  lpBytesReturned = (LPDWORD)&v23;
  v23 = 0;
  v22 = 0;
  *(_OWORD *)&Overlapped.Internal = 0;
  if ( lpNumberOfBytesTransferred )
    lpBytesReturned = lpNumberOfBytesTransferred;
  *(_OWORD *)&Overlapped.Offset = 0;
  EventW = (unsigned __int64)CreateEventW(0, 1, 0, 0);
  Overlapped.hEvent = (HANDLE)EventW;
  if ( EventW )
  {
    Overlapped.hEvent = (HANDLE)(EventW | 1);
    if ( DeviceIoControl(a1, a3, a4, nInBufferSize, lpOutBuffer, nOutBufferSize, lpBytesReturned, &Overlapped) )
    {
      if ( Overlapped.Internal )
      {
        switch ( Overlapped.Internal )
        {
          case 0x102uLL:
            v15 = -2147023436;
            break;
          case 0x105uLL:
            v15 = -2147024662;
            break;
          case 0xFFFFFFFFC00000BBuLL:
            v15 = -2147024846;
            break;
          case 0xFFFFFFFFC00000D0uLL:
            v15 = -2147024825;
            break;
          case 0xFFFFFFFFC0000240uLL:
            v15 = -2147023661;
            break;
          default:
            goto LABEL_46;
        }
LABEL_45:
        *lpBytesReturned = 0;
        goto LABEL_47;
      }
    }
    else
    {
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      if ( v15 == -2147023899 )
      {
        if ( a9 )
        {
          Handles[1] = a9;
          Handles[0] = Overlapped.hEvent;
          v17 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
          if ( v17 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && *((char *)WPP_GLOBAL_Control + 28) < 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_dqD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, v19, v17, a1, a3);
            }
            CancelIoEx(a1, &Overlapped);
          }
        }
        if ( GetOverlappedResult(a1, &Overlapped, lpBytesReturned, 1) )
        {
          v15 = 0;
          goto LABEL_47;
        }
        v20 = GetLastError();
        v15 = v20;
        if ( v20 > 0 )
          v15 = (unsigned __int16)v20 | 0x80070000;
LABEL_32:
        if ( v15 >= 0 )
          goto LABEL_47;
        goto LABEL_45;
      }
      if ( v15 != -2147024774 && v15 != -2147024662 || a3 != 3080195 || nOutBufferSize )
        goto LABEL_32;
      if ( !*lpBytesReturned )
      {
        if ( (int)Apx::ApfHelper::SyncIoctl(a1, a2, 0x2F0003u, a4, nInBufferSize, &v22, 4u, lpBytesReturned, a9) >= 0 )
        {
          v15 = 0;
          *lpBytesReturned = v22;
        }
        goto LABEL_32;
      }
    }
LABEL_46:
    v15 = 0;
    goto LABEL_47;
  }
  v14 = GetLastError();
  v15 = v14;
  if ( v14 > 0 )
    v15 = (unsigned __int16)v14 | 0x80070000;
LABEL_47:
  if ( Overlapped.hEvent )
  {
    CloseHandle(Overlapped.hEvent);
    Overlapped.hEvent = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18000ba84  mov     rax, rsp
0x18000ba87  mov     [rax+8], rbx
0x18000ba8b  mov     [rax+18h], rsi
0x18000ba8f  mov     [rax+10h], edx
0x18000ba92  push    rbp
0x18000ba93  push    r12
0x18000ba95  push    r13
0x18000ba97  push    r14
0x18000ba99  push    r15
0x18000ba9b  lea     rbp, [rax-37h]
0x18000ba9f  sub     rsp, 90h
0x18000baa6  mov     r13, r9
0x18000baa9  mov     r15d, r8d
0x18000baac  mov     r14, rcx
0x18000baaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bab6  lea     r12, WPP_GLOBAL_Control
0x18000babd  cmp     rcx, r12
0x18000bac0  jz      short loc_18000BAE3
0x18000bac2  test    byte ptr [rcx+1Ch], 1
0x18000bac6  jz      short loc_18000BAE3
0x18000bac8  cmp     byte ptr [rcx+19h], 5
0x18000bacc  jb      short loc_18000BAE3
0x18000bace  mov     rcx, [rcx+10h]
0x18000bad2  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x18000bad9  mov     edx, 21h ; '!'
0x18000bade  call    WPP_SF_
0x18000bae3  mov     rax, [rbp+2Fh+lpNumberOfBytesTransferred]
0x18000bae7  lea     rsi, [rbp+2Fh+var_5C]
0x18000baeb  xorps   xmm0, xmm0
0x18000baee  mov     [rbp+2Fh+var_5C], 0
0x18000baf5  test    rax, rax
0x18000baf8  mov     [rbp+2Fh+var_60], 0
0x18000baff  movups  xmmword ptr [rbp+2Fh+Overlapped.Internal], xmm0
0x18000bb03  cmovnz  rsi, rax
0x18000bb07  xor     r9d, r9d; lpName
0x18000bb0a  xor     r8d, r8d; bInitialState
0x18000bb0d  xor     ecx, ecx; lpEventAttributes
0x18000bb0f  movups  xmmword ptr [rbp+2Fh+Overlapped.10h], xmm0
0x18000bb13  lea     edx, [r9+1]; bManualReset
0x18000bb17  call    cs:__imp_CreateEventW
0x18000bb1d  mov     [rbp+2Fh+Overlapped.hEvent], rax
0x18000bb21  test    rax, rax
0x18000bb24  jnz     short loc_18000BB44
0x18000bb26  call    cs:__imp_GetLastError
0x18000bb2c  mov     ebx, eax
0x18000bb2e  test    eax, eax
0x18000bb30  jle     loc_18000BD2A
0x18000bb36  movzx   ebx, ax
0x18000bb39  or      ebx, 80070000h
0x18000bb3f  jmp     loc_18000BD2A
0x18000bb44  mov     r12d, [rbp+2Fh+arg_30]
0x18000bb48  or      rax, 1
0x18000bb4c  mov     r9d, [rbp+2Fh+nInBufferSize]; nInBufferSize
0x18000bb50  mov     r8, r13; lpInBuffer
0x18000bb53  mov     [rbp+2Fh+Overlapped.hEvent], rax
0x18000bb57  mov     edx, r15d; dwIoControlCode
0x18000bb5a  lea     rax, [rbp+2Fh+Overlapped]
0x18000bb5e  mov     rcx, r14; hDevice
0x18000bb61  mov     [rsp+0B0h+lpOverlapped], rax; lpOverlapped
0x18000bb66  mov     rax, [rbp+2Fh+arg_28]
0x18000bb6a  mov     [rsp+0B0h+lpBytesReturned], rsi; lpBytesReturned
0x18000bb6f  mov     [rsp+0B0h+nOutBufferSize], r12d; nOutBufferSize
0x18000bb74  mov     [rsp+0B0h+lpOutBuffer], rax; lpOutBuffer
0x18000bb79  call    cs:__imp_DeviceIoControl
0x18000bb7f  test    eax, eax
0x18000bb81  jnz     loc_18000BCC7
0x18000bb87  call    cs:__imp_GetLastError
0x18000bb8d  mov     ebx, eax
0x18000bb8f  test    eax, eax
0x18000bb91  jle     short loc_18000BB9C
0x18000bb93  movzx   ebx, ax
0x18000bb96  or      ebx, 80070000h
0x18000bb9c  cmp     ebx, 800703E5h
0x18000bba2  jnz     loc_18000BC59
0x18000bba8  mov     rcx, [rbp+2Fh+arg_40]
0x18000bbac  test    rcx, rcx
0x18000bbaf  jz      short loc_18000BC1A
0x18000bbb1  mov     rax, [rbp+2Fh+Overlapped.hEvent]
0x18000bbb5  lea     rdx, [rbp+2Fh+Handles]; lpHandles
0x18000bbb9  xor     r8d, r8d; bWaitAll
0x18000bbbc  mov     [rbp+2Fh+var_50], rcx
0x18000bbc0  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000bbc4  mov     [rbp+2Fh+Handles], rax
0x18000bbc8  lea     ecx, [r8+2]; nCount
0x18000bbcc  call    cs:__imp_WaitForMultipleObjects
0x18000bbd2  test    eax, eax
0x18000bbd4  jz      short loc_18000BC1A
0x18000bbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bbdd  lea     r12, WPP_GLOBAL_Control
0x18000bbe4  cmp     rcx, r12
0x18000bbe7  jz      short loc_18000BC0B
0x18000bbe9  test    byte ptr [rcx+1Ch], 80h
0x18000bbed  jz      short loc_18000BC0B
0x18000bbef  cmp     byte ptr [rcx+19h], 3
0x18000bbf3  jb      short loc_18000BC0B
0x18000bbf5  mov     rcx, [rcx+10h]
0x18000bbf9  mov     r9d, eax
0x18000bbfc  mov     [rsp+0B0h+nOutBufferSize], r15d
0x18000bc01  mov     [rsp+0B0h+lpOutBuffer], r14
0x18000bc06  call    WPP_SF_dqD
0x18000bc0b  lea     rdx, [rbp+2Fh+Overlapped]; lpOverlapped
0x18000bc0f  mov     rcx, r14; hFile
0x18000bc12  call    cs:__imp_CancelIoEx
0x18000bc18  jmp     short loc_18000BC21
0x18000bc1a  lea     r12, WPP_GLOBAL_Control
0x18000bc21  mov     r9d, 1; bWait
0x18000bc27  lea     rdx, [rbp+2Fh+Overlapped]; lpOverlapped
0x18000bc2b  mov     r8, rsi; lpNumberOfBytesTransferred
0x18000bc2e  mov     rcx, r14; hFile
0x18000bc31  call    cs:__imp_GetOverlappedResult
0x18000bc37  test    eax, eax
0x18000bc39  jz      short loc_18000BC42
0x18000bc3b  xor     ebx, ebx
0x18000bc3d  jmp     loc_18000BD2A
0x18000bc42  call    cs:__imp_GetLastError
0x18000bc48  mov     ebx, eax
0x18000bc4a  test    eax, eax
0x18000bc4c  jle     short loc_18000BCC1
0x18000bc4e  movzx   ebx, ax
0x18000bc51  or      ebx, 80070000h
0x18000bc57  jmp     short loc_18000BCC1
0x18000bc59  cmp     ebx, 8007007Ah
0x18000bc5f  jz      short loc_18000BC69
0x18000bc61  cmp     ebx, 800700EAh
0x18000bc67  jnz     short loc_18000BCC1
0x18000bc69  mov     r8d, 2F0003h; unsigned int
0x18000bc6f  cmp     r15d, r8d
0x18000bc72  jnz     short loc_18000BCC1
0x18000bc74  test    r12d, r12d
0x18000bc77  jnz     short loc_18000BCC1
0x18000bc79  cmp     [rsi], r12d
0x18000bc7c  ja      loc_18000BD21
0x18000bc82  mov     rax, [rbp+2Fh+arg_40]
0x18000bc86  mov     r9, r13; void *
0x18000bc89  mov     edx, [rbp+2Fh+arg_8]; unsigned int
0x18000bc8c  mov     rcx, r14; void *
0x18000bc8f  mov     [rsp+0B0h+var_70], rax; void *
0x18000bc94  lea     rax, [rbp+2Fh+var_60]
0x18000bc98  mov     [rsp+0B0h+lpOverlapped], rsi; lpNumberOfBytesTransferred
0x18000bc9d  mov     dword ptr [rsp+0B0h+lpBytesReturned], 4; DWORD
0x18000bca5  mov     qword ptr [rsp+0B0h+nOutBufferSize], rax; void *
0x18000bcaa  mov     eax, [rbp+2Fh+nInBufferSize]
0x18000bcad  mov     dword ptr [rsp+0B0h+lpOutBuffer], eax; nInBufferSize
0x18000bcb1  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x18000bcb6  test    eax, eax
0x18000bcb8  js      short loc_18000BCC1
0x18000bcba  mov     eax, [rbp+2Fh+var_60]
0x18000bcbd  xor     ebx, ebx
0x18000bcbf  mov     [rsi], eax
0x18000bcc1  test    ebx, ebx
0x18000bcc3  jns     short loc_18000BD23
0x18000bcc5  jmp     short loc_18000BD19
0x18000bcc7  mov     rax, [rbp+2Fh+Overlapped.Internal]
0x18000bccb  test    rax, rax
0x18000bcce  jz      short loc_18000BD21
0x18000bcd0  cmp     rax, 102h
0x18000bcd6  jz      short loc_18000BD14
0x18000bcd8  cmp     rax, 105h
0x18000bcde  jz      short loc_18000BD0D
0x18000bce0  cmp     rax, 0FFFFFFFFC00000BBh
0x18000bce6  jz      short loc_18000BD06
0x18000bce8  cmp     rax, 0FFFFFFFFC00000D0h
0x18000bcee  jz      short loc_18000BCFF
0x18000bcf0  cmp     rax, 0FFFFFFFFC0000240h
0x18000bcf6  jnz     short loc_18000BD21
0x18000bcf8  mov     ebx, 800704D3h
0x18000bcfd  jmp     short loc_18000BD19
0x18000bcff  mov     ebx, 80070047h
0x18000bd04  jmp     short loc_18000BD19
0x18000bd06  mov     ebx, 80070032h
0x18000bd0b  jmp     short loc_18000BD19
0x18000bd0d  mov     ebx, 800700EAh
0x18000bd12  jmp     short loc_18000BD19
0x18000bd14  mov     ebx, 800705B4h
0x18000bd19  mov     dword ptr [rsi], 0
0x18000bd1f  jmp     short loc_18000BD23
0x18000bd21  xor     ebx, ebx
0x18000bd23  lea     r12, WPP_GLOBAL_Control
0x18000bd2a  mov     rcx, [rbp+2Fh+Overlapped.hEvent]; hObject
0x18000bd2e  test    rcx, rcx
0x18000bd31  jz      short loc_18000BD41
0x18000bd33  call    cs:__imp_CloseHandle
0x18000bd39  mov     [rbp+2Fh+Overlapped.hEvent], 0
0x18000bd41  mov     rcx, cs:WPP_GLOBAL_Control
0x18000bd48  cmp     rcx, r12
0x18000bd4b  jz      short loc_18000BD6E
0x18000bd4d  test    byte ptr [rcx+1Ch], 1
0x18000bd51  jz      short loc_18000BD6E
0x18000bd53  cmp     byte ptr [rcx+19h], 5
0x18000bd57  jb      short loc_18000BD6E
0x18000bd59  mov     rcx, [rcx+10h]
0x18000bd5d  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x18000bd64  mov     edx, 23h ; '#'
0x18000bd69  call    WPP_SF_
0x18000bd6e  lea     r11, [rsp+0B0h+var_20]
0x18000bd76  mov     eax, ebx
0x18000bd78  mov     rbx, [r11+30h]
0x18000bd7c  mov     rsi, [r11+40h]
0x18000bd80  mov     rsp, r11
0x18000bd83  pop     r15
0x18000bd85  pop     r14
0x18000bd87  pop     r13
0x18000bd89  pop     r12
0x18000bd8b  pop     rbp
0x18000bd8c  retn
```
