# RadioInstance::OnSystemRadioStateChangeCompleted(void)

- ea: `0x180013ea0`
- end: `0x180013fca`
- name: `?OnSystemRadioStateChangeCompleted@RadioInstance@@UEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(RadioInstance *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001770`
- `0x18000b814`
- `0x18000c2a4`
- `0x180013ea0`
- `0x180016940`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ec2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013ec2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RadioInstance::OnSystemRadioStateChangeCompleted(const struct _GUID *this)
{
  unsigned __int8 *Data4; // rbx
  unsigned int Data1; // eax
  unsigned int v4; // r14d
  __int64 v5; // rcx
  __int64 v6; // rcx
  unsigned __int8 v8; // [rsp+20h] [rbp-60h]
  unsigned __int8 v9; // [rsp+28h] [rbp-58h]
  char *v10; // [rsp+78h] [rbp-8h] BYREF

  Data4 = this[1].Data4;
  EnterCriticalSection((LPCRITICAL_SECTION)this[1].Data4);
  v10 = (char *)Data4;
  Data1 = this[5].Data1;
  if ( Data1 )
  {
    this[5].Data1 = Data1 - 1;
    --*(_DWORD *)&this[4].Data4[4];
  }
  RadioInstance::_UpdateUIEnabled((RadioInstance *)&this[-1]);
  v4 = -2147019873;
  v5 = *(_QWORD *)&this[4].Data1;
  if ( v5 )
  {
    v9 = this[5].Data4[1];
    v8 = this[5].Data4[0];
    v4 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned __int8, unsigned __int8, int))(*(_QWORD *)v5 + 32LL))(
           v5,
           2,
           0,
           *(_QWORD *)&this[6].Data1,
           v8,
           v9,
           this[5].Data4[2] != 0 ? 2 : 0);
  }
  if ( (unsigned int)dword_180037050 > 4 )
  {
    RmGuidToMediaTypeString(this + 7);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      &byte_18002E2DF);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  return v4;
}

```

## disassembly

```asm
0x180013ea0  mov     [rsp-18h+arg_8], rbx
0x180013ea5  mov     [rsp-18h+arg_10], rsi
0x180013eaa  push    rbp
0x180013eab  push    rdi
0x180013eac  push    r14
0x180013eae  mov     rbp, rsp
0x180013eb1  sub     rsp, 80h
0x180013eb8  mov     rdi, rcx
0x180013ebb  lea     rbx, [rcx+18h]
0x180013ebf  mov     rcx, rbx; lpCriticalSection
0x180013ec2  call    cs:__imp_EnterCriticalSection
0x180013ec8  mov     [rbp+var_8], rbx
0x180013ecc  lea     rcx, [rdi-10h]; this
0x180013ed0  mov     eax, [rcx+60h]
0x180013ed3  test    eax, eax
0x180013ed5  jz      short loc_180013EDF
0x180013ed7  dec     eax
0x180013ed9  mov     [rdi+50h], eax
0x180013edc  dec     dword ptr [rdi+4Ch]
0x180013edf  call    ?_UpdateUIEnabled@RadioInstance@@AEAAXXZ; RadioInstance::_UpdateUIEnabled(void)
0x180013ee4  mov     r14d, 8007139Fh
0x180013eea  mov     rcx, [rdi+40h]
0x180013eee  test    rcx, rcx
0x180013ef1  jz      short loc_180013F2F
0x180013ef3  mov     r9, [rcx]
0x180013ef6  mov     al, [rdi+5Ah]
0x180013ef9  neg     al
0x180013efb  sbb     r8d, r8d
0x180013efe  mov     edx, 2
0x180013f03  and     r8d, edx
0x180013f06  mov     r10, [r9+20h]
0x180013f0a  mov     dword ptr [rsp+80h+var_50], r8d
0x180013f0f  mov     al, [rdi+59h]
0x180013f12  mov     byte ptr [rsp+80h+var_58], al
0x180013f16  mov     al, [rdi+58h]
0x180013f19  mov     byte ptr [rsp+80h+var_60], al
0x180013f1d  mov     r9, [rdi+60h]
0x180013f21  xor     r8d, r8d
0x180013f24  mov     rax, r10
0x180013f27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f2c  mov     r14d, eax
0x180013f2f  mov     ecx, cs:dword_180037050
0x180013f35  cmp     ecx, 4
0x180013f38  jbe     short loc_180013FA6
0x180013f3a  mov     [rbp+var_30], r14d
0x180013f3e  mov     ecx, [rdi+50h]
0x180013f41  mov     [rbp+var_2C], ecx
0x180013f44  mov     ecx, [rdi+4Ch]
0x180013f47  mov     [rbp+var_28], ecx
0x180013f4a  mov     rcx, [rdi+68h]
0x180013f4e  mov     [rbp+var_20], rcx
0x180013f52  lea     rcx, [rdi+70h]; struct _GUID *
0x180013f56  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180013f5b  mov     [rbp+var_18], rax
0x180013f5f  mov     [rbp+var_10], rcx
0x180013f63  lea     rax, [rbp+var_30]
0x180013f67  mov     [rsp+80h+var_38], rax
0x180013f6c  lea     rax, [rbp+var_2C]
0x180013f70  mov     [rsp+80h+var_40], rax
0x180013f75  lea     rax, [rbp+var_28]
0x180013f79  mov     [rsp+80h+var_48], rax
0x180013f7e  lea     rax, [rbp+var_20]
0x180013f82  mov     [rsp+80h+var_50], rax
0x180013f87  lea     rax, [rbp+var_18]
0x180013f8b  mov     [rsp+80h+var_58], rax
0x180013f90  lea     rax, [rbp+var_10]
0x180013f94  mov     [rsp+80h+var_60], rax
0x180013f99  lea     rdx, byte_18002E2DF
0x180013fa0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@66@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180013fa5  nop
0x180013fa6  lea     rcx, [rbp+var_8]
0x180013faa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180013faf  mov     eax, r14d
0x180013fb2  lea     r11, [rsp+80h+var_s0]
0x180013fba  mov     rbx, [r11+28h]
0x180013fbe  mov     rsi, [r11+30h]
0x180013fc2  mov     rsp, r11
0x180013fc5  pop     r14
0x180013fc7  pop     rdi
0x180013fc8  pop     rbp
0x180013fc9  retn
```
