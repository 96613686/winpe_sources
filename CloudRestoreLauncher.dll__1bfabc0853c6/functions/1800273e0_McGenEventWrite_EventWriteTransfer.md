# McGenEventWrite_EventWriteTransfer

- ea: `0x1800273e0`
- end: `0x180027432`
- name: `McGenEventWrite_EventWriteTransfer`
- size: `82`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `42`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180027438`
- `0x180027500`
- `0x180038170`
- `0x18003fcd4`
- `0x180046134`
- `0x180046174`
- `0x1800461e4`
- `0x18004623c`
- `0x1800462bc`
- `0x180046624`
- `0x180072b6c`
- `0x18007ed70`
- `0x180081910`
- `0x1800974b0`
- `0x180097550`
- `0x1800975fc`
- `0x180097748`
- `0x1800977e8`
- `0x1800978a4`
- `0x18009e770`
- `0x1800a1e48`
- `0x1800a4288`
- `0x1800c3fdc`
- `0x1800c56e0`
- `0x1800c67ac`
- `0x1800c68bc`
- `0x1800c6a00`
- `0x1800c6b00`
- `0x1800d0a64`
- `0x1800d6a2c`
- `0x1800d6ac4`
- `0x1800e4e7c`
- `0x1800edffc`
- `0x1800fa8b4`
- `0x1800fe4cc`
- `0x180104710`
- `0x180104a30`
- `0x180105780`
- `0x18010e238`
- `0x18010e2e8`
- `0x18010e388`
- `0x18010ea00`

## callees

- `0x1800273e0`

## import_xrefs

- `ADVAPI32!EventWriteTransfer` at `0x180027427`
- `ADVAPI32!EventWriteTransfer` at `0x180027427`

## pseudocode

```c
ULONG __fastcall McGenEventWrite_EventWriteTransfer(
        __int64 a1,
        const EVENT_DESCRIPTOR *a2,
        __int64 a3,
        ULONG UserDataCount,
        PEVENT_DATA_DESCRIPTOR UserData)
{
  unsigned __int16 *v5; // rcx
  int v6; // r8d

  v5 = (unsigned __int16 *)qword_18017A048;
  if ( qword_18017A048 )
  {
    UserData->Ptr = qword_18017A048;
    v6 = 2;
    LODWORD(v5) = *v5;
  }
  else
  {
    UserData->Ptr = 0;
    v6 = 0;
  }
  UserData->Size = (unsigned int)v5;
  UserData->Reserved = v6;
  return EventWriteTransfer(Microsoft_Windows_CloudRestoreLauncher_Context, a2, 0, 0, UserDataCount, UserData);
}

```

## disassembly

```asm
0x1800273e0  sub     rsp, 38h
0x1800273e4  mov     rcx, cs:qword_18017A048
0x1800273eb  mov     rax, [rsp+38h+arg_20]
0x1800273f0  test    rcx, rcx
0x1800273f3  jnz     short loc_1800273FD
0x1800273f5  mov     [rax], rcx
0x1800273f8  xor     r8d, r8d
0x1800273fb  jmp     short loc_180027409
0x1800273fd  mov     [rax], rcx
0x180027400  mov     r8d, 2
0x180027406  movzx   ecx, word ptr [rcx]
0x180027409  mov     [rax+8], ecx
0x18002740c  mov     [rax+0Ch], r8d
0x180027410  xor     r8d, r8d; ActivityId
0x180027413  mov     rcx, cs:Microsoft_Windows_CloudRestoreLauncher_Context; RegHandle
0x18002741a  mov     [rsp+38h+UserData], rax; UserData
0x18002741f  mov     [rsp+38h+UserDataCount], r9d; UserDataCount
0x180027424  xor     r9d, r9d; RelatedActivityId
0x180027427  call    cs:__imp_EventWriteTransfer
0x18002742d  add     rsp, 38h
0x180027431  retn
```
