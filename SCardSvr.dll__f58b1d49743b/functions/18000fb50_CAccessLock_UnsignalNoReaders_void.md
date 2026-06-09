# CAccessLock::UnsignalNoReaders(void)

- ea: `0x18000fb50`
- end: `0x18000fb83`
- name: `?UnsignalNoReaders@CAccessLock@@IEAAXXZ`
- size: `51`
- prototype: `void __fastcall(CAccessLock *__hidden this)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180004c8c`
- `0x180005b2c`
- `0x1800067a0`
- `0x180007910`
- `0x180009230`
- `0x1800098b0`
- `0x180009b30`
- `0x18000a310`
- `0x18000c250`
- `0x18000c9a0`
- `0x18000cd80`
- `0x18000cf60`
- `0x18000d2f0`
- `0x18000ecb0`
- `0x18000f2a0`
- `0x18000f87c`
- `0x18000fcf0`
- `0x180010044`
- `0x180010390`
- `0x1800106f0`
- `0x180010994`
- `0x180013740`

## callees

- `0x18000fb50`
- `0x18003261b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fb58`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000fb58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fb67`

## pseudocode

```c
void __fastcall CAccessLock::UnsignalNoReaders(HANDLE *this)
{
  ulong pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  if ( !ResetEvent(this[9]) )
  {
    pExceptionObject = GetLastError();
    throw &pExceptionObject;
  }
}

```

## disassembly

```asm
0x18000fb50  sub     rsp, 28h
0x18000fb54  mov     rcx, [rcx+48h]; hEvent
0x18000fb58  call    cs:__imp_ResetEvent
0x18000fb5e  test    eax, eax
0x18000fb60  jz      short loc_18000FB67
0x18000fb62  add     rsp, 28h
0x18000fb66  retn
0x18000fb67  call    cs:__imp_GetLastError
0x18000fb6d  lea     rdx, _TI1K; pThrowInfo
0x18000fb74  mov     [rsp+28h+pExceptionObject], eax
0x18000fb78  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000fb7d  call    _CxxThrowException_0
```
