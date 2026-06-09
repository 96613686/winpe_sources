# StateWebServer::StartSocketTimer(void)

- ea: `0x1400027ec`
- end: `0x14000283e`
- name: `?StartSocketTimer@StateWebServer@@AEAAJXZ`
- size: `82`
- prototype: `__int64 __fastcall(StateWebServer *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140001a20`
- `0x140002678`

## callees

- `0x1400023d0`
- `0x1400027ec`
- `0x140004f2c`

## import_xrefs

- `KERNEL32!CreateThread` at `0x14000281b`
- `KERNEL32!CreateThread` at `0x14000281b`

## pseudocode

```c
__int64 __fastcall StateWebServer::StartSocketTimer(StateWebServer *this)
{
  unsigned int v1; // edi
  HANDLE Thread; // rax

  v1 = 0;
  *((_BYTE *)this + 16) = 0;
  StateWebServer::GetSocketTimeoutValueFromReg(this);
  Thread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)SocketExpiryThreadFunc, 0, 0, 0);
  *((_QWORD *)this + 1) = Thread;
  if ( !Thread )
    return (unsigned int)GetLastWin32Error();
  return v1;
}

```

## disassembly

```asm
0x1400027ec  mov     [rsp+arg_0], rbx
0x1400027f1  push    rdi
0x1400027f2  sub     rsp, 30h
0x1400027f6  xor     edi, edi
0x1400027f8  mov     rbx, rcx
0x1400027fb  mov     [rcx+10h], dil
0x1400027ff  call    ?GetSocketTimeoutValueFromReg@StateWebServer@@AEAAJXZ; StateWebServer::GetSocketTimeoutValueFromReg(void)
0x140002804  xor     r9d, r9d; lpParameter
0x140002807  mov     [rsp+38h+lpThreadId], rdi; lpThreadId
0x14000280c  lea     r8, ?SocketExpiryThreadFunc@@YAKPEAX@Z; lpStartAddress
0x140002813  mov     [rsp+38h+dwCreationFlags], edi; dwCreationFlags
0x140002817  xor     edx, edx; dwStackSize
0x140002819  xor     ecx, ecx; lpThreadAttributes
0x14000281b  call    cs:__imp_CreateThread
0x140002821  mov     [rbx+8], rax
0x140002825  test    rax, rax
0x140002828  jnz     short loc_140002831
0x14000282a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x14000282f  mov     edi, eax
0x140002831  mov     rbx, [rsp+38h+arg_0]
0x140002836  mov     eax, edi
0x140002838  add     rsp, 30h
0x14000283c  pop     rdi
0x14000283d  retn
```
