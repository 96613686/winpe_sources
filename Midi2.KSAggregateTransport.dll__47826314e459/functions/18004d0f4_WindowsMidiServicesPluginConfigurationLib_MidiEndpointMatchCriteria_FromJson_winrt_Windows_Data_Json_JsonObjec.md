# WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria::FromJson(winrt::Windows::Data::Json::JsonObject const &)

- ea: `0x18004d0f4`
- end: `0x18004d741`
- name: `?FromJson@MidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@SA?AV?$shared_ptr@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@AEBUJsonObject@Json@Data@Windows@winrt@@@Z`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, service_task`

## callers

- `0x18001e790`

## callees

- `0x180005070`
- `0x180005f2c`
- `0x180005fa4`
- `0x180014f84`
- `0x18001d12c`
- `0x18004bdb0`
- `0x18004d0f4`
- `0x18004dbac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6cf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6de`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6ed`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d70b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d71a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d729`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d739`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6cf`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6de`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6ed`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d6fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d70b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d71a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d729`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18004d739`

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
0x18004d0f4  mov     rax, rsp
0x18004d0f7  mov     [rax+10h], rbx
0x18004d0fb  mov     [rax+20h], rsi
0x18004d0ff  mov     [rax+8], rcx
0x18004d103  push    rdi
0x18004d104  push    r12
0x18004d106  push    r13
0x18004d108  push    r14
0x18004d10a  push    r15
0x18004d10c  sub     rsp, 0A0h
0x18004d113  movaps  xmmword ptr [rax-38h], xmm6
0x18004d117  movaps  xmmword ptr [rax-48h], xmm7
0x18004d11b  mov     r15, rdx
0x18004d11e  mov     r12, rcx
0x18004d121  xor     ebx, ebx
0x18004d123  lea     ecx, [rbx+60h]; Size
0x18004d126  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004d12b  mov     r13, rax
0x18004d12e  lea     ecx, [rbx+1]
0x18004d131  mov     [rax+8], ecx
0x18004d134  mov     [rax+0Ch], ecx
0x18004d137  lea     rax, ??_7?$_Ref_count_obj2@VMidiEndpointMatchCriteria@WindowsMidiServicesPluginConfigurationLib@@@std@@6B@; const std::_Ref_count_obj2<WindowsMidiServicesPluginConfigurationLib::MidiEndpointMatchCriteria>::`vftable'
0x18004d13e  mov     [r13+0], rax
0x18004d142  lea     rdi, [r13+10h]
0x18004d146  mov     [r13+24h], ebx
0x18004d14a  mov     [r13+4Ah], ebx
0x18004d14e  mov     [r13+4Eh], bx
0x18004d153  mov     [rdi], rbx
0x18004d156  mov     [rdi+8], rbx
0x18004d15a  mov     [rdi+10h], ebx
0x18004d15d  mov     [rdi+18h], rbx
0x18004d161  mov     [rdi+20h], rbx
0x18004d165  mov     [rdi+28h], rbx
0x18004d169  mov     [rdi+30h], rbx
0x18004d16d  mov     [rdi+38h], bx
0x18004d171  mov     [rdi+40h], rbx
0x18004d175  mov     [rdi+48h], rbx
0x18004d179  mov     [rsp+0C8h+var_A0], rdi
0x18004d17e  mov     [rsp+0C8h+var_98], r13
0x18004d183  mov     [rsp+0C8h+var_70], rbx
0x18004d188  mov     [rsp+0C8h+var_88], ecx
0x18004d18c  mov     [rsp+0C8h+var_84], 10h
0x18004d194  lea     rax, aEndpointdevice_0; "endpointDeviceId"
0x18004d19b  mov     [rsp+0C8h+var_78], rax
0x18004d1a0  lea     rax, [rsp+0C8h+var_88]
0x18004d1a5  mov     [rsp+0C8h+var_90], rax
0x18004d1aa  lea     r9, [rsp+0C8h+var_70]
0x18004d1af  lea     r8, [rsp+0C8h+var_90]
0x18004d1b4  lea     rdx, [rsp+0C8h+lpMem]
0x18004d1bc  mov     rcx, r15
0x18004d1bf  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d1c4  mov     rdx, rax
0x18004d1c7  mov     rcx, rdi
0x18004d1ca  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d1cf  mov     rsi, [rsp+0C8h+lpMem]
0x18004d1d7  or      r14d, 0FFFFFFFFh
0x18004d1db  test    rsi, rsi
0x18004d1de  jz      short loc_18004D204
0x18004d1e0  mov     eax, r14d
0x18004d1e3  lock xadd [rsi+18h], eax
0x18004d1e8  sub     eax, 1
0x18004d1eb  jnz     loc_18004D6C7
0x18004d1f1  nop
0x18004d1f2  call    WINRT_IMPL_GetProcessHeap
0x18004d1f7  mov     rcx, rax; hHeap
0x18004d1fa  mov     r8, rsi; lpMem
0x18004d1fd  xor     edx, edx; dwFlags
0x18004d1ff  call    WINRT_IMPL_HeapFree
0x18004d204  mov     [rsp+0C8h+var_70], rbx
0x18004d209  mov     [rsp+0C8h+var_88], 1
0x18004d211  mov     [rsp+0C8h+var_84], 18h
0x18004d219  lea     rax, aEndpointdevice; "endpointDeviceInstanceId"
0x18004d220  mov     [rsp+0C8h+var_78], rax
0x18004d225  lea     rax, [rsp+0C8h+var_88]
0x18004d22a  mov     [rsp+0C8h+var_90], rax
0x18004d22f  lea     r9, [rsp+0C8h+var_70]
0x18004d234  lea     r8, [rsp+0C8h+var_90]
0x18004d239  lea     rdx, [rsp+0C8h+lpMem]
0x18004d241  mov     rcx, r15
0x18004d244  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d249  lea     rcx, [rdi+8]
0x18004d24d  mov     rdx, rax
0x18004d250  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d255  mov     rsi, [rsp+0C8h+lpMem]
0x18004d25d  test    rsi, rsi
0x18004d260  jz      short loc_18004D286
0x18004d262  mov     eax, r14d
0x18004d265  lock xadd [rsi+18h], eax
0x18004d26a  sub     eax, 1
0x18004d26d  jnz     loc_18004D6D6
0x18004d273  nop
0x18004d274  call    WINRT_IMPL_GetProcessHeap
0x18004d279  mov     rcx, rax; hHeap
0x18004d27c  mov     r8, rsi; lpMem
0x18004d27f  xor     edx, edx; dwFlags
0x18004d281  call    WINRT_IMPL_HeapFree
0x18004d286  mov     esi, 1
0x18004d28b  mov     [rsp+0C8h+var_88], esi
0x18004d28f  mov     [rsp+0C8h+var_84], 0Bh
0x18004d297  lea     rax, aUsbvendorid; "usbVendorId"
0x18004d29e  mov     [rsp+0C8h+var_78], rax
0x18004d2a3  lea     rax, [rsp+0C8h+var_88]
0x18004d2a8  mov     [rsp+0C8h+var_90], rax
0x18004d2ad  xorps   xmm6, xmm6
0x18004d2b0  xorps   xmm2, xmm2
0x18004d2b3  lea     rdx, [rsp+0C8h+var_90]
0x18004d2b8  mov     rcx, r15
0x18004d2bb  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18004d2c0  movsd   xmm7, cs:__real@40efffe000000000
0x18004d2c8  comisd  xmm6, xmm0
0x18004d2cc  ja      short loc_18004D2D4
0x18004d2ce  comisd  xmm0, xmm7
0x18004d2d2  jbe     short loc_18004D2D7
0x18004d2d4  xorps   xmm0, xmm0
0x18004d2d7  cvttsd2si eax, xmm0
0x18004d2db  mov     [rdi+10h], ax
0x18004d2df  mov     [rsp+0C8h+var_88], esi
0x18004d2e3  mov     [rsp+0C8h+var_84], 0Ch
0x18004d2eb  lea     rax, aUsbproductid; "usbProductId"
0x18004d2f2  mov     [rsp+0C8h+var_78], rax
0x18004d2f7  lea     rax, [rsp+0C8h+var_88]
0x18004d2fc  mov     [rsp+0C8h+var_90], rax
0x18004d301  xorps   xmm2, xmm2
0x18004d304  lea     rdx, [rsp+0C8h+var_90]
0x18004d309  mov     rcx, r15
0x18004d30c  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18004d311  comisd  xmm6, xmm0
0x18004d315  ja      short loc_18004D31D
0x18004d317  comisd  xmm0, xmm7
0x18004d31b  jbe     short loc_18004D320
0x18004d31d  xorps   xmm0, xmm0
0x18004d320  cvttsd2si eax, xmm0
0x18004d324  mov     [rdi+12h], ax
0x18004d328  mov     [rsp+0C8h+var_70], rbx
0x18004d32d  mov     [rsp+0C8h+var_88], esi
0x18004d331  mov     [rsp+0C8h+var_84], 0Fh
0x18004d339  lea     rax, aUsbserialnumbe; "usbSerialNumber"
0x18004d340  mov     [rsp+0C8h+var_78], rax
0x18004d345  lea     rax, [rsp+0C8h+var_88]
0x18004d34a  mov     [rsp+0C8h+var_90], rax
0x18004d34f  lea     r9, [rsp+0C8h+var_70]
0x18004d354  lea     r8, [rsp+0C8h+var_90]
0x18004d359  lea     rdx, [rsp+0C8h+lpMem]
0x18004d361  mov     rcx, r15
0x18004d364  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d369  lea     rcx, [rdi+18h]
0x18004d36d  mov     rdx, rax
0x18004d370  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d375  mov     rsi, [rsp+0C8h+lpMem]
0x18004d37d  test    rsi, rsi
0x18004d380  jz      short loc_18004D3A6
0x18004d382  mov     eax, r14d
0x18004d385  lock xadd [rsi+18h], eax
0x18004d38a  sub     eax, 1
0x18004d38d  jnz     loc_18004D6E5
0x18004d393  nop
0x18004d394  call    WINRT_IMPL_GetProcessHeap
0x18004d399  mov     rcx, rax; hHeap
0x18004d39c  mov     r8, rsi; lpMem
0x18004d39f  xor     edx, edx; dwFlags
0x18004d3a1  call    WINRT_IMPL_HeapFree
0x18004d3a6  mov     [rsp+0C8h+var_70], rbx
0x18004d3ab  mov     [rsp+0C8h+var_88], 1
0x18004d3b3  mov     [rsp+0C8h+var_84], 10h
0x18004d3bb  lea     rax, aManufacturerna; "manufacturerName"
0x18004d3c2  mov     [rsp+0C8h+var_78], rax
0x18004d3c7  lea     rax, [rsp+0C8h+var_88]
0x18004d3cc  mov     [rsp+0C8h+var_90], rax
0x18004d3d1  lea     r9, [rsp+0C8h+var_70]
0x18004d3d6  lea     r8, [rsp+0C8h+var_90]
0x18004d3db  lea     rdx, [rsp+0C8h+lpMem]
0x18004d3e3  mov     rcx, r15
0x18004d3e6  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d3eb  lea     rcx, [rdi+20h]
0x18004d3ef  mov     rdx, rax
0x18004d3f2  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d3f7  mov     rsi, [rsp+0C8h+lpMem]
0x18004d3ff  test    rsi, rsi
0x18004d402  jz      short loc_18004D428
0x18004d404  mov     eax, r14d
0x18004d407  lock xadd [rsi+18h], eax
0x18004d40c  sub     eax, 1
0x18004d40f  jnz     loc_18004D6F4
0x18004d415  nop
0x18004d416  call    WINRT_IMPL_GetProcessHeap
0x18004d41b  mov     rcx, rax; hHeap
0x18004d41e  mov     r8, rsi; lpMem
0x18004d421  xor     edx, edx; dwFlags
0x18004d423  call    WINRT_IMPL_HeapFree
0x18004d428  mov     [rsp+0C8h+var_70], rbx
0x18004d42d  mov     [rsp+0C8h+var_88], 1
0x18004d435  mov     [rsp+0C8h+var_84], 11h
0x18004d43d  lea     rax, aProductinstanc; "productInstanceId"
0x18004d444  mov     [rsp+0C8h+var_78], rax
0x18004d449  lea     rax, [rsp+0C8h+var_88]
0x18004d44e  mov     [rsp+0C8h+var_90], rax
0x18004d453  lea     r9, [rsp+0C8h+var_70]
0x18004d458  lea     r8, [rsp+0C8h+var_90]
0x18004d45d  lea     rdx, [rsp+0C8h+lpMem]
0x18004d465  mov     rcx, r15
0x18004d468  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d46d  lea     rcx, [rdi+28h]
0x18004d471  mov     rdx, rax
0x18004d474  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d479  mov     rsi, [rsp+0C8h+lpMem]
0x18004d481  test    rsi, rsi
0x18004d484  jz      short loc_18004D4AA
0x18004d486  mov     eax, r14d
0x18004d489  lock xadd [rsi+18h], eax
0x18004d48e  sub     eax, 1
0x18004d491  jnz     loc_18004D703
0x18004d497  nop
0x18004d498  call    WINRT_IMPL_GetProcessHeap
0x18004d49d  mov     rcx, rax; hHeap
0x18004d4a0  mov     r8, rsi; lpMem
0x18004d4a3  xor     edx, edx; dwFlags
0x18004d4a5  call    WINRT_IMPL_HeapFree
0x18004d4aa  mov     [rsp+0C8h+var_70], rbx
0x18004d4af  mov     [rsp+0C8h+var_88], 1
0x18004d4b7  mov     [rsp+0C8h+var_84], 0Fh
0x18004d4bf  lea     rax, aStaticipaddres; "staticIPAddress"
0x18004d4c6  mov     [rsp+0C8h+var_78], rax
0x18004d4cb  lea     rax, [rsp+0C8h+var_88]
0x18004d4d0  mov     [rsp+0C8h+var_90], rax
0x18004d4d5  lea     r9, [rsp+0C8h+var_70]
0x18004d4da  lea     r8, [rsp+0C8h+var_90]
0x18004d4df  lea     rdx, [rsp+0C8h+lpMem]
0x18004d4e7  mov     rcx, r15
0x18004d4ea  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d4ef  lea     rcx, [rdi+30h]
0x18004d4f3  mov     rdx, rax
0x18004d4f6  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d4fb  mov     rsi, [rsp+0C8h+lpMem]
0x18004d503  test    rsi, rsi
0x18004d506  jz      short loc_18004D52C
0x18004d508  mov     eax, r14d
0x18004d50b  lock xadd [rsi+18h], eax
0x18004d510  sub     eax, 1
0x18004d513  jnz     loc_18004D712
0x18004d519  nop
0x18004d51a  call    WINRT_IMPL_GetProcessHeap
0x18004d51f  mov     rcx, rax; hHeap
0x18004d522  mov     r8, rsi; lpMem
0x18004d525  xor     edx, edx; dwFlags
0x18004d527  call    WINRT_IMPL_HeapFree
0x18004d52c  mov     esi, 1
0x18004d531  mov     [rsp+0C8h+var_88], esi
0x18004d535  mov     [rsp+0C8h+var_84], 4
0x18004d53d  lea     rax, aPort; "port"
0x18004d544  mov     [rsp+0C8h+var_78], rax
0x18004d549  lea     rax, [rsp+0C8h+var_88]
0x18004d54e  mov     [rsp+0C8h+var_90], rax
0x18004d553  xorps   xmm2, xmm2
0x18004d556  lea     rdx, [rsp+0C8h+var_90]
0x18004d55b  mov     rcx, r15
0x18004d55e  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@N@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedNumber(winrt::param::hstring const &,double)
0x18004d563  comisd  xmm6, xmm0
0x18004d567  ja      short loc_18004D56F
0x18004d569  comisd  xmm0, xmm7
0x18004d56d  jbe     short loc_18004D572
0x18004d56f  xorps   xmm0, xmm0
0x18004d572  cvttsd2si eax, xmm0
0x18004d576  mov     [rdi+38h], ax
0x18004d57a  mov     [rsp+0C8h+var_70], rbx
0x18004d57f  mov     [rsp+0C8h+var_88], esi
0x18004d583  mov     [rsp+0C8h+var_84], 1Dh
0x18004d58b  lea     rax, aTransportsuppl; "transportSuppliedEndpointName"
0x18004d592  mov     [rsp+0C8h+var_78], rax
0x18004d597  lea     rax, [rsp+0C8h+var_88]
0x18004d59c  mov     [rsp+0C8h+var_90], rax
0x18004d5a1  lea     r9, [rsp+0C8h+var_70]
0x18004d5a6  lea     r8, [rsp+0C8h+var_90]
0x18004d5ab  lea     rdx, [rsp+0C8h+lpMem]
0x18004d5b3  mov     rcx, r15
0x18004d5b6  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObjectWithDefaultValues@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Data_Json_IJsonObjectWithDefaultValues<winrt::Windows::Data::Json::JsonObject>::GetNamedString(winrt::param::hstring const &,winrt::param::hstring const &)
0x18004d5bb  lea     rcx, [rdi+40h]
0x18004d5bf  mov     rdx, rax
0x18004d5c2  call    ??4hstring@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::hstring::operator=(winrt::hstring &&)
0x18004d5c7  mov     rsi, [rsp+0C8h+lpMem]
0x18004d5cf  test    rsi, rsi
0x18004d5d2  jz      short loc_18004D5F8
0x18004d5d4  mov     eax, r14d
0x18004d5d7  lock xadd [rsi+18h], eax
0x18004d5dc  sub     eax, 1
0x18004d5df  jnz     loc_18004D721
0x18004d5e5  nop
0x18004d5e6  call    WINRT_IMPL_GetProcessHeap
0x18004d5eb  mov     rcx, rax; hHeap
0x18004d5ee  mov     r8, rsi; lpMem
0x18004d5f1  xor     edx, edx; dwFlags
0x18004d5f3  call    WINRT_IMPL_HeapFree
0x18004d5f8  mov     [rsp+0C8h+var_70], rbx
0x18004d5fd  mov     [rsp+0C8h+var_88], 1
0x18004d605  mov     [rsp+0C8h+var_84], 10h
0x18004d60d  lea     rax, aParentdevicena; "parentDeviceName"
0x18004d614  mov     [rsp+0C8h+var_78], rax
0x18004d619  lea     rax, [rsp+0C8h+var_88]
0x18004d61e  mov     [rsp+0C8h+var_90], rax
0x18004d623  lea     r9, [rsp+0C8h+var_70]
0x18004d628  lea     r8, [rsp+0C8h+var_90]
  ... truncated ...
```
