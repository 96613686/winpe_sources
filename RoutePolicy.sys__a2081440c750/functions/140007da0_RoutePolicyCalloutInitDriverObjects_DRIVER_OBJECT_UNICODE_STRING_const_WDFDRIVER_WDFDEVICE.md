# RoutePolicyCalloutInitDriverObjects(_DRIVER_OBJECT *,_UNICODE_STRING const *,WDFDRIVER__ * *,WDFDEVICE__ * *)

- ea: `0x140007da0`
- end: `0x140008052`
- name: `?RoutePolicyCalloutInitDriverObjects@@YAJPEAU_DRIVER_OBJECT@@PEBU_UNICODE_STRING@@PEAPEAUWDFDRIVER__@@PEAPEAUWDFDEVICE__@@@Z`
- size: `690`
- prototype: `__int64 __fastcall(struct _DRIVER_OBJECT *, const struct _UNICODE_STRING *, struct WDFDRIVER__ **, struct WDFDEVICE__ **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14001903c`

## callees

- `0x140001008`
- `0x140007da0`
- `0x14000a680`
- `0x14000a6c0`

## string_xrefs

- `0x140007e34`: `WdfDriverCreate failed`
- `0x140007fa9`: `WdfDeviceCreate failed`

## pseudocode

```c
__int64 __fastcall RoutePolicyCalloutInitDriverObjects(
        struct _DRIVER_OBJECT *a1,
        const struct _UNICODE_STRING *a2,
        struct WDFDRIVER__ **a3,
        struct WDFDEVICE__ **a4)
{
  int v6; // eax
  int v7; // r8d
  int v8; // r9d
  unsigned int v9; // ebx
  __int64 v11; // rdx
  __int64 v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // r9
  int v17; // eax
  int v18; // r8d
  int v19; // r9d
  int v20; // [rsp+40h] [rbp-9h] BYREF
  const char *v21; // [rsp+48h] [rbp-1h] BYREF
  _QWORD v22[4]; // [rsp+50h] [rbp+7h] BYREF
  __int64 v23; // [rsp+70h] [rbp+27h] BYREF

  v22[2] = RoutePolicyCalloutEvtDriverUnload;
  v22[0] = 32;
  v22[3] = 1;
  v22[1] = 0;
  v6 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct _DRIVER_OBJECT *, const struct _UNICODE_STRING *, _QWORD, _QWORD *, struct WDFDRIVER__ **))(WdfFunctions_01015 + 928))(
         WdfDriverGlobals,
         a1,
         a2,
         0,
         v22,
         a3);
  v9 = v6;
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v20 = v6;
      v21 = "WdfDriverCreate failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_140012050,
        (unsigned int)byte_140010645,
        v7,
        v8,
        (__int64)&v21,
        (__int64)&v20);
    }
    return v9;
  }
  v11 = (__int64)*a3;
  v23 = 0;
  v12 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, const UNICODE_STRING *))(WdfFunctions_01015 + 200))(
          WdfDriverGlobals,
          v11,
          &SDDL_DEVOBJ_KERNEL_ONLY);
  v23 = v12;
  if ( v12 )
  {
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64))(WdfFunctions_01015 + 528))(
      WdfDriverGlobals,
      v12,
      18);
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, _QWORD))(WdfFunctions_01015 + 560))(
      WdfDriverGlobals,
      v23,
      256,
      0);
    LOBYTE(v16) = 1;
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, __int64, __int64))(WdfFunctions_01015 + 560))(
      WdfDriverGlobals,
      v23,
      128,
      v16);
    v17 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64 *, _QWORD, struct WDFDEVICE__ **))(WdfFunctions_01015 + 600))(
            WdfDriverGlobals,
            &v23,
            0,
            a4);
    v9 = v17;
    if ( v17 < 0 )
    {
      if ( (unsigned int)dword_140012050 > 2 )
      {
        v20 = v17;
        v21 = "WdfDeviceCreate failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_140012050,
          (unsigned int)byte_14001056D,
          v18,
          v19,
          (__int64)&v21,
          (__int64)&v20);
      }
      if ( v23 )
        (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 432))(WdfDriverGlobals);
      return v9;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01015 + 216))(WdfDriverGlobals, *a4);
    if ( v23 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 432))(WdfDriverGlobals);
    return 0;
  }
  else
  {
    if ( (unsigned int)dword_140012050 > 2 )
    {
      v20 = v9;
      v21 = "WdfControlDeviceInitAllocate failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v13,
        (unsigned int)&dword_1400105B4,
        v14,
        v15,
        (__int64)&v21,
        (__int64)&v20);
    }
    if ( v23 )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01015 + 432))(WdfDriverGlobals);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140007da0  push    rbp
0x140007da2  push    rbx
0x140007da3  push    rsi
0x140007da4  push    rdi
0x140007da5  lea     rbp, [rsp-3Fh]
0x140007daa  sub     rsp, 88h
0x140007db1  mov     rax, cs:__security_cookie
0x140007db8  xor     rax, rsp
0x140007dbb  mov     [rbp+57h+var_28], rax
0x140007dbf  mov     [rsp+0A0h+var_78], r8
0x140007dc4  lea     rax, RoutePolicyCalloutEvtDriverUnload
0x140007dcb  mov     [rbp+57h+var_40], rax
0x140007dcf  mov     rdi, r8
0x140007dd2  mov     rax, cs:WdfFunctions_01015
0x140007dd9  lea     r8, [rbp+57h+var_50]
0x140007ddd  mov     [rsp+0A0h+var_80], r8
0x140007de2  mov     rsi, r9
0x140007de5  mov     r8, rdx
0x140007de8  mov     [rbp+57h+var_50], 20h ; ' '
0x140007df0  mov     [rbp+57h+var_38], 1
0x140007df8  mov     rdx, rcx
0x140007dfb  mov     rcx, cs:WdfDriverGlobals
0x140007e02  xor     r9d, r9d
0x140007e05  mov     [rbp+57h+var_48], 0
0x140007e0d  mov     rax, [rax+3A0h]
0x140007e14  call    _guard_dispatch_icall
0x140007e19  mov     ebx, eax
0x140007e1b  test    eax, eax
0x140007e1d  jns     short loc_140007E5D
0x140007e1f  mov     ecx, cs:dword_140012050
0x140007e25  cmp     ecx, 2
0x140007e28  jbe     short loc_140007E56
0x140007e2a  mov     [rbp+57h+var_60], eax
0x140007e2d  lea     rdx, byte_140010645
0x140007e34  lea     rax, aWdfdrivercreat; "WdfDriverCreate failed"
0x140007e3b  mov     [rbp+57h+var_58], rax
0x140007e3f  lea     rax, [rbp+57h+var_60]
0x140007e43  mov     [rsp+0A0h+var_78], rax
0x140007e48  lea     rax, [rbp+57h+var_58]
0x140007e4c  mov     [rsp+0A0h+var_80], rax
0x140007e51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007e56  mov     eax, ebx
0x140007e58  jmp     loc_140008039
0x140007e5d  mov     rax, cs:WdfFunctions_01015
0x140007e64  lea     r8, SDDL_DEVOBJ_KERNEL_ONLY
0x140007e6b  mov     rdx, [rdi]
0x140007e6e  mov     rcx, cs:WdfDriverGlobals
0x140007e75  mov     [rbp+57h+var_30], 0
0x140007e7d  mov     rax, [rax+0C8h]
0x140007e84  call    _guard_dispatch_icall
0x140007e89  mov     [rbp+57h+var_30], rax
0x140007e8d  test    rax, rax
0x140007e90  jnz     short loc_140007EF6
0x140007e92  mov     eax, cs:dword_140012050
0x140007e98  cmp     eax, 2
0x140007e9b  jbe     short loc_140007EC9
0x140007e9d  lea     rax, aWdfcontroldevi; "WdfControlDeviceInitAllocate failed"
0x140007ea4  mov     [rbp+57h+var_60], ebx
0x140007ea7  mov     [rbp+57h+var_58], rax
0x140007eab  lea     rdx, dword_1400105B4
0x140007eb2  lea     rax, [rbp+57h+var_60]
0x140007eb6  mov     [rsp+0A0h+var_78], rax
0x140007ebb  lea     rax, [rbp+57h+var_58]
0x140007ebf  mov     [rsp+0A0h+var_80], rax
0x140007ec4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007ec9  mov     rdx, [rbp+57h+var_30]
0x140007ecd  test    rdx, rdx
0x140007ed0  jz      short loc_140007EEC
0x140007ed2  mov     rax, cs:WdfFunctions_01015
0x140007ed9  mov     rcx, cs:WdfDriverGlobals
0x140007ee0  mov     rax, [rax+1B0h]
0x140007ee7  call    _guard_dispatch_icall
0x140007eec  mov     eax, 0C000009Ah
0x140007ef1  jmp     loc_140008039
0x140007ef6  mov     rcx, cs:WdfFunctions_01015
0x140007efd  mov     rdx, rax
0x140007f00  mov     r8d, 12h
0x140007f06  mov     r10, [rcx+210h]
0x140007f0d  mov     rcx, cs:WdfDriverGlobals
0x140007f14  mov     rax, r10
0x140007f17  call    _guard_dispatch_icall
0x140007f1c  mov     rax, cs:WdfFunctions_01015
0x140007f23  xor     r9d, r9d
0x140007f26  mov     rdx, [rbp+57h+var_30]
0x140007f2a  mov     r8d, 100h
0x140007f30  mov     rcx, cs:WdfDriverGlobals
0x140007f37  mov     rax, [rax+230h]
0x140007f3e  call    _guard_dispatch_icall
0x140007f43  mov     rax, cs:WdfFunctions_01015
0x140007f4a  mov     r9b, 1
0x140007f4d  mov     rdx, [rbp+57h+var_30]
0x140007f51  mov     r8d, 80h
0x140007f57  mov     rcx, cs:WdfDriverGlobals
0x140007f5e  mov     rax, [rax+230h]
0x140007f65  call    _guard_dispatch_icall
0x140007f6a  mov     rax, cs:WdfFunctions_01015
0x140007f71  lea     rdx, [rbp+57h+var_30]
0x140007f75  mov     rcx, cs:WdfDriverGlobals
0x140007f7c  mov     r9, rsi
0x140007f7f  xor     r8d, r8d
0x140007f82  mov     rax, [rax+258h]
0x140007f89  call    _guard_dispatch_icall
0x140007f8e  mov     ebx, eax
0x140007f90  test    eax, eax
0x140007f92  jns     short loc_140007FF7
0x140007f94  mov     ecx, cs:dword_140012050
0x140007f9a  cmp     ecx, 2
0x140007f9d  jbe     short loc_140007FCB
0x140007f9f  mov     [rbp+57h+var_60], eax
0x140007fa2  lea     rdx, byte_14001056D
0x140007fa9  lea     rax, aWdfdevicecreat; "WdfDeviceCreate failed"
0x140007fb0  mov     [rbp+57h+var_58], rax
0x140007fb4  lea     rax, [rbp+57h+var_60]
0x140007fb8  mov     [rsp+0A0h+var_78], rax
0x140007fbd  lea     rax, [rbp+57h+var_58]
0x140007fc1  mov     [rsp+0A0h+var_80], rax
0x140007fc6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x140007fcb  mov     rdx, [rbp+57h+var_30]
0x140007fcf  test    rdx, rdx
0x140007fd2  jz      loc_140007E56
0x140007fd8  mov     rax, cs:WdfFunctions_01015
0x140007fdf  mov     rcx, cs:WdfDriverGlobals
0x140007fe6  mov     rax, [rax+1B0h]
0x140007fed  call    _guard_dispatch_icall
0x140007ff2  jmp     loc_140007E56
0x140007ff7  mov     rax, cs:WdfFunctions_01015
0x140007ffe  mov     rdx, [rsi]
0x140008001  mov     rcx, cs:WdfDriverGlobals
0x140008008  mov     rax, [rax+0D8h]
0x14000800f  call    _guard_dispatch_icall
0x140008014  mov     rdx, [rbp+57h+var_30]
0x140008018  test    rdx, rdx
0x14000801b  jz      short loc_140008037
0x14000801d  mov     rax, cs:WdfFunctions_01015
0x140008024  mov     rcx, cs:WdfDriverGlobals
0x14000802b  mov     rax, [rax+1B0h]
0x140008032  call    _guard_dispatch_icall
0x140008037  xor     eax, eax
0x140008039  mov     rcx, [rbp+57h+var_28]
0x14000803d  xor     rcx, rsp; StackCookie
0x140008040  call    __security_check_cookie
0x140008045  add     rsp, 88h
0x14000804c  pop     rdi
0x14000804d  pop     rsi
0x14000804e  pop     rbx
0x14000804f  pop     rbp
0x140008050  retn
```
