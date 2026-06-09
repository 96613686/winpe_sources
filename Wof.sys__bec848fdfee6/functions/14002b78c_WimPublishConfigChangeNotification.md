# WimPublishConfigChangeNotification

- ea: `0x14002b78c`
- end: `0x14002b7c5`
- name: `WimPublishConfigChangeNotification`
- size: `57`
- prototype: `__int64 (__fastcall *())(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14002ad78`
- `0x14002badc`

## callees

- `0x140011640`
- `0x14002b78c`

## pseudocode

```c
__int64 (__fastcall *WimPublishConfigChangeNotification())(_QWORD, _QWORD, _QWORD)
{
  __int64 (__fastcall *result)(_QWORD, _QWORD, _QWORD); // rax

  result = ZwUpdateWnfStateDataWrapper;
  if ( ZwUpdateWnfStateDataWrapper )
    return (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ZwUpdateWnfStateDataWrapper(
                                                             &WNF_WOF_OVERLAY_CONFIGURATION_CHANGE,
                                                             0,
                                                             0);
  return result;
}

```

## disassembly

```asm
0x14002b78c  sub     rsp, 48h
0x14002b790  mov     rax, cs:ZwUpdateWnfStateDataWrapper
0x14002b797  xor     ecx, ecx
0x14002b799  test    rax, rax
0x14002b79c  jz      short loc_14002B7BF
0x14002b79e  mov     [rsp+48h+var_18], ecx
0x14002b7a2  xor     r9d, r9d
0x14002b7a5  mov     [rsp+48h+var_20], ecx
0x14002b7a9  xor     r8d, r8d
0x14002b7ac  mov     [rsp+48h+var_28], rcx
0x14002b7b1  xor     edx, edx
0x14002b7b3  lea     rcx, WNF_WOF_OVERLAY_CONFIGURATION_CHANGE
0x14002b7ba  call    _guard_dispatch_icall
0x14002b7bf  add     rsp, 48h
0x14002b7c3  retn
```
