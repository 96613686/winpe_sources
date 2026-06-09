# ProvisioningHandler::AllocateRpcInterfaceTemplates(RPC_INTERFACE_TEMPLATEW * *,ulong *)

- ea: `0x18001f6a8`
- end: `0x18001f9dd`
- name: `?AllocateRpcInterfaceTemplates@ProvisioningHandler@@QEAAJPEAPEAURPC_INTERFACE_TEMPLATEW@@PEAK@Z`
- size: `821`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, struct RPC_INTERFACE_TEMPLATEW **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004eaf0`

## callees

- `0x180018194`
- `0x180019c94`
- `0x18001ae60`
- `0x18001f6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7f9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f7f9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f7cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f7e6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f7cd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f838`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f772`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f838`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f762`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f828`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f762`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001f828`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18001f703`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x18001f703`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ProvisioningHandler::AllocateRpcInterfaceTemplates(
        LPCRITICAL_SECTION lpCriticalSection,
        struct RPC_INTERFACE_TEMPLATEW **a2,
        unsigned int *a3)
{
  int v6; // eax
  signed int LastError; // eax
  unsigned int v8; // ebx
  PSECURITY_DESCRIPTOR v9; // rdi
  signed int v10; // eax
  _DWORD *v11; // rcx
  void **v13; // [rsp+30h] [rbp-30h] BYREF
  PSECURITY_DESCRIPTOR v14; // [rsp+38h] [rbp-28h] BYREF
  void **v15; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-18h] BYREF
  void **v17; // [rsp+50h] [rbp-10h] BYREF
  void *v18; // [rsp+58h] [rbp-8h] BYREF
  _DWORD *v19; // [rsp+A8h] [rbp+48h] BYREF

  v17 = &Microsoft::WRL::Wrappers::HandleT<TransientObjectSecurityDescriptorTraits>::`vftable';
  v18 = 0;
  v15 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  SecurityDescriptor = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v17);
  v6 = QueryTransientObjectSecurityDescriptor(9, L"NgcContainerRpc\\NgcProvisioningHandlerInterface", &v18);
  if ( v6 >= 0 )
  {
    v9 = v18;
    EnterCriticalSection(lpCriticalSection);
    LOBYTE(lpCriticalSection[1].DebugInfo) = 1;
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 4 )
    {
      LODWORD(v19) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)byte_1800AC80B,
        0,
        0,
        (__int64)&v19);
    }
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v15);
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:LSD:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;IU)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v19) = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&unk_1800AC7C8,
          0,
          0,
          (__int64)&v19);
      }
      goto LABEL_22;
    }
    v9 = SecurityDescriptor;
    EnterCriticalSection(lpCriticalSection);
    LOBYTE(lpCriticalSection[1].DebugInfo) = 0;
  }
  LeaveCriticalSection(lpCriticalSection);
  v13 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  v14 = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v13);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:LSD:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;S-1-5-80-244839577-329614340-306960744-2725339395-521240708)",
         1u,
         &v14,
         0) )
  {
    wil::make_unique_cotaskmem_nothrow<RPC_INTERFACE_TEMPLATEW [0]>(&v19);
    v11 = v19;
    if ( v19 )
    {
      *v19 = 0;
      *((_QWORD *)v11 + 1) = qword_180088F20;
      *((_QWORD *)v11 + 2) = 0;
      *((_QWORD *)v11 + 8) = L"INgcProvisioningHandler";
      *((_QWORD *)v11 + 3) = 0;
      v11[8] = 41;
      *(_QWORD *)(v11 + 9) = 1234;
      *((_QWORD *)v11 + 6) = 0;
      *((_QWORD *)v11 + 7) = 0;
      *((_QWORD *)v11 + 9) = v9;
      *((_QWORD *)v11 + 11) = qword_180089570;
      *((_QWORD *)v11 + 18) = L"IVscProvisioningHandler";
      v11[20] = 0;
      *((_QWORD *)v11 + 12) = 0;
      *((_QWORD *)v11 + 13) = 0;
      v11[28] = 41;
      *(_QWORD *)(v11 + 29) = 1234;
      *((_QWORD *)v11 + 16) = 0;
      *((_QWORD *)v11 + 17) = 0;
      *((_QWORD *)v11 + 19) = v14;
      *a3 = 2;
      *a2 = (struct RPC_INTERFACE_TEMPLATEW *)v11;
      v18 = 0;
      SecurityDescriptor = 0;
      v14 = 0;
      v13 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v13);
      v8 = 0;
    }
    else
    {
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v19) = -2147024882;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)byte_1800AC861,
          0,
          0,
          (__int64)&v19);
      }
      v13 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v13);
      v8 = -2147024882;
    }
  }
  else
  {
    v10 = GetLastError();
    v8 = v10;
    if ( v10 > 0 )
      v8 = (unsigned __int16)v10 | 0x80070000;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v19) = v8;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)byte_1800AC8AB,
        0,
        0,
        (__int64)&v19);
    }
    v13 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v13);
  }
LABEL_22:
  v15 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v15);
  v17 = &Microsoft::WRL::Wrappers::HandleT<TransientObjectSecurityDescriptorTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v17);
  return v8;
}

```

## disassembly

```asm
0x18001f6a8  mov     [rsp-28h+arg_0], rbx
0x18001f6ad  mov     [rsp-28h+arg_8], rsi
0x18001f6b2  push    rbp
0x18001f6b3  push    rdi
0x18001f6b4  push    r12
0x18001f6b6  push    r14
0x18001f6b8  push    r15
0x18001f6ba  mov     rbp, rsp
0x18001f6bd  sub     rsp, 60h
0x18001f6c1  mov     rbx, rcx
0x18001f6c4  lea     rax, ??_7?$HandleT@UTransientObjectSecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<TransientObjectSecurityDescriptorTraits>::`vftable'
0x18001f6cb  xor     r15d, r15d
0x18001f6ce  mov     [rbp+var_10], rax
0x18001f6d2  lea     r12, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18001f6d9  mov     [rbp+var_8], r15
0x18001f6dd  lea     rcx, [rbp+var_10]
0x18001f6e1  mov     [rbp+var_20], r12
0x18001f6e5  mov     [rbp+SecurityDescriptor], r15
0x18001f6e9  mov     rsi, r8
0x18001f6ec  mov     r14, rdx
0x18001f6ef  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f6f4  lea     r8, [rbp+var_8]
0x18001f6f8  lea     rdx, aNgccontainerrp; "NgcContainerRpc\\NgcProvisioningHandler"...
0x18001f6ff  lea     ecx, [r15+9]
0x18001f703  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x18001f70a  nop     dword ptr [rax+rax+00h]
0x18001f70f  test    eax, eax
0x18001f711  jns     loc_18001F7DF
0x18001f717  mov     ecx, cs:dword_1800BE0B8
0x18001f71d  cmp     ecx, 4
0x18001f720  jbe     short loc_18001F747
0x18001f722  mov     dword ptr [rbp+arg_18], eax
0x18001f725  lea     rdx, byte_1800AC80B
0x18001f72c  lea     rax, [rbp+arg_18]
0x18001f730  xor     r9d, r9d
0x18001f733  xor     r8d, r8d
0x18001f736  mov     [rsp+60h+var_40], rax
0x18001f73b  lea     rcx, dword_1800BE0B8
0x18001f742  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f747  lea     rcx, [rbp+var_20]
0x18001f74b  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f750  xor     r9d, r9d; SecurityDescriptorSize
0x18001f753  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001f757  lea     rcx, aOLsdAGrgwgxSyA; "O:LSD:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;IU)"
0x18001f75e  lea     edx, [r9+1]; StringSDRevision
0x18001f762  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001f769  nop     dword ptr [rax+rax+00h]
0x18001f76e  test    eax, eax
0x18001f770  jnz     short loc_18001F7C6
0x18001f772  call    cs:__imp_GetLastError
0x18001f779  nop     dword ptr [rax+rax+00h]
0x18001f77e  mov     ebx, eax
0x18001f780  test    eax, eax
0x18001f782  jle     short loc_18001F78D
0x18001f784  movzx   ebx, ax
0x18001f787  or      ebx, 80070000h
0x18001f78d  mov     eax, cs:dword_1800BE0B8
0x18001f793  cmp     eax, 2
0x18001f796  jbe     loc_18001F9A0
0x18001f79c  lea     rax, [rbp+arg_18]
0x18001f7a0  mov     dword ptr [rbp+arg_18], ebx
0x18001f7a3  xor     r9d, r9d
0x18001f7a6  mov     [rsp+60h+var_40], rax
0x18001f7ab  xor     r8d, r8d
0x18001f7ae  lea     rdx, unk_1800AC7C8
0x18001f7b5  lea     rcx, dword_1800BE0B8
0x18001f7bc  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f7c1  jmp     loc_18001F9A0
0x18001f7c6  mov     rdi, [rbp+SecurityDescriptor]
0x18001f7ca  mov     rcx, rbx; lpCriticalSection
0x18001f7cd  call    cs:__imp_EnterCriticalSection
0x18001f7d4  nop     dword ptr [rax+rax+00h]
0x18001f7d9  mov     [rbx+28h], r15b
0x18001f7dd  jmp     short loc_18001F7F6
0x18001f7df  mov     rdi, [rbp+var_8]
0x18001f7e3  mov     rcx, rbx; lpCriticalSection
0x18001f7e6  call    cs:__imp_EnterCriticalSection
0x18001f7ed  nop     dword ptr [rax+rax+00h]
0x18001f7f2  mov     byte ptr [rbx+28h], 1
0x18001f7f6  mov     rcx, rbx; lpCriticalSection
0x18001f7f9  call    cs:__imp_LeaveCriticalSection
0x18001f800  nop     dword ptr [rax+rax+00h]
0x18001f805  lea     rcx, [rbp+var_30]
0x18001f809  mov     [rbp+var_30], r12
0x18001f80d  mov     [rbp+var_28], r15
0x18001f811  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f816  xor     r9d, r9d; SecurityDescriptorSize
0x18001f819  lea     r8, [rbp+var_28]; SecurityDescriptor
0x18001f81d  lea     rcx, aOLsdAGrgwgxSyA_0; "O:LSD:(A;;GRGWGX;;;SY)(A;;GRGWGX;;;S-1-"...
0x18001f824  lea     edx, [r9+1]; StringSDRevision
0x18001f828  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001f82f  nop     dword ptr [rax+rax+00h]
0x18001f834  test    eax, eax
0x18001f836  jnz     short loc_18001F895
0x18001f838  call    cs:__imp_GetLastError
0x18001f83f  nop     dword ptr [rax+rax+00h]
0x18001f844  mov     ebx, eax
0x18001f846  test    eax, eax
0x18001f848  jle     short loc_18001F853
0x18001f84a  movzx   ebx, ax
0x18001f84d  or      ebx, 80070000h
0x18001f853  mov     eax, cs:dword_1800BE0B8
0x18001f859  cmp     eax, 2
0x18001f85c  jbe     short loc_18001F883
0x18001f85e  lea     rax, [rbp+arg_18]
0x18001f862  mov     dword ptr [rbp+arg_18], ebx
0x18001f865  xor     r9d, r9d
0x18001f868  mov     [rsp+60h+var_40], rax
0x18001f86d  xor     r8d, r8d
0x18001f870  lea     rdx, byte_1800AC8AB
0x18001f877  lea     rcx, dword_1800BE0B8
0x18001f87e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f883  lea     rcx, [rbp+var_30]
0x18001f887  mov     [rbp+var_30], r12
0x18001f88b  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f890  jmp     loc_18001F9A0
0x18001f895  lea     rcx, [rbp+arg_18]
0x18001f899  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@URPC_INTERFACE_TEMPLATEW@@@wil@@YA?AV?$unique_ptr@$$BY0A@URPC_INTERFACE_TEMPLATEW@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<RPC_INTERFACE_TEMPLATEW [0]>(unsigned __int64)
0x18001f89e  mov     rcx, [rbp+arg_18]
0x18001f8a2  test    rcx, rcx
0x18001f8a5  jnz     short loc_18001F8F2
0x18001f8a7  mov     eax, cs:dword_1800BE0B8
0x18001f8ad  cmp     eax, 2
0x18001f8b0  jbe     short loc_18001F8DB
0x18001f8b2  lea     rax, [rbp+arg_18]
0x18001f8b6  mov     dword ptr [rbp+arg_18], 8007000Eh
0x18001f8bd  xor     r9d, r9d
0x18001f8c0  mov     [rsp+60h+var_40], rax
0x18001f8c5  xor     r8d, r8d
0x18001f8c8  lea     rdx, byte_1800AC861
0x18001f8cf  lea     rcx, dword_1800BE0B8
0x18001f8d6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001f8db  lea     rcx, [rbp+var_30]
0x18001f8df  mov     [rbp+var_30], r12
0x18001f8e3  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f8e8  mov     ebx, 8007000Eh
0x18001f8ed  jmp     loc_18001F9A0
0x18001f8f2  mov     [rcx], r15d
0x18001f8f5  lea     rax, qword_180088F20
0x18001f8fc  mov     [rcx+8], rax
0x18001f900  mov     r8d, 29h ; ')'
0x18001f906  mov     [rcx+10h], r15
0x18001f90a  lea     rax, aIngcprovisioni; "INgcProvisioningHandler"
0x18001f911  mov     [rcx+40h], rax
0x18001f915  lea     rax, qword_180089570
0x18001f91c  mov     [rcx+18h], r15
0x18001f920  mov     [rcx+20h], r8d
0x18001f924  mov     qword ptr [rcx+24h], 4D2h
0x18001f92c  mov     [rcx+30h], r15
0x18001f930  mov     [rcx+38h], r15
0x18001f934  mov     [rcx+48h], rdi
0x18001f938  mov     [rcx+58h], rax
0x18001f93c  lea     rax, aIvscprovisioni; "IVscProvisioningHandler"
0x18001f943  mov     [rcx+90h], rax
0x18001f94a  mov     [rcx+50h], r15d
0x18001f94e  mov     [rcx+60h], r15
0x18001f952  mov     [rcx+68h], r15
0x18001f956  mov     [rcx+70h], r8d
0x18001f95a  mov     qword ptr [rcx+74h], 4D2h
0x18001f962  mov     [rcx+80h], r15
0x18001f969  mov     [rcx+88h], r15
0x18001f970  mov     rax, [rbp+var_28]
0x18001f974  mov     [rcx+98h], rax
0x18001f97b  mov     dword ptr [rsi], 2
0x18001f981  mov     [r14], rcx
0x18001f984  lea     rcx, [rbp+var_30]
0x18001f988  mov     [rbp+var_8], r15
0x18001f98c  mov     [rbp+SecurityDescriptor], r15
0x18001f990  mov     [rbp+var_28], r15
0x18001f994  mov     [rbp+var_30], r12
0x18001f998  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f99d  mov     ebx, r15d
0x18001f9a0  lea     rcx, [rbp+var_20]
0x18001f9a4  mov     [rbp+var_20], r12
0x18001f9a8  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f9ad  lea     rax, ??_7?$HandleT@UTransientObjectSecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<TransientObjectSecurityDescriptorTraits>::`vftable'
0x18001f9b4  lea     rcx, [rbp+var_10]
0x18001f9b8  mov     [rbp+var_10], rax
0x18001f9bc  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18001f9c1  lea     r11, [rsp+60h+var_s0]
0x18001f9c6  mov     eax, ebx
0x18001f9c8  mov     rbx, [r11+30h]
0x18001f9cc  mov     rsi, [r11+38h]
0x18001f9d0  mov     rsp, r11
0x18001f9d3  pop     r15
0x18001f9d5  pop     r14
0x18001f9d7  pop     r12
0x18001f9d9  pop     rdi
0x18001f9da  pop     rbp
0x18001f9db  retn
```
