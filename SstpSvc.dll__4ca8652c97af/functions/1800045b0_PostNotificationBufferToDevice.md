# PostNotificationBufferToDevice

- ea: `0x1800045b0`
- end: `0x18000481b`
- name: `PostNotificationBufferToDevice`
- size: `619`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180003920`
- `0x18000a0d4`

## callees

- `0x180002d70`
- `0x1800045b0`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`
- `0x18001bd80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046c9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800046bf`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800046bf`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800046ea`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x1800046ea`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004681`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004681`

## pseudocode

```c
__int64 __fastcall PostNotificationBufferToDevice(__int64 a1)
{
  DWORD LastError; // eax
  DWORD v3; // ebx
  int v5; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v6[2044]; // [rsp+54h] [rbp-ACh] BYREF
  int v7; // [rsp+850h] [rbp+750h] BYREF
  _BYTE v8[2044]; // [rsp+854h] [rbp+754h] BYREF

  v7 = 0;
  memset_0(v8, 0, sizeof(v8));
  *(_OWORD *)a1 = 0;
  *(_OWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_DWORD *)(a1 + 32) = 17769;
  v5 = 0;
  memset_0(v6, 0, sizeof(v6));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString((wchar_t *)&v5, L"Entering %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
  StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
  if ( DeviceIoControl(
         *((HANDLE *)SstpSvcGlobals + 35),
         0x128038u,
         0,
         0,
         (LPVOID)(a1 + 40),
         0x2010u,
         0,
         (LPOVERLAPPED)a1)
    || (LastError = GetLastError(), v3 = LastError, LastError == 997)
    || !LastError )
  {
    v3 = 0;
  }
  else
  {
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v5) = 0;
      FormatRRASErrorString((wchar_t *)&v5, L"AsyncSstpDeviceIoControl fails with [%d]", v3);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v5);
    }
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v5) = 0;
    FormatRRASErrorString((wchar_t *)&v5, L"LEaving %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(
        (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceInfo,
        (const wchar_t *)&v5);
  }
  if ( v3 )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v7) = 0;
      FormatRRASErrorString((wchar_t *)&v7, L"Failure to queue mini-send buffers - %d", v3);
      if ( (byte_18002D803 & 8) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(
          (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
          (const wchar_t *)&v7);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(
            (REGHANDLE *)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (const EVENT_DESCRIPTOR *)RasSSTPSvcTraceError,
            L"Freeing up the buffer");
      }
    }
    FreeBufferToPool((__int64)SstpSvcGlobals + 312, a1, 1);
  }
  return v3;
}

```

## disassembly

```asm
0x1800045b0  push    rbp
0x1800045b2  push    rbx
0x1800045b3  push    rdi
0x1800045b4  push    r14
0x1800045b6  lea     rbp, [rsp-0F68h]
0x1800045be  mov     eax, 1068h
0x1800045c3  call    _alloca_probe
0x1800045c8  sub     rsp, rax
0x1800045cb  mov     rax, cs:__security_cookie
0x1800045d2  xor     rax, rsp
0x1800045d5  mov     [rbp+0F80h+var_30], rax
0x1800045dc  mov     rdi, rcx
0x1800045df  xor     eax, eax
0x1800045e1  mov     ebx, 7FCh
0x1800045e6  mov     [rbp+0F80h+var_830], eax
0x1800045ec  mov     r8d, ebx; Size
0x1800045ef  lea     rcx, [rbp+0F80h+var_82C]; void *
0x1800045f6  xor     edx, edx; Val
0x1800045f8  call    memset_0
0x1800045fd  xorps   xmm0, xmm0
0x180004600  lea     rcx, [rsp+1080h+var_102C]; void *
0x180004605  movups  xmmword ptr [rdi], xmm0
0x180004608  xor     eax, eax
0x18000460a  mov     r8d, ebx; Size
0x18000460d  movups  xmmword ptr [rdi+10h], xmm0
0x180004611  mov     [rdi+20h], rax
0x180004615  xor     edx, edx; Val
0x180004617  mov     dword ptr [rdi+20h], 4569h
0x18000461e  mov     [rsp+1080h+var_1030], eax
0x180004622  call    memset_0
0x180004627  test    cs:byte_18002D803, 10h
0x18000462e  lea     r14, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004635  jz      short loc_180004673
0x180004637  xor     eax, eax
0x180004639  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180004640  lea     rdx, aEnteringWs; "Entering %ws"
0x180004647  mov     word ptr [rsp+1080h+var_1030], ax
0x18000464c  lea     rcx, [rsp+1080h+var_1030]
0x180004651  call    FormatRRASErrorString
0x180004656  test    cs:byte_18002D803, 10h
0x18000465d  jz      short loc_180004673
0x18000465f  lea     r8, [rsp+1080h+var_1030]
0x180004664  mov     rcx, r14
0x180004667  lea     rdx, RasSSTPSvcTraceInfo
0x18000466e  call    McTemplateU0z_EventWriteTransfer
0x180004673  mov     rcx, cs:SstpSvcGlobals
0x18000467a  mov     rcx, [rcx+120h]; pio
0x180004681  call    cs:__imp_StartThreadpoolIo
0x180004687  mov     rcx, cs:SstpSvcGlobals
0x18000468e  lea     rax, [rdi+28h]
0x180004692  mov     [rsp+1080h+lpOverlapped], rdi; lpOverlapped
0x180004697  xor     r9d, r9d; nInBufferSize
0x18000469a  mov     [rsp+1080h+lpBytesReturned], 0; lpBytesReturned
0x1800046a3  xor     r8d, r8d; lpInBuffer
0x1800046a6  mov     [rsp+1080h+nOutBufferSize], 2010h; nOutBufferSize
0x1800046ae  mov     edx, 128038h; dwIoControlCode
0x1800046b3  mov     rcx, [rcx+118h]; hDevice
0x1800046ba  mov     [rsp+1080h+lpOutBuffer], rax; lpOutBuffer
0x1800046bf  call    cs:__imp_DeviceIoControl
0x1800046c5  test    eax, eax
0x1800046c7  jnz     short loc_180004733
0x1800046c9  call    cs:__imp_GetLastError
0x1800046cf  mov     ebx, eax
0x1800046d1  cmp     eax, 3E5h
0x1800046d6  jz      short loc_180004733
0x1800046d8  test    eax, eax
0x1800046da  jz      short loc_180004733
0x1800046dc  mov     rcx, cs:SstpSvcGlobals
0x1800046e3  mov     rcx, [rcx+120h]; pio
0x1800046ea  call    cs:__imp_CancelThreadpoolIo
0x1800046f0  test    cs:byte_18002D803, 8
0x1800046f7  jz      short loc_180004735
0x1800046f9  xor     eax, eax
0x1800046fb  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x180004702  mov     r8d, ebx
0x180004705  mov     word ptr [rsp+1080h+var_1030], ax
0x18000470a  lea     rcx, [rsp+1080h+var_1030]
0x18000470f  call    FormatRRASErrorString
0x180004714  test    cs:byte_18002D803, 8
0x18000471b  jz      short loc_180004735
0x18000471d  lea     r8, [rsp+1080h+var_1030]
0x180004722  mov     rcx, r14
0x180004725  lea     rdx, RasSSTPSvcTraceError
0x18000472c  call    McTemplateU0z_EventWriteTransfer
0x180004731  jmp     short loc_180004735
0x180004733  xor     ebx, ebx
0x180004735  test    cs:byte_18002D803, 10h
0x18000473c  jz      short loc_18000477A
0x18000473e  xor     eax, eax
0x180004740  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180004747  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000474e  mov     word ptr [rsp+1080h+var_1030], ax
0x180004753  lea     rcx, [rsp+1080h+var_1030]
0x180004758  call    FormatRRASErrorString
0x18000475d  test    cs:byte_18002D803, 10h
0x180004764  jz      short loc_18000477A
0x180004766  lea     r8, [rsp+1080h+var_1030]
0x18000476b  mov     rcx, r14
0x18000476e  lea     rdx, RasSSTPSvcTraceInfo
0x180004775  call    McTemplateU0z_EventWriteTransfer
0x18000477a  test    ebx, ebx
0x18000477c  jz      short loc_1800047FD
0x18000477e  test    cs:byte_18002D803, 8
0x180004785  jz      short loc_1800047E4
0x180004787  xor     eax, eax
0x180004789  lea     rdx, aFailureToQueue; "Failure to queue mini-send buffers - %d"
0x180004790  mov     r8d, ebx
0x180004793  mov     word ptr [rbp+0F80h+var_830], ax
0x18000479a  lea     rcx, [rbp+0F80h+var_830]
0x1800047a1  call    FormatRRASErrorString
0x1800047a6  test    cs:byte_18002D803, 8
0x1800047ad  jz      short loc_1800047E4
0x1800047af  lea     r8, [rbp+0F80h+var_830]
0x1800047b6  mov     rcx, r14
0x1800047b9  lea     rdx, RasSSTPSvcTraceError
0x1800047c0  call    McTemplateU0z_EventWriteTransfer
0x1800047c5  test    cs:byte_18002D803, 8
0x1800047cc  jz      short loc_1800047E4
0x1800047ce  lea     r8, aFreeingUpTheBu; "Freeing up the buffer"
0x1800047d5  mov     rcx, r14
0x1800047d8  lea     rdx, RasSSTPSvcTraceError
0x1800047df  call    McTemplateU0z_EventWriteTransfer
0x1800047e4  mov     rcx, cs:SstpSvcGlobals
0x1800047eb  mov     r8b, 1
0x1800047ee  add     rcx, 138h
0x1800047f5  mov     rdx, rdi
0x1800047f8  call    FreeBufferToPool
0x1800047fd  mov     eax, ebx
0x1800047ff  mov     rcx, [rbp+0F80h+var_30]
0x180004806  xor     rcx, rsp; StackCookie
0x180004809  call    __security_check_cookie
0x18000480e  add     rsp, 1068h
0x180004815  pop     r14
0x180004817  pop     rdi
0x180004818  pop     rbx
0x180004819  pop     rbp
0x18000481a  retn
```
