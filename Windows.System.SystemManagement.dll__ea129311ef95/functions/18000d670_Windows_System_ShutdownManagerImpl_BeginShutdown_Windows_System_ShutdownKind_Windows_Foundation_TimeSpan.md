# Windows::System::ShutdownManagerImpl::BeginShutdown(Windows::System::ShutdownKind,Windows::Foundation::TimeSpan)

- ea: `0x18000d670`
- end: `0x18000d7fe`
- name: `?BeginShutdown@ShutdownManagerImpl@System@Windows@@UEAAJW4ShutdownKind@23@UTimeSpan@Foundation@3@@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002dc0`
- `0x18000d0a4`
- `0x18000d424`
- `0x18000d670`
- `0x18000e9d0`
- `0x18000ed24`
- `0x18000f824`
- `0x18000f854`
- `0x18000fa18`
- `0x18000fd54`
- `0x18001c6a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d770`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d770`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d757`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000d757`

## pseudocode

```c
__int64 __fastcall Windows::System::ShutdownManagerImpl::BeginShutdown(__int64 a1, int a2, __int64 a3)
{
  signed int HasSystemManagementCapability; // edi
  int v7; // eax
  HANDLE Thread; // rax
  signed int LastError; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-198h]
  unsigned __int8 v12[16]; // [rsp+30h] [rbp-188h] BYREF
  _QWORD v13[42]; // [rsp+40h] [rbp-178h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v12[0] = 0;
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v13,
    "BeginShutdownActivity");
  v13[0] = &Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::`vftable';
  Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StartActivity((Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *)v13);
  HasSystemManagementCapability = Windows::System::SystemManagementUtil::HasSystemManagementCapability(v12);
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_19;
  if ( !v12[0] )
  {
    HasSystemManagementCapability = -2147024891;
LABEL_19:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\windows\\iot\\winrt\\sysadmin\\lib\\shutdownmanager\\shutdownmanagerimpl.cpp",
      (const char *)(unsigned int)HasSystemManagementCapability,
      dwCreationFlags);
    goto LABEL_20;
  }
  if ( a2 )
  {
    if ( a2 != 1 )
    {
LABEL_6:
      HasSystemManagementCapability = -2147024809;
      goto LABEL_19;
    }
    v7 = 1;
  }
  else
  {
    v7 = 0;
  }
  *(_DWORD *)(a1 + 88) = v7;
  if ( a3 < 0 )
    goto LABEL_6;
  *(_DWORD *)(a1 + 84) = a3 / 0x989680uLL;
  HasSystemManagementCapability = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(a1 + 64);
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_19;
  Thread = CreateThread(
             0,
             0,
             (LPTHREAD_START_ROUTINE)Windows::System::ShutdownManagerImpl::s_InitiateSystemShutdownThread,
             (LPVOID)(a1 - 40),
             0,
             0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1 + 72,
    Thread);
  if ( *(_QWORD *)(a1 + 72) )
  {
    if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(a1 + 64) )
    {
      HasSystemManagementCapability = -2147467260;
      goto LABEL_19;
    }
    HasSystemManagementCapability = *(_DWORD *)(a1 + 80);
  }
  else
  {
    LastError = GetLastError();
    HasSystemManagementCapability = LastError;
    if ( LastError > 0 )
      HasSystemManagementCapability = (unsigned __int16)LastError | 0x80070000;
  }
  if ( HasSystemManagementCapability < 0 )
    goto LABEL_19;
LABEL_20:
  wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v13,
    HasSystemManagementCapability);
  Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::~BeginShutdownActivity((Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity *)v13);
  return (unsigned int)HasSystemManagementCapability;
}

```

## disassembly

```asm
0x18000d670  mov     [rsp+arg_8], rbx
0x18000d675  mov     [rsp+arg_18], rbp
0x18000d67a  push    rsi
0x18000d67b  push    rdi
0x18000d67c  push    r14
0x18000d67e  sub     rsp, 1A0h
0x18000d685  mov     rax, cs:__security_cookie
0x18000d68c  xor     rax, rsp
0x18000d68f  mov     [rsp+1B8h+var_28], rax
0x18000d697  mov     esi, edx
0x18000d699  mov     [rsp+1B8h+var_188], 0
0x18000d69e  mov     rbp, rcx
0x18000d6a1  lea     rdx, aBeginshutdowna; "BeginShutdownActivity"
0x18000d6a8  lea     rcx, [rsp+1B8h+var_178]
0x18000d6ad  mov     rbx, r8
0x18000d6b0  call    ??0?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000d6b5  lea     rax, ??_7BeginShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@6B@; const Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::`vftable'
0x18000d6bc  lea     rcx, [rsp+1B8h+var_178]; this
0x18000d6c1  mov     [rsp+1B8h+var_178], rax
0x18000d6c6  call    ?StartActivity@BeginShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAAXXZ; Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::StartActivity(void)
0x18000d6cb  lea     rcx, [rsp+1B8h+var_188]; unsigned __int8 *
0x18000d6d0  call    ?HasSystemManagementCapability@SystemManagementUtil@System@Windows@@SAJPEAE@Z; Windows::System::SystemManagementUtil::HasSystemManagementCapability(uchar *)
0x18000d6d5  mov     edi, eax
0x18000d6d7  test    eax, eax
0x18000d6d9  js      loc_18000D7A2
0x18000d6df  cmp     [rsp+1B8h+var_188], 0
0x18000d6e4  jnz     short loc_18000D6F0
0x18000d6e6  mov     edi, 80070005h
0x18000d6eb  jmp     loc_18000D7A2
0x18000d6f0  test    esi, esi
0x18000d6f2  jz      short loc_18000D70A
0x18000d6f4  cmp     esi, 1
0x18000d6f7  jz      short loc_18000D703
0x18000d6f9  mov     edi, 80070057h
0x18000d6fe  jmp     loc_18000D7A2
0x18000d703  mov     eax, 1
0x18000d708  jmp     short loc_18000D70C
0x18000d70a  xor     eax, eax
0x18000d70c  mov     [rbp+58h], eax
0x18000d70f  test    rbx, rbx
0x18000d712  js      short loc_18000D6F9
0x18000d714  mov     rax, 0D6BF94D5E57A42BDh
0x18000d71e  lea     rcx, [rbp+40h]
0x18000d722  mul     rbx
0x18000d725  shr     rdx, 17h
0x18000d729  mov     [rbp+54h], edx
0x18000d72c  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18000d731  mov     edi, eax
0x18000d733  test    eax, eax
0x18000d735  js      short loc_18000D7A2
0x18000d737  mov     [rsp+1B8h+lpThreadId], 0; lpThreadId
0x18000d740  lea     r9, [rbp-28h]; lpParameter
0x18000d744  lea     r8, ?s_InitiateSystemShutdownThread@ShutdownManagerImpl@System@Windows@@CAKPEAX@Z; lpStartAddress
0x18000d74b  mov     [rsp+1B8h+dwCreationFlags], 0; int
0x18000d753  xor     edx, edx; dwStackSize
0x18000d755  xor     ecx, ecx; lpThreadAttributes
0x18000d757  call    cs:__imp_CreateThread
0x18000d75d  mov     rdx, rax
0x18000d760  lea     rcx, [rbp+48h]
0x18000d764  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18000d769  cmp     qword ptr [rbp+48h], 0
0x18000d76e  jnz     short loc_18000D787
0x18000d770  call    cs:__imp_GetLastError
0x18000d776  mov     edi, eax
0x18000d778  test    eax, eax
0x18000d77a  jle     short loc_18000D797
0x18000d77c  movzx   edi, ax
0x18000d77f  or      edi, 80070000h
0x18000d785  jmp     short loc_18000D797
0x18000d787  lea     rcx, [rbp+40h]
0x18000d78b  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18000d790  test    al, al
0x18000d792  jz      short loc_18000D79D
0x18000d794  mov     edi, [rbp+50h]
0x18000d797  test    edi, edi
0x18000d799  jns     short loc_18000D7BE
0x18000d79b  jmp     short loc_18000D7A2
0x18000d79d  mov     edi, 80004004h
0x18000d7a2  mov     rcx, [rsp+1B8h]; this
0x18000d7aa  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\iot\\winrt\\sysadm"...
0x18000d7b1  mov     r9d, edi; char *
0x18000d7b4  mov     edx, 72h ; 'r'; void *
0x18000d7b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000d7be  mov     edx, edi
0x18000d7c0  lea     rcx, [rsp+1B8h+var_178]
0x18000d7c5  call    ?Stop@?$ActivityBase@VSysAdminTraceLoggingProvider@System@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<Windows::System::SysAdminTraceLoggingProvider,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18000d7ca  lea     rcx, [rsp+1B8h+var_178]; this
0x18000d7cf  call    ??1BeginShutdownActivity@SysAdminTraceLoggingProvider@System@Windows@@QEAA@XZ; Windows::System::SysAdminTraceLoggingProvider::BeginShutdownActivity::~BeginShutdownActivity(void)
0x18000d7d4  mov     eax, edi
0x18000d7d6  mov     rcx, [rsp+1B8h+var_28]
0x18000d7de  xor     rcx, rsp; StackCookie
0x18000d7e1  call    __security_check_cookie
0x18000d7e6  lea     r11, [rsp+1B8h+var_18]
0x18000d7ee  mov     rbx, [r11+28h]
0x18000d7f2  mov     rbp, [r11+38h]
0x18000d7f6  mov     rsp, r11
0x18000d7f9  pop     r14
0x18000d7fb  pop     rdi
0x18000d7fc  pop     rsi
0x18000d7fd  retn
```
