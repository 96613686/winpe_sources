# NcbCCResetDeleteEventHelper

- ea: `0x180020820`
- end: `0x18002086e`
- name: `NcbCCResetDeleteEventHelper`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180021050`

## callees

- `0x18000a0a0`
- `0x180020820`

## import_xrefs

- `BrokerLib!BrRemoveBrokeredEvent` at `0x18002083b`
- `BrokerLib!BrRemoveBrokeredEvent` at `0x18002083b`

## string_xrefs

- `0x18002084f`: `NcbCCResetDeleteEventHelper: BrRemoveBrokeredEvent finished.`

## pseudocode

```c
__int64 __fastcall NcbCCResetDeleteEventHelper(__int128 *a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  v8 = *a1;
  v3 = ((__int64 (__fastcall *)(__int64, __int64, __int64, __int128 *))BrRemoveBrokeredEvent)(
         g_NcbCCResetBroker,
         a2,
         a3,
         &v8);
  v6 = v3;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v5, v4, L"NcbCCResetDeleteEventHelper: BrRemoveBrokeredEvent finished.", v3);
  if ( v6 == 5 )
    return 87;
  return v6;
}

```

## disassembly

```asm
0x180020820  push    rbx
0x180020822  sub     rsp, 30h
0x180020826  movups  xmm0, xmmword ptr [rcx]
0x180020829  mov     rcx, cs:g_NcbCCResetBroker
0x180020830  lea     r9, [rsp+38h+var_18]
0x180020835  movdqu  [rsp+38h+var_18], xmm0
0x18002083b  call    cs:__imp_BrRemoveBrokeredEvent
0x180020841  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020848  mov     ebx, eax
0x18002084a  jz      short loc_18002085B
0x18002084c  mov     r9d, eax
0x18002084f  lea     r8, aNcbccresetdele; "NcbCCResetDeleteEventHelper: BrRemoveBr"...
0x180020856  call    McTemplateU0zq_EventWriteTransfer
0x18002085b  mov     eax, 57h ; 'W'
0x180020860  cmp     ebx, 5
0x180020863  cmovz   ebx, eax
0x180020866  mov     eax, ebx
0x180020868  add     rsp, 30h
0x18002086c  pop     rbx
0x18002086d  retn
```
