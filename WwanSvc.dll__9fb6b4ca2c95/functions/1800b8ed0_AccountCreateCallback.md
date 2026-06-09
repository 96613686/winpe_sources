# _AccountCreateCallback

- ea: `0x1800b8ed0`
- end: `0x1800b9005`
- name: `_AccountCreateCallback`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180012300`
- `0x180019f24`
- `0x180074758`
- `0x1800b8ed0`
- `0x1800b937c`
- `0x1800c5d28`

## import_xrefs

- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x1800b8f3f`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x1800b8f3f`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800b8fa0`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800b8fa0`
- `MobileNetworking!SetNetworkAccountBindingDeviceInterfacePath` at `0x1800b8f8b`
- `MobileNetworking!SetNetworkAccountBindingDeviceInterfacePath` at `0x1800b8f8b`

## string_xrefs

- `0x1800b8edc`: `_AccountCreateCallback`
- `0x1800b8fb8`: `AccountCreateCallback: device creation failed with hresult 0x%8x`
- `0x1800b8fad`: `AccountCreateCallback: failed with hresult 0x%8x`

## pseudocode

```c
void __fastcall AccountCreateCallback(__int64 a1, int a2, void *a3)
{
  int v6; // eax
  signed int v7; // ebx

  WwanLog::Enter("_AccountCreateCallback");
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( a2 < 0 )
  {
    v7 = 0;
    WwanLog::Error(
      "_AccountCreateCallback",
      0,
      L"AccountCreateCallback: device creation failed with hresult 0x%8x",
      (unsigned int)a2);
  }
  else
  {
    v6 = SwDeviceInterfaceRegister(a1, &GUID_DEVINTERFACE_MBAE, 0);
    v7 = v6;
    if ( v6 >= 0 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v7 = -2147418113;
LABEL_8:
      WwanLog::Error("_AccountCreateCallback", 0, L"AccountCreateCallback: failed with hresult 0x%8x", (unsigned int)v7);
      goto LABEL_10;
    }
    WwanLog::Error("_AccountCreateCallback", 0, L"SwDeviceInterfaceRegister failed, hr = 0x%8x", (unsigned int)v6);
    if ( v7 < 0 )
      goto LABEL_8;
  }
LABEL_10:
  if ( a3 )
    FreeSwDeviceCreateCallbackContext(a3);
  if ( v7 < 0 )
  {
    if ( (v7 & 0x1FFF0000) == 0x70000 )
      v7 = (unsigned __int16)v7;
  }
  else
  {
    v7 = 0;
  }
  WwanLog::ExitWithStatus("_AccountCreateCallback", v7);
}

```

## disassembly

```asm
0x1800b8ed0  push    rbx
0x1800b8ed2  push    rbp
0x1800b8ed3  push    rsi
0x1800b8ed4  push    rdi
0x1800b8ed5  sub     rsp, 48h
0x1800b8ed9  mov     rbx, rcx
0x1800b8edc  lea     rbp, aAccountcreatec_0; "_AccountCreateCallback"
0x1800b8ee3  mov     rcx, rbp; char *
0x1800b8ee6  mov     rdi, r8
0x1800b8ee9  mov     esi, edx
0x1800b8eeb  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800b8ef0  mov     [rsp+68h+arg_10], 0
0x1800b8efc  test    rdi, rdi
0x1800b8eff  jnz     short loc_1800B8F06
0x1800b8f01  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b8f06  test    esi, esi
0x1800b8f08  js      loc_1800B8FB6
0x1800b8f0e  lea     rax, [rsp+68h+arg_10]
0x1800b8f16  mov     r9d, 1
0x1800b8f1c  mov     [rsp+68h+var_38], rax
0x1800b8f21  lea     rdx, GUID_DEVINTERFACE_MBAE
0x1800b8f28  lea     rax, qword_1801511E8
0x1800b8f2f  mov     [rsp+68h+var_40], r9d
0x1800b8f34  xor     r8d, r8d
0x1800b8f37  mov     [rsp+68h+var_48], rax
0x1800b8f3c  mov     rcx, rbx
0x1800b8f3f  call    cs:__imp_SwDeviceInterfaceRegister
0x1800b8f45  mov     ebx, eax
0x1800b8f47  test    eax, eax
0x1800b8f49  jns     short loc_1800B8F61
0x1800b8f4b  mov     r9d, eax
0x1800b8f4e  lea     r8, aSwdeviceinterf; "SwDeviceInterfaceRegister failed, hr = "...
0x1800b8f55  xor     edx, edx; struct _GUID *
0x1800b8f57  mov     rcx, rbp; char *
0x1800b8f5a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b8f5f  jmp     short loc_1800B8F93
0x1800b8f61  mov     rdx, [rsp+68h+arg_10]
0x1800b8f69  test    rdx, rdx
0x1800b8f6c  jnz     short loc_1800B8F87
0x1800b8f6e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800b8f73  mov     rdx, [rsp+68h+arg_10]
0x1800b8f7b  test    rdx, rdx
0x1800b8f7e  jnz     short loc_1800B8F87
0x1800b8f80  mov     ebx, 8000FFFFh
0x1800b8f85  jmp     short loc_1800B8FAA
0x1800b8f87  mov     rcx, [rdi+8]
0x1800b8f8b  call    cs:__imp_SetNetworkAccountBindingDeviceInterfacePath
0x1800b8f91  mov     ebx, eax
0x1800b8f93  mov     rcx, [rsp+68h+arg_10]
0x1800b8f9b  test    rcx, rcx
0x1800b8f9e  jz      short loc_1800B8FA6
0x1800b8fa0  call    cs:__imp_SwMemFree
0x1800b8fa6  test    ebx, ebx
0x1800b8fa8  jns     short loc_1800B8FCC
0x1800b8faa  mov     r9d, ebx
0x1800b8fad  lea     r8, aAccountcreatec_1; "AccountCreateCallback: failed with hres"...
0x1800b8fb4  jmp     short loc_1800B8FC2
0x1800b8fb6  xor     ebx, ebx
0x1800b8fb8  lea     r8, aAccountcreatec; "AccountCreateCallback: device creation "...
0x1800b8fbf  mov     r9d, esi
0x1800b8fc2  xor     edx, edx; struct _GUID *
0x1800b8fc4  mov     rcx, rbp; char *
0x1800b8fc7  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b8fcc  test    rdi, rdi
0x1800b8fcf  jz      short loc_1800B8FD9
0x1800b8fd1  mov     rcx, rdi; lpMem
0x1800b8fd4  call    _FreeSwDeviceCreateCallbackContext
0x1800b8fd9  test    ebx, ebx
0x1800b8fdb  js      short loc_1800B8FE1
0x1800b8fdd  xor     ebx, ebx
0x1800b8fdf  jmp     short loc_1800B8FF2
0x1800b8fe1  mov     eax, ebx
0x1800b8fe3  and     eax, 1FFF0000h
0x1800b8fe8  cmp     eax, 70000h
0x1800b8fed  jnz     short loc_1800B8FF2
0x1800b8fef  movzx   ebx, bx
0x1800b8ff2  mov     edx, ebx; unsigned int
0x1800b8ff4  mov     rcx, rbp; char *
0x1800b8ff7  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800b8ffc  add     rsp, 48h
0x1800b9000  pop     rdi
0x1800b9001  pop     rsi
0x1800b9002  pop     rbp
0x1800b9003  pop     rbx
0x1800b9004  retn
```
