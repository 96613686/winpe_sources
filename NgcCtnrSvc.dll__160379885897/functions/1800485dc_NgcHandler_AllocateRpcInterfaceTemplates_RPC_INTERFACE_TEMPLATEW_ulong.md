# NgcHandler::AllocateRpcInterfaceTemplates(RPC_INTERFACE_TEMPLATEW * *,ulong *)

- ea: `0x1800485dc`
- end: `0x180048848`
- name: `?AllocateRpcInterfaceTemplates@NgcHandler@@QEAAJPEAPEAURPC_INTERFACE_TEMPLATEW@@PEAK@Z`
- size: `620`
- prototype: `__int64 __fastcall(NgcHandler *__hidden this, struct RPC_INTERFACE_TEMPLATEW **, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800485d0`

## callees

- `0x180018194`
- `0x180019c94`
- `0x18001ae60`
- `0x1800485dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800486be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180048627`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800486ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180048627`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800486ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcHandler::AllocateRpcInterfaceTemplates(
        NgcHandler *this,
        struct RPC_INTERFACE_TEMPLATEW **a2,
        unsigned int *a3)
{
  signed int v5; // eax
  unsigned int v6; // ebx
  signed int LastError; // eax
  NgcHandler *v8; // rcx
  void **v10; // [rsp+30h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR v11; // [rsp+38h] [rbp-18h] BYREF
  void **v12; // [rsp+40h] [rbp-10h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-8h] BYREF
  NgcHandler *v14; // [rsp+70h] [rbp+20h] BYREF

  v14 = this;
  v12 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  SecurityDescriptor = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v12);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:LSD:(A;;GRGWGX;;;SY)", 1u, &SecurityDescriptor, 0) )
  {
    v10 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
    v11 = 0;
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v10);
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:LSD:(A;;GRGWGX;;;SY)", 1u, &v11, 0) )
    {
      wil::make_unique_cotaskmem_nothrow<RPC_INTERFACE_TEMPLATEW [0]>(&v14);
      v8 = v14;
      if ( v14 )
      {
        *(_DWORD *)v14 = 0;
        *((_QWORD *)v8 + 1) = qword_180087470;
        *((_QWORD *)v8 + 2) = 0;
        *((_QWORD *)v8 + 8) = L"INgcHandler";
        *((_QWORD *)v8 + 3) = 0;
        *((_DWORD *)v8 + 8) = 41;
        *(_QWORD *)((char *)v8 + 36) = 1234;
        *((_QWORD *)v8 + 6) = 0;
        *((_QWORD *)v8 + 7) = 0;
        *((_QWORD *)v8 + 9) = SecurityDescriptor;
        *((_QWORD *)v8 + 11) = qword_180087180;
        *((_QWORD *)v8 + 18) = L"INgcSecureBioHandler";
        *((_DWORD *)v8 + 20) = 0;
        *((_QWORD *)v8 + 12) = 0;
        *((_QWORD *)v8 + 13) = 0;
        *((_DWORD *)v8 + 28) = 41;
        *(_QWORD *)((char *)v8 + 116) = 1234;
        *((_QWORD *)v8 + 16) = 0;
        *((_QWORD *)v8 + 17) = 0;
        *((_QWORD *)v8 + 19) = v11;
        *a3 = 2;
        *a2 = v8;
        SecurityDescriptor = 0;
        v11 = 0;
        v10 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v10);
        v6 = 0;
      }
      else
      {
        if ( (unsigned int)dword_1800BE0B8 > 2 )
        {
          LODWORD(v14) = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800BE0B8,
            (unsigned int)byte_1800AB6ED,
            0,
            0,
            (__int64)&v14);
        }
        v10 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v10);
        v6 = -2147024882;
      }
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        LODWORD(v14) = v6;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800BE0B8,
          (unsigned int)&dword_1800AB7AC,
          0,
          0,
          (__int64)&v14);
      }
      v10 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
      Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v10);
    }
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      LODWORD(v14) = v6;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800BE0B8,
        (unsigned int)&byte_1800AB7EF,
        0,
        0,
        (__int64)&v14);
    }
  }
  v12 = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(&v12);
  return v6;
}

```

## disassembly

```asm
0x1800485dc  mov     [rsp-18h+arg_8], rbx
0x1800485e1  mov     [rsp-18h+arg_10], rsi
0x1800485e6  mov     [rsp-18h+arg_0], rcx
0x1800485eb  push    rbp
0x1800485ec  push    rdi
0x1800485ed  push    r14
0x1800485ef  mov     rbp, rsp
0x1800485f2  sub     rsp, 50h
0x1800485f6  lea     r14, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x1800485fd  xor     esi, esi
0x1800485ff  lea     rcx, [rbp+var_10]
0x180048603  mov     [rbp+var_10], r14
0x180048607  mov     [rbp+SecurityDescriptor], rsi
0x18004860b  mov     rbx, r8
0x18004860e  mov     rdi, rdx
0x180048611  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180048616  xor     r9d, r9d; SecurityDescriptorSize
0x180048619  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004861d  lea     edx, [rsi+1]; StringSDRevision
0x180048620  lea     rcx, aOLsdAGrgwgxSy; "O:LSD:(A;;GRGWGX;;;SY)"
0x180048627  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004862e  nop     dword ptr [rax+rax+00h]
0x180048633  test    eax, eax
0x180048635  jnz     short loc_18004868B
0x180048637  call    cs:__imp_GetLastError
0x18004863e  nop     dword ptr [rax+rax+00h]
0x180048643  mov     ebx, eax
0x180048645  test    eax, eax
0x180048647  jle     short loc_180048652
0x180048649  movzx   ebx, ax
0x18004864c  or      ebx, 80070000h
0x180048652  mov     eax, cs:dword_1800BE0B8
0x180048658  cmp     eax, 2
0x18004865b  jbe     loc_180048823
0x180048661  lea     rax, [rbp+arg_0]
0x180048665  mov     dword ptr [rbp+arg_0], ebx
0x180048668  xor     r9d, r9d
0x18004866b  mov     [rsp+50h+var_30], rax
0x180048670  xor     r8d, r8d
0x180048673  lea     rdx, byte_1800AB7EF
0x18004867a  lea     rcx, dword_1800BE0B8
0x180048681  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180048686  jmp     loc_180048823
0x18004868b  lea     rcx, [rbp+var_20]
0x18004868f  mov     [rbp+var_20], r14
0x180048693  mov     [rbp+var_18], rsi
0x180048697  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18004869c  xor     r9d, r9d; SecurityDescriptorSize
0x18004869f  lea     r8, [rbp+var_18]; SecurityDescriptor
0x1800486a3  lea     rcx, aOLsdAGrgwgxSy; "O:LSD:(A;;GRGWGX;;;SY)"
0x1800486aa  lea     edx, [r9+1]; StringSDRevision
0x1800486ae  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800486b5  nop     dword ptr [rax+rax+00h]
0x1800486ba  test    eax, eax
0x1800486bc  jnz     short loc_18004871B
0x1800486be  call    cs:__imp_GetLastError
0x1800486c5  nop     dword ptr [rax+rax+00h]
0x1800486ca  mov     ebx, eax
0x1800486cc  test    eax, eax
0x1800486ce  jle     short loc_1800486D9
0x1800486d0  movzx   ebx, ax
0x1800486d3  or      ebx, 80070000h
0x1800486d9  mov     eax, cs:dword_1800BE0B8
0x1800486df  cmp     eax, 2
0x1800486e2  jbe     short loc_180048709
0x1800486e4  lea     rax, [rbp+arg_0]
0x1800486e8  mov     dword ptr [rbp+arg_0], ebx
0x1800486eb  xor     r9d, r9d
0x1800486ee  mov     [rsp+50h+var_30], rax
0x1800486f3  xor     r8d, r8d
0x1800486f6  lea     rdx, dword_1800AB7AC
0x1800486fd  lea     rcx, dword_1800BE0B8
0x180048704  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180048709  lea     rcx, [rbp+var_20]
0x18004870d  mov     [rbp+var_20], r14
0x180048711  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180048716  jmp     loc_180048823
0x18004871b  lea     rcx, [rbp+arg_0]
0x18004871f  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@URPC_INTERFACE_TEMPLATEW@@@wil@@YA?AV?$unique_ptr@$$BY0A@URPC_INTERFACE_TEMPLATEW@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<RPC_INTERFACE_TEMPLATEW [0]>(unsigned __int64)
0x180048724  mov     rcx, [rbp+arg_0]
0x180048728  test    rcx, rcx
0x18004872b  jnz     short loc_180048778
0x18004872d  mov     eax, cs:dword_1800BE0B8
0x180048733  cmp     eax, 2
0x180048736  jbe     short loc_180048761
0x180048738  lea     rax, [rbp+arg_0]
0x18004873c  mov     dword ptr [rbp+arg_0], 8007000Eh
0x180048743  xor     r9d, r9d
0x180048746  mov     [rsp+50h+var_30], rax
0x18004874b  xor     r8d, r8d
0x18004874e  lea     rdx, byte_1800AB6ED
0x180048755  lea     rcx, dword_1800BE0B8
0x18004875c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180048761  lea     rcx, [rbp+var_20]
0x180048765  mov     [rbp+var_20], r14
0x180048769  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18004876e  mov     ebx, 8007000Eh
0x180048773  jmp     loc_180048823
0x180048778  mov     [rcx], esi
0x18004877a  lea     rax, qword_180087470
0x180048781  mov     [rcx+8], rax
0x180048785  mov     r8d, 29h ; ')'
0x18004878b  mov     [rcx+10h], rsi
0x18004878f  lea     rax, aIngchandler; "INgcHandler"
0x180048796  mov     [rcx+40h], rax
0x18004879a  mov     [rcx+18h], rsi
0x18004879e  mov     [rcx+20h], r8d
0x1800487a2  mov     qword ptr [rcx+24h], 4D2h
0x1800487aa  mov     [rcx+30h], rsi
0x1800487ae  mov     [rcx+38h], rsi
0x1800487b2  mov     rax, [rbp+SecurityDescriptor]
0x1800487b6  mov     [rcx+48h], rax
0x1800487ba  lea     rax, qword_180087180
0x1800487c1  mov     [rcx+58h], rax
0x1800487c5  lea     rax, aIngcsecurebioh; "INgcSecureBioHandler"
0x1800487cc  mov     [rcx+90h], rax
0x1800487d3  mov     [rcx+50h], esi
0x1800487d6  mov     [rcx+60h], rsi
0x1800487da  mov     [rcx+68h], rsi
0x1800487de  mov     [rcx+70h], r8d
0x1800487e2  mov     qword ptr [rcx+74h], 4D2h
0x1800487ea  mov     [rcx+80h], rsi
0x1800487f1  mov     [rcx+88h], rsi
0x1800487f8  mov     rax, [rbp+var_18]
0x1800487fc  mov     [rcx+98h], rax
0x180048803  mov     dword ptr [rbx], 2
0x180048809  mov     [rdi], rcx
0x18004880c  lea     rcx, [rbp+var_20]
0x180048810  mov     [rbp+SecurityDescriptor], rsi
0x180048814  mov     [rbp+var_18], rsi
0x180048818  mov     [rbp+var_20], r14
0x18004881c  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180048821  mov     ebx, esi
0x180048823  lea     rcx, [rbp+var_10]
0x180048827  mov     [rbp+var_10], r14
0x18004882b  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x180048830  lea     r11, [rsp+50h+var_s0]
0x180048835  mov     eax, ebx
0x180048837  mov     rbx, [r11+28h]
0x18004883b  mov     rsi, [r11+30h]
0x18004883f  mov     rsp, r11
0x180048842  pop     r14
0x180048844  pop     rdi
0x180048845  pop     rbp
0x180048846  retn
```
