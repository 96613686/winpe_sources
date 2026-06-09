# Bus_IsAutoConnectionDisabled

- ea: `0x14002ae68`
- end: `0x14002aff3`
- name: `Bus_IsAutoConnectionDisabled`
- size: `395`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140007154`
- `0x140007478`
- `0x14000b44c`

## callees

- `0x140001a50`
- `0x1400024b8`
- `0x14001adc0`
- `0x14001ae00`
- `0x14002ae68`

## string_xrefs

- `0x14002ae88`: `\Registry\Machine\SYSTEM\CurrentControlSet\Control\Bluetooth\Audio\Hfp`

## pseudocode

```c
_BOOL8 Bus_IsAutoConnectionDisabled()
{
  int v0; // eax
  BOOL v1; // ebx
  int v3; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v4; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v5[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v6[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v7; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v8[2]; // [rsp+80h] [rbp-80h]
  _OWORD v9[7]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v10[2]; // [rsp+110h] [rbp+10h]

  v9[0] = *(_OWORD *)L"\\Registry\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp";
  v5[0] = 9306252;
  v9[2] = *(_OWORD *)L"e\\SYSTEM\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp";
  v5[1] = v9;
  v9[1] = *(_OWORD *)L"y\\Machine\\SYSTEM\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp";
  v4 = 0;
  v9[4] = *(_OWORD *)L"ControlSet\\Control\\Bluetooth\\Audio\\Hfp";
  v9[3] = *(_OWORD *)L"\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp";
  v9[6] = *(_OWORD *)L"ol\\Bluetooth\\Audio\\Hfp";
  v9[5] = *(_OWORD *)L"et\\Control\\Bluetooth\\Audio\\Hfp";
  v10[0] = *(_OWORD *)L"ooth\\Audio\\Hfp";
  *(_OWORD *)((char *)v10 + 14) = *(_OWORD *)L"dio\\Hfp";
  wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(
    &v4,
    0);
  v0 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD *, __int64, _QWORD, __int64 *))(WdfFunctions_01015 + 1832))(
         WdfDriverGlobals,
         0,
         v5,
         131097,
         0,
         &v4);
  v3 = 0;
  v1 = v0 >= 0
    && (v6[1] = &v7,
        v7 = *(_OWORD *)L"DisableAutoConnect",
        v6[0] = 2490404,
        v8[0] = *(_OWORD *)L"utoConnect",
        *(_QWORD *)((char *)v8 + 14) = *(_QWORD *)L"ect",
        (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, int *))(WdfFunctions_01015 + 1920))(
          WdfDriverGlobals,
          v4,
          v6,
          &v3) >= 0)
    && v3 != 0;
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v4);
  return v1;
}

```

## disassembly

```asm
0x14002ae68  mov     [rsp-8+arg_0], rbx
0x14002ae6d  push    rbp
0x14002ae6e  lea     rbp, [rsp-40h]
0x14002ae73  sub     rsp, 140h
0x14002ae7a  mov     rax, cs:__security_cookie
0x14002ae81  xor     rax, rsp
0x14002ae84  mov     [rbp+40h+var_10], rax
0x14002ae88  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0; "\\Registry\\Machine\\SYSTEM\\CurrentCon"...
0x14002ae8f  lea     rax, [rbp+40h+var_A0]
0x14002ae93  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+10h; "y\\Machine\\SYSTEM\\CurrentControlSet\\"...
0x14002ae9a  lea     rcx, [rsp+140h+var_F8]
0x14002ae9f  movups  [rbp+40h+var_A0], xmm0
0x14002aea3  xor     edx, edx
0x14002aea5  mov     [rsp+140h+var_F0], 8E008Ch
0x14002aeae  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+20h; "e\\SYSTEM\\CurrentControlSet\\Control\\"...
0x14002aeb5  movups  [rbp+40h+var_80], xmm0
0x14002aeb9  mov     [rsp+140h+var_E8], rax
0x14002aebe  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+40h; "ControlSet\\Control\\Bluetooth\\Audio\\"...
0x14002aec5  movups  [rbp+40h+var_90], xmm1
0x14002aec9  mov     [rsp+140h+var_F8], 0
0x14002aed2  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+30h; "\\CurrentControlSet\\Control\\Bluetooth"...
0x14002aed9  movups  [rbp+40h+var_60], xmm0
0x14002aedd  movaps  xmm0, xmmword ptr cs:aRegistryMachin_0+60h; "ol\\Bluetooth\\Audio\\Hfp"
0x14002aee4  movups  [rbp+40h+var_70], xmm1
0x14002aee8  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+50h; "et\\Control\\Bluetooth\\Audio\\Hfp"
0x14002aeef  movups  [rbp+40h+var_40], xmm0
0x14002aef3  movups  xmm0, xmmword ptr cs:aRegistryMachin_0+7Eh; "dio\\Hfp"
0x14002aefa  movups  [rbp+40h+var_50], xmm1
0x14002aefe  movaps  xmm1, xmmword ptr cs:aRegistryMachin_0+70h; "ooth\\Audio\\Hfp"
0x14002af05  movups  xmmword ptr [rbp+40h+var_30], xmm1
0x14002af09  movups  xmmword ptr [rbp+40h+var_30+0Eh], xmm0
0x14002af0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUWDFKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>::reset(WDFKEY__ *)
0x14002af12  mov     rax, cs:WdfFunctions_01015
0x14002af19  lea     rcx, [rsp+140h+var_F8]
0x14002af1e  mov     [rsp+140h+var_118], rcx
0x14002af23  lea     r8, [rsp+140h+var_F0]
0x14002af28  mov     rcx, cs:WdfDriverGlobals
0x14002af2f  mov     r9d, 20019h
0x14002af35  xor     edx, edx
0x14002af37  mov     [rsp+140h+var_120], 0
0x14002af40  mov     rax, [rax+728h]
0x14002af47  call    _guard_dispatch_icall
0x14002af4c  mov     [rsp+140h+var_100], 0
0x14002af54  test    eax, eax
0x14002af56  js      short loc_14002AFC7
0x14002af58  movups  xmm0, xmmword ptr cs:aDisableautocon; "DisableAutoConnect"
0x14002af5f  mov     rdx, [rsp+140h+var_F8]
0x14002af64  lea     rax, [rsp+140h+var_D0]
0x14002af69  movups  xmm1, xmmword ptr cs:aDisableautocon+10h; "utoConnect"
0x14002af70  mov     rcx, cs:WdfDriverGlobals
0x14002af77  lea     r9, [rsp+140h+var_100]
0x14002af7c  mov     [rsp+140h+var_D8], rax
0x14002af81  lea     r8, [rsp+140h+var_E0]
0x14002af86  mov     rax, cs:WdfFunctions_01015
0x14002af8d  movups  [rsp+140h+var_D0], xmm0
0x14002af92  mov     [rsp+140h+var_E0], 260024h
0x14002af9b  movsd   xmm0, qword ptr cs:aDisableautocon+1Eh; "ect"
0x14002afa3  movups  xmmword ptr [rbp+40h+var_C0], xmm1
0x14002afa7  movsd   qword ptr [rbp+40h+var_C0+0Eh], xmm0
0x14002afac  mov     rax, [rax+780h]
0x14002afb3  call    _guard_dispatch_icall
0x14002afb8  test    eax, eax
0x14002afba  js      short loc_14002AFC7
0x14002afbc  xor     ebx, ebx
0x14002afbe  cmp     [rsp+140h+var_100], ebx
0x14002afc2  setnz   bl
0x14002afc5  jmp     short loc_14002AFC9
0x14002afc7  xor     ebx, ebx
0x14002afc9  lea     rcx, [rsp+140h+var_F8]
0x14002afce  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002afd3  mov     eax, ebx
0x14002afd5  mov     rcx, [rbp+40h+var_10]
0x14002afd9  xor     rcx, rsp; StackCookie
0x14002afdc  call    __security_check_cookie
0x14002afe1  mov     rbx, [rsp+140h+arg_0]
0x14002afe9  add     rsp, 140h
0x14002aff0  pop     rbp
0x14002aff1  retn
```
