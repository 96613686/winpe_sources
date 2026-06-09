# s_WTSVirtualChannelRead

- ea: `0x1800173cc`
- end: `0x180017644`
- name: `s_WTSVirtualChannelRead`
- size: `632`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180016bb0`

## callees

- `0x1800019cc`
- `0x180002240`
- `0x180014b90`
- `0x1800172fc`
- `0x1800173cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800174f5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800174f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017489`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017489`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800174c2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800174a7`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800174a7`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180017505`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x180017505`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001753c`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18001753c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001746c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001746c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x18001741a`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSVirtualChannelQuery` at `0x18001741a`

## string_xrefs

- `0x180017454`: `s_WTSVirtualChannelRead`

## pseudocode

```c
__int64 __fastcall s_WTSVirtualChannelRead(void *a1, __int64 a2, void *a3, __int64 a4, LPDWORD lpNumberOfBytesRead)
{
  signed int v5; // ebx
  signed int LastError; // eax
  int v8; // edx
  int v9; // ecx
  int v10; // r9d
  void *v11; // rdi
  signed int v12; // eax
  int v13; // edx
  int v14; // ecx
  int lpOverlapped; // [rsp+20h] [rbp-81h]
  DWORD pBytesReturned; // [rsp+30h] [rbp-71h] BYREF
  DWORD v18; // [rsp+34h] [rbp-6Dh] BYREF
  int v19; // [rsp+38h] [rbp-69h] BYREF
  signed int v20; // [rsp+3Ch] [rbp-65h] BYREF
  PVOID ppBuffer; // [rsp+40h] [rbp-61h] BYREF
  __int64 v22; // [rsp+48h] [rbp-59h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+50h] [rbp-51h] BYREF
  char v24[32]; // [rsp+70h] [rbp-31h] BYREF
  __int64 *v25; // [rsp+90h] [rbp-11h]
  __int64 v26; // [rsp+98h] [rbp-9h]
  signed int *v27; // [rsp+A0h] [rbp-1h]
  __int64 v28; // [rsp+A8h] [rbp+7h]
  int *v29; // [rsp+B0h] [rbp+Fh]
  __int64 v30; // [rsp+B8h] [rbp+17h]
  DWORD *v31; // [rsp+C0h] [rbp+1Fh]
  __int64 v32; // [rsp+C8h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+57h]

  v5 = 0;
  ppBuffer = 0;
  pBytesReturned = 0;
  memset(&Overlapped, 0, sizeof(Overlapped));
  if ( WTSVirtualChannelQuery(a1, WTSVirtualFileHandle, &ppBuffer, &pBytesReturned) )
    goto LABEL_9;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  if ( v5 >= 0 )
  {
LABEL_9:
    v11 = *(void **)ppBuffer;
    WTSFreeMemory(ppBuffer);
    Overlapped.hEvent = 0;
    Overlapped.Pointer = 0;
    SetEvent(_readThreadReadyEvent);
    if ( !ReadFile(v11, a3, 0x1000u, lpNumberOfBytesRead, &Overlapped) )
    {
      if ( GetLastError() == 997 )
        goto LABEL_16;
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      if ( v5 >= 0 )
      {
LABEL_16:
        if ( WaitForSingleObject(v11, 0xFFFFFFFF) == 258 )
        {
          CancelIo(v11);
          *lpNumberOfBytesRead = 0;
          v5 = -2147023436;
          if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
            McTemplateU0sqq_EventWriteTransfer(v14, v13, (unsigned int)"s_WTSVirtualChannelRead", 142, 180);
        }
        else
        {
          GetOverlappedResult(v11, &Overlapped, lpNumberOfBytesRead, 0);
        }
      }
      else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
      {
        v10 = 136;
        goto LABEL_7;
      }
    }
  }
  else if ( (Microsoft_WindowsPhone_InputEnableBits & 1) != 0 )
  {
    v10 = 116;
LABEL_7:
    McTemplateU0sqq_EventWriteTransfer(v9, v8, (unsigned int)"s_WTSVirtualChannelRead", v10, v5);
  }
  if ( (unsigned int)dword_180082080 > 5
    && (qword_180082090 & 0x400000400000LL) != 0
    && (qword_180082098 & 0x400000400000LL) == qword_180082098 )
  {
    v18 = *lpNumberOfBytesRead;
    v19 = 4096;
    v31 = &v18;
    v20 = v5;
    v29 = &v19;
    v22 = 0x1000000;
    v27 = &v20;
    v25 = &v22;
    v32 = 4;
    v30 = 4;
    v28 = 4;
    v26 = 8;
    tlgWriteTransfer_EventWriteTransfer(&dword_180082080, &unk_180075494, 0, 0, 6, v24);
  }
  if ( v5 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\DVCTransport\\DynamicVirtualChannelTransport.cpp",
      (const char *)(unsigned int)v5,
      lpOverlapped);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800173cc  mov     [rsp-8+arg_8], rbx
0x1800173d1  mov     [rsp-8+arg_18], rsi
0x1800173d6  push    rbp
0x1800173d7  push    rdi
0x1800173d8  push    r14
0x1800173da  lea     rbp, [rsp-3Fh]
0x1800173df  sub     rsp, 0E0h
0x1800173e6  mov     rax, cs:__security_cookie
0x1800173ed  xor     rax, rsp
0x1800173f0  mov     [rbp+4Fh+var_20], rax
0x1800173f4  mov     rsi, [rbp+4Fh+lpNumberOfBytesRead]
0x1800173f8  lea     r9, [rbp+4Fh+pBytesReturned]; pBytesReturned
0x1800173fc  xor     ebx, ebx
0x1800173fe  xorps   xmm0, xmm0
0x180017401  mov     r14, r8
0x180017404  mov     [rbp+4Fh+ppBuffer], rbx
0x180017408  lea     r8, [rbp+4Fh+ppBuffer]; ppBuffer
0x18001740c  mov     [rbp+4Fh+pBytesReturned], ebx
0x18001740f  movups  xmmword ptr [rbp+4Fh+Overlapped.Internal], xmm0
0x180017413  lea     edx, [rbx+1]; WTS_VIRTUAL_CLASS
0x180017416  movups  xmmword ptr [rbp+4Fh+Overlapped.10h], xmm0
0x18001741a  call    cs:__imp_WTSVirtualChannelQuery
0x180017420  test    eax, eax
0x180017422  jnz     short loc_180017465
0x180017424  call    cs:__imp_GetLastError
0x18001742a  mov     ebx, eax
0x18001742c  test    eax, eax
0x18001742e  jle     short loc_180017439
0x180017430  movzx   ebx, ax
0x180017433  or      ebx, 80070000h
0x180017439  test    ebx, ebx
0x18001743b  jns     short loc_180017465
0x18001743d  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x180017444  jz      loc_180017542
0x18001744a  mov     r9d, 74h ; 't'
0x180017450  mov     dword ptr [rsp+0F0h+lpOverlapped], ebx
0x180017454  lea     r8, aSWtsvirtualcha_0; "s_WTSVirtualChannelRead"
0x18001745b  call    McTemplateU0sqq_EventWriteTransfer
0x180017460  jmp     loc_180017542
0x180017465  mov     rcx, [rbp+4Fh+ppBuffer]; pMemory
0x180017469  mov     rdi, [rcx]
0x18001746c  call    cs:__imp_WTSFreeMemory
0x180017472  mov     rcx, cs:?_readThreadReadyEvent@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x180017479  mov     [rbp+4Fh+Overlapped.hEvent], 0
0x180017481  mov     qword ptr [rbp+4Fh+Overlapped.10h], 0
0x180017489  call    cs:__imp_SetEvent
0x18001748f  lea     rax, [rbp+4Fh+Overlapped]
0x180017493  mov     r9, rsi; lpNumberOfBytesRead
0x180017496  mov     r8d, 1000h; nNumberOfBytesToRead
0x18001749c  mov     [rsp+0F0h+lpOverlapped], rax; lpOverlapped
0x1800174a1  mov     rdx, r14; lpBuffer
0x1800174a4  mov     rcx, rdi; hFile
0x1800174a7  call    cs:__imp_ReadFile
0x1800174ad  test    eax, eax
0x1800174af  jnz     loc_180017542
0x1800174b5  call    cs:__imp_GetLastError
0x1800174bb  cmp     eax, 3E5h
0x1800174c0  jz      short loc_1800174EF
0x1800174c2  call    cs:__imp_GetLastError
0x1800174c8  mov     ebx, eax
0x1800174ca  test    eax, eax
0x1800174cc  jle     short loc_1800174D7
0x1800174ce  movzx   ebx, ax
0x1800174d1  or      ebx, 80070000h
0x1800174d7  test    ebx, ebx
0x1800174d9  jns     short loc_1800174EF
0x1800174db  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x1800174e2  jz      short loc_180017542
0x1800174e4  mov     r9d, 88h
0x1800174ea  jmp     loc_180017450
0x1800174ef  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800174f2  mov     rcx, rdi; hHandle
0x1800174f5  call    cs:__imp_WaitForSingleObject
0x1800174fb  mov     rcx, rdi; hFile
0x1800174fe  cmp     eax, 102h
0x180017503  jnz     short loc_180017532
0x180017505  call    cs:__imp_CancelIo
0x18001750b  mov     dword ptr [rsi], 0
0x180017511  mov     ebx, 800705B4h
0x180017516  test    cs:Microsoft_WindowsPhone_InputEnableBits, 1
0x18001751d  jz      short loc_180017542
0x18001751f  mov     dword ptr [rsp+0F0h+lpOverlapped], 800705B4h
0x180017527  mov     r9d, 8Eh
0x18001752d  jmp     loc_180017454
0x180017532  xor     r9d, r9d; bWait
0x180017535  lea     rdx, [rbp+4Fh+Overlapped]; lpOverlapped
0x180017539  mov     r8, rsi; lpNumberOfBytesTransferred
0x18001753c  call    cs:__imp_GetOverlappedResult
0x180017542  mov     eax, cs:dword_180082080
0x180017548  cmp     eax, 5
0x18001754b  jbe     loc_180017602
0x180017551  mov     rcx, cs:qword_180082098
0x180017558  mov     rdx, 400000400000h
0x180017562  mov     rax, cs:qword_180082090
0x180017569  test    rdx, rax
0x18001756c  jz      loc_180017602
0x180017572  mov     rax, rcx
0x180017575  and     rax, rdx
0x180017578  cmp     rax, rcx
0x18001757b  jnz     loc_180017602
0x180017581  mov     eax, [rsi]
0x180017583  lea     rdx, unk_180075494
0x18001758a  mov     [rbp+4Fh+var_BC], eax
0x18001758d  lea     rcx, dword_180082080
0x180017594  lea     rax, [rbp+4Fh+var_BC]
0x180017598  mov     [rbp+4Fh+var_B8], 1000h
0x18001759f  mov     [rbp+4Fh+var_30], rax
0x1800175a3  xor     r9d, r9d
0x1800175a6  lea     rax, [rbp+4Fh+var_B8]
0x1800175aa  mov     [rbp+4Fh+var_B4], ebx
0x1800175ad  mov     [rbp+4Fh+var_40], rax
0x1800175b1  xor     r8d, r8d
0x1800175b4  lea     rax, [rbp+4Fh+var_B4]
0x1800175b8  mov     [rbp+4Fh+var_A8], 1000000h
0x1800175c0  mov     [rbp+4Fh+var_50], rax
0x1800175c4  lea     rax, [rbp+4Fh+var_A8]
0x1800175c8  mov     [rbp+4Fh+var_60], rax
0x1800175cc  lea     rax, [rbp+4Fh+var_80]
0x1800175d0  mov     [rsp+0F0h+var_C8], rax
0x1800175d5  mov     dword ptr [rsp+0F0h+lpOverlapped], 6; int
0x1800175dd  mov     [rbp+4Fh+var_28], 4
0x1800175e5  mov     [rbp+4Fh+var_38], 4
0x1800175ed  mov     [rbp+4Fh+var_48], 4
0x1800175f5  mov     [rbp+4Fh+var_58], 8
0x1800175fd  call    _tlgWriteTransfer_EventWriteTransfer
0x180017602  test    ebx, ebx
0x180017604  jns     short loc_18001761E
0x180017606  mov     rcx, [rbp+57h]; this
0x18001760a  lea     r8, aMincoreTextinp_6; "mincore\\textinput\\dev\\virtualization"...
0x180017611  mov     r9d, ebx; char *
0x180017614  mov     edx, 0A1h; void *
0x180017619  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001761e  mov     eax, ebx
0x180017620  mov     rcx, [rbp+4Fh+var_20]
0x180017624  xor     rcx, rsp; StackCookie
0x180017627  call    __security_check_cookie
0x18001762c  lea     r11, [rsp+0F0h+var_10]
0x180017634  mov     rbx, [r11+28h]
0x180017638  mov     rsi, [r11+38h]
0x18001763c  mov     rsp, r11
0x18001763f  pop     r14
0x180017641  pop     rdi
0x180017642  pop     rbp
0x180017643  retn
```
