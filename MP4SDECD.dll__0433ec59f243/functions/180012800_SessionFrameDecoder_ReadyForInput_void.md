# SessionFrameDecoder::ReadyForInput(void)

- ea: `0x180012800`
- end: `0x180012812`
- name: `?ReadyForInput@SessionFrameDecoder@@QEAAJXZ`
- size: `18`
- prototype: `bool __fastcall(SessionFrameDecoder *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180012580`
- `0x1800139f0`

## callees

- `0x180012800`

## pseudocode

```c
bool __fastcall SessionFrameDecoder::ReadyForInput(SessionFrameDecoder *this)
{
  __int64 v1; // rdx
  bool result; // al

  v1 = *((_QWORD *)this + 2);
  result = 0;
  if ( v1 )
    return *(_DWORD *)(v1 + 116) == 0;
  return result;
}

```

## disassembly

```asm
0x180012800  mov     rdx, [rcx+10h]
0x180012804  xor     eax, eax
0x180012806  test    rdx, rdx
0x180012809  jz      short locret_180012811
0x18001280b  cmp     [rdx+74h], eax
0x18001280e  setz    al
0x180012811  retn
```
