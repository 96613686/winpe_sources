# StartAddress

- ea: `0x18005c2c0`
- end: `0x18005c3b9`
- name: `StartAddress`
- size: `249`
- prototype: `__int64 __fastcall(char *Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18005c2c0`
- `0x18006a010`

## import_xrefs

- `FLTLIB!FilterGetMessage` at `0x18005c33c`
- `FLTLIB!FilterGetMessage` at `0x18005c33c`
- `KERNEL32!GetLastError` at `0x18005c374`
- `KERNEL32!GetLastError` at `0x18005c374`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18005c366`
- `KERNEL32!GetQueuedCompletionStatus` at `0x18005c366`

## pseudocode

```c
__int64 __fastcall StartAddress(char *Parameter)
{
  int Message; // ebx
  void *v3; // rcx
  LPOVERLAPPED v4; // rsi
  struct _FILTER_MESSAGE_HEADER *v5; // rbx
  signed int LastError; // eax
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp+8h] BYREF
  LPOVERLAPPED lpOverlapped; // [rsp+58h] [rbp+10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp+18h] BYREF

  Message = 0;
  lpOverlapped = 0;
  CompletionKey = 0;
  v3 = (void *)*((_QWORD *)Parameter + 10);
  NumberOfBytesTransferred = 0;
  while ( GetQueuedCompletionStatus(v3, &NumberOfBytesTransferred, &CompletionKey, &lpOverlapped, 0xFFFFFFFF) )
  {
    v4 = lpOverlapped;
    if ( !lpOverlapped )
      goto LABEL_10;
    v5 = (struct _FILTER_MESSAGE_HEADER *)(*((_QWORD *)Parameter + 14)
                                         + (unsigned int)(LODWORD(lpOverlapped[-1].hEvent) * *((_DWORD *)Parameter + 34)));
    (*(void (__fastcall **)(_QWORD, struct _FILTER_MESSAGE_HEADER *, _QWORD, char *))(**((_QWORD **)Parameter + 9) + 8LL))(
      *((_QWORD *)Parameter + 9),
      v5,
      NumberOfBytesTransferred,
      Parameter + 40);
    *(_OWORD *)&v4->Internal = 0;
    *(_OWORD *)&v4->Offset = 0;
    Message = FilterGetMessage(*((HANDLE *)Parameter + 1), v5, *((_DWORD *)Parameter + 34), v4);
    if ( Message != -2147023899 )
      goto LABEL_10;
    v3 = (void *)*((_QWORD *)Parameter + 10);
  }
  LastError = GetLastError();
  Message = LastError;
  if ( LastError > 0 )
    Message = (unsigned __int16)LastError | 0x80070000;
  if ( Message != -2147024809 && Message != -2147024161 )
  {
LABEL_10:
    if ( Message < 0 )
      (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)Parameter + 9) + 16LL))(
        *((_QWORD *)Parameter + 9),
        (unsigned int)Message);
  }
  return 0;
}

```

## disassembly

```asm
0x18005c2c0  push    rbx
0x18005c2c2  push    rsi
0x18005c2c3  push    rdi
0x18005c2c4  sub     rsp, 30h
0x18005c2c8  xor     ebx, ebx
0x18005c2ca  mov     [rsp+48h+lpOverlapped], 0
0x18005c2d3  mov     rdi, rcx
0x18005c2d6  mov     [rsp+48h+CompletionKey], rbx
0x18005c2db  mov     rcx, [rcx+50h]
0x18005c2df  mov     [rsp+48h+NumberOfBytesTransferred], 0
0x18005c2e7  jmp     short loc_18005C34F
0x18005c2e9  mov     rsi, [rsp+48h+lpOverlapped]
0x18005c2ee  test    rsi, rsi
0x18005c2f1  jz      loc_18005C399
0x18005c2f7  mov     ebx, [rdi+88h]
0x18005c2fd  lea     r9, [rdi+28h]
0x18005c301  mov     rcx, [rdi+48h]
0x18005c305  imul    ebx, [rsi-8]
0x18005c309  mov     r8d, [rsp+48h+NumberOfBytesTransferred]
0x18005c30e  mov     rax, [rcx]
0x18005c311  add     rbx, [rdi+70h]
0x18005c315  mov     rdx, rbx
0x18005c318  mov     rax, [rax+8]
0x18005c31c  call    j__guard_dispatch_icall
0x18005c321  xorps   xmm0, xmm0
0x18005c324  mov     r9, rsi; lpOverlapped
0x18005c327  movups  xmmword ptr [rsi], xmm0
0x18005c32a  mov     rdx, rbx; lpMessageBuffer
0x18005c32d  movups  xmmword ptr [rsi+10h], xmm0
0x18005c331  mov     r8d, [rdi+88h]; dwMessageBufferSize
0x18005c338  mov     rcx, [rdi+8]; hPort
0x18005c33c  call    cs:FilterGetMessage
0x18005c342  mov     ebx, eax
0x18005c344  cmp     eax, 800703E5h
0x18005c349  jnz     short loc_18005C399
0x18005c34b  mov     rcx, [rdi+50h]; CompletionPort
0x18005c34f  lea     r9, [rsp+48h+lpOverlapped]; lpOverlapped
0x18005c354  mov     [rsp+48h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x18005c35c  lea     r8, [rsp+48h+CompletionKey]; lpCompletionKey
0x18005c361  lea     rdx, [rsp+48h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18005c366  call    cs:GetQueuedCompletionStatus
0x18005c36c  test    eax, eax
0x18005c36e  jnz     loc_18005C2E9
0x18005c374  call    cs:GetLastError
0x18005c37a  mov     ebx, eax
0x18005c37c  test    eax, eax
0x18005c37e  jle     short loc_18005C389
0x18005c380  movzx   ebx, ax
0x18005c383  or      ebx, 80070000h
0x18005c389  cmp     ebx, 80070057h
0x18005c38f  jz      short loc_18005C3AF
0x18005c391  cmp     ebx, 800702DFh
0x18005c397  jz      short loc_18005C3AF
0x18005c399  test    ebx, ebx
0x18005c39b  jns     short loc_18005C3AF
0x18005c39d  mov     rcx, [rdi+48h]
0x18005c3a1  mov     edx, ebx
0x18005c3a3  mov     rax, [rcx]
0x18005c3a6  mov     rax, [rax+10h]
0x18005c3aa  call    j__guard_dispatch_icall
0x18005c3af  xor     eax, eax
0x18005c3b1  add     rsp, 30h
0x18005c3b5  pop     rdi
0x18005c3b6  pop     rsi
0x18005c3b7  pop     rbx
0x18005c3b8  retn
```
