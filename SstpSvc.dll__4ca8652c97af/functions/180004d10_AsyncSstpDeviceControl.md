# AsyncSstpDeviceControl

- ea: `0x180004d10`
- end: `0x180004eec`
- name: `AsyncSstpDeviceControl`
- size: `476`
- prototype: `__int64 __fastcall(DWORD dwIoControlCode, LPVOID lpInBuffer, DWORD nInBufferSize, LPVOID lpOutBuffer, DWORD, LPOVERLAPPED)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180001240`
- `0x18000bf68`
- `0x18000cec8`

## callees

- `0x180004d10`
- `0x18000827c`
- `0x180008360`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004dba`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004db0`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004db0`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180004e0a`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x180004e0a`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004d76`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180004d76`

## pseudocode

```c
__int64 __fastcall AsyncSstpDeviceControl(
        DWORD dwIoControlCode,
        LPVOID lpInBuffer,
        DWORD nInBufferSize,
        LPVOID lpOutBuffer,
        DWORD nOutBufferSize,
        LPOVERLAPPED lpOverlapped)
{
  DWORD LastError; // ebx
  int v12; // [rsp+40h] [rbp-838h] BYREF
  _BYTE v13[2044]; // [rsp+44h] [rbp-834h] BYREF

  v12 = 0;
  memset_0(v13, 0, sizeof(v13));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"Entering %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v12);
  }
  StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
  if ( DeviceIoControl(
         *((HANDLE *)SstpSvcGlobals + 35),
         dwIoControlCode,
         lpInBuffer,
         nInBufferSize,
         lpOutBuffer,
         nOutBufferSize,
         0,
         lpOverlapped)
    || (LastError = GetLastError(), LastError == 997)
    || !LastError )
  {
    LastError = 0;
  }
  else
  {
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v12) = 0;
      FormatRRASErrorString(&v12, L"AsyncSstpDeviceIoControl fails with [%d]", LastError);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v12);
    }
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v12) = 0;
    FormatRRASErrorString(&v12, L"LEaving %ws", L"AsyncSstpDeviceControl");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v12);
  }
  return LastError;
}

```

## disassembly

```asm
0x180004d10  push    rbx
0x180004d12  push    rbp
0x180004d13  push    rsi
0x180004d14  push    rdi
0x180004d15  push    r14
0x180004d17  sub     rsp, 850h
0x180004d1e  mov     rax, cs:__security_cookie
0x180004d25  xor     rax, rsp
0x180004d28  mov     [rsp+878h+var_38], rax
0x180004d30  mov     r14, [rsp+878h+arg_28]
0x180004d38  mov     esi, r8d
0x180004d3b  mov     rdi, rdx
0x180004d3e  mov     ebx, ecx
0x180004d40  xor     eax, eax
0x180004d42  lea     rcx, [rsp+878h+var_834]; void *
0x180004d47  xor     edx, edx; Val
0x180004d49  mov     [rsp+878h+var_838], eax
0x180004d4d  mov     r8d, 7FCh; Size
0x180004d53  mov     rbp, r9
0x180004d56  call    memset_0
0x180004d5b  test    cs:byte_18002D803, 10h
0x180004d62  jnz     loc_180004E5A
0x180004d68  mov     rcx, cs:SstpSvcGlobals
0x180004d6f  mov     rcx, [rcx+120h]; pio
0x180004d76  call    cs:__imp_StartThreadpoolIo
0x180004d7c  mov     rcx, cs:SstpSvcGlobals
0x180004d83  mov     r9d, esi; nInBufferSize
0x180004d86  mov     eax, [rsp+878h+arg_20]
0x180004d8d  mov     r8, rdi; lpInBuffer
0x180004d90  mov     [rsp+878h+lpOverlapped], r14; lpOverlapped
0x180004d95  mov     edx, ebx; dwIoControlCode
0x180004d97  mov     [rsp+878h+lpBytesReturned], 0; lpBytesReturned
0x180004da0  mov     rcx, [rcx+118h]; hDevice
0x180004da7  mov     [rsp+878h+nOutBufferSize], eax; nOutBufferSize
0x180004dab  mov     [rsp+878h+lpOutBuffer], rbp; lpOutBuffer
0x180004db0  call    cs:__imp_DeviceIoControl
0x180004db6  test    eax, eax
0x180004db8  jnz     short loc_180004DC9
0x180004dba  call    cs:__imp_GetLastError
0x180004dc0  mov     ebx, eax
0x180004dc2  cmp     eax, 3E5h
0x180004dc7  jnz     short loc_180004DF8
0x180004dc9  xor     ebx, ebx
0x180004dcb  test    cs:byte_18002D803, 10h
0x180004dd2  jnz     loc_180004EA3
0x180004dd8  mov     eax, ebx
0x180004dda  mov     rcx, [rsp+878h+var_38]
0x180004de2  xor     rcx, rsp; StackCookie
0x180004de5  call    __security_check_cookie
0x180004dea  add     rsp, 850h
0x180004df1  pop     r14
0x180004df3  pop     rdi
0x180004df4  pop     rsi
0x180004df5  pop     rbp
0x180004df6  pop     rbx
0x180004df7  retn
0x180004df8  test    ebx, ebx
0x180004dfa  jz      short loc_180004DC9
0x180004dfc  mov     rcx, cs:SstpSvcGlobals
0x180004e03  mov     rcx, [rcx+120h]; pio
0x180004e0a  call    cs:__imp_CancelThreadpoolIo
0x180004e10  test    cs:byte_18002D803, 8
0x180004e17  jz      short loc_180004DCB
0x180004e19  xor     eax, eax
0x180004e1b  lea     rdx, aAsyncsstpdevic; "AsyncSstpDeviceIoControl fails with [%d"...
0x180004e22  mov     r8d, ebx
0x180004e25  mov     word ptr [rsp+878h+var_838], ax
0x180004e2a  lea     rcx, [rsp+878h+var_838]
0x180004e2f  call    FormatRRASErrorString
0x180004e34  test    cs:byte_18002D803, 8
0x180004e3b  jz      short loc_180004DCB
0x180004e3d  lea     r8, [rsp+878h+var_838]
0x180004e42  lea     rdx, RasSSTPSvcTraceError
0x180004e49  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e50  call    McTemplateU0z_EventWriteTransfer
0x180004e55  jmp     loc_180004DCB
0x180004e5a  xor     eax, eax
0x180004e5c  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180004e63  lea     rdx, aEnteringWs; "Entering %ws"
0x180004e6a  mov     word ptr [rsp+878h+var_838], ax
0x180004e6f  lea     rcx, [rsp+878h+var_838]
0x180004e74  call    FormatRRASErrorString
0x180004e79  test    cs:byte_18002D803, 10h
0x180004e80  jz      loc_180004D68
0x180004e86  lea     r8, [rsp+878h+var_838]
0x180004e8b  lea     rdx, RasSSTPSvcTraceInfo
0x180004e92  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004e99  call    McTemplateU0z_EventWriteTransfer
0x180004e9e  jmp     loc_180004D68
0x180004ea3  xor     eax, eax
0x180004ea5  lea     r8, aAsyncsstpdevic_0; "AsyncSstpDeviceControl"
0x180004eac  lea     rdx, aLeavingWs; "LEaving %ws"
0x180004eb3  mov     word ptr [rsp+878h+var_838], ax
0x180004eb8  lea     rcx, [rsp+878h+var_838]
0x180004ebd  call    FormatRRASErrorString
0x180004ec2  test    cs:byte_18002D803, 10h
0x180004ec9  jz      loc_180004DD8
0x180004ecf  lea     r8, [rsp+878h+var_838]
0x180004ed4  lea     rdx, RasSSTPSvcTraceInfo
0x180004edb  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180004ee2  call    McTemplateU0z_EventWriteTransfer
0x180004ee7  jmp     loc_180004DD8
```
