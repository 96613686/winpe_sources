# RoutePolicyCallout::Wrapper_WcmKGetInterfaceForNetworkRequest(void *,_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH *,void * *)

- ea: `0x140006cc4`
- end: `0x140006e1f`
- name: `?Wrapper_WcmKGetInterfaceForNetworkRequest@RoutePolicyCallout@@YAKPEAXAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@PEAT_NET_LUID_LH@@PEAPEAX@Z`
- size: `347`
- prototype: `unsigned int(RoutePolicyCallout *__hidden this, void *, const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *, union _NET_LUID_LH *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140007280`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140006cc4`
- `0x140009fb4`
- `0x140009ff8`
- `0x14000a2d8`
- `0x14000a680`

## string_xrefs

- `0x140006dc3`: `WcmKOpenHandle failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyCallout::Wrapper_WcmKGetInterfaceForNetworkRequest(
        RoutePolicyCallout *this,
        const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *a2,
        union _NET_LUID_LH *a3,
        union _NET_LUID_LH *a4)
{
  __int64 result; // rax
  unsigned int v8; // ebx
  void *v9; // rcx
  int v10; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+30h] [rbp-78h] BYREF
  const char *v14; // [rsp+38h] [rbp-70h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+40h] [rbp-68h] BYREF
  int *v16; // [rsp+60h] [rbp-48h]
  __int64 v17; // [rsp+68h] [rbp-40h]

  a4->Value = 0;
  result = WcmKGetInterfaceForNetworkRequest(this, a2, a3, (void **)a4);
  v8 = result;
  if ( (_DWORD)result )
  {
    if ( (unsigned int)(result + 1073610725) > 1
      && (_DWORD)result != -1073610729
      && (_DWORD)result != 1062
      && (_DWORD)result != -2147417848
      && (unsigned int)(result + 2147418106) > 2
      && (_DWORD)result != -2147418094 )
    {
      return v8;
    }
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v13 = result;
      v16 = &v13;
      v17 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000FFEF, 0, 0, 3u, &v15);
    }
    v9 = (void *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 4);
    if ( v9 )
      WcmKCloseHandle(v9);
    v10 = WcmKOpenHandle((void **)RoutePolicyCallout::g_pCalloutContext + 4);
    if ( v10 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v13 = v10;
        v14 = "WcmKOpenHandle failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140012050,
          (unsigned __int8 *)byte_14000EE9D,
          v11,
          v12,
          (int **)&v14,
          (__int64)&v13);
      }
      return v8;
    }
    return WcmKGetInterfaceForNetworkRequest(*((void **)RoutePolicyCallout::g_pCalloutContext + 4), a2, a3, (void **)a4);
  }
  return result;
}

```

## disassembly

```asm
0x140006cc4  push    rbx
0x140006cc6  push    rbp
0x140006cc7  push    rsi
0x140006cc8  push    rdi
0x140006cc9  sub     rsp, 88h
0x140006cd0  mov     rax, cs:__security_cookie
0x140006cd7  xor     rax, rsp
0x140006cda  mov     [rsp+0A8h+var_38], rax
0x140006cdf  mov     rdi, r9
0x140006ce2  mov     qword ptr [r9], 0
0x140006ce9  mov     rbp, r8
0x140006cec  mov     rsi, rdx
0x140006cef  call    ?WcmKGetInterfaceForNetworkRequest@@YAKPEAXAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@PEAT_NET_LUID_LH@@PEAPEAX@Z; WcmKGetInterfaceForNetworkRequest(void *,_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH *,void * *)
0x140006cf4  mov     ebx, eax
0x140006cf6  test    eax, eax
0x140006cf8  jz      loc_140006E05
0x140006cfe  add     eax, 3FFDFFE5h
0x140006d03  cmp     eax, 1
0x140006d06  jbe     short loc_140006D37
0x140006d08  cmp     ebx, 0C0020017h
0x140006d0e  jz      short loc_140006D37
0x140006d10  cmp     ebx, 426h
0x140006d16  jz      short loc_140006D37
0x140006d18  cmp     ebx, 80010108h
0x140006d1e  jz      short loc_140006D37
0x140006d20  lea     eax, [rbx+7FFEFFFAh]
0x140006d26  cmp     eax, 2
0x140006d29  jbe     short loc_140006D37
0x140006d2b  cmp     ebx, 80010012h
0x140006d31  jnz     loc_140006DE8
0x140006d37  mov     eax, cs:dword_140012050
0x140006d3d  cmp     eax, 4
0x140006d40  jbe     short loc_140006D84
0x140006d42  lea     rax, [rsp+0A8h+var_78]
0x140006d47  mov     [rsp+0A8h+var_78], ebx
0x140006d4b  mov     [rsp+0A8h+var_48], rax
0x140006d50  lea     rdx, byte_14000FFEF; int
0x140006d57  lea     rax, [rsp+0A8h+var_68]
0x140006d5c  mov     [rsp+0A8h+var_40], 4
0x140006d65  mov     [rsp+0A8h+var_80], rax; PEVENT_DATA_DESCRIPTOR
0x140006d6a  lea     rcx, dword_140012050; int
0x140006d71  xor     r9d, r9d; int
0x140006d74  mov     [rsp+0A8h+var_88], 3; ULONG
0x140006d7c  xor     r8d, r8d; int
0x140006d7f  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006d84  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006d8b  mov     rcx, [rax+20h]; void *
0x140006d8f  test    rcx, rcx
0x140006d92  jz      short loc_140006D99
0x140006d94  call    ?WcmKCloseHandle@@YAXPEAX@Z; WcmKCloseHandle(void *)
0x140006d99  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006da0  add     rcx, 20h ; ' '; void **
0x140006da4  call    ?WcmKOpenHandle@@YAJPEAPEAX@Z; WcmKOpenHandle(void * *)
0x140006da9  test    eax, eax
0x140006dab  jns     short loc_140006DEC
0x140006dad  mov     ecx, cs:dword_140012050
0x140006db3  cmp     ecx, 2
0x140006db6  jbe     short loc_140006DE8
0x140006db8  mov     [rsp+0A8h+var_78], eax
0x140006dbc  lea     rdx, byte_14000EE9D
0x140006dc3  lea     rax, aWcmkopenhandle; "WcmKOpenHandle failed"
0x140006dca  mov     [rsp+0A8h+var_70], rax
0x140006dcf  lea     rax, [rsp+0A8h+var_78]
0x140006dd4  mov     [rsp+0A8h+var_80], rax
0x140006dd9  lea     rax, [rsp+0A8h+var_70]
0x140006dde  mov     qword ptr [rsp+0A8h+var_88], rax
0x140006de3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140006de8  mov     eax, ebx
0x140006dea  jmp     short loc_140006E05
0x140006dec  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006df3  mov     r9, rdi; void **
0x140006df6  mov     r8, rbp; union _NET_LUID_LH *
0x140006df9  mov     rdx, rsi; struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *
0x140006dfc  mov     rcx, [rcx+20h]; void *
0x140006e00  call    ?WcmKGetInterfaceForNetworkRequest@@YAKPEAXAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@PEAT_NET_LUID_LH@@PEAPEAX@Z; WcmKGetInterfaceForNetworkRequest(void *,_WCM_ROUTE_POLICY_NETWORK_REQUEST const &,_NET_LUID_LH *,void * *)
0x140006e05  mov     rcx, [rsp+0A8h+var_38]
0x140006e0a  xor     rcx, rsp; StackCookie
0x140006e0d  call    __security_check_cookie
0x140006e12  add     rsp, 88h
0x140006e19  pop     rdi
0x140006e1a  pop     rsi
0x140006e1b  pop     rbp
0x140006e1c  pop     rbx
0x140006e1d  retn
```
