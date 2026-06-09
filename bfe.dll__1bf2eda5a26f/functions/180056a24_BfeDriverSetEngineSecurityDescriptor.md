# BfeDriverSetEngineSecurityDescriptor

- ea: `0x180056a24`
- end: `0x180056ae2`
- name: `BfeDriverSetEngineSecurityDescriptor`
- size: `190`
- prototype: `__int64 __fastcall(PVOID InputBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002fe28`

## callees

- `0x180018b74`
- `0x180024b30`
- `0x1800557a4`
- `0x180056a24`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x180056a31`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180056a7c`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180056a31`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180056a7c`

## string_xrefs

- `0x180056ab6`: `bfe.dll`
- `0x180056ac5`: `BfeDriverSetEngineSecurityDescriptor`

## pseudocode

```c
__int64 __fastcall BfeDriverSetEngineSecurityDescriptor(PVOID InputBuffer)
{
  ULONG v2; // eax
  __int64 v3; // rbx
  ULONG v4; // eax
  __int64 v5; // rax

  v2 = RtlLengthSecurityDescriptor(InputBuffer);
  v3 = BfeDeviceIoControl(gBfeDriverControlComponent, 0x124048u, v2, InputBuffer, 0, 0, 0, 0);
  if ( v3 )
    goto LABEL_4;
  v4 = RtlLengthSecurityDescriptor(InputBuffer);
  v5 = BfeDeviceIoControl(gBfeDriverControlComponent, 0x12404Cu, v4, InputBuffer, 0, 0, 0, 0);
  v3 = v5;
  if ( v5 )
  {
    MicrosoftTelemetryAssertTriggeredArgs("bfe.dll", (unsigned int)v5, 0);
LABEL_4:
    WfpReportError(v3, "BfeDriverSetEngineSecurityDescriptor");
  }
  return v3;
}

```

## disassembly

```asm
0x180056a24  mov     [rsp+arg_0], rbx
0x180056a29  push    rdi
0x180056a2a  sub     rsp, 40h
0x180056a2e  mov     rdi, rcx
0x180056a31  call    cs:__imp_RtlLengthSecurityDescriptor
0x180056a37  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180056a3e  mov     r9, rdi; InputBuffer
0x180056a41  mov     [rsp+48h+var_10], 0; __int64
0x180056a4a  mov     r8d, eax; InputBufferLength
0x180056a4d  mov     [rsp+48h+var_18], 0; __int64
0x180056a56  mov     edx, 124048h; IoControlCode
0x180056a5b  mov     [rsp+48h+var_20], 0; PVOID
0x180056a64  mov     [rsp+48h+var_28], 0; ULONG
0x180056a6c  call    BfeDeviceIoControl
0x180056a71  mov     rbx, rax
0x180056a74  test    rax, rax
0x180056a77  jnz     short loc_180056AC5
0x180056a79  mov     rcx, rdi; SecurityDescriptor
0x180056a7c  call    cs:__imp_RtlLengthSecurityDescriptor
0x180056a82  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180056a89  mov     r9, rdi; InputBuffer
0x180056a8c  mov     [rsp+48h+var_10], rbx; __int64
0x180056a91  mov     r8d, eax; InputBufferLength
0x180056a94  mov     [rsp+48h+var_18], rbx; __int64
0x180056a99  mov     edx, 12404Ch; IoControlCode
0x180056a9e  mov     [rsp+48h+var_20], rbx; PVOID
0x180056aa3  mov     [rsp+48h+var_28], ebx; ULONG
0x180056aa7  call    BfeDeviceIoControl
0x180056aac  mov     rbx, rax
0x180056aaf  test    rax, rax
0x180056ab2  jz      short loc_180056AD4
0x180056ab4  mov     edx, eax
0x180056ab6  lea     rcx, aBfeDll_0; "bfe.dll"
0x180056abd  xor     r8d, r8d
0x180056ac0  call    MicrosoftTelemetryAssertTriggeredArgs
0x180056ac5  lea     rdx, aBfedriverseten_0; "BfeDriverSetEngineSecurityDescriptor"
0x180056acc  mov     rcx, rbx
0x180056acf  call    WfpReportError
0x180056ad4  mov     rax, rbx
0x180056ad7  mov     rbx, [rsp+48h+arg_0]
0x180056adc  add     rsp, 40h
0x180056ae0  pop     rdi
0x180056ae1  retn
```
