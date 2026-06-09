# HttpSendHttpResponse

- ea: `0x180002610`
- end: `0x180002817`
- name: `HttpSendHttpResponse`
- size: `519`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, HTTP_REQUEST_ID RequestId, ULONG Flags, PHTTP_RESPONSE HttpResponse, PHTTP_CACHE_POLICY CachePolicy, PULONG BytesSent, PVOID Reserved1, ULONG Reserved2, LPOVERLAPPED Overlapped, PHTTP_LOG_DATA LogData)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180002610`
- `0x1800029a0`
- `0x180002b40`
- `0x18000b010`
- `0x18000b424`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002765`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002765`

## pseudocode

```c
ULONG __stdcall HttpSendHttpResponse(
        HANDLE RequestQueueHandle,
        HTTP_REQUEST_ID RequestId,
        ULONG Flags,
        PHTTP_RESPONSE HttpResponse,
        PHTTP_CACHE_POLICY CachePolicy,
        PULONG BytesSent,
        PVOID Reserved1,
        ULONG Reserved2,
        LPOVERLAPPED Overlapped,
        PHTTP_LOG_DATA LogData)
{
  ULONG v11; // r15d
  int v15; // eax
  __int64 v16; // r9
  int v17; // eax
  ULONG v18; // ebx
  __int64 v19; // rcx
  __int128 InputBuffer; // [rsp+40h] [rbp-88h] BYREF
  __int128 v21; // [rsp+50h] [rbp-78h]
  __int128 v22; // [rsp+60h] [rbp-68h]
  PHTTP_LOG_DATA v23; // [rsp+70h] [rbp-58h]

  InputBuffer = 0;
  v23 = 0;
  v21 = 0;
  v11 = Flags;
  v22 = 0;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_ILqd(
      RequestQueueHandle,
      12,
      Flags,
      RequestId,
      Flags,
      HttpResponse->pEntityChunks,
      HttpResponse->EntityChunkCount);
  if ( BytesSent )
    *BytesSent = 0;
  if ( Reserved1 || Reserved2 )
    return 87;
  WORD4(InputBuffer) = HttpResponse->EntityChunkCount;
  *(_QWORD *)&v21 = HttpResponse->pEntityChunks;
  *(_QWORD *)&InputBuffer = HttpResponse;
  *(_QWORD *)&v22 = RequestId;
  DWORD2(v22) = v11;
  if ( CachePolicy )
  {
    *((struct _HTTP_CACHE_POLICY *)&v21 + 1) = *CachePolicy;
    v15 = HIDWORD(v21);
    v16 = DWORD2(v21);
  }
  else
  {
    v15 = 0;
    *((_QWORD *)&v21 + 1) = 0;
    v16 = 0;
  }
  if ( (byte_1800126A3 & 4) != 0 )
  {
    WPP_SF_dL(RequestQueueHandle, 13, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, v16, v15);
    v11 = DWORD2(v22);
  }
  if ( !LogData )
    goto LABEL_13;
  if ( LogData->Type )
    return 87;
  v23 = LogData;
LABEL_13:
  if ( Overlapped )
  {
    v17 = HttpApiOverlappedDeviceControl(
            RequestQueueHandle,
            Overlapped,
            0x12403Fu,
            &InputBuffer,
            0x38u,
            0,
            0,
            (__int64)BytesSent);
  }
  else
  {
    DWORD2(v22) = v11 | 0x80;
    v17 = HttpApiSynchronousDeviceControl(RequestQueueHandle, 0x12403Fu, &InputBuffer, 0x38u, 0, 0, (__int64)BytesSent);
  }
  v18 = v17;
  v19 = 3LL * (((unsigned __int8)_InterlockedExchangeAdd(&dword_180013008, 1u) + 1) & 0x1F);
  g_ApiCallInfos[v19 + 192] = v17;
  GetSystemTimeAsFileTime((LPFILETIME)&g_ApiCallInfos[v19 + 193]);
  return v18;
}

```

## disassembly

```asm
0x180002610  push    rbx
0x180002612  push    rbp
0x180002613  push    rsi
0x180002614  push    rdi
0x180002615  push    r12
0x180002617  push    r13
0x180002619  push    r14
0x18000261b  push    r15
0x18000261d  sub     rsp, 88h
0x180002624  xorps   xmm0, xmm0
0x180002627  xor     eax, eax
0x180002629  movups  [rsp+0C8h+InputBuffer], xmm0
0x18000262e  mov     [rsp+0C8h+var_58], rax
0x180002633  mov     rbp, r9
0x180002636  movups  [rsp+0C8h+var_78], xmm0
0x18000263b  mov     r15d, r8d
0x18000263e  mov     r14, rdx
0x180002641  movups  [rsp+0C8h+var_68], xmm0
0x180002646  mov     r12, rcx
0x180002649  test    cs:byte_1800126A3, 4
0x180002650  jnz     loc_1800027C9
0x180002656  mov     rbx, [rsp+0C8h+BytesSent]
0x18000265e  xor     r13d, r13d
0x180002661  test    rbx, rbx
0x180002664  jz      short loc_180002669
0x180002666  mov     [rbx], r13d
0x180002669  cmp     [rsp+0C8h+Reserved1], r13
0x180002671  jz      short loc_18000268C
0x180002673  mov     eax, 57h ; 'W'
0x180002678  add     rsp, 88h
0x18000267f  pop     r15
0x180002681  pop     r14
0x180002683  pop     r13
0x180002685  pop     r12
0x180002687  pop     rdi
0x180002688  pop     rsi
0x180002689  pop     rbp
0x18000268a  pop     rbx
0x18000268b  retn
0x18000268c  cmp     [rsp+0C8h+Reserved2], r13d
0x180002694  jnz     short loc_180002673
0x180002696  movzx   eax, word ptr [rbp+218h]
0x18000269d  mov     word ptr [rsp+0C8h+InputBuffer+8], ax
0x1800026a2  mov     rax, [rbp+220h]
0x1800026a9  mov     qword ptr [rsp+0C8h+var_78], rax
0x1800026ae  mov     rax, [rsp+0C8h+CachePolicy]
0x1800026b6  mov     qword ptr [rsp+0C8h+InputBuffer], rbp
0x1800026bb  mov     qword ptr [rsp+0C8h+var_68], r14
0x1800026c0  mov     dword ptr [rsp+0C8h+var_68+8], r15d
0x1800026c5  test    rax, rax
0x1800026c8  jz      loc_1800027B5
0x1800026ce  mov     rax, [rax]
0x1800026d1  mov     qword ptr [rsp+0C8h+var_78+8], rax
0x1800026d6  mov     eax, dword ptr [rsp+0C8h+var_78+0Ch]
0x1800026da  mov     r9d, dword ptr [rsp+0C8h+var_78+8]
0x1800026df  test    cs:byte_1800126A3, 4
0x1800026e6  jnz     loc_1800027F8
0x1800026ec  mov     rax, [rsp+0C8h+LogData]
0x1800026f4  test    rax, rax
0x1800026f7  jnz     loc_1800027A2
0x1800026fd  mov     rdx, [rsp+0C8h+Overlapped]; ApcContext
0x180002705  mov     rcx, r12; FileHandle
0x180002708  test    rdx, rdx
0x18000270b  jz      short loc_180002772
0x18000270d  mov     [rsp+0C8h+var_90], rbx; __int64
0x180002712  lea     r9, [rsp+0C8h+InputBuffer]; InputBuffer
0x180002717  mov     [rsp+0C8h+var_98], r13d; ULONG
0x18000271c  mov     r8d, 12403Fh; IoControlCode
0x180002722  mov     [rsp+0C8h+var_A0], r13; PVOID
0x180002727  mov     [rsp+0C8h+var_A8], 38h ; '8'; ULONG
0x18000272f  call    HttpApiOverlappedDeviceControl
0x180002734  mov     ebx, eax
0x180002736  mov     ecx, 1
0x18000273b  lock xadd cs:dword_180013008, ecx
0x180002743  inc     ecx
0x180002745  lea     rax, g_ApiCallInfos
0x18000274c  and     ecx, 1Fh
0x18000274f  lea     rcx, [rcx+rcx*2]
0x180002753  mov     [rax+rcx*4+300h], ebx
0x18000275a  lea     rcx, [rcx+0C1h]
0x180002761  lea     rcx, [rax+rcx*4]; lpSystemTimeAsFileTime
0x180002765  call    cs:__imp_GetSystemTimeAsFileTime
0x18000276b  mov     eax, ebx
0x18000276d  jmp     loc_180002678
0x180002772  bts     r15d, 7
0x180002777  mov     qword ptr [rsp+0C8h+var_98], rbx; __int64
0x18000277c  mov     dword ptr [rsp+0C8h+var_A0], r13d; ULONG
0x180002781  lea     r8, [rsp+0C8h+InputBuffer]; InputBuffer
0x180002786  mov     r9d, 38h ; '8'; InputBufferLength
0x18000278c  mov     dword ptr [rsp+0C8h+var_68+8], r15d
0x180002791  mov     edx, 12403Fh; IoControlCode
0x180002796  mov     qword ptr [rsp+0C8h+var_A8], r13; PVOID
0x18000279b  call    HttpApiSynchronousDeviceControl
0x1800027a0  jmp     short loc_180002734
0x1800027a2  cmp     [rax], r13d
0x1800027a5  jnz     loc_180002673
0x1800027ab  mov     [rsp+0C8h+var_58], rax
0x1800027b0  jmp     loc_1800026FD
0x1800027b5  mov     eax, r13d
0x1800027b8  mov     dword ptr [rsp+0C8h+var_78+8], r13d
0x1800027bd  mov     dword ptr [rsp+0C8h+var_78+0Ch], eax
0x1800027c1  mov     r9d, r13d
0x1800027c4  jmp     loc_1800026DF
0x1800027c9  movzx   eax, word ptr [r9+218h]
0x1800027d1  mov     edx, 0Ch
0x1800027d6  mov     [rsp+0C8h+var_98], eax
0x1800027da  mov     rax, [r9+220h]
0x1800027e1  mov     r9, r14
0x1800027e4  mov     [rsp+0C8h+var_A0], rax
0x1800027e9  mov     [rsp+0C8h+var_A8], r15d
0x1800027ee  call    WPP_SF_ILqd
0x1800027f3  jmp     loc_180002656
0x1800027f8  mov     edx, 0Dh
0x1800027fd  mov     [rsp+0C8h+var_A8], eax
0x180002801  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x180002808  call    WPP_SF_dL
0x18000280d  mov     r15d, dword ptr [rsp+0C8h+var_68+8]
0x180002812  jmp     loc_1800026EC
```
