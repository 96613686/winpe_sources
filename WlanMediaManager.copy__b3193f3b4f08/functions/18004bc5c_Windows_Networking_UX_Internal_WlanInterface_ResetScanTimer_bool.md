# Windows::Networking::UX::Internal::WlanInterface::_ResetScanTimer(bool)

- ea: `0x18004bc5c`
- end: `0x18004beb1`
- name: `?_ResetScanTimer@WlanInterface@Internal@UX@Networking@Windows@@IEAAX_N@Z`
- size: `597`
- prototype: `void __fastcall(PVOID Parameter, bool)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025dc4`
- `0x18003a658`
- `0x180042f18`
- `0x18004481c`

## callees

- `0x180008e30`
- `0x18000de4c`
- `0x1800121e8`
- `0x1800141a0`
- `0x18001d4d4`
- `0x1800252bc`
- `0x18002feb0`
- `0x18004bc5c`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004bd89`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004be50`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004be34`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004be34`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18004bd7f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18004bd7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Networking::UX::Internal::WlanInterface::_ResetScanTimer(char *Parameter, char a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  _QWORD *v6; // rsi
  void *v7; // rbp
  struct Windows::Networking::UX::Internal::IAccessPointHelper **v8; // rdx
  int AccessPointHelper; // eax
  Windows::Networking::UX::Internal::WlanMediaManager *v10; // rcx
  Windows::Networking::UX::Internal::WlanMediaManager *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  signed int LastError; // eax
  PVOID *v15; // rcx
  signed int v16; // eax
  __int64 v17; // [rsp+70h] [rbp+8h] BYREF
  char v18; // [rsp+80h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  wil::EnterCriticalSection(&v18, Parameter + 1304);
  v6 = Parameter + 1176;
  v7 = (void *)*((_QWORD *)Parameter + 147);
  if ( !a2 )
  {
    Parameter[1184] = 0;
    *v6 = -1;
    goto LABEL_26;
  }
  if ( !Parameter[1184] )
  {
    *v6 = -1;
    v17 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v4, v5);
    AccessPointHelper = Windows::Networking::UX::Internal::AccessPointHelpers::GetAccessPointHelper(
                          (Windows::Networking::UX::Internal::AccessPointHelpers *)&v17,
                          v8);
    if ( AccessPointHelper >= 0 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 104LL))(v17);
    }
    else
    {
      v10 = (Windows::Networking::UX::Internal::WlanMediaManager *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          25,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          (unsigned int)AccessPointHelper);
    }
    Windows::Networking::UX::Internal::WlanMediaManager::RequestScan(v10, (const struct _GUID *)(Parameter + 1204));
    if ( Parameter[1186] )
      Windows::Networking::UX::Internal::WlanMediaManager::RequestScan(v11, (const struct _GUID *)(Parameter + 1188));
    if ( CreateTimerQueueTimer(
           (PHANDLE)Parameter + 147,
           0,
           Windows::Networking::UX::Internal::WlanInterface::s_ScanTimerCallback,
           Parameter,
           0x1F4u,
           0,
           0) )
    {
      Parameter[1184] = 1;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          26,
          &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
          (unsigned int)LastError);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17, v12, v13);
LABEL_26:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
    if ( v7 != (void *)-1LL && !DeleteTimerQueueTimer(0, v7, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_34;
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
        (unsigned int)v16);
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
      WPP_SF_(v15[2], 29, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
    return;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
}

```

## disassembly

```asm
0x18004bc5c  mov     [rsp+arg_8], rbx
0x18004bc61  push    rbp
0x18004bc62  push    rsi
0x18004bc63  push    rdi
0x18004bc64  push    r12
0x18004bc66  push    r15
0x18004bc68  sub     rsp, 40h
0x18004bc6c  mov     dil, dl
0x18004bc6f  mov     rbx, rcx
0x18004bc72  lea     r15, WPP_GLOBAL_Control
0x18004bc79  lea     r12, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004bc80  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bc87  cmp     rcx, r15
0x18004bc8a  jz      short loc_18004BCA3
0x18004bc8c  test    byte ptr [rcx+1Ch], 8
0x18004bc90  jz      short loc_18004BCA3
0x18004bc92  mov     edx, 18h
0x18004bc97  mov     r8, r12
0x18004bc9a  mov     rcx, [rcx+10h]
0x18004bc9e  call    WPP_SF_
0x18004bca3  lea     rdx, [rbx+518h]
0x18004bcaa  lea     rcx, [rsp+68h+arg_10]
0x18004bcb2  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18004bcb7  nop
0x18004bcb8  lea     rsi, [rbx+498h]
0x18004bcbf  mov     rbp, [rsi]
0x18004bcc2  test    dil, dil
0x18004bcc5  jz      loc_18004BE0C
0x18004bccb  cmp     byte ptr [rbx+4A0h], 0
0x18004bcd2  jnz     loc_18004BDD6
0x18004bcd8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004bcdc  mov     [rsi], rdi
0x18004bcdf  mov     [rsp+68h+arg_0], 0
0x18004bce8  lea     rcx, [rsp+68h+arg_0]
0x18004bced  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004bcf2  lea     rcx, [rsp+68h+arg_0]; this
0x18004bcf7  call    ?GetAccessPointHelper@AccessPointHelpers@Internal@UX@Networking@Windows@@YAJPEAPEAUIAccessPointHelper@2345@@Z; Windows::Networking::UX::Internal::AccessPointHelpers::GetAccessPointHelper(Windows::Networking::UX::Internal::IAccessPointHelper * *)
0x18004bcfc  test    eax, eax
0x18004bcfe  jns     short loc_18004BD26
0x18004bd00  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bd07  cmp     rcx, r15
0x18004bd0a  jz      short loc_18004BD37
0x18004bd0c  test    byte ptr [rcx+1Ch], 2
0x18004bd10  jz      short loc_18004BD37
0x18004bd12  lea     edx, [rdi+1Ah]
0x18004bd15  mov     r9d, eax
0x18004bd18  mov     r8, r12
0x18004bd1b  mov     rcx, [rcx+10h]
0x18004bd1f  call    WPP_SF_d
0x18004bd24  jmp     short loc_18004BD37
0x18004bd26  mov     rcx, [rsp+68h+arg_0]
0x18004bd2b  mov     rax, [rcx]
0x18004bd2e  mov     rax, [rax+68h]
0x18004bd32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd37  lea     rdx, [rbx+4B4h]; struct _GUID *
0x18004bd3e  call    ?RequestScan@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@@Z; Windows::Networking::UX::Internal::WlanMediaManager::RequestScan(_GUID const &)
0x18004bd43  cmp     byte ptr [rbx+4A2h], 0
0x18004bd4a  jz      short loc_18004BD58
0x18004bd4c  lea     rdx, [rbx+4A4h]; struct _GUID *
0x18004bd53  call    ?RequestScan@WlanMediaManager@Internal@UX@Networking@Windows@@QEAAJAEBU_GUID@@@Z; Windows::Networking::UX::Internal::WlanMediaManager::RequestScan(_GUID const &)
0x18004bd58  mov     [rsp+68h+Flags], 0; Flags
0x18004bd60  mov     [rsp+68h+Period], 0; Period
0x18004bd68  mov     [rsp+68h+DueTime], 1F4h; DueTime
0x18004bd70  mov     r9, rbx; Parameter
0x18004bd73  lea     r8, ?s_ScanTimerCallback@WlanInterface@Internal@UX@Networking@Windows@@KAXPEAXE@Z; Callback
0x18004bd7a  xor     edx, edx; TimerQueue
0x18004bd7c  mov     rcx, rsi; phNewTimer
0x18004bd7f  call    cs:__imp_CreateTimerQueueTimer
0x18004bd85  test    eax, eax
0x18004bd87  jnz     short loc_18004BDC3
0x18004bd89  call    cs:__imp_GetLastError
0x18004bd8f  test    eax, eax
0x18004bd91  jle     short loc_18004BD9B
0x18004bd93  movzx   eax, ax
0x18004bd96  or      eax, 80070000h
0x18004bd9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bda2  cmp     rcx, r15
0x18004bda5  jz      short loc_18004BDCA
0x18004bda7  test    byte ptr [rcx+1Ch], 2
0x18004bdab  jz      short loc_18004BDCA
0x18004bdad  mov     edx, 1Ah
0x18004bdb2  mov     r9d, eax
0x18004bdb5  mov     r8, r12
0x18004bdb8  mov     rcx, [rcx+10h]
0x18004bdbc  call    WPP_SF_d
0x18004bdc1  jmp     short loc_18004BDCA
0x18004bdc3  mov     byte ptr [rbx+4A0h], 1
0x18004bdca  lea     rcx, [rsp+68h+arg_0]
0x18004bdcf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004bdd4  jmp     short loc_18004BE1A
0x18004bdd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bddd  cmp     rcx, r15
0x18004bde0  jz      short loc_18004BDFA
0x18004bde2  test    byte ptr [rcx+1Ch], 8
0x18004bde6  jz      short loc_18004BDFA
0x18004bde8  mov     edx, 1Bh
0x18004bded  mov     r8, r12
0x18004bdf0  mov     rcx, [rcx+10h]
0x18004bdf4  call    WPP_SF_
0x18004bdf9  nop
0x18004bdfa  lea     rcx, [rsp+68h+arg_10]
0x18004be02  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004be07  jmp     loc_18004BEA0
0x18004be0c  mov     byte ptr [rbx+4A0h], 0
0x18004be13  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004be17  mov     [rsi], rdi
0x18004be1a  lea     rcx, [rsp+68h+arg_10]
0x18004be22  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18004be27  cmp     rbp, rdi
0x18004be2a  jz      short loc_18004BE7D
0x18004be2c  mov     r8, rdi; CompletionEvent
0x18004be2f  mov     rdx, rbp; Timer
0x18004be32  xor     ecx, ecx; TimerQueue
0x18004be34  call    cs:__imp_DeleteTimerQueueTimer
0x18004be3a  test    eax, eax
0x18004be3c  jnz     short loc_18004BE7D
0x18004be3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be45  cmp     rcx, r15
0x18004be48  jz      short loc_18004BEA0
0x18004be4a  test    byte ptr [rcx+1Ch], 2
0x18004be4e  jz      short loc_18004BE84
0x18004be50  call    cs:__imp_GetLastError
0x18004be56  test    eax, eax
0x18004be58  jle     short loc_18004BE62
0x18004be5a  movzx   eax, ax
0x18004be5d  or      eax, 80070000h
0x18004be62  mov     edx, 1Ch
0x18004be67  mov     r9d, eax
0x18004be6a  mov     r8, r12
0x18004be6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be74  mov     rcx, [rcx+10h]
0x18004be78  call    WPP_SF_d
0x18004be7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004be84  cmp     rcx, r15
0x18004be87  jz      short loc_18004BEA0
0x18004be89  test    byte ptr [rcx+1Ch], 8
0x18004be8d  jz      short loc_18004BEA0
0x18004be8f  mov     edx, 1Dh
0x18004be94  mov     r8, r12
0x18004be97  mov     rcx, [rcx+10h]
0x18004be9b  call    WPP_SF_
0x18004bea0  mov     rbx, [rsp+68h+arg_8]
0x18004bea5  add     rsp, 40h
0x18004bea9  pop     r15
0x18004beab  pop     r12
0x18004bead  pop     rdi
0x18004beae  pop     rsi
0x18004beaf  pop     rbp
0x18004beb0  retn
```
