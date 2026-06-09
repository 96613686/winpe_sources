# CMidiDeviceManager::UseFallbackMidi1PortDefinition(ushort const *,winrt::Windows::Devices::Enumeration::DeviceInformation,std::map<uint,_PORT_INFO,std::less<uint>,std::allocator<std::pair<uint const,_PORT_INFO>>> * const)

- ea: `0x1400351b4`
- end: `0x140035506`
- name: `?UseFallbackMidi1PortDefinition@CMidiDeviceManager@@AEAAJPEBGUDeviceInformation@Enumeration@Devices@Windows@winrt@@QEAV?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@@Z`
- size: `850`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x140032ff4`

## callees

- `0x140001ce8`
- `0x1400054c0`
- `0x1400060ec`
- `0x14000617c`
- `0x1400061e8`
- `0x1400072d4`
- `0x140007c20`
- `0x14000984c`
- `0x14000c7f4`
- `0x14000cc2c`
- `0x14000cd78`
- `0x14001440c`
- `0x14001fa84`
- `0x1400272cc`
- `0x140029128`
- `0x14003182c`
- `0x1400351b4`
- `0x14005a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400354c7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1400354c7`

## string_xrefs

- `0x1400352cd`: `Discovery has completed. Using fallback WinMM port definitions`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CMidiDeviceManager::UseFallbackMidi1PortDefinition(
        wchar_t *a1,
        void *a2,
        const char **a3,
        __int64 a4)
{
  __int64 v4; // r13
  int v8; // r12d
  _DWORD *v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  const char *v12; // rdx
  const char *v13; // rcx
  struct winrt::impl::shared_hstring_header *v14; // rbx
  _DWORD *v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int i; // r14d
  unsigned int v19; // eax
  __int64 v20; // r13
  bool v21; // bl
  __int64 v22; // rax
  __int64 v23; // r8
  void **v24; // rcx
  unsigned __int64 v25; // rdx
  char *v26; // rsi
  __int64 v27; // rbx
  __int64 v28; // rax
  const wchar_t *v29; // rdx
  unsigned __int64 v30; // r8
  unsigned __int64 v31; // r8
  __int128 *v32; // rdx
  __int64 v33; // rax
  void *v34; // rbx
  int v35; // eax
  HANDLE ProcessHeap; // rax
  const char *v38; // [rsp+40h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-51h] BYREF
  const wchar_t *v40; // [rsp+50h] [rbp-49h] BYREF
  const char **v41; // [rsp+58h] [rbp-41h] BYREF
  __int64 v42; // [rsp+60h] [rbp-39h]
  const char **v43; // [rsp+68h] [rbp-31h]
  __int128 v44; // [rsp+70h] [rbp-29h] BYREF
  __int128 v45; // [rsp+80h] [rbp-19h]
  _OWORD v46[2]; // [rsp+90h] [rbp-9h] BYREF

  v4 = a4;
  v42 = a4;
  v43 = a3;
  v8 = 0;
  LODWORD(v38) = 0;
  v9 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  v12 = "CMidiDeviceManager::UseFallbackMidi1PortDefinition";
  if ( *v9 > 4u )
  {
    lpMem = a2;
    v38 = (const char *)L"Enter";
    v40 = a1;
    v41 = (const char **)"CMidiDeviceManager::UseFallbackMidi1PortDefinition";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (__int64)v9,
      (__int64)byte_14008996D,
      v10,
      v11,
      &v41,
      (__int64)&v40,
      &v38,
      &lpMem);
  }
  v41 = &v38;
  v13 = *a3;
  v38 = v13;
  if ( v13 )
    (*(void (__fastcall **)(const char *, const char *))(*(_QWORD *)v13 + 8LL))(v13, v12);
  v14 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)0x2A, (unsigned int)v12);
  memcpy_s((char *)v14 + 28, 0x54u, L"{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} 140", 0x54u);
  lpMem = v14;
  if ( WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<bool>(
         (volatile signed __int32 **)&lpMem,
         &v38) )
  {
    v15 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v15 > 4u )
    {
      v41 = (const char **)a2;
      v40 = L"Discovery has completed. Using fallback WinMM port definitions";
      lpMem = a1;
      v38 = "CMidiDeviceManager::UseFallbackMidi1PortDefinition";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (__int64)v15,
        (__int64)word_140089312,
        v16,
        v17,
        &v38,
        (__int64)&lpMem,
        &v40,
        &v41);
    }
    for ( i = 0; i < 2; ++i )
    {
      LODWORD(v38) = 0;
      v19 = 0;
      while ( v19 <= 0xF )
      {
        v20 = 16LL * i + v4;
        *(_BYTE *)std::map<unsigned int,_PORT_INFO>::operator[](v20, &v38) = 1;
        v21 = (_DWORD)v38 == 0;
        *(_BYTE *)(std::map<unsigned int,_PORT_INFO>::operator[](v20, &v38) + 1) = v21;
        *(_DWORD *)(std::map<unsigned int,_PORT_INFO>::operator[](v20, &v38) + 40) = i;
        v22 = std::map<unsigned int,_PORT_INFO>::operator[](v20, &v38);
        v24 = (void **)(v22 + 8);
        v25 = -1;
        do
          ++v25;
        while ( *((_WORD *)a2 + v25) );
        if ( v25 > *(_QWORD *)(v22 + 32) )
        {
          ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
            v24,
            v25,
            v23,
            a2);
        }
        else
        {
          if ( *(_QWORD *)(v22 + 32) <= 7u )
            v26 = (char *)(v22 + 8);
          else
            v26 = (char *)*v24;
          *(_QWORD *)(v22 + 24) = v25;
          v27 = 2 * v25;
          memmove_0(v26, a2, 2 * v25);
          *(_WORD *)&v26[v27] = 0;
        }
        v28 = winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(
                a3,
                &lpMem);
        if ( *(_QWORD *)v28 )
          v29 = *(const wchar_t **)(*(_QWORD *)v28 + 16LL);
        else
          v29 = &S2;
        v44 = 0;
        v45 = 0;
        v30 = -1;
        do
          ++v30;
        while ( v29[v30] );
        std::wstring::_Construct<1,unsigned short const *>((char **)&v44, v29, v30);
        memset(v46, 0, sizeof(v46));
        v31 = 31;
        if ( (unsigned __int64)v45 < 0x1F )
          v31 = v45;
        v32 = &v44;
        if ( *((_QWORD *)&v45 + 1) > 7u )
          v32 = (__int128 *)v44;
        std::wstring::_Construct<1,unsigned short const *>((char **)v46, v32, v31);
        v33 = std::map<unsigned int,_PORT_INFO>::operator[](v20, &v38);
        std::wstring::operator=((char **)(v33 + 48), (__int64)v46);
        std::wstring::~wstring((char **)v46);
        std::wstring::~wstring((char **)&v44);
        v34 = lpMem;
        if ( lpMem )
        {
          v35 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v35 )
          {
            if ( v35 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, v34);
          }
          lpMem = 0;
        }
        v8 |= 1u;
        v19 = (_DWORD)v38 + 1;
        LODWORD(v38) = (_DWORD)v38 + 1;
        v4 = v42;
      }
    }
  }
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return 0;
}

```

## disassembly

```asm
0x1400351b4  mov     [rsp-8+arg_0], rbx
0x1400351b9  push    rbp
0x1400351ba  push    rsi
0x1400351bb  push    rdi
0x1400351bc  push    r12
0x1400351be  push    r13
0x1400351c0  push    r14
0x1400351c2  push    r15
0x1400351c4  lea     rbp, [rsp-27h]
0x1400351c9  sub     rsp, 0C0h
0x1400351d0  mov     rax, cs:__security_cookie
0x1400351d7  xor     rax, rsp
0x1400351da  mov     [rbp+57h+var_40], rax
0x1400351de  mov     r13, r9
0x1400351e1  mov     [rbp+57h+var_90], r9
0x1400351e5  mov     rdi, r8
0x1400351e8  mov     r15, rdx
0x1400351eb  mov     rsi, rcx
0x1400351ee  mov     [rbp+57h+var_88], r8
0x1400351f2  xor     r14d, r14d
0x1400351f5  mov     r12d, r14d
0x1400351f8  mov     dword ptr [rbp+57h+var_B0], r14d
0x1400351fc  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x140035201  mov     rcx, [rax+8]
0x140035205  mov     eax, [rcx]
0x140035207  lea     rdx, aCmidideviceman_14; "CMidiDeviceManager::UseFallbackMidi1Por"...
0x14003520e  cmp     eax, 4
0x140035211  jbe     short loc_14003525A
0x140035213  mov     [rbp+57h+lpMem], r15
0x140035217  lea     rax, aEnter; "Enter"
0x14003521e  mov     [rbp+57h+var_B0], rax
0x140035222  mov     [rbp+57h+var_A0], rsi
0x140035226  mov     [rbp+57h+var_98], rdx
0x14003522a  lea     rax, [rbp+57h+lpMem]
0x14003522e  mov     [rsp+0F0h+var_B8], rax
0x140035233  lea     rax, [rbp+57h+var_B0]
0x140035237  mov     [rsp+0F0h+var_C0], rax
0x14003523c  lea     rax, [rbp+57h+var_A0]
0x140035240  mov     [rsp+0F0h+var_C8], rax
0x140035245  lea     rax, [rbp+57h+var_98]
0x140035249  mov     [rsp+0F0h+var_D0], rax
0x14003524e  lea     rdx, byte_14008996D
0x140035255  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14003525a  lea     rax, [rbp+57h+var_B0]
0x14003525e  mov     [rbp+57h+var_98], rax
0x140035262  mov     rcx, [rdi]
0x140035265  mov     [rbp+57h+var_B0], rcx
0x140035269  test    rcx, rcx
0x14003526c  jz      short loc_14003527B
0x14003526e  mov     rax, [rcx]
0x140035271  mov     rax, [rax+8]
0x140035275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003527a  nop
0x14003527b  mov     ecx, 2Ah ; '*'; this
0x140035280  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x140035285  mov     rbx, rax
0x140035288  lea     rcx, [rax+1Ch]; Destination
0x14003528c  mov     edx, 54h ; 'T'; DestinationSize
0x140035291  mov     r9d, edx; SourceSize
0x140035294  lea     r8, a3f114a6a11fa4b_16; "{3F114A6A-11FA-4BD0-9D2C-6B7780CD80AD} "...
0x14003529b  call    memcpy_s
0x1400352a0  mov     [rbp+57h+lpMem], rbx
0x1400352a4  lea     rdx, [rbp+57h+var_B0]
0x1400352a8  lea     rcx, [rbp+57h+lpMem]
0x1400352ac  call    ??$SafeGetSwdPropertyFromDeviceInformation@_N@WindowsMidiServicesInternal@@YA_NUhstring@winrt@@UDeviceInformation@Enumeration@Devices@Windows@2@_N@Z; WindowsMidiServicesInternal::SafeGetSwdPropertyFromDeviceInformation<bool>(winrt::hstring,winrt::Windows::Devices::Enumeration::DeviceInformation,bool)
0x1400352b1  test    al, al
0x1400352b3  jz      loc_1400354CE
0x1400352b9  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x1400352be  mov     rcx, [rax+8]
0x1400352c2  mov     eax, [rcx]
0x1400352c4  cmp     eax, 4
0x1400352c7  jbe     short loc_140035317
0x1400352c9  mov     [rbp+57h+var_98], r15
0x1400352cd  lea     rax, aDiscoveryHasCo; "Discovery has completed. Using fallback"...
0x1400352d4  mov     [rbp+57h+var_A0], rax
0x1400352d8  mov     [rbp+57h+lpMem], rsi
0x1400352dc  lea     rax, aCmidideviceman_14; "CMidiDeviceManager::UseFallbackMidi1Por"...
0x1400352e3  mov     [rbp+57h+var_B0], rax
0x1400352e7  lea     rax, [rbp+57h+var_98]
0x1400352eb  mov     [rsp+0F0h+var_B8], rax
0x1400352f0  lea     rax, [rbp+57h+var_A0]
0x1400352f4  mov     [rsp+0F0h+var_C0], rax
0x1400352f9  lea     rax, [rbp+57h+lpMem]
0x1400352fd  mov     [rsp+0F0h+var_C8], rax
0x140035302  lea     rax, [rbp+57h+var_B0]
0x140035306  mov     [rsp+0F0h+var_D0], rax
0x14003530b  lea     rdx, word_140089312
0x140035312  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x140035317  xor     esi, esi
0x140035319  mov     r14d, esi
0x14003531c  mov     dword ptr [rbp+57h+var_B0], esi
0x14003531f  mov     eax, esi
0x140035321  cmp     eax, 0Fh
0x140035324  ja      loc_1400354B8
0x14003532a  mov     eax, r14d
0x14003532d  shl     rax, 4
0x140035331  add     r13, rax
0x140035334  lea     rdx, [rbp+57h+var_B0]
0x140035338  mov     rcx, r13
0x14003533b  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x140035340  mov     byte ptr [rax], 1
0x140035343  cmp     dword ptr [rbp+57h+var_B0], esi
0x140035346  setz    bl
0x140035349  lea     rdx, [rbp+57h+var_B0]
0x14003534d  mov     rcx, r13
0x140035350  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x140035355  mov     [rax+1], bl
0x140035358  lea     rdx, [rbp+57h+var_B0]
0x14003535c  mov     rcx, r13
0x14003535f  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x140035364  mov     [rax+28h], r14d
0x140035368  lea     rdx, [rbp+57h+var_B0]
0x14003536c  mov     rcx, r13
0x14003536f  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x140035374  lea     rcx, [rax+8]
0x140035378  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14003537c  inc     rdx
0x14003537f  cmp     [r15+rdx*2], si
0x140035384  jnz     short loc_14003537C
0x140035386  cmp     rdx, [rcx+18h]
0x14003538a  ja      short loc_1400353BB
0x14003538c  cmp     qword ptr [rcx+18h], 7
0x140035391  jbe     short loc_140035398
0x140035393  mov     rsi, [rcx]
0x140035396  jmp     short loc_14003539B
0x140035398  mov     rsi, rcx
0x14003539b  mov     [rcx+10h], rdx
0x14003539f  lea     rbx, [rdx+rdx]
0x1400353a3  mov     r8, rbx; Size
0x1400353a6  mov     rdx, r15; Src
0x1400353a9  mov     rcx, rsi; void *
0x1400353ac  call    memmove_0
0x1400353b1  xor     eax, eax
0x1400353b3  mov     [rbx+rsi], ax
0x1400353b7  xor     esi, esi
0x1400353b9  jmp     short loc_1400353C3
0x1400353bb  mov     r9, r15
0x1400353be  call    ??$_Reallocate_for@V_lambda_1_@?1???$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV23@QEBG_K@Z@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1???$_Assign@G@01@AEAAAEAV01@QEBG0@Z@PEBG@Z; std::wstring::_Reallocate_for<`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *>(unsigned __int64,`std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)'::`2'::_lambda_1_,ushort const *)
0x1400353c3  lea     rdx, [rbp+57h+lpMem]
0x1400353c7  mov     rcx, rdi
0x1400353ca  call    ?Name@?$consume_Windows_Devices_Enumeration_IDeviceInformation@UIDeviceInformation@Enumeration@Devices@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Devices_Enumeration_IDeviceInformation<winrt::Windows::Devices::Enumeration::IDeviceInformation>::Name(void)
0x1400353cf  nop
0x1400353d0  mov     rdx, [rax]
0x1400353d3  test    rdx, rdx
0x1400353d6  jz      short loc_1400353DE
0x1400353d8  mov     rdx, [rdx+10h]
0x1400353dc  jmp     short loc_1400353E5
0x1400353de  lea     rdx, S2
0x1400353e5  xorps   xmm0, xmm0
0x1400353e8  movups  [rbp+57h+var_80], xmm0
0x1400353ec  xorps   xmm1, xmm1
0x1400353ef  movdqu  [rbp+57h+var_70], xmm1
0x1400353f4  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400353f8  inc     r8
0x1400353fb  cmp     [rdx+r8*2], si
0x140035400  jnz     short loc_1400353F8
0x140035402  lea     rcx, [rbp+57h+var_80]
0x140035406  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14003540b  nop
0x14003540c  xorps   xmm0, xmm0
0x14003540f  movups  [rbp+57h+var_60], xmm0
0x140035413  xorps   xmm1, xmm1
0x140035416  movdqu  [rbp+57h+var_50], xmm1
0x14003541b  mov     r8d, 1Fh
0x140035421  cmp     qword ptr [rbp+57h+var_70], r8
0x140035425  cmovb   r8, qword ptr [rbp+57h+var_70]
0x14003542a  lea     rdx, [rbp+57h+var_80]
0x14003542e  cmp     qword ptr [rbp+57h+var_70+8], 7
0x140035433  cmova   rdx, qword ptr [rbp+57h+var_80]
0x140035438  lea     rcx, [rbp+57h+var_60]
0x14003543c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140035441  nop
0x140035442  lea     rdx, [rbp+57h+var_B0]
0x140035446  mov     rcx, r13
0x140035449  call    ??A?$map@IU_PORT_INFO@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIU_PORT_INFO@@@std@@@3@@std@@QEAAAEAU_PORT_INFO@@AEBI@Z; std::map<uint,_PORT_INFO>::operator[](uint const &)
0x14003544e  lea     rcx, [rax+30h]
0x140035452  lea     rdx, [rbp+57h+var_60]
0x140035456  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14003545b  nop
0x14003545c  lea     rcx, [rbp+57h+var_60]; void *
0x140035460  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140035465  nop
0x140035466  lea     rcx, [rbp+57h+var_80]; void *
0x14003546a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14003546f  nop
0x140035470  mov     rbx, [rbp+57h+lpMem]
0x140035474  test    rbx, rbx
0x140035477  jz      short loc_1400354A3
0x140035479  or      eax, 0FFFFFFFFh
0x14003547c  lock xadd [rbx+18h], eax
0x140035481  sub     eax, 1
0x140035484  jnz     short loc_14003549B
0x140035486  nop
0x140035487  call    WINRT_IMPL_GetProcessHeap
0x14003548c  mov     rcx, rax; hHeap
0x14003548f  mov     r8, rbx; lpMem
0x140035492  xor     edx, edx; dwFlags
0x140035494  call    WINRT_IMPL_HeapFree
0x140035499  jmp     short loc_14003549F
0x14003549b  test    eax, eax
0x14003549d  js      short loc_1400354C7
0x14003549f  mov     [rbp+57h+lpMem], rsi
0x1400354a3  or      r12d, 1
0x1400354a7  mov     eax, dword ptr [rbp+57h+var_B0]
0x1400354aa  inc     eax
0x1400354ac  mov     dword ptr [rbp+57h+var_B0], eax
0x1400354af  mov     r13, [rbp+57h+var_90]
0x1400354b3  jmp     loc_140035321
0x1400354b8  inc     r14d
0x1400354bb  cmp     r14d, 2
0x1400354bf  jb      loc_14003531C
0x1400354c5  jmp     short loc_1400354D0
0x1400354c7  call    cs:__imp_abort
0x1400354ce  xor     esi, esi
0x1400354d0  cmp     [rdi], rsi
0x1400354d3  jz      short loc_1400354DD
0x1400354d5  mov     rcx, rdi
0x1400354d8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1400354dd  xor     eax, eax
0x1400354df  mov     rcx, [rbp+57h+var_40]
0x1400354e3  xor     rcx, rsp; StackCookie
0x1400354e6  call    __security_check_cookie
0x1400354eb  mov     rbx, [rsp+0F0h+arg_0]
0x1400354f3  add     rsp, 0C0h
0x1400354fa  pop     r15
0x1400354fc  pop     r14
0x1400354fe  pop     r13
0x140035500  pop     r12
0x140035502  pop     rdi
0x140035503  pop     rsi
0x140035504  pop     rbp
0x140035505  retn
```
