# CDeviceHandler::StopDiscovery(void)

- ea: `0x180008034`
- end: `0x18000814a`
- name: `?StopDiscovery@CDeviceHandler@@QEAAXXZ`
- size: `278`
- prototype: `void __fastcall(CDeviceHandler *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800033ec`
- `0x1800074f0`
- `0x1800079e0`
- `0x18000aa58`
- `0x180011dc0`

## callees

- `0x180008034`
- `0x18000a644`
- `0x18000baa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008143`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008078`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008078`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800080fc`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x1800080fc`

## pseudocode

```c
void __fastcall CDeviceHandler::StopDiscovery(CDeviceHandler *this)
{
  CNetworkHandler *v2; // rcx
  _QWORD *v3; // rcx

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( *((_DWORD *)this + 2) )
  {
    v2 = *(&Block + 1);
    if ( *(&Block + 1) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
        v2 = *(&Block + 1);
      }
      CNetworkHandler::LogNetworkSizes(v2);
      goto LABEL_13;
    }
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
LABEL_13:
    v3 = WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)this )
  {
    DevCloseObjectQuery(*(_QWORD *)this);
    *(_QWORD *)this = 0;
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x20) != 0 )
    WPP_SF_(v3[2], 37, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x180008034  mov     [rsp+arg_0], rbx
0x180008039  mov     [rsp+arg_8], rbp
0x18000803e  push    rdi
0x18000803f  sub     rsp, 20h
0x180008043  mov     rbx, rcx
0x180008046  mov     rcx, cs:WPP_GLOBAL_Control
0x18000804d  lea     rbp, WPP_GLOBAL_Control
0x180008054  cmp     rcx, rbp
0x180008057  jz      short loc_180008074
0x180008059  test    byte ptr [rcx+1Ch], 20h
0x18000805d  jz      short loc_180008074
0x18000805f  mov     rcx, [rcx+10h]
0x180008063  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x18000806a  mov     edx, 22h ; '"'
0x18000806f  call    WPP_SF_
0x180008074  lea     rcx, [rbx+10h]; lpCriticalSection
0x180008078  call    cs:__imp_EnterCriticalSection
0x18000807e  cmp     dword ptr [rbx+8], 0
0x180008082  jz      short loc_1800080C5
0x180008084  mov     rcx, qword ptr cs:Block+8
0x18000808b  test    rcx, rcx
0x18000808e  jz      short loc_1800080C5
0x180008090  mov     rax, cs:WPP_GLOBAL_Control
0x180008097  cmp     rax, rbp
0x18000809a  jz      short loc_1800080BE
0x18000809c  test    byte ptr [rax+1Ch], 8
0x1800080a0  jz      short loc_1800080BE
0x1800080a2  mov     rcx, [rax+10h]
0x1800080a6  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x1800080ad  mov     edx, 23h ; '#'
0x1800080b2  call    WPP_SF_
0x1800080b7  mov     rcx, qword ptr cs:Block+8; this
0x1800080be  call    ?LogNetworkSizes@CNetworkHandler@@QEAAXXZ; CNetworkHandler::LogNetworkSizes(void)
0x1800080c3  jmp     short loc_1800080EC
0x1800080c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080cc  cmp     rcx, rbp
0x1800080cf  jz      short loc_1800080F3
0x1800080d1  test    byte ptr [rcx+1Ch], 8
0x1800080d5  jz      short loc_1800080F3
0x1800080d7  mov     rcx, [rcx+10h]
0x1800080db  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x1800080e2  mov     edx, 24h ; '$'
0x1800080e7  call    WPP_SF_
0x1800080ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800080f3  cmp     qword ptr [rbx], 0
0x1800080f7  jz      short loc_180008110
0x1800080f9  mov     rcx, [rbx]
0x1800080fc  call    cs:__imp_DevCloseObjectQuery
0x180008102  mov     qword ptr [rbx], 0
0x180008109  mov     rcx, cs:WPP_GLOBAL_Control
0x180008110  cmp     rcx, rbp
0x180008113  jz      short loc_180008130
0x180008115  test    byte ptr [rcx+1Ch], 20h
0x180008119  jz      short loc_180008130
0x18000811b  mov     rcx, [rcx+10h]
0x18000811f  lea     r8, WPP_7fef1fa79ee3391c6a163bc1b1bc3ea3_Traceguids
0x180008126  mov     edx, 25h ; '%'
0x18000812b  call    WPP_SF_
0x180008130  lea     rcx, [rbx+10h]
0x180008134  mov     rbx, [rsp+28h+arg_0]
0x180008139  mov     rbp, [rsp+28h+arg_8]
0x18000813e  add     rsp, 20h
0x180008142  pop     rdi
0x180008143  jmp     cs:__imp_LeaveCriticalSection
```
