# NgcUtils::RpcClient::RpcClient(ulong,ulong,ulong,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,_SID const *,void * const)

- ea: `0x18005e54c`
- end: `0x18005e826`
- name: `??0RpcClient@NgcUtils@@QEAA@KKKKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBU_SID@@QEAX@Z`
- size: `730`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, DWORD, int, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055bb4`

## callees

- `0x180018194`
- `0x180019c94`
- `0x18001ced8`
- `0x18002d518`
- `0x18002d554`
- `0x180032e4c`
- `0x180037c34`
- `0x18005e54c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005e570`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18005e570`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e74e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005e7ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005e6b5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005e6b5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e5f5`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005e5f5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e662`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005e662`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005e5da`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18005e5da`

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
  PSID *v7; // rsi
  DWORD LengthSid; // eax
  DWORD v9; // r15d
  char *v10; // rdx
  __int64 v11; // r14
  unsigned __int64 v12; // rcx
  size_t v13; // rbx
  int v14; // eax
  LPCWSTR v15; // rbx
  DWORD v17; // ebx
  DWORD LastError; // ebx
  DWORD v19; // ebx
  _BYTE pExceptionObject[32]; // [rsp+30h] [rbp-20h] BYREF
  DWORD v21; // [rsp+A8h] [rbp+58h] BYREF

  v21 = a4;
  InitializeSRWLock((PSRWLOCK)a1);
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  *(_DWORD *)(a1 + 24) = 3;
  *(_DWORD *)(a1 + 28) = 1;
  *(_DWORD *)(a1 + 32) = 1;
  *(_DWORD *)(a1 + 36) = 2;
  *(_QWORD *)(a1 + 40) = qword_1800896F0;
  *(_DWORD *)(a1 + 48) = 0;
  v7 = (PSID *)(a1 + 56);
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = &Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable';
  *(_QWORD *)(a1 + 88) = 0;
  if ( !IsValidSid(qword_180098278) )
  {
    LastError = GetLastError();
    if ( (unsigned int)dword_1800BE0B8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0) )
    {
      v21 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&dword_1800AEA04,
        0,
        0,
        (__int64)&v21);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, LastError);
    throw (win32_exception *)pExceptionObject;
  }
  LengthSid = GetLengthSid(qword_180098278);
  v9 = LengthSid;
  v10 = (char *)*v7;
  v11 = *(_QWORD *)(a1 + 64);
  v12 = v11 - *(_QWORD *)(a1 + 56);
  if ( LengthSid >= v12 )
  {
    if ( LengthSid > v12 )
    {
      if ( (unsigned __int64)LengthSid <= *(_QWORD *)(a1 + 72) - (_QWORD)v10 )
      {
        v13 = LengthSid - v12;
        memset_0(*(void **)(a1 + 64), 0, v13);
        *(_QWORD *)(a1 + 64) = v13 + v11;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a1 + 56, LengthSid);
      }
    }
  }
  else
  {
    *(_QWORD *)(a1 + 64) = &v10[LengthSid];
  }
  if ( !CopySid(v9, *v7, qword_180098278) )
  {
    v19 = GetLastError();
    if ( (unsigned int)dword_1800BE0B8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0) )
    {
      v21 = v19;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)byte_1800AEA35,
        0,
        0,
        (__int64)&v21);
    }
    win32_exception::win32_exception((win32_exception *)pExceptionObject, v19);
    throw (win32_exception *)pExceptionObject;
  }
  if ( *(_DWORD *)(a1 + 24) == 3 )
  {
    v14 = *(_DWORD *)(a1 + 28);
    if ( (v14 & 1) != 0 )
      *(_DWORD *)(a1 + 28) = v14 | 0x10;
  }
  v15 = StringSecurityDescriptor;
  if ( *((_QWORD *)StringSecurityDescriptor + 2) )
  {
    Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(a1 + 80);
    if ( *((_QWORD *)v15 + 3) > 7u )
      v15 = *(LPCWSTR *)v15;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, (PSECURITY_DESCRIPTOR *)(a1 + 88), 0) )
    {
      v17 = GetLastError();
      if ( (unsigned int)dword_1800BE0B8 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800BE0B8, 0) )
      {
        v21 = v17;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800AE99F,
          0,
          0,
          (__int64)&v21);
      }
      win32_exception::win32_exception((win32_exception *)pExceptionObject, v17);
      throw (win32_exception *)pExceptionObject;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18005e54c  mov     [rsp-38h+arg_8], rbx
0x18005e551  mov     [rsp-38h+arg_18], r9d
0x18005e556  mov     [rsp-38h+arg_0], rcx
0x18005e55b  push    rbp
0x18005e55c  push    rsi
0x18005e55d  push    rdi
0x18005e55e  push    r12
0x18005e560  push    r13
0x18005e562  push    r14
0x18005e564  push    r15
0x18005e566  mov     rbp, rsp
0x18005e569  sub     rsp, 50h
0x18005e56d  mov     rdi, rcx
0x18005e570  call    cs:__imp_InitializeSRWLock
0x18005e577  nop     dword ptr [rax+rax+00h]
0x18005e57c  lea     rax, ??_7?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::`vftable'
0x18005e583  mov     [rdi+8], rax
0x18005e587  xor     r14d, r14d
0x18005e58a  mov     [rdi+10h], r14
0x18005e58e  mov     dword ptr [rdi+18h], 3
0x18005e595  lea     eax, [r14+1]
0x18005e599  mov     [rdi+1Ch], eax
0x18005e59c  mov     [rdi+20h], eax
0x18005e59f  mov     dword ptr [rdi+24h], 2
0x18005e5a6  lea     rax, qword_1800896F0
0x18005e5ad  mov     [rdi+28h], rax
0x18005e5b1  mov     [rdi+30h], r14d
0x18005e5b5  lea     rsi, [rdi+38h]
0x18005e5b9  mov     [rsi], r14
0x18005e5bc  mov     [rsi+8], r14
0x18005e5c0  mov     [rsi+10h], r14
0x18005e5c4  lea     rax, ??_7?$HandleT@USecurityDescriptorTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<SecurityDescriptorTraits>::`vftable'
0x18005e5cb  mov     [rdi+50h], rax
0x18005e5cf  mov     [rdi+58h], r14
0x18005e5d3  lea     rcx, qword_180098278; pSid
0x18005e5da  call    cs:__imp_IsValidSid
0x18005e5e1  nop     dword ptr [rax+rax+00h]
0x18005e5e6  test    eax, eax
0x18005e5e8  jz      loc_18005E74E
0x18005e5ee  lea     rcx, qword_180098278; pSid
0x18005e5f5  call    cs:__imp_GetLengthSid
0x18005e5fc  nop     dword ptr [rax+rax+00h]
0x18005e601  mov     r15d, eax
0x18005e604  mov     rdx, [rsi]
0x18005e607  mov     r14, [rsi+8]
0x18005e60b  mov     rcx, r14
0x18005e60e  sub     rcx, rdx
0x18005e611  mov     ebx, eax
0x18005e613  cmp     r15, rcx
0x18005e616  jnb     short loc_18005E622
0x18005e618  lea     rcx, [r15+rdx]
0x18005e61c  mov     [rsi+8], rcx
0x18005e620  jmp     short loc_18005E655
0x18005e622  jbe     short loc_18005E655
0x18005e624  mov     rax, [rsi+10h]
0x18005e628  sub     rax, rdx
0x18005e62b  cmp     rbx, rax
0x18005e62e  jbe     short loc_18005E63D
0x18005e630  mov     rdx, rbx
0x18005e633  mov     rcx, rsi
0x18005e636  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005e63b  jmp     short loc_18005E655
0x18005e63d  sub     rbx, rcx
0x18005e640  mov     r8, rbx; Size
0x18005e643  xor     edx, edx; Val
0x18005e645  mov     rcx, r14; void *
0x18005e648  call    memset_0
0x18005e64d  lea     rax, [rbx+r14]
0x18005e651  mov     [rsi+8], rax
0x18005e655  lea     r8, qword_180098278; pSourceSid
0x18005e65c  mov     rdx, [rsi]; pDestinationSid
0x18005e65f  mov     ecx, r15d; nDestinationSidLength
0x18005e662  call    cs:__imp_CopySid
0x18005e669  nop     dword ptr [rax+rax+00h]
0x18005e66e  test    eax, eax
0x18005e670  jz      loc_18005E7BA
0x18005e676  cmp     dword ptr [rdi+18h], 3
0x18005e67a  jnz     short loc_18005E689
0x18005e67c  mov     eax, [rdi+1Ch]
0x18005e67f  test    al, 1
0x18005e681  jz      short loc_18005E689
0x18005e683  or      eax, 10h
0x18005e686  mov     [rdi+1Ch], eax
0x18005e689  mov     rbx, [rbp+StringSecurityDescriptor]
0x18005e68d  cmp     qword ptr [rbx+10h], 0
0x18005e692  jz      short loc_18005E6C5
0x18005e694  lea     rcx, [rdi+50h]
0x18005e698  call    ?Close@?$HandleT@URpcInterfaceGroupTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcInterfaceGroupTraits>::Close(void)
0x18005e69d  cmp     qword ptr [rbx+18h], 7
0x18005e6a2  jbe     short loc_18005E6A7
0x18005e6a4  mov     rbx, [rbx]
0x18005e6a7  xor     r9d, r9d; SecurityDescriptorSize
0x18005e6aa  lea     r8, [rdi+58h]; SecurityDescriptor
0x18005e6ae  lea     edx, [r9+1]; StringSDRevision
0x18005e6b2  mov     rcx, rbx; StringSecurityDescriptor
0x18005e6b5  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005e6bc  nop     dword ptr [rax+rax+00h]
0x18005e6c1  test    eax, eax
0x18005e6c3  jz      short loc_18005E6E1
0x18005e6c5  mov     rax, rdi
0x18005e6c8  mov     rbx, [rsp+50h+arg_8]
0x18005e6d0  add     rsp, 50h
0x18005e6d4  pop     r15
0x18005e6d6  pop     r14
0x18005e6d8  pop     r13
0x18005e6da  pop     r12
0x18005e6dc  pop     rdi
0x18005e6dd  pop     rsi
0x18005e6de  pop     rbp
0x18005e6df  retn
0x18005e6e1  call    cs:__imp_GetLastError
0x18005e6e8  nop     dword ptr [rax+rax+00h]
0x18005e6ed  nop
0x18005e6ee  mov     ebx, eax
0x18005e6f0  mov     ecx, cs:dword_1800BE0B8
0x18005e6f6  cmp     ecx, 2
0x18005e6f9  jbe     short loc_18005E732
0x18005e6fb  xor     edx, edx
0x18005e6fd  lea     rcx, dword_1800BE0B8
0x18005e704  call    _tlgKeywordOn
0x18005e709  test    al, al
0x18005e70b  jz      short loc_18005E732
0x18005e70d  mov     [rbp+arg_18], ebx
0x18005e710  lea     rax, [rbp+arg_18]
0x18005e714  mov     [rsp+50h+var_30], rax
0x18005e719  xor     r9d, r9d
0x18005e71c  xor     r8d, r8d
0x18005e71f  lea     rdx, byte_1800AE99F
0x18005e726  lea     rcx, dword_1800BE0B8
0x18005e72d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005e732  mov     edx, ebx; unsigned int
0x18005e734  lea     rcx, [rbp+pExceptionObject]; this
0x18005e738  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18005e73d  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18005e744  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005e748  call    _CxxThrowException_0
0x18005e74e  call    cs:__imp_GetLastError
0x18005e755  nop     dword ptr [rax+rax+00h]
0x18005e75a  mov     ebx, eax
0x18005e75c  mov     ecx, cs:dword_1800BE0B8
0x18005e762  cmp     ecx, 2
0x18005e765  jbe     short loc_18005E79E
0x18005e767  xor     edx, edx
0x18005e769  lea     rcx, dword_1800BE0B8
0x18005e770  call    _tlgKeywordOn
0x18005e775  test    al, al
0x18005e777  jz      short loc_18005E79E
0x18005e779  mov     [rbp+arg_18], ebx
0x18005e77c  lea     rax, [rbp+arg_18]
0x18005e780  mov     [rsp+50h+var_30], rax
0x18005e785  xor     r9d, r9d
0x18005e788  xor     r8d, r8d
0x18005e78b  lea     rdx, dword_1800AEA04
0x18005e792  lea     rcx, dword_1800BE0B8
0x18005e799  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005e79e  mov     edx, ebx; unsigned int
0x18005e7a0  lea     rcx, [rbp+pExceptionObject]; this
0x18005e7a4  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18005e7a9  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18005e7b0  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005e7b4  call    _CxxThrowException_0
0x18005e7ba  call    cs:__imp_GetLastError
0x18005e7c1  nop     dword ptr [rax+rax+00h]
0x18005e7c6  mov     ebx, eax
0x18005e7c8  mov     ecx, cs:dword_1800BE0B8
0x18005e7ce  cmp     ecx, 2
0x18005e7d1  jbe     short loc_18005E80A
0x18005e7d3  xor     edx, edx
0x18005e7d5  lea     rcx, dword_1800BE0B8
0x18005e7dc  call    _tlgKeywordOn
0x18005e7e1  test    al, al
0x18005e7e3  jz      short loc_18005E80A
0x18005e7e5  mov     [rbp+arg_18], ebx
0x18005e7e8  lea     rax, [rbp+arg_18]
0x18005e7ec  mov     [rsp+50h+var_30], rax
0x18005e7f1  xor     r9d, r9d
0x18005e7f4  xor     r8d, r8d
0x18005e7f7  lea     rdx, byte_1800AEA35
0x18005e7fe  lea     rcx, dword_1800BE0B8
0x18005e805  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005e80a  mov     edx, ebx; unsigned int
0x18005e80c  lea     rcx, [rbp+pExceptionObject]; this
0x18005e810  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18005e815  lea     rdx, _TI3?AVwin32_exception@@; pThrowInfo
0x18005e81c  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18005e820  call    _CxxThrowException_0
```
