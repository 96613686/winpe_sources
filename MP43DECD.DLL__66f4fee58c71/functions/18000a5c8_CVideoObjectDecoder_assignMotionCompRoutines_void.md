# CVideoObjectDecoder::assignMotionCompRoutines(void)

- ea: `0x18000a5c8`
- end: `0x18000a60e`
- name: `?assignMotionCompRoutines@CVideoObjectDecoder@@AEAAXXZ`
- size: `70`
- prototype: `void __fastcall(CVideoObjectDecoder *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000a6bc`

## callees

- `0x18000a5c8`

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
0x18000a5c8  cmp     dword ptr [rcx+0EC4h], 0
0x18000a5cf  jz      short locret_18000A60D
0x18000a5d1  cmp     dword ptr [rcx+0EC8h], 0
0x18000a5d8  jz      short loc_18000A5F1
0x18000a5da  mov     rax, [rcx+190h]
0x18000a5e1  mov     [rcx+0E40h], rax
0x18000a5e8  mov     rax, [rcx+188h]
0x18000a5ef  jmp     short loc_18000A606
0x18000a5f1  mov     rax, [rcx+1A0h]
0x18000a5f8  mov     [rcx+0E40h], rax
0x18000a5ff  mov     rax, [rcx+198h]
0x18000a606  mov     [rcx+0E38h], rax
0x18000a60d  retn
```
