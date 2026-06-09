# WiFiTaskPipeClient::PipeBroken(void)

- ea: `0x140007ce0`
- end: `0x140007d25`
- name: `?PipeBroken@WiFiTaskPipeClient@@UEAAJXZ`
- size: `69`
- prototype: `__int64 __fastcall(WiFiTaskPipeClient *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x140007ce0`
- `0x14000bef0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007d18`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140007d18`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::PipeBroken(WiFiTaskPipeClient *this)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40);
  }
  SetEvent(g_hAllDoneEvent);
  return 0;
}

```

## disassembly

```asm
0x140007ce0  sub     rsp, 28h
0x140007ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x140007ceb  lea     rax, WPP_GLOBAL_Control
0x140007cf2  cmp     rcx, rax
0x140007cf5  jz      short loc_140007D11
0x140007cf7  cmp     byte ptr [rcx+19h], 4
0x140007cfb  jb      short loc_140007D11
0x140007cfd  test    byte ptr [rcx+1Ch], 1
0x140007d01  jz      short loc_140007D11
0x140007d03  mov     rcx, [rcx+10h]
0x140007d07  mov     edx, 28h ; '('
0x140007d0c  call    WPP_SF_
0x140007d11  mov     rcx, cs:?g_hAllDoneEvent@@3PEAXEA; hEvent
0x140007d18  call    cs:__imp_SetEvent
0x140007d1e  xor     eax, eax
0x140007d20  add     rsp, 28h
0x140007d24  retn
```
