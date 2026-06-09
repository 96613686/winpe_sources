# CMutex::CMutex(void)

- ea: `0x18000ec00`
- end: `0x18000eca9`
- name: `??0CMutex@@QEAA@XZ`
- size: `169`
- prototype: `CMutex *__fastcall(CMutex *this, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000dca0`
- `0x18002d394`

## callees

- `0x18000ec00`
- `0x18000fc40`
- `0x180014180`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec38`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000ec38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ec86`

## pseudocode

```c
CMutex *__fastcall CMutex::CMutex(CMutex *this, unsigned int a2)
{
  char *EventW; // rsi
  DWORD LastError; // eax
  ulong pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  CCriticalSectionObject::CCriticalSectionObject(this, a2);
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  EventW = (char *)CreateEventW(0, 0, 1, 0);
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    LastError = GetLastError();
  else
    LastError = 0;
  *((_DWORD *)this + 20) = LastError;
  if ( (unsigned __int64)(*((_QWORD *)this + 9) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    CHandleObject::Close((CMutex *)((char *)this + 72));
  *((_QWORD *)this + 9) = EventW;
  if ( ((unsigned __int64)(EventW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    pExceptionObject = *((_DWORD *)this + 20);
    throw &pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000ec00  mov     [rsp+arg_10], rbx
0x18000ec05  mov     [rsp+arg_0], rcx
0x18000ec0a  push    rbp
0x18000ec0b  push    rsi
0x18000ec0c  push    rdi
0x18000ec0d  sub     rsp, 20h
0x18000ec11  mov     rdi, rcx
0x18000ec14  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x18000ec19  nop
0x18000ec1a  xor     ebp, ebp
0x18000ec1c  mov     [rdi+48h], rbp
0x18000ec20  mov     [rdi+50h], ebp
0x18000ec23  mov     [rdi+38h], rbp
0x18000ec27  mov     [rdi+40h], rbp
0x18000ec2b  xor     r9d, r9d; lpName
0x18000ec2e  xor     edx, edx; bManualReset
0x18000ec30  xor     ecx, ecx; lpEventAttributes
0x18000ec32  mov     r8d, 1; bInitialState
0x18000ec38  call    cs:__imp_CreateEventW
0x18000ec3e  mov     rsi, rax
0x18000ec41  lea     rcx, [rax-1]
0x18000ec45  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000ec49  ja      short loc_18000EC86
0x18000ec4b  mov     eax, ebp
0x18000ec4d  mov     [rdi+50h], eax
0x18000ec50  mov     rax, [rdi+48h]
0x18000ec54  dec     rax
0x18000ec57  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ec5b  jbe     short loc_18000EC8E
0x18000ec5d  mov     [rdi+48h], rsi
0x18000ec61  lea     rax, [rsi+1]
0x18000ec65  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000ec6b  jnz     short loc_18000EC99
0x18000ec6d  mov     eax, [rdi+50h]
0x18000ec70  mov     [rsp+38h+pExceptionObject], eax
0x18000ec74  lea     rdx, _TI1K; pThrowInfo
0x18000ec7b  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000ec80  call    _CxxThrowException_0
0x18000ec86  call    cs:__imp_GetLastError
0x18000ec8c  jmp     short loc_18000EC4D
0x18000ec8e  lea     rcx, [rdi+48h]; this
0x18000ec92  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x18000ec97  jmp     short loc_18000EC5D
0x18000ec99  mov     rax, rdi
0x18000ec9c  mov     rbx, [rsp+38h+arg_10]
0x18000eca1  add     rsp, 20h
0x18000eca5  pop     rdi
0x18000eca6  pop     rsi
0x18000eca7  pop     rbp
0x18000eca8  retn
```
