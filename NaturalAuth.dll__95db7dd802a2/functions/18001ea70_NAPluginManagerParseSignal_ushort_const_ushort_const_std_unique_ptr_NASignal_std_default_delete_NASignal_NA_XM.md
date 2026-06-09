# NAPluginManagerParseSignal(ushort const *,ushort const *,std::unique_ptr<NASignal,std::default_delete<NASignal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x18001ea70`
- end: `0x18001ec90`
- name: `?NAPluginManagerParseSignal@@YAJPEBG0PEAV?$unique_ptr@VNASignal@@U?$default_delete@VNASignal@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `544`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, __int64 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180020204`

## callees

- `0x1800011c0`
- `0x1800014f0`
- `0x180004170`
- `0x18000459c`
- `0x180009a74`
- `0x18000b7b8`
- `0x18000c9e0`
- `0x18000cab8`
- `0x180011c8c`
- `0x18001aa2c`
- `0x18001d9f8`
- `0x18001da80`
- `0x18001dba0`
- `0x18001ea70`
- `0x1800219a0`
- `0x180046010`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x18001eac9`
- `ntdll!RtlAcquireSRWLockShared` at `0x18001eac9`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ec6a`
- `ntdll!RtlReleaseSRWLockShared` at `0x18001ec6a`

## pseudocode

```c
__int64 __fastcall NAPluginManagerParseSignal(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 *a3,
        unsigned __int16 *a4)
{
  __int64 v8; // rdx
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  char v12; // al
  __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 CorrelationVector; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  int v21; // [rsp+60h] [rbp-69h] BYREF
  int v22; // [rsp+64h] [rbp-65h] BYREF
  unsigned int v23; // [rsp+68h] [rbp-61h] BYREF
  void *v24; // [rsp+70h] [rbp-59h] BYREF
  void *v25; // [rsp+78h] [rbp-51h] BYREF
  __int64 v26; // [rsp+80h] [rbp-49h] BYREF
  int *v27; // [rsp+88h] [rbp-41h] BYREF
  int *v28; // [rsp+90h] [rbp-39h] BYREF
  __int64 v29; // [rsp+98h] [rbp-31h] BYREF
  char v30[16]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v31; // [rsp+B0h] [rbp-19h]
  _BYTE v32[40]; // [rsp+B8h] [rbp-11h] BYREF

  v24 = 0;
  v8 = *a3;
  *a3 = 0;
  if ( v8 )
    std::default_delete<NASignal>::operator()();
  v9 = -2147023834;
  RtlAcquireSRWLockShared(&stru_18005FAE0);
  if ( byte_18005FC59 )
  {
    std::wstring::wstring(v32, a1);
    std::_Tree<std::_Tmap_traits<std::wstring,PluginSignalInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginSignalInfo>>,0>>::_Find_lower_bound<std::wstring>(
      v10,
      v30,
      v32);
    v12 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
            v11,
            v31,
            v32);
    v13 = qword_18005F9A8;
    if ( v12 )
      v13 = v31;
    std::wstring::_Tidy_deallocate(v32);
    if ( v13 == qword_18005F9A8 )
    {
      v9 = -2147023431;
      StringCchCopyW(a4 + 4, 0x100u, a2);
    }
    else
    {
      v9 = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 *, void **, unsigned __int16 *))(*(_QWORD *)(v13 + 72) + 24LL))(
             *(_QWORD *)(v13 + 64),
             a2,
             &v24,
             a4);
      if ( !v9 )
      {
        v25 = operator new(0x30u);
        v14 = PluginSignal::PluginSignal(v25, v24, *(_QWORD *)(v13 + 64), *(_QWORD *)(v13 + 72), *(_DWORD *)(v13 + 80));
        v15 = *a3;
        *a3 = v14;
        if ( v15 )
          std::default_delete<NASignal>::operator()();
      }
    }
  }
  if ( (unsigned int)dword_18005C570 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18005C570, 0x400000000000LL) )
  {
    CorrelationVector = NaturalAuthTraceLogging::GetCorrelationVector(v32);
    v26 = std::_String_val<std::_Simple_types<char>>::_Myptr(CorrelationVector);
    v27 = (int *)(a4 + 260);
    v28 = (int *)(a4 + 4);
    v21 = *((_DWORD *)a4 + 1);
    v22 = *(_DWORD *)a4;
    v29 = a1;
    v25 = v24;
    v23 = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<char>>(
      v17,
      (unsigned int)byte_18004FB13,
      v18,
      v19,
      (__int64)&v23,
      (__int64)&v25,
      (__int64)&v29,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v26);
    std::string::_Tidy_deallocate(v32);
  }
  RtlReleaseSRWLockShared(&stru_18005FAE0);
  return v9;
}

```

## disassembly

```asm
0x18001ea70  push    rbp
0x18001ea72  push    rbx
0x18001ea73  push    rsi
0x18001ea74  push    rdi
0x18001ea75  push    r12
0x18001ea77  push    r14
0x18001ea79  push    r15
0x18001ea7b  lea     rbp, [rsp-27h]
0x18001ea80  sub     rsp, 0F0h
0x18001ea87  mov     rax, cs:__security_cookie
0x18001ea8e  xor     rax, rsp
0x18001ea91  mov     [rbp+57h+var_40], rax
0x18001ea95  mov     r14, r9
0x18001ea98  mov     rsi, r8
0x18001ea9b  mov     r15, rdx
0x18001ea9e  mov     r12, rcx
0x18001eaa1  mov     [rbp+57h+var_B0], 0
0x18001eaa9  mov     rdx, [r8]
0x18001eaac  mov     qword ptr [r8], 0
0x18001eab3  test    rdx, rdx
0x18001eab6  jz      short loc_18001EABD
0x18001eab8  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18001eabd  mov     ebx, 80070426h
0x18001eac2  lea     rcx, stru_18005FAE0
0x18001eac9  call    cs:__imp_RtlAcquireSRWLockShared
0x18001eacf  nop
0x18001ead0  cmp     cs:byte_18005FC59, 0
0x18001ead7  jz      loc_18001EB94
0x18001eadd  mov     rdx, r12
0x18001eae0  lea     rcx, [rbp+57h+var_68]
0x18001eae4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001eae9  lea     r8, [rbp+57h+var_68]
0x18001eaed  lea     rdx, [rbp+57h+var_80]
0x18001eaf1  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PluginSignalInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginSignalInfo>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001eaf6  lea     r8, [rbp+57h+var_68]
0x18001eafa  mov     rdx, [rbp+57h+var_70]
0x18001eafe  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x18001eb03  mov     rdi, cs:qword_18005F9A8
0x18001eb0a  test    al, al
0x18001eb0c  cmovnz  rdi, [rbp+57h+var_70]
0x18001eb11  lea     rcx, [rbp+57h+var_68]
0x18001eb15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001eb1a  cmp     rdi, cs:qword_18005F9A8
0x18001eb21  jnz     short loc_18001EB3B
0x18001eb23  mov     ebx, 800705B9h
0x18001eb28  lea     rcx, [r14+8]; unsigned __int16 *
0x18001eb2c  mov     r8, r15; unsigned __int16 *
0x18001eb2f  mov     edx, 100h; unsigned __int64
0x18001eb34  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001eb39  jmp     short loc_18001EB94
0x18001eb3b  mov     rax, [rdi+48h]
0x18001eb3f  mov     r9, r14
0x18001eb42  lea     r8, [rbp+57h+var_B0]
0x18001eb46  mov     rdx, r15
0x18001eb49  mov     rcx, [rdi+40h]
0x18001eb4d  mov     rax, [rax+18h]
0x18001eb51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb56  mov     ebx, eax
0x18001eb58  test    eax, eax
0x18001eb5a  jnz     short loc_18001EB94
0x18001eb5c  lea     ecx, [rax+30h]; Size
0x18001eb5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001eb64  mov     [rbp+57h+var_A8], rax
0x18001eb68  mov     ecx, [rdi+50h]
0x18001eb6b  mov     dword ptr [rsp+120h+var_100], ecx
0x18001eb6f  mov     r9, [rdi+48h]
0x18001eb73  mov     r8, [rdi+40h]
0x18001eb77  mov     rdx, [rbp+57h+var_B0]
0x18001eb7b  mov     rcx, rax
0x18001eb7e  call    ??0PluginSignal@@QEAA@_JPEAU_PluginContext@@PEAUNA_PLUGIN_FUNCTION_TABLE@@W4NA_SIGNAL_TYPE_INFO@@@Z; PluginSignal::PluginSignal(__int64,_PluginContext *,NA_PLUGIN_FUNCTION_TABLE *,NA_SIGNAL_TYPE_INFO)
0x18001eb83  nop
0x18001eb84  mov     rdx, [rsi]
0x18001eb87  mov     [rsi], rax
0x18001eb8a  test    rdx, rdx
0x18001eb8d  jz      short loc_18001EB94
0x18001eb8f  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18001eb94  mov     eax, cs:dword_18005C570
0x18001eb9a  cmp     eax, 5
0x18001eb9d  jbe     loc_18001EC63
0x18001eba3  mov     rdx, 400000000000h
0x18001ebad  lea     rcx, dword_18005C570
0x18001ebb4  call    _tlgKeywordOn
0x18001ebb9  test    al, al
0x18001ebbb  jz      loc_18001EC63
0x18001ebc1  lea     rcx, [rbp+57h+var_68]
0x18001ebc5  call    ?GetCorrelationVector@NaturalAuthTraceLogging@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; NaturalAuthTraceLogging::GetCorrelationVector(void)
0x18001ebca  mov     rcx, rax
0x18001ebcd  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18001ebd2  mov     [rbp+57h+var_A0], rax
0x18001ebd6  lea     rax, [r14+208h]
0x18001ebdd  mov     [rbp+57h+var_98], rax
0x18001ebe1  lea     rax, [r14+8]
0x18001ebe5  mov     [rbp+57h+var_90], rax
0x18001ebe9  mov     eax, [r14+4]
0x18001ebed  mov     [rbp+57h+var_C0], eax
0x18001ebf0  mov     eax, [r14]
0x18001ebf3  mov     [rbp+57h+var_BC], eax
0x18001ebf6  mov     [rbp+57h+var_88], r12
0x18001ebfa  mov     rax, [rbp+57h+var_B0]
0x18001ebfe  mov     [rbp+57h+var_A8], rax
0x18001ec02  mov     [rbp+57h+var_B8], ebx
0x18001ec05  lea     rax, [rbp+57h+var_A0]
0x18001ec09  mov     [rsp+120h+var_C8], rax
0x18001ec0e  lea     rax, [rbp+57h+var_98]
0x18001ec12  mov     [rsp+120h+var_D0], rax
0x18001ec17  lea     rax, [rbp+57h+var_90]
0x18001ec1b  mov     [rsp+120h+var_D8], rax
0x18001ec20  lea     rax, [rbp+57h+var_C0]
0x18001ec24  mov     [rsp+120h+var_E0], rax
0x18001ec29  lea     rax, [rbp+57h+var_BC]
0x18001ec2d  mov     [rsp+120h+var_E8], rax
0x18001ec32  lea     rax, [rbp+57h+var_88]
0x18001ec36  mov     [rsp+120h+var_F0], rax
0x18001ec3b  lea     rax, [rbp+57h+var_A8]
0x18001ec3f  mov     [rsp+120h+var_F8], rax
0x18001ec44  lea     rax, [rbp+57h+var_B8]
0x18001ec48  mov     [rsp+120h+var_100], rax
0x18001ec4d  lea     rdx, byte_18004FB13
0x18001ec54  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U1@U1@U3@U3@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@3355AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &)
0x18001ec59  lea     rcx, [rbp+57h+var_68]
0x18001ec5d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18001ec62  nop
0x18001ec63  lea     rcx, stru_18005FAE0
0x18001ec6a  call    cs:__imp_RtlReleaseSRWLockShared
0x18001ec70  mov     eax, ebx
0x18001ec72  mov     rcx, [rbp+57h+var_40]
0x18001ec76  xor     rcx, rsp; StackCookie
0x18001ec79  call    __security_check_cookie
0x18001ec7e  add     rsp, 0F0h
0x18001ec85  pop     r15
0x18001ec87  pop     r14
0x18001ec89  pop     r12
0x18001ec8b  pop     rdi
0x18001ec8c  pop     rsi
0x18001ec8d  pop     rbx
0x18001ec8e  pop     rbp
0x18001ec8f  retn
```
