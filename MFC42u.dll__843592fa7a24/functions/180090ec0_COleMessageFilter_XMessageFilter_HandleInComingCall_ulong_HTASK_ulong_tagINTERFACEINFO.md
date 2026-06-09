# COleMessageFilter::XMessageFilter::HandleInComingCall(ulong,HTASK__ *,ulong,tagINTERFACEINFO *)

- ea: `0x180090ec0`
- end: `0x180090f37`
- name: `?HandleInComingCall@XMessageFilter@COleMessageFilter@@UEAAKKPEAUHTASK__@@KPEAUtagINTERFACEINFO@@@Z`
- size: `119`
- prototype: `unsigned int __fastcall(COleMessageFilter::XMessageFilter *__hidden this, unsigned int, HTASK, unsigned int, struct tagINTERFACEINFO *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180090ec0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090f08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180090f08`
- `USER32!PeekMessageW` at `0x180090efe`
- `USER32!PeekMessageW` at `0x180090efe`
- `USER32!PostThreadMessageW` at `0x180090f1b`
- `USER32!PostThreadMessageW` at `0x180090f1b`

## pseudocode

```c
__int64 __fastcall COleMessageFilter::XMessageFilter::HandleInComingCall(
        COleMessageFilter::XMessageFilter *this,
        int a2,
        HTASK a3)
{
  DWORD CurrentThreadId; // eax
  struct tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF

  if ( !*((_DWORD *)this - 7) )
  {
    if ( a2 == 1 || a2 == 4 )
    {
      memset(&Msg, 0, sizeof(Msg));
      if ( !PeekMessageW(&Msg, 0, 0x36Au, 0x36Au, 0) )
      {
        CurrentThreadId = GetCurrentThreadId();
        PostThreadMessageW(CurrentThreadId, 0x36Au, 0, 0);
      }
    }
    return 0;
  }
  if ( a2 != 1 && a2 != 4 )
    return 0;
  return *((unsigned int *)this - 2);
}

```

## disassembly

```asm
0x180090ec0  sub     rsp, 68h
0x180090ec4  cmp     dword ptr [rcx-1Ch], 0
0x180090ec8  jnz     short loc_180090F25
0x180090eca  cmp     edx, 1
0x180090ecd  jz      short loc_180090ED4
0x180090ecf  cmp     edx, 4
0x180090ed2  jnz     short loc_180090F21
0x180090ed4  xorps   xmm0, xmm0
0x180090ed7  mov     [rsp+68h+wRemoveMsg], 0; wRemoveMsg
0x180090edf  mov     r9d, 36Ah; wMsgFilterMax
0x180090ee5  lea     rcx, [rsp+68h+Msg]; lpMsg
0x180090eea  mov     r8d, r9d; wMsgFilterMin
0x180090eed  xor     edx, edx; hWnd
0x180090eef  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x180090ef4  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x180090ef9  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x180090efe  call    cs:__imp_PeekMessageW
0x180090f04  test    eax, eax
0x180090f06  jnz     short loc_180090F21
0x180090f08  call    cs:__imp_GetCurrentThreadId
0x180090f0e  xor     r9d, r9d; lParam
0x180090f11  xor     r8d, r8d; wParam
0x180090f14  mov     ecx, eax; idThread
0x180090f16  mov     edx, 36Ah; Msg
0x180090f1b  call    cs:__imp_PostThreadMessageW
0x180090f21  xor     eax, eax
0x180090f23  jmp     short loc_180090F32
0x180090f25  cmp     edx, 1
0x180090f28  jz      short loc_180090F2F
0x180090f2a  cmp     edx, 4
0x180090f2d  jnz     short loc_180090F21
0x180090f2f  mov     eax, [rcx-8]
0x180090f32  add     rsp, 68h
0x180090f36  retn
```
