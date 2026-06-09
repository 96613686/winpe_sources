# CompileHealth(int)

- ea: `0x140002db4`
- end: `0x140002e45`
- name: `?CompileHealth@@YAHH@Z`
- size: `145`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x140003234`

## callees

- `0x140002db4`
- `0x140002e4c`
- `0x140003518`
- `0x14000353c`
- `0x1400035c0`

## pseudocode

```c
__int64 __fastcall CompileHealth(int a1)
{
  __int64 v2; // rdx
  unsigned int Health; // edi
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  unsigned int v9; // [rsp+38h] [rbp+10h] BYREF

  v9 = 0;
  Health = CompileHealth_GetHealth(&v9);
  if ( Health )
  {
    v4 = v9;
    guiStorageSpacesState = v9;
    McGenEventRegister_EventRegister(SpaceAgent, v2, SpaceAgent_Context, SpaceAgent_Context);
    if ( a1 )
    {
      if ( (Microsoft_Windows_StorageSpaces_ManagementAgentEnableBits & 1) != 0 )
      {
        v7 = v4;
LABEL_7:
        McTemplateU0q_EventWriteTransfer(v6, v5, v7);
      }
    }
    else if ( (Microsoft_Windows_StorageSpaces_ManagementAgentEnableBits & 1) != 0 )
    {
      v7 = v4 + 5000;
      goto LABEL_7;
    }
    McGenEventUnregister_EventUnregister(SpaceAgent_Context);
  }
  return Health;
}

```

## disassembly

```asm
0x140002db4  mov     rax, rsp
0x140002db7  mov     [rax+8], rbx
0x140002dbb  mov     [rax+18h], rsi
0x140002dbf  push    rdi
0x140002dc0  sub     rsp, 20h
0x140002dc4  mov     esi, ecx
0x140002dc6  mov     dword ptr [rax+10h], 0
0x140002dcd  lea     rcx, [rax+10h]
0x140002dd1  call    CompileHealth_GetHealth
0x140002dd6  mov     edi, eax
0x140002dd8  test    eax, eax
0x140002dda  jz      short loc_140002E33
0x140002ddc  mov     ebx, [rsp+28h+arg_8]
0x140002de0  lea     r9, SpaceAgent_Context
0x140002de7  lea     r8, SpaceAgent_Context
0x140002dee  mov     cs:?guiStorageSpacesState@@3IA, ebx; uint guiStorageSpacesState
0x140002df4  lea     rcx, SpaceAgent
0x140002dfb  call    McGenEventRegister_EventRegister
0x140002e00  test    esi, esi
0x140002e02  jz      short loc_140002E12
0x140002e04  test    cs:Microsoft_Windows_StorageSpaces_ManagementAgentEnableBits, 1
0x140002e0b  jz      short loc_140002E27
0x140002e0d  mov     r8d, ebx
0x140002e10  jmp     short loc_140002E22
0x140002e12  test    cs:Microsoft_Windows_StorageSpaces_ManagementAgentEnableBits, 1
0x140002e19  jz      short loc_140002E27
0x140002e1b  lea     r8d, [rbx+1388h]
0x140002e22  call    McTemplateU0q_EventWriteTransfer
0x140002e27  lea     rcx, SpaceAgent_Context
0x140002e2e  call    McGenEventUnregister_EventUnregister
0x140002e33  mov     rbx, [rsp+28h+arg_0]
0x140002e38  mov     eax, edi
0x140002e3a  mov     rsi, [rsp+28h+arg_10]
0x140002e3f  add     rsp, 20h
0x140002e43  pop     rdi
0x140002e44  retn
```
