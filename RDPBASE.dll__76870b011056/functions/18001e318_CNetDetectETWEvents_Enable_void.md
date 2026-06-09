# CNetDetectETWEvents::Enable(void)

- ea: `0x18001e318`
- end: `0x18001e739`
- name: `?Enable@CNetDetectETWEvents@@QEAAJXZ`
- size: `1057`
- prototype: `__int64 __fastcall(CNetDetectETWEvents *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18001dc60`
- `0x18006fba0`

## callees

- `0x180019a80`
- `0x180019ab0`
- `0x18001e318`
- `0x18001e740`
- `0x180046a84`
- `0x1800711c8`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001e358`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001e358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e348`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001e348`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e337`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001e337`

## pseudocode

```c
__int64 __fastcall CNetDetectETWEvents::Enable(CNetDetectETWEvents *this)
{
  DWORD CurrentProcessId; // eax
  _QWORD *v3; // r14
  int GenericCounter; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  DWORD pSessionId; // [rsp+80h] [rbp+8h] BYREF

  *((_QWORD *)this + 13) = 1;
  *((_DWORD *)this + 28) = GetTickCount();
  pSessionId = 0;
  CurrentProcessId = GetCurrentProcessId();
  if ( !ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    pSessionId = -1;
  if ( *((_QWORD *)this + 7) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 56);
    *((_QWORD *)this + 7) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 56);
  }
  if ( *((_QWORD *)this + 8) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 64);
    *((_QWORD *)this + 8) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 64);
  }
  v3 = (_QWORD *)((char *)this + 80);
  if ( *((_QWORD *)this + 10) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 80);
    *v3 = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 80);
  }
  if ( *((_QWORD *)this + 9) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 72);
    *((_QWORD *)this + 9) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 72);
  }
  if ( *((_QWORD *)this + 11) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 88);
    *((_QWORD *)this + 11) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 88);
  }
  if ( *((_QWORD *)this + 12) )
  {
    TCntPtr<IXMLDOMNodeList>::SafeRelease((char *)this + 96);
    *((_QWORD *)this + 12) = 0;
    TCntPtr<ITSAsyncCallback>::SafeAddRef((char *)this + 96);
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::BandwidthChange",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 56);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 10;
    v8 = "Failed to initialize RDV::RDP::NetDetect::SteadyStateChange counter";
LABEL_36:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)WPP_3a244bda74cf3929f26bbd2137c5f8c0_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v8,
      GenericCounter);
    return (unsigned int)GenericCounter;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::LatencyResponse",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 64);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 11;
    v8 = "Failed to initialize RDV::RDP::NetDetect::LatencyResponse counter";
    goto LABEL_36;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::RttChange",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 80);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 12;
    v8 = "Failed to initialize RDV::RDP::NetDetect::RttChange counter";
    goto LABEL_36;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::LatencyPingRequest",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 72);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 13;
    v8 = "Failed to initialize RDV::RDP::NetDetect::LatencyPingRequest counter";
    goto LABEL_36;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::WindowChange",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 88);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 14;
    v8 = "Failed to initialize RDV::RDP::NetDetect::WindowChange counter";
    goto LABEL_36;
  }
  GenericCounter = RDPAPI_GetGenericCounter(
                     (unsigned int)L"RDV::RDP::NetDetect::BandwidthMeasurement",
                     pSessionId,
                     0,
                     -1,
                     4,
                     (__int64)this + 96);
  if ( GenericCounter < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)GenericCounter;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 15;
    v8 = "Failed to initialize RDV::RDP::NetDetect::BandwidthMeasurement counter";
    goto LABEL_36;
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)*v3 + 32LL))(*v3) )
    *((_DWORD *)this + 27) = 1;
  return (unsigned int)GenericCounter;
}

```

## disassembly

```asm
0x18001e318  push    rbx
0x18001e31a  push    rbp
0x18001e31b  push    rsi
0x18001e31c  push    rdi
0x18001e31d  push    r12
0x18001e31f  push    r13
0x18001e321  push    r14
0x18001e323  push    r15
0x18001e325  sub     rsp, 38h
0x18001e329  mov     rdi, rcx
0x18001e32c  mov     qword ptr [rcx+68h], 1
0x18001e334  xor     r13d, r13d
0x18001e337  call    cs:__imp_GetTickCount
0x18001e33d  mov     [rdi+70h], eax
0x18001e340  mov     [rsp+78h+pSessionId], r13d
0x18001e348  call    cs:__imp_GetCurrentProcessId
0x18001e34e  mov     ecx, eax; dwProcessId
0x18001e350  lea     rdx, [rsp+78h+pSessionId]; pSessionId
0x18001e358  call    cs:__imp_ProcessIdToSessionId
0x18001e35e  test    eax, eax
0x18001e360  jnz     short loc_18001E36D
0x18001e362  mov     [rsp+78h+pSessionId], 0FFFFFFFFh
0x18001e36d  lea     rbx, [rdi+38h]
0x18001e371  cmp     [rbx], r13
0x18001e374  jnz     loc_18001E5B3
0x18001e37a  lea     rsi, [rdi+40h]
0x18001e37e  cmp     [rsi], r13
0x18001e381  jnz     loc_18001E5CB
0x18001e387  lea     r14, [rdi+50h]
0x18001e38b  cmp     [r14], r13
0x18001e38e  jnz     loc_18001E5E3
0x18001e394  lea     r15, [rdi+48h]
0x18001e398  cmp     [r15], r13
0x18001e39b  jnz     loc_18001E5FB
0x18001e3a1  lea     rbp, [rdi+58h]
0x18001e3a5  cmp     [rbp+0], r13
0x18001e3a9  jnz     loc_18001E613
0x18001e3af  lea     r12, [rdi+60h]
0x18001e3b3  cmp     [r12], r13
0x18001e3b7  jnz     loc_18001E62C
0x18001e3bd  mov     edx, [rsp+78h+pSessionId]
0x18001e3c4  lea     rcx, aRdvRdpNetdetec; "RDV::RDP::NetDetect::BandwidthChange"
0x18001e3cb  mov     [rsp+78h+var_50], rbx
0x18001e3d0  or      r9d, 0FFFFFFFFh
0x18001e3d4  xor     r8d, r8d
0x18001e3d7  mov     dword ptr [rsp+78h+var_58], 4
0x18001e3df  call    RDPAPI_GetGenericCounter
0x18001e3e4  mov     ebx, eax
0x18001e3e6  test    eax, eax
0x18001e3e8  js      loc_18001E53D
0x18001e3ee  mov     edx, [rsp+78h+pSessionId]
0x18001e3f5  lea     rcx, aRdvRdpNetdetec_4; "RDV::RDP::NetDetect::LatencyResponse"
0x18001e3fc  mov     [rsp+78h+var_50], rsi
0x18001e401  xor     r8d, r8d
0x18001e404  or      esi, 0FFFFFFFFh
0x18001e407  mov     dword ptr [rsp+78h+var_58], 4
0x18001e40f  mov     r9d, esi
0x18001e412  call    RDPAPI_GetGenericCounter
0x18001e417  mov     ebx, eax
0x18001e419  test    eax, eax
0x18001e41b  js      loc_18001E67E
0x18001e421  mov     edx, [rsp+78h+pSessionId]
0x18001e428  lea     rcx, aRdvRdpNetdetec_1; "RDV::RDP::NetDetect::RttChange"
0x18001e42f  mov     [rsp+78h+var_50], r14
0x18001e434  mov     r9d, esi
0x18001e437  xor     r8d, r8d
0x18001e43a  mov     dword ptr [rsp+78h+var_58], 4
0x18001e442  call    RDPAPI_GetGenericCounter
0x18001e447  mov     ebx, eax
0x18001e449  test    eax, eax
0x18001e44b  js      loc_18001E508
0x18001e451  mov     edx, [rsp+78h+pSessionId]
0x18001e458  lea     rcx, aRdvRdpNetdetec_3; "RDV::RDP::NetDetect::LatencyPingRequest"
0x18001e45f  mov     [rsp+78h+var_50], r15
0x18001e464  mov     r9d, esi
0x18001e467  mov     r15d, 4
0x18001e46d  xor     r8d, r8d
0x18001e470  mov     dword ptr [rsp+78h+var_58], r15d
0x18001e475  call    RDPAPI_GetGenericCounter
0x18001e47a  mov     ebx, eax
0x18001e47c  test    eax, eax
0x18001e47e  js      loc_18001E6BC
0x18001e484  mov     edx, [rsp+78h+pSessionId]
0x18001e48b  lea     rcx, aRdvRdpNetdetec_0; "RDV::RDP::NetDetect::WindowChange"
0x18001e492  mov     [rsp+78h+var_50], rbp
0x18001e497  mov     r9d, esi
0x18001e49a  xor     r8d, r8d
0x18001e49d  mov     dword ptr [rsp+78h+var_58], r15d
0x18001e4a2  call    RDPAPI_GetGenericCounter
0x18001e4a7  mov     ebx, eax
0x18001e4a9  test    eax, eax
0x18001e4ab  js      loc_18001E572
0x18001e4b1  mov     edx, [rsp+78h+pSessionId]
0x18001e4b8  lea     rcx, aRdvRdpNetdetec_2; "RDV::RDP::NetDetect::BandwidthMeasureme"...
0x18001e4bf  mov     [rsp+78h+var_50], r12
0x18001e4c4  mov     r9d, esi
0x18001e4c7  xor     r8d, r8d
0x18001e4ca  mov     dword ptr [rsp+78h+var_58], r15d
0x18001e4cf  call    RDPAPI_GetGenericCounter
0x18001e4d4  mov     ebx, eax
0x18001e4d6  test    eax, eax
0x18001e4d8  js      loc_18001E6FD
0x18001e4de  mov     rcx, [r14]
0x18001e4e1  mov     rax, [rcx]
0x18001e4e4  mov     rax, [rax+20h]
0x18001e4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4ed  test    eax, eax
0x18001e4ef  jnz     loc_18001E72D
0x18001e4f5  mov     eax, ebx
0x18001e4f7  add     rsp, 38h
0x18001e4fb  pop     r15
0x18001e4fd  pop     r14
0x18001e4ff  pop     r13
0x18001e501  pop     r12
0x18001e503  pop     rdi
0x18001e504  pop     rsi
0x18001e505  pop     rbp
0x18001e506  pop     rbx
0x18001e507  retn
0x18001e508  mov     rax, cs:WPP_GLOBAL_Control
0x18001e50f  lea     rcx, WPP_GLOBAL_Control
0x18001e516  cmp     rax, rcx
0x18001e519  jz      short loc_18001E4F5
0x18001e51b  test    byte ptr [rax+1Ch], 8
0x18001e51f  jz      short loc_18001E4F5
0x18001e521  cmp     byte ptr [rax+19h], 2
0x18001e525  jb      short loc_18001E4F5
0x18001e527  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e52c  mov     edx, 0Ch
0x18001e531  lea     rcx, aFailedToInitia_26; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e538  jmp     loc_18001E656
0x18001e53d  mov     rax, cs:WPP_GLOBAL_Control
0x18001e544  lea     rcx, WPP_GLOBAL_Control
0x18001e54b  cmp     rax, rcx
0x18001e54e  jz      short loc_18001E4F5
0x18001e550  test    byte ptr [rax+1Ch], 8
0x18001e554  jz      short loc_18001E4F5
0x18001e556  cmp     byte ptr [rax+19h], 2
0x18001e55a  jb      short loc_18001E4F5
0x18001e55c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e561  mov     edx, 0Ah
0x18001e566  lea     rcx, aFailedToInitia_69; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e56d  jmp     loc_18001E656
0x18001e572  mov     rax, cs:WPP_GLOBAL_Control
0x18001e579  lea     rcx, WPP_GLOBAL_Control
0x18001e580  cmp     rax, rcx
0x18001e583  jz      loc_18001E4F5
0x18001e589  test    byte ptr [rax+1Ch], 8
0x18001e58d  jz      loc_18001E4F5
0x18001e593  cmp     byte ptr [rax+19h], 2
0x18001e597  jb      loc_18001E4F5
0x18001e59d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e5a2  mov     edx, 0Eh
0x18001e5a7  lea     rcx, aFailedToInitia_1; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e5ae  jmp     loc_18001E656
0x18001e5b3  mov     rcx, rbx; void *
0x18001e5b6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e5bb  mov     rcx, rbx
0x18001e5be  mov     [rbx], r13
0x18001e5c1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e5c6  jmp     loc_18001E37A
0x18001e5cb  mov     rcx, rsi; void *
0x18001e5ce  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e5d3  mov     rcx, rsi
0x18001e5d6  mov     [rsi], r13
0x18001e5d9  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e5de  jmp     loc_18001E387
0x18001e5e3  mov     rcx, r14; void *
0x18001e5e6  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e5eb  mov     rcx, r14
0x18001e5ee  mov     [r14], r13
0x18001e5f1  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e5f6  jmp     loc_18001E394
0x18001e5fb  mov     rcx, r15; void *
0x18001e5fe  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e603  mov     rcx, r15
0x18001e606  mov     [r15], r13
0x18001e609  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e60e  jmp     loc_18001E3A1
0x18001e613  mov     rcx, rbp; void *
0x18001e616  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e61b  mov     rcx, rbp
0x18001e61e  mov     [rbp+0], r13
0x18001e622  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e627  jmp     loc_18001E3AF
0x18001e62c  mov     rcx, r12; void *
0x18001e62f  call    ?SafeRelease@?$TCntPtr@UIXMLDOMNodeList@@@@AEAAXXZ; TCntPtr<IXMLDOMNodeList>::SafeRelease(void)
0x18001e634  mov     rcx, r12
0x18001e637  mov     [r12], r13
0x18001e63b  call    ?SafeAddRef@?$TCntPtr@VITSAsyncCallback@@@@AEAAXXZ; TCntPtr<ITSAsyncCallback>::SafeAddRef(void)
0x18001e640  jmp     loc_18001E3BD
0x18001e645  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e64a  mov     edx, 0Fh
0x18001e64f  lea     rcx, aFailedToInitia_75; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e656  mov     dword ptr [rsp+78h+var_50], ebx
0x18001e65a  lea     r8, WPP_3a244bda74cf3929f26bbd2137c5f8c0_Traceguids
0x18001e661  mov     [rsp+78h+var_58], rcx
0x18001e666  mov     r9d, eax
0x18001e669  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e670  mov     rcx, [rcx+10h]
0x18001e674  call    WPP_SF_DsD
0x18001e679  jmp     loc_18001E4F5
0x18001e67e  mov     rax, cs:WPP_GLOBAL_Control
0x18001e685  lea     rcx, WPP_GLOBAL_Control
0x18001e68c  cmp     rax, rcx
0x18001e68f  jz      loc_18001E4F5
0x18001e695  test    byte ptr [rax+1Ch], 8
0x18001e699  jz      loc_18001E4F5
0x18001e69f  cmp     byte ptr [rax+19h], 2
0x18001e6a3  jb      loc_18001E4F5
0x18001e6a9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e6ae  mov     edx, 0Bh
0x18001e6b3  lea     rcx, aFailedToInitia_46; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e6ba  jmp     short loc_18001E656
0x18001e6bc  mov     rax, cs:WPP_GLOBAL_Control
0x18001e6c3  lea     rcx, WPP_GLOBAL_Control
0x18001e6ca  cmp     rax, rcx
0x18001e6cd  jz      loc_18001E4F5
0x18001e6d3  test    byte ptr [rax+1Ch], 8
0x18001e6d7  jz      loc_18001E4F5
0x18001e6dd  cmp     byte ptr [rax+19h], 2
0x18001e6e1  jb      loc_18001E4F5
0x18001e6e7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18001e6ec  mov     edx, 0Dh
0x18001e6f1  lea     rcx, aFailedToInitia_28; "Failed to initialize RDV::RDP::NetDetec"...
0x18001e6f8  jmp     loc_18001E656
0x18001e6fd  mov     rax, cs:WPP_GLOBAL_Control
0x18001e704  lea     rcx, WPP_GLOBAL_Control
0x18001e70b  cmp     rax, rcx
0x18001e70e  jz      loc_18001E4F5
0x18001e714  test    byte ptr [rax+1Ch], 8
0x18001e718  jz      loc_18001E4F5
0x18001e71e  cmp     byte ptr [rax+19h], 2
0x18001e722  jb      loc_18001E4F5
0x18001e728  jmp     loc_18001E645
0x18001e72d  mov     dword ptr [rdi+6Ch], 1
0x18001e734  jmp     loc_18001E4F5
```
