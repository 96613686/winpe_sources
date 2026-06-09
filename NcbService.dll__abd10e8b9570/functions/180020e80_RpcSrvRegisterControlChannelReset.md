# RpcSrvRegisterControlChannelReset

- ea: `0x180020e80`
- end: `0x180021040`
- name: `RpcSrvRegisterControlChannelReset`
- size: `448`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180003ed0`
- `0x180009740`
- `0x18000a0a0`
- `0x180020914`
- `0x180020e80`

## import_xrefs

- `BrokerLib!BrDeleteBrokeredEvent` at `0x180020ff4`
- `BrokerLib!BrDeleteBrokeredEvent` at `0x180020ff4`
- `BrokerLib!BrRegisterBrokeredEvent` at `0x180020f78`
- `BrokerLib!BrRegisterBrokeredEvent` at `0x180020f78`
- `BrokerLib!BrLockBroker` at `0x180020f50`
- `BrokerLib!BrLockBroker` at `0x180020f50`
- `BrokerLib!BrUnlockBroker` at `0x180020f89`
- `BrokerLib!BrUnlockBroker` at `0x180020f89`
- `BrokerLib!BrCreateBrokeredEvent` at `0x180020f37`
- `BrokerLib!BrCreateBrokeredEvent` at `0x180020f37`

## string_xrefs

- `0x18002101a`: `RegisterCCR: Completed.`

## pseudocode

```c
__int64 __fastcall RpcSrvRegisterControlChannelReset(__int64 a1, _OWORD *a2)
{
  unsigned int ProcessInformation; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  LPVOID lpMem[3]; // [rsp+40h] [rbp-18h] BYREF
  __int64 v17; // [rsp+70h] [rbp+18h] BYREF
  LPVOID v18; // [rsp+78h] [rbp+20h] BYREF

  lpMem[0] = 0;
  v18 = 0;
  v17 = 0;
  ProcessInformation = NcbCCResetGetProcessInformation(lpMem, &v18);
  v6 = ProcessInformation;
  if ( ProcessInformation )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_19;
    McTemplateU0zq_EventWriteTransfer(v5, v4, L"RegisterCCR: Failed to get process info", ProcessInformation);
  }
  else
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(v5, v4, L"Registering event for package:");
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v10, v9, v18);
    }
    v6 = BrCreateBrokeredEvent(g_NcbCCResetBroker, v18, lpMem[0], 3624, 0, 0, &v17);
    if ( !v6 )
    {
      v6 = BrLockBroker(g_NcbCCResetBroker, 0);
      if ( v6
        || (v6 = BrRegisterBrokeredEvent(g_NcbCCResetBroker, v17, 0, 1, 0), BrUnlockBroker(g_NcbCCResetBroker, 0), v6) )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v12, v11, L"RegisterCCR: Failed to register event", v6);
        BrDeleteBrokeredEvent(g_NcbCCResetBroker, v17);
      }
      else
      {
        *a2 = *(_OWORD *)v17;
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        {
          McTemplateU0z_EventWriteTransfer(v12, v11, L"Successfully registered app:");
          if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
            McTemplateU0z_EventWriteTransfer(v14, v13, *(_QWORD *)(v17 + 24));
        }
      }
    }
    VpnFree(lpMem[0]);
    VpnFree(v18);
  }
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v8, v7, L"RegisterCCR: Completed.", v6);
LABEL_19:
  if ( (int)v6 > 0 )
    return (unsigned __int16)v6 | 0x80070000;
  return v6;
}

```

## disassembly

```asm
0x180020e80  mov     rax, rsp
0x180020e83  mov     [rax+8], rbx
0x180020e87  push    rsi
0x180020e88  sub     rsp, 50h
0x180020e8c  mov     rsi, rdx
0x180020e8f  mov     qword ptr [rax-18h], 0
0x180020e97  lea     rdx, [rax+20h]
0x180020e9b  mov     qword ptr [rax+20h], 0
0x180020ea3  lea     rcx, [rax-18h]
0x180020ea7  mov     qword ptr [rax+18h], 0
0x180020eaf  call    NcbCCResetGetProcessInformation
0x180020eb4  mov     ebx, eax
0x180020eb6  test    eax, eax
0x180020eb8  jz      short loc_180020EDB
0x180020eba  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020ec1  jz      loc_180021026
0x180020ec7  mov     r9d, eax
0x180020eca  lea     r8, aRegisterccrFai_0; "RegisterCCR: Failed to get process info"
0x180020ed1  call    McTemplateU0zq_EventWriteTransfer
0x180020ed6  jmp     loc_18002100E
0x180020edb  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020ee1  test    al, 1
0x180020ee3  jz      short loc_180020F05
0x180020ee5  lea     r8, aRegisteringEve; "Registering event for package:"
0x180020eec  call    McTemplateU0z_EventWriteTransfer
0x180020ef1  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020ef7  test    al, 1
0x180020ef9  jz      short loc_180020F05
0x180020efb  mov     r8, [rsp+58h+arg_18]
0x180020f00  call    McTemplateU0z_EventWriteTransfer
0x180020f05  mov     r8, [rsp+58h+lpMem]
0x180020f0a  lea     rax, [rsp+58h+arg_10]
0x180020f0f  mov     rdx, [rsp+58h+arg_18]
0x180020f14  mov     r9d, 0E28h
0x180020f1a  mov     rcx, cs:g_NcbCCResetBroker
0x180020f21  mov     [rsp+58h+var_28], rax
0x180020f26  mov     [rsp+58h+var_30], 0
0x180020f2f  mov     dword ptr [rsp+58h+var_38], 0
0x180020f37  call    cs:__imp_BrCreateBrokeredEvent
0x180020f3d  mov     ebx, eax
0x180020f3f  test    eax, eax
0x180020f41  jnz     loc_180020FFA
0x180020f47  mov     rcx, cs:g_NcbCCResetBroker
0x180020f4e  xor     edx, edx
0x180020f50  call    cs:__imp_BrLockBroker
0x180020f56  mov     ebx, eax
0x180020f58  test    eax, eax
0x180020f5a  jnz     short loc_180020FD0
0x180020f5c  mov     rdx, [rsp+58h+arg_10]
0x180020f61  lea     r9d, [rax+1]
0x180020f65  mov     rcx, cs:g_NcbCCResetBroker
0x180020f6c  xor     r8d, r8d
0x180020f6f  mov     [rsp+58h+var_38], 0
0x180020f78  call    cs:__imp_BrRegisterBrokeredEvent
0x180020f7e  mov     rcx, cs:g_NcbCCResetBroker
0x180020f85  xor     edx, edx
0x180020f87  mov     ebx, eax
0x180020f89  call    cs:__imp_BrUnlockBroker
0x180020f8f  test    ebx, ebx
0x180020f91  jnz     short loc_180020FD0
0x180020f93  mov     r8, [rsp+58h+arg_10]
0x180020f98  movups  xmm0, xmmword ptr [r8]
0x180020f9c  movdqu  xmmword ptr [rsi], xmm0
0x180020fa0  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020fa6  test    al, 1
0x180020fa8  jz      short loc_180020FFA
0x180020faa  lea     r8, aSuccessfullyRe; "Successfully registered app:"
0x180020fb1  call    McTemplateU0z_EventWriteTransfer
0x180020fb6  mov     eax, cs:Microsoft_Windows_Network_Connection_BrokerEnableBits
0x180020fbc  mov     r8, [rsp+58h+arg_10]
0x180020fc1  test    al, 1
0x180020fc3  jz      short loc_180020FFA
0x180020fc5  mov     r8, [r8+18h]
0x180020fc9  call    McTemplateU0z_EventWriteTransfer
0x180020fce  jmp     short loc_180020FFA
0x180020fd0  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180020fd7  jz      short loc_180020FE8
0x180020fd9  mov     r9d, ebx
0x180020fdc  lea     r8, aRegisterccrFai; "RegisterCCR: Failed to register event"
0x180020fe3  call    McTemplateU0zq_EventWriteTransfer
0x180020fe8  mov     rdx, [rsp+58h+arg_10]
0x180020fed  mov     rcx, cs:g_NcbCCResetBroker
0x180020ff4  call    cs:__imp_BrDeleteBrokeredEvent
0x180020ffa  mov     rcx, [rsp+58h+lpMem]; lpMem
0x180020fff  call    VpnFree
0x180021004  mov     rcx, [rsp+58h+arg_18]; lpMem
0x180021009  call    VpnFree
0x18002100e  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180021015  jz      short loc_180021026
0x180021017  mov     r9d, ebx
0x18002101a  lea     r8, aRegisterccrCom; "RegisterCCR: Completed."
0x180021021  call    McTemplateU0zq_EventWriteTransfer
0x180021026  test    ebx, ebx
0x180021028  jle     short loc_180021033
0x18002102a  movzx   ebx, bx
0x18002102d  or      ebx, 80070000h
0x180021033  mov     eax, ebx
0x180021035  mov     rbx, [rsp+58h+arg_0]
0x18002103a  add     rsp, 50h
0x18002103e  pop     rsi
0x18002103f  retn
```
