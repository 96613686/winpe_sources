# CVideoObjectDecoder::assignMotionCompRoutines(void)

- ea: `0x18000a688`
- end: `0x18000a6ce`
- name: `?assignMotionCompRoutines@CVideoObjectDecoder@@AEAAXXZ`
- size: `70`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a77c`

## callees

- `0x18000a688`

## pseudocode

```c
void __fastcall CVideoObjectDecoder::assignMotionCompRoutines(CVideoObjectDecoder *this)
{
  __int64 v1; // rax

  if ( *((_DWORD *)this + 945) )
  {
    if ( *((_DWORD *)this + 946) )
    {
      *((_QWORD *)this + 456) = *((_QWORD *)this + 50);
      v1 = *((_QWORD *)this + 49);
    }
    else
    {
      *((_QWORD *)this + 456) = *((_QWORD *)this + 52);
      v1 = *((_QWORD *)this + 51);
    }
    *((_QWORD *)this + 455) = v1;
  }
}

```

## disassembly

```asm
0x18000a688  cmp     dword ptr [rcx+0EC4h], 0
0x18000a68f  jz      short locret_18000A6CD
0x18000a691  cmp     dword ptr [rcx+0EC8h], 0
0x18000a698  jz      short loc_18000A6B1
0x18000a69a  mov     rax, [rcx+190h]
0x18000a6a1  mov     [rcx+0E40h], rax
0x18000a6a8  mov     rax, [rcx+188h]
0x18000a6af  jmp     short loc_18000A6C6
0x18000a6b1  mov     rax, [rcx+1A0h]
0x18000a6b8  mov     [rcx+0E40h], rax
0x18000a6bf  mov     rax, [rcx+198h]
0x18000a6c6  mov     [rcx+0E38h], rax
0x18000a6cd  retn
```
