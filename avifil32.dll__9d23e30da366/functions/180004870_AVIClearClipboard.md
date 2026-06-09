# AVIClearClipboard

- ea: `0x180004870`
- end: `0x18000493b`
- name: `AVIClearClipboard`
- size: `203`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x180001460`
- `0x180004870`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048a0`
- `ole32!OleUninitialize` at `0x1800048d2`
- `ole32!OleUninitialize` at `0x1800048d2`
- `ole32!OleInitialize` at `0x180004887`
- `ole32!OleInitialize` at `0x180004887`
- `ole32!OleFlushClipboard` at `0x180004898`
- `ole32!OleFlushClipboard` at `0x180004898`
- `USER32!TranslateMessage` at `0x180004906`
- `USER32!TranslateMessage` at `0x180004906`
- `USER32!PeekMessageW` at `0x18000492c`
- `USER32!PeekMessageW` at `0x18000492c`
- `USER32!DispatchMessageW` at `0x180004911`
- `USER32!DispatchMessageW` at `0x180004911`

## pseudocode

```c
HRESULT __stdcall AVIClearClipboard()
{
  HRESULT v0; // ebx
  HTASK *CurrentThreadId; // r8
  int i; // edx
  MSG Msg; // [rsp+30h] [rbp-48h] BYREF

  if ( OleInitialize(0) >= 0 )
    _InterlockedIncrement(&glOleRefCount);
  v0 = OleFlushClipboard();
LABEL_4:
  CurrentThreadId = (HTASK *)(int)GetCurrentThreadId();
  for ( i = 0; i < 64; ++i )
  {
    if ( (&ahtaskUsed)[i] == CurrentThreadId )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      goto LABEL_4;
    }
  }
  if ( glOleRefCount )
  {
    _InterlockedDecrement(&glOleRefCount);
    OleUninitialize();
  }
  return v0;
}

```

## disassembly

```asm
0x180004870  push    rbx
0x180004872  sub     rsp, 70h
0x180004876  mov     rax, cs:__security_cookie
0x18000487d  xor     rax, rsp
0x180004880  mov     [rsp+78h+var_18], rax
0x180004885  xor     ecx, ecx; pvReserved
0x180004887  call    cs:__imp_OleInitialize
0x18000488d  test    eax, eax
0x18000488f  js      short loc_180004898
0x180004891  lock inc cs:glOleRefCount
0x180004898  call    cs:__imp_OleFlushClipboard
0x18000489e  mov     ebx, eax
0x1800048a0  call    cs:__imp_GetCurrentThreadId
0x1800048a6  movsxd  r8, eax
0x1800048a9  xor     edx, edx
0x1800048ab  movsxd  rcx, edx
0x1800048ae  lea     rax, ?ahtaskUsed@@3PAPEAUHTASK__@@A; HTASK__ * near * ahtaskUsed
0x1800048b5  cmp     [rax+rcx*8], r8
0x1800048b9  jz      short loc_1800048ED
0x1800048bb  inc     edx
0x1800048bd  cmp     edx, 40h ; '@'
0x1800048c0  jl      short loc_1800048AB
0x1800048c2  cmp     cs:glOleRefCount, 0
0x1800048c9  jz      short loc_1800048D8
0x1800048cb  lock dec cs:glOleRefCount
0x1800048d2  call    cs:__imp_OleUninitialize
0x1800048d8  mov     eax, ebx
0x1800048da  mov     rcx, [rsp+78h+var_18]
0x1800048df  xor     rcx, rsp; StackCookie
0x1800048e2  call    __security_check_cookie
0x1800048e7  add     rsp, 70h
0x1800048eb  pop     rbx
0x1800048ec  retn
0x1800048ed  xorps   xmm0, xmm0
0x1800048f0  movups  xmmword ptr [rsp+78h+Msg.hwnd], xmm0
0x1800048f5  movups  xmmword ptr [rsp+78h+Msg.wParam], xmm0
0x1800048fa  movups  xmmword ptr [rsp+78h+Msg.time], xmm0
0x1800048ff  jmp     short loc_180004917
0x180004901  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180004906  call    cs:__imp_TranslateMessage
0x18000490c  lea     rcx, [rsp+78h+Msg]; lpMsg
0x180004911  call    cs:__imp_DispatchMessageW
0x180004917  xor     r9d, r9d; wMsgFilterMax
0x18000491a  mov     [rsp+78h+wRemoveMsg], 1; wRemoveMsg
0x180004922  xor     r8d, r8d; wMsgFilterMin
0x180004925  lea     rcx, [rsp+78h+Msg]; lpMsg
0x18000492a  xor     edx, edx; hWnd
0x18000492c  call    cs:__imp_PeekMessageW
0x180004932  test    eax, eax
0x180004934  jnz     short loc_180004901
0x180004936  jmp     loc_1800048A0
```
