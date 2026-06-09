# CMtfPredictionCandidate::TakeReadingRef(ushort const * *)

- ea: `0x18002a5b0`
- end: `0x18002a5ef`
- name: `?TakeReadingRef@CMtfPredictionCandidate@@UEAAJPEAPEBG@Z`
- size: `63`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, const unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18002a5b0`
- `0x18002aff8`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::TakeReadingRef(CMtfPredictionCandidate *this, const unsigned __int16 **a2)
{
  CMtfPredictionCandidate *v4; // rcx
  __int64 result; // rax

  v4 = (CMtfPredictionCandidate *)((char *)this - 16);
  if ( *((_BYTE *)v4 + 116) || (result = CMtfPredictionCandidate::_UpdateCachedStrings(v4), (int)result >= 0) )
  {
    *a2 = (const unsigned __int16 *)*((_QWORD *)this + 9);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002a5b0  mov     [rsp+arg_0], rbx
0x18002a5b5  push    rdi
0x18002a5b6  sub     rsp, 20h
0x18002a5ba  mov     rdi, rdx
0x18002a5bd  mov     rbx, rcx
0x18002a5c0  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18002a5c4  cmp     byte ptr [rcx+74h], 0
0x18002a5c8  jnz     short loc_18002A5D3
0x18002a5ca  call    ?_UpdateCachedStrings@CMtfPredictionCandidate@@IEAAJXZ; CMtfPredictionCandidate::_UpdateCachedStrings(void)
0x18002a5cf  test    eax, eax
0x18002a5d1  js      short loc_18002A5E3
0x18002a5d3  mov     rax, [rbx+48h]
0x18002a5d7  mov     [rdi], rax
0x18002a5da  xor     eax, eax
0x18002a5dc  jmp     short loc_18002A5E3
0x18002a5de  mov     eax, 80004005h
0x18002a5e3  mov     rbx, [rsp+28h+arg_0]
0x18002a5e8  add     rsp, 20h
0x18002a5ec  pop     rdi
0x18002a5ed  retn
```
