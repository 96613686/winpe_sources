# CBrokerDownloadBindStatusCallback::OnProgress(ulong,ulong,ulong,ushort const *)

- ea: `0x180014e80`
- end: `0x180014f8e`
- name: `?OnProgress@CBrokerDownloadBindStatusCallback@@UEAAJKKKPEBG@Z`
- size: `270`
- prototype: `__int64 __fastcall(CBrokerDownloadBindStatusCallback *__hidden this, unsigned int, unsigned int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010230`

## callees

- `0x180001358`
- `0x180001a58`
- `0x180014e80`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014f10`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x180014f10`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014f01`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180014f01`

## pseudocode

```c
__int64 __fastcall CBrokerDownloadBindStatusCallback::OnProgress(
        CBrokerDownloadBindStatusCallback *this,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        const unsigned __int16 *a5)
{
  char *v5; // rdi
  unsigned int v6; // ebx
  const WCHAR *v7; // r8
  int v8; // r9d
  int v9; // r10d
  int v10; // r11d
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  int v15; // [rsp+70h] [rbp+1Fh] BYREF
  int v16; // [rsp+74h] [rbp+23h] BYREF
  const WCHAR *v17; // [rsp+78h] [rbp+27h] BYREF
  char *v18; // [rsp+80h] [rbp+2Fh] BYREF
  struct IE_GLOBAL_THREAD_STATE *v19; // [rsp+88h] [rbp+37h] BYREF
  __int64 CLSID; // [rsp+90h] [rbp+3Fh] BYREF
  int v21; // [rsp+B0h] [rbp+5Fh] BYREF
  char v22; // [rsp+B8h] [rbp+67h] BYREF

  v5 = (char *)this - 16;
  if ( a2 >= *((_DWORD *)this + 4) || (v6 = 0, a3 >= *((_DWORD *)v5 + 8)) )
    v6 = -2147467260;
  if ( (unsigned int)dword_18003F000 > 5 && (unsigned __int8)tlgKeywordOn(this, 0x10000000) )
  {
    LODWORD(a5) = v6;
    v17 = v7;
    v21 = v8;
    v15 = v9;
    v16 = v10;
    v18 = v5;
    v22 = 1;
    v19 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v11,
      (__int64)byte_180035653,
      v12,
      v13,
      &CLSID,
      (__int64 *)&v19,
      (__int64)&v22,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v15,
      (__int64)&v21,
      &v17,
      (__int64)&a5);
  }
  return v6;
}

```

## disassembly

```asm
0x180014e80  mov     [rsp-8+arg_10], rbx
0x180014e85  mov     [rsp-8+arg_18], rdi
0x180014e8a  push    rbp
0x180014e8b  lea     rbp, [rsp-4Fh]
0x180014e90  sub     rsp, 0A0h
0x180014e97  lea     rdi, [rcx-10h]
0x180014e9b  mov     r10d, r8d
0x180014e9e  mov     r11d, edx
0x180014ea1  cmp     edx, [rdi+20h]
0x180014ea4  jnb     short loc_180014EAE
0x180014ea6  xor     ebx, ebx
0x180014ea8  cmp     r8d, [rdi+20h]
0x180014eac  jb      short loc_180014EB3
0x180014eae  mov     ebx, 80004004h
0x180014eb3  mov     r8, [rbp+4Fh+arg_20]
0x180014eb7  lea     rax, aNull; "(null)"
0x180014ebe  test    r8, r8
0x180014ec1  cmovz   r8, rax
0x180014ec5  mov     eax, cs:dword_18003F000
0x180014ecb  cmp     eax, 5
0x180014ece  jbe     loc_180014F77
0x180014ed4  mov     edx, 10000000h
0x180014ed9  call    _tlgKeywordOn
0x180014ede  test    al, al
0x180014ee0  jz      loc_180014F77
0x180014ee6  mov     dword ptr [rbp+4Fh+arg_20], ebx
0x180014ee9  mov     [rbp+4Fh+var_28], r8
0x180014eed  mov     [rbp+4Fh+arg_0], r9d
0x180014ef1  mov     [rbp+4Fh+var_30], r10d
0x180014ef5  mov     [rbp+4Fh+var_2C], r11d
0x180014ef9  mov     [rbp+4Fh+var_20], rdi
0x180014efd  mov     [rbp+4Fh+arg_8], 1
0x180014f01  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180014f07  mov     ecx, 10000003h
0x180014f0c  mov     [rbp+4Fh+var_18], rax
0x180014f10  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x180014f16  mov     [rbp+4Fh+var_10], rax
0x180014f1a  lea     rdx, byte_180035653
0x180014f21  lea     rax, [rbp+4Fh+arg_20]
0x180014f25  mov     [rsp+0A0h+var_40], rax
0x180014f2a  lea     rax, [rbp+4Fh+var_28]
0x180014f2e  mov     [rsp+0A0h+var_48], rax
0x180014f33  lea     rax, [rbp+4Fh+arg_0]
0x180014f37  mov     [rsp+0A0h+var_50], rax
0x180014f3c  lea     rax, [rbp+4Fh+var_30]
0x180014f40  mov     [rsp+0A0h+var_58], rax
0x180014f45  lea     rax, [rbp+4Fh+var_2C]
0x180014f49  mov     [rsp+0A0h+var_60], rax
0x180014f4e  lea     rax, [rbp+4Fh+var_20]
0x180014f52  mov     [rsp+0A0h+var_68], rax
0x180014f57  lea     rax, [rbp+4Fh+arg_8]
0x180014f5b  mov     [rsp+0A0h+var_70], rax
0x180014f60  lea     rax, [rbp+4Fh+var_18]
0x180014f64  mov     [rsp+0A0h+var_78], rax
0x180014f69  lea     rax, [rbp+4Fh+var_10]
0x180014f6d  mov     [rsp+0A0h+var_80], rax
0x180014f72  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U4@U4@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@66AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180014f77  lea     r11, [rsp+0A0h+var_s0]
0x180014f7f  mov     eax, ebx
0x180014f81  mov     rbx, [r11+20h]
0x180014f85  mov     rdi, [r11+28h]
0x180014f89  mov     rsp, r11
0x180014f8c  pop     rbp
0x180014f8d  retn
```
