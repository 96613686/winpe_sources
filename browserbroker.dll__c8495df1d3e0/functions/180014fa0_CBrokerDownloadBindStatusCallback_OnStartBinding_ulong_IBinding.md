# CBrokerDownloadBindStatusCallback::OnStartBinding(ulong,IBinding *)

- ea: `0x180014fa0`
- end: `0x180015061`
- name: `?OnStartBinding@CBrokerDownloadBindStatusCallback@@UEAAJKPEAUIBinding@@@Z`
- size: `193`
- prototype: `__int64 __fastcall(CBrokerDownloadBindStatusCallback *__hidden this, unsigned int, struct IBinding *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001358`
- `0x1800019a8`
- `0x180014bb0`
- `0x180014fa0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180015002`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180015002`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014ff2`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014ff2`

## pseudocode

```c
__int64 __fastcall CBrokerDownloadBindStatusCallback::OnStartBinding(
        CBrokerDownloadBindStatusCallback *this,
        __int64 a2,
        struct IBinding *a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  char *v10; // [rsp+50h] [rbp-28h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v11; // [rsp+58h] [rbp-20h] BYREF
  __int64 v12[3]; // [rsp+60h] [rbp-18h] BYREF
  char v13; // [rsp+80h] [rbp+8h] BYREF
  struct IBinding *v14; // [rsp+98h] [rbp+20h] BYREF

  ATL::CComPtr<IBinding>::operator=((_QWORD *)this + 1, (__int64)a3);
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x10000000) )
  {
    v14 = a3;
    v10 = (char *)this - 16;
    v13 = 1;
    v11 = GlobalThreadState();
    v12[0] = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
      v6,
      (__int64)word_180035702,
      v7,
      v8,
      v12,
      (__int64 *)&v11,
      (__int64)&v13,
      (__int64)&v10,
      (__int64)&v14);
  }
  return 0;
}

```

## disassembly

```asm
0x180014fa0  mov     [rsp+arg_8], rbx
0x180014fa5  push    rdi
0x180014fa6  sub     rsp, 70h
0x180014faa  mov     rdi, rcx
0x180014fad  mov     rdx, r8
0x180014fb0  add     rcx, 8
0x180014fb4  mov     rbx, r8
0x180014fb7  call    ??4?$CComPtr@UIBinding@@@ATL@@QEAAPEAUIBinding@@PEAU2@@Z; ATL::CComPtr<IBinding>::operator=(IBinding *)
0x180014fbc  mov     eax, cs:dword_18003F000
0x180014fc2  cmp     eax, 5
0x180014fc5  jbe     loc_180015051
0x180014fcb  mov     edx, 10000000h
0x180014fd0  call    _tlgKeywordOn
0x180014fd5  test    al, al
0x180014fd7  jz      short loc_180015051
0x180014fd9  lea     rax, [rdi-10h]
0x180014fdd  mov     [rsp+78h+arg_18], rbx
0x180014fe5  mov     [rsp+78h+var_28], rax
0x180014fea  mov     [rsp+78h+arg_0], 1
0x180014ff2  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180014ff8  mov     ecx, 10000003h
0x180014ffd  mov     [rsp+78h+var_20], rax
0x180015002  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180015008  mov     [rsp+78h+var_18], rax
0x18001500d  lea     rdx, word_180035702
0x180015014  lea     rax, [rsp+78h+arg_18]
0x18001501c  mov     [rsp+78h+var_38], rax
0x180015021  lea     rax, [rsp+78h+var_28]
0x180015026  mov     [rsp+78h+var_40], rax
0x18001502b  lea     rax, [rsp+78h+arg_0]
0x180015033  mov     [rsp+78h+var_48], rax
0x180015038  lea     rax, [rsp+78h+var_20]
0x18001503d  mov     [rsp+78h+var_50], rax
0x180015042  lea     rax, [rsp+78h+var_18]
0x180015047  mov     [rsp+78h+var_58], rax
0x18001504c  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180015051  mov     rbx, [rsp+78h+arg_8]
0x180015059  xor     eax, eax
0x18001505b  add     rsp, 70h
0x18001505f  pop     rdi
0x180015060  retn
```
