# CAccessLock::CAccessLock(ulong)

- ea: `0x180029c28`
- end: `0x180029d61`
- name: `??0CAccessLock@@QEAA@K@Z`
- size: `313`
- prototype: `CAccessLock *__fastcall(CAccessLock *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d394`

## callees

- `0x1800016c0`
- `0x18000fc40`
- `0x180014180`
- `0x180029c28`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029cde`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029c76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180029cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cf5`

## pseudocode

```c
CAccessLock *__fastcall CAccessLock::CAccessLock(CAccessLock *this, unsigned int a2)
{
  char *EventW; // rbp
  DWORD LastError; // eax
  char *v5; // rsi
  DWORD v6; // eax
  ulong pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  pExceptionObject = a2;
  CCriticalSectionObject::CCriticalSectionObject(this, a2);
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 20) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  EventW = (char *)CreateEventW(0, 1, 1, 0);
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    LastError = GetLastError();
  else
    LastError = 0;
  *((_DWORD *)this + 20) = LastError;
  if ( (unsigned int)CHandleObject::IsValid((CAccessLock *)((char *)this + 72)) )
    CHandleObject::Close((CAccessLock *)((char *)this + 72));
  *((_QWORD *)this + 9) = EventW;
  if ( !(unsigned int)CHandleObject::IsValid((CAccessLock *)((char *)this + 72)) )
  {
    pExceptionObject = *((_DWORD *)this + 20);
    throw &pExceptionObject;
  }
  v5 = (char *)CreateEventW(0, 1, 1, 0);
  if ( (unsigned __int64)(v5 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    v6 = GetLastError();
  else
    v6 = 0;
  *((_DWORD *)this + 24) = v6;
  if ( (unsigned int)CHandleObject::IsValid((CAccessLock *)((char *)this + 88)) )
    CHandleObject::Close((CAccessLock *)((char *)this + 88));
  *((_QWORD *)this + 11) = v5;
  if ( !(unsigned int)CHandleObject::IsValid((CAccessLock *)((char *)this + 88)) )
  {
    pExceptionObject = *((_DWORD *)this + 24);
    throw &pExceptionObject;
  }
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = 20000;
  return this;
}

```

## disassembly

```asm
0x180029c28  mov     [rsp+arg_10], rbx
0x180029c2d  mov     [rsp+pExceptionObject], edx
0x180029c31  mov     [rsp+arg_0], rcx
0x180029c36  push    rbp
0x180029c37  push    rsi
0x180029c38  push    rdi
0x180029c39  sub     rsp, 20h
0x180029c3d  mov     rbx, rcx
0x180029c40  call    ??0CCriticalSectionObject@@QEAA@K@Z; CCriticalSectionObject::CCriticalSectionObject(ulong)
0x180029c45  nop
0x180029c46  lea     rsi, [rbx+48h]
0x180029c4a  mov     qword ptr [rsi], 0
0x180029c51  mov     dword ptr [rsi+8], 0
0x180029c58  lea     rdi, [rbx+58h]
0x180029c5c  mov     qword ptr [rdi], 0
0x180029c63  mov     dword ptr [rdi+8], 0
0x180029c6a  xor     r9d, r9d; lpName
0x180029c6d  lea     edx, [r9+1]; bManualReset
0x180029c71  xor     ecx, ecx; lpEventAttributes
0x180029c73  mov     r8d, edx; bInitialState
0x180029c76  call    cs:__imp_CreateEventW
0x180029c7c  mov     rbp, rax
0x180029c7f  lea     rcx, [rax-1]
0x180029c83  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180029c87  ja      short loc_180029C8D
0x180029c89  xor     eax, eax
0x180029c8b  jmp     short loc_180029C93
0x180029c8d  call    cs:__imp_GetLastError
0x180029c93  mov     [rsi+8], eax
0x180029c96  mov     rcx, rsi; this
0x180029c99  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x180029c9e  test    eax, eax
0x180029ca0  jz      short loc_180029CAA
0x180029ca2  mov     rcx, rsi; this
0x180029ca5  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x180029caa  mov     [rsi], rbp
0x180029cad  mov     rcx, rsi; this
0x180029cb0  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x180029cb5  test    eax, eax
0x180029cb7  jnz     short loc_180029CD2
0x180029cb9  mov     eax, [rbx+50h]
0x180029cbc  mov     [rsp+38h+pExceptionObject], eax
0x180029cc0  lea     rdx, _TI1K; pThrowInfo
0x180029cc7  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180029ccc  call    _CxxThrowException_0
0x180029cd2  xor     r9d, r9d; lpName
0x180029cd5  lea     edx, [r9+1]; bManualReset
0x180029cd9  xor     ecx, ecx; lpEventAttributes
0x180029cdb  mov     r8d, edx; bInitialState
0x180029cde  call    cs:__imp_CreateEventW
0x180029ce4  mov     rsi, rax
0x180029ce7  lea     rcx, [rax-1]
0x180029ceb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180029cef  ja      short loc_180029CF5
0x180029cf1  xor     eax, eax
0x180029cf3  jmp     short loc_180029CFB
0x180029cf5  call    cs:__imp_GetLastError
0x180029cfb  mov     [rdi+8], eax
0x180029cfe  mov     rcx, rdi; this
0x180029d01  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x180029d06  test    eax, eax
0x180029d08  jz      short loc_180029D12
0x180029d0a  mov     rcx, rdi; this
0x180029d0d  call    ?Close@CHandleObject@@QEAAKXZ; CHandleObject::Close(void)
0x180029d12  mov     [rdi], rsi
0x180029d15  mov     rcx, rdi; this
0x180029d18  call    ?IsValid@CHandleObject@@QEBAHXZ; CHandleObject::IsValid(void)
0x180029d1d  test    eax, eax
0x180029d1f  jnz     short loc_180029D3A
0x180029d21  mov     eax, [rbx+60h]
0x180029d24  mov     [rsp+38h+pExceptionObject], eax
0x180029d28  lea     rdx, _TI1K; pThrowInfo
0x180029d2f  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x180029d34  call    _CxxThrowException_0
0x180029d3a  mov     qword ptr [rbx+68h], 0
0x180029d42  mov     qword ptr [rbx+38h], 0
0x180029d4a  mov     dword ptr [rbx+40h], 4E20h
0x180029d51  mov     rax, rbx
0x180029d54  mov     rbx, [rsp+38h+arg_10]
0x180029d59  add     rsp, 20h
0x180029d5d  pop     rdi
0x180029d5e  pop     rsi
0x180029d5f  pop     rbp
0x180029d60  retn
```
