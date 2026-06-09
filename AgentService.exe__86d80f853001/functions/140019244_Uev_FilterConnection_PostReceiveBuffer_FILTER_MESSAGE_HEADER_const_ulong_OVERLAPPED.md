# Uev::FilterConnection::PostReceiveBuffer(_FILTER_MESSAGE_HEADER * const,ulong,_OVERLAPPED *)

- ea: `0x140019244`
- end: `0x1400192b8`
- name: `?PostReceiveBuffer@FilterConnection@Uev@@QEAAJQEAU_FILTER_MESSAGE_HEADER@@KPEAU_OVERLAPPED@@@Z`
- size: `116`
- prototype: `int(Uev::FilterConnection *__hidden this, struct _FILTER_MESSAGE_HEADER *const, unsigned int, struct _OVERLAPPED *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x1400198cc`
- `0x140019b3c`

## callees

- `0x14000ac88`
- `0x14000acc4`
- `0x1400191ec`
- `0x140019244`

## import_xrefs

- `FLTLIB!FilterGetMessage` at `0x14001927b`
- `FLTLIB!FilterGetMessage` at `0x14001927b`

## string_xrefs

- `0x140019259`: `AgentService.FilterConnection::PostReceiveBuffer: Entry`
- `0x14001928c`: `AgentService.FilterConnection::PostReceiveBuffer: Get message failed, status = 0x%X`
- `0x1400192a1`: `AgentService.FilterConnection::PostReceiveBuffer: Exit, retStatus = 0x%X`

## pseudocode

```c
__int64 __fastcall Uev::FilterConnection::PostReceiveBuffer(
        HANDLE *this,
        struct _FILTER_MESSAGE_HEADER *const a2,
        DWORD a3,
        struct _OVERLAPPED *a4)
{
  unsigned int Message; // ebx

  DbgTrace<5>(L"AgentService.FilterConnection::PostReceiveBuffer: Entry");
  if ( (char *)*this - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    Message = -2147022646;
  }
  else
  {
    Message = FilterGetMessage(*this, a2, a3, a4);
    if ( Message != -2147023899 )
      DbgTraceFrmtErr<long>((wchar_t *)L"AgentService.FilterConnection::PostReceiveBuffer: Get message failed, status = 0x%X");
  }
  DbgTraceFrmt<5,long>((wchar_t *)L"AgentService.FilterConnection::PostReceiveBuffer: Exit, retStatus = 0x%X");
  return Message;
}

```

## disassembly

```asm
0x140019244  push    rbx
0x140019246  push    rbp
0x140019247  push    rsi
0x140019248  push    rdi
0x140019249  sub     rsp, 28h
0x14001924d  mov     rdi, r9
0x140019250  mov     esi, r8d
0x140019253  mov     rbp, rdx
0x140019256  mov     rbx, rcx
0x140019259  lea     rcx, aAgentserviceFi_4; "AgentService.FilterConnection::PostRece"...
0x140019260  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x140019265  mov     rcx, [rbx]; hPort
0x140019268  lea     rax, [rcx-1]
0x14001926c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140019270  ja      short loc_14001929A
0x140019272  mov     r9, rdi; lpOverlapped
0x140019275  mov     r8d, esi; dwMessageBufferSize
0x140019278  mov     rdx, rbp; lpMessageBuffer
0x14001927b  call    cs:__imp_FilterGetMessage
0x140019281  mov     ebx, eax
0x140019283  cmp     eax, 800703E5h
0x140019288  jz      short loc_14001929F
0x14001928a  mov     edx, eax
0x14001928c  lea     rcx, aAgentserviceFi_2; "AgentService.FilterConnection::PostRece"...
0x140019293  call    ??$DbgTraceFrmtErr@J@@YAXPEB_WJ@Z; DbgTraceFrmtErr<long>(wchar_t const *,long)
0x140019298  jmp     short loc_14001929F
0x14001929a  mov     ebx, 800708CAh
0x14001929f  mov     edx, ebx
0x1400192a1  lea     rcx, aAgentserviceFi_3; "AgentService.FilterConnection::PostRece"...
0x1400192a8  call    ??$DbgTraceFrmt@$04J@@YAXPEB_WJ@Z; DbgTraceFrmt<5,long>(wchar_t const *,long)
0x1400192ad  mov     eax, ebx
0x1400192af  add     rsp, 28h
0x1400192b3  pop     rdi
0x1400192b4  pop     rsi
0x1400192b5  pop     rbp
0x1400192b6  pop     rbx
0x1400192b7  retn
```
