# SEManager::GetSEBySmartCardReaderId(ushort const *,ISecureElement * *)

- ea: `0x180011710`
- end: `0x180011a34`
- name: `?GetSEBySmartCardReaderId@SEManager@@UEAAJPEBGPEAPEAUISecureElement@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(SEManager *__hidden this, const unsigned __int16 *, struct ISecureElement **)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000c964`
- `0x180010314`
- `0x18001063c`
- `0x180011710`
- `0x180012818`
- `0x180019054`
- `0x1800191b0`
- `0x1800194a8`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800119fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800118eb`

## string_xrefs

- `0x18001172c`: `SEManager::GetSEReaderById`
- `0x18001175f`: `onecoreuap\ds\nfc\product\semanagement\service\src\semanager.cpp`
- `0x1800117b3`: `onecoreuap\ds\nfc\product\semanagement\service\src\semanager.cpp`
- `0x180011995`: `onecoreuap\ds\nfc\product\semanagement\service\src\semanager.cpp`
- `0x1800119e5`: `onecoreuap\ds\nfc\product\semanagement\service\src\semanager.cpp`
- `0x1800117f9`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\sedriverquery.cpp`
- `0x18001187e`: `onecoreuap\ds\nfc\product\semanagement\common\seutils\src\sedriverquery.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SEManager::GetSEBySmartCardReaderId(SEManager *this, char *a2, struct ISecureElement **a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v9; // rcx
  __int64 v10; // r9
  __int64 v11; // rdx
  int DriverInterfaces; // eax
  const unsigned __int16 *i; // rcx
  __int64 v14; // rax
  char *v15; // r10
  int v16; // r9d
  int v17; // r8d
  int DeviceInterfaceGuidProperty; // eax
  _QWORD *j; // rbx
  __int64 v20; // rax
  __int64 *v21; // rax
  __int64 v22; // rbx
  int v23; // eax
  __int64 v24; // rcx
  __int128 v25; // [rsp+20h] [rbp-50h] BYREF
  __int64 v26; // [rsp+30h] [rbp-40h]
  struct _GUID v27; // [rsp+38h] [rbp-38h] BYREF
  __int64 *v28; // [rsp+48h] [rbp-28h] BYREF
  __int64 *v29; // [rsp+50h] [rbp-20h]
  const wchar_t *v30; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v30 = L"SEManager::GetSEReaderById";
  if ( (byte_180132D81 & 0x10) != 0 )
    McTemplateU0z_EventWriteTransfer(this, ")#", L"SEManager::GetSEReaderById");
  if ( !a3 )
  {
    v5 = -2147024809;
    v6 = 319;
    goto LABEL_5;
  }
  *a3 = 0;
  if ( (void *)qword_1801331C8 == SEManager::s_SEReaderList )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x143,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semanager.cpp",
      (const char *)0x80070037LL,
      v25);
LABEL_50:
    if ( (byte_180132D81 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(v9, "*#", L"SEManager::GetSEReaderById");
    return 2147942455LL;
  }
  v27 = GUID_NULL;
  v25 = 0;
  v26 = 0;
  if ( a2 )
  {
    DriverInterfaces = NfcDriverQuery::FindDriverInterfaces(&GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION);
    v5 = DriverInterfaces;
    if ( DriverInterfaces >= 0 )
    {
      for ( i = (const unsigned __int16 *)v25; i != *((const unsigned __int16 **)&v25 + 1); i += 16 )
      {
        v14 = *((_QWORD *)i + 3) <= 7u ? (__int64)i : *(_QWORD *)i;
        v15 = &a2[-v14];
        do
        {
          v16 = *(unsigned __int16 *)&v15[v14];
          v17 = *(unsigned __int16 *)v14 - v16;
          if ( v17 )
            break;
          v14 += 2;
        }
        while ( v16 );
        if ( !v17 )
          break;
      }
      if ( i == *((const unsigned __int16 **)&v25 + 1) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x18,
          (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\sedriverquery.cpp",
          (const char *)0x80070037LL,
          v25);
        v5 = -2147024841;
        goto LABEL_33;
      }
      if ( *((_QWORD *)i + 3) > 7u )
        i = *(const unsigned __int16 **)i;
      DeviceInterfaceGuidProperty = NfcDriverQuery::GetDeviceInterfaceGuidProperty(
                                      i,
                                      &DEVPKEY_Device_ReaderSecureElementId,
                                      &v27);
      v5 = DeviceInterfaceGuidProperty;
      if ( DeviceInterfaceGuidProperty >= 0 )
      {
        v5 = 0;
        goto LABEL_33;
      }
      v10 = (unsigned int)DeviceInterfaceGuidProperty;
      v11 = 26;
    }
    else
    {
      v10 = (unsigned int)DriverInterfaces;
      v11 = 17;
    }
  }
  else
  {
    v5 = -2147024809;
    v10 = 2147942487LL;
    v11 = 16;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seutils\\src\\sedriverquery.cpp",
    (const char *)v10,
    v25);
LABEL_33:
  std::vector<std::wstring>::_Tidy(&v25);
  if ( v5 < 0 )
  {
    v6 = 326;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semanager.cpp",
      (const char *)(unsigned int)v5,
      v25);
LABEL_6:
    if ( (byte_180132D81 & 0x10) != 0 )
      McTemplateU0z_EventWriteTransfer(v7, "*#", L"SEManager::GetSEReaderById");
    return (unsigned int)v5;
  }
  *(_QWORD *)&v25 = &SEManager::s_csLock;
  EnterCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
  BYTE8(v25) = 1;
  for ( j = SEManager::s_SEReaderList; ; j += 2 )
  {
    if ( j == (_QWORD *)qword_1801331C8 )
      goto LABEL_49;
    v20 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*j + 24LL))(*j);
    std::vector<SecureElement *>::vector<SecureElement *>(&v28, v20);
    v21 = v28;
    if ( v28 != v29 )
    {
      do
      {
        if ( *(_QWORD *)&v27.Data1 == *(_QWORD *)(*v21 + 12) && *(_QWORD *)v27.Data4 == *(_QWORD *)(*v21 + 20) )
          break;
        ++v21;
      }
      while ( v21 != v29 );
      if ( v21 != v29 )
        break;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>(&v28);
  }
  v22 = *v21;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>(&v28);
  if ( !v22 )
  {
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x158,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semanager.cpp",
      (const char *)0x80070037LL,
      v25);
    LeaveCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
    goto LABEL_50;
  }
  v23 = (*(__int64 (__fastcall **)(__int64, struct ISecureElement **))(*(_QWORD *)v22 + 24LL))(v22, a3);
  v5 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x159,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\service\\src\\semanager.cpp",
      (const char *)(unsigned int)v23,
      v25);
    LeaveCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
    goto LABEL_6;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
  if ( (byte_180132D81 & 0x10) != 0 )
    McTemplateU0z_EventWriteTransfer(v24, "*#", L"SEManager::GetSEReaderById");
  return 0;
}

```

## disassembly

```asm
0x180011710  mov     [rsp-18h+arg_0], rbx
0x180011715  mov     [rsp-18h+arg_8], rsi
0x18001171a  push    rbp
0x18001171b  push    r14
0x18001171d  push    r15
0x18001171f  mov     rbp, rsp
0x180011722  sub     rsp, 70h
0x180011726  mov     r14, r8
0x180011729  mov     rsi, rdx
0x18001172c  lea     r15, aSemanagerGetse; "SEManager::GetSEReaderById"
0x180011733  mov     [rbp+var_10], r15
0x180011737  test    cs:byte_180132D81, 10h
0x18001173e  jz      short loc_180011750
0x180011740  mov     r8, r15
0x180011743  lea     rdx, SEMgr_Event_COM_API_Start; ")#"
0x18001174a  call    McTemplateU0z_EventWriteTransfer
0x18001174f  nop
0x180011750  test    r14, r14
0x180011753  jnz     short loc_180011792
0x180011755  mov     ebx, 80070057h
0x18001175a  mov     edx, 13Fh; void *
0x18001175f  lea     r8, aOnecoreuapDsNf_12; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180011766  mov     r9d, ebx; char *
0x180011769  mov     rcx, [rbp+18h]; this
0x18001176d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011772  nop
0x180011773  test    cs:byte_180132D81, 10h
0x18001177a  jz      short loc_18001178B
0x18001177c  mov     r8, r15
0x18001177f  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x180011786  call    McTemplateU0z_EventWriteTransfer
0x18001178b  mov     eax, ebx
0x18001178d  jmp     loc_180011A1E
0x180011792  mov     qword ptr [r14], 0
0x180011799  mov     rax, cs:qword_1801331C8
0x1800117a0  cmp     rax, cs:?s_SEReaderList@SEManager@@0V?$vector@V?$shared_ptr@VSEReader@@@std@@V?$allocator@V?$shared_ptr@VSEReader@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SEReader>> SEManager::s_SEReaderList
0x1800117a7  jnz     short loc_1800117C9
0x1800117a9  mov     rcx, [rbp+18h]; this
0x1800117ad  mov     r9d, 80070037h; char *
0x1800117b3  lea     r8, aOnecoreuapDsNf_12; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800117ba  mov     edx, 143h; void *
0x1800117bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117c4  jmp     loc_180011A01
0x1800117c9  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800117d0  movdqu  xmmword ptr [rbp+var_38.Data1], xmm0
0x1800117d5  xorps   xmm1, xmm1
0x1800117d8  movdqu  [rbp+var_50], xmm1
0x1800117dd  mov     [rbp+var_40], 0
0x1800117e5  test    rsi, rsi
0x1800117e8  jnz     short loc_18001180B
0x1800117ea  mov     ebx, 80070057h
0x1800117ef  mov     r9d, ebx; char *
0x1800117f2  lea     edx, [rsi+10h]; void *
0x1800117f5  mov     rcx, [rbp+18h]; this
0x1800117f9  lea     r8, aOnecoreuapDsNf_8; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180011800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011805  nop
0x180011806  jmp     loc_1800118C6
0x18001180b  lea     rdx, [rbp+var_50]
0x18001180f  lea     rcx, GUID_DEVINTERFACE_SMARTCARD_READER_INFORMATION; InterfaceClassGuid
0x180011816  call    ?FindDriverInterfaces@NfcDriverQuery@@SAJAEBU_GUID@@PEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; NfcDriverQuery::FindDriverInterfaces(_GUID const &,std::vector<std::wstring> *)
0x18001181b  mov     ebx, eax
0x18001181d  test    eax, eax
0x18001181f  jns     short loc_18001182B
0x180011821  mov     r9d, eax
0x180011824  mov     edx, 11h
0x180011829  jmp     short loc_1800117F5
0x18001182b  mov     rcx, qword ptr [rbp+var_50]
0x18001182f  mov     rdx, qword ptr [rbp+var_50+8]
0x180011833  jmp     short loc_18001186A
0x180011835  cmp     qword ptr [rcx+18h], 7
0x18001183a  jbe     short loc_180011841
0x18001183c  mov     rax, [rcx]
0x18001183f  jmp     short loc_180011844
0x180011841  mov     rax, rcx
0x180011844  mov     r10, rsi
0x180011847  sub     r10, rax
0x18001184a  movzx   r8d, word ptr [rax]
0x18001184e  movzx   r9d, word ptr [rax+r10]
0x180011853  sub     r8d, r9d
0x180011856  jnz     short loc_180011861
0x180011858  add     rax, 2
0x18001185c  test    r9d, r9d
0x18001185f  jnz     short loc_18001184A
0x180011861  test    r8d, r8d
0x180011864  jz      short loc_18001186F
0x180011866  add     rcx, 20h ; ' '
0x18001186a  cmp     rcx, rdx
0x18001186d  jnz     short loc_180011835
0x18001186f  cmp     rcx, rdx
0x180011872  jnz     short loc_180011897
0x180011874  mov     rcx, [rbp+18h]; this
0x180011878  mov     r9d, 80070037h; char *
0x18001187e  lea     r8, aOnecoreuapDsNf_8; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x180011885  mov     edx, 18h; void *
0x18001188a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001188f  nop
0x180011890  mov     ebx, 80070037h
0x180011895  jmp     short loc_1800118C6
0x180011897  cmp     qword ptr [rcx+18h], 7
0x18001189c  jbe     short loc_1800118A1
0x18001189e  mov     rcx, [rcx]; unsigned __int16 *
0x1800118a1  lea     r8, [rbp+var_38]; struct _GUID *
0x1800118a5  lea     rdx, DEVPKEY_Device_ReaderSecureElementId; struct _DEVPROPKEY *
0x1800118ac  call    ?GetDeviceInterfaceGuidProperty@NfcDriverQuery@@SAJPEBGAEBU_DEVPROPKEY@@PEAU_GUID@@@Z; NfcDriverQuery::GetDeviceInterfaceGuidProperty(ushort const *,_DEVPROPKEY const &,_GUID *)
0x1800118b1  mov     ebx, eax
0x1800118b3  test    eax, eax
0x1800118b5  jns     short loc_1800118C4
0x1800118b7  mov     r9d, eax
0x1800118ba  mov     edx, 1Ah
0x1800118bf  jmp     loc_1800117F5
0x1800118c4  xor     ebx, ebx
0x1800118c6  lea     rcx, [rbp+var_50]
0x1800118ca  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800118cf  test    ebx, ebx
0x1800118d1  jns     short loc_1800118DD
0x1800118d3  mov     edx, 146h
0x1800118d8  jmp     loc_18001175F
0x1800118dd  lea     rsi, ?s_csLock@SEManager@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection SEManager::s_csLock
0x1800118e4  mov     qword ptr [rbp+var_50], rsi
0x1800118e8  mov     rcx, rsi; lpCriticalSection
0x1800118eb  call    cs:__imp_EnterCriticalSection
0x1800118f1  mov     byte ptr [rbp+var_50+8], 1
0x1800118f5  mov     rbx, cs:?s_SEReaderList@SEManager@@0V?$vector@V?$shared_ptr@VSEReader@@@std@@V?$allocator@V?$shared_ptr@VSEReader@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SEReader>> SEManager::s_SEReaderList
0x1800118fc  cmp     rbx, cs:qword_1801331C8
0x180011903  jz      loc_1800119DB
0x180011909  mov     rcx, [rbx]
0x18001190c  mov     rax, [rcx]
0x18001190f  mov     rax, [rax+18h]
0x180011913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011918  mov     rdx, rax
0x18001191b  lea     rcx, [rbp+var_28]
0x18001191f  call    ??0?$vector@PEAVSecureElement@@V?$allocator@PEAVSecureElement@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<SecureElement *>::vector<SecureElement *>(std::vector<SecureElement *> const &)
0x180011924  mov     rax, [rbp+var_28]
0x180011928  mov     rdx, [rbp+var_20]
0x18001192c  cmp     rax, rdx
0x18001192f  jz      short loc_180011956
0x180011931  mov     r8, qword ptr [rbp+var_38.Data4]
0x180011935  mov     r9, qword ptr [rbp+var_38.Data1]
0x180011939  mov     rcx, [rax]
0x18001193c  cmp     r9, [rcx+0Ch]
0x180011940  jnz     short loc_180011948
0x180011942  cmp     r8, [rcx+14h]
0x180011946  jz      short loc_180011951
0x180011948  add     rax, 8
0x18001194c  cmp     rax, rdx
0x18001194f  jnz     short loc_180011939
0x180011951  cmp     rax, rdx
0x180011954  jnz     short loc_180011965
0x180011956  lea     rcx, [rbp+var_28]
0x18001195a  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>(void)
0x18001195f  add     rbx, 10h
0x180011963  jmp     short loc_1800118FC
0x180011965  mov     rbx, [rax]
0x180011968  lea     rcx, [rbp+var_28]
0x18001196c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBIURegistryEntry@PaymentTransactionRegistry@Service@Mediator@Payment@Windows@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<uint const,Windows::Payment::Mediator::Service::PaymentTransactionRegistry::RegistryEntry>>>>>>(void)
0x180011971  test    rbx, rbx
0x180011974  jz      short loc_1800119DB
0x180011976  mov     rax, [rbx]
0x180011979  mov     rdx, r14
0x18001197c  mov     rcx, rbx
0x18001197f  mov     rax, [rax+18h]
0x180011983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011988  mov     ebx, eax
0x18001198a  test    eax, eax
0x18001198c  jns     short loc_1800119B5
0x18001198e  mov     rcx, [rbp+18h]; this
0x180011992  mov     r9d, eax; char *
0x180011995  lea     r8, aOnecoreuapDsNf_12; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001199c  mov     edx, 159h; void *
0x1800119a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119a6  nop
0x1800119a7  mov     rcx, rsi; lpCriticalSection
0x1800119aa  call    cs:__imp_LeaveCriticalSection
0x1800119b0  jmp     loc_180011773
0x1800119b5  mov     rcx, rsi; lpCriticalSection
0x1800119b8  call    cs:__imp_LeaveCriticalSection
0x1800119be  nop
0x1800119bf  test    cs:byte_180132D81, 10h
0x1800119c6  jz      short loc_1800119D7
0x1800119c8  mov     r8, r15
0x1800119cb  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x1800119d2  call    McTemplateU0z_EventWriteTransfer
0x1800119d7  xor     eax, eax
0x1800119d9  jmp     short loc_180011A1E
0x1800119db  mov     rcx, [rbp+18h]; this
0x1800119df  mov     r9d, 80070037h; char *
0x1800119e5  lea     r8, aOnecoreuapDsNf_12; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x1800119ec  mov     edx, 158h; void *
0x1800119f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119f6  nop
0x1800119f7  mov     rcx, rsi; lpCriticalSection
0x1800119fa  call    cs:__imp_LeaveCriticalSection
0x180011a00  nop
0x180011a01  test    cs:byte_180132D81, 10h
0x180011a08  jz      short loc_180011A19
0x180011a0a  mov     r8, r15
0x180011a0d  lea     rdx, SEMgr_Event_COM_API_End; "*#"
0x180011a14  call    McTemplateU0z_EventWriteTransfer
0x180011a19  mov     eax, 80070037h
0x180011a1e  lea     r11, [rsp+70h+var_s0]
0x180011a23  mov     rbx, [r11+20h]
0x180011a27  mov     rsi, [r11+28h]
0x180011a2b  mov     rsp, r11
0x180011a2e  pop     r15
0x180011a30  pop     r14
0x180011a32  pop     rbp
0x180011a33  retn
```
