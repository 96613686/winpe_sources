# MapsBrokerAsyncOperation::ResetCallback(bool *)

- ea: `0x180007de0`
- end: `0x180007e2d`
- name: `?ResetCallback@MapsBrokerAsyncOperation@@UEAAJPEA_N@Z`
- size: `77`
- prototype: `__int64 __fastcall(MapsBrokerAsyncOperation *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180007e15`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007df9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180007df9`

## pseudocode

```c
__int64 __fastcall MapsBrokerAsyncOperation::ResetCallback(MapsBrokerAsyncOperation *this, bool *a2)
{
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *a2 = *((_QWORD *)this + 8) != 0;
  *((_QWORD *)this + 8) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  return 0;
}

```

## disassembly

```asm
0x180007de0  mov     [rsp+arg_0], rbx
0x180007de5  mov     [rsp+arg_8], rsi
0x180007dea  push    rdi
0x180007deb  sub     rsp, 20h
0x180007def  mov     rsi, rcx
0x180007df2  mov     rdi, rdx
0x180007df5  add     rcx, 10h; lpCriticalSection
0x180007df9  call    cs:__imp_EnterCriticalSection
0x180007dff  cmp     qword ptr [rsi+40h], 0
0x180007e04  lea     rcx, [rsi+10h]; lpCriticalSection
0x180007e08  setnz   al
0x180007e0b  mov     [rdi], al
0x180007e0d  mov     qword ptr [rsi+40h], 0
0x180007e15  call    cs:__imp_LeaveCriticalSection
0x180007e1b  mov     rbx, [rsp+28h+arg_0]
0x180007e20  xor     eax, eax
0x180007e22  mov     rsi, [rsp+28h+arg_8]
0x180007e27  add     rsp, 20h
0x180007e2b  pop     rdi
0x180007e2c  retn
```
