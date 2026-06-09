# NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SID const *,void * const)

- ea: `0x18000ec0c`
- end: `0x18000ee79`
- name: `??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z`
- size: `621`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, DWORD, int, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ea40`

## callees

- `0x18000ec0c`
- `0x180010a94`
- `0x180022b00`
- `0x180028d18`
- `0x180038764`
- `0x18005dd80`
- `0x18007612c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ec2c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ec2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee13`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ecba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000ecba`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ecd8`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18000ecd8`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000eca5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18000eca5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ed25`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000ed25`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::RpcClient::RpcClient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        DWORD a4,
        int a5,
        LPCWSTR StringSecurityDescriptor)
{
  __int64 LengthSid; // rbx
  int v8; // eax
  LPCWSTR v9; // rbx
  DWORD v11; // ebx
  DWORD LastError; // ebx
  DWORD v13; // ebx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  DWORD v15; // [rsp+98h] [rbp+48h] BYREF

  v15 = a4;
  InitializeSRWLock((PSRWLOCK)a1);
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 3;
  *(_DWORD *)(a1 + 28) = 1;
  *(_DWORD *)(a1 + 32) = 1;
  *(_DWORD *)(a1 + 36) = 2;
  *(_QWORD *)(a1 + 40) = qword_1800D7AD0;
  *(_DWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  *(_QWORD *)(a1 + 88) = 0;
  if ( !IsValidSid(qword_1800E5CF8) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_180122070 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0) )
    {
      v15 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_1801084C9,
        0,
        0,
        (__int64)&v15);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, LastError);
    throw (win32_exception *)pExceptionObject;
  }
  LengthSid = GetLengthSid(qword_1800E5CF8);
  std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a1 + 56, LengthSid);
  if ( !CopySid(LengthSid, *(PSID *)(a1 + 56), qword_1800E5CF8) )
  {
    v13 = GetLastError();
    if ( (unsigned int)dword_180122070 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0) )
    {
      v15 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_180108455,
        0,
        0,
        (__int64)&v15);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, v13);
    throw (win32_exception *)pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 24) == 3 )
  {
    v8 = *(_DWORD *)(a1 + 28);
    if ( (v8 & 1) != 0 )
      *(_DWORD *)(a1 + 28) = v8 | 0x10;
  }
  v9 = StringSecurityDescriptor;
  if ( *((_QWORD *)StringSecurityDescriptor + 2) )
  {
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(a1 + 80);
    if ( *((_QWORD *)v9 + 3) > 7u )
      v9 = *(LPCWSTR *)v9;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v9, 1u, (PSECURITY_DESCRIPTOR *)(a1 + 88), 0) )
    {
      v11 = GetLastError();
      if ( (unsigned int)dword_180122070 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0) )
      {
        v15 = v11;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_180108489,
          0,
          0,
          (__int64)&v15);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, v11);
      throw (win32_exception *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000ec0c  mov     [rsp-28h+arg_8], rbx
0x18000ec11  mov     [rsp-28h+arg_18], r9d
0x18000ec16  mov     [rsp-28h+arg_0], rcx
0x18000ec1b  push    rbp
0x18000ec1c  push    rsi
0x18000ec1d  push    rdi
0x18000ec1e  push    r14
0x18000ec20  push    r15
0x18000ec22  mov     rbp, rsp
0x18000ec25  sub     rsp, 50h
0x18000ec29  mov     rdi, rcx
0x18000ec2c  call    cs:__imp_InitializeSRWLock
0x18000ec32  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18000ec39  mov     [rdi+8], rax
0x18000ec3d  mov     qword ptr [rdi+10h], 0
0x18000ec45  mov     dword ptr [rdi+18h], 3
0x18000ec4c  mov     eax, 1
0x18000ec51  mov     [rdi+1Ch], eax
0x18000ec54  mov     [rdi+20h], eax
0x18000ec57  mov     dword ptr [rdi+24h], 2
0x18000ec5e  lea     rax, qword_1800D7AD0
0x18000ec65  mov     [rdi+28h], rax
0x18000ec69  mov     dword ptr [rdi+30h], 0
0x18000ec70  lea     rsi, [rdi+38h]
0x18000ec74  mov     qword ptr [rsi], 0
0x18000ec7b  mov     qword ptr [rsi+8], 0
0x18000ec83  mov     qword ptr [rsi+10h], 0
0x18000ec8b  lea     rax, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18000ec92  mov     [rdi+50h], rax
0x18000ec96  mov     qword ptr [rdi+58h], 0
0x18000ec9e  lea     rcx, qword_1800E5CF8; pSid
0x18000eca5  call    cs:__imp_IsValidSid
0x18000ecab  test    eax, eax
0x18000ecad  jz      loc_18000EDAD
0x18000ecb3  lea     rcx, qword_1800E5CF8; pSid
0x18000ecba  call    cs:__imp_GetLengthSid
0x18000ecc0  mov     ebx, eax
0x18000ecc2  mov     edx, eax
0x18000ecc4  mov     rcx, rsi
0x18000ecc7  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000eccc  lea     r8, qword_1800E5CF8; pSourceSid
0x18000ecd3  mov     rdx, [rsi]; pDestinationSid
0x18000ecd6  mov     ecx, ebx; nDestinationSidLength
0x18000ecd8  call    cs:__imp_CopySid
0x18000ecde  test    eax, eax
0x18000ece0  jz      loc_18000EE13
0x18000ece6  cmp     dword ptr [rdi+18h], 3
0x18000ecea  jnz     short loc_18000ECF9
0x18000ecec  mov     eax, [rdi+1Ch]
0x18000ecef  test    al, 1
0x18000ecf1  jz      short loc_18000ECF9
0x18000ecf3  or      eax, 10h
0x18000ecf6  mov     [rdi+1Ch], eax
0x18000ecf9  mov     rbx, [rbp+StringSecurityDescriptor]
0x18000ecfd  cmp     qword ptr [rbx+10h], 0
0x18000ed02  jz      short loc_18000ED2F
0x18000ed04  lea     rcx, [rdi+50h]
0x18000ed08  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18000ed0d  cmp     qword ptr [rbx+18h], 7
0x18000ed12  jbe     short loc_18000ED17
0x18000ed14  mov     rbx, [rbx]
0x18000ed17  xor     r9d, r9d; SecurityDescriptorSize
0x18000ed1a  lea     r8, [rdi+58h]; SecurityDescriptor
0x18000ed1e  lea     edx, [r9+1]; StringSDRevision
0x18000ed22  mov     rcx, rbx; StringSecurityDescriptor
0x18000ed25  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000ed2b  test    eax, eax
0x18000ed2d  jz      short loc_18000ED46
0x18000ed2f  mov     rax, rdi
0x18000ed32  mov     rbx, [rsp+50h+arg_8]
0x18000ed3a  add     rsp, 50h
0x18000ed3e  pop     r15
0x18000ed40  pop     r14
0x18000ed42  pop     rdi
0x18000ed43  pop     rsi
0x18000ed44  pop     rbp
0x18000ed45  retn
0x18000ed46  call    cs:__imp_GetLastError
0x18000ed4c  nop
0x18000ed4d  mov     ebx, eax
0x18000ed4f  mov     ecx, cs:dword_180122070
0x18000ed55  cmp     ecx, 2
0x18000ed58  jbe     short loc_18000ED91
0x18000ed5a  xor     edx, edx
0x18000ed5c  lea     rcx, dword_180122070
0x18000ed63  call    _tlgKeywordOn
0x18000ed68  test    al, al
0x18000ed6a  jz      short loc_18000ED91
0x18000ed6c  mov     [rbp+arg_18], ebx
0x18000ed6f  lea     rax, [rbp+arg_18]
0x18000ed73  mov     [rsp+50h+var_30], rax
0x18000ed78  xor     r9d, r9d
0x18000ed7b  xor     r8d, r8d
0x18000ed7e  lea     rdx, byte_180108489
0x18000ed85  lea     rcx, dword_180122070
0x18000ed8c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000ed91  mov     edx, ebx; unsigned int
0x18000ed93  lea     rcx, [rbp+pExceptionObject]; this
0x18000ed97  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18000ed9c  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18000eda3  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000eda7  call    _CxxThrowException_0
0x18000edad  call    cs:__imp_GetLastError
0x18000edb3  mov     ebx, eax
0x18000edb5  mov     ecx, cs:dword_180122070
0x18000edbb  cmp     ecx, 2
0x18000edbe  jbe     short loc_18000EDF7
0x18000edc0  xor     edx, edx
0x18000edc2  lea     rcx, dword_180122070
0x18000edc9  call    _tlgKeywordOn
0x18000edce  test    al, al
0x18000edd0  jz      short loc_18000EDF7
0x18000edd2  mov     [rbp+arg_18], ebx
0x18000edd5  lea     rax, [rbp+arg_18]
0x18000edd9  mov     [rsp+50h+var_30], rax
0x18000edde  xor     r9d, r9d
0x18000ede1  xor     r8d, r8d
0x18000ede4  lea     rdx, byte_1801084C9
0x18000edeb  lea     rcx, dword_180122070
0x18000edf2  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000edf7  mov     edx, ebx; unsigned int
0x18000edf9  lea     rcx, [rbp+pExceptionObject]; this
0x18000edfd  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18000ee02  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18000ee09  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ee0d  call    _CxxThrowException_0
0x18000ee13  call    cs:__imp_GetLastError
0x18000ee19  mov     ebx, eax
0x18000ee1b  mov     ecx, cs:dword_180122070
0x18000ee21  cmp     ecx, 2
0x18000ee24  jbe     short loc_18000EE5D
0x18000ee26  xor     edx, edx
0x18000ee28  lea     rcx, dword_180122070
0x18000ee2f  call    _tlgKeywordOn
0x18000ee34  test    al, al
0x18000ee36  jz      short loc_18000EE5D
0x18000ee38  mov     [rbp+arg_18], ebx
0x18000ee3b  lea     rax, [rbp+arg_18]
0x18000ee3f  mov     [rsp+50h+var_30], rax
0x18000ee44  xor     r9d, r9d
0x18000ee47  xor     r8d, r8d
0x18000ee4a  lea     rdx, byte_180108455
0x18000ee51  lea     rcx, dword_180122070
0x18000ee58  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18000ee5d  mov     edx, ebx; unsigned int
0x18000ee5f  lea     rcx, [rbp+pExceptionObject]; this
0x18000ee63  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18000ee68  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18000ee6f  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000ee73  call    _CxxThrowException_0
```
