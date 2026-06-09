# StartAddress

- ea: `0x180074730`
- end: `0x180074824`
- name: `StartAddress`
- size: `244`
- prototype: `__int64 __fastcall(__int128 *lpThreadParameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180074064`
- `0x180074114`
- `0x180074484`
- `0x180074730`
- `0x18007b9de`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180074756`
- `KERNEL32!GetCurrentThreadId` at `0x180074756`
- `KERNEL32!GetModuleHandleW` at `0x18007478e`
- `KERNEL32!GetModuleHandleW` at `0x18007478e`
- `KERNEL32!WaitForSingleObject` at `0x1800747d8`
- `KERNEL32!WaitForSingleObject` at `0x1800747d8`
- `KERNEL32!SetEvent` at `0x1800747b6`
- `KERNEL32!SetEvent` at `0x1800747b6`
- `USER32!DispatchMessageW` at `0x1800747f0`
- `USER32!DispatchMessageW` at `0x1800747f0`
- `USER32!GetMessageW` at `0x180074802`
- `USER32!GetMessageW` at `0x180074802`
- `USER32!TranslateMessage` at `0x1800747e6`
- `USER32!TranslateMessage` at `0x1800747e6`

## pseudocode

```c
__int64 __fastcall StartAddress(__int128 *lpThreadParameter)
{
  __int128 v1; // xmm6
  __int64 *ModuleMsoSynchronizer_0; // rbx
  DWORD CurrentThreadId; // eax
  bool v4; // zf
  int MessageW; // eax
  HANDLE hHandle[2]; // [rsp+68h] [rbp-19h]
  WNDCLASSW Msg; // [rsp+78h] [rbp-9h] BYREF

  v1 = *lpThreadParameter;
  *(_OWORD *)hHandle = *lpThreadParameter;
  ModuleMsoSynchronizer_0 = GetModuleMsoSynchronizer_0();
  CurrentThreadId = GetCurrentThreadId();
  v4 = byte_1800BADD4 == 0;
  *(_DWORD *)ModuleMsoSynchronizer_0 = CurrentThreadId;
  if ( v4 )
  {
    memset(&Msg, 0, sizeof(Msg));
    Msg.lpfnWndProc = (WNDPROC)sub_1800744F0;
    Msg.lpszClassName = L"MsoSynchronizerWndClass";
    Msg.hInstance = GetModuleHandleW(0);
    sub_180074064(&Msg);
    byte_1800BADD4 = 1;
  }
  ModuleMsoSynchronizer_0[2] = (__int64)sub_180074114();
  SetEvent((HANDLE)v1);
  memset(&Msg, 0, 48);
  while ( 1 )
  {
    MessageW = GetMessageW((LPMSG)&Msg, 0, 0, 0);
    if ( !MessageW || MessageW == -1 || !WaitForSingleObject(hHandle[1], 0) )
      break;
    TranslateMessage((const MSG *)&Msg);
    DispatchMessageW((const MSG *)&Msg);
  }
  return 0;
}

```

## disassembly

```asm
0x180074730  mov     rax, rsp
0x180074733  mov     [rax+8], rbx
0x180074737  push    rbp
0x180074738  lea     rbp, [rax-5Fh]
0x18007473c  sub     rsp, 0D0h
0x180074743  movaps  xmmword ptr [rax-18h], xmm6
0x180074747  movups  xmm6, xmmword ptr [rcx]
0x18007474a  movups  xmmword ptr [rbp+57h+hHandle], xmm6
0x18007474e  call    GetModuleMsoSynchronizer_0
0x180074753  mov     rbx, rax
0x180074756  call    cs:GetCurrentThreadId
0x18007475c  cmp     cs:byte_1800BADD4, 0
0x180074763  mov     [rbx], eax
0x180074765  jnz     short loc_1800747A8
0x180074767  xor     edx, edx; Val
0x180074769  lea     rcx, [rbp+57h+Msg]; void *
0x18007476d  lea     r8d, [rdx+48h]; Size
0x180074771  call    memset
0x180074776  lea     rax, sub_1800744F0
0x18007477d  xor     ecx, ecx; lpModuleName
0x18007477f  mov     qword ptr [rbp+57h+Msg.message], rax
0x180074783  lea     rax, ClassName; "MsoSynchronizerWndClass"
0x18007478a  mov     [rbp+57h+var_20], rax
0x18007478e  call    cs:GetModuleHandleW
0x180074794  lea     rcx, [rbp+57h+Msg]; lpWndClass
0x180074798  mov     [rbp+57h+Msg.lParam], rax
0x18007479c  call    sub_180074064
0x1800747a1  mov     cs:byte_1800BADD4, 1
0x1800747a8  call    sub_180074114
0x1800747ad  movq    rcx, xmm6; hEvent
0x1800747b2  mov     [rbx+10h], rax
0x1800747b6  call    cs:SetEvent
0x1800747bc  xorps   xmm0, xmm0
0x1800747bf  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x1800747c3  movups  xmmword ptr [rbp+7], xmm0
0x1800747c7  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x1800747cb  jmp     short loc_1800747F6
0x1800747cd  cmp     eax, 0FFFFFFFFh
0x1800747d0  jz      short loc_18007480C
0x1800747d2  mov     rcx, [rbp+57h+hHandle+8]; hHandle
0x1800747d6  xor     edx, edx; dwMilliseconds
0x1800747d8  call    cs:WaitForSingleObject
0x1800747de  test    eax, eax
0x1800747e0  jz      short loc_18007480C
0x1800747e2  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800747e6  call    cs:TranslateMessage
0x1800747ec  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800747f0  call    cs:DispatchMessageW
0x1800747f6  xor     r9d, r9d; wMsgFilterMax
0x1800747f9  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1800747fd  xor     r8d, r8d; wMsgFilterMin
0x180074800  xor     edx, edx; hWnd
0x180074802  call    cs:GetMessageW
0x180074808  test    eax, eax
0x18007480a  jnz     short loc_1800747CD
0x18007480c  lea     r11, [rsp+0D0h+var_s0]
0x180074814  xor     eax, eax
0x180074816  mov     rbx, [r11+10h]
0x18007481a  movaps  xmm6, xmmword ptr [r11-10h]
0x18007481f  mov     rsp, r11
0x180074822  pop     rbp
0x180074823  retn
```
