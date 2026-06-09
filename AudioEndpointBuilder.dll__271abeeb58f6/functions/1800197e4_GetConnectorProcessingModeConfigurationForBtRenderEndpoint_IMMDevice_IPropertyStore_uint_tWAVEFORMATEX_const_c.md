# GetConnectorProcessingModeConfigurationForBtRenderEndpoint(IMMDevice *,IPropertyStore *,uint,tWAVEFORMATEX const * const *,__int64,std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>,std::allocator<std::unique_ptr<CConnectorProcessingModeCharacteristics,std::default_delete<CConnectorProcessingModeCharacteristics>>>> &)

- ea: `0x1800197e4`
- end: `0x180019ce0`
- name: `?GetConnectorProcessingModeConfigurationForBtRenderEndpoint@@YAJPEAUIMMDevice@@PEAUIPropertyStore@@IPEBQEBUtWAVEFORMATEX@@_JAEAV?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@@Z`
- size: `1276`
- prototype: `__int64 __fastcall(__int64, struct IPropertyStore *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800170ac`

## callees

- `0x180010da8`
- `0x1800197e4`
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

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001989c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019cbb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001989c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019b27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019cbb`

## string_xrefs

- `0x18001987b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180019ad8`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180019c57`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall GetConnectorProcessingModeConfigurationForBtRenderEndpoint(
        __int64 a1,
        struct IPropertyStore *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v6; // r15
  struct IPropertyStore *v7; // r14
  unsigned int v8; // r13d
  void *v9; // rcx
  int HostConnectorSignalProcessingModes; // ebx
  const char *v11; // r9
  void *v12; // rcx
  __int64 result; // rax
  char v14; // al
  unsigned int v15; // r12d
  CConnectorProcessingModeCharacteristics *v16; // rax
  CConnectorProcessingModeCharacteristics *v17; // rbx
  int v18; // r9d
  unsigned __int64 v19; // r8
  __int64 v20; // rdx
  int v21; // eax
  signed int v22; // r15d
  int v23; // eax
  unsigned int v24; // r14d
  void *v25; // rcx
  double v26; // xmm1_8
  void *v27; // rcx
  void *v28; // rcx
  unsigned int v29[2]; // [rsp+20h] [rbp-118h]
  LPVOID pv; // [rsp+70h] [rbp-C8h] BYREF
  unsigned int v31; // [rsp+78h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+7Ch] [rbp-BCh]
  CConnectorProcessingModeCharacteristics *v33; // [rsp+80h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+88h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+90h] [rbp-A8h]
  int v36; // [rsp+98h] [rbp-A0h]
  int v37; // [rsp+9Ch] [rbp-9Ch]
  int v38; // [rsp+A0h] [rbp-98h]
  int v39; // [rsp+A4h] [rbp-94h]
  struct _GUID v40; // [rsp+B0h] [rbp-88h] BYREF
  __int64 v41; // [rsp+C0h] [rbp-78h] BYREF
  unsigned __int64 v42; // [rsp+C8h] [rbp-70h]
  __int128 v43; // [rsp+D0h] [rbp-68h] BYREF
  char v44; // [rsp+E0h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]
  int v47; // [rsp+148h] [rbp+10h]

  v47 = (int)a2;
  v6 = a4;
  v7 = a2;
  v8 = 0;
  pv = 0;
  v31 = 0;
  *(_QWORD *)&v43 = &pv;
  *((_QWORD *)&v43 + 1) = 0;
  v44 = 1;
  try
  {
    HostConnectorSignalProcessingModes = GetHostConnectorSignalProcessingModes(a2, &v31, (struct _GUID **)&v43 + 1);
    if ( v44 )
    {
      v9 = *(void **)v43;
      *(_QWORD *)v43 = *((_QWORD *)&v43 + 1);
      if ( v9 )
        CoTaskMemFree(v9);
    }
    if ( HostConnectorSignalProcessingModes >= 0 )
    {
      v34 = 0;
      GetPacketSizeConstraints(v9, v7, &v34);
      v14 = 0;
      do
      {
LABEL_10:
        if ( v14 )
        {
          std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v34);
          v28 = pv;
          pv = 0;
          if ( v28 )
            CoTaskMemFree(v28);
          return 0;
        }
        std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::clear(a6);
        v14 = 1;
        v15 = 0;
LABEL_12:
        ;
      }
      while ( v15 >= v31 );
      v16 = (CConnectorProcessingModeCharacteristics *)operator new[](
                                                         0x40u,
                                                         (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)&v40.Data1 = v16;
      if ( v16 )
      {
        v40 = (struct _GUID)*((_OWORD *)pv + v15);
        v17 = CConnectorProcessingModeCharacteristics::CConnectorProcessingModeCharacteristics(v16, &v40);
      }
      else
      {
        v17 = 0;
      }
      v33 = v17;
      if ( v17 )
      {
        wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v41);
        v40 = (struct _GUID)*((_OWORD *)pv + v15);
        GetConnectorProcessingModeDataFormatsFromDriver(
          (_DWORD)g_DeviceEnumerator,
          (_DWORD)v7,
          (unsigned int)&v40,
          v18,
          (__int64)&v41);
        if ( v42 )
        {
          v19 = v42;
          v20 = v41;
        }
        else
        {
          v19 = 2;
          v20 = v6;
        }
        v35 = v20;
        *(_QWORD *)&v40.Data1 = v19;
        v39 = v42 != 0 ? 2 : 0;
        while ( 1 )
        {
          if ( v8 >= v19 )
          {
            std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::push_back(a6, &v33);
            wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v41);
            std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v33);
            ++v15;
            v14 = 1;
            LODWORD(v7) = v47;
            v6 = a4;
            v8 = 0;
            goto LABEL_12;
          }
          v32 = 0;
          v37 = 0;
          v36 = 0;
          v38 = 0;
          v43 = *((_OWORD *)pv + v15);
          *(_QWORD *)v29 = *(_QWORD *)(v20 + 8LL * v8);
          v21 = DiscoverPeriodicityCharacteristicsForFormat(a1, 0, v19, &v43);
          v20 = v35;
          if ( v21 >= 0 )
          {
            v22 = v32;
            v23 = CConnectorProcessingModeCharacteristics::AddConnectorFormat(
                    v17,
                    *(const struct tWAVEFORMATEX **)(v35 + 8LL * v8),
                    v32,
                    v32,
                    v32,
                    v32,
                    v32);
            v24 = v23;
            if ( v23 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1671,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v23,
                v29[0]);
              wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v41);
              std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v33);
              std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v34);
              v25 = pv;
              pv = 0;
              if ( v25 )
                CoTaskMemFree(v25);
              return v24;
            }
            v20 = v35;
            v26 = (double)*(int *)(*(_QWORD *)(v35 + 8LL * v8) + 4LL);
            if ( (unsigned int)(int)((double)v22 * 10000000.0 / v26 + 0.5) < a5 )
            {
              a5 = (unsigned int)(int)((double)(v22 + 1) * 10000000.0 / v26 + 0.5);
              wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,unsigned __int64>(&v41);
              std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v33);
              v8 = 0;
              v14 = 0;
              LODWORD(v7) = v47;
              v6 = a4;
              goto LABEL_10;
            }
          }
          ++v8;
          v19 = *(_QWORD *)&v40.Data1;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1651,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x8007000ELL,
        v29[0]);
      std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(&v33);
      std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(&v34);
      v27 = pv;
      pv = 0;
      if ( v27 )
        CoTaskMemFree(v27);
      result = 2147942414LL;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1641,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)HostConnectorSignalProcessingModes,
        v29[0]);
      v12 = pv;
      pv = 0;
      if ( v12 )
        CoTaskMemFree(v12);
      result = (unsigned int)HostConnectorSignalProcessingModes;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x168B,
                           (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800197e4  mov     r11, rsp
0x1800197e7  mov     [r11+20h], r9
0x1800197eb  mov     [r11+18h], r8d
0x1800197ef  mov     [r11+10h], rdx
0x1800197f3  mov     [r11+8], rcx
0x1800197f7  push    rbx
0x1800197f8  push    rsi
0x1800197f9  push    rdi
0x1800197fa  push    r12
0x1800197fc  push    r13
0x1800197fe  push    r14
0x180019800  push    r15
0x180019802  sub     rsp, 100h
0x180019809  mov     r15, r9
0x18001980c  mov     r14, rdx
0x18001980f  xor     r13d, r13d
0x180019812  mov     [rsp+138h+pv], r13
0x180019817  mov     [rsp+138h+var_C0], r13d
0x18001981c  lea     rax, [rsp+138h+pv]
0x180019821  mov     [r11-68h], rax
0x180019825  mov     [r11-60h], r13
0x180019829  mov     byte ptr [r11-58h], 1
0x18001982e  lea     r8, [r11-60h]; struct _GUID **
0x180019832  lea     rdx, [rsp+138h+var_C0]; unsigned int *
0x180019837  mov     rcx, r14; struct IPropertyStore *
0x18001983a  call    ?GetHostConnectorSignalProcessingModes@@YAJPEAUIPropertyStore@@PEAKPEAPEAU_GUID@@@Z; GetHostConnectorSignalProcessingModes(IPropertyStore *,ulong *,_GUID * *)
0x18001983f  mov     ebx, eax
0x180019841  cmp     [rsp+138h+var_58], r13b
0x180019849  jz      short loc_18001986C
0x18001984b  mov     r8, qword ptr [rsp+138h+var_68]
0x180019853  mov     rcx, [r8]; pv
0x180019856  mov     rdx, qword ptr [rsp+138h+var_68+8]
0x18001985e  mov     [r8], rdx
0x180019861  test    rcx, rcx
0x180019864  jz      short loc_18001986C
0x180019866  call    cs:__imp_CoTaskMemFree
0x18001986c  test    ebx, ebx
0x18001986e  jns     short loc_1800198A9
0x180019870  mov     rcx, [rsp+138h]; this
0x180019878  mov     r9d, ebx; char *
0x18001987b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180019882  mov     edx, 1641h; void *
0x180019887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001988c  nop
0x18001988d  mov     rcx, [rsp+138h+pv]; pv
0x180019892  mov     [rsp+138h+pv], r13
0x180019897  test    rcx, rcx
0x18001989a  jz      short loc_1800198A2
0x18001989c  call    cs:__imp_CoTaskMemFree
0x1800198a2  mov     eax, ebx
0x1800198a4  jmp     loc_180019CCC
0x1800198a9  mov     [rsp+138h+var_B0], r13
0x1800198b1  lea     r8, [rsp+138h+var_B0]
0x1800198b9  mov     rdx, r14
0x1800198bc  call    ?GetPacketSizeConstraints@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@AEAV?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@@Z; GetPacketSizeConstraints(IMMDeviceEnumerator *,IPropertyStore *,std::unique_ptr<PacketSizeConstraints> &)
0x1800198c1  mov     al, r13b
0x1800198c4  mov     rdi, [rsp+138h+var_B0]
0x1800198cc  test    al, al
0x1800198ce  jnz     loc_180019C9E
0x1800198d4  mov     rcx, [rsp+138h+arg_28]
0x1800198dc  call    ?clear@?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::clear(void)
0x1800198e1  mov     al, 1
0x1800198e3  mov     byte ptr [rsp+138h+arg_10], al
0x1800198ea  mov     r12d, r13d
0x1800198ed  cmp     r12d, [rsp+138h+var_C0]
0x1800198f2  jnb     short loc_1800198CC
0x1800198f4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800198fb  mov     ecx, 40h ; '@'; unsigned __int64
0x180019900  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180019905  mov     qword ptr [rsp+138h+var_88.Data1], rax
0x18001990d  mov     esi, r12d
0x180019910  test    rax, rax
0x180019913  jz      short loc_180019941
0x180019915  mov     edx, esi
0x180019917  add     rdx, rdx
0x18001991a  mov     rcx, [rsp+138h+pv]
0x18001991f  movups  xmm0, xmmword ptr [rcx+rdx*8]
0x180019923  movdqu  xmmword ptr [rsp+138h+var_88.Data1], xmm0
0x18001992c  lea     rdx, [rsp+138h+var_88]; struct _GUID
0x180019934  mov     rcx, rax; this
0x180019937  call    ??0CConnectorProcessingModeCharacteristics@@QEAA@U_GUID@@@Z; CConnectorProcessingModeCharacteristics::CConnectorProcessingModeCharacteristics(_GUID)
0x18001993c  mov     rbx, rax
0x18001993f  jmp     short loc_180019944
0x180019941  mov     rbx, r13
0x180019944  mov     [rsp+138h+var_B8], rbx
0x18001994c  test    rbx, rbx
0x18001994f  jz      loc_180019C47
0x180019955  lea     rcx, [rsp+138h+var_78]
0x18001995d  call    ??0?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019962  nop
0x180019963  add     rsi, rsi
0x180019966  mov     rax, [rsp+138h+pv]
0x18001996b  movups  xmm0, xmmword ptr [rax+rsi*8]
0x18001996f  movdqu  xmmword ptr [rsp+138h+var_88.Data1], xmm0
0x180019978  lea     rax, [rsp+138h+var_78]
0x180019980  mov     qword ptr [rsp+138h+var_118], rax
0x180019985  lea     r8, [rsp+138h+var_88]
0x18001998d  mov     rdx, r14
0x180019990  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180019997  call    ?GetConnectorProcessingModeDataFormatsFromDriver@@YAJPEAUIMMDeviceEnumerator@@PEAUIPropertyStore@@U_GUID@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@AEAV?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@@Z; GetConnectorProcessingModeDataFormatsFromDriver(IMMDeviceEnumerator *,IPropertyStore *,_GUID,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64> &)
0x18001999c  mov     rcx, [rsp+138h+var_70]
0x1800199a4  test    rcx, rcx
0x1800199a7  jz      short loc_1800199B6
0x1800199a9  mov     r8, rcx
0x1800199ac  mov     rdx, [rsp+138h+var_78]
0x1800199b4  jmp     short loc_1800199BF
0x1800199b6  mov     r8d, 2
0x1800199bc  mov     rdx, r15
0x1800199bf  mov     [rsp+138h+var_A8], rdx
0x1800199c7  mov     qword ptr [rsp+138h+var_88.Data1], r8
0x1800199cf  cmp     r13, rcx
0x1800199d2  sbb     ecx, ecx
0x1800199d4  and     ecx, 2
0x1800199d7  mov     [rsp+138h+var_94], ecx
0x1800199de  mov     r14d, r13d
0x1800199e1  cmp     r14, r8
0x1800199e4  jnb     loc_180019BF4
0x1800199ea  xor     r15d, r15d
0x1800199ed  mov     [rsp+138h+var_BC], r15d
0x1800199f2  mov     [rsp+138h+var_9C], r15d
0x1800199fa  mov     [rsp+138h+var_A0], r15d
0x180019a02  mov     [rsp+138h+var_98], r15d
0x180019a0a  mov     rax, [rsp+138h+pv]
0x180019a0f  movups  xmm0, xmmword ptr [rax+rsi*8]
0x180019a13  movdqu  [rsp+138h+var_68], xmm0
0x180019a1c  lea     rax, [rsp+138h+var_48]
0x180019a24  mov     [rsp+138h+var_D8], rax
0x180019a29  lea     rax, [rsp+138h+var_A0]
0x180019a31  mov     [rsp+138h+var_E0], rax
0x180019a36  lea     rax, [rsp+138h+var_9C]
0x180019a3e  mov     [rsp+138h+var_E8], rax
0x180019a43  lea     rax, [rsp+138h+var_98]
0x180019a4b  mov     [rsp+138h+var_F0], rax
0x180019a50  lea     rax, [rsp+138h+var_BC]
0x180019a55  mov     [rsp+138h+var_F8], rax
0x180019a5a  mov     rax, [rsp+138h+arg_20]
0x180019a62  mov     [rsp+138h+var_100], rax
0x180019a67  mov     [rsp+138h+var_108], ecx
0x180019a6b  mov     qword ptr [rsp+138h+var_110], rdi
0x180019a70  mov     rax, [rdx+r14*8]
0x180019a74  mov     qword ptr [rsp+138h+var_118], rax
0x180019a79  lea     r9, [rsp+138h+var_68]
0x180019a81  xor     edx, edx
0x180019a83  mov     rcx, [rsp+138h+arg_0]
0x180019a8b  call    ?DiscoverPeriodicityCharacteristicsForFormat@@YAJPEAUIMMDevice@@W4AUDIO_DIRECTION@@W4__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001@@U_GUID@@PEBUtWAVEFORMATEX@@PEAUPacketSizeConstraints@@W4DPCF_OPTIONS@@_JPEAI8888@Z; DiscoverPeriodicityCharacteristicsForFormat(IMMDevice *,AUDIO_DIRECTION,__MIDL___MIDL_itf_audioengineendpoint_0000_0000_0001,_GUID,tWAVEFORMATEX const *,PacketSizeConstraints *,DPCF_OPTIONS,__int64,uint *,uint *,uint *,uint *,uint *)
0x180019a90  mov     rdx, [rsp+138h+var_A8]
0x180019a98  test    eax, eax
0x180019a9a  js      loc_180019BDD
0x180019aa0  mov     r15d, [rsp+138h+var_BC]
0x180019aa5  mov     [rsp+138h+var_108], r15d; unsigned int
0x180019aaa  mov     [rsp+138h+var_110], r15d; unsigned int
0x180019aaf  mov     [rsp+138h+var_118], r15d; int
0x180019ab4  mov     r9d, r15d; unsigned int
0x180019ab7  mov     r8d, r15d; unsigned int
0x180019aba  mov     rdx, [rdx+r14*8]; struct tWAVEFORMATEX *
0x180019abe  mov     rcx, rbx; this
0x180019ac1  call    ?AddConnectorFormat@CConnectorProcessingModeCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@IIIII@Z; CConnectorProcessingModeCharacteristics::AddConnectorFormat(tWAVEFORMATEX const *,uint,uint,uint,uint,uint)
0x180019ac6  mov     r14d, eax
0x180019ac9  test    eax, eax
0x180019acb  jns     short loc_180019B35
0x180019acd  mov     rcx, [rsp+138h]; this
0x180019ad5  mov     r9d, eax; char *
0x180019ad8  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180019adf  mov     edx, 1671h; void *
0x180019ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ae9  nop
0x180019aea  lea     rcx, [rsp+138h+var_78]
0x180019af2  call    ??1?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019af7  nop
0x180019af8  lea     rcx, [rsp+138h+var_B8]
0x180019b00  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x180019b05  nop
0x180019b06  lea     rcx, [rsp+138h+var_B0]
0x180019b0e  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x180019b13  nop
0x180019b14  mov     rcx, [rsp+138h+pv]; pv
0x180019b19  mov     [rsp+138h+pv], 0
0x180019b22  test    rcx, rcx
0x180019b25  jz      short loc_180019B2D
0x180019b27  call    cs:__imp_CoTaskMemFree
0x180019b2d  mov     eax, r14d
0x180019b30  jmp     loc_180019CCC
0x180019b35  mov     eax, r13d
0x180019b38  mov     rdx, [rsp+138h+var_A8]
0x180019b40  mov     rax, [rdx+rax*8]
0x180019b44  mov     ecx, [rax+4]
0x180019b47  xorps   xmm1, xmm1
0x180019b4a  cvtsi2sd xmm1, rcx
0x180019b4f  xorps   xmm0, xmm0
0x180019b52  cvtsi2sd xmm0, r15
0x180019b57  movsd   xmm2, cs:__real@416312d000000000
0x180019b5f  mulsd   xmm0, xmm2
0x180019b63  divsd   xmm0, xmm1
0x180019b67  movsd   xmm3, cs:__real@3fe0000000000000
0x180019b6f  addsd   xmm0, xmm3
0x180019b73  cvttsd2si rax, xmm0
0x180019b78  cmp     rax, [rsp+138h+arg_20]
0x180019b80  jge     short loc_180019BDD
0x180019b82  lea     ecx, [r15+1]
0x180019b86  xorps   xmm0, xmm0
0x180019b89  cvtsi2sd xmm0, rcx
0x180019b8e  mulsd   xmm0, xmm2
0x180019b92  divsd   xmm0, xmm1
0x180019b96  addsd   xmm0, xmm3
0x180019b9a  cvttsd2si rax, xmm0
0x180019b9f  mov     [rsp+138h+arg_20], rax
0x180019ba7  lea     rcx, [rsp+138h+var_78]
0x180019baf  call    ??1?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019bb4  nop
0x180019bb5  lea     rcx, [rsp+138h+var_B8]
0x180019bbd  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x180019bc2  xor     r13d, r13d
0x180019bc5  mov     al, r13b
0x180019bc8  mov     r14, [rsp+138h+arg_8]
0x180019bd0  mov     r15, [rsp+138h+arg_18]
0x180019bd8  jmp     loc_1800198CC
0x180019bdd  inc     r13d
0x180019be0  mov     r8, qword ptr [rsp+138h+var_88.Data1]
0x180019be8  mov     ecx, [rsp+138h+var_94]
0x180019bef  jmp     loc_1800199DE
0x180019bf4  lea     rdx, [rsp+138h+var_B8]
0x180019bfc  mov     rcx, [rsp+138h+arg_28]
0x180019c04  call    ?push_back@?$vector@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@V?$allocator@V?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@2@@Z; std::vector<std::unique_ptr<CConnectorProcessingModeCharacteristics>>::push_back(std::unique_ptr<CConnectorProcessingModeCharacteristics> &&)
0x180019c09  nop
0x180019c0a  lea     rcx, [rsp+138h+var_78]
0x180019c12  call    ??1?$unique_any_array_ptr@PEAUtWAVEFORMATEX@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U23@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>::~unique_any_array_ptr<tWAVEFORMATEX *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,unsigned __int64>(void)
0x180019c17  nop
0x180019c18  lea     rcx, [rsp+138h+var_B8]
0x180019c20  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x180019c25  inc     r12d
0x180019c28  mov     al, byte ptr [rsp+138h+arg_10]
0x180019c2f  mov     r14, [rsp+138h+arg_8]
0x180019c37  mov     r15, [rsp+138h+arg_18]
0x180019c3f  xor     r13d, r13d
0x180019c42  jmp     loc_1800198ED
0x180019c47  mov     rcx, [rsp+138h]; this
0x180019c4f  mov     ebx, 8007000Eh
0x180019c54  mov     r9d, ebx; char *
0x180019c57  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180019c5e  mov     edx, 1651h; void *
0x180019c63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c68  nop
0x180019c69  lea     rcx, [rsp+138h+var_B8]
0x180019c71  call    ??1?$unique_ptr@VCConnectorProcessingModeCharacteristics@@U?$default_delete@VCConnectorProcessingModeCharacteristics@@@std@@@std@@QEAA@XZ; std::unique_ptr<CConnectorProcessingModeCharacteristics>::~unique_ptr<CConnectorProcessingModeCharacteristics>(void)
0x180019c76  nop
0x180019c77  lea     rcx, [rsp+138h+var_B0]
0x180019c7f  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x180019c84  nop
0x180019c85  mov     rcx, [rsp+138h+pv]; pv
0x180019c8a  mov     [rsp+138h+pv], r13
0x180019c8f  test    rcx, rcx
0x180019c92  jz      short loc_180019C9A
0x180019c94  call    cs:__imp_CoTaskMemFree
0x180019c9a  mov     eax, ebx
0x180019c9c  jmp     short loc_180019CCC
0x180019c9e  lea     rcx, [rsp+138h+var_B0]
0x180019ca6  call    ??1?$unique_ptr@UPacketSizeConstraints@@U?$default_delete@UPacketSizeConstraints@@@std@@@std@@QEAA@XZ; std::unique_ptr<PacketSizeConstraints>::~unique_ptr<PacketSizeConstraints>(void)
0x180019cab  nop
0x180019cac  mov     rcx, [rsp+138h+pv]; pv
0x180019cb1  mov     [rsp+138h+pv], r13
0x180019cb6  test    rcx, rcx
0x180019cb9  jz      short loc_180019CC1
0x180019cbb  call    cs:__imp_CoTaskMemFree
0x180019cc1  xor     eax, eax
0x180019cc3  jmp     short loc_180019CCC
0x180019cc5  mov     eax, [rsp+138h+arg_10]
0x180019ccc  add     rsp, 100h
0x180019cd3  pop     r15
0x180019cd5  pop     r14
0x180019cd7  pop     r13
0x180019cd9  pop     r12
0x180019cdb  pop     rdi
0x180019cdc  pop     rsi
0x180019cdd  pop     rbx
0x180019cde  retn
```
