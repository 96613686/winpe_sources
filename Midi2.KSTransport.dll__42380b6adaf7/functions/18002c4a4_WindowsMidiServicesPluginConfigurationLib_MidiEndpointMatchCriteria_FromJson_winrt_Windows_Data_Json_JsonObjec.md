# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x18002c4a4`
- end: `0x18002caf1`
- name: `?FromJson@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x180023ac0`

## callees

- `0x180004460`
- `0x1800052fc`
- `0x180005374`
- `0x180011240`
- `0x180022478`
- `0x18002bb20`
- `0x18002c4a4`
- `0x18002cf5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca8e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002caac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cabb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002caca`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cad9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cae9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca7f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca8e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ca9d`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002caac`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cabb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002caca`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cad9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cae9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria **__fastcall WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson(
        WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria **a1,
        __int64 *a2)
{
  _DWORD *v4; // r13
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *v5; // rdi
  _QWORD *NamedString; // rax
  void *v7; // rsi
  int v8; // eax
  HANDLE ProcessHeap; // rax
  _QWORD *v10; // rax
  __int64 v11; // r8
  void *v12; // rsi
  int v13; // eax
  HANDLE v14; // rax
  __int64 v15; // r8
  double NamedNumber; // xmm0_8
  double v17; // xmm0_8
  _QWORD *v18; // rax
  void *v19; // rsi
  int v20; // eax
  HANDLE v21; // rax
  _QWORD *v22; // rax
  void *v23; // rsi
  int v24; // eax
  HANDLE v25; // rax
  _QWORD *v26; // rax
  void *v27; // rsi
  int v28; // eax
  HANDLE v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // r8
  void *v32; // rsi
  int v33; // eax
  HANDLE v34; // rax
  double v35; // xmm0_8
  _QWORD *v36; // rax
  void *v37; // rsi
  int v38; // eax
  HANDLE v39; // rax
  _QWORD *v40; // rax
  void *v41; // rsi
  int v42; // r14d
  HANDLE v43; // rax
  WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria **result; // rax
  int *v45; // [rsp+38h] [rbp-90h] BYREF
  int v46; // [rsp+40h] [rbp-88h] BYREF
  int v47; // [rsp+44h] [rbp-84h]
  const wchar_t *v48; // [rsp+50h] [rbp-78h]
  _QWORD v49[9]; // [rsp+58h] [rbp-70h] BYREF
  LPVOID lpMem; // [rsp+E0h] [rbp+18h] BYREF

  try
  {
    v4 = operator new(0x60u);
    v4[2] = 1;
    v4[3] = 1;
    *(_QWORD *)v4 = &std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::`vftable';
    v5 = (WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)(v4 + 4);
    v4[9] = 0;
    *(_DWORD *)((char *)v4 + 74) = 0;
    *((_WORD *)v4 + 39) = 0;
    *((_QWORD *)v4 + 2) = 0;
    *((_QWORD *)v4 + 3) = 0;
    v4[8] = 0;
    *((_QWORD *)v4 + 5) = 0;
    *((_QWORD *)v4 + 6) = 0;
    *((_QWORD *)v4 + 7) = 0;
    *((_QWORD *)v4 + 8) = 0;
    *((_WORD *)v4 + 36) = 0;
    *((_QWORD *)v4 + 10) = 0;
    *((_QWORD *)v4 + 11) = 0;
    v49[0] = 0;
    v46 = 1;
    v47 = 16;
    v48 = L"endpointDeviceId";
    v45 = &v46;
    NamedString = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
                    a2,
                    &lpMem,
                    &v45,
                    v49);
    winrt::hstring::operator=(v4 + 4, NamedString);
    v7 = lpMem;
    if ( lpMem )
    {
      v8 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v8 )
      {
        if ( v8 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v7);
      }
    }
    v49[0] = 0;
    v46 = 1;
    v47 = 24;
    v48 = L"endpointDeviceInstanceId";
    v45 = &v46;
    v10 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 6, v10);
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v13 )
      {
        if ( v13 < 0 )
          abort();
      }
      else
      {
        v14 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v14, 0, v12);
      }
    }
    v46 = 1;
    v47 = 11;
    v48 = L"usbVendorId";
    v45 = &v46;
    NamedNumber = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(
                    a2,
                    &v45,
                    v11);
    if ( NamedNumber < 0.0 || NamedNumber > 65535.0 )
      NamedNumber = 0.0;
    *((_WORD *)v4 + 16) = (int)NamedNumber;
    v46 = 1;
    v47 = 12;
    v48 = L"usbProductId";
    v45 = &v46;
    v17 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(
            a2,
            &v45,
            v15);
    if ( v17 < 0.0 || v17 > 65535.0 )
      v17 = 0.0;
    *((_WORD *)v4 + 17) = (int)v17;
    v49[0] = 0;
    v46 = 1;
    v47 = 15;
    v48 = L"usbSerialNumber";
    v45 = &v46;
    v18 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 10, v18);
    v19 = lpMem;
    if ( lpMem )
    {
      v20 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v20 )
      {
        if ( v20 < 0 )
          abort();
      }
      else
      {
        v21 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v21, 0, v19);
      }
    }
    v49[0] = 0;
    v46 = 1;
    v47 = 16;
    v48 = L"manufacturerName";
    v45 = &v46;
    v22 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 12, v22);
    v23 = lpMem;
    if ( lpMem )
    {
      v24 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v24 )
      {
        if ( v24 < 0 )
          abort();
      }
      else
      {
        v25 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v25, 0, v23);
      }
    }
    v49[0] = 0;
    v46 = 1;
    v47 = 17;
    v48 = L"productInstanceId";
    v45 = &v46;
    v26 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 14, v26);
    v27 = lpMem;
    if ( lpMem )
    {
      v28 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v28 )
      {
        if ( v28 < 0 )
          abort();
      }
      else
      {
        v29 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v29, 0, v27);
      }
    }
    v49[0] = 0;
    v46 = 1;
    v47 = 15;
    v48 = L"staticIPAddress";
    v45 = &v46;
    v30 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 16, v30);
    v32 = lpMem;
    if ( lpMem )
    {
      v33 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v33 )
      {
        if ( v33 < 0 )
          abort();
      }
      else
      {
        v34 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v34, 0, v32);
      }
    }
    v46 = 1;
    v47 = 4;
    v48 = L"port";
    v45 = &v46;
    v35 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(
            a2,
            &v45,
            v31);
    if ( v35 < 0.0 || v35 > 65535.0 )
      v35 = 0.0;
    *((_WORD *)v4 + 36) = (int)v35;
    v49[0] = 0;
    v46 = 1;
    v47 = 29;
    v48 = L"transportSuppliedEndpointName";
    v45 = &v46;
    v36 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 20, v36);
    v37 = lpMem;
    if ( lpMem )
    {
      v38 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v38 )
      {
        if ( v38 < 0 )
          abort();
      }
      else
      {
        v39 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v39, 0, v37);
      }
    }
    v49[0] = 0;
    v46 = 1;
    v47 = 16;
    v48 = L"parentDeviceName";
    v45 = &v46;
    v40 = winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(
            a2,
            &lpMem,
            &v45,
            v49);
    winrt::hstring::operator=(v4 + 22, v40);
    v41 = lpMem;
    if ( lpMem )
    {
      v42 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v42 )
      {
        if ( v42 < 0 )
          abort();
      }
      else
      {
        v43 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v43, 0, v41);
      }
    }
    WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::Normalize(v5);
    *a1 = v5;
    a1[1] = (WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria *)v4;
    result = a1;
  }
  catch ( ... )
  {
    OutputDebugStringW(L"Exception parsing MIDI Endpoint Match JSON.");
    result = a1;
    *a1 = 0;
    a1[1] = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002c4a4  mov     rax, rsp
0x18002c4a7  mov     [rax+10h], rbx
0x18002c4ab  mov     [rax+20h], rsi
0x18002c4af  mov     [rax+8], rcx
0x18002c4b3  push    rdi
0x18002c4b4  push    r12
0x18002c4b6  push    r13
0x18002c4b8  push    r14
0x18002c4ba  push    r15
0x18002c4bc  sub     rsp, 0A0h
0x18002c4c3  movaps  xmmword ptr [rax-38h], xmm6
0x18002c4c7  movaps  xmmword ptr [rax-48h], xmm7
0x18002c4cb  mov     r15, rdx
0x18002c4ce  mov     r12, rcx
0x18002c4d1  xor     ebx, ebx
0x18002c4d3  lea     ecx, [rbx+60h]; Size
0x18002c4d6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002c4db  mov     r13, rax
0x18002c4de  lea     ecx, [rbx+1]
0x18002c4e1  mov     [rax+8], ecx
0x18002c4e4  mov     [rax+0Ch], ecx
0x18002c4e7  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::`vftable'
0x18002c4ee  mov     [r13+0], rax
0x18002c4f2  lea     rdi, [r13+10h]
0x18002c4f6  mov     [r13+24h], ebx
0x18002c4fa  mov     [r13+4Ah], ebx
0x18002c4fe  mov     [r13+4Eh], bx
0x18002c503  mov     [rdi], rbx
0x18002c506  mov     [rdi+8], rbx
0x18002c50a  mov     [rdi+10h], ebx
0x18002c50d  mov     [rdi+18h], rbx
0x18002c511  mov     [rdi+20h], rbx
0x18002c515  mov     [rdi+28h], rbx
0x18002c519  mov     [rdi+30h], rbx
0x18002c51d  mov     [rdi+38h], bx
0x18002c521  mov     [rdi+40h], rbx
0x18002c525  mov     [rdi+48h], rbx
0x18002c529  mov     [rsp+0C8h+var_A0], rdi
0x18002c52e  mov     [rsp+0C8h+var_98], r13
0x18002c533  mov     [rsp+0C8h+var_70], rbx
0x18002c538  mov     [rsp+0C8h+var_88], ecx
0x18002c53c  mov     [rsp+0C8h+var_84], 10h
0x18002c544  lea     rax, aEndpointdevice_0; "endpointDeviceId"
0x18002c54b  mov     [rsp+0C8h+var_78], rax
0x18002c550  lea     rax, [rsp+0C8h+var_88]
0x18002c555  mov     [rsp+0C8h+var_90], rax
0x18002c55a  lea     r9, [rsp+0C8h+var_70]
0x18002c55f  lea     r8, [rsp+0C8h+var_90]
0x18002c564  lea     rdx, [rsp+0C8h+lpMem]
0x18002c56c  mov     rcx, r15
0x18002c56f  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c574  mov     rdx, rax
0x18002c577  mov     rcx, rdi
0x18002c57a  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c57f  mov     rsi, [rsp+0C8h+lpMem]
0x18002c587  or      r14d, 0FFFFFFFFh
0x18002c58b  test    rsi, rsi
0x18002c58e  jz      short loc_18002C5B4
0x18002c590  mov     eax, r14d
0x18002c593  lock xadd [rsi+18h], eax
0x18002c598  sub     eax, 1
0x18002c59b  jnz     loc_18002CA77
0x18002c5a1  nop
0x18002c5a2  call    WINRT_IMPL_GetProcessHeap
0x18002c5a7  mov     rcx, rax; hHeap
0x18002c5aa  mov     r8, rsi; lpMem
0x18002c5ad  xor     edx, edx; dwFlags
0x18002c5af  call    WINRT_IMPL_HeapFree
0x18002c5b4  mov     [rsp+0C8h+var_70], rbx
0x18002c5b9  mov     [rsp+0C8h+var_88], 1
0x18002c5c1  mov     [rsp+0C8h+var_84], 18h
0x18002c5c9  lea     rax, aEndpointdevice; "endpointDeviceInstanceId"
0x18002c5d0  mov     [rsp+0C8h+var_78], rax
0x18002c5d5  lea     rax, [rsp+0C8h+var_88]
0x18002c5da  mov     [rsp+0C8h+var_90], rax
0x18002c5df  lea     r9, [rsp+0C8h+var_70]
0x18002c5e4  lea     r8, [rsp+0C8h+var_90]
0x18002c5e9  lea     rdx, [rsp+0C8h+lpMem]
0x18002c5f1  mov     rcx, r15
0x18002c5f4  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c5f9  lea     rcx, [rdi+8]
0x18002c5fd  mov     rdx, rax
0x18002c600  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c605  mov     rsi, [rsp+0C8h+lpMem]
0x18002c60d  test    rsi, rsi
0x18002c610  jz      short loc_18002C636
0x18002c612  mov     eax, r14d
0x18002c615  lock xadd [rsi+18h], eax
0x18002c61a  sub     eax, 1
0x18002c61d  jnz     loc_18002CA86
0x18002c623  nop
0x18002c624  call    WINRT_IMPL_GetProcessHeap
0x18002c629  mov     rcx, rax; hHeap
0x18002c62c  mov     r8, rsi; lpMem
0x18002c62f  xor     edx, edx; dwFlags
0x18002c631  call    WINRT_IMPL_HeapFree
0x18002c636  mov     esi, 1
0x18002c63b  mov     [rsp+0C8h+var_88], esi
0x18002c63f  mov     [rsp+0C8h+var_84], 0Bh
0x18002c647  lea     rax, aUsbvendorid; "usbVendorId"
0x18002c64e  mov     [rsp+0C8h+var_78], rax
0x18002c653  lea     rax, [rsp+0C8h+var_88]
0x18002c658  mov     [rsp+0C8h+var_90], rax
0x18002c65d  xorps   xmm6, xmm6
0x18002c660  xorps   xmm2, xmm2
0x18002c663  lea     rdx, [rsp+0C8h+var_90]
0x18002c668  mov     rcx, r15
0x18002c66b  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18002c670  movsd   xmm7, cs:__real@40efffe000000000
0x18002c678  comisd  xmm6, xmm0
0x18002c67c  ja      short loc_18002C684
0x18002c67e  comisd  xmm0, xmm7
0x18002c682  jbe     short loc_18002C687
0x18002c684  xorps   xmm0, xmm0
0x18002c687  cvttsd2si eax, xmm0
0x18002c68b  mov     [rdi+10h], ax
0x18002c68f  mov     [rsp+0C8h+var_88], esi
0x18002c693  mov     [rsp+0C8h+var_84], 0Ch
0x18002c69b  lea     rax, aUsbproductid; "usbProductId"
0x18002c6a2  mov     [rsp+0C8h+var_78], rax
0x18002c6a7  lea     rax, [rsp+0C8h+var_88]
0x18002c6ac  mov     [rsp+0C8h+var_90], rax
0x18002c6b1  xorps   xmm2, xmm2
0x18002c6b4  lea     rdx, [rsp+0C8h+var_90]
0x18002c6b9  mov     rcx, r15
0x18002c6bc  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18002c6c1  comisd  xmm6, xmm0
0x18002c6c5  ja      short loc_18002C6CD
0x18002c6c7  comisd  xmm0, xmm7
0x18002c6cb  jbe     short loc_18002C6D0
0x18002c6cd  xorps   xmm0, xmm0
0x18002c6d0  cvttsd2si eax, xmm0
0x18002c6d4  mov     [rdi+12h], ax
0x18002c6d8  mov     [rsp+0C8h+var_70], rbx
0x18002c6dd  mov     [rsp+0C8h+var_88], esi
0x18002c6e1  mov     [rsp+0C8h+var_84], 0Fh
0x18002c6e9  lea     rax, aUsbserialnumbe; "usbSerialNumber"
0x18002c6f0  mov     [rsp+0C8h+var_78], rax
0x18002c6f5  lea     rax, [rsp+0C8h+var_88]
0x18002c6fa  mov     [rsp+0C8h+var_90], rax
0x18002c6ff  lea     r9, [rsp+0C8h+var_70]
0x18002c704  lea     r8, [rsp+0C8h+var_90]
0x18002c709  lea     rdx, [rsp+0C8h+lpMem]
0x18002c711  mov     rcx, r15
0x18002c714  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c719  lea     rcx, [rdi+18h]
0x18002c71d  mov     rdx, rax
0x18002c720  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c725  mov     rsi, [rsp+0C8h+lpMem]
0x18002c72d  test    rsi, rsi
0x18002c730  jz      short loc_18002C756
0x18002c732  mov     eax, r14d
0x18002c735  lock xadd [rsi+18h], eax
0x18002c73a  sub     eax, 1
0x18002c73d  jnz     loc_18002CA95
0x18002c743  nop
0x18002c744  call    WINRT_IMPL_GetProcessHeap
0x18002c749  mov     rcx, rax; hHeap
0x18002c74c  mov     r8, rsi; lpMem
0x18002c74f  xor     edx, edx; dwFlags
0x18002c751  call    WINRT_IMPL_HeapFree
0x18002c756  mov     [rsp+0C8h+var_70], rbx
0x18002c75b  mov     [rsp+0C8h+var_88], 1
0x18002c763  mov     [rsp+0C8h+var_84], 10h
0x18002c76b  lea     rax, aManufacturerna; "manufacturerName"
0x18002c772  mov     [rsp+0C8h+var_78], rax
0x18002c777  lea     rax, [rsp+0C8h+var_88]
0x18002c77c  mov     [rsp+0C8h+var_90], rax
0x18002c781  lea     r9, [rsp+0C8h+var_70]
0x18002c786  lea     r8, [rsp+0C8h+var_90]
0x18002c78b  lea     rdx, [rsp+0C8h+lpMem]
0x18002c793  mov     rcx, r15
0x18002c796  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c79b  lea     rcx, [rdi+20h]
0x18002c79f  mov     rdx, rax
0x18002c7a2  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c7a7  mov     rsi, [rsp+0C8h+lpMem]
0x18002c7af  test    rsi, rsi
0x18002c7b2  jz      short loc_18002C7D8
0x18002c7b4  mov     eax, r14d
0x18002c7b7  lock xadd [rsi+18h], eax
0x18002c7bc  sub     eax, 1
0x18002c7bf  jnz     loc_18002CAA4
0x18002c7c5  nop
0x18002c7c6  call    WINRT_IMPL_GetProcessHeap
0x18002c7cb  mov     rcx, rax; hHeap
0x18002c7ce  mov     r8, rsi; lpMem
0x18002c7d1  xor     edx, edx; dwFlags
0x18002c7d3  call    WINRT_IMPL_HeapFree
0x18002c7d8  mov     [rsp+0C8h+var_70], rbx
0x18002c7dd  mov     [rsp+0C8h+var_88], 1
0x18002c7e5  mov     [rsp+0C8h+var_84], 11h
0x18002c7ed  lea     rax, aProductinstanc; "productInstanceId"
0x18002c7f4  mov     [rsp+0C8h+var_78], rax
0x18002c7f9  lea     rax, [rsp+0C8h+var_88]
0x18002c7fe  mov     [rsp+0C8h+var_90], rax
0x18002c803  lea     r9, [rsp+0C8h+var_70]
0x18002c808  lea     r8, [rsp+0C8h+var_90]
0x18002c80d  lea     rdx, [rsp+0C8h+lpMem]
0x18002c815  mov     rcx, r15
0x18002c818  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c81d  lea     rcx, [rdi+28h]
0x18002c821  mov     rdx, rax
0x18002c824  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c829  mov     rsi, [rsp+0C8h+lpMem]
0x18002c831  test    rsi, rsi
0x18002c834  jz      short loc_18002C85A
0x18002c836  mov     eax, r14d
0x18002c839  lock xadd [rsi+18h], eax
0x18002c83e  sub     eax, 1
0x18002c841  jnz     loc_18002CAB3
0x18002c847  nop
0x18002c848  call    WINRT_IMPL_GetProcessHeap
0x18002c84d  mov     rcx, rax; hHeap
0x18002c850  mov     r8, rsi; lpMem
0x18002c853  xor     edx, edx; dwFlags
0x18002c855  call    WINRT_IMPL_HeapFree
0x18002c85a  mov     [rsp+0C8h+var_70], rbx
0x18002c85f  mov     [rsp+0C8h+var_88], 1
0x18002c867  mov     [rsp+0C8h+var_84], 0Fh
0x18002c86f  lea     rax, aStaticipaddres; "staticIPAddress"
0x18002c876  mov     [rsp+0C8h+var_78], rax
0x18002c87b  lea     rax, [rsp+0C8h+var_88]
0x18002c880  mov     [rsp+0C8h+var_90], rax
0x18002c885  lea     r9, [rsp+0C8h+var_70]
0x18002c88a  lea     r8, [rsp+0C8h+var_90]
0x18002c88f  lea     rdx, [rsp+0C8h+lpMem]
0x18002c897  mov     rcx, r15
0x18002c89a  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c89f  lea     rcx, [rdi+30h]
0x18002c8a3  mov     rdx, rax
0x18002c8a6  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c8ab  mov     rsi, [rsp+0C8h+lpMem]
0x18002c8b3  test    rsi, rsi
0x18002c8b6  jz      short loc_18002C8DC
0x18002c8b8  mov     eax, r14d
0x18002c8bb  lock xadd [rsi+18h], eax
0x18002c8c0  sub     eax, 1
0x18002c8c3  jnz     loc_18002CAC2
0x18002c8c9  nop
0x18002c8ca  call    WINRT_IMPL_GetProcessHeap
0x18002c8cf  mov     rcx, rax; hHeap
0x18002c8d2  mov     r8, rsi; lpMem
0x18002c8d5  xor     edx, edx; dwFlags
0x18002c8d7  call    WINRT_IMPL_HeapFree
0x18002c8dc  mov     esi, 1
0x18002c8e1  mov     [rsp+0C8h+var_88], esi
0x18002c8e5  mov     [rsp+0C8h+var_84], 4
0x18002c8ed  lea     rax, aPort; "port"
0x18002c8f4  mov     [rsp+0C8h+var_78], rax
0x18002c8f9  lea     rax, [rsp+0C8h+var_88]
0x18002c8fe  mov     [rsp+0C8h+var_90], rax
0x18002c903  xorps   xmm2, xmm2
0x18002c906  lea     rdx, [rsp+0C8h+var_90]
0x18002c90b  mov     rcx, r15
0x18002c90e  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18002c913  comisd  xmm6, xmm0
0x18002c917  ja      short loc_18002C91F
0x18002c919  comisd  xmm0, xmm7
0x18002c91d  jbe     short loc_18002C922
0x18002c91f  xorps   xmm0, xmm0
0x18002c922  cvttsd2si eax, xmm0
0x18002c926  mov     [rdi+38h], ax
0x18002c92a  mov     [rsp+0C8h+var_70], rbx
0x18002c92f  mov     [rsp+0C8h+var_88], esi
0x18002c933  mov     [rsp+0C8h+var_84], 1Dh
0x18002c93b  lea     rax, aTransportsuppl; "transportSuppliedEndpointName"
0x18002c942  mov     [rsp+0C8h+var_78], rax
0x18002c947  lea     rax, [rsp+0C8h+var_88]
0x18002c94c  mov     [rsp+0C8h+var_90], rax
0x18002c951  lea     r9, [rsp+0C8h+var_70]
0x18002c956  lea     r8, [rsp+0C8h+var_90]
0x18002c95b  lea     rdx, [rsp+0C8h+lpMem]
0x18002c963  mov     rcx, r15
0x18002c966  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18002c96b  lea     rcx, [rdi+40h]
0x18002c96f  mov     rdx, rax
0x18002c972  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18002c977  mov     rsi, [rsp+0C8h+lpMem]
0x18002c97f  test    rsi, rsi
0x18002c982  jz      short loc_18002C9A8
0x18002c984  mov     eax, r14d
0x18002c987  lock xadd [rsi+18h], eax
0x18002c98c  sub     eax, 1
0x18002c98f  jnz     loc_18002CAD1
0x18002c995  nop
0x18002c996  call    WINRT_IMPL_GetProcessHeap
0x18002c99b  mov     rcx, rax; hHeap
0x18002c99e  mov     r8, rsi; lpMem
0x18002c9a1  xor     edx, edx; dwFlags
0x18002c9a3  call    WINRT_IMPL_HeapFree
0x18002c9a8  mov     [rsp+0C8h+var_70], rbx
0x18002c9ad  mov     [rsp+0C8h+var_88], 1
0x18002c9b5  mov     [rsp+0C8h+var_84], 10h
0x18002c9bd  lea     rax, aParentdevicena; "parentDeviceName"
0x18002c9c4  mov     [rsp+0C8h+var_78], rax
0x18002c9c9  lea     rax, [rsp+0C8h+var_88]
0x18002c9ce  mov     [rsp+0C8h+var_90], rax
0x18002c9d3  lea     r9, [rsp+0C8h+var_70]
0x18002c9d8  lea     r8, [rsp+0C8h+var_90]
  ... truncated ...
```
