# WerStartSystemErrorHandler

- ea: `0x140059210`
- end: `0x140059348`
- name: `WerStartSystemErrorHandler`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x140058c20`

## callees

- `0x140059210`
- `0x140059970`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x1400592b5`
- `ntoskrnl!EtwRegister` at `0x1400592b5`
- `ntoskrnl!EtwUnregister` at `0x140059311`
- `ntoskrnl!EtwUnregister` at `0x140059311`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140059294`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x140059294`
- `ntoskrnl!EtwEventEnabled` at `0x1400592d4`
- `ntoskrnl!EtwEventEnabled` at `0x1400592d4`
- `ntoskrnl!ZwQueryWnfStateNameInformation` at `0x140059263`
- `ntoskrnl!ZwQueryWnfStateNameInformation` at `0x140059263`
- `ntoskrnl!EtwWrite` at `0x1400592fb`
- `ntoskrnl!EtwWrite` at `0x1400592fb`

## pseudocode

```c
__int64 WerStartSystemErrorHandler()
{
  int v0; // ebx
  __int64 result; // rax
  int v2; // [rsp+40h] [rbp-30h] BYREF
  ULONGLONG RegHandle; // [rsp+48h] [rbp-28h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-20h] BYREF

  RegHandle = 0;
  v0 = 0;
  v2 = 0;
  EventDescriptor = 0;
  if ( (int)ZwQueryWnfStateNameInformation(&WNF_WER_SERVICE_START, 1, 0, &v2, 4) >= 0 && v2 )
    v0 = (int)ZwUpdateWnfStateData(&WNF_WER_SERVICE_START, 0, 0, 0, 0, 0, 0) >= 0;
  if ( EtwRegister(&ProviderId, 0, 0, &RegHandle) >= 0 )
  {
    EventDescriptor = 0;
    if ( EtwEventEnabled(RegHandle, &EventDescriptor) && EtwWrite(RegHandle, &EventDescriptor, 0, 0, 0) >= 0 )
      ++v0;
    EtwUnregister(RegHandle);
  }
  result = 0;
  if ( !v0 )
    return 3221225600LL;
  return result;
}

```

## disassembly

```asm
0x140059210  mov     [rsp-8+arg_0], rbx
0x140059215  mov     [rsp-8+arg_8], rsi
0x14005921a  push    rbp
0x14005921b  mov     rbp, rsp
0x14005921e  sub     rsp, 70h
0x140059222  mov     rax, cs:__security_cookie
0x140059229  xor     rax, rsp
0x14005922c  mov     [rbp+var_10], rax
0x140059230  xorps   xmm0, xmm0
0x140059233  mov     [rbp+RegHandle], 0
0x14005923b  xor     ebx, ebx
0x14005923d  mov     [rbp+var_30], 0
0x140059244  lea     r9, [rbp+var_30]
0x140059248  mov     dword ptr [rsp+70h+UserData], 4
0x140059250  xor     r8d, r8d
0x140059253  lea     rcx, WNF_WER_SERVICE_START
0x14005925a  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x14005925e  lea     esi, [rbx+1]
0x140059261  mov     edx, esi
0x140059263  call    cs:__imp_ZwQueryWnfStateNameInformation
0x14005926a  nop     dword ptr [rax+rax+00h]
0x14005926f  test    eax, eax
0x140059271  js      short loc_1400592A5
0x140059273  cmp     [rbp+var_30], ebx
0x140059276  jz      short loc_1400592A5
0x140059278  mov     [rsp+70h+var_40], ebx
0x14005927c  lea     rcx, WNF_WER_SERVICE_START
0x140059283  mov     [rsp+70h+var_48], ebx
0x140059287  xor     r9d, r9d
0x14005928a  xor     r8d, r8d
0x14005928d  mov     [rsp+70h+UserData], rbx
0x140059292  xor     edx, edx
0x140059294  call    cs:__imp_ZwUpdateWnfStateData
0x14005929b  nop     dword ptr [rax+rax+00h]
0x1400592a0  test    eax, eax
0x1400592a2  cmovns  ebx, esi
0x1400592a5  lea     r9, [rbp+RegHandle]; RegHandle
0x1400592a9  xor     r8d, r8d; CallbackContext
0x1400592ac  xor     edx, edx; EnableCallback
0x1400592ae  lea     rcx, ProviderId; ProviderId
0x1400592b5  call    cs:__imp_EtwRegister
0x1400592bc  nop     dword ptr [rax+rax+00h]
0x1400592c1  test    eax, eax
0x1400592c3  js      short loc_14005931D
0x1400592c5  mov     rcx, [rbp+RegHandle]; RegHandle
0x1400592c9  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x1400592cd  xorps   xmm0, xmm0
0x1400592d0  movups  xmmword ptr [rbp+EventDescriptor.Id], xmm0
0x1400592d4  call    cs:__imp_EtwEventEnabled
0x1400592db  nop     dword ptr [rax+rax+00h]
0x1400592e0  test    al, al
0x1400592e2  jz      short loc_14005930D
0x1400592e4  mov     rcx, [rbp+RegHandle]; RegHandle
0x1400592e8  lea     rdx, [rbp+EventDescriptor]; EventDescriptor
0x1400592ec  xor     r9d, r9d; UserDataCount
0x1400592ef  mov     [rsp+70h+UserData], 0; UserData
0x1400592f8  xor     r8d, r8d; ActivityId
0x1400592fb  call    cs:__imp_EtwWrite
0x140059302  nop     dword ptr [rax+rax+00h]
0x140059307  test    eax, eax
0x140059309  js      short loc_14005930D
0x14005930b  add     ebx, esi
0x14005930d  mov     rcx, [rbp+RegHandle]; RegHandle
0x140059311  call    cs:__imp_EtwUnregister
0x140059318  nop     dword ptr [rax+rax+00h]
0x14005931d  xor     eax, eax
0x14005931f  mov     ecx, 0C0000080h
0x140059324  test    ebx, ebx
0x140059326  cmovz   eax, ecx
0x140059329  mov     rcx, [rbp+var_10]
0x14005932d  xor     rcx, rsp; StackCookie
0x140059330  call    __security_check_cookie
0x140059335  lea     r11, [rsp+70h+var_s0]
0x14005933a  mov     rbx, [r11+10h]
0x14005933e  mov     rsi, [r11+18h]
0x140059342  mov     rsp, r11
0x140059345  pop     rbp
0x140059346  retn
```
