# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::RemoveUnpairedContainersFromRegistry(void)

- ea: `0x180043510`
- end: `0x180043bb0`
- name: `?RemoveUnpairedContainersFromRegistry@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAAXXZ`
- size: `1696`
- prototype: `void __fastcall(Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180041708`

## callees

- `0x180001dd0`
- `0x18000ab4c`
- `0x180012554`
- `0x1800134d4`
- `0x1800142c8`
- `0x18001446c`
- `0x1800151f4`
- `0x180015b1c`
- `0x180019c68`
- `0x180019d20`
- `0x180019f80`
- `0x18002eb08`
- `0x18003d654`
- `0x18003d694`
- `0x18003dd08`
- `0x18003ea34`
- `0x18003f0c8`
- `0x180043510`
- `0x18004572c`
- `0x180045f68`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043846`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180043846`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043ad4`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043ad4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004399b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004399b`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180043b7f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x180043b7f`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18004378b`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18004378b`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180043826`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180043826`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180043b09`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180043b09`

## string_xrefs

- `0x180043924`: `System\CurrentControlSet\Services\BthAvctpSvc\Parameters\Bats`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::RemoveUnpairedContainersFromRegistry(
        Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector *this)
{
  char v2; // di
  char v3; // dl
  char v4; // r8
  int Objects; // eax
  int v6; // edx
  __int64 v7; // r8
  __int64 v8; // rbx
  __int64 v9; // rsi
  __int64 Property; // rax
  char v11; // dl
  char v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rax
  DWORD v16; // esi
  DWORD i; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  char v20; // bl
  char v21; // dl
  char v22; // r8
  __int64 j; // rbx
  __int64 v24; // rdi
  const WCHAR *v25; // rax
  HKEY v26; // r8
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  _BYTE v35[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v36[24]; // [rsp+90h] [rbp-70h] BYREF
  unsigned int *v37; // [rsp+A8h] [rbp-58h]
  __int64 *v38; // [rsp+B0h] [rbp-50h]
  char v39; // [rsp+B8h] [rbp-48h]
  _BYTE v40[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v41[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v42[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v43[32]; // [rsp+120h] [rbp+20h] BYREF
  DEVPROPKEY v44; // [rsp+140h] [rbp+40h] BYREF
  int v45; // [rsp+154h] [rbp+54h]
  __int64 v46; // [rsp+158h] [rbp+58h]
  _DWORD v47[3]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v48; // [rsp+16Ch] [rbp+6Ch]
  _BYTE v49[28]; // [rsp+17Ch] [rbp+7Ch] BYREF
  int v50; // [rsp+198h] [rbp+98h]
  int v51; // [rsp+1A0h] [rbp+A0h]
  __int128 v52; // [rsp+1A4h] [rbp+A4h]
  _BYTE v53[28]; // [rsp+1B4h] [rbp+B4h] BYREF
  int v54; // [rsp+1D0h] [rbp+D0h]
  DEVPROPKEY v55; // [rsp+1D8h] [rbp+D8h]
  int v56; // [rsp+1ECh] [rbp+ECh]
  __int64 v57; // [rsp+1F0h] [rbp+F0h]
  int v58; // [rsp+1F8h] [rbp+F8h]
  int v59; // [rsp+1FCh] [rbp+FCh]
  GUID *v60; // [rsp+200h] [rbp+100h]
  int v61; // [rsp+208h] [rbp+108h]
  DEVPROPKEY v62; // [rsp+210h] [rbp+110h]
  int v63; // [rsp+224h] [rbp+124h]
  __int64 v64; // [rsp+228h] [rbp+128h]
  int v65; // [rsp+230h] [rbp+130h]
  int v66; // [rsp+234h] [rbp+134h]
  GUID *v67; // [rsp+238h] [rbp+138h]
  int v68; // [rsp+240h] [rbp+140h]
  int v69; // [rsp+248h] [rbp+148h]
  __int128 v70; // [rsp+24Ch] [rbp+14Ch]
  _BYTE v71[28]; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v72; // [rsp+278h] [rbp+178h]
  DEVPROPKEY v73; // [rsp+280h] [rbp+180h]
  int v74; // [rsp+294h] [rbp+194h]
  __int64 v75; // [rsp+298h] [rbp+198h]
  __int64 v76; // [rsp+2A0h] [rbp+1A0h]
  __int64 v77; // [rsp+2A8h] [rbp+1A8h]
  int v78; // [rsp+2B0h] [rbp+1B0h]
  int v79; // [rsp+2B8h] [rbp+1B8h]
  __int128 v80; // [rsp+2BCh] [rbp+1BCh]
  _BYTE v81[28]; // [rsp+2CCh] [rbp+1CCh] BYREF
  OLECHAR sz[40]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v2 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v3 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    v3 = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (v4 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    v4 = 0;
  }
  if ( v3 || v4 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      v4,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      70,
      &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
      (char)this);
  v44 = DEVPKEY_Device_ContainerId;
  v45 = 0;
  v46 = 0;
  v47[0] = 0x100000;
  v47[2] = 0;
  v48 = 0;
  memset(v49, 0, sizeof(v49));
  v50 = 3145728;
  v51 = 0;
  v52 = 0;
  memset(v53, 0, sizeof(v53));
  v54 = 2;
  v55 = DEVPKEY_DeviceInterface_ClassGuid;
  v56 = 0;
  v57 = 0;
  v58 = 13;
  v59 = 16;
  v60 = &GUID_BTH_DEVICE_INTERFACE;
  v61 = 2;
  v62 = DEVPKEY_DeviceInterface_ClassGuid;
  v63 = 0;
  v64 = 0;
  v65 = 13;
  v66 = 16;
  v67 = &GUID_BLUETOOTHLE_DEVICE_INTERFACE;
  v68 = 0x400000;
  v69 = 0;
  v70 = 0;
  memset(v71, 0, sizeof(v71));
  v72 = 1;
  v73 = DEVPKEY_Device_ContainerId;
  v74 = 0;
  v75 = 0;
  v76 = 13;
  v77 = 0;
  v78 = 0x200000;
  v79 = 0;
  v80 = 0;
  memset(v81, 0, sizeof(v81));
  v29 = 0;
  v32 = 0;
  v37 = &v29;
  v38 = &v32;
  v39 = 1;
  Objects = DevGetObjects(1, 0, 1, &v44);
  if ( Objects >= 0 )
  {
    std::set<std::wstring>::set<std::wstring>(v35);
    v8 = v32;
    v9 = v32 + 32LL * v29;
    while ( v8 != v9 )
    {
      Property = DevFindProperty(&DEVPKEY_Device_ContainerId, 0, 0, *(unsigned int *)(v8 + 16), *(_QWORD *)(v8 + 24));
      if ( Property )
      {
        if ( StringFromGUID2(*(const GUID *const *)(Property + 40), sz, 39) )
        {
          std::wstring::wstring((__int64)v40, (__int64)sz);
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(
            v35,
            v36,
            v40);
          std::wstring::_Tidy_deallocate(v40);
          if ( v36[8] )
          {
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
            {
              v11 = 0;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              || (v12 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
            {
              v12 = 0;
            }
            if ( v11 || v12 )
              WPP_RECORDER_AND_TRACE_SF_Sq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                5,
                1,
                72,
                &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
                (__int64)sz,
                (char)this);
          }
        }
      }
      v8 += 32;
    }
    v33 = 0;
    v34 = 0;
    hKey = 0;
    v13 = std::wstring::wstring(
            (__int64)v43,
            (__int64)L"System\\CurrentControlSet\\Services\\BthAvctpSvc\\Parameters\\Bats");
    v14 = std::operator+<unsigned short>(v42, v13);
    std::operator+<unsigned short>(v41, v14, (char *)this + 248);
    std::wstring::_Tidy_deallocate(v42);
    std::wstring::_Tidy_deallocate(v43);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x20019u, &hKey) )
    {
      cchName = 39;
      v16 = 0;
      for ( i = 0; !RegEnumKeyExW(hKey, i, sz, &cchName, 0, 0, 0, 0); i = v16 )
      {
        cchName = 39;
        std::wstring::wstring((__int64)v40, (__int64)sz);
        v18 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
                v35,
                v36);
        v20 = std::_Tree<std::_Tmap_traits<std::wstring,_GUID,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::_Lower_bound_duplicate<std::wstring>(
                v19,
                *(_QWORD *)(v18 + 16),
                v40);
        std::wstring::_Tidy_deallocate(v40);
        if ( !v20 )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || (v21 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
          {
            v21 = 0;
          }
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            || (v22 = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
          {
            v22 = 0;
          }
          if ( v21 || v22 )
            WPP_RECORDER_AND_TRACE_SF_Sq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              5,
              1,
              73,
              &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
              (__int64)sz,
              (char)this);
          std::wstring::wstring((__int64)v40, (__int64)sz);
          std::vector<std::wstring>::push_back(&v33, v40);
          std::wstring::_Tidy_deallocate(v40);
        }
        ++v16;
      }
    }
    if ( hKey )
    {
      v24 = *((_QWORD *)&v33 + 1);
      for ( j = v33; j != v24; j += 32 )
      {
        v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(j);
        RegDeleteKeyW(v26, v25);
      }
    }
    std::wstring::_Tidy_deallocate(v41);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( (_QWORD)v33 )
    {
      std::_Destroy_range<std::allocator<std::wstring>>(v33, *((_QWORD *)&v33 + 1), v27, v28);
      std::_Deallocate<16>((void *)v33, (struct std::nothrow_t *)((v34 - v33) & 0xFFFFFFFFFFFFFFE0uLL));
      v33 = 0;
      v34 = 0;
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v35);
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v6) = v2;
      WPP_RECORDER_AND_TRACE_SF_lq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v6,
        v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        7,
        (unsigned int)v47,
        71,
        (unsigned int)&v32,
        Objects,
        (char)this);
    }
  }
  DevFreeObjects(v29, v32, v7);
}

```

## disassembly

```asm
0x180043510  mov     [rsp-8+arg_8], rbx
0x180043515  mov     [rsp-8+arg_10], rsi
0x18004351a  push    rbp
0x18004351b  push    rdi
0x18004351c  push    r13
0x18004351e  push    r14
0x180043520  push    r15
0x180043522  lea     rbp, [rsp-250h]
0x18004352a  sub     rsp, 350h
0x180043531  mov     rax, cs:__security_cookie
0x180043538  xor     rax, rsp
0x18004353b  mov     [rbp+270h+var_30], rax
0x180043542  mov     r14, rcx
0x180043545  lea     r13, WPP_GLOBAL_Control
0x18004354c  xor     r15d, r15d
0x18004354f  lea     edi, [r15+1]
0x180043553  mov     rcx, cs:WPP_GLOBAL_Control
0x18004355a  cmp     rcx, r13
0x18004355d  jz      short loc_18004356E
0x18004355f  test    [rcx+1Ch], dil
0x180043563  jz      short loc_18004356E
0x180043565  cmp     byte ptr [rcx+19h], 5
0x180043569  mov     dl, dil
0x18004356c  jnb     short loc_180043571
0x18004356e  mov     dl, r15b; int
0x180043571  lea     rbx, WPP_RECORDER_INITIALIZED
0x180043578  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x18004357f  jz      short loc_18004358B
0x180043581  cmp     [rcx+30h], r15w
0x180043586  mov     r8b, dil
0x180043589  jnz     short loc_18004358E
0x18004358b  mov     r8b, r15b; int
0x18004358e  lea     r9, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x180043595  test    dl, dl
0x180043597  jnz     short loc_18004359E
0x180043599  test    r8b, r8b
0x18004359c  jz      short loc_1800435C5
0x18004359e  mov     qword ptr [rsp+370h+var_330], r14; char
0x1800435a3  mov     [rsp+370h+lpftLastWriteTime], r9; MessageGuid
0x1800435a8  mov     word ptr [rsp+370h+lpcchClass], 46h ; 'F'; __int16
0x1800435af  mov     dword ptr [rsp+370h+lpClass], edi; int
0x1800435b3  mov     byte ptr [rsp+370h+phkResult], 5; char
0x1800435b8  mov     r9, [rcx+28h]; int
0x1800435bc  mov     rcx, [rcx+10h]; int
0x1800435c0  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800435c5  movups  xmm1, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x1800435cc  movups  [rbp+270h+var_230], xmm1
0x1800435d0  mov     ecx, cs:DEVPKEY_Device_ContainerId.pid
0x1800435d6  mov     [rbp+270h+var_220], ecx
0x1800435d9  mov     [rbp+270h+var_21C], r15d
0x1800435dd  mov     [rbp+270h+var_218], r15
0x1800435e1  mov     [rbp+270h+var_210], 100000h
0x1800435e8  mov     [rbp+270h+var_208], r15d
0x1800435ec  xorps   xmm0, xmm0
0x1800435ef  xor     eax, eax
0x1800435f1  movups  [rbp+270h+var_204], xmm0
0x1800435f5  movups  xmmword ptr [rbp+270h+var_1F4], xmm0
0x1800435f9  movups  xmmword ptr [rbp+270h+var_1F4+0Ch], xmm0
0x180043600  mov     [rbp+270h+var_1D8], 300000h
0x18004360a  mov     [rbp+270h+var_1D0], r15d
0x180043611  movups  [rbp+270h+var_1CC], xmm0
0x180043618  movups  xmmword ptr [rbp+270h+var_1BC], xmm0
0x18004361f  movups  xmmword ptr [rbp+270h+var_1BC+0Ch], xmm0
0x180043626  lea     r9d, [rax+2]
0x18004362a  mov     [rbp+270h+var_1A0], r9d
0x180043631  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x180043638  movups  [rbp+270h+var_198], xmm0
0x18004363f  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x180043645  mov     [rbp+270h+var_188], eax
0x18004364b  mov     [rbp+270h+var_184], r15d
0x180043652  mov     [rbp+270h+var_180], r15
0x180043659  lea     r10d, [r9+0Bh]
0x18004365d  mov     [rbp+270h+var_178], r10d
0x180043664  lea     r8d, [r9+0Eh]
0x180043668  mov     [rbp+270h+var_174], r8d
0x18004366f  lea     rdx, GUID_BTH_DEVICE_INTERFACE
0x180043676  mov     [rbp+270h+var_170], rdx
0x18004367d  mov     [rbp+270h+var_168], r9d
0x180043684  movaps  [rbp+270h+var_160], xmm0
0x18004368b  mov     [rbp+270h+var_150], eax
0x180043691  mov     [rbp+270h+var_14C], r15d
0x180043698  mov     [rbp+270h+var_148], r15
0x18004369f  mov     [rbp+270h+var_140], r10d
0x1800436a6  mov     [rbp+270h+var_13C], r8d
0x1800436ad  lea     rax, GUID_BLUETOOTHLE_DEVICE_INTERFACE
0x1800436b4  mov     [rbp+270h+var_138], rax
0x1800436bb  mov     [rbp+270h+var_130], 400000h
0x1800436c5  mov     [rbp+270h+var_128], r15d
0x1800436cc  xorps   xmm0, xmm0
0x1800436cf  xor     eax, eax
0x1800436d1  movups  [rbp+270h+var_124], xmm0
0x1800436d8  movups  xmmword ptr [rbp+270h+var_114], xmm0
0x1800436df  movups  xmmword ptr [rbp+270h+var_114+0Ch], xmm0
0x1800436e6  mov     [rbp+270h+var_F8], edi
0x1800436ec  movaps  [rbp+270h+var_F0], xmm1
0x1800436f3  mov     [rbp+270h+var_E0], ecx
0x1800436f9  mov     [rbp+270h+var_DC], r15d
0x180043700  mov     [rbp+270h+var_D8], r15
0x180043707  mov     [rbp+270h+var_D0], r10
0x18004370e  mov     [rbp+270h+var_C8], r15
0x180043715  mov     [rbp+270h+var_C0], 200000h
0x18004371f  mov     [rbp+270h+var_B8], r15d
0x180043726  movups  [rbp+270h+var_B4], xmm0
0x18004372d  movups  xmmword ptr [rbp+270h+var_A4], xmm0
0x180043734  movups  xmmword ptr [rbp+270h+var_A4+0Ch], xmm0
0x18004373b  mov     [rsp+370h+var_320], r15d
0x180043740  mov     [rsp+370h+var_310], r15
0x180043745  lea     rax, [rsp+370h+var_320]
0x18004374a  mov     [rbp+270h+var_2C8], rax
0x18004374e  lea     rax, [rsp+370h+var_310]
0x180043753  mov     [rbp+270h+var_2C0], rax
0x180043757  mov     [rbp+270h+var_2B8], dil
0x18004375b  lea     rax, [rsp+370h+var_310]
0x180043760  mov     [rsp+370h+lpftLastWriteTime], rax
0x180043765  lea     rax, [rsp+370h+var_320]
0x18004376a  mov     [rsp+370h+lpcchClass], rax
0x18004376f  lea     rax, [rbp+270h+var_210]
0x180043773  mov     [rsp+370h+lpClass], rax
0x180043778  mov     dword ptr [rsp+370h+phkResult], 7
0x180043780  lea     r9, [rbp+270h+var_230]
0x180043784  mov     r8d, edi
0x180043787  xor     edx, edx
0x180043789  mov     ecx, edi
0x18004378b  call    cs:__imp_DevGetObjects
0x180043791  test    eax, eax
0x180043793  jns     short loc_1800437EE
0x180043795  mov     rcx, cs:WPP_GLOBAL_Control
0x18004379c  cmp     rcx, r13
0x18004379f  jz      short loc_1800437AD
0x1800437a1  test    [rcx+1Ch], dil
0x1800437a5  jz      short loc_1800437AD
0x1800437a7  cmp     byte ptr [rcx+19h], 4
0x1800437ab  jnb     short loc_1800437B0
0x1800437ad  mov     dil, r15b
0x1800437b0  cmp     cs:WPP_RECORDER_INITIALIZED, rbx
0x1800437b7  setnz   r8b
0x1800437bb  test    dil, dil
0x1800437be  jnz     short loc_1800437C9
0x1800437c0  test    r8b, r8b
0x1800437c3  jz      loc_180043B76
0x1800437c9  mov     qword ptr [rsp+370h+var_328], r14
0x1800437ce  mov     dword ptr [rsp+370h+var_330], eax
0x1800437d2  mov     word ptr [rsp+370h+lpcchClass], 47h ; 'G'
0x1800437d9  mov     r9, [rcx+28h]
0x1800437dd  mov     dl, dil
0x1800437e0  mov     rcx, [rcx+10h]
0x1800437e4  call    WPP_RECORDER_AND_TRACE_SF_lq
0x1800437e9  jmp     loc_180043B76
0x1800437ee  lea     rcx, [rbp+270h+var_2F0]
0x1800437f2  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x1800437f7  nop
0x1800437f8  mov     rbx, [rsp+370h+var_310]
0x1800437fd  mov     esi, [rsp+370h+var_320]
0x180043801  shl     rsi, 5
0x180043805  add     rsi, rbx
0x180043808  jmp     loc_180043908
0x18004380d  mov     rax, [rbx+18h]
0x180043811  mov     [rsp+370h+phkResult], rax
0x180043816  mov     r9d, [rbx+10h]
0x18004381a  xor     r8d, r8d
0x18004381d  xor     edx, edx
0x18004381f  lea     rcx, DEVPKEY_Device_ContainerId
0x180043826  call    cs:__imp_DevFindProperty
0x18004382c  test    rax, rax
0x18004382f  jz      loc_180043904
0x180043835  mov     r8d, 27h ; '''; cchMax
0x18004383b  lea     rdx, [rbp+270h+sz]; lpsz
0x180043842  mov     rcx, [rax+28h]; rguid
0x180043846  call    cs:__imp_StringFromGUID2
0x18004384c  test    eax, eax
0x18004384e  jz      loc_180043904
0x180043854  lea     rdx, [rbp+270h+sz]
0x18004385b  lea     rcx, [rbp+270h+var_2B0]
0x18004385f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043864  nop
0x180043865  lea     r8, [rbp+270h+var_2B0]
0x180043869  lea     rdx, [rbp+270h+var_2E0]
0x18004386d  lea     rcx, [rbp+270h+var_2F0]
0x180043871  call    ??$_Emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Emplace<std::wstring>(std::wstring &&)
0x180043876  nop
0x180043877  lea     rcx, [rbp+270h+var_2B0]
0x18004387b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043880  cmp     [rbp+270h+var_2D8], r15b
0x180043884  jz      short loc_180043904
0x180043886  mov     rcx, cs:WPP_GLOBAL_Control
0x18004388d  cmp     rcx, r13
0x180043890  jz      short loc_1800438A1
0x180043892  test    [rcx+1Ch], dil
0x180043896  jz      short loc_1800438A1
0x180043898  cmp     byte ptr [rcx+19h], 5
0x18004389c  mov     dl, dil
0x18004389f  jnb     short loc_1800438A4
0x1800438a1  mov     dl, r15b
0x1800438a4  lea     rax, WPP_RECORDER_INITIALIZED
0x1800438ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800438b2  jz      short loc_1800438BE
0x1800438b4  cmp     [rcx+30h], r15w
0x1800438b9  mov     r8b, dil
0x1800438bc  jnz     short loc_1800438C1
0x1800438be  mov     r8b, r15b
0x1800438c1  test    dl, dl
0x1800438c3  jnz     short loc_1800438CA
0x1800438c5  test    r8b, r8b
0x1800438c8  jz      short loc_180043904
0x1800438ca  mov     qword ptr [rsp+370h+var_328], r14; char
0x1800438cf  lea     rax, [rbp+270h+sz]
0x1800438d6  mov     qword ptr [rsp+370h+var_330], rax; __int64
0x1800438db  lea     rax, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x1800438e2  mov     [rsp+370h+lpftLastWriteTime], rax; MessageGuid
0x1800438e7  mov     word ptr [rsp+370h+lpcchClass], 48h ; 'H'; __int16
0x1800438ee  mov     dword ptr [rsp+370h+lpClass], edi; int
0x1800438f2  mov     byte ptr [rsp+370h+phkResult], 5; char
0x1800438f7  mov     r9, [rcx+28h]
0x1800438fb  mov     rcx, [rcx+10h]; LoggerHandle
0x1800438ff  call    WPP_RECORDER_AND_TRACE_SF_Sq
0x180043904  add     rbx, 20h ; ' '
0x180043908  cmp     rbx, rsi
0x18004390b  jnz     loc_18004380D
0x180043911  xorps   xmm0, xmm0
0x180043914  movdqu  [rsp+370h+var_308], xmm0
0x18004391a  mov     [rsp+370h+var_2F8], r15
0x18004391f  mov     [rsp+370h+hKey], r15
0x180043924  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Bt"...
0x18004392b  lea     rcx, [rbp+270h+var_250]
0x18004392f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180043934  nop
0x180043935  mov     rdx, rax
0x180043938  lea     rcx, [rbp+270h+var_270]
0x18004393c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180043941  nop
0x180043942  lea     r8, [r14+0F8h]
0x180043949  mov     rdx, rax
0x18004394c  lea     rcx, [rbp+270h+var_290]
0x180043950  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180043955  nop
0x180043956  lea     rcx, [rbp+270h+var_270]
0x18004395a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004395f  nop
0x180043960  lea     rcx, [rbp+270h+var_250]
0x180043964  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043969  xor     edx, edx
0x18004396b  lea     rcx, [rsp+370h+hKey]
0x180043970  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043975  lea     rcx, [rbp+270h+var_290]
0x180043979  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004397e  mov     rdx, rax; lpSubKey
0x180043981  lea     rax, [rsp+370h+hKey]
0x180043986  mov     [rsp+370h+phkResult], rax; phkResult
0x18004398b  mov     r9d, 20019h; samDesired
0x180043991  xor     r8d, r8d; ulOptions
0x180043994  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004399b  call    cs:__imp_RegOpenKeyExW
0x1800439a1  test    eax, eax
0x1800439a3  jnz     loc_180043AE2
0x1800439a9  mov     [rsp+370h+cchName], 27h ; '''
0x1800439b1  mov     esi, r15d
0x1800439b4  xor     edx, edx
0x1800439b6  jmp     loc_180043AAF
0x1800439bb  mov     [rsp+370h+cchName], 27h ; '''
0x1800439c3  lea     rdx, [rbp+270h+sz]
0x1800439ca  lea     rcx, [rbp+270h+var_2B0]
0x1800439ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800439d3  lea     r8, [rbp+270h+var_2B0]
0x1800439d7  lea     rdx, [rbp+270h+var_2E0]
0x1800439db  lea     rcx, [rbp+270h+var_2F0]
0x1800439df  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1800439e4  lea     r8, [rbp+270h+var_2B0]
0x1800439e8  mov     rdx, [rax+10h]
0x1800439ec  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,_GUID>,void *> * const,std::wstring const &)
0x1800439f1  mov     bl, al
0x1800439f3  lea     rcx, [rbp+270h+var_2B0]
0x1800439f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800439fc  test    bl, bl
0x1800439fe  jnz     loc_180043AAB
0x180043a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a0b  cmp     rcx, r13
0x180043a0e  jz      short loc_180043A1F
0x180043a10  test    [rcx+1Ch], dil
0x180043a14  jz      short loc_180043A1F
0x180043a16  cmp     byte ptr [rcx+19h], 5
0x180043a1a  mov     dl, dil
0x180043a1d  jnb     short loc_180043A22
0x180043a1f  mov     dl, r15b
0x180043a22  lea     rax, WPP_RECORDER_INITIALIZED
0x180043a29  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180043a30  jz      short loc_180043A3C
0x180043a32  cmp     [rcx+30h], r15w
0x180043a37  mov     r8b, dil
0x180043a3a  jnz     short loc_180043A3F
0x180043a3c  mov     r8b, r15b
0x180043a3f  test    dl, dl
0x180043a41  jnz     short loc_180043A48
0x180043a43  test    r8b, r8b
0x180043a46  jz      short loc_180043A82
0x180043a48  mov     qword ptr [rsp+370h+var_328], r14; char
0x180043a4d  lea     rax, [rbp+270h+sz]
0x180043a54  mov     qword ptr [rsp+370h+var_330], rax; __int64
0x180043a59  lea     rax, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x180043a60  mov     [rsp+370h+lpftLastWriteTime], rax; MessageGuid
0x180043a65  mov     word ptr [rsp+370h+lpcchClass], 49h ; 'I'; __int16
  ... truncated ...
```
