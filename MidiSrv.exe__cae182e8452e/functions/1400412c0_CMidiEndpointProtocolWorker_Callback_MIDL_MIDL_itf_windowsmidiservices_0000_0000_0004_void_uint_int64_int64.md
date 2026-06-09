# CMidiEndpointProtocolWorker::Callback(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64,__int64)

- ea: `0x1400412c0`
- end: `0x140041669`
- name: `?Callback@CMidiEndpointProtocolWorker@@UEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J2@Z`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140001ce8`
- `0x14000611c`
- `0x140008b34`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x14004125c`
- `0x1400412c0`
- `0x140041670`
- `0x140041728`
- `0x140042194`
- `0x14004225c`
- `0x14004249c`
- `0x1400426b4`
- `0x1400428c4`
- `0x140042d08`
- `0x140042f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400412f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140041311`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1400412f4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140041311`

## string_xrefs

- `0x140041636`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140041346`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x14004136e`: `avcore\midi2\service\exe\midiendpointprotocolworker.cpp`
- `0x140041375`: `CMidiEndpointProtocolWorker::Callback`

## pseudocode

```c
__int64 __fastcall CMidiEndpointProtocolWorker::Callback(_QWORD *a1, __int64 a2, __m128i *a3, unsigned int a4)
{
  void *v4; // rbx
  unsigned __int64 v7; // r14
  DWORD v8; // eax
  const char *v9; // r9
  __m128i *v11; // r15
  _DWORD *v12; // rcx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // r14
  _QWORD *v16; // rax
  unsigned int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  int v24; // r14d
  __int64 v25; // rdx
  int v26; // eax
  _DWORD *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // [rsp+20h] [rbp-60h]
  const char *v31; // [rsp+40h] [rbp-40h] BYREF
  _QWORD *v32; // [rsp+48h] [rbp-38h] BYREF
  __m128i v33; // [rsp+50h] [rbp-30h] BYREF
  _QWORD pExceptionObject[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  _QWORD *v36; // [rsp+B0h] [rbp+30h] BYREF

  v4 = (void *)a1[18];
  v7 = a4;
  v8 = WaitForSingleObjectEx(v4, 0, 0);
  if ( v8 == 258 )
  {
    if ( a3 )
    {
      pExceptionObject[1] = a3;
      v11 = (__m128i *)((char *)a3 + 4 * (v7 >> 2));
      pExceptionObject[2] = v11;
      while ( 1 )
      {
        pExceptionObject[0] = a3;
        if ( a3 >= v11 )
          return 0;
        if ( WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject) == 4 )
        {
          if ( a3 >= v11 )
          {
            std::format_error::format_error((std::format_error *)pExceptionObject, "Invalid UMP. Past end of buffer.");
            throw (std::runtime_error *)pExceptionObject;
          }
          if ( (unsigned __int32)a3->m128i_i32[0] >> 28 == 15 )
          {
            v33 = 0u;
            v12 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
            if ( *v12 <= 4u )
            {
              v15 = a1 + 7;
            }
            else
            {
              v15 = a1 + 7;
              if ( a1[10] <= 7u )
                v16 = a1 + 7;
              else
                v16 = (_QWORD *)*v15;
              v36 = v16;
              v32 = a1;
              v31 = (const char *)L"Stream message received.";
              v33.m128i_i64[0] = (__int64)"CMidiEndpointProtocolWorker::Callback";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                (__int64)v12,
                (__int64)byte_14008C395,
                v13,
                v14,
                &v33,
                (__int64)&v32,
                &v31,
                &v36);
            }
            if ( 4
               * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject) == 16 )
            {
              v17 = _mm_cvtsi128_si32(*a3);
              v33 = *a3;
              v18 = (HIWORD(v17) & 0x3FF) - 1;
              if ( v18 )
              {
                v19 = v18 - 1;
                if ( v19 )
                {
                  v20 = v19 - 1;
                  if ( v20 )
                  {
                    v21 = v20 - 1;
                    if ( v21 )
                    {
                      v22 = v21 - 2;
                      if ( v22 )
                      {
                        v23 = v22 - 11;
                        if ( v23 )
                        {
                          if ( v23 == 1 )
                          {
                            v24 = CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage(
                                    (CMidiEndpointProtocolWorker *)a1,
                                    (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                            if ( v24 < 0 )
                            {
                              v25 = 566;
LABEL_48:
                              wil::details::in1diag3::Return_Hr(
                                retaddr,
                                (void *)v25,
                                (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
                                (const char *)(unsigned int)v24,
                                v30);
                              return (unsigned int)v24;
                            }
                          }
                        }
                        else
                        {
                          v24 = CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage(
                                  (CMidiEndpointProtocolWorker *)a1,
                                  (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                          if ( v24 < 0 )
                          {
                            v25 = 562;
                            goto LABEL_48;
                          }
                        }
                      }
                      else
                      {
                        v24 = CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest(
                                (CMidiEndpointProtocolWorker *)a1,
                                (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                        if ( v24 < 0 )
                        {
                          v25 = 558;
                          goto LABEL_48;
                        }
                      }
                    }
                    else
                    {
                      v24 = CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage(
                              (CMidiEndpointProtocolWorker *)a1,
                              (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                      if ( v24 < 0 )
                      {
                        v25 = 570;
                        goto LABEL_48;
                      }
                    }
                  }
                  else
                  {
                    v24 = CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage(
                            (CMidiEndpointProtocolWorker *)a1,
                            (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                    if ( v24 < 0 )
                    {
                      v25 = 574;
                      goto LABEL_48;
                    }
                  }
                }
                else
                {
                  v24 = CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage(
                          (CMidiEndpointProtocolWorker *)a1,
                          (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                  if ( v24 < 0 )
                  {
                    v25 = 554;
                    goto LABEL_48;
                  }
                }
              }
              else
              {
                v24 = CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage(
                        (CMidiEndpointProtocolWorker *)a1,
                        (struct WindowsMidiServicesInternal::PackedUmp128 *)&v33);
                if ( v24 < 0 )
                {
                  v25 = 550;
                  goto LABEL_48;
                }
              }
              v26 = CMidiEndpointProtocolWorker::CheckIfDiscoveryComplete((CMidiEndpointProtocolWorker *)a1);
              if ( v26 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x247,
                  (int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
                  (const char *)(unsigned int)v26);
            }
            else
            {
              v27 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
              if ( *v27 > 2u )
              {
                if ( a1[10] > 7u )
                  v15 = (_QWORD *)*v15;
                v36 = v15;
                v33.m128i_i64[0] = (__int64)L"Failed to parse stream message into UMP128.";
                v32 = a1;
                v31 = "CMidiEndpointProtocolWorker::Callback";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                  (__int64)v27,
                  (__int64)&dword_14008BE7C,
                  v28,
                  v29,
                  &v31,
                  (__int64)&v32,
                  &v33,
                  &v36);
              }
            }
          }
        }
        if ( a3 == v11 )
        {
          std::format_error::format_error((std::format_error *)pExceptionObject, "Invalid UMP. Past end of buffer.");
          throw (std::runtime_error *)pExceptionObject;
        }
        a3 = (__m128i *)((char *)a3
                       + 4
                       * WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount((WindowsMidiServicesInternal::UmpBufferIterator *)pExceptionObject));
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x202,
      (unsigned int)"avcore\\midi2\\service\\exe\\midiendpointprotocolworker.cpp",
      (const char *)0x80070057LL,
      v30);
    return 2147942487LL;
  }
  else
  {
    if ( v8 || WaitForSingleObjectEx(v4, 0, 0) )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0xB07,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    return 0;
  }
}

```

## disassembly

```asm
0x1400412c0  mov     [rsp-28h+arg_8], rbx
0x1400412c5  mov     [rsp-28h+arg_10], rsi
0x1400412ca  push    rbp
0x1400412cb  push    rdi
0x1400412cc  push    r12
0x1400412ce  push    r14
0x1400412d0  push    r15
0x1400412d2  mov     rbp, rsp
0x1400412d5  sub     rsp, 80h
0x1400412dc  mov     rbx, [rcx+90h]
0x1400412e3  mov     rsi, r8
0x1400412e6  mov     rdi, rcx
0x1400412e9  mov     r14d, r9d
0x1400412ec  mov     rcx, rbx; hHandle
0x1400412ef  xor     r8d, r8d; bAlertable
0x1400412f2  xor     edx, edx; dwMilliseconds
0x1400412f4  call    cs:__imp_WaitForSingleObjectEx
0x1400412fa  cmp     eax, 102h
0x1400412ff  jz      short loc_14004133D
0x140041301  test    eax, eax
0x140041303  jnz     loc_140041632
0x140041309  xor     r8d, r8d; bAlertable
0x14004130c  xor     edx, edx; dwMilliseconds
0x14004130e  mov     rcx, rbx; hHandle
0x140041311  call    cs:__imp_WaitForSingleObjectEx
0x140041317  test    eax, eax
0x140041319  jnz     loc_140041632
0x14004131f  xor     eax, eax
0x140041321  lea     r11, [rsp+80h+var_s0]
0x140041329  mov     rbx, [r11+38h]
0x14004132d  mov     rsi, [r11+40h]
0x140041331  mov     rsp, r11
0x140041334  pop     r15
0x140041336  pop     r14
0x140041338  pop     r12
0x14004133a  pop     rdi
0x14004133b  pop     rbp
0x14004133c  retn
0x14004133d  test    rsi, rsi
0x140041340  jnz     short loc_140041363
0x140041342  mov     rcx, [rbp+28h]; this
0x140041346  lea     r8, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x14004134d  mov     edi, 80070057h
0x140041352  mov     edx, 202h; void *
0x140041357  mov     r9d, edi; char *
0x14004135a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004135f  mov     eax, edi
0x140041361  jmp     short loc_140041321
0x140041363  mov     rax, r14
0x140041366  mov     [rbp+var_18], rsi
0x14004136a  shr     rax, 2
0x14004136e  lea     rbx, aAvcoreMidi2Ser; "avcore\\midi2\\service\\exe\\midiendpoi"...
0x140041375  lea     r12, aCmidiendpointp_11; "CMidiEndpointProtocolWorker::Callback"
0x14004137c  lea     r15, [rsi+rax*4]
0x140041380  mov     [rbp+var_10], r15
0x140041384  mov     [rbp+pExceptionObject], rsi
0x140041388  cmp     rsi, r15
0x14004138b  jnb     short loc_14004131F
0x14004138d  lea     rcx, [rbp+pExceptionObject]; this
0x140041391  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x140041396  cmp     al, 4
0x140041398  jnz     loc_1400415DF
0x14004139e  cmp     rsi, r15
0x1400413a1  jnb     loc_140041648
0x1400413a7  mov     eax, [rsi]
0x1400413a9  shr     eax, 1Ch
0x1400413ac  cmp     al, 0Fh
0x1400413ae  jnz     loc_1400415DF
0x1400413b4  mov     qword ptr [rbp+var_30], 0
0x1400413bc  mov     qword ptr [rbp+var_30+8], 0
0x1400413c4  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400413c9  mov     rcx, [rax+8]
0x1400413cd  mov     eax, [rcx]
0x1400413cf  cmp     eax, 4
0x1400413d2  jbe     short loc_140041430
0x1400413d4  cmp     qword ptr [rdi+50h], 7
0x1400413d9  lea     r14, [rdi+38h]
0x1400413dd  jbe     short loc_1400413E4
0x1400413df  mov     rax, [r14]
0x1400413e2  jmp     short loc_1400413E7
0x1400413e4  mov     rax, r14
0x1400413e7  mov     [rbp+arg_0], rax
0x1400413eb  lea     rdx, byte_14008C395
0x1400413f2  lea     rax, aStreamMessageR; "Stream message received."
0x1400413f9  mov     [rbp+var_38], rdi
0x1400413fd  mov     [rbp+var_40], rax
0x140041401  lea     rax, [rbp+arg_0]
0x140041405  mov     [rsp+80h+var_48], rax
0x14004140a  lea     rax, [rbp+var_40]
0x14004140e  mov     [rsp+80h+var_50], rax
0x140041413  lea     rax, [rbp+var_38]
0x140041417  mov     [rsp+80h+var_58], rax
0x14004141c  lea     rax, [rbp+var_30]
0x140041420  mov     [rsp+80h+var_60], rax
0x140041425  mov     qword ptr [rbp+var_30], r12
0x140041429  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14004142e  jmp     short loc_140041434
0x140041430  lea     r14, [rdi+38h]
0x140041434  lea     rcx, [rbp+pExceptionObject]; this
0x140041438  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x14004143d  shl     al, 2
0x140041440  cmp     al, 10h
0x140041442  jnz     loc_14004157E
0x140041448  movups  xmm0, xmmword ptr [rsi]
0x14004144b  movd    ecx, xmm0
0x14004144f  movups  [rbp+var_30], xmm0
0x140041453  shr     ecx, 10h
0x140041456  and     ecx, 3FFh
0x14004145c  sub     ecx, 1
0x14004145f  jz      loc_140041545
0x140041465  sub     ecx, 1
0x140041468  jz      loc_140041528
0x14004146e  sub     ecx, 1
0x140041471  jz      loc_14004150B
0x140041477  sub     ecx, 1
0x14004147a  jz      short loc_1400414EE
0x14004147c  sub     ecx, 2
0x14004147f  jz      short loc_1400414D1
0x140041481  sub     ecx, 0Bh
0x140041484  jz      short loc_1400414B0
0x140041486  cmp     ecx, 1
0x140041489  jnz     loc_14004155C
0x14004148f  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x140041493  mov     rcx, rdi; this
0x140041496  call    ?ProcessFunctionBlockNameNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessFunctionBlockNameNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x14004149b  mov     r14d, eax
0x14004149e  test    eax, eax
0x1400414a0  jns     loc_14004155C
0x1400414a6  mov     edx, 236h
0x1400414ab  jmp     loc_1400415FE
0x1400414b0  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x1400414b4  mov     rcx, rdi; this
0x1400414b7  call    ?ProcessFunctionBlockInfoNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessFunctionBlockInfoNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x1400414bc  mov     r14d, eax
0x1400414bf  test    eax, eax
0x1400414c1  jns     loc_14004155C
0x1400414c7  mov     edx, 232h
0x1400414cc  jmp     loc_1400415FE
0x1400414d1  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x1400414d5  mov     rcx, rdi; this
0x1400414d8  call    ?ProcessStreamConfigurationRequest@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessStreamConfigurationRequest(WindowsMidiServicesInternal::PackedUmp128 &)
0x1400414dd  mov     r14d, eax
0x1400414e0  test    eax, eax
0x1400414e2  jns     short loc_14004155C
0x1400414e4  mov     edx, 22Eh
0x1400414e9  jmp     loc_1400415FE
0x1400414ee  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x1400414f2  mov     rcx, rdi; this
0x1400414f5  call    ?ProcessProductInstanceIdNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessProductInstanceIdNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x1400414fa  mov     r14d, eax
0x1400414fd  test    eax, eax
0x1400414ff  jns     short loc_14004155C
0x140041501  mov     edx, 23Ah
0x140041506  jmp     loc_1400415FE
0x14004150b  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x14004150f  mov     rcx, rdi; this
0x140041512  call    ?ProcessEndpointNameNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessEndpointNameNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140041517  mov     r14d, eax
0x14004151a  test    eax, eax
0x14004151c  jns     short loc_14004155C
0x14004151e  mov     edx, 23Eh
0x140041523  jmp     loc_1400415FE
0x140041528  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x14004152c  mov     rcx, rdi; this
0x14004152f  call    ?ProcessDeviceIdentityNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessDeviceIdentityNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140041534  mov     r14d, eax
0x140041537  test    eax, eax
0x140041539  jns     short loc_14004155C
0x14004153b  mov     edx, 22Ah
0x140041540  jmp     loc_1400415FE
0x140041545  lea     rdx, [rbp+var_30]; struct WindowsMidiServicesInternal::PackedUmp128 *
0x140041549  mov     rcx, rdi; this
0x14004154c  call    ?ProcessEndpointInfoNotificationMessage@CMidiEndpointProtocolWorker@@AEAAJAEAUPackedUmp128@WindowsMidiServicesInternal@@@Z; CMidiEndpointProtocolWorker::ProcessEndpointInfoNotificationMessage(WindowsMidiServicesInternal::PackedUmp128 &)
0x140041551  mov     r14d, eax
0x140041554  test    eax, eax
0x140041556  js      loc_1400415F9
0x14004155c  mov     rcx, rdi; this
0x14004155f  call    ?CheckIfDiscoveryComplete@CMidiEndpointProtocolWorker@@AEAAJXZ; CMidiEndpointProtocolWorker::CheckIfDiscoveryComplete(void)
0x140041564  test    eax, eax
0x140041566  jns     short loc_1400415DF
0x140041568  mov     rcx, [rbp+28h]; this
0x14004156c  mov     r9d, eax; char *
0x14004156f  mov     r8, rbx; unsigned int
0x140041572  mov     edx, 247h; void *
0x140041577  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14004157c  jmp     short loc_1400415DF
0x14004157e  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140041583  mov     rcx, [rax+8]
0x140041587  mov     eax, [rcx]
0x140041589  cmp     eax, 2
0x14004158c  jbe     short loc_1400415DF
0x14004158e  cmp     qword ptr [rdi+50h], 7
0x140041593  jbe     short loc_140041598
0x140041595  mov     r14, [r14]
0x140041598  lea     rax, aFailedToParseS; "Failed to parse stream message into UMP"...
0x14004159f  mov     [rbp+arg_0], r14
0x1400415a3  mov     qword ptr [rbp+var_30], rax
0x1400415a7  lea     rdx, dword_14008BE7C
0x1400415ae  lea     rax, [rbp+arg_0]
0x1400415b2  mov     [rbp+var_38], rdi
0x1400415b6  mov     [rsp+80h+var_48], rax
0x1400415bb  lea     rax, [rbp+var_30]
0x1400415bf  mov     [rsp+80h+var_50], rax
0x1400415c4  lea     rax, [rbp+var_38]
0x1400415c8  mov     [rsp+80h+var_58], rax
0x1400415cd  lea     rax, [rbp+var_40]
0x1400415d1  mov     [rsp+80h+var_60], rax
0x1400415d6  mov     [rbp+var_40], r12
0x1400415da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1400415df  lea     rcx, [rbp+pExceptionObject]; this
0x1400415e3  cmp     rsi, r15
0x1400415e6  jz      short loc_140041615
0x1400415e8  call    ?CurrentMessageWordCount@UmpBufferIterator@WindowsMidiServicesInternal@@QEBAEXZ; WindowsMidiServicesInternal::UmpBufferIterator::CurrentMessageWordCount(void)
0x1400415ed  movzx   eax, al
0x1400415f0  lea     rsi, [rsi+rax*4]
0x1400415f4  jmp     loc_140041384
0x1400415f9  mov     edx, 226h; void *
0x1400415fe  mov     rcx, [rbp+28h]; this
0x140041602  mov     r9d, r14d; char *
0x140041605  mov     r8, rbx; unsigned int
0x140041608  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14004160d  mov     eax, r14d
0x140041610  jmp     loc_140041321
0x140041615  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x14004161c  call    ??0format_error@std@@QEAA@PEBD@Z; std::format_error::format_error(char const *)
0x140041621  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x140041628  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14004162c  call    _CxxThrowException_0
0x140041632  mov     rcx, [rbp+28h]; this
0x140041636  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14004163d  mov     edx, 0B07h; void *
0x140041642  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x140041648  lea     rdx, aInvalidUmpPast; "Invalid UMP. Past end of buffer."
0x14004164f  lea     rcx, [rbp+pExceptionObject]; this
0x140041653  call    ??0format_error@std@@QEAA@PEBD@Z; std::format_error::format_error(char const *)
0x140041658  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x14004165f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140041663  call    _CxxThrowException_0
```
