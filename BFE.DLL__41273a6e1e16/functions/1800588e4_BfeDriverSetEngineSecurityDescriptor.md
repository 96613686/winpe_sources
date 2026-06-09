# BfeDriverSetEngineSecurityDescriptor

- ea: `0x1800588e4`
- end: `0x1800589af`
- name: `BfeDriverSetEngineSecurityDescriptor`
- size: `203`
- prototype: `__int64 __fastcall(PVOID InputBuffer)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031740`

## callees

- `0x1800197d0`
- `0x18002077c`
- `0x1800575a0`
- `0x1800588e4`

## import_xrefs

- `ntdll!RtlLengthSecurityDescriptor` at `0x1800588f1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180058942`
- `ntdll!RtlLengthSecurityDescriptor` at `0x1800588f1`
- `ntdll!RtlLengthSecurityDescriptor` at `0x180058942`

## string_xrefs

- `0x180058982`: `bfe.dll`
- `0x180058991`: `BfeDriverSetEngineSecurityDescriptor`

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
0x1800588e4  mov     [rsp+arg_0], rbx
0x1800588e9  push    rdi
0x1800588ea  sub     rsp, 40h
0x1800588ee  mov     rdi, rcx
0x1800588f1  call    cs:__imp_RtlLengthSecurityDescriptor
0x1800588f8  nop     dword ptr [rax+rax+00h]
0x1800588fd  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180058904  mov     r9, rdi; InputBuffer
0x180058907  mov     [rsp+48h+var_10], 0; __int64
0x180058910  mov     r8d, eax; InputBufferLength
0x180058913  mov     [rsp+48h+var_18], 0; __int64
0x18005891c  mov     edx, 124048h; IoControlCode
0x180058921  mov     [rsp+48h+var_20], 0; PVOID
0x18005892a  mov     [rsp+48h+var_28], 0; ULONG
0x180058932  call    BfeDeviceIoControl
0x180058937  mov     rbx, rax
0x18005893a  test    rax, rax
0x18005893d  jnz     short loc_180058991
0x18005893f  mov     rcx, rdi; SecurityDescriptor
0x180058942  call    cs:__imp_RtlLengthSecurityDescriptor
0x180058949  nop     dword ptr [rax+rax+00h]
0x18005894e  mov     rcx, cs:gBfeDriverControlComponent; FileHandle
0x180058955  mov     r9, rdi; InputBuffer
0x180058958  mov     [rsp+48h+var_10], rbx; __int64
0x18005895d  mov     r8d, eax; InputBufferLength
0x180058960  mov     [rsp+48h+var_18], rbx; __int64
0x180058965  mov     edx, 12404Ch; IoControlCode
0x18005896a  mov     [rsp+48h+var_20], rbx; PVOID
0x18005896f  mov     [rsp+48h+var_28], ebx; ULONG
0x180058973  call    BfeDeviceIoControl
0x180058978  mov     rbx, rax
0x18005897b  test    rax, rax
0x18005897e  jz      short loc_1800589A0
0x180058980  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "WFP_IS_SUCCESS(result)")
0x180058982  lea     rcx, aBfeDll_0; "bfe.dll"
0x180058989  xor     r8d, r8d
0x18005898c  call    MicrosoftTelemetryAssertTriggeredArgs
0x180058991  lea     rdx, aBfedriverseten_0; "BfeDriverSetEngineSecurityDescriptor"
0x180058998  mov     rcx, rbx
0x18005899b  call    WfpReportError
0x1800589a0  mov     rax, rbx
0x1800589a3  mov     rbx, [rsp+48h+arg_0]
0x1800589a8  add     rsp, 40h
0x1800589ac  pop     rdi
0x1800589ad  retn
```
