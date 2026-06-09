# LogDevNodeState

- ea: `0x140016de0`
- end: `0x140016edf`
- name: `LogDevNodeState`
- size: `255`
- prototype: `__int64 __fastcall(DEVINST dnDevInst)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140018dc0`

## callees

- `0x140016de0`
- `0x140021274`
- `0x140027124`
- `0x140045f30`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140016e8a`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_PropertyW` at `0x140016e8a`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016e57`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016eb8`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016e57`
- `DEVRTL!DevRtlWriteTextLog` at `0x140016eb8`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140016e19`
- `DEVRTL!DevRtlGetThreadLogToken` at `0x140016e19`

## string_xrefs

- `0x140016e40`: `Config Flags: 0x%08X`

## pseudocode

```c
CONFIGRET __fastcall LogDevNodeState(DEVINST dnDevInst)
{
  __int64 ThreadLogToken; // rbx
  CONFIGRET result; // eax
  int v4; // [rsp+30h] [rbp-1B8h] BYREF
  ULONG PropertyBufferSize; // [rsp+34h] [rbp-1B4h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+38h] [rbp-1B0h] BYREF
  BYTE PropertyBuffer[400]; // [rsp+40h] [rbp-1A8h] BYREF

  PropertyType = 0;
  PropertyBufferSize = 0;
  v4 = 0;
  ThreadLogToken = DevRtlGetThreadLogToken();
  LogDeviceStatus(dnDevInst);
  if ( (unsigned int)DevUtilsGetConfigFlags(dnDevInst, &v4) )
    DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Config Flags: 0x%08X", v4);
  PropertyBufferSize = 400;
  result = CM_Get_DevNode_PropertyW(
             dnDevInst,
             &DEVPKEY_Device_Parent,
             &PropertyType,
             PropertyBuffer,
             &PropertyBufferSize,
             0);
  if ( !result && PropertyType == 18 )
    return DevRtlWriteTextLog(ThreadLogToken, 1, 4, "Parent Device: %ws", PropertyBuffer);
  return result;
}

```

## disassembly

```asm
0x140016de0  mov     [rsp+arg_8], rbx
0x140016de5  push    rdi
0x140016de6  sub     rsp, 1E0h
0x140016ded  mov     rax, cs:__security_cookie
0x140016df4  xor     rax, rsp
0x140016df7  mov     [rsp+1E8h+var_18], rax
0x140016dff  mov     edi, ecx
0x140016e01  mov     [rsp+1E8h+PropertyType], 0
0x140016e09  mov     [rsp+1E8h+var_1B4], 0
0x140016e11  mov     [rsp+1E8h+var_1B8], 0
0x140016e19  call    cs:__imp_DevRtlGetThreadLogToken
0x140016e1f  mov     rdx, rax
0x140016e22  mov     ecx, edi; dnDevInst
0x140016e24  mov     rbx, rax
0x140016e27  call    LogDeviceStatus
0x140016e2c  lea     rdx, [rsp+1E8h+var_1B8]
0x140016e31  mov     ecx, edi
0x140016e33  call    DevUtilsGetConfigFlags
0x140016e38  test    eax, eax
0x140016e3a  jz      short loc_140016E5D
0x140016e3c  mov     ecx, [rsp+1E8h+var_1B8]
0x140016e40  lea     r9, aConfigFlags0x0; "Config Flags: 0x%08X"
0x140016e47  mov     edx, 1
0x140016e4c  mov     dword ptr [rsp+1E8h+PropertyBufferSize], ecx
0x140016e50  mov     rcx, rbx
0x140016e53  lea     r8d, [rdx+3]
0x140016e57  call    cs:__imp_DevRtlWriteTextLog
0x140016e5d  lea     rax, [rsp+1E8h+var_1B4]
0x140016e62  mov     [rsp+1E8h+ulFlags], 0; ulFlags
0x140016e6a  lea     r9, [rsp+1E8h+PropertyBuffer]; PropertyBuffer
0x140016e6f  mov     [rsp+1E8h+PropertyBufferSize], rax; PropertyBufferSize
0x140016e74  lea     r8, [rsp+1E8h+PropertyType]; PropertyType
0x140016e79  mov     [rsp+1E8h+var_1B4], 190h
0x140016e81  lea     rdx, DEVPKEY_Device_Parent; PropertyKey
0x140016e88  mov     ecx, edi; dnDevInst
0x140016e8a  call    cs:__imp_CM_Get_DevNode_PropertyW
0x140016e90  test    eax, eax
0x140016e92  jnz     short loc_140016EBE
0x140016e94  cmp     [rsp+1E8h+PropertyType], 12h
0x140016e99  jnz     short loc_140016EBE
0x140016e9b  mov     edx, 1
0x140016ea0  lea     rax, [rsp+1E8h+PropertyBuffer]
0x140016ea5  lea     r9, aParentDeviceWs; "Parent Device: %ws"
0x140016eac  mov     [rsp+1E8h+PropertyBufferSize], rax
0x140016eb1  mov     rcx, rbx
0x140016eb4  lea     r8d, [rdx+3]
0x140016eb8  call    cs:__imp_DevRtlWriteTextLog
0x140016ebe  mov     rcx, [rsp+1E8h+var_18]
0x140016ec6  xor     rcx, rsp; StackCookie
0x140016ec9  call    __security_check_cookie
0x140016ece  mov     rbx, [rsp+1E8h+arg_8]
0x140016ed6  add     rsp, 1E0h
0x140016edd  pop     rdi
0x140016ede  retn
```
