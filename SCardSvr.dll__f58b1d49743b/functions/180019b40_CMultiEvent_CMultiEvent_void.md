# CMultiEvent::CMultiEvent(void)

- ea: `0x180019b40`
- end: `0x180019bbb`
- name: `??0CMultiEvent@@QEAA@XZ`
- size: `123`
- prototype: `CMultiEvent *__fastcall(CMultiEvent *this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180011410`
- `0x18002d394`

## callees

- `0x18000fc40`
- `0x180019b40`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180019b76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019b8a`

## pseudocode

```c
CMultiEvent *__fastcall CMultiEvent::CMultiEvent(CMultiEvent *this, unsigned int a2)
{
  __int64 i; // rdi
  HANDLE EventW; // rax
  ulong pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  CCriticalSectionObject::CCriticalSectionObject(this, a2);
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + i + 7) = EventW;
    if ( !EventW )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
  }
  *((_DWORD *)this + 22) = 0;
  return this;
}

```

## disassembly

```asm
0x180019b40  mov     [rsp+arg_10], rbx
0x180019b45  mov     [rsp+arg_0], rcx
0x180019b4a  push    rdi
0x180019b4b  sub     rsp, 20h
0x180019b4f  mov     rbx, rcx
0x180019b52  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180019b57  nop
0x180019b58  xorps   xmm0, xmm0
0x180019b5b  movups  xmmword ptr [rbx+38h], xmm0
0x180019b5f  movups  xmmword ptr [rbx+48h], xmm0
0x180019b63  xor     edi, edi
0x180019b65  cmp     edi, 4
0x180019b68  jnb     short loc_180019BA6
0x180019b6a  xor     r9d, r9d; lpName
0x180019b6d  xor     r8d, r8d; bInitialState
0x180019b70  lea     edx, [r9+1]; bManualReset
0x180019b74  xor     ecx, ecx; lpEventAttributes
0x180019b76  call    cs:__imp_CreateEventW
0x180019b7c  mov     [rbx+rdi*8+38h], rax
0x180019b81  test    rax, rax
0x180019b84  jz      short loc_180019B8A
0x180019b86  inc     edi
0x180019b88  jmp     short loc_180019B65
0x180019b8a  call    cs:__imp_GetLastError
0x180019b90  mov     [rsp+28h+pExceptionObject], eax
0x180019b94  lea     rdx, _TI1K; pThrowInfo
0x180019b9b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180019ba0  call    _CxxThrowException_0
0x180019ba6  mov     dword ptr [rbx+58h], 0
0x180019bad  mov     rax, rbx
0x180019bb0  mov     rbx, [rsp+28h+arg_10]
0x180019bb5  add     rsp, 20h
0x180019bb9  pop     rdi
0x180019bba  retn
```
