# Uev::NotificationListener::Listen(void)

- ea: `0x1400198cc`
- end: `0x140019ada`
- name: `?Listen@NotificationListener@Uev@@AEAAKXZ`
- size: `526`
- prototype: `__int64 __fastcall(Uev::NotificationListener *this, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x140019ae0`

## callees

- `0x140003e50`
- `0x14000ac28`
- `0x14000ac58`
- `0x14000ac88`
- `0x14000acc4`
- `0x1400191ec`
- `0x140019244`
- `0x1400198cc`
- `0x14009b010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001994d`
- `KERNEL32!GetLastError` at `0x14001994d`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140019943`
- `KERNEL32!GetQueuedCompletionStatus` at `0x140019943`
- `FLTLIB!FilterReplyMessage` at `0x140019a3f`
- `FLTLIB!FilterReplyMessage` at `0x140019a3f`

## string_xrefs

- `0x140019a1a`: `AgentService.FilterConnection::SendReplyMessage: Entry`
- `0x140019a4d`: `AgentService.FilterConnection::SendReplyMessage: Reply message failed, status = 0x%X`
- `0x140019a62`: `AgentService.FilterConnection::SendReplyMessage: Exit, retStatus = 0x%X`
- `0x140019912`: `AgentService.NotificationListener::Listen: Entry`
- `0x140019977`: `AgentService.NotificationListener::Listen: Un-expected error obtaining queued completion status, status = 0x%X`
- `0x1400199e5`: `AgentService.NotificationListener::Listen: Un-expected receive message size`
- `0x140019a74`: `AgentService.NotificationListener::Listen: Error encountered sending reply, status = 0x%X`
- `0x140019aaa`: `AgentService.NotificationListener::Listen: Exit`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Uev::NotificationListener::Listen(Uev::NotificationListener *this, __int64 a2)
{
  Uev::NotificationListener *v2; // rdi
  __int64 v3; // rdx
  signed int LastError; // eax
  HANDLE *p_hEvent; // r15
  unsigned int *v6; // r12
  struct _FILTER_MESSAGE_HEADER *v7; // r14
  char *v8; // rcx
  HRESULT v9; // esi
  HANDLE *v12; // [rsp+38h] [rbp-90h]
  unsigned int *v13; // [rsp+40h] [rbp-88h]
  LPOVERLAPPED Overlapped; // [rsp+50h] [rbp-78h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+58h] [rbp-70h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp-68h] BYREF
  _BYTE ReplyBuffer[24]; // [rsp+68h] [rbp-60h] BYREF

  v2 = this;
  Overlapped = 0;
  NumberOfBytesTransferred = 0;
  CompletionKey = 0;
  DbgTrace<4>(L"AgentService.NotificationListener::Listen: Entry", a2);
  while ( *((_BYTE *)v2 + 20) )
  {
    if ( !GetQueuedCompletionStatus(
            *((HANDLE *)v2 + 1),
            &NumberOfBytesTransferred,
            &CompletionKey,
            &Overlapped,
            0xFFFFFFFF) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError != -2147024809 && LastError != -2147024161 )
        DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.NotificationListener::Listen: Un-expected error obtaining queued c"
                                          "ompletion status, status = 0x%X");
      break;
    }
    p_hEvent = &Overlapped[-1].hEvent;
    v12 = &Overlapped[-1].hEvent;
    v6 = (unsigned int *)((char *)v2 + 16);
    v13 = (unsigned int *)((char *)v2 + 16);
    v7 = (struct _FILTER_MESSAGE_HEADER *)(*((_QWORD *)v2 + 10)
                                         + (unsigned int)(LODWORD(Overlapped[-1].hEvent) * *((_DWORD *)v2 + 4)));
    if ( NumberOfBytesTransferred >= *((_DWORD *)v2 + 4) )
    {
      try
      {
        (*(void (__fastcall **)(Uev::NotificationListener *, struct _FILTER_MESSAGE_HEADER *))(*(_QWORD *)v2 + 8LL))(
          v2,
          v7 + 1);
      }
      catch ( ... )
      {
        DbgTrace<2>(L"AgentService.NotificationListener::Listen: Un-expected exception");
        v2 = this;
        p_hEvent = v12;
        v6 = v13;
      }
    }
    else
    {
      DbgTrace<2>(L"AgentService.NotificationListener::Listen: Un-expected receive message size");
    }
    memset(ReplyBuffer, 0, sizeof(ReplyBuffer));
    *(_QWORD *)&ReplyBuffer[8] = v7->MessageId;
    *(_DWORD *)&ReplyBuffer[16] = 0;
    DbgTrace<5>(L"AgentService.FilterConnection::SendReplyMessage: Entry");
    v8 = (char *)*((_QWORD *)v2 + 19);
    if ( (unsigned __int64)(v8 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v9 = -2147022646;
    }
    else
    {
      v9 = FilterReplyMessage(v8, (PFILTER_REPLY_HEADER)ReplyBuffer, 0x14u);
      if ( v9 < 0 )
        DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.FilterConnection::SendReplyMessage: Reply message failed, status = 0x%X");
    }
    DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.FilterConnection::SendReplyMessage: Exit, retStatus = 0x%X");
    if ( v9 < 0 )
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.NotificationListener::Listen: Error encountered sending reply, status = 0x%X");
    *(_OWORD *)(p_hEvent + 1) = 0;
    *(_OWORD *)(p_hEvent + 3) = 0;
    if ( Uev::FilterConnection::PostReceiveBuffer(
           (Uev::NotificationListener *)((char *)v2 + 152),
           v7,
           *v6,
           (struct _OVERLAPPED *)(p_hEvent + 1)) != -2147023899 )
      break;
  }
  DbgTrace<4>(L"AgentService.NotificationListener::Listen: Exit", v3);
  return 0;
}

```

## disassembly

```asm
0x1400198cc  push    rsi
0x1400198ce  push    rdi
0x1400198cf  push    r12
0x1400198d1  push    r13
0x1400198d3  push    r14
0x1400198d5  push    r15
0x1400198d7  sub     rsp, 98h
0x1400198de  mov     rax, cs:__security_cookie
0x1400198e5  xor     rax, rsp
0x1400198e8  mov     [rsp+0C8h+var_48], rax
0x1400198f0  mov     rdi, rcx
0x1400198f3  mov     [rsp+0C8h+var_98], rcx
0x1400198f8  mov     [rsp+0C8h+Overlapped], 0
0x140019901  mov     [rsp+0C8h+NumberOfBytesTransferred], 0
0x140019909  mov     [rsp+0C8h+CompletionKey], 0
0x140019912  lea     rcx, aAgentserviceNo_12; "AgentService.NotificationListener::List"...
0x140019919  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x14001991e  cmp     byte ptr [rdi+14h], 0
0x140019922  jz      loc_140019AAA
0x140019928  mov     [rsp+0C8h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x140019930  lea     r9, [rsp+0C8h+Overlapped]; lpOverlapped
0x140019935  lea     r8, [rsp+0C8h+CompletionKey]; lpCompletionKey
0x14001993a  lea     rdx, [rsp+0C8h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x14001993f  mov     rcx, [rdi+8]; CompletionPort
0x140019943  call    cs:__imp_GetQueuedCompletionStatus
0x140019949  test    eax, eax
0x14001994b  jnz     short loc_140019988
0x14001994d  call    cs:__imp_GetLastError
0x140019953  test    eax, eax
0x140019955  jle     short loc_14001995F
0x140019957  movzx   eax, ax
0x14001995a  or      eax, 80070000h
0x14001995f  cmp     eax, 80070057h
0x140019964  jz      loc_140019AAA
0x14001996a  cmp     eax, 800702DFh
0x14001996f  jz      loc_140019AAA
0x140019975  mov     edx, eax
0x140019977  lea     rcx, aAgentserviceNo_4; "AgentService.NotificationListener::List"...
0x14001997e  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019983  jmp     loc_140019AAA
0x140019988  mov     r15, [rsp+0C8h+Overlapped]
0x14001998d  add     r15, 0FFFFFFFFFFFFFFF8h
0x140019991  mov     [rsp+0C8h+var_90], r15
0x140019996  lea     r12, [rdi+10h]
0x14001999a  mov     [rsp+0C8h+var_88], r12
0x14001999f  mov     edx, [r12]
0x1400199a3  mov     r14d, edx
0x1400199a6  imul    r14d, [r15]
0x1400199aa  add     r14, [rdi+50h]
0x1400199ae  mov     [rsp+0C8h+var_80], r14
0x1400199b3  cmp     [rsp+0C8h+NumberOfBytesTransferred], edx
0x1400199b7  jb      short loc_1400199E5
0x1400199b9  mov     rax, [rdi]
0x1400199bc  lea     rdx, [r14+10h]
0x1400199c0  mov     rcx, rdi
0x1400199c3  mov     rax, [rax+8]
0x1400199c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400199cc  nop
0x1400199cd  jmp     short loc_1400199F1
0x1400199cf  mov     rdi, [rsp+0C8h+var_98]
0x1400199d4  mov     r15, [rsp+0C8h+var_90]
0x1400199d9  mov     r12, [rsp+0C8h+var_88]
0x1400199de  mov     r14, [rsp+0C8h+var_80]
0x1400199e3  jmp     short loc_1400199F1
0x1400199e5  lea     rcx, aAgentserviceNo_8; "AgentService.NotificationListener::List"...
0x1400199ec  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x1400199f1  mov     qword ptr [rsp+0C8h+ReplyBuffer], 0
0x1400199fa  xorps   xmm0, xmm0
0x1400199fd  movups  xmmword ptr [rsp+0C8h+ReplyBuffer+8], xmm0
0x140019a02  mov     rax, [r14+8]
0x140019a06  mov     qword ptr [rsp+0C8h+ReplyBuffer+8], rax
0x140019a0b  mov     dword ptr [rsp+0C8h+ReplyBuffer+10h], 0
0x140019a13  lea     r13, [rdi+98h]
0x140019a1a  lea     rcx, aAgentserviceFi_5; "AgentService.FilterConnection::SendRepl"...
0x140019a21  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140019a26  mov     rcx, [r13+0]; hPort
0x140019a2a  lea     rax, [rcx-1]
0x140019a2e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019a32  ja      short loc_140019A5B
0x140019a34  mov     r8d, 14h; dwReplyBufferSize
0x140019a3a  lea     rdx, [rsp+0C8h+ReplyBuffer]; lpReplyBuffer
0x140019a3f  call    cs:__imp_FilterReplyMessage
0x140019a45  mov     esi, eax
0x140019a47  test    eax, eax
0x140019a49  jns     short loc_140019A60
0x140019a4b  mov     edx, eax
0x140019a4d  lea     rcx, aAgentserviceFi_0; "AgentService.FilterConnection::SendRepl"...
0x140019a54  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019a59  jmp     short loc_140019A60
0x140019a5b  mov     esi, 800708CAh
0x140019a60  mov     edx, esi
0x140019a62  lea     rcx, aAgentserviceFi; "AgentService.FilterConnection::SendRepl"...
0x140019a69  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x140019a6e  test    esi, esi
0x140019a70  jns     short loc_140019A80
0x140019a72  mov     edx, esi
0x140019a74  lea     rcx, aAgentserviceNo_2; "AgentService.NotificationListener::List"...
0x140019a7b  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019a80  lea     r9, [r15+8]; struct _OVERLAPPED *
0x140019a84  xorps   xmm0, xmm0
0x140019a87  movups  xmmword ptr [r9], xmm0
0x140019a8b  movups  xmmword ptr [r9+10h], xmm0
0x140019a90  mov     r8d, [r12]; unsigned int
0x140019a94  mov     rdx, r14; struct _FILTER_MESSAGE_HEADER *
0x140019a97  mov     rcx, r13; this
0x140019a9a  call    ?PostReceiveBuffer@FilterConnection@Uev@@QEAAJQEAU_FILTER_MESSAGE_HEADER@@KPEAU_OVERLAPPED@@@Z; Uev::FilterConnection::PostReceiveBuffer(_FILTER_MESSAGE_HEADER * const,ulong,_OVERLAPPED *)
0x140019a9f  cmp     eax, 800703E5h
0x140019aa4  jz      loc_14001991E
0x140019aaa  lea     rcx, aAgentserviceNo_16; "AgentService.NotificationListener::List"...
0x140019ab1  call    ??$DbgTrace@$03@@YAXPEB_W@Z; DbgTrace<4>(wchar_t const *)
0x140019ab6  xor     eax, eax
0x140019ab8  mov     rcx, [rsp+0C8h+var_48]
0x140019ac0  xor     rcx, rsp; StackCookie
0x140019ac3  call    __security_check_cookie
0x140019ac8  add     rsp, 98h
0x140019acf  pop     r15
0x140019ad1  pop     r14
0x140019ad3  pop     r13
0x140019ad5  pop     r12
0x140019ad7  pop     rdi
0x140019ad8  pop     rsi
0x140019ad9  retn
```
