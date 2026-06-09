# IndicateCallConnectedToTPI

- ea: `0x18000afbc`
- end: `0x18000b2d9`
- name: `IndicateCallConnectedToTPI`
- size: `797`
- prototype: `int __fastcall(LPOVERLAPPED)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000a620`

## callees

- `0x1800021f0`
- `0x180002908`
- `0x180002d40`
- `0x1800033b0`
- `0x180006b10`
- `0x180006e80`
- `0x18000827c`
- `0x180008360`
- `0x18000afbc`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b14e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b060`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b14e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b244`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b071`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b071`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b145`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b145`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18000b1e3`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b09f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b191`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b09f`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x18000b191`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18000b1ba`
- `HTTPAPI!HttpWaitForDisconnect` at `0x18000b1ba`

## string_xrefs

- `0x18000b102`: `CoId=%hs:IncomingCallConnected request fails with %d`

## pseudocode

```c
int __fastcall IndicateCallConnectedToTPI(LPOVERLAPPED a1)
{
  unsigned int v2; // eax
  int result; // eax
  ULONG v4; // eax
  ULONG v5; // edi
  int v6; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v7[2044]; // [rsp+44h] [rbp-BCh] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString((wchar_t *)&v6, L"Entering %ws", L"IndicateCallConnectedToTPI");
    if ( (byte_18002D803 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  LODWORD(a1[1].Internal) = 17774;
  *(_OWORD *)&a1->Internal = 0;
  *(_OWORD *)&a1->Offset = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
  HIDWORD(a1[7].hEvent) |= 0x8000u;
  LeaveCriticalSection((LPCRITICAL_SECTION)&a1[9]);
  if ( (unsigned int)IsProxyCall(a1)
    || (_InterlockedIncrement((volatile signed __int32 *)&a1[6].16),
        StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36)),
        v2 = AsyncDeviceControl(*((_QWORD *)SstpSvcGlobals + 35), 1212460, (int)a1 + 240, 4, 0, 0, a1),
        v2 == 997) )
  {
    StartThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
    _InterlockedIncrement((volatile signed __int32 *)&a1[6].16);
    v4 = HttpWaitForDisconnect(*((HANDLE *)SstpSvcGlobals + 8), (HTTP_CONNECTION_ID)a1[8].hEvent, a1 + 4);
    v5 = v4;
    if ( !v4 || v4 == 997 )
    {
      PostReceiveOnCall(a1);
      result = IsProxyCall(a1);
      if ( !result )
        result = PostSendNotificationRequest(a1);
    }
    else
    {
      CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 21));
      if ( (byte_18002D803 & 8) != 0 )
      {
        LOWORD(v6) = 0;
        FormatRRASErrorString(
          (wchar_t *)&v6,
          L"CoId=%hs:WaitForDisconnect fails with error %d",
          &a1[17].InternalHigh,
          v5);
        if ( (byte_18002D803 & 8) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
      }
      DereferenceRefCount((__int64)&a1[6].Pointer);
      EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
      result = InitiateCallContextCleanup(a1, 1);
    }
  }
  else
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(
        (wchar_t *)&v6,
        L"CoId=%hs:IncomingCallConnected request fails with %d",
        &a1[17].InternalHigh,
        v2);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
    CancelThreadpoolIo(*((PTP_IO *)SstpSvcGlobals + 36));
    EnterCriticalSection((LPCRITICAL_SECTION)&a1[9]);
    HIDWORD(a1[7].hEvent) = HIDWORD(a1[7].hEvent) & 0xFFFF7DDF | 0x200;
    InitiateCallContextCleanup(a1, 2);
    result = DereferenceRefCount((__int64)&a1[6].Pointer);
  }
  if ( (byte_18002D803 & 0x10) != 0 )
  {
    LOWORD(v6) = 0;
    result = FormatRRASErrorString((wchar_t *)&v6, L"LEaving %ws", L"IndicateCallConnectedToTPI");
    if ( (byte_18002D803 & 0x10) != 0 )
      return McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceInfo, &v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000afbc  push    rbp
0x18000afbe  push    rbx
0x18000afbf  push    rsi
0x18000afc0  push    rdi
0x18000afc1  lea     rbp, [rsp-758h]
0x18000afc9  sub     rsp, 858h
0x18000afd0  mov     rax, cs:__security_cookie
0x18000afd7  xor     rax, rsp
0x18000afda  mov     [rbp+770h+var_30], rax
0x18000afe1  mov     rbx, rcx
0x18000afe4  xor     eax, eax
0x18000afe6  lea     rcx, [rsp+870h+var_82C]; void *
0x18000afeb  mov     [rsp+870h+var_830], eax
0x18000afef  xor     edx, edx; Val
0x18000aff1  mov     r8d, 7FCh; Size
0x18000aff7  call    memset_0
0x18000affc  test    cs:byte_18002D803, 10h
0x18000b003  jz      short loc_18000B045
0x18000b005  xor     eax, eax
0x18000b007  lea     r8, aIndicatecallco; "IndicateCallConnectedToTPI"
0x18000b00e  lea     rdx, aEnteringWs; "Entering %ws"
0x18000b015  mov     word ptr [rsp+870h+var_830], ax
0x18000b01a  lea     rcx, [rsp+870h+var_830]
0x18000b01f  call    FormatRRASErrorString
0x18000b024  test    cs:byte_18002D803, 10h
0x18000b02b  jz      short loc_18000B045
0x18000b02d  lea     r8, [rsp+870h+var_830]
0x18000b032  lea     rdx, RasSSTPSvcTraceInfo
0x18000b039  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b040  call    McTemplateU0z_EventWriteTransfer
0x18000b045  xorps   xmm0, xmm0
0x18000b048  mov     dword ptr [rbx+20h], 456Eh
0x18000b04f  movups  xmmword ptr [rbx], xmm0
0x18000b052  lea     rdi, [rbx+120h]
0x18000b059  mov     rcx, rdi; lpCriticalSection
0x18000b05c  movups  xmmword ptr [rbx+10h], xmm0
0x18000b060  call    cs:__imp_EnterCriticalSection
0x18000b066  bts     dword ptr [rbx+0FCh], 0Fh
0x18000b06e  mov     rcx, rdi; lpCriticalSection
0x18000b071  call    cs:__imp_LeaveCriticalSection
0x18000b077  mov     rcx, rbx
0x18000b07a  call    IsProxyCall
0x18000b07f  test    eax, eax
0x18000b081  jnz     loc_18000B183
0x18000b087  lea     rsi, [rbx+0D0h]
0x18000b08e  lock inc dword ptr [rsi]
0x18000b091  mov     rcx, cs:SstpSvcGlobals
0x18000b098  mov     rcx, [rcx+120h]; pio
0x18000b09f  call    cs:__imp_StartThreadpoolIo
0x18000b0a5  mov     rcx, cs:SstpSvcGlobals
0x18000b0ac  lea     r8, [rbx+0F0h]; int
0x18000b0b3  mov     [rsp+870h+var_840], rbx; LPOVERLAPPED
0x18000b0b8  mov     edx, 12802Ch; int
0x18000b0bd  mov     [rsp+870h+var_848], 0; DWORD
0x18000b0c5  mov     r9d, 4; int
0x18000b0cb  mov     [rsp+870h+var_850], 0; LPVOID
0x18000b0d4  mov     rcx, [rcx+118h]; int
0x18000b0db  call    AsyncDeviceControl
0x18000b0e0  cmp     eax, 3E5h
0x18000b0e5  jz      loc_18000B183
0x18000b0eb  test    cs:byte_18002D803, 8
0x18000b0f2  jz      short loc_18000B137
0x18000b0f4  xor     ecx, ecx
0x18000b0f6  lea     r8, [rbx+228h]
0x18000b0fd  mov     word ptr [rsp+870h+var_830], cx
0x18000b102  lea     rdx, aCoidHsIncoming; "CoId=%hs:IncomingCallConnected request "...
0x18000b109  lea     rcx, [rsp+870h+var_830]
0x18000b10e  mov     r9d, eax
0x18000b111  call    FormatRRASErrorString
0x18000b116  test    cs:byte_18002D803, 8
0x18000b11d  jz      short loc_18000B137
0x18000b11f  lea     r8, [rsp+870h+var_830]
0x18000b124  lea     rdx, RasSSTPSvcTraceError
0x18000b12b  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b132  call    McTemplateU0z_EventWriteTransfer
0x18000b137  mov     rcx, cs:SstpSvcGlobals
0x18000b13e  mov     rcx, [rcx+120h]; pio
0x18000b145  call    cs:__imp_CancelThreadpoolIo
0x18000b14b  mov     rcx, rdi; lpCriticalSection
0x18000b14e  call    cs:__imp_EnterCriticalSection
0x18000b154  mov     eax, [rbx+0FCh]
0x18000b15a  mov     edx, 2
0x18000b15f  and     eax, 0FFFF7FDFh
0x18000b164  mov     rcx, rbx
0x18000b167  bts     eax, 9
0x18000b16b  mov     [rbx+0FCh], eax
0x18000b171  call    InitiateCallContextCleanup
0x18000b176  mov     rcx, rsi
0x18000b179  call    DereferenceRefCount
0x18000b17e  jmp     loc_18000B275
0x18000b183  mov     rcx, cs:SstpSvcGlobals
0x18000b18a  mov     rcx, [rcx+0A8h]; pio
0x18000b191  call    cs:__imp_StartThreadpoolIo
0x18000b197  lea     rsi, [rbx+0D0h]
0x18000b19e  lock inc dword ptr [rsi]
0x18000b1a1  mov     rcx, cs:SstpSvcGlobals
0x18000b1a8  lea     r8, [rbx+80h]; Overlapped
0x18000b1af  mov     rdx, [rbx+118h]; ConnectionId
0x18000b1b6  mov     rcx, [rcx+40h]; RequestQueueHandle
0x18000b1ba  call    cs:__imp_HttpWaitForDisconnect
0x18000b1c0  mov     edi, eax
0x18000b1c2  test    eax, eax
0x18000b1c4  jz      loc_18000B259
0x18000b1ca  cmp     eax, 3E5h
0x18000b1cf  jz      loc_18000B259
0x18000b1d5  mov     rcx, cs:SstpSvcGlobals
0x18000b1dc  mov     rcx, [rcx+0A8h]; pio
0x18000b1e3  call    cs:__imp_CancelThreadpoolIo
0x18000b1e9  test    cs:byte_18002D803, 8
0x18000b1f0  jz      short loc_18000B235
0x18000b1f2  xor     eax, eax
0x18000b1f4  lea     r8, [rbx+228h]
0x18000b1fb  mov     r9d, edi
0x18000b1fe  mov     word ptr [rsp+870h+var_830], ax
0x18000b203  lea     rdx, aCoidHsWaitford; "CoId=%hs:WaitForDisconnect fails with e"...
0x18000b20a  lea     rcx, [rsp+870h+var_830]
0x18000b20f  call    FormatRRASErrorString
0x18000b214  test    cs:byte_18002D803, 8
0x18000b21b  jz      short loc_18000B235
0x18000b21d  lea     r8, [rsp+870h+var_830]
0x18000b222  lea     rdx, RasSSTPSvcTraceError
0x18000b229  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b230  call    McTemplateU0z_EventWriteTransfer
0x18000b235  mov     rcx, rsi
0x18000b238  call    DereferenceRefCount
0x18000b23d  lea     rcx, [rbx+120h]; lpCriticalSection
0x18000b244  call    cs:__imp_EnterCriticalSection
0x18000b24a  mov     edx, 1
0x18000b24f  mov     rcx, rbx
0x18000b252  call    InitiateCallContextCleanup
0x18000b257  jmp     short loc_18000B275
0x18000b259  mov     rcx, rbx
0x18000b25c  call    PostReceiveOnCall
0x18000b261  mov     rcx, rbx
0x18000b264  call    IsProxyCall
0x18000b269  test    eax, eax
0x18000b26b  jnz     short loc_18000B275
0x18000b26d  mov     rcx, rbx
0x18000b270  call    PostSendNotificationRequest
0x18000b275  test    cs:byte_18002D803, 10h
0x18000b27c  jz      short loc_18000B2BE
0x18000b27e  xor     eax, eax
0x18000b280  lea     r8, aIndicatecallco; "IndicateCallConnectedToTPI"
0x18000b287  lea     rdx, aLeavingWs; "LEaving %ws"
0x18000b28e  mov     word ptr [rsp+870h+var_830], ax
0x18000b293  lea     rcx, [rsp+870h+var_830]
0x18000b298  call    FormatRRASErrorString
0x18000b29d  test    cs:byte_18002D803, 10h
0x18000b2a4  jz      short loc_18000B2BE
0x18000b2a6  lea     r8, [rsp+870h+var_830]
0x18000b2ab  lea     rdx, RasSSTPSvcTraceInfo
0x18000b2b2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000b2b9  call    McTemplateU0z_EventWriteTransfer
0x18000b2be  mov     rcx, [rbp+770h+var_30]
0x18000b2c5  xor     rcx, rsp; StackCookie
0x18000b2c8  call    __security_check_cookie
0x18000b2cd  add     rsp, 858h
0x18000b2d4  pop     rdi
0x18000b2d5  pop     rsi
0x18000b2d6  pop     rbx
0x18000b2d7  pop     rbp
0x18000b2d8  retn
```
