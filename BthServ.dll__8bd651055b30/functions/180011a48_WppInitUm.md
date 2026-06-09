# WppInitUm

- ea: `0x180011a48`
- end: `0x180011b0d`
- name: `WppInitUm`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callers

- `0x180010f04`

## callees

- `0x180011a48`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180011ada`
- `ntdll!RtlInitUnicodeString` at `0x180011ada`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180011ab8`
- `ntdll!EtwRegisterTraceGuidsW` at `0x180011ab8`
- `WppRecorderUM!WppAutoLogStart` at `0x180011aee`
- `WppRecorderUM!WppAutoLogStart` at `0x180011aee`

## string_xrefs

- `0x180011ac9`: `Bluetooth Support Service`

## pseudocode

```c
__int64 *WppInitUm()
{
  _QWORD *v0; // rbx
  __int64 *v1; // rdi
  __int64 v2; // r8
  __int64 *result; // rax
  __int128 v4; // [rsp+40h] [rbp-28h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v0 = WPP_GLOBAL_Control;
  v1 = &WPP_REGISTRATION_GUIDS;
  v4 = 0;
  while ( v0 )
  {
    v2 = *v1;
    v4 = (unsigned __int64)*v1++;
    v0[4] = v2;
    ((void (__fastcall *)(__int64 (__fastcall *)(), _QWORD *, __int64, __int64, __int128 *, _QWORD, _QWORD, _QWORD *))EtwRegisterTraceGuidsW)(
      WppControlCallback,
      v0,
      v2,
      1,
      &v4,
      0,
      0,
      v0 + 1);
    v0 = (_QWORD *)*v0;
  }
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"Bluetooth Support Service");
  WppAutoLogStart(WPP_GLOBAL_Control, 0, &DestinationString);
  result = &WPP_MAIN_CB;
  WPP_RECORDER_INITIALIZED = &WPP_MAIN_CB;
  return result;
}

```

## disassembly

```asm
0x180011a48  mov     [rsp+arg_0], rbx
0x180011a4d  push    rdi
0x180011a4e  sub     rsp, 60h
0x180011a52  mov     rbx, cs:WPP_GLOBAL_Control
0x180011a59  lea     rdi, WPP_REGISTRATION_GUIDS
0x180011a60  xorps   xmm0, xmm0
0x180011a63  movups  [rsp+68h+var_28], xmm0
0x180011a68  jmp     short loc_180011AC1
0x180011a6a  mov     r8, [rdi]
0x180011a6d  lea     rax, [rbx+8]
0x180011a71  mov     [rsp+68h+var_30], rax
0x180011a76  lea     rcx, WppControlCallback
0x180011a7d  mov     [rsp+68h+var_38], 0
0x180011a86  lea     rax, [rsp+68h+var_28]
0x180011a8b  mov     qword ptr [rsp+68h+var_28], r8
0x180011a90  lea     rdi, [rdi+8]
0x180011a94  mov     qword ptr [rsp+68h+var_28+8], 0
0x180011a9d  mov     r9d, 1
0x180011aa3  mov     [rsp+68h+var_40], 0
0x180011aac  mov     rdx, rbx
0x180011aaf  mov     [rsp+68h+var_48], rax
0x180011ab4  mov     [rbx+20h], r8
0x180011ab8  call    cs:__imp_EtwRegisterTraceGuidsW
0x180011abe  mov     rbx, [rbx]
0x180011ac1  test    rbx, rbx
0x180011ac4  jnz     short loc_180011A6A
0x180011ac6  xorps   xmm0, xmm0
0x180011ac9  lea     rdx, SourceString; "Bluetooth Support Service"
0x180011ad0  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180011ad5  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x180011ada  call    cs:__imp_RtlInitUnicodeString
0x180011ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ae7  lea     r8, [rsp+68h+DestinationString]
0x180011aec  xor     edx, edx
0x180011aee  call    cs:__imp_WppAutoLogStart
0x180011af4  mov     rbx, [rsp+68h+arg_0]
0x180011af9  lea     rax, WPP_MAIN_CB
0x180011b00  mov     cs:WPP_RECORDER_INITIALIZED, rax
0x180011b07  add     rsp, 60h
0x180011b0b  pop     rdi
0x180011b0c  retn
```
