# IEFavResolver::RequestFaviconDataFromEdge(ushort const *,ushort const *)

- ea: `0x18001a1b0`
- end: `0x18001a300`
- name: `?RequestFaviconDataFromEdge@IEFavResolver@@AEAAJPEBG0@Z`
- size: `336`
- prototype: `int(IEFavResolver *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180016a9c`

## callees

- `0x1800021b8`
- `0x18000d17c`
- `0x18001a1b0`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a29a`
- `iertutil!__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z` at `0x18001a29a`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18001a25c`
- `edgeIso!__imp_?LCIEPostMessage@@YAJKKKKK@Z` at `0x18001a25c`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18001a1f1`
- `edgeIso!__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z` at `0x18001a1f1`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001a26b`
- `edgeIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001a26b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a28b`
- `edgeIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18001a28b`

## pseudocode

```c
__int64 __fastcall IEFavResolver::RequestFaviconDataFromEdge(
        IEFavResolver *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v6; // ebx
  unsigned int v7; // r11d
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // r9
  int v12; // [rsp+50h] [rbp-30h] BYREF
  struct _IsoMessage *v13; // [rsp+58h] [rbp-28h] BYREF
  const WCHAR *v14; // [rsp+60h] [rbp-20h] BYREF
  const WCHAR *v15; // [rsp+68h] [rbp-18h] BYREF
  struct IE_GLOBAL_THREAD_STATE *v16; // [rsp+70h] [rbp-10h] BYREF
  __int64 CLSID; // [rsp+78h] [rbp-8h] BYREF
  char v18; // [rsp+A0h] [rbp+20h] BYREF
  unsigned int v19; // [rsp+B8h] [rbp+38h] BYREF

  v19 = 0;
  v13 = 0;
  v6 = IsoAllocMessageBuffer(*((_DWORD *)this + 2), &v19, 0x640u, &v13);
  if ( v6 >= 0 )
  {
    v6 = StringCchCopyW((unsigned __int16 *)v13 + 16, 0x104u, a2);
    if ( v6 < 0
      || (v6 = StringCchCopyW((unsigned __int16 *)v13 + 276, v7, a3), v6 < 0)
      || (*((_DWORD *)v13 + 398) = 0,
          v6 = LCIEPostMessage(*((_DWORD *)this + 2), *((_DWORD *)this + 1), 0xDC7u, 0, v19),
          v6 < 0) )
    {
      IsoFreeMessageBuffer(v19);
    }
  }
  if ( (unsigned int)dword_18003F000 > 5 )
  {
    v12 = v6;
    v14 = a3;
    v15 = a2;
    v18 = 1;
    v16 = GlobalThreadState();
    CLSID = IEConfiguration_GetCLSID(268435459);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v8,
      (__int64)byte_180035DD5,
      v9,
      v10,
      &CLSID,
      (__int64 *)&v16,
      (__int64)&v18,
      &v15,
      &v14,
      (__int64)&v12);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a1b0  mov     [rsp-18h+arg_8], rbx
0x18001a1b5  mov     [rsp-18h+arg_10], rsi
0x18001a1ba  push    rbp
0x18001a1bb  push    rdi
0x18001a1bc  push    r14
0x18001a1be  mov     rbp, rsp
0x18001a1c1  sub     rsp, 80h
0x18001a1c8  mov     rsi, r8
0x18001a1cb  mov     [rbp+arg_18], 0
0x18001a1d2  mov     r14, rdx
0x18001a1d5  mov     [rbp+var_28], 0
0x18001a1dd  mov     rdi, rcx
0x18001a1e0  lea     rdx, [rbp+arg_18]
0x18001a1e4  mov     ecx, [rcx+8]
0x18001a1e7  lea     r9, [rbp+var_28]
0x18001a1eb  mov     r8d, 640h
0x18001a1f1  call    cs:__imp_?IsoAllocMessageBuffer@@YAJKPEAKKPEAPEAU_IsoMessage@@@Z; IsoAllocMessageBuffer(ulong,ulong *,ulong,_IsoMessage * *)
0x18001a1f7  mov     ebx, eax
0x18001a1f9  test    eax, eax
0x18001a1fb  js      short loc_18001A271
0x18001a1fd  mov     rcx, [rbp+var_28]
0x18001a201  mov     r11d, 104h
0x18001a207  add     rcx, 20h ; ' '; unsigned __int16 *
0x18001a20b  mov     edx, r11d; unsigned __int64
0x18001a20e  mov     r8, r14; unsigned __int16 *
0x18001a211  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a216  mov     ebx, eax
0x18001a218  test    eax, eax
0x18001a21a  js      short loc_18001A268
0x18001a21c  mov     rcx, [rbp+var_28]
0x18001a220  mov     r8, rsi; unsigned __int16 *
0x18001a223  add     rcx, 228h; unsigned __int16 *
0x18001a22a  mov     edx, r11d; unsigned __int64
0x18001a22d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a232  mov     ebx, eax
0x18001a234  test    eax, eax
0x18001a236  js      short loc_18001A268
0x18001a238  mov     rax, [rbp+var_28]
0x18001a23c  xor     r9d, r9d
0x18001a23f  mov     r8d, 0DC7h
0x18001a245  mov     dword ptr [rax+638h], 0
0x18001a24f  mov     eax, [rbp+arg_18]
0x18001a252  mov     edx, [rdi+4]
0x18001a255  mov     ecx, [rdi+8]
0x18001a258  mov     dword ptr [rsp+80h+var_60], eax
0x18001a25c  call    cs:__imp_?LCIEPostMessage@@YAJKKKKK@Z; LCIEPostMessage(ulong,ulong,ulong,ulong,ulong)
0x18001a262  mov     ebx, eax
0x18001a264  test    eax, eax
0x18001a266  jns     short loc_18001A271
0x18001a268  mov     ecx, [rbp+arg_18]
0x18001a26b  call    cs:__imp_?IsoFreeMessageBuffer@@YAJK@Z; IsoFreeMessageBuffer(ulong)
0x18001a271  mov     eax, cs:dword_18003F000
0x18001a277  cmp     eax, 5
0x18001a27a  jbe     short loc_18001A2E6
0x18001a27c  mov     [rbp+var_30], ebx
0x18001a27f  mov     [rbp+var_20], rsi
0x18001a283  mov     [rbp+var_18], r14
0x18001a287  mov     [rbp+arg_0], 1
0x18001a28b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x18001a291  mov     ecx, 10000003h
0x18001a296  mov     [rbp+var_10], rax
0x18001a29a  call    cs:__imp_?IEConfiguration_GetCLSID@@YAPEBU_GUID@@W4IEConfigurationID@@@Z; IEConfiguration_GetCLSID(IEConfigurationID)
0x18001a2a0  mov     [rbp+var_8], rax
0x18001a2a4  lea     rdx, byte_180035DD5
0x18001a2ab  lea     rax, [rbp+var_30]
0x18001a2af  mov     [rsp+80h+var_38], rax
0x18001a2b4  lea     rax, [rbp+var_20]
0x18001a2b8  mov     [rsp+80h+var_40], rax
0x18001a2bd  lea     rax, [rbp+var_18]
0x18001a2c1  mov     [rsp+80h+var_48], rax
0x18001a2c6  lea     rax, [rbp+arg_0]
0x18001a2ca  mov     [rsp+80h+var_50], rax
0x18001a2cf  lea     rax, [rbp+var_10]
0x18001a2d3  mov     [rsp+80h+var_58], rax
0x18001a2d8  lea     rax, [rbp+var_8]
0x18001a2dc  mov     [rsp+80h+var_60], rax
0x18001a2e1  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_BrowserWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_BrowserWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001a2e6  lea     r11, [rsp+80h+var_s0]
0x18001a2ee  mov     eax, ebx
0x18001a2f0  mov     rbx, [r11+28h]
0x18001a2f4  mov     rsi, [r11+30h]
0x18001a2f8  mov     rsp, r11
0x18001a2fb  pop     r14
0x18001a2fd  pop     rdi
0x18001a2fe  pop     rbp
0x18001a2ff  retn
```
