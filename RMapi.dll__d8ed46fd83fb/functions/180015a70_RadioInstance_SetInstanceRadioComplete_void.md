# RadioInstance::SetInstanceRadioComplete(void)

- ea: `0x180015a70`
- end: `0x180015b79`
- name: `?SetInstanceRadioComplete@RadioInstance@@UEAAJXZ`
- size: `265`
- prototype: `__int64 __fastcall(RadioInstance *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180001670`
- `0x18000b814`
- `0x18000c2a4`
- `0x180015a70`
- `0x180016940`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a8b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180015a8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RadioInstance::SetInstanceRadioComplete(const struct _GUID *this)
{
  unsigned __int8 *Data4; // rbx
  unsigned int v3; // ebx
  __int64 v4; // r11
  int v5; // ecx
  __int64 v6; // rcx
  unsigned __int8 v8; // [rsp+20h] [rbp-29h]
  unsigned __int8 v9; // [rsp+28h] [rbp-21h]
  char *v10; // [rsp+70h] [rbp+27h] BYREF

  Data4 = this[1].Data4;
  EnterCriticalSection((LPCRITICAL_SECTION)this[1].Data4);
  v10 = (char *)Data4;
  --*(_DWORD *)&this[4].Data4[4];
  RadioInstance::_UpdateUIEnabled((RadioInstance *)&this[-1]);
  v3 = -2147019873;
  v4 = *(_QWORD *)&this[4].Data1;
  if ( v4 )
  {
    if ( this[5].Data4[2] )
      v5 = 2;
    else
      v5 = *(_DWORD *)&this[4].Data4[4] != 0;
    v9 = this[5].Data4[1];
    v8 = this[5].Data4[0];
    v3 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, unsigned __int8, unsigned __int8, int))(*(_QWORD *)v4 + 32LL))(
           v4,
           2,
           0,
           *(_QWORD *)&this[6].Data1,
           v8,
           v9,
           v5);
  }
  if ( (unsigned int)dword_180037050 > 4 )
  {
    RmGuidToMediaTypeString(this + 7);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v6,
      byte_18002E003);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
  return v3;
}

```

## disassembly

```asm
0x180015a70  push    rbp
0x180015a72  push    rbx
0x180015a73  push    rsi
0x180015a74  push    rdi
0x180015a75  lea     rbp, [rsp-3Fh]
0x180015a7a  sub     rsp, 88h
0x180015a81  mov     rdi, rcx
0x180015a84  lea     rbx, [rcx+18h]
0x180015a88  mov     rcx, rbx; lpCriticalSection
0x180015a8b  call    cs:__imp_EnterCriticalSection
0x180015a91  mov     [rbp+57h+var_30], rbx
0x180015a95  lea     rcx, [rdi-10h]; this
0x180015a99  mov     eax, [rcx+5Ch]
0x180015a9c  mov     esi, 1
0x180015aa1  sub     eax, esi
0x180015aa3  mov     [rdi+4Ch], eax
0x180015aa6  call    ?_UpdateUIEnabled@RadioInstance@@AEAAXXZ; RadioInstance::_UpdateUIEnabled(void)
0x180015aab  mov     ebx, 8007139Fh
0x180015ab0  mov     r11, [rdi+40h]
0x180015ab4  test    r11, r11
0x180015ab7  jz      short loc_180015AFB
0x180015ab9  lea     edx, [rsi+1]
0x180015abc  cmp     byte ptr [rdi+5Ah], 0
0x180015ac0  jz      short loc_180015AC6
0x180015ac2  mov     ecx, edx
0x180015ac4  jmp     short loc_180015ACE
0x180015ac6  xor     ecx, ecx
0x180015ac8  cmp     [rdi+4Ch], ecx
0x180015acb  cmova   ecx, esi
0x180015ace  mov     rax, [r11]
0x180015ad1  mov     r10, [rax+20h]
0x180015ad5  mov     dword ptr [rsp+0A0h+var_70], ecx
0x180015ad9  mov     al, [rdi+59h]
0x180015adc  mov     byte ptr [rsp+0A0h+var_78], al
0x180015ae0  mov     al, [rdi+58h]
0x180015ae3  mov     byte ptr [rsp+0A0h+var_80], al
0x180015ae7  mov     r9, [rdi+60h]
0x180015aeb  xor     r8d, r8d
0x180015aee  mov     rcx, r11
0x180015af1  mov     rax, r10
0x180015af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015af9  mov     ebx, eax
0x180015afb  mov     ecx, cs:dword_180037050
0x180015b01  cmp     ecx, 4
0x180015b04  jbe     short loc_180015B62
0x180015b06  mov     [rbp+57h+var_50], ebx
0x180015b09  mov     ecx, [rdi+4Ch]
0x180015b0c  mov     [rbp+57h+var_4C], ecx
0x180015b0f  mov     rcx, [rdi+68h]
0x180015b13  mov     [rbp+57h+var_48], rcx
0x180015b17  lea     rcx, [rdi+70h]; struct _GUID *
0x180015b1b  call    ?RmGuidToMediaTypeString@@YAPEBDAEBU_GUID@@@Z; RmGuidToMediaTypeString(_GUID const &)
0x180015b20  mov     [rbp+57h+var_40], rax
0x180015b24  mov     [rbp+57h+var_38], rcx
0x180015b28  lea     rax, [rbp+57h+var_50]
0x180015b2c  mov     [rsp+0A0h+var_60], rax
0x180015b31  lea     rax, [rbp+57h+var_4C]
0x180015b35  mov     [rsp+0A0h+var_68], rax
0x180015b3a  lea     rax, [rbp+57h+var_48]
0x180015b3e  mov     [rsp+0A0h+var_70], rax
0x180015b43  lea     rax, [rbp+57h+var_40]
0x180015b47  mov     [rsp+0A0h+var_78], rax
0x180015b4c  lea     rax, [rbp+57h+var_38]
0x180015b50  mov     [rsp+0A0h+var_80], rax
0x180015b55  lea     rdx, byte_18002E003
0x180015b5c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@D@@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180015b61  nop
0x180015b62  lea     rcx, [rbp+57h+var_30]
0x180015b66  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180015b6b  mov     eax, ebx
0x180015b6d  add     rsp, 88h
0x180015b74  pop     rdi
0x180015b75  pop     rsi
0x180015b76  pop     rbx
0x180015b77  pop     rbp
0x180015b78  retn
```
