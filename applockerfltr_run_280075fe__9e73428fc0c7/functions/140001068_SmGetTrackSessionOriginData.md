# SmGetTrackSessionOriginData

- ea: `0x140001068`
- end: `0x14000107e`
- name: `SmGetTrackSessionOriginData`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140007e00`

## callees

- `0x140001068`

## pseudocode

```c
signed __int64 SmGetTrackSessionOriginData()
{
  signed __int64 result; // rax

  result = 0;
  if ( qword_140004078 )
    return _InterlockedCompareExchange64((volatile signed __int64 *)qword_140004078, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140001068  mov     rdx, cs:qword_140004078
0x14000106f  xor     eax, eax
0x140001071  test    rdx, rdx
0x140001074  jz      short locret_14000107D
0x140001076  xor     ecx, ecx
0x140001078  lock cmpxchg [rdx], rcx
0x14000107d  retn
```
