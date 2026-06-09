# LogDeviceStatus

- ea: `0x140021274`
- end: `0x140021386`
- name: `LogDeviceStatus`
- size: `274`
- prototype: `__int64 __fastcall(DEVINST dnDevInst)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140016de0`
- `0x140019278`

## callees

- `0x140021274`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1400212bc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x1400212bc`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002130a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x14002130a`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002134f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140021370`
- `DEVRTL!DevRtlWriteTextLog` at `0x14002134f`
- `DEVRTL!DevRtlWriteTextLog` at `0x140021370`

## pseudocode

```c
__int64 __fastcall LogDeviceStatus(DEVINST dnDevInst, __int64 a2)
{
  CONFIGRET DevNode_Status; // eax
  const char *v5; // r9
  __int64 v6; // r8
  int v7; // eax
  ULONG pulStatus; // [rsp+40h] [rbp-10h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+44h] [rbp-Ch] BYREF
  ULONG pulProblemNumber; // [rsp+48h] [rbp-8h] BYREF
  ULONG PropertyBufferSize; // [rsp+70h] [rbp+20h] BYREF
  int PropertyBuffer; // [rsp+78h] [rbp+28h] BYREF

  pulStatus = 0;
  pulProblemNumber = 0;
  PropertyBuffer = 0;
  PropertyBufferSize = 0;
  PropertyType = 0;
  DevNode_Status = CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst, 0);
  if ( DevNode_Status )
  {
    v5 = "Unable to get device status after wait. cr = 0x%02X";
    v6 = 2;
    return DevRtlWriteTextLog(a2, 1, v6, v5, DevNode_Status);
  }
  DevNode_Status = pulStatus;
  if ( (pulStatus & 0x400) == 0 )
  {
    v5 = "Device Status: 0x%08X";
    v6 = 4;
    return DevRtlWriteTextLog(a2, 1, v6, v5, DevNode_Status);
  }
  PropertyBufferSize = 4;
  if ( !CM_Get_DevNode_PropertyW(
          dnDevInst,
          &DEVPKEY_Device_ProblemStatus,
          &PropertyType,
          (PBYTE)&PropertyBuffer,
          &PropertyBufferSize,
          0)
    && PropertyType == 24
    && PropertyBufferSize == 4 )
  {
    v7 = PropertyBuffer;
  }
  else
  {
    v7 = 0;
    PropertyBuffer = 0;
  }
  return DevRtlWriteTextLog(a2, 1, 4, "Device Status: 0x%08X [0x%02X - 0x%08X]", pulStatus, pulProblemNumber, v7);
}

```

## disassembly

```asm
0x140021274  mov     [rsp-8+arg_0], rbx
0x140021279  mov     [rsp-8+arg_8], rdi
0x14002127e  push    rbp
0x14002127f  mov     rbp, rsp
0x140021282  sub     rsp, 50h
0x140021286  mov     rbx, rdx
0x140021289  mov     [rbp+pulStatus], 0
0x140021290  mov     edi, ecx
0x140021292  mov     [rbp+pulProblemNumber], 0
0x140021299  mov     r8d, ecx; dnDevInst
0x14002129c  mov     [rbp+PropertyBuffer], 0
0x1400212a3  lea     rdx, [rbp+pulProblemNumber]; pulProblemNumber
0x1400212a7  mov     [rbp+arg_10], 0
0x1400212ae  lea     rcx, [rbp+pulStatus]; pulStatus
0x1400212b2  mov     [rbp+PropertyType], 0
0x1400212b9  xor     r9d, r9d; ulFlags
0x1400212bc  call    cs:__imp_CM_Get_DevNode_Status
0x1400212c2  test    eax, eax
0x1400212c4  jz      short loc_1400212D8
0x1400212c6  lea     r9, aUnableToGetDev_0; "Unable to get device status after wait."...
0x1400212cd  mov     r8d, 2
0x1400212d3  jmp     loc_140021364
0x1400212d8  mov     eax, [rbp+pulStatus]
0x1400212db  bt      eax, 0Ah
0x1400212df  jnb     short loc_140021357
0x1400212e1  lea     rax, [rbp+arg_10]
0x1400212e5  mov     [rsp+50h+ulFlags], 0; ulFlags
0x1400212ed  lea     r9, [rbp+PropertyBuffer]; PropertyBuffer
0x1400212f1  mov     [rsp+50h+PropertyBufferSize], rax; PropertyBufferSize
0x1400212f6  lea     r8, [rbp+PropertyType]; PropertyType
0x1400212fa  mov     [rbp+arg_10], 4
0x140021301  lea     rdx, DEVPKEY_Device_ProblemStatus; PropertyKey
0x140021308  mov     ecx, edi; dnDevInst
0x14002130a  call    cs:__imp_CM_Get_DevNode_PropertyW
0x140021310  test    eax, eax
0x140021312  jnz     short loc_140021325
0x140021314  cmp     [rbp+PropertyType], 18h
0x140021318  jnz     short loc_140021325
0x14002131a  cmp     [rbp+arg_10], 4
0x14002131e  jnz     short loc_140021325
0x140021320  mov     eax, [rbp+PropertyBuffer]
0x140021323  jmp     short loc_14002132A
0x140021325  xor     eax, eax
0x140021327  mov     [rbp+PropertyBuffer], eax
0x14002132a  mov     [rsp+50h+var_20], eax
0x14002132e  lea     r9, aDeviceStatus0x; "Device Status: 0x%08X [0x%02X - 0x%08X]"
0x140021335  mov     eax, [rbp+pulProblemNumber]
0x140021338  mov     edx, 1
0x14002133d  mov     [rsp+50h+ulFlags], eax
0x140021341  mov     rcx, rbx
0x140021344  mov     eax, [rbp+pulStatus]
0x140021347  mov     dword ptr [rsp+50h+PropertyBufferSize], eax
0x14002134b  lea     r8d, [rdx+3]
0x14002134f  call    cs:__imp_DevRtlWriteTextLog
0x140021355  jmp     short loc_140021376
0x140021357  lea     r9, aDeviceStatus0x_0; "Device Status: 0x%08X"
0x14002135e  mov     r8d, 4
0x140021364  mov     edx, 1
0x140021369  mov     dword ptr [rsp+50h+PropertyBufferSize], eax
0x14002136d  mov     rcx, rbx
0x140021370  call    cs:__imp_DevRtlWriteTextLog
0x140021376  mov     rbx, [rsp+50h+arg_0]
0x14002137b  mov     rdi, [rsp+50h+arg_8]
0x140021380  add     rsp, 50h
0x140021384  pop     rbp
0x140021385  retn
```
