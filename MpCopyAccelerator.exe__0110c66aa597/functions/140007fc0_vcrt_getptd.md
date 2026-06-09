# __vcrt_getptd

- ea: `0x140007fc0`
- end: `0x140007fd9`
- name: `__vcrt_getptd`
- size: `25`
- prototype: ``
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a20`
- `0x140006a74`
- `0x140006ac8`
- `0x1400074fc`
- `0x140007538`
- `0x14000758c`
- `0x1400075a0`
- `0x1400075b4`
- `0x1400075cc`
- `0x1400075e4`
- `0x14000766c`
- `0x140007740`
- `0x1400077b8`
- `0x140007810`
- `0x140007878`
- `0x14000788c`
- `0x140007cd0`
- `0x140008a3c`
- `0x140008f40`
- `0x14000948c`
- `0x1400096f0`
- `0x140009c58`
- `0x140009e8c`
- `0x14000a144`
- `0x14000a360`
- `0x14000a550`
- `0x14000a91c`
- `0x14000a9b4`
- `0x14000a9e4`
- `0x14000ab70`

## callees

- `0x140007fc0`
- `0x140007fdc`
- `0x140013658`

## pseudocode

```c
__int64 _vcrt_getptd()
{
  __int64 result; // rax

  result = _vcrt_getptd_noexit();
  if ( !result )
    abort();
  return result;
}

```

## disassembly

```asm
0x140007fc0  sub     rsp, 28h
0x140007fc4  call    __vcrt_getptd_noexit
0x140007fc9  test    rax, rax
0x140007fcc  jz      short loc_140007FD3
0x140007fce  add     rsp, 28h
0x140007fd2  retn
0x140007fd3  call    abort
```
