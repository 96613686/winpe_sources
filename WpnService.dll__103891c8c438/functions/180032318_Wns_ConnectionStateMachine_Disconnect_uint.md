# Wns::ConnectionStateMachine::Disconnect(uint)

- ea: `0x180032318`
- end: `0x180032494`
- name: `?Disconnect@ConnectionStateMachine@Wns@@AEAAXI@Z`
- size: `380`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005df0`
- `0x180007278`

## callees

- `0x180003190`
- `0x18000a910`
- `0x18000fefc`
- `0x180015ba8`
- `0x180022ce4`
- `0x1800232b4`
- `0x18002ffd0`
- `0x180032318`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032338`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180032338`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032375`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180032375`

## string_xrefs

- `0x1800323f9`: `Unknown thread state encountered in machine`

## pseudocode

```c
void __fastcall Wns::ConnectionStateMachine::Disconnect(LPCRITICAL_SECTION lpCriticalSection, unsigned int a2)
{
  int DebugInfo; // ecx
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  unsigned int v13; // eax
  const char *v14; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  LPCRITICAL_SECTION v16; // [rsp+50h] [rbp+8h] BYREF

  while ( 1 )
  {
    EnterCriticalSection(lpCriticalSection);
    v16 = lpCriticalSection;
    DebugInfo = (int)lpCriticalSection[1].DebugInfo;
    if ( !DebugInfo )
      goto LABEL_7;
    v5 = DebugInfo - 1;
    if ( !v5 )
      goto LABEL_7;
    v6 = v5 - 1;
    if ( v6 )
    {
      v7 = v6 - 1;
      if ( v7 )
      {
        v8 = v7 - 1;
        if ( v8 )
        {
          if ( v8 != 1 )
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x175,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
              (const char *)0x8000FFFFLL,
              (int)"Unknown state encountered in machine",
              v14);
LABEL_7:
          v9 = 6;
          goto LABEL_8;
        }
        v9 = 4;
      }
      else
      {
        LODWORD(lpCriticalSection[1].DebugInfo) = 4;
        v9 = 2;
      }
    }
    else
    {
      v9 = 3;
    }
LABEL_8:
    LeaveCriticalSection(lpCriticalSection);
    v10 = v9 - 2;
    if ( !v10 )
    {
      Wns::ConnectionProviderLoader::Get(*(_QWORD *)&lpCriticalSection[9].LockCount, &v16);
      _ResetEvent___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBAXXZ(&lpCriticalSection[1].LockCount);
      Wns::CPTransactionRequestManager::Clear((Wns::CPTransactionRequestManager *)&lpCriticalSection[1].LockSemaphore);
      v13 = (*(__int64 (__fastcall **)(LPCRITICAL_SECTION))&v16->DebugInfo->EntryCount)(v16);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x252,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
        (const char *)v13,
        (int)"Failed to Disconnect",
        v14);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v16);
      return;
    }
    v11 = v10 - 1;
    if ( v11 )
      break;
    if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                             &lpCriticalSection[1].LockCount,
                             a2) )
      return;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    if ( v12 != 2 )
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x18D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\mux\\connectionstatemachine.cpp",
        (const char *)0x8000FFFFLL,
        (int)"Unknown thread state encountered in machine",
        v14);
  }
}

```

## disassembly

```asm
0x180032318  mov     [rsp+arg_8], rbx
0x18003231d  mov     [rsp+arg_10], rbp
0x180032322  push    rsi
0x180032323  push    rdi
0x180032324  push    r14
0x180032326  sub     rsp, 30h
0x18003232a  mov     ebp, edx
0x18003232c  mov     rdi, rcx
0x18003232f  mov     r14d, 30h ; '0'
0x180032335  mov     rcx, rdi; lpCriticalSection
0x180032338  call    cs:__imp_EnterCriticalSection
0x18003233e  mov     [rsp+48h+arg_0], rdi
0x180032343  mov     ecx, [rdi+28h]
0x180032346  test    ecx, ecx
0x180032348  jz      short loc_180032363
0x18003234a  sub     ecx, 1
0x18003234d  jz      short loc_180032363
0x18003234f  sub     ecx, 1
0x180032352  jz      short loc_1800323B2
0x180032354  sub     ecx, 1
0x180032357  jz      short loc_1800323A4
0x180032359  sub     ecx, 1
0x18003235c  jz      short loc_18003239D
0x18003235e  cmp     ecx, 1
0x180032361  jnz     short loc_1800323B9
0x180032363  mov     ebx, 6
0x180032368  mov     rcx, r14
0x18003236b  mov     rax, rdi
0x18003236e  lea     rsi, [rcx+rax]
0x180032372  mov     rcx, rdi; lpCriticalSection
0x180032375  call    cs:__imp_LeaveCriticalSection
0x18003237b  sub     ebx, 2
0x18003237e  jz      loc_18003241D
0x180032384  sub     ebx, 1
0x180032387  jnz     short loc_1800323E2
0x180032389  lea     rcx, [rdi+30h]
0x18003238d  mov     edx, ebp
0x18003238f  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x180032394  test    al, al
0x180032396  jnz     short loc_180032335
0x180032398  jmp     loc_180032481
0x18003239d  mov     ebx, 4
0x1800323a2  jmp     short loc_180032368
0x1800323a4  mov     dword ptr [rdi+28h], 4
0x1800323ab  mov     ebx, 2
0x1800323b0  jmp     short loc_180032368
0x1800323b2  mov     ebx, 3
0x1800323b7  jmp     short loc_180032368
0x1800323b9  mov     rcx, [rsp+48h]; this
0x1800323be  lea     rax, aUnknownStateEn; "Unknown state encountered in machine"
0x1800323c5  mov     qword ptr [rsp+48h+var_28], rax; int
0x1800323ca  mov     r9d, 8000FFFFh; char *
0x1800323d0  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800323d7  mov     edx, 175h; void *
0x1800323dc  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800323e2  sub     ebx, 1
0x1800323e5  jz      loc_180032481
0x1800323eb  cmp     ebx, 2
0x1800323ee  jz      loc_180032481
0x1800323f4  mov     rcx, [rsp+48h]; this
0x1800323f9  lea     rax, aUnknownThreadS_0; "Unknown thread state encountered in mac"...
0x180032400  mov     qword ptr [rsp+48h+var_28], rax; int
0x180032405  mov     r9d, 8000FFFFh; char *
0x18003240b  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180032412  mov     edx, 18Dh; void *
0x180032417  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x18003241d  lea     rdx, [rsp+48h+arg_0]
0x180032422  mov     rcx, [rdi+170h]
0x180032429  call    ?Get@ConnectionProviderLoader@Wns@@QEBA?AV?$ComPtr@UIConnectionProvider@@@WRL@Microsoft@@XZ; Wns::ConnectionProviderLoader::Get(void)
0x18003242e  nop
0x18003242f  mov     rcx, rsi
0x180032432  call    ?ResetEvent@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBAXXZ
0x180032437  lea     rcx, [rdi+40h]; this
0x18003243b  call    ?Clear@CPTransactionRequestManager@Wns@@QEAAXXZ; Wns::CPTransactionRequestManager::Clear(void)
0x180032440  mov     rcx, [rsp+48h+arg_0]
0x180032445  mov     rax, [rcx]
0x180032448  mov     rax, [rax+20h]
0x18003244c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032451  mov     rcx, [rsp+48h]; this
0x180032456  lea     rdx, aFailedToDiscon; "Failed to Disconnect"
0x18003245d  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180032462  mov     r9d, eax; char *
0x180032465  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003246c  mov     edx, 252h; void *
0x180032471  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180032476  nop
0x180032477  lea     rcx, [rsp+48h+arg_0]
0x18003247c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180032481  mov     rbx, [rsp+48h+arg_8]
0x180032486  mov     rbp, [rsp+48h+arg_10]
0x18003248b  add     rsp, 30h
0x18003248f  pop     r14
0x180032491  pop     rdi
0x180032492  pop     rsi
0x180032493  retn
```
