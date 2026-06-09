# HttpQueryServiceConfiguration

- ea: `0x180001e70`
- end: `0x180002608`
- name: `HttpQueryServiceConfiguration`
- size: `1944`
- prototype: `ULONG __stdcall(HANDLE ServiceHandle, HTTP_SERVICE_CONFIG_ID ConfigId, PVOID pInput, ULONG InputLength, PVOID pOutput, ULONG OutputLength, PULONG pReturnLength, LPOVERLAPPED pOverlapped)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001920`
- `0x180001e70`
- `0x180002cc0`
- `0x180008674`
- `0x180008b90`
- `0x18000941c`
- `0x18000a4c8`
- `0x18000a5f0`
- `0x18000b080`
- `0x18000be2c`
- `0x18000beb4`
- `0x18000c1bc`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180002016`
- `ntdll!NtDeviceIoControlFile` at `0x180002016`
- `ntdll!NtWaitForSingleObject` at `0x1800020cc`
- `ntdll!NtWaitForSingleObject` at `0x1800020cc`
- `ntdll!RtlNtStatusToDosError` at `0x18000204f`
- `ntdll!RtlNtStatusToDosError` at `0x18000204f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800025ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800025ab`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002510`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002510`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000259d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800024f7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000259d`

## pseudocode

```c
ULONG __stdcall HttpQueryServiceConfiguration(
        HANDLE ServiceHandle,
        HTTP_SERVICE_CONFIG_ID ConfigId,
        PVOID pInput,
        ULONG InputLength,
        PVOID pOutput,
        ULONG OutputLength,
        PULONG pReturnLength,
        LPOVERLAPPED pOverlapped)
{
  char v11; // si
  DWORD LowPart; // r14d
  __int16 *v13; // rdx
  int v14; // ecx
  int v15; // r8d
  bool v16; // r13
  _BYTE *OutputBuffer; // rsi
  _QWORD *v18; // rcx
  ULONG v19; // r9d
  void *v20; // r15
  HANDLE v21; // r12
  NTSTATUS Status; // ebx
  HANDLE v23; // r14
  __int64 v24; // rcx
  ULONG v25; // eax
  __int64 v26; // r8
  ULONG v27; // ebx
  HTTP_SERVICE_CONFIG_ID v29; // ebx
  int v30; // eax
  int v31; // eax
  __int128 v32; // xmm1
  __int128 v33; // xmm1
  __int128 v34; // xmm1
  __int128 v35; // xmm1
  int v36; // eax
  __int128 v37; // xmm1
  __int128 v38; // xmm1
  __int128 v39; // xmm1
  __int128 v40; // xmm1
  int v41; // eax
  __int128 v42; // xmm1
  __int128 v43; // xmm1
  __int128 v44; // xmm1
  __int128 v45; // xmm1
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  __int128 v51; // xmm0
  __int128 v52; // xmm1
  __int128 v53; // xmm0
  LSTATUS UrlAclInfo; // eax
  HANDLE v55; // rax
  LPVOID v56; // rax
  HANDLE ProcessHeap; // rax
  ULONG OutputBufferLength; // [rsp+48h] [rbp-B8h]
  HANDLE Event; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v60; // [rsp+60h] [rbp-A0h]
  _LARGE_INTEGER Timeout; // [rsp+68h] [rbp-98h] BYREF
  HTTP_SERVICE_CONFIG_ID v62; // [rsp+70h] [rbp-90h]
  HTTP_SERVICE_CONFIG_ID InputBuffer; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v64[144]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v65; // [rsp+118h] [rbp+18h]
  _DWORD *v66; // [rsp+120h] [rbp+20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v68[4]; // [rsp+140h] [rbp+40h] BYREF
  int v69; // [rsp+144h] [rbp+44h]

  v62 = ConfigId;
  v60 = pOutput;
  v11 = InputLength;
  LODWORD(Event) = InputLength;
  memset_0(&InputBuffer, 0, 0xA0u);
  LowPart = 0;
  v69 = 0;
  Timeout.LowPart = 0;
  v66 = 0;
  memset_0(v68, 0, 0xD4u);
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_IqLqL(v14, (_DWORD)v13, v15, ConfigId, (char)pInput, v11, pOutput, OutputLength);
  if ( pOverlapped || ServiceHandle )
    goto LABEL_49;
  v16 = 0;
  OutputBuffer = 0;
  if ( pReturnLength )
    *pReturnLength = 0;
  InputBuffer = ConfigId;
  if ( ConfigId != HttpServiceConfigSSLCertInfo )
  {
    if ( ConfigId != HttpServiceConfigTimeout )
    {
      v13 = &_ImageBase;
      switch ( ConfigId )
      {
        case 0:
          v18 = v60;
          LowPart = 136;
          v19 = OutputLength;
          if ( v60 && OutputLength < 0x88 )
            goto LABEL_48;
          if ( !pReturnLength )
          {
            v27 = 87;
            goto LABEL_31;
          }
          OutputBuffer = v68;
          if ( v60 )
          {
            OutputBuffer = 0;
            LowPart = 0;
          }
          v16 = v60 == 0;
          break;
        case 2:
          UrlAclInfo = QueryUrlAclInfo((__int64)pInput, (int)Event, v60, OutputLength, (unsigned int *)&Timeout);
          LowPart = Timeout.LowPart;
          v27 = UrlAclInfo;
          goto LABEL_29;
        case 4:
        case 7:
          goto LABEL_39;
        case 5:
        case 11:
          if ( !pInput || (_DWORD)Event != 152 )
            goto LABEL_48;
          v36 = *(_DWORD *)pInput;
          v37 = *(_OWORD *)((char *)pInput + 24);
          v18 = v60;
          v19 = OutputLength;
          *(_OWORD *)&v64[8] = *(_OWORD *)((char *)pInput + 8);
          *(_OWORD *)&v64[24] = v37;
          *(_DWORD *)v64 = v36;
          LODWORD(v65) = *((_DWORD *)pInput + 36);
          v38 = *(_OWORD *)((char *)pInput + 56);
          *(_OWORD *)&v64[40] = *(_OWORD *)((char *)pInput + 40);
          *(_OWORD *)&v64[56] = v38;
          v39 = *(_OWORD *)((char *)pInput + 88);
          *(_OWORD *)&v64[72] = *(_OWORD *)((char *)pInput + 72);
          *(_OWORD *)&v64[88] = v39;
          v40 = *(_OWORD *)((char *)pInput + 120);
          *(_OWORD *)&v64[104] = *(_OWORD *)((char *)pInput + 104);
          *(_QWORD *)&v64[136] = *((_QWORD *)pInput + 17);
          *(_OWORD *)&v64[120] = v40;
          if ( v60 && OutputLength >= 0xD8 )
            goto LABEL_13;
          LowPart = 216;
          goto LABEL_37;
        case 6:
          if ( !pInput || (_DWORD)Event != 144 )
            goto LABEL_48;
          v31 = *(_DWORD *)pInput;
          v32 = *(_OWORD *)((char *)pInput + 24);
          v18 = v60;
          v19 = OutputLength;
          *(_OWORD *)&v64[8] = *(_OWORD *)((char *)pInput + 8);
          *(_OWORD *)&v64[24] = v32;
          *(_DWORD *)v64 = v31;
          LODWORD(v65) = *((_DWORD *)pInput + 34);
          v33 = *(_OWORD *)((char *)pInput + 56);
          *(_OWORD *)&v64[40] = *(_OWORD *)((char *)pInput + 40);
          *(_OWORD *)&v64[56] = v33;
          v34 = *(_OWORD *)((char *)pInput + 88);
          *(_OWORD *)&v64[72] = *(_OWORD *)((char *)pInput + 72);
          *(_OWORD *)&v64[88] = v34;
          v35 = *(_OWORD *)((char *)pInput + 120);
          *(_OWORD *)&v64[104] = *(_OWORD *)((char *)pInput + 104);
          *(_OWORD *)&v64[120] = v35;
          if ( v60 && OutputLength >= 0xD0 )
            goto LABEL_13;
          LowPart = 208;
          goto LABEL_37;
        case 8:
        case 10:
          if ( !pInput || (_DWORD)Event != 144 )
            goto LABEL_48;
          v41 = *(_DWORD *)pInput;
          v42 = *(_OWORD *)((char *)pInput + 24);
          v18 = v60;
          v19 = OutputLength;
          *(_OWORD *)&v64[8] = *(_OWORD *)((char *)pInput + 8);
          *(_OWORD *)&v64[24] = v42;
          *(_DWORD *)v64 = v41;
          v65 = *((_QWORD *)pInput + 17);
          v43 = *(_OWORD *)((char *)pInput + 56);
          *(_OWORD *)&v64[40] = *(_OWORD *)((char *)pInput + 40);
          *(_OWORD *)&v64[56] = v43;
          v44 = *(_OWORD *)((char *)pInput + 88);
          *(_OWORD *)&v64[72] = *(_OWORD *)((char *)pInput + 72);
          *(_OWORD *)&v64[88] = v44;
          v45 = *(_OWORD *)((char *)pInput + 120);
          *(_OWORD *)&v64[104] = *(_OWORD *)((char *)pInput + 104);
          *(_OWORD *)&v64[120] = v45;
          if ( v60 && OutputLength >= 0xA0 )
            goto LABEL_13;
          LowPart = 160;
          goto LABEL_37;
        case 9:
        case 12:
          if ( !pInput || (_DWORD)Event != 152 )
            goto LABEL_48;
          v18 = v60;
          v19 = OutputLength;
          v46 = *((_OWORD *)pInput + 1);
          *(_OWORD *)v64 = *(_OWORD *)pInput;
          v47 = *((_OWORD *)pInput + 2);
          *(_OWORD *)&v64[16] = v46;
          v48 = *((_OWORD *)pInput + 3);
          *(_OWORD *)&v64[32] = v47;
          v49 = *((_OWORD *)pInput + 4);
          *(_OWORD *)&v64[48] = v48;
          v50 = *((_OWORD *)pInput + 5);
          *(_OWORD *)&v64[64] = v49;
          v51 = *((_OWORD *)pInput + 6);
          *(_OWORD *)&v64[80] = v50;
          v52 = *((_OWORD *)pInput + 7);
          *(_OWORD *)&v64[96] = v51;
          v53 = *((_OWORD *)pInput + 8);
          *(_OWORD *)&v64[112] = v52;
          v65 = *((_QWORD *)pInput + 18);
          *(_OWORD *)&v64[128] = v53;
          if ( v60 && OutputLength >= 0xA8 )
            goto LABEL_13;
          LowPart = 168;
          goto LABEL_37;
        default:
          goto LABEL_48;
      }
      goto LABEL_13;
    }
LABEL_39:
    if ( pInput && (_DWORD)Event == 4 )
    {
      v19 = OutputLength;
      v18 = v60;
      *(_DWORD *)v64 = *(_DWORD *)pInput;
LABEL_13:
      if ( HIDWORD(v65) != 3 )
      {
        v20 = 0;
        if ( !OutputBuffer )
        {
          OutputBuffer = v18;
          LowPart = v19;
        }
LABEL_16:
        v21 = g_ServiceCommChannelHandle;
        IoStatusBlock = 0;
        Timeout.QuadPart = 0;
        Event = 0;
        if ( (byte_1800126A3 & 4) != 0 )
          WPP_SF_qLqLqL(
            (_DWORD)v18,
            (_DWORD)v13,
            0,
            (_DWORD)g_ServiceCommChannelHandle,
            134,
            (char)&InputBuffer,
            160,
            OutputBuffer,
            LowPart);
        Status = HttpApiAcquireCachedEvent(&Event);
        if ( Status < 0 )
          goto LABEL_22;
        OutputBufferLength = LowPart;
        v23 = Event;
        Status = NtDeviceIoControlFile(
                   v21,
                   Event,
                   0,
                   0,
                   &IoStatusBlock,
                   0x124086u,
                   &InputBuffer,
                   0xA0u,
                   OutputBuffer,
                   OutputBufferLength);
        if ( Status == 259 )
        {
          Timeout.QuadPart = 0x7FFFFFFFFFFFFFFFLL;
          NtWaitForSingleObject(v23, 0, &Timeout);
          Status = IoStatusBlock.Status;
        }
        if ( (Status & 0xC0000000) == 0xC0000000 )
        {
LABEL_22:
          LowPart = 0;
        }
        else
        {
          LowPart = IoStatusBlock.Information;
          if ( (byte_1800126A3 & 4) == 0 )
          {
LABEL_25:
            v25 = RtlNtStatusToDosError(Status);
            v27 = v25;
            if ( v16 )
            {
              if ( !v25 || v25 == 234 )
                v27 = 122;
            }
            else if ( !v25 && HIDWORD(v65) == 3 )
            {
              v29 = v62;
              v30 = CalculateTlsParamsSize((unsigned int)v62, OutputBuffer, v26, &v66);
              LowPart += v30 - 5264 * *v66;
              if ( OutputLength >= LowPart )
                v27 = DeserializeTlsParams((unsigned int)v29, OutputBuffer, v60, OutputLength);
              else
                v27 = 122;
            }
            if ( v20 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v20);
            }
            goto LABEL_29;
          }
          WPP_SF_L(v24, 11, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids);
        }
        if ( (byte_1800126A3 & 4) != 0 )
          WPP_SF_d(1050, 12, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids, (unsigned int)Status);
        goto LABEL_25;
      }
      v55 = GetProcessHeap();
      LowPart = 21531;
      v27 = 8;
      v56 = HeapAlloc(v55, 8u, 0x541Bu);
      v20 = v56;
      if ( v56 )
      {
        v16 = 0;
        OutputBuffer = v56;
        goto LABEL_16;
      }
      goto LABEL_83;
    }
    goto LABEL_48;
  }
  if ( !pInput || (_DWORD)Event != 24 )
  {
LABEL_48:
    LowPart = 0;
LABEL_49:
    v27 = 87;
    goto LABEL_29;
  }
  if ( *(_DWORD *)pInput || (v27 = CopySockAddrToSockAddrStorage(*((_QWORD *)pInput + 1), &v64[8])) == 0 )
  {
    v18 = v60;
    v19 = OutputLength;
    *(_DWORD *)v64 = *(_DWORD *)pInput;
    LODWORD(v65) = *((_DWORD *)pInput + 4);
    if ( !v60 || OutputLength < 0x58 )
    {
      LowPart = 88;
LABEL_37:
      v16 = 1;
      OutputBuffer = v68;
    }
    goto LABEL_13;
  }
LABEL_83:
  LowPart = 0;
LABEL_29:
  if ( pReturnLength )
    *pReturnLength = LowPart;
LABEL_31:
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_d(1050, 47, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, v27);
  return v27;
}

```

## disassembly

```asm
0x180001e70  mov     [rsp-8+arg_0], rbx
0x180001e75  push    rbp
0x180001e76  push    rsi
0x180001e77  push    rdi
0x180001e78  push    r12
0x180001e7a  push    r13
0x180001e7c  push    r14
0x180001e7e  push    r15
0x180001e80  lea     rbp, [rsp-130h]
0x180001e88  sub     rsp, 230h
0x180001e8f  mov     rax, cs:__security_cookie
0x180001e96  xor     rax, rsp
0x180001e99  mov     [rbp+160h+var_40], rax
0x180001ea0  mov     r13, [rbp+160h+pOutput]
0x180001ea7  mov     r15, r8
0x180001eaa  mov     rdi, [rbp+160h+pReturnLength]
0x180001eb1  mov     rbx, rcx
0x180001eb4  movsxd  r12, edx
0x180001eb7  lea     rcx, [rbp+160h+var_1E0]; void *
0x180001ebb  xor     edx, edx; Val
0x180001ebd  mov     [rsp+260h+var_1F0], r12d
0x180001ec2  mov     r8d, 0A0h; Size
0x180001ec8  mov     [rsp+260h+var_200], r13
0x180001ecd  mov     esi, r9d
0x180001ed0  mov     dword ptr [rsp+260h+Event], r9d
0x180001ed5  call    memset_0
0x180001eda  xor     r14d, r14d
0x180001edd  lea     rcx, [rbp+160h+var_120]; void *
0x180001ee1  xor     eax, eax
0x180001ee3  mov     [rsp+260h+var_210], r14d
0x180001ee8  xor     edx, edx; Val
0x180001eea  mov     [rbp+160h+var_11C], eax
0x180001eed  mov     r8d, 0D4h; Size
0x180001ef3  mov     dword ptr [rsp+260h+Timeout], r14d
0x180001ef8  mov     [rbp+160h+var_140], r14
0x180001efc  call    memset_0
0x180001f01  test    cs:byte_1800126A3, 4
0x180001f08  jnz     loc_1800021AF
0x180001f0e  cmp     [rbp+160h+pOverlapped], r14
0x180001f15  jnz     loc_1800021A5
0x180001f1b  test    rbx, rbx
0x180001f1e  jnz     loc_1800021A5
0x180001f24  xor     r8d, r8d
0x180001f27  xor     r13b, r13b
0x180001f2a  mov     esi, r8d
0x180001f2d  test    rdi, rdi
0x180001f30  jz      short loc_180001F35
0x180001f32  mov     [rdi], r8d
0x180001f35  mov     [rbp+160h+var_1E0], r12d
0x180001f39  cmp     r12d, 1
0x180001f3d  jnz     loc_180002116
0x180001f43  test    r15, r15
0x180001f46  jz      def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x180001f4c  cmp     dword ptr [rsp+260h+Event], 18h
0x180001f51  jnz     def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x180001f57  cmp     [r15], esi
0x180001f5a  jz      loc_1800024DC
0x180001f60  mov     eax, [r15]
0x180001f63  mov     rcx, [rsp+260h+var_200]
0x180001f68  mov     r9d, [rbp+160h+OutputLength]
0x180001f6f  mov     dword ptr [rbp+160h+var_1D8], eax
0x180001f72  mov     eax, [r15+10h]
0x180001f76  mov     dword ptr [rbp+160h+var_148], eax
0x180001f79  test    rcx, rcx
0x180001f7c  jz      loc_180002104
0x180001f82  cmp     r9d, 58h ; 'X'
0x180001f86  jb      loc_180002104
0x180001f8c  cmp     dword ptr [rbp+160h+var_148+4], 3
0x180001f90  jz      loc_1800024F7
0x180001f96  mov     r15, r8
0x180001f99  test    rsi, rsi
0x180001f9c  jnz     short loc_180001FA4
0x180001f9e  mov     rsi, rcx
0x180001fa1  mov     r14d, r9d
0x180001fa4  mov     r12, cs:g_ServiceCommChannelHandle
0x180001fab  xorps   xmm0, xmm0
0x180001fae  movups  xmmword ptr [rbp+160h+var_138], xmm0
0x180001fb2  mov     qword ptr [rsp+260h+Timeout], r8
0x180001fb7  mov     [rsp+260h+Event], r8
0x180001fbc  test    cs:byte_1800126A3, 4
0x180001fc3  jnz     loc_180002536
0x180001fc9  lea     rcx, [rsp+260h+Event]
0x180001fce  call    HttpApiAcquireCachedEvent
0x180001fd3  mov     ebx, eax
0x180001fd5  test    eax, eax
0x180001fd7  js      short loc_18000203B
0x180001fd9  mov     [rsp+260h+OutputBufferLength], r14d; OutputBufferLength
0x180001fde  lea     rax, [rbp+160h+var_1E0]
0x180001fe2  mov     r14, [rsp+260h+Event]
0x180001fe7  xor     r9d, r9d; ApcContext
0x180001fea  mov     [rsp+260h+OutputBuffer], rsi; OutputBuffer
0x180001fef  xor     r8d, r8d; ApcRoutine
0x180001ff2  mov     [rsp+260h+InputBufferLength], 0A0h; InputBufferLength
0x180001ffa  mov     rdx, r14; Event
0x180001ffd  mov     [rsp+260h+InputBuffer], rax; InputBuffer
0x180002002  mov     rcx, r12; FileHandle
0x180002005  lea     rax, [rbp+160h+var_138]
0x180002009  mov     [rsp+260h+IoControlCode], 124086h; IoControlCode
0x180002011  mov     [rsp+260h+IoStatusBlock], rax; IoStatusBlock
0x180002016  call    cs:__imp_NtDeviceIoControlFile
0x18000201c  mov     ebx, eax
0x18000201e  cmp     eax, 103h
0x180002023  jz      loc_1800020B2
0x180002029  mov     eax, ebx
0x18000202b  and     eax, 0C0000000h
0x180002030  cmp     eax, 0C0000000h
0x180002035  jnz     loc_1800020DA
0x18000203b  mov     r14d, [rsp+260h+var_210]
0x180002040  test    cs:byte_1800126A3, 4
0x180002047  jnz     loc_180002566
0x18000204d  mov     ecx, ebx; Status
0x18000204f  call    cs:__imp_RtlNtStatusToDosError
0x180002055  mov     ebx, eax
0x180002057  test    r13b, r13b
0x18000205a  jnz     loc_180002187
0x180002060  test    eax, eax
0x180002062  jz      loc_180002143
0x180002068  test    r15, r15
0x18000206b  jnz     loc_18000259D
0x180002071  test    rdi, rdi
0x180002074  jz      short loc_180002079
0x180002076  mov     [rdi], r14d
0x180002079  test    cs:byte_1800126A3, 4
0x180002080  jnz     loc_1800025B6
0x180002086  mov     eax, ebx
0x180002088  mov     rcx, [rbp+160h+var_40]
0x18000208f  xor     rcx, rsp; StackCookie
0x180002092  call    __security_check_cookie
0x180002097  mov     rbx, [rsp+260h+arg_0]
0x18000209f  add     rsp, 230h
0x1800020a6  pop     r15
0x1800020a8  pop     r14
0x1800020aa  pop     r13
0x1800020ac  pop     r12
0x1800020ae  pop     rdi
0x1800020af  pop     rsi
0x1800020b0  pop     rbp
0x1800020b1  retn
0x1800020b2  lea     r8, [rsp+260h+Timeout]; Timeout
0x1800020b7  mov     dword ptr [rsp+260h+Timeout], 0FFFFFFFFh
0x1800020bf  xor     edx, edx; Alertable
0x1800020c1  mov     dword ptr [rsp+260h+Timeout+4], 7FFFFFFFh
0x1800020c9  mov     rcx, r14; Handle
0x1800020cc  call    cs:__imp_NtWaitForSingleObject
0x1800020d2  mov     ebx, dword ptr [rbp+160h+var_138]
0x1800020d5  jmp     loc_180002029
0x1800020da  mov     r14d, dword ptr [rbp+160h+var_138.Information]
0x1800020de  test    cs:byte_1800126A3, 4
0x1800020e5  jz      loc_18000204D
0x1800020eb  mov     edx, 0Bh
0x1800020f0  lea     r8, WPP_f0d88ac2d9fc3a89569733988c3b753d_Traceguids
0x1800020f7  mov     r9d, r14d
0x1800020fa  call    WPP_SF_L
0x1800020ff  jmp     loc_180002040
0x180002104  mov     r14d, 58h ; 'X'
0x18000210a  mov     r13b, 1
0x18000210d  lea     rsi, [rbp+160h+var_120]
0x180002111  jmp     loc_180001F8C
0x180002116  cmp     r12d, 3
0x18000211a  jnz     loc_1800021D4
0x180002120  test    r15, r15; jumptable 00000001800021EC cases 4,7
0x180002123  jz      short def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x180002125  cmp     dword ptr [rsp+260h+Event], 4
0x18000212a  jnz     short def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x18000212c  mov     eax, [r15]
0x18000212f  mov     r9d, [rbp+160h+OutputLength]
0x180002136  mov     rcx, [rsp+260h+var_200]
0x18000213b  mov     dword ptr [rbp+160h+var_1D8], eax
0x18000213e  jmp     loc_180001F8C
0x180002143  cmp     dword ptr [rbp+160h+var_148+4], 3
0x180002147  jnz     loc_180002068
0x18000214d  mov     ebx, [rsp+260h+var_1F0]
0x180002151  lea     r9, [rbp+160h+var_140]
0x180002155  mov     ecx, ebx
0x180002157  mov     rdx, rsi
0x18000215a  call    CalculateTlsParamsSize
0x18000215f  mov     rcx, [rbp+160h+var_140]
0x180002163  imul    edx, [rcx], 1490h
0x180002169  sub     eax, edx
0x18000216b  add     r14d, eax
0x18000216e  mov     eax, [rbp+160h+OutputLength]
0x180002174  cmp     eax, r14d
0x180002177  jnb     loc_180002584
0x18000217d  mov     ebx, 7Ah ; 'z'
0x180002182  jmp     loc_180002068
0x180002187  test    eax, eax
0x180002189  jz      short loc_180002196
0x18000218b  cmp     eax, 0EAh
0x180002190  jnz     loc_180002068
0x180002196  mov     ebx, 7Ah ; 'z'
0x18000219b  jmp     loc_180002068
0x1800021a0  mov     r14d, [rsp+260h+var_210]; jumptable 00000001800021EC default case, cases 1,3
0x1800021a5  mov     ebx, 57h ; 'W'
0x1800021aa  jmp     loc_180002071
0x1800021af  mov     eax, [rbp+160h+OutputLength]
0x1800021b5  mov     r9, r12
0x1800021b8  mov     [rsp+260h+InputBufferLength], eax
0x1800021bc  mov     [rsp+260h+InputBuffer], r13
0x1800021c1  mov     [rsp+260h+IoControlCode], esi
0x1800021c5  mov     [rsp+260h+IoStatusBlock], r15
0x1800021ca  call    WPP_SF_IqLqL
0x1800021cf  jmp     loc_180001F0E
0x1800021d4  cmp     r12d, 0Ch; switch 13 cases
0x1800021d8  ja      short def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x1800021da  lea     rdx, __ImageBase
0x1800021e1  mov     ecx, ds:(jpt_1800021EC - 180000000h)[rdx+r12*4]
0x1800021e9  add     rcx, rdx
0x1800021ec  jmp     rcx; switch jump
0x1800021ee  test    r15, r15; jumptable 00000001800021EC case 6
0x1800021f1  jz      short def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x1800021f3  cmp     dword ptr [rsp+260h+Event], 90h
0x1800021fb  jnz     short def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x1800021fd  movups  xmm0, xmmword ptr [r15+8]
0x180002202  mov     eax, [r15]
0x180002205  movups  xmm1, xmmword ptr [r15+18h]
0x18000220a  mov     rcx, [rsp+260h+var_200]
0x18000220f  mov     r9d, [rbp+160h+OutputLength]
0x180002216  movaps  [rbp+160h+var_1D8+8], xmm0
0x18000221a  movaps  [rbp+160h+var_1C0], xmm1
0x18000221e  mov     dword ptr [rbp+160h+var_1D8], eax
0x180002221  mov     eax, [r15+88h]
0x180002228  mov     dword ptr [rbp+160h+var_148], eax
0x18000222b  movups  xmm0, xmmword ptr [r15+28h]
0x180002230  movups  xmm1, xmmword ptr [r15+38h]
0x180002235  movaps  [rbp+160h+var_1B0], xmm0
0x180002239  movaps  [rbp+160h+var_1A0], xmm1
0x18000223d  movups  xmm0, xmmword ptr [r15+48h]
0x180002242  movups  xmm1, xmmword ptr [r15+58h]
0x180002247  movaps  [rbp+160h+var_190], xmm0
0x18000224b  movaps  [rbp+160h+var_180], xmm1
0x18000224f  movups  xmm0, xmmword ptr [r15+68h]
0x180002254  movups  xmm1, xmmword ptr [r15+78h]
0x180002259  movaps  [rbp+160h+var_170], xmm0
0x18000225d  movaps  [rbp+160h+var_160], xmm1
0x180002261  test    rcx, rcx
0x180002264  jz      short loc_180002273
0x180002266  cmp     r9d, 0D0h
0x18000226d  jnb     loc_180001F8C
0x180002273  mov     r14d, 0D0h
0x180002279  jmp     loc_18000210A
0x18000227e  test    r15, r15; jumptable 00000001800021EC cases 5,11
0x180002281  jz      def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x180002287  cmp     dword ptr [rsp+260h+Event], 98h
0x18000228f  jnz     def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x180002295  movups  xmm0, xmmword ptr [r15+8]
0x18000229a  mov     eax, [r15]
0x18000229d  movups  xmm1, xmmword ptr [r15+18h]
0x1800022a2  mov     rcx, [rsp+260h+var_200]
0x1800022a7  mov     r9d, [rbp+160h+OutputLength]
0x1800022ae  movaps  [rbp+160h+var_1D8+8], xmm0
0x1800022b2  movaps  [rbp+160h+var_1C0], xmm1
0x1800022b6  mov     dword ptr [rbp+160h+var_1D8], eax
0x1800022b9  mov     eax, [r15+90h]
0x1800022c0  mov     dword ptr [rbp+160h+var_148], eax
0x1800022c3  movups  xmm0, xmmword ptr [r15+28h]
0x1800022c8  movups  xmm1, xmmword ptr [r15+38h]
0x1800022cd  movaps  [rbp+160h+var_1B0], xmm0
0x1800022d1  movaps  [rbp+160h+var_1A0], xmm1
0x1800022d5  movups  xmm0, xmmword ptr [r15+48h]
0x1800022da  movups  xmm1, xmmword ptr [r15+58h]
0x1800022df  movaps  [rbp+160h+var_190], xmm0
0x1800022e3  movaps  [rbp+160h+var_180], xmm1
0x1800022e7  movups  xmm0, xmmword ptr [r15+68h]
0x1800022ec  movups  xmm1, xmmword ptr [r15+78h]
0x1800022f1  movaps  [rbp+160h+var_170], xmm0
0x1800022f5  movsd   xmm0, qword ptr [r15+88h]
0x1800022fe  movsd   [rbp+160h+var_150], xmm0
0x180002303  movaps  [rbp+160h+var_160], xmm1
0x180002307  test    rcx, rcx
0x18000230a  jz      short loc_180002319
0x18000230c  cmp     r9d, 0D8h
0x180002313  jnb     loc_180001F8C
0x180002319  mov     r14d, 0D8h
0x18000231f  jmp     loc_18000210A
0x180002324  test    r15, r15; jumptable 00000001800021EC cases 8,10
0x180002327  jz      def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x18000232d  cmp     dword ptr [rsp+260h+Event], 90h
0x180002335  jnz     def_1800021EC; jumptable 00000001800021EC default case, cases 1,3
0x18000233b  movups  xmm0, xmmword ptr [r15+8]
0x180002340  mov     eax, [r15]
0x180002343  movups  xmm1, xmmword ptr [r15+18h]
0x180002348  mov     rcx, [rsp+260h+var_200]
0x18000234d  mov     r9d, [rbp+160h+OutputLength]
0x180002354  movaps  [rbp+160h+var_1D8+8], xmm0
0x180002358  movaps  [rbp+160h+var_1C0], xmm1
0x18000235c  mov     dword ptr [rbp+160h+var_1D8], eax
0x18000235f  mov     eax, [r15+88h]
0x180002366  mov     dword ptr [rbp+160h+var_148], eax
0x180002369  mov     eax, [r15+8Ch]
0x180002370  mov     dword ptr [rbp+160h+var_148+4], eax
0x180002373  movups  xmm0, xmmword ptr [r15+28h]
0x180002378  movups  xmm1, xmmword ptr [r15+38h]
0x18000237d  movaps  [rbp+160h+var_1B0], xmm0
0x180002381  movaps  [rbp+160h+var_1A0], xmm1
0x180002385  movups  xmm0, xmmword ptr [r15+48h]
0x18000238a  movups  xmm1, xmmword ptr [r15+58h]
0x18000238f  movaps  [rbp+160h+var_190], xmm0
0x180002393  movaps  [rbp+160h+var_180], xmm1
0x180002397  movups  xmm0, xmmword ptr [r15+68h]
0x18000239c  movups  xmm1, xmmword ptr [r15+78h]
  ... truncated ...
```
