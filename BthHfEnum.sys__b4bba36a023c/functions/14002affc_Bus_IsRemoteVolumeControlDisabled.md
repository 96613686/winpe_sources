# Bus_IsRemoteVolumeControlDisabled

- ea: `0x14002affc`
- end: `0x14002b1b6`
- name: `Bus_IsRemoteVolumeControlDisabled`
- size: `442`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14002b5a0`

## callees

- `0x140001a10`
- `0x140001a2c`
- `0x140001a50`
- `0x14001adc0`
- `0x14001ae00`
- `0x14002affc`

## string_xrefs

- `0x14002b01c`: `\Registry\Machine\System\CurrentControlSet\Control\Bluetooth\Audio\Hfp\AudioGateway`

## pseudocode

```c
_BOOL8 Bus_IsRemoteVolumeControlDisabled()
{
  __int64 v0; // rax
  int v1; // ebx
  BOOL v2; // ebx
  int v4; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v5; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v6[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v7[3]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v8[2]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v9[22]; // [rsp+98h] [rbp-68h]
  _OWORD v10[10]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v11; // [rsp+150h] [rbp+50h]

  v10[0] = *(_OWORD *)L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v11 = *(_QWORD *)L"way";
  v10[1] = *(_OWORD *)L"y\\Machine\\System\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v6[0] = 11010214;
  v10[2] = *(_OWORD *)L"e\\System\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v6[1] = v10;
  v10[3] = *(_OWORD *)L"\\CurrentControlSet\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v5 = 0;
  v10[4] = *(_OWORD *)L"ControlSet\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v10[5] = *(_OWORD *)L"et\\Control\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v10[6] = *(_OWORD *)L"ol\\Bluetooth\\Audio\\Hfp\\AudioGateway";
  v10[7] = *(_OWORD *)L"ooth\\Audio\\Hfp\\AudioGateway";
  v10[8] = *(_OWORD *)L"io\\Hfp\\AudioGateway";
  v10[9] = *(_OWORD *)L"udioGateway";
  v0 = wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(
         v7,
         &v5);
  v1 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD *, __int64, _QWORD, __int64))(WdfFunctions_01015
                                                                                                  + 1832))(
         WdfDriverGlobals,
         0,
         v6,
         131097,
         0,
         v0 + 8);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(v7);
  v4 = 0;
  v2 = v1 >= 0
    && (v8[0] = *(_OWORD *)L"DisableRemoteVolumeControl",
        v7[1] = v8,
        v8[1] = *(_OWORD *)L"emoteVolumeControl",
        v7[0] = 3538996,
        *(_OWORD *)v9 = *(_OWORD *)L"umeControl",
        *(_QWORD *)&v9[14] = *(_QWORD *)L"rol",
        (*(int (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *, int *))(WdfFunctions_01015 + 1920))(
          WdfDriverGlobals,
          v5,
          v7,
          &v4) >= 0)
    && v4 != 0;
  wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(&v5);
  return v2;
}

```

## disassembly

```asm
0x14002affc  mov     [rsp-8+arg_0], rbx
0x14002b001  push    rbp
0x14002b002  lea     rbp, [rsp-70h]
0x14002b007  sub     rsp, 170h
0x14002b00e  mov     rax, cs:__security_cookie
0x14002b015  xor     rax, rsp
0x14002b018  mov     [rbp+70h+var_10], rax
0x14002b01c  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x14002b023  lea     rdx, [rsp+170h+var_128]
0x14002b028  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x14002b02f  lea     rcx, [rsp+170h+var_110]
0x14002b034  mov     rax, qword ptr cs:aRegistryMachin+0A0h; "way"
0x14002b03b  movups  [rbp+70h+var_C0], xmm0
0x14002b03f  mov     [rbp+70h+var_20], rax
0x14002b043  lea     rax, [rbp+70h+var_C0]
0x14002b047  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x14002b04e  movups  [rbp+70h+var_B0], xmm1
0x14002b052  mov     [rsp+170h+var_120], 0A800A6h
0x14002b05b  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Control\\Bluetooth"...
0x14002b062  movups  [rbp+70h+var_A0], xmm0
0x14002b066  mov     [rsp+170h+var_118], rax
0x14002b06b  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Control\\Bluetooth\\Audio\\"...
0x14002b072  movups  [rbp+70h+var_90], xmm1
0x14002b076  mov     [rsp+170h+var_128], 0
0x14002b07f  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Control\\Bluetooth\\Audio\\Hfp\\Aud"...
0x14002b086  movups  [rbp+70h+var_80], xmm0
0x14002b08a  movaps  xmm0, xmmword ptr cs:aRegistryMachin+60h; "ol\\Bluetooth\\Audio\\Hfp\\AudioGateway"
0x14002b091  movups  [rbp+70h+var_70], xmm1
0x14002b095  movaps  xmm1, xmmword ptr cs:aRegistryMachin+70h; "ooth\\Audio\\Hfp\\AudioGateway"
0x14002b09c  movups  [rbp+70h+var_60], xmm0
0x14002b0a0  movaps  xmm0, xmmword ptr cs:aRegistryMachin+80h; "io\\Hfp\\AudioGateway"
0x14002b0a7  movups  [rbp+70h+var_50], xmm1
0x14002b0ab  movaps  xmm1, xmmword ptr cs:aRegistryMachin+90h; "udioGateway"
0x14002b0b2  movups  [rbp+70h+var_40], xmm0
0x14002b0b6  movups  [rbp+70h+var_30], xmm1
0x14002b0ba  call    ??$out_param@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AU?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@0@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::out_param<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>> &)
0x14002b0bf  mov     r9d, 20019h
0x14002b0c5  lea     r8, [rsp+170h+var_120]
0x14002b0ca  xor     edx, edx
0x14002b0cc  lea     rcx, [rax+8]
0x14002b0d0  mov     rax, cs:WdfFunctions_01015
0x14002b0d7  mov     [rsp+170h+var_148], rcx
0x14002b0dc  mov     rcx, cs:WdfDriverGlobals
0x14002b0e3  mov     [rsp+170h+var_150], 0
0x14002b0ec  mov     rax, [rax+728h]
0x14002b0f3  call    _guard_dispatch_icall
0x14002b0f8  lea     rcx, [rsp+170h+var_110]
0x14002b0fd  mov     ebx, eax
0x14002b0ff  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<WDFKEY__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFKEY__ *,WDFKEY__ *,0,std::nullptr_t>>>>(void)
0x14002b104  mov     [rsp+170h+var_130], 0
0x14002b10c  test    ebx, ebx
0x14002b10e  js      short loc_14002B18A
0x14002b110  movups  xmm0, xmmword ptr cs:aDisableremotev; "DisableRemoteVolumeControl"
0x14002b117  mov     rdx, [rsp+170h+var_128]
0x14002b11c  lea     rax, [rsp+170h+var_F8]
0x14002b121  movups  xmm1, xmmword ptr cs:aDisableremotev+10h; "emoteVolumeControl"
0x14002b128  mov     rcx, cs:WdfDriverGlobals
0x14002b12f  lea     r9, [rsp+170h+var_130]
0x14002b134  movups  [rsp+170h+var_F8], xmm0
0x14002b139  mov     [rsp+170h+var_108], rax
0x14002b13e  lea     r8, [rsp+170h+var_110]
0x14002b143  movups  xmm0, xmmword ptr cs:aDisableremotev+20h; "umeControl"
0x14002b14a  mov     rax, cs:WdfFunctions_01015
0x14002b151  movups  [rbp+70h+var_E8], xmm1
0x14002b155  mov     [rsp+170h+var_110], 360034h
0x14002b15e  movsd   xmm1, qword ptr cs:aDisableremotev+2Eh; "rol"
0x14002b166  movups  xmmword ptr [rbp+70h+var_D8], xmm0
0x14002b16a  movsd   qword ptr [rbp+70h+var_D8+0Eh], xmm1
0x14002b16f  mov     rax, [rax+780h]
0x14002b176  call    _guard_dispatch_icall
0x14002b17b  test    eax, eax
0x14002b17d  js      short loc_14002B18A
0x14002b17f  xor     ebx, ebx
0x14002b181  cmp     [rsp+170h+var_130], ebx
0x14002b185  setnz   bl
0x14002b188  jmp     short loc_14002B18C
0x14002b18a  xor     ebx, ebx
0x14002b18c  lea     rcx, [rsp+170h+var_128]
0x14002b191  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002b196  mov     eax, ebx
0x14002b198  mov     rcx, [rbp+70h+var_10]
0x14002b19c  xor     rcx, rsp; StackCookie
0x14002b19f  call    __security_check_cookie
0x14002b1a4  mov     rbx, [rsp+170h+arg_0]
0x14002b1ac  add     rsp, 170h
0x14002b1b3  pop     rbp
0x14002b1b4  retn
```
