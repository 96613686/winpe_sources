# WindowsDispatch(void)

- ea: `0x140003714`
- end: `0x140003913`
- name: `?WindowsDispatch@@YAXXZ`
- size: `511`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140003ab8`

## callees

- `0x14000267c`
- `0x140003714`
- `0x140003c48`
- `0x140003cb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003775`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x140003775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400038fc`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x140003845`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x140003845`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140003860`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140003860`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14000383a`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x14000383a`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400038a8`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400038a8`

## pseudocode

```c
void WindowsDispatch(void)
{
  DWORD LastError; // eax
  __int64 v1; // r8
  _QWORD *v2; // rcx
  __int64 v3; // rdx
  DWORD v4; // eax
  MSG Msg; // [rsp+30h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
  if ( (unsigned __int8)IsCreateWindowExWPresent() )
  {
    while ( 1 )
    {
LABEL_29:
      v4 = MsgWaitForMultipleObjects(1u, &g_shutdownEvent, 0, 0xFFFFFFFF, 0x1CFFu);
      if ( !v4 )
      {
        v2 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return;
        if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
          goto LABEL_9;
        }
        goto LABEL_10;
      }
      if ( v4 != 1 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        if ( Msg.message == 18 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
          }
          goto LABEL_29;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
    }
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      LastError = GetLastError();
      v2 = WPP_GLOBAL_Control;
      v3 = 15;
      goto LABEL_8;
    }
  }
  else
  {
    LastError = WaitForSingleObjectEx(g_shutdownEvent, 0xFFFFFFFF, 1);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      v3 = 16;
LABEL_8:
      WPP_SF_d(v2[2], v3, v1, LastError);
LABEL_9:
      v2 = WPP_GLOBAL_Control;
    }
  }
LABEL_10:
  if ( v2 != &WPP_GLOBAL_Control && (*((_DWORD *)v2 + 7) & 0x100) != 0 )
    WPP_SF_(v2[2], 17, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
}

```

## disassembly

```asm
0x140003714  mov     [rsp+arg_0], rbp
0x140003719  mov     [rsp+arg_8], rsi
0x14000371e  push    rdi
0x14000371f  sub     rsp, 60h
0x140003723  mov     rcx, cs:WPP_GLOBAL_Control
0x14000372a  lea     rsi, WPP_GLOBAL_Control
0x140003731  lea     rbp, WPP_b31ecff79cb331789948a4f8474fa944_Traceguids
0x140003738  mov     edi, 100h
0x14000373d  cmp     rcx, rsi
0x140003740  jz      short loc_140003758
0x140003742  test    [rcx+1Ch], edi
0x140003745  jz      short loc_140003758
0x140003747  mov     rcx, [rcx+10h]
0x14000374b  mov     edx, 0Ah
0x140003750  mov     r8, rbp
0x140003753  call    WPP_SF_
0x140003758  call    IsCreateWindowExWPresent
0x14000375d  test    al, al
0x14000375f  jnz     loc_14000388E
0x140003765  mov     rcx, cs:?g_shutdownEvent@@3PEAXEA; hHandle
0x14000376c  mov     r8d, 1; bAlertable
0x140003772  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003775  call    cs:__imp_WaitForSingleObjectEx
0x14000377b  mov     rcx, cs:WPP_GLOBAL_Control
0x140003782  cmp     rcx, rsi
0x140003785  jz      short loc_1400037BF
0x140003787  test    [rcx+1Ch], edi
0x14000378a  jz      short loc_1400037A4
0x14000378c  mov     edx, 10h
0x140003791  mov     rcx, [rcx+10h]
0x140003795  mov     r9d, eax
0x140003798  call    WPP_SF_d
0x14000379d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037a4  cmp     rcx, rsi
0x1400037a7  jz      short loc_1400037BF
0x1400037a9  test    [rcx+1Ch], edi
0x1400037ac  jz      short loc_1400037BF
0x1400037ae  mov     rcx, [rcx+10h]
0x1400037b2  mov     edx, 11h
0x1400037b7  mov     r8, rbp
0x1400037ba  call    WPP_SF_
0x1400037bf  mov     rbp, [rsp+68h+arg_0]
0x1400037c4  mov     rsi, [rsp+68h+arg_8]
0x1400037c9  add     rsp, 60h
0x1400037cd  pop     rdi
0x1400037ce  retn
0x1400037cf  cmp     eax, 1
0x1400037d2  jnz     loc_1400038E3
0x1400037d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400037df  cmp     rcx, rsi
0x1400037e2  jz      short loc_1400037F8
0x1400037e4  test    [rcx+1Ch], edi
0x1400037e7  jz      short loc_1400037F8
0x1400037e9  mov     rcx, [rcx+10h]
0x1400037ed  lea     edx, [rax+0Bh]
0x1400037f0  mov     r8, rbp
0x1400037f3  call    WPP_SF_
0x1400037f8  xorps   xmm0, xmm0
0x1400037fb  movups  xmmword ptr [rsp+68h+Msg.hwnd], xmm0
0x140003800  movups  xmmword ptr [rsp+68h+Msg.wParam], xmm0
0x140003805  movups  xmmword ptr [rsp+68h+Msg.time], xmm0
0x14000380a  jmp     short loc_14000384B
0x14000380c  cmp     [rsp+68h+Msg.message], 12h
0x140003811  jz      short loc_14000386C
0x140003813  mov     rcx, cs:WPP_GLOBAL_Control
0x14000381a  cmp     rcx, rsi
0x14000381d  jz      short loc_140003835
0x14000381f  test    [rcx+1Ch], edi
0x140003822  jz      short loc_140003835
0x140003824  mov     rcx, [rcx+10h]
0x140003828  mov     edx, 0Eh
0x14000382d  mov     r8, rbp
0x140003830  call    WPP_SF_
0x140003835  lea     rcx, [rsp+68h+Msg]; lpMsg
0x14000383a  call    cs:__imp_TranslateMessage
0x140003840  lea     rcx, [rsp+68h+Msg]; lpMsg
0x140003845  call    cs:__imp_DispatchMessageW
0x14000384b  xor     r9d, r9d; wMsgFilterMax
0x14000384e  mov     [rsp+68h+wRemoveMsg], 1; wRemoveMsg
0x140003856  xor     r8d, r8d; wMsgFilterMin
0x140003859  lea     rcx, [rsp+68h+Msg]; lpMsg
0x14000385e  xor     edx, edx; hWnd
0x140003860  call    cs:__imp_PeekMessageW
0x140003866  test    eax, eax
0x140003868  jnz     short loc_14000380C
0x14000386a  jmp     short loc_14000388E
0x14000386c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003873  cmp     rcx, rsi
0x140003876  jz      short loc_14000388E
0x140003878  test    [rcx+1Ch], edi
0x14000387b  jz      short loc_14000388E
0x14000387d  mov     rcx, [rcx+10h]
0x140003881  mov     edx, 0Dh
0x140003886  mov     r8, rbp
0x140003889  call    WPP_SF_
0x14000388e  xor     r8d, r8d; fWaitAll
0x140003891  mov     [rsp+68h+wRemoveMsg], 1CFFh; dwWakeMask
0x140003899  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14000389d  lea     rdx, ?g_shutdownEvent@@3PEAXEA; pHandles
0x1400038a4  lea     ecx, [r8+1]; nCount
0x1400038a8  call    cs:__imp_MsgWaitForMultipleObjects
0x1400038ae  test    eax, eax
0x1400038b0  jnz     loc_1400037CF
0x1400038b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038bd  cmp     rcx, rsi
0x1400038c0  jz      loc_1400037BF
0x1400038c6  test    [rcx+1Ch], edi
0x1400038c9  jz      loc_1400037A4
0x1400038cf  mov     rcx, [rcx+10h]
0x1400038d3  lea     edx, [rax+0Bh]
0x1400038d6  mov     r8, rbp
0x1400038d9  call    WPP_SF_
0x1400038de  jmp     loc_14000379D
0x1400038e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038ea  cmp     rcx, rsi
0x1400038ed  jz      loc_1400037BF
0x1400038f3  test    [rcx+1Ch], edi
0x1400038f6  jz      loc_1400037A4
0x1400038fc  call    cs:__imp_GetLastError
0x140003902  mov     rcx, cs:WPP_GLOBAL_Control
0x140003909  mov     edx, 0Fh
0x14000390e  jmp     loc_140003791
```
