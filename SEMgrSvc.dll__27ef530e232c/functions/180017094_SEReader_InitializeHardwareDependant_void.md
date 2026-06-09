# SEReader::InitializeHardwareDependant(void)

- ea: `0x180017094`
- end: `0x1800174e0`
- name: `?InitializeHardwareDependant@SEReader@@AEAAJXZ`
- size: `1100`
- prototype: `__int64 __fastcall(SEReader *__hidden this)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update`

## callers

- `0x180016e48`
- `0x18001752c`

## callees

- `0x1800049a0`
- `0x1800049c4`
- `0x180004e9c`
- `0x180004ec0`
- `0x180005858`
- `0x18000c964`
- `0x180016284`
- `0x180016578`
- `0x1800166b0`
- `0x180016874`
- `0x180016afc`
- `0x180017094`
- `0x180017cb4`
- `0x1800191b0`
- `0x180019898`
- `0x18001a344`
- `0x18001ad58`
- `0x18001f5a0`
- `0x18001f6c0`
- `0x18001fb2c`
- `0x18007ce94`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017497`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800171f2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017270`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017497`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017100`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017100`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001732f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001738f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001732f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001738f`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800172da`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x1800172da`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180017291`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800172c2`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x180017291`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x1800172c2`

## string_xrefs

- `0x180017250`: `onecoreuap\ds\nfc\product\semanagement\service\src\sereader.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall SEReader::InitializeHardwareDependant(SEReader *this)
{
  RfFieldEventHandler *v2; // rax
  NFCConnector *v3; // rdi
  RfFieldEventHandler *v4; // rax
  volatile signed __int32 *v5; // rdi
  NFCConnector *v6; // rcx
  int updated; // edi
  const unsigned __int16 *v8; // r14
  const unsigned __int16 *v9; // rdx
  int DeviceInterfaceGuidProperty; // eax
  __int64 *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rcx
  RfFieldEventHandler *v14; // rax
  RfFieldEventHandler *v15; // rdi
  RfFieldEventHandler *v16; // rax
  RfFieldEventHandler *v17; // rdi
  __int64 v18; // rdi
  int v19; // eax
  SEReader *v20; // rcx
  struct _SECURE_ELEMENT_ENDPOINT_INFO *v21; // r15
  const struct _SECURE_ELEMENT_ENDPOINT_INFO *i; // r14
  int v23; // eax
  struct SecureElement *v24; // rdi
  struct SecureElement *v26; // [rsp+20h] [rbp-E0h] BYREF
  RfFieldEventHandler *v27; // [rsp+28h] [rbp-D8h]
  struct _SECURE_ELEMENT_ENDPOINT_INFO *v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v29; // [rsp+40h] [rbp-C0h]
  char *v30; // [rsp+48h] [rbp-B8h]
  char v31; // [rsp+50h] [rbp-B0h]
  _DWORD v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct SecureElement *v33; // [rsp+70h] [rbp-90h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]

  memset_0(v32, 0, 0x1A0u);
  v26 = (struct SecureElement *)-1LL;
  if ( !*((_DWORD *)this + 50) )
  {
    v30 = (char *)this + 160;
    EnterCriticalSection((LPCRITICAL_SECTION)this + 4);
    v31 = 1;
    *(_OWORD *)v28 = 0;
    v29 = 0;
    *((_DWORD *)this + 50) = 1;
    v2 = (RfFieldEventHandler *)operator new(0xB0u, (const struct std::nothrow_t *)std::nothrow);
    v27 = v2;
    if ( v2 )
      v3 = NFCConnector::NFCConnector(v2);
    else
      v3 = 0;
    v4 = (RfFieldEventHandler *)operator new(0x18u);
    v27 = v4;
    *(_OWORD *)v4 = 0;
    *((_DWORD *)v4 + 2) = 1;
    *((_DWORD *)v4 + 3) = 1;
    *(_QWORD *)v4 = &std::_Ref_count<NFCConnector>::`vftable';
    *((_QWORD *)v4 + 2) = v3;
    *((_QWORD *)this + 26) = v3;
    v5 = (volatile signed __int32 *)*((_QWORD *)this + 27);
    *((_QWORD *)this + 27) = v4;
    if ( v5 )
    {
      if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
    }
    v6 = (NFCConnector *)*((_QWORD *)this + 26);
    if ( !v6 )
    {
      updated = -2147024882;
LABEL_11:
      std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(v28);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 4);
LABEL_46:
      SEReader::DeinitializeHardwareDependent(this);
      return (unsigned int)updated;
    }
    v8 = (const unsigned __int16 *)((char *)this + 96);
    if ( *((_QWORD *)this + 15) <= 7u )
      v9 = (const unsigned __int16 *)((char *)this + 96);
    else
      v9 = *(const unsigned __int16 **)v8;
    updated = NFCConnector::Initialize(v6, v9, (void **)&v26);
    if ( updated < 0 )
      goto LABEL_11;
    if ( *((_QWORD *)this + 15) > 7u )
      v8 = *(const unsigned __int16 **)v8;
    DeviceInterfaceGuidProperty = NfcDriverQuery::GetDeviceInterfaceGuidProperty(
                                    v8,
                                    &DEVPKEY_Device_ContainerId,
                                    (struct _GUID *)this + 14);
    updated = DeviceInterfaceGuidProperty;
    if ( DeviceInterfaceGuidProperty < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x197,
        (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\sereader.cpp",
        (const char *)(unsigned int)DeviceInterfaceGuidProperty,
        (int)v26);
      std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(v28);
      LeaveCriticalSection((LPCRITICAL_SECTION)this + 4);
      return (unsigned int)updated;
    }
    v11 = (__int64 *)((char *)this + 272);
    v12 = *((_QWORD *)this + 34);
    *((_QWORD *)this + 34) = 0;
    if ( v12 )
      CM_Unregister_Notification();
    v32[0] = 416;
    v32[2] = 1;
    v33 = v26;
    if ( v26 != (struct SecureElement *)-1LL )
    {
      v13 = *v11;
      *v11 = 0;
      if ( v13 )
        CM_Unregister_Notification();
      if ( (unsigned int)CM_Register_Notification(v32, this, &SEReader::HandleDeviceNotification, (char *)this + 272) )
      {
        updated = -2147418113;
        goto LABEL_11;
      }
    }
    v27 = (RfFieldEventHandler *)operator new(0x70u);
    v14 = RfFieldEventHandler::RfFieldEventHandler(v27, (SEReader *)((char *)this + 8), 1);
    v15 = (RfFieldEventHandler *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = v14;
    if ( v15 )
    {
      RfFieldEventHandler::Uninitialize(v15);
      DeleteCriticalSection((LPCRITICAL_SECTION)v15);
      operator delete(v15);
    }
    RfFieldEventHandler::Initialize(*((PVOID *)this + 18), *((struct NFCConnector **)this + 26));
    v27 = (RfFieldEventHandler *)operator new(0x70u);
    v16 = RfFieldEventHandler::RfFieldEventHandler(v27, (SEReader *)((char *)this + 8), 0);
    v17 = (RfFieldEventHandler *)*((_QWORD *)this + 19);
    *((_QWORD *)this + 19) = v16;
    if ( v17 )
    {
      RfFieldEventHandler::Uninitialize(v17);
      DeleteCriticalSection((LPCRITICAL_SECTION)v17);
      operator delete(v17);
    }
    RfFieldEventHandler::Initialize(*((PVOID *)this + 19), *((struct NFCConnector **)this + 26));
    v18 = *((_QWORD *)this + 26);
    LODWORD(v26) = 0;
    if ( NfcRegUtils::GetDword(
           (const struct NfcRegistryLocation *)&qword_1800A1BE8,
           L"DisableHCESupport",
           (unsigned int *)&v26) >= 0 )
    {
      v19 = (int)v26;
    }
    else
    {
      v19 = 0;
      LODWORD(v26) = 0;
    }
    updated = NFCConnector::EnumerateSE(v18, v19 != 0, v28);
    if ( updated < 0 )
      goto LABEL_11;
    v21 = v28[1];
    for ( i = v28[0]; i != v21; i = (const struct _SECURE_ELEMENT_ENDPOINT_INFO *)((char *)i + 20) )
    {
      v26 = 0;
      v23 = SEReader::CreateSecureElement(v20, i, &v26);
      v24 = v26;
      if ( v23 >= 0 )
        SEReader::AddSecureElement(this, v26);
      if ( v24 && _InterlockedExchangeAdd((volatile signed __int32 *)v24 + 2, 0xFFFFFFFF) == 1 )
        (**(void (__fastcall ***)(struct SecureElement *, __int64))v24)(v24, 1);
    }
    updated = SEReader::UpdateSecureElementEmulationMode(this, 0, 0);
    if ( updated < 0 )
      goto LABEL_11;
    std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(v28);
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 4);
  }
  updated = SEReader::ApplyCardEmulationPolicy(this);
  if ( updated < 0 )
    goto LABEL_46;
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180017094  mov     [rsp-8+arg_8], rbx
0x180017099  mov     [rsp-8+arg_10], rsi
0x18001709e  push    rbp
0x18001709f  push    rdi
0x1800170a0  push    r13
0x1800170a2  push    r14
0x1800170a4  push    r15
0x1800170a6  lea     rbp, [rsp-110h]
0x1800170ae  sub     rsp, 210h
0x1800170b5  mov     rax, cs:__security_cookie
0x1800170bc  xor     rax, rsp
0x1800170bf  mov     [rbp+130h+var_30], rax
0x1800170c6  mov     rbx, rcx
0x1800170c9  xor     edx, edx; Val
0x1800170cb  mov     r8d, 1A0h; Size
0x1800170d1  lea     rcx, [rsp+230h+var_1D0]; void *
0x1800170d6  call    memset_0
0x1800170db  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800170df  mov     [rsp+230h+var_210], r13; int
0x1800170e4  cmp     dword ptr [rbx+0C8h], 0
0x1800170eb  jnz     loc_18001749D
0x1800170f1  lea     rsi, [rbx+0A0h]
0x1800170f8  mov     [rsp+230h+var_1E8], rsi
0x1800170fd  mov     rcx, rsi; lpCriticalSection
0x180017100  call    cs:__imp_EnterCriticalSection
0x180017106  lea     r15d, [r13+2]
0x18001710a  mov     [rsp+230h+var_1E0], r15b
0x18001710f  xorps   xmm0, xmm0
0x180017112  movdqu  xmmword ptr [rsp+230h+var_200], xmm0
0x180017118  mov     [rsp+230h+var_1F0], 0
0x180017121  mov     [rbx+0C8h], r15d
0x180017128  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001712f  mov     ecx, 0B0h; unsigned __int64
0x180017134  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017139  mov     [rsp+230h+var_208], rax
0x18001713e  test    rax, rax
0x180017141  jz      short loc_180017150
0x180017143  mov     rcx, rax; this
0x180017146  call    ??0NFCConnector@@QEAA@XZ; NFCConnector::NFCConnector(void)
0x18001714b  mov     rdi, rax
0x18001714e  jmp     short loc_180017152
0x180017150  xor     edi, edi
0x180017152  mov     [rsp+230h+var_208], rdi
0x180017157  mov     ecx, 18h; Size
0x18001715c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017161  mov     [rsp+230h+var_208], rax
0x180017166  xorps   xmm0, xmm0
0x180017169  movups  xmmword ptr [rax], xmm0
0x18001716c  mov     [rax+8], r15d
0x180017170  mov     [rax+0Ch], r15d
0x180017174  lea     rcx, ??_7?$_Ref_count@VNFCConnector@@@std@@6B@; const std::_Ref_count<NFCConnector>::`vftable'
0x18001717b  mov     [rax], rcx
0x18001717e  mov     [rax+10h], rdi
0x180017182  mov     [rbx+0D0h], rdi
0x180017189  mov     rdi, [rbx+0D8h]
0x180017190  mov     [rbx+0D8h], rax
0x180017197  test    rdi, rdi
0x18001719a  jz      short loc_1800171D3
0x18001719c  mov     eax, r13d
0x18001719f  lock xadd [rdi+8], eax
0x1800171a4  add     eax, r13d
0x1800171a7  jnz     short loc_1800171D3
0x1800171a9  mov     rax, [rdi]
0x1800171ac  mov     rcx, rdi
0x1800171af  mov     rax, [rax]
0x1800171b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171b7  mov     eax, r13d
0x1800171ba  lock xadd [rdi+0Ch], eax
0x1800171bf  add     eax, r13d
0x1800171c2  jnz     short loc_1800171D3
0x1800171c4  mov     rax, [rdi]
0x1800171c7  mov     rcx, rdi
0x1800171ca  mov     rax, [rax+8]
0x1800171ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171d3  mov     rcx, [rbx+0D0h]; this
0x1800171da  test    rcx, rcx
0x1800171dd  jnz     short loc_1800171FD
0x1800171df  mov     edi, 8007000Eh
0x1800171e4  lea     rcx, [rsp+230h+var_200]
0x1800171e9  call    ??1?$vector@U_SECURE_ELEMENT_ENDPOINT_INFO@@V?$allocator@U_SECURE_ELEMENT_ENDPOINT_INFO@@@std@@@std@@QEAA@XZ; std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(void)
0x1800171ee  nop
0x1800171ef  mov     rcx, rsi; lpCriticalSection
0x1800171f2  call    cs:__imp_LeaveCriticalSection
0x1800171f8  jmp     loc_1800174AB
0x1800171fd  lea     r14, [rbx+60h]
0x180017201  cmp     qword ptr [r14+18h], 7
0x180017206  jbe     short loc_18001720D
0x180017208  mov     rdx, [r14]
0x18001720b  jmp     short loc_180017210
0x18001720d  mov     rdx, r14; Src
0x180017210  lea     r8, [rsp+230h+var_210]; void **
0x180017215  call    ?Initialize@NFCConnector@@QEAAJPEBGPEAPEAX@Z; NFCConnector::Initialize(ushort const *,void * *)
0x18001721a  mov     edi, eax
0x18001721c  test    eax, eax
0x18001721e  js      short loc_1800171E4
0x180017220  cmp     qword ptr [r14+18h], 7
0x180017225  jbe     short loc_18001722A
0x180017227  mov     r14, [r14]
0x18001722a  lea     r8, [rbx+0E0h]; struct _GUID *
0x180017231  lea     rdx, DEVPKEY_Device_ContainerId; struct _DEVPROPKEY *
0x180017238  mov     rcx, r14; unsigned __int16 *
0x18001723b  call    ?GetDeviceInterfaceGuidProperty@NfcDriverQuery@@SAJPEBGAEBU_DEVPROPKEY@@PEAU_GUID@@@Z; NfcDriverQuery::GetDeviceInterfaceGuidProperty(ushort const *,_DEVPROPKEY const &,_GUID *)
0x180017240  mov     edi, eax
0x180017242  test    eax, eax
0x180017244  jns     short loc_18001727B
0x180017246  mov     rcx, [rbp+138h]; this
0x18001724d  mov     r9d, eax; char *
0x180017250  lea     r8, aOnecoreuapDsNf_13; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180017257  mov     edx, 197h; void *
0x18001725c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017261  nop
0x180017262  lea     rcx, [rsp+230h+var_200]
0x180017267  call    ??1?$vector@U_SECURE_ELEMENT_ENDPOINT_INFO@@V?$allocator@U_SECURE_ELEMENT_ENDPOINT_INFO@@@std@@@std@@QEAA@XZ; std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(void)
0x18001726c  nop
0x18001726d  mov     rcx, rsi; lpCriticalSection
0x180017270  call    cs:__imp_LeaveCriticalSection
0x180017276  jmp     loc_1800174B3
0x18001727b  lea     rdi, [rbx+110h]
0x180017282  mov     rcx, [rdi]
0x180017285  mov     qword ptr [rdi], 0
0x18001728c  test    rcx, rcx
0x18001728f  jz      short loc_180017297
0x180017291  call    cs:__imp_CM_Unregister_Notification
0x180017297  mov     [rsp+230h+var_1D0], 1A0h
0x18001729f  mov     [rsp+230h+var_1C8], r15d
0x1800172a4  mov     rax, [rsp+230h+var_210]
0x1800172a9  mov     [rsp+230h+var_1C0], rax
0x1800172ae  cmp     rax, r13
0x1800172b1  jz      short loc_1800172EE
0x1800172b3  mov     rcx, [rdi]
0x1800172b6  mov     qword ptr [rdi], 0
0x1800172bd  test    rcx, rcx
0x1800172c0  jz      short loc_1800172C8
0x1800172c2  call    cs:__imp_CM_Unregister_Notification
0x1800172c8  mov     r9, rdi
0x1800172cb  lea     r8, ?HandleDeviceNotification@SEReader@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; SEReader::HandleDeviceNotification(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x1800172d2  mov     rdx, rbx
0x1800172d5  lea     rcx, [rsp+230h+var_1D0]
0x1800172da  call    cs:__imp_CM_Register_Notification
0x1800172e0  test    eax, eax
0x1800172e2  jz      short loc_1800172EE
0x1800172e4  mov     edi, 8000FFFFh
0x1800172e9  jmp     loc_1800171E4
0x1800172ee  mov     r15d, 70h ; 'p'
0x1800172f4  mov     ecx, r15d; Size
0x1800172f7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800172fc  mov     [rsp+230h+var_208], rax
0x180017301  mov     r8b, 1; bool
0x180017304  lea     rdx, [rbx+8]; struct IRfFieldEventHandlerCallbacks *
0x180017308  mov     rcx, rax; this
0x18001730b  call    ??0RfFieldEventHandler@@QEAA@PEAUIRfFieldEventHandlerCallbacks@@_N@Z; RfFieldEventHandler::RfFieldEventHandler(IRfFieldEventHandlerCallbacks *,bool)
0x180017310  nop
0x180017311  mov     rdi, [rbx+90h]
0x180017318  mov     [rbx+90h], rax
0x18001731f  test    rdi, rdi
0x180017322  jz      short loc_180017341
0x180017324  mov     rcx, rdi; this
0x180017327  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x18001732c  mov     rcx, rdi; lpCriticalSection
0x18001732f  call    cs:__imp_DeleteCriticalSection
0x180017335  nop
0x180017336  mov     edx, r15d
0x180017339  mov     rcx, rdi; Block
0x18001733c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180017341  mov     rdx, [rbx+0D0h]; struct NFCConnector *
0x180017348  mov     rcx, [rbx+90h]; pv
0x18001734f  call    ?Initialize@RfFieldEventHandler@@QEAAJPEAVNFCConnector@@@Z; RfFieldEventHandler::Initialize(NFCConnector *)
0x180017354  mov     rcx, r15; Size
0x180017357  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001735c  mov     [rsp+230h+var_208], rax
0x180017361  xor     r8d, r8d; bool
0x180017364  lea     rdx, [rbx+8]; struct IRfFieldEventHandlerCallbacks *
0x180017368  mov     rcx, rax; this
0x18001736b  call    ??0RfFieldEventHandler@@QEAA@PEAUIRfFieldEventHandlerCallbacks@@_N@Z; RfFieldEventHandler::RfFieldEventHandler(IRfFieldEventHandlerCallbacks *,bool)
0x180017370  nop
0x180017371  mov     rdi, [rbx+98h]
0x180017378  mov     [rbx+98h], rax
0x18001737f  test    rdi, rdi
0x180017382  jz      short loc_1800173A1
0x180017384  mov     rcx, rdi; this
0x180017387  call    ?Uninitialize@RfFieldEventHandler@@QEAAXXZ; RfFieldEventHandler::Uninitialize(void)
0x18001738c  mov     rcx, rdi; lpCriticalSection
0x18001738f  call    cs:__imp_DeleteCriticalSection
0x180017395  nop
0x180017396  mov     rdx, r15
0x180017399  mov     rcx, rdi; Block
0x18001739c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800173a1  mov     rdx, [rbx+0D0h]; struct NFCConnector *
0x1800173a8  mov     rcx, [rbx+98h]; pv
0x1800173af  call    ?Initialize@RfFieldEventHandler@@QEAAJPEAVNFCConnector@@@Z; RfFieldEventHandler::Initialize(NFCConnector *)
0x1800173b4  mov     rdi, [rbx+0D0h]
0x1800173bb  mov     dword ptr [rsp+230h+var_210], 0
0x1800173c3  lea     r8, [rsp+230h+var_210]; unsigned int *
0x1800173c8  lea     rdx, aDisablehcesupp; "DisableHCESupport"
0x1800173cf  lea     rcx, qword_1800A1BE8; struct NfcRegistryLocation *
0x1800173d6  call    ?GetDword@NfcRegUtils@@SAJAEBUNfcRegistryLocation@@PEBGPEAK@Z; NfcRegUtils::GetDword(NfcRegistryLocation const &,ushort const *,ulong *)
0x1800173db  test    eax, eax
0x1800173dd  jns     short loc_1800173E7
0x1800173df  xor     eax, eax
0x1800173e1  mov     dword ptr [rsp+230h+var_210], eax
0x1800173e5  jmp     short loc_1800173EB
0x1800173e7  mov     eax, dword ptr [rsp+230h+var_210]
0x1800173eb  xor     edx, edx
0x1800173ed  test    eax, eax
0x1800173ef  setnz   dl
0x1800173f2  lea     r8, [rsp+230h+var_200]
0x1800173f7  mov     rcx, rdi
0x1800173fa  call    ?EnumerateSE@NFCConnector@@QEAAJKPEAV?$vector@U_SECURE_ELEMENT_ENDPOINT_INFO@@V?$allocator@U_SECURE_ELEMENT_ENDPOINT_INFO@@@std@@@std@@@Z; NFCConnector::EnumerateSE(ulong,std::vector<_SECURE_ELEMENT_ENDPOINT_INFO> *)
0x1800173ff  mov     edi, eax
0x180017401  test    eax, eax
0x180017403  js      loc_1800171E4
0x180017409  mov     r15, [rsp+230h+var_200+8]
0x18001740e  mov     r14, [rsp+230h+var_200]
0x180017413  jmp     short loc_18001746D
0x180017415  mov     [rsp+230h+var_210], 0
0x18001741e  lea     r8, [rsp+230h+var_210]; struct SecureElement **
0x180017423  mov     rdx, r14; struct _SECURE_ELEMENT_ENDPOINT_INFO *
0x180017426  call    ?CreateSecureElement@SEReader@@AEAAJAEBU_SECURE_ELEMENT_ENDPOINT_INFO@@PEAPEAVSecureElement@@@Z; SEReader::CreateSecureElement(_SECURE_ELEMENT_ENDPOINT_INFO const &,SecureElement * *)
0x18001742b  mov     rdi, [rsp+230h+var_210]
0x180017430  test    eax, eax
0x180017432  js      short loc_18001743F
0x180017434  mov     rdx, rdi; struct SecureElement *
0x180017437  mov     rcx, rbx; this
0x18001743a  call    ?AddSecureElement@SEReader@@AEAAJPEAVSecureElement@@@Z; SEReader::AddSecureElement(SecureElement *)
0x18001743f  test    rdi, rdi
0x180017442  jz      short loc_180017469
0x180017444  mov     eax, r13d
0x180017447  lock xadd [rdi+8], eax
0x18001744c  add     eax, r13d
0x18001744f  jnz     short loc_180017469
0x180017451  test    rdi, rdi
0x180017454  jz      short loc_180017469
0x180017456  mov     rax, [rdi]
0x180017459  mov     edx, 1
0x18001745e  mov     rcx, rdi
0x180017461  mov     rax, [rax]
0x180017464  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017469  add     r14, 14h
0x18001746d  cmp     r14, r15
0x180017470  jnz     short loc_180017415
0x180017472  xor     r8d, r8d; bool
0x180017475  xor     edx, edx; bool
0x180017477  mov     rcx, rbx; this
0x18001747a  call    ?UpdateSecureElementEmulationMode@SEReader@@AEAAJ_N0@Z; SEReader::UpdateSecureElementEmulationMode(bool,bool)
0x18001747f  mov     edi, eax
0x180017481  lea     rcx, [rsp+230h+var_200]
0x180017486  test    eax, eax
0x180017488  js      loc_1800171E9
0x18001748e  call    ??1?$vector@U_SECURE_ELEMENT_ENDPOINT_INFO@@V?$allocator@U_SECURE_ELEMENT_ENDPOINT_INFO@@@std@@@std@@QEAA@XZ; std::vector<_SECURE_ELEMENT_ENDPOINT_INFO>::~vector<_SECURE_ELEMENT_ENDPOINT_INFO>(void)
0x180017493  nop
0x180017494  mov     rcx, rsi; lpCriticalSection
0x180017497  call    cs:__imp_LeaveCriticalSection
0x18001749d  mov     rcx, rbx; this
0x1800174a0  call    ?ApplyCardEmulationPolicy@SEReader@@AEAAJXZ; SEReader::ApplyCardEmulationPolicy(void)
0x1800174a5  mov     edi, eax
0x1800174a7  test    eax, eax
0x1800174a9  jns     short loc_1800174B3
0x1800174ab  mov     rcx, rbx; this
0x1800174ae  call    ?DeinitializeHardwareDependent@SEReader@@AEAAJXZ; SEReader::DeinitializeHardwareDependent(void)
0x1800174b3  mov     eax, edi
0x1800174b5  mov     rcx, [rbp+130h+var_30]
0x1800174bc  xor     rcx, rsp; StackCookie
0x1800174bf  call    __security_check_cookie
0x1800174c4  lea     r11, [rsp+230h+var_20]
0x1800174cc  mov     rbx, [r11+38h]
0x1800174d0  mov     rsi, [r11+40h]
0x1800174d4  mov     rsp, r11
0x1800174d7  pop     r15
0x1800174d9  pop     r14
0x1800174db  pop     r13
0x1800174dd  pop     rdi
0x1800174de  pop     rbp
0x1800174df  retn
```
