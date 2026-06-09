# CBrokerDownloadBindStatusCallback::OnStopBinding(long,ushort const *)

- ea: `0x180015070`
- end: `0x180015139`
- name: `?OnStopBinding@CBrokerDownloadBindStatusCallback@@UEAAJJPEBG@Z`
- size: `201`
- prototype: `__int64 __fastcall(CBrokerDownloadBindStatusCallback *__hidden this, int, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180001358`
- `0x180001b78`
- `0x180014bb0`
- `0x180015070`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800150db`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x1800150db`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800150cc`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1800150cc`

## pseudocode

```c
__int64 __fastcall CBrokerDownloadBindStatusCallback::OnStopBinding(
        CBrokerDownloadBindStatusCallback *this,
        int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  char *v11; // [rsp+50h] [rbp-20h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v12; // [rsp+58h] [rbp-18h] BYREF
  __int64 CLSID; // [rsp+60h] [rbp-10h] BYREF
  char v14; // [rsp+90h] [rbp+20h] BYREF
  int v15; // [rsp+A0h] [rbp+30h] BYREF
  const WCHAR *v16; // [rsp+A8h] [rbp+38h] BYREF

  ATL::CComPtr<IBinding>::operator=((_QWORD *)this + 1, 0);
  if ( !a3 )
    a3 = L"(null)";
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(v6, 0x10000000) )
  {
    v16 = a3;
    v11 = (char *)this - 16;
    v15 = a2;
    v14 = 1;
    v12 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (__int64)word_1800355CA,
      v8,
      v9,
      &CLSID,
      (__int64 *)&v12,
      (__int64)&v14,
      (__int64)&v11,
      (__int64)&v15,
      &v16);
  }
  return 0;
}

```

## disassembly

```asm
0x180015070  mov     [rsp-18h+arg_8], rbx
0x180015075  push    rbp
0x180015076  push    rsi
0x180015077  push    rdi
0x180015078  mov     rbp, rsp
0x18001507b  sub     rsp, 70h
0x18001507f  mov     esi, edx
0x180015081  mov     rdi, rcx
0x180015084  add     rcx, 8
0x180015088  xor     edx, edx
0x18001508a  mov     rbx, r8
0x18001508d  call    ??4?$CComPtr@UIBinding@@@ATL@@QEAAPEAUIBinding@@PEAU2@@Z; ATL::CComPtr<IBinding>::operator=(IBinding *)
0x180015092  test    rbx, rbx
0x180015095  lea     rax, aNull; "(null)"
0x18001509c  cmovz   rbx, rax
0x1800150a0  mov     eax, cs:dword_18003F000
0x1800150a6  cmp     eax, 5
0x1800150a9  jbe     short loc_180015127
0x1800150ab  mov     edx, 10000000h
0x1800150b0  call    _tlgKeywordOn
0x1800150b5  test    al, al
0x1800150b7  jz      short loc_180015127
0x1800150b9  lea     rax, [rdi-10h]
0x1800150bd  mov     [rbp+arg_18], rbx
0x1800150c1  mov     [rbp+var_20], rax
0x1800150c5  mov     [rbp+arg_10], esi
0x1800150c8  mov     [rbp+arg_0], 1
0x1800150cc  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1800150d2  mov     ecx, 10000003h
0x1800150d7  mov     [rbp+var_18], rax
0x1800150db  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x1800150e1  mov     [rbp+var_10], rax
0x1800150e5  lea     rdx, word_1800355CA
0x1800150ec  lea     rax, [rbp+arg_18]
0x1800150f0  mov     [rsp+70h+var_28], rax
0x1800150f5  lea     rax, [rbp+arg_10]
0x1800150f9  mov     [rsp+70h+var_30], rax
0x1800150fe  lea     rax, [rbp+var_20]
0x180015102  mov     [rsp+70h+var_38], rax
0x180015107  lea     rax, [rbp+arg_0]
0x18001510b  mov     [rsp+70h+var_40], rax
0x180015110  lea     rax, [rbp+var_18]
0x180015114  mov     [rsp+70h+var_48], rax
0x180015119  lea     rax, [rbp+var_10]
0x18001511d  mov     [rsp+70h+var_50], rax
0x180015122  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180015127  mov     rbx, [rsp+70h+arg_8]
0x18001512f  xor     eax, eax
0x180015131  add     rsp, 70h
0x180015135  pop     rdi
0x180015136  pop     rsi
0x180015137  pop     rbp
0x180015138  retn
```
