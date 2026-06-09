# CBthActiveConnector::_ExitSuspend(void)

- ea: `0x18000785c`
- end: `0x180007879`
- name: `?_ExitSuspend@CBthActiveConnector@@AEAAXXZ`
- size: `29`
- prototype: `void __fastcall(CBthActiveConnector *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003980`
- `0x180006360`
- `0x180007790`
- `0x180011b04`

## callees

- `0x18000785c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000786e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000786e`

## pseudocode

```c
void __fastcall CBthActiveConnector::_ExitSuspend(CBthActiveConnector *this)
{
  char *v1; // rcx

  v1 = (char *)*((_QWORD *)this + 3);
  if ( (unsigned __int64)(v1 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    SetEvent(v1);
}

```

## disassembly

```asm
0x18000785c  sub     rsp, 28h
0x180007860  mov     rcx, [rcx+18h]; hEvent
0x180007864  lea     rax, [rcx-1]
0x180007868  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000786c  ja      short loc_180007874
0x18000786e  call    cs:__imp_SetEvent
0x180007874  add     rsp, 28h
0x180007878  retn
```
