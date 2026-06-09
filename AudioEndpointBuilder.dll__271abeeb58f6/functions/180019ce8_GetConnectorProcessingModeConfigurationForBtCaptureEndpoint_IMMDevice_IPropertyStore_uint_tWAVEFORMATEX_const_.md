# GetConnectorProcessingModeConfigurationForBtCaptureEndpoint(IMMDevice *,IPropertyStore *,uint,tWAVEFORMATEX const * const *,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>,std::allocator<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>>> &)

- ea: `0x180019ce8`
- end: `0x18001a12d`
- name: `?GetConnectorProcessingModeConfigurationForBtCaptureEndpoint@@YAJPEAUIMMDevice@@PEAUIPropertyStore@@IPEBQEBUtWAVEFORMATEX@@AEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@@Z`
- size: `1093`
- prototype: `__int64 __fastcall(__int64, struct IPropertyStore *, __int64, CConnectorProcessingModeCharacteristics *, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800170ac`

## callees

- `0x180010da8`
- `0x180019ce8`
- `0x18001a134`
- `0x18001acac`
- `0x18001b7b4`
- `0x180020034`
- `0x180028604`
- `0x1800372c0`
- `0x180037304`
- `0x180039028`
- `0x1800394a8`
- `0x18003edfc`
- `0x1800489b0`
- `0x180048b20`
- `0x18005df1c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a02b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a108`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019d97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a02b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a0e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a108`

## string_xrefs

- `0x180019d76`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180019fdc`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001a0a4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall GetConnectorProcessingModeConfigurationForBtCaptureEndpoint(
        __int64 a1,
        struct IPropertyStore *a2,
        __int64 a3,
        CConnectorProcessingModeCharacteristics *a4,
        __int64 a5)
{
  void *v6; // rcx
  int HostConnectorSignalProcessingModes; // ebx
  const char *v8; // r9
  void *v9; // rcx
  __int64 result; // rax
  unsigned int v11; // r14d
  CConnectorProcessingModeCharacteristics *v12; // rax
  CConnectorProcessingModeCharacteristics *v13; // rbx
  int v14; // r9d
  unsigned __int64 v15; // rdx
  __int64 (**v16)[5]; // r8
  unsigned int i; // r12d
  int v18; // eax
  unsigned int v19; // r15d
  void *v20; // rcx
  void *v21; // rcx
  void *v22; // rcx
  unsigned int v23[2]; // [rsp+20h] [rbp-108h]
  LPVOID pv; // [rsp+70h] [rbp-B8h] BYREF
  unsigned int v25; // [rsp+78h] [rbp-B0h]
  unsigned int v26; // [rsp+7Ch] [rbp-ACh]
  unsigned int v27; // [rsp+80h] [rbp-A8h]
  unsigned int v28; // [rsp+84h] [rbp-A4h]
  __int64 v29; // [rsp+88h] [rbp-A0h] BYREF
  CConnectorProcessingModeCharacteristics *v30; // [rsp+90h] [rbp-98h] BYREF
  int v31; // [rsp+98h] [rbp-90h]
  __int64 (**v32)[5]; // [rsp+A0h] [rbp-88h]
  struct _GUID v33; // [rsp+B0h] [rbp-78h] BYREF
  __int64 (**v34)[5]; // [rsp+C0h] [rbp-68h] BYREF
  unsigned __int64 v35; // [rsp+C8h] [rbp-60h]
  __int128 v36; // [rsp+D0h] [rbp-58h] BYREF
  char v37; // [rsp+E0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]
  unsigned int v40; // [rsp+140h] [rbp+18h] BYREF
  CConnectorProcessingModeCharacteristics *v41; // [rsp+148h] [rbp+20h]

  v41 = a4;
  pv = 0;
  v40 = 0;
  *(_QWORD *)&v36 = &pv;
  *((_QWORD *)&v36 + 1) = 0;
  v37 = 1;
  try
  {
    HostConnectorSignalProcessingModes = GetHostConnectorSignalProcessingModes(a2, &v40, (struct _GUID **)&v36 + 1);
    if ( v37 )
    {
      v6 = *(void **)v36;
      *(_QWORD *)v36 = *((_QWORD *)&v36 + 1);
      if ( v6 )
        CoTaskMemFree(v6);
    }
    if ( HostConnectorSignalProcessingModes >= 0 )
    {
      v29 = 0;
      GetPacketSizeConstraints(v6, a2, &v29);
      std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::clear(a5);
      v11 = 0;
LABEL_10:
      if ( v11 >= v40 )
      {
        std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v29);
        v22 = pv;
        pv = 0;
        if ( v22 )
          CoTaskMemFree(v22);
        result = 0;
      }
      else
      {
        v12 = (CConnectorProcessingModeCharacteristics *)operator new[](
                                                           0x40u,
                                                           (const struct std::nothrow_t *)&std::nothrow);
        v41 = v12;
        if ( v12 )
        {
          v33 = (struct _GUID)*((_OWORD *)pv + v11);
          v13 = CConnectorProcessingModeCharacteristics::CConnectorProcessingModeCharacteristics(v12, &v33);
        }
        else
        {
          v13 = 0;
        }
        v30 = v13;
        if ( v13 )
        {
          wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v34);
          v33 = (struct _GUID)*((_OWORD *)pv + v11);
          GetConnectorProcessingModeDataFormatsFromDriver(
            (_DWORD)g_DeviceEnumerator,
            (_DWORD)a2,
            (unsigned int)&v33,
            v14,
            (__int64)&v34);
          if ( v35 )
          {
            v15 = v35;
            *(_QWORD *)&v33.Data1 = v35;
            v16 = v34;
          }
          else
          {
            v15 = 2;
            *(_QWORD *)&v33.Data1 = 2;
            v16 = off_18006ACC8;
          }
          v32 = v16;
          v31 = v35 != 0 ? 2 : 0;
          for ( i = 0; ; ++i )
          {
            if ( i >= v15 )
            {
              std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::push_back(a5, &v30);
              wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v34);
              std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v30);
              ++v11;
              goto LABEL_10;
            }
            v28 = 0;
            v26 = 0;
            v25 = 0;
            v27 = 0;
            LODWORD(v41) = 0;
            v36 = *((_OWORD *)pv + v11);
            *(_QWORD *)v23 = v16[i];
            if ( (int)DiscoverPeriodicityCharacteristicsForFormat(a1, 1, v16, &v36) >= 0 )
            {
              v18 = CConnectorProcessingModeCharacteristics::AddConnectorFormat(
                      v13,
                      (const struct tWAVEFORMATEX *)v32[i],
                      v28,
                      v27,
                      v26,
                      v25,
                      (unsigned int)v41);
              v19 = v18;
              if ( v18 < 0 )
                break;
            }
            v15 = *(_QWORD *)&v33.Data1;
            v16 = v32;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x16BD,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v18,
            v23[0]);
          wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v34);
          std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v30);
          std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v29);
          v20 = pv;
          pv = 0;
          if ( v20 )
            CoTaskMemFree(v20);
          result = v19;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x169F,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)0x8007000ELL,
            v23[0]);
          std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v30);
          std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v29);
          v21 = pv;
          pv = 0;
          if ( v21 )
            CoTaskMemFree(v21);
          result = 2147942414LL;
        }
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1694,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)HostConnectorSignalProcessingModes,
        v23[0]);
      v9 = pv;
      pv = 0;
      if ( v9 )
        CoTaskMemFree(v9);
      result = (unsigned int)HostConnectorSignalProcessingModes;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x16C7,
                           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180019ce8  mov     r11, rsp
0x180019ceb  mov     [r11+20h], r9
0x180019cef  mov     [r11+18h], r8d
0x180019cf3  mov     [r11+8], rcx
0x180019cf7  push    rbx
0x180019cf8  push    rsi
0x180019cf9  push    rdi
0x180019cfa  push    r12
0x180019cfc  push    r13
0x180019cfe  push    r14
0x180019d00  push    r15
0x180019d02  sub     rsp, 0F0h
0x180019d09  mov     r13, rdx
0x180019d0c  xor     r15d, r15d
0x180019d0f  mov     [rsp+128h+pv], r15
0x180019d14  mov     [r11+18h], r15d
0x180019d18  lea     rax, [rsp+128h+pv]
0x180019d1d  mov     [r11-58h], rax
0x180019d21  mov     [r11-50h], r15
0x180019d25  mov     byte ptr [r11-48h], 1
0x180019d2a  lea     r8, [r11-50h]; struct _GUID **
0x180019d2e  lea     rdx, [r11+18h]; unsigned int *
0x180019d32  mov     rcx, r13; struct IPropertyStore *
0x180019d35  call    ?GetHostConnectorSignalProcessingModes@@YAJPEAUIPropertyStore@@PEAKPEAPEAU_GUID@@@Z; GetHostConnectorSignalProcessingModes(IPropertyStore *,ulong *,_GUID * *)
0x180019d3a  mov     ebx, eax
0x180019d3c  cmp     [rsp+128h+var_48], r15b
0x180019d44  jz      short loc_180019D67
0x180019d46  mov     r8, qword ptr [rsp+128h+var_58]
0x180019d4e  mov     rcx, [r8]; pv
0x180019d51  mov     rdx, qword ptr [rsp+128h+var_58+8]
0x180019d59  mov     [r8], rdx
0x180019d5c  test    rcx, rcx
0x180019d5f  jz      short loc_180019D67
0x180019d61  call    cs:__imp_CoTaskMemFree
0x180019d67  test    ebx, ebx
0x180019d69  jns     short loc_180019DA4
0x180019d6b  mov     rcx, [rsp+128h]; this
0x180019d73  mov     r9d, ebx; char *
0x180019d76  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180019d7d  mov     edx, 1694h; void *
0x180019d82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019d87  nop
0x180019d88  mov     rcx, [rsp+128h+pv]; pv
0x180019d8d  mov     [rsp+128h+pv], r15
0x180019d92  test    rcx, rcx
0x180019d95  jz      short loc_180019D9D
0x180019d97  call    cs:__imp_CoTaskMemFree
0x180019d9d  mov     eax, ebx
0x180019d9f  jmp     loc_18001A119
0x180019da4  mov     [rsp+128h+var_A0], r15
0x180019dac  lea     r8, [rsp+128h+var_A0]
0x180019db4  mov     rdx, r13
0x180019db7  call    ?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z; GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints> &)
0x180019dbc  mov     rcx, [rsp+128h+arg_20]
0x180019dc4  call    ?clear@?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::clear(void)
0x180019dc9  mov     r14d, r15d
0x180019dcc  mov     rdi, [rsp+128h+var_A0]
0x180019dd4  cmp     r14d, [rsp+128h+arg_10]
0x180019ddc  jnb     loc_18001A0EB
0x180019de2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180019de9  mov     ecx, 40h ; '@'; unsigned __int64
0x180019dee  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019df3  mov     [rsp+128h+arg_18], rax
0x180019dfb  mov     esi, r14d
0x180019dfe  test    rax, rax
0x180019e01  jz      short loc_180019E2F
0x180019e03  mov     edx, esi
0x180019e05  add     rdx, rdx
0x180019e08  mov     rcx, [rsp+128h+pv]
0x180019e0d  movups  xmm0, xmmword ptr [rcx+rdx*8]
0x180019e11  movdqu  xmmword ptr [rsp+128h+var_78.Data1], xmm0
0x180019e1a  lea     rdx, [rsp+128h+var_78]; struct _GUID
0x180019e22  mov     rcx, rax; this
0x180019e25  call    ??0CConnectorProcessingModeCharacteristics@@QEAA@U_GUID@@@Z; CConnectorProcessingModeCharacteristics::CConnectorProcessingModeCharacteristics(_GUID)
0x180019e2a  mov     rbx, rax
0x180019e2d  jmp     short loc_180019E32
0x180019e2f  mov     rbx, r15
0x180019e32  mov     [rsp+128h+var_98], rbx
0x180019e3a  test    rbx, rbx
0x180019e3d  jz      loc_18001A094
0x180019e43  lea     rcx, [rsp+128h+var_68]
0x180019e4b  call    ??0?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019e50  nop
0x180019e51  add     rsi, rsi
0x180019e54  mov     rax, [rsp+128h+pv]
0x180019e59  movups  xmm0, xmmword ptr [rax+rsi*8]
0x180019e5d  movdqu  xmmword ptr [rsp+128h+var_78.Data1], xmm0
0x180019e66  lea     rax, [rsp+128h+var_68]
0x180019e6e  mov     qword ptr [rsp+128h+var_108], rax
0x180019e73  lea     r8, [rsp+128h+var_78]
0x180019e7b  mov     rdx, r13
0x180019e7e  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180019e85  call    ?GetConnectorProcessingModeDataFormatsFromDriver@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@AEAV?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@@Z; GetConnectorProcessingModeDataFormatsFromDriver(IMMDeviceEnumerator *,IPropertyStore *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64> &)
0x180019e8a  mov     rcx, [rsp+128h+var_60]
0x180019e92  test    rcx, rcx
0x180019e95  jz      short loc_180019EAC
0x180019e97  mov     rdx, rcx
0x180019e9a  mov     qword ptr [rsp+128h+var_78.Data1], rcx
0x180019ea2  mov     r8, [rsp+128h+var_68]
0x180019eaa  jmp     short loc_180019EC0
0x180019eac  mov     edx, 2
0x180019eb1  mov     qword ptr [rsp+128h+var_78.Data1], rdx
0x180019eb9  lea     r8, off_18006ACC8
0x180019ec0  mov     [rsp+128h+var_88], r8
0x180019ec8  cmp     r15, rcx
0x180019ecb  sbb     ecx, ecx
0x180019ecd  and     ecx, 2
0x180019ed0  mov     [rsp+128h+var_90], ecx
0x180019ed7  mov     r12d, r15d
0x180019eda  mov     r15d, r12d
0x180019edd  cmp     r15, rdx
0x180019ee0  jnb     loc_18001A058
0x180019ee6  xor     edx, edx
0x180019ee8  mov     [rsp+128h+var_A4], edx
0x180019eef  mov     [rsp+128h+var_AC], edx
0x180019ef3  mov     [rsp+128h+var_B0], edx
0x180019ef7  mov     [rsp+128h+var_A8], edx
0x180019efe  mov     dword ptr [rsp+128h+arg_18], edx
0x180019f05  mov     rax, [rsp+128h+pv]
0x180019f0a  movups  xmm0, xmmword ptr [rax+rsi*8]
0x180019f0e  movdqu  [rsp+128h+var_58], xmm0
0x180019f17  lea     rax, [rsp+128h+arg_18]
0x180019f1f  mov     [rsp+128h+var_C8], rax
0x180019f24  lea     rax, [rsp+128h+var_B0]
0x180019f29  mov     [rsp+128h+var_D0], rax
0x180019f2e  lea     rax, [rsp+128h+var_AC]
0x180019f33  mov     [rsp+128h+var_D8], rax
0x180019f38  lea     rax, [rsp+128h+var_A8]
0x180019f40  mov     [rsp+128h+var_E0], rax
0x180019f45  lea     rax, [rsp+128h+var_A4]
0x180019f4d  mov     [rsp+128h+var_E8], rax
0x180019f52  mov     [rsp+128h+var_F0], rdx
0x180019f57  mov     [rsp+128h+var_F8], ecx
0x180019f5b  mov     qword ptr [rsp+128h+var_100], rdi
0x180019f60  mov     rax, [r8+r15*8]
0x180019f64  mov     qword ptr [rsp+128h+var_108], rax
0x180019f69  lea     r9, [rsp+128h+var_58]
0x180019f71  mov     edx, 1
0x180019f76  mov     rcx, [rsp+128h+arg_0]
0x180019f7e  call    ?DiscoverPeriodicityCharacteristicsForFormat@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@PEAUPacketSizeConstraints@@W4DPCF_OPTIONS@@_JPEAI8888@Z; DiscoverPeriodicityCharacteristicsForFormat(IMMDevice *,AUDIO_DIRECTION,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *,PacketSizeConstraints *,DPCF_OPTIONS,__int64,uint *,uint *,uint *,uint *,uint *)
0x180019f83  test    eax, eax
0x180019f85  js      loc_18001A039
0x180019f8b  mov     eax, dword ptr [rsp+128h+arg_18]
0x180019f92  mov     [rsp+128h+var_F8], eax; unsigned int
0x180019f96  mov     eax, [rsp+128h+var_B0]
0x180019f9a  mov     [rsp+128h+var_100], eax; unsigned int
0x180019f9e  mov     eax, [rsp+128h+var_AC]
0x180019fa2  mov     [rsp+128h+var_108], eax; int
0x180019fa6  mov     r9d, [rsp+128h+var_A8]; unsigned int
0x180019fae  mov     r8d, [rsp+128h+var_A4]; unsigned int
0x180019fb6  mov     rdx, [rsp+128h+var_88]
0x180019fbe  mov     rdx, [rdx+r15*8]; struct tWAVEFORMATEX *
0x180019fc2  mov     rcx, rbx; this
0x180019fc5  call    ?AddConnectorFormat@CConnectorProcessingModeCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@IIIII@Z; CConnectorProcessingModeCharacteristics::AddConnectorFormat(tWAVEFORMATEX const *,uint,uint,uint,uint,uint)
0x180019fca  mov     r15d, eax
0x180019fcd  test    eax, eax
0x180019fcf  jns     short loc_18001A039
0x180019fd1  mov     rcx, [rsp+128h]; this
0x180019fd9  mov     r9d, eax; char *
0x180019fdc  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180019fe3  mov     edx, 16BDh; void *
0x180019fe8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fed  nop
0x180019fee  lea     rcx, [rsp+128h+var_68]
0x180019ff6  call    ??1?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019ffb  nop
0x180019ffc  lea     rcx, [rsp+128h+var_98]
0x18001a004  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x18001a009  nop
0x18001a00a  lea     rcx, [rsp+128h+var_A0]
0x18001a012  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x18001a017  nop
0x18001a018  mov     rcx, [rsp+128h+pv]; pv
0x18001a01d  mov     [rsp+128h+pv], 0
0x18001a026  test    rcx, rcx
0x18001a029  jz      short loc_18001A031
0x18001a02b  call    cs:__imp_CoTaskMemFree
0x18001a031  mov     eax, r15d
0x18001a034  jmp     loc_18001A119
0x18001a039  inc     r12d
0x18001a03c  mov     rdx, qword ptr [rsp+128h+var_78.Data1]
0x18001a044  mov     r8, [rsp+128h+var_88]
0x18001a04c  mov     ecx, [rsp+128h+var_90]
0x18001a053  jmp     loc_180019EDA
0x18001a058  lea     rdx, [rsp+128h+var_98]
0x18001a060  mov     rcx, [rsp+128h+arg_20]
0x18001a068  call    ?push_back@?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@2@@Z; std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::push_back(std::unique_ptr<CConnectorProcessingModeCharacteristics> &&)
0x18001a06d  nop
0x18001a06e  lea     rcx, [rsp+128h+var_68]
0x18001a076  call    ??1?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x18001a07b  nop
0x18001a07c  lea     rcx, [rsp+128h+var_98]
0x18001a084  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x18001a089  inc     r14d
0x18001a08c  xor     r15d, r15d
0x18001a08f  jmp     loc_180019DD4
0x18001a094  mov     rcx, [rsp+128h]; this
0x18001a09c  mov     ebx, 8007000Eh
0x18001a0a1  mov     r9d, ebx; char *
0x18001a0a4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001a0ab  mov     edx, 169Fh; void *
0x18001a0b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0b5  nop
0x18001a0b6  lea     rcx, [rsp+128h+var_98]
0x18001a0be  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x18001a0c3  nop
0x18001a0c4  lea     rcx, [rsp+128h+var_A0]
0x18001a0cc  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x18001a0d1  nop
0x18001a0d2  mov     rcx, [rsp+128h+pv]; pv
0x18001a0d7  mov     [rsp+128h+pv], r15
0x18001a0dc  test    rcx, rcx
0x18001a0df  jz      short loc_18001A0E7
0x18001a0e1  call    cs:__imp_CoTaskMemFree
0x18001a0e7  mov     eax, ebx
0x18001a0e9  jmp     short loc_18001A119
0x18001a0eb  lea     rcx, [rsp+128h+var_A0]
0x18001a0f3  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x18001a0f8  nop
0x18001a0f9  mov     rcx, [rsp+128h+pv]; pv
0x18001a0fe  mov     [rsp+128h+pv], r15
0x18001a103  test    rcx, rcx
0x18001a106  jz      short loc_18001A10E
0x18001a108  call    cs:__imp_CoTaskMemFree
0x18001a10e  xor     eax, eax
0x18001a110  jmp     short loc_18001A119
0x18001a112  mov     eax, [rsp+128h+arg_10]
0x18001a119  add     rsp, 0F0h
0x18001a120  pop     r15
0x18001a122  pop     r14
0x18001a124  pop     r13
0x18001a126  pop     r12
0x18001a128  pop     rdi
0x18001a129  pop     rsi
0x18001a12a  pop     rbx
0x18001a12b  retn
```
