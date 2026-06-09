# CMidi2KSAggregateMidiBidi::Shutdown(void)

- ea: `0x18001b050`
- end: `0x18001b157`
- name: `?Shutdown@CMidi2KSAggregateMidiBidi@@UEAAJXZ`
- size: `263`
- prototype: `__int64 __fastcall(CMidi2KSAggregateMidiBidi *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001f48`
- `0x180005044`
- `0x1800117d8`
- `0x180012304`
- `0x180012380`
- `0x180018e30`
- `0x18001b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b13b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b13b`

## pseudocode

```c
__int64 __fastcall CMidi2KSAggregateMidiBidi::Shutdown(CMidi2KSAggregateMidiBidi *this)
{
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  _QWORD *v5; // rax
  CMidi2KSAggregateMidi *v6; // rcx
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  const char *v9; // [rsp+50h] [rbp-28h] BYREF
  __int64 v10; // [rsp+80h] [rbp+8h] BYREF
  _QWORD *v11; // [rsp+88h] [rbp+10h] BYREF
  const wchar_t *v12; // [rsp+90h] [rbp+18h] BYREF
  CMidi2KSAggregateMidiBidi *v13; // [rsp+98h] [rbp+20h] BYREF

  v2 = (_DWORD *)*((_QWORD *)MidiKSAggregateTransportTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v10 = *((_QWORD *)this + 6);
    v5 = (_QWORD *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) > 7u )
      v5 = (_QWORD *)*v5;
    v11 = v5;
    v13 = this;
    v12 = L"Cleaning up";
    v9 = "CMidi2KSAggregateMidiBidi::Shutdown";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (_DWORD)v2,
      (unsigned int)byte_180088D8B,
      v3,
      v4,
      (__int64)&v9,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11,
      (__int64)&v10);
  }
  v6 = (CMidi2KSAggregateMidi *)*((_QWORD *)this + 7);
  if ( v6 )
  {
    CMidi2KSAggregateMidi::Shutdown(v6);
    v7 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = 0;
    if ( v7 )
    {
      std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(&v7[2]);
      std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v7[1].LockSemaphore);
      std::_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<unsigned char,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<unsigned char>,std::allocator<std::pair<unsigned char const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(&v7[1].LockCount);
      DeleteCriticalSection(v7);
      operator delete(v7);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001b050  push    rbx
0x18001b052  push    rdi
0x18001b053  sub     rsp, 68h
0x18001b057  mov     rbx, rcx
0x18001b05a  call    ?Instance@MidiKSAggregateTransportTelemetryProvider@@KAPEAV1@XZ; MidiKSAggregateTransportTelemetryProvider::Instance(void)
0x18001b05f  mov     rcx, [rax+8]
0x18001b063  mov     eax, [rcx]
0x18001b065  cmp     eax, 4
0x18001b068  jbe     loc_18001B0FE
0x18001b06e  mov     rax, [rbx+30h]
0x18001b072  nop
0x18001b073  mov     [rsp+78h+arg_0], rax
0x18001b07b  lea     rax, [rbx+10h]
0x18001b07f  cmp     qword ptr [rax+18h], 7
0x18001b084  jbe     short loc_18001B089
0x18001b086  mov     rax, [rax]
0x18001b089  mov     [rsp+78h+arg_8], rax
0x18001b091  lea     rdx, byte_180088D8B
0x18001b098  lea     rax, aCleaningUp; "Cleaning up"
0x18001b09f  mov     [rsp+78h+arg_18], rbx
0x18001b0a7  mov     [rsp+78h+arg_10], rax
0x18001b0af  lea     rax, aCmidi2ksaggreg_7; "CMidi2KSAggregateMidiBidi::Shutdown"
0x18001b0b6  mov     [rsp+78h+var_28], rax
0x18001b0bb  lea     rax, [rsp+78h+arg_0]
0x18001b0c3  mov     [rsp+78h+var_38], rax
0x18001b0c8  lea     rax, [rsp+78h+arg_8]
0x18001b0d0  mov     [rsp+78h+var_40], rax
0x18001b0d5  lea     rax, [rsp+78h+arg_10]
0x18001b0dd  mov     [rsp+78h+var_48], rax
0x18001b0e2  lea     rax, [rsp+78h+arg_18]
0x18001b0ea  mov     [rsp+78h+var_50], rax
0x18001b0ef  lea     rax, [rsp+78h+var_28]
0x18001b0f4  mov     [rsp+78h+var_58], rax
0x18001b0f9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x18001b0fe  mov     rcx, [rbx+38h]; this
0x18001b102  test    rcx, rcx
0x18001b105  jz      short loc_18001B14E
0x18001b107  call    ?Shutdown@CMidi2KSAggregateMidi@@QEAAJXZ; CMidi2KSAggregateMidi::Shutdown(void)
0x18001b10c  mov     rdi, [rbx+38h]
0x18001b110  mov     qword ptr [rbx+38h], 0
0x18001b118  test    rdi, rdi
0x18001b11b  jz      short loc_18001B14E
0x18001b11d  lea     rcx, [rdi+50h]
0x18001b121  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::unique_ptr<KsHandleWrapper>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::unique_ptr<KsHandleWrapper>>>,0>>(void)
0x18001b126  lea     rcx, [rdi+40h]
0x18001b12a  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001b12f  lea     rcx, [rdi+30h]
0x18001b133  call    ??1?$_Tree@V?$_Tmap_traits@EV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@U?$less@E@std@@V?$allocator@U?$pair@$$CBEV?$com_ptr_t@VCMidi2KSAggregateMidiInProxy@@Uerr_returncode_policy@wil@@@wil@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>::~_Tree<std::_Tmap_traits<uchar,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>,std::less<uchar>,std::allocator<std::pair<uchar const,wil::com_ptr_t<CMidi2KSAggregateMidiInProxy,wil::err_returncode_policy>>>,0>>(void)
0x18001b138  mov     rcx, rdi; lpCriticalSection
0x18001b13b  call    cs:__imp_DeleteCriticalSection
0x18001b141  mov     edx, 60h ; '`'
0x18001b146  mov     rcx, rdi; Block
0x18001b149  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b14e  xor     eax, eax
0x18001b150  add     rsp, 68h
0x18001b154  pop     rdi
0x18001b155  pop     rbx
0x18001b156  retn
```
