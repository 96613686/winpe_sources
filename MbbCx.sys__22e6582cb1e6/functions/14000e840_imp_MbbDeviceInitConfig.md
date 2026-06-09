# imp_MbbDeviceInitConfig

- ea: `0x14000e840`
- end: `0x14000e8f8`
- name: `imp_MbbDeviceInitConfig`
- size: `184`
- prototype: `NTSTATUS __stdcall(PWDFDEVICE_INIT DeviceInit)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x140009e10`
- `0x140009f1c`
- `0x14000e560`
- `0x14000e840`
- `0x140047e90`

## pseudocode

```c
NTSTATUS __stdcall imp_MbbDeviceInitConfig(PWDFDEVICE_INIT DeviceInit)
{
  __int64 v1; // rdx
  __int64 v2; // rdi
  struct WDFCXDEVICE_INIT *v3; // rax
  int v4; // edx
  struct WDFCXDEVICE_INIT *v5; // rbx

  v2 = v1;
  (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 3528))(WdfDriverGlobals);
  v3 = (struct WDFCXDEVICE_INIT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64))(WdfFunctions_01031 + 3168))(
                                    WdfDriverGlobals,
                                    v2);
  v5 = v3;
  if ( v3 )
  {
    CxDeviceInitSetPnpPowerCallbacks(v3);
    CxDeviceInitSetPowerPolicyCallbacks(v5);
    return 0;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v4) = 2;
      WPP_RECORDER_SF_qs(
        WPP_GLOBAL_Control->DeviceExtension,
        v4,
        11,
        10,
        (__int64)WPP_c2cb746ee0e53b6729cbe0619734295d_Traceguids,
        v2,
        (__int64)"cxDeviceInit");
    }
    return -1073741670;
  }
}

```

## disassembly

```asm
0x14000e840  mov     [rsp+arg_0], rbx
0x14000e845  push    rdi
0x14000e846  sub     rsp, 40h
0x14000e84a  mov     rax, cs:WdfFunctions_01031
0x14000e851  mov     rdi, rdx
0x14000e854  mov     rcx, cs:WdfDriverGlobals
0x14000e85b  mov     rax, [rax+0DC8h]
0x14000e862  call    _guard_dispatch_icall
0x14000e867  mov     rax, cs:WdfFunctions_01031
0x14000e86e  mov     rdx, rdi
0x14000e871  mov     rcx, cs:WdfDriverGlobals
0x14000e878  mov     rax, [rax+0C60h]
0x14000e87f  call    _guard_dispatch_icall
0x14000e884  mov     rbx, rax
0x14000e887  test    rax, rax
0x14000e88a  jnz     short loc_14000E8DA
0x14000e88c  lea     rax, WPP_RECORDER_INITIALIZED
0x14000e893  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000e89a  jz      short loc_14000E8D3
0x14000e89c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e8a3  lea     rax, aCxdeviceinit; "cxDeviceInit"
0x14000e8aa  mov     [rsp+48h+var_18], rax
0x14000e8af  lea     r9d, [rbx+0Ah]
0x14000e8b3  lea     rax, WPP_c2cb746ee0e53b6729cbe0619734295d_Traceguids
0x14000e8ba  mov     [rsp+48h+var_20], rdi
0x14000e8bf  lea     r8d, [rbx+0Bh]
0x14000e8c3  mov     [rsp+48h+var_28], rax
0x14000e8c8  mov     rcx, [rcx+40h]
0x14000e8cc  mov     dl, 2
0x14000e8ce  call    WPP_RECORDER_SF_qs
0x14000e8d3  mov     eax, 0C000009Ah
0x14000e8d8  jmp     short loc_14000E8EC
0x14000e8da  mov     rcx, rbx; struct WDFCXDEVICE_INIT *
0x14000e8dd  call    ?CxDeviceInitSetPnpPowerCallbacks@@YAXPEAUWDFCXDEVICE_INIT@@@Z; CxDeviceInitSetPnpPowerCallbacks(WDFCXDEVICE_INIT *)
0x14000e8e2  mov     rcx, rbx; struct WDFCXDEVICE_INIT *
0x14000e8e5  call    ?CxDeviceInitSetPowerPolicyCallbacks@@YAXPEAUWDFCXDEVICE_INIT@@@Z; CxDeviceInitSetPowerPolicyCallbacks(WDFCXDEVICE_INIT *)
0x14000e8ea  xor     eax, eax
0x14000e8ec  mov     rbx, [rsp+48h+arg_0]
0x14000e8f1  add     rsp, 40h
0x14000e8f5  pop     rdi
0x14000e8f6  retn
```
