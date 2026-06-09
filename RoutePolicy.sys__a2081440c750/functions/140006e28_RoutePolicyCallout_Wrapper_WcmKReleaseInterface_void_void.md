# RoutePolicyCallout::Wrapper_WcmKReleaseInterface(void *,void *)

- ea: `0x140006e28`
- end: `0x140006f76`
- name: `?Wrapper_WcmKReleaseInterface@RoutePolicyCallout@@YAKPEAX0@Z`
- size: `334`
- prototype: `unsigned int(RoutePolicyCallout *__hidden this, void *, void *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x140003f18`
- `0x14000664c`
- `0x140007110`
- `0x140007280`

## callees

- `0x140001008`
- `0x1400012f0`
- `0x140006e28`
- `0x140009fb4`
- `0x140009ff8`
- `0x14000a478`
- `0x14000a680`

## string_xrefs

- `0x140006f1b`: `WcmKOpenHandle failed`

## pseudocode

```c
unsigned int __fastcall RoutePolicyCallout::Wrapper_WcmKReleaseInterface(RoutePolicyCallout *this, void *a2, void *a3)
{
  unsigned int result; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // [rsp+30h] [rbp-58h] BYREF
  const char *v11; // [rsp+38h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v12; // [rsp+40h] [rbp-48h] BYREF
  unsigned int *v13; // [rsp+60h] [rbp-28h]
  __int64 v14; // [rsp+68h] [rbp-20h]

  result = WcmKReleaseInterface(this, a2);
  v5 = result;
  if ( result )
  {
    if ( result + 1073610725 > 1
      && result != -1073610729
      && result != 1062
      && result != -2147417848
      && result + 2147418106 > 2
      && result != -2147418094 )
    {
      return v5;
    }
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v10 = result;
      v13 = &v10;
      v14 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&unk_14000F2D8, 0, 0, 3u, &v12);
    }
    v6 = (void *)*((_QWORD *)RoutePolicyCallout::g_pCalloutContext + 4);
    if ( v6 )
      WcmKCloseHandle(v6);
    v7 = WcmKOpenHandle((void **)RoutePolicyCallout::g_pCalloutContext + 4);
    if ( v7 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v10 = v7;
        v11 = "WcmKOpenHandle failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)dword_140012050,
          (unsigned __int8 *)byte_14000F9D3,
          v8,
          v9,
          (int **)&v11,
          (__int64)&v10);
      }
      return v5;
    }
    return WcmKReleaseInterface(*((void **)RoutePolicyCallout::g_pCalloutContext + 4), a2);
  }
  return result;
}

```

## disassembly

```asm
0x140006e28  mov     [rsp+arg_10], rbx
0x140006e2d  push    rdi
0x140006e2e  sub     rsp, 80h
0x140006e35  mov     rax, cs:__security_cookie
0x140006e3c  xor     rax, rsp
0x140006e3f  mov     [rsp+88h+var_18], rax
0x140006e44  mov     rdi, rdx
0x140006e47  call    ?WcmKReleaseInterface@@YAKPEAX0@Z; WcmKReleaseInterface(void *,void *)
0x140006e4c  mov     ebx, eax
0x140006e4e  test    eax, eax
0x140006e50  jz      loc_140006F57
0x140006e56  add     eax, 3FFDFFE5h
0x140006e5b  cmp     eax, 1
0x140006e5e  jbe     short loc_140006E8F
0x140006e60  cmp     ebx, 0C0020017h
0x140006e66  jz      short loc_140006E8F
0x140006e68  cmp     ebx, 426h
0x140006e6e  jz      short loc_140006E8F
0x140006e70  cmp     ebx, 80010108h
0x140006e76  jz      short loc_140006E8F
0x140006e78  lea     eax, [rbx+7FFEFFFAh]
0x140006e7e  cmp     eax, 2
0x140006e81  jbe     short loc_140006E8F
0x140006e83  cmp     ebx, 80010012h
0x140006e89  jnz     loc_140006F40
0x140006e8f  mov     eax, cs:dword_140012050
0x140006e95  cmp     eax, 4
0x140006e98  jbe     short loc_140006EDC
0x140006e9a  lea     rax, [rsp+88h+var_58]
0x140006e9f  mov     [rsp+88h+var_58], ebx
0x140006ea3  mov     [rsp+88h+var_28], rax
0x140006ea8  lea     rdx, unk_14000F2D8; int
0x140006eaf  lea     rax, [rsp+88h+var_48]
0x140006eb4  mov     [rsp+88h+var_20], 4
0x140006ebd  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x140006ec2  lea     rcx, dword_140012050; int
0x140006ec9  xor     r9d, r9d; int
0x140006ecc  mov     [rsp+88h+var_68], 3; ULONG
0x140006ed4  xor     r8d, r8d; int
0x140006ed7  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006edc  mov     rax, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006ee3  mov     rcx, [rax+20h]; void *
0x140006ee7  test    rcx, rcx
0x140006eea  jz      short loc_140006EF1
0x140006eec  call    ?WcmKCloseHandle@@YAXPEAX@Z; WcmKCloseHandle(void *)
0x140006ef1  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006ef8  add     rcx, 20h ; ' '; void **
0x140006efc  call    ?WcmKOpenHandle@@YAJPEAPEAX@Z; WcmKOpenHandle(void * *)
0x140006f01  test    eax, eax
0x140006f03  jns     short loc_140006F44
0x140006f05  mov     ecx, cs:dword_140012050
0x140006f0b  cmp     ecx, 2
0x140006f0e  jbe     short loc_140006F40
0x140006f10  mov     [rsp+88h+var_58], eax
0x140006f14  lea     rdx, byte_14000F9D3
0x140006f1b  lea     rax, aWcmkopenhandle; "WcmKOpenHandle failed"
0x140006f22  mov     [rsp+88h+var_50], rax
0x140006f27  lea     rax, [rsp+88h+var_58]
0x140006f2c  mov     [rsp+88h+var_60], rax
0x140006f31  lea     rax, [rsp+88h+var_50]
0x140006f36  mov     qword ptr [rsp+88h+var_68], rax
0x140006f3b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140006f40  mov     eax, ebx
0x140006f42  jmp     short loc_140006F57
0x140006f44  mov     rcx, cs:?g_pCalloutContext@RoutePolicyCallout@@3PEAUCALLOUT_CONTEXT@1@EA; RoutePolicyCallout::CALLOUT_CONTEXT * RoutePolicyCallout::g_pCalloutContext
0x140006f4b  mov     rdx, rdi; void *
0x140006f4e  mov     rcx, [rcx+20h]; void *
0x140006f52  call    ?WcmKReleaseInterface@@YAKPEAX0@Z; WcmKReleaseInterface(void *,void *)
0x140006f57  mov     rcx, [rsp+88h+var_18]
0x140006f5c  xor     rcx, rsp; StackCookie
0x140006f5f  call    __security_check_cookie
0x140006f64  mov     rbx, [rsp+88h+arg_10]
0x140006f6c  add     rsp, 80h
0x140006f73  pop     rdi
0x140006f74  retn
```
