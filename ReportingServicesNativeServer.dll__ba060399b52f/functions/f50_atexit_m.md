# ::_atexit_m

- ea: `0xf50`
- end: `0xf6b`
- name: `::_atexit_m`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x2c0`
- `0x2f0`
- `0x320`
- `0x360`

## callees

- `0xd40`
- `0x1090`

## pseudocode

```c

```

## disassembly

```asm
0xf50  ldarg.0
0xf51  call     void* EncodePointer(void* _Ptr)
0xf56  ldsflda  unsigned int64 ?A0x15aeb141.__exit_list_size
0xf5b  ldsflda  void(())* ?A0x15aeb141.__onexitend_m
0xf60  ldsflda  void(())* ?A0x15aeb141.__onexitbegin_m
0xf65  call     int32 _atexit_helper(void(()) func, unsigned int64* __pexit_list_size, void(())** __ponexitend_e, void(())** __ponexitbegin_e)
0xf6a  ret
```
