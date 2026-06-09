# CBufferSourceManager::Complete(CTStickyVal<int> *)

- ea: `0x180028dc4`
- end: `0x180028e0f`
- name: `?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800218c0`
- `0x180029040`
- `0x1800293b0`
- `0x1800295e4`
- `0x180029b4c`
- `0x18002a2f0`
- `0x18002a480`
- `0x18002a9a0`
- `0x18002ade0`
- `0x18002d4e0`
- `0x18002dbf0`

## callees

- `0x180028dc4`
- `0x180028e18`

## pseudocode

```c
__int64 __fastcall CBufferSourceManager::Complete(__int64 a1)
{
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 88) )
  {
    result = CBufferSourceManager::CompleteCopyBuffer_();
    if ( (int)result >= 0 )
      *(_DWORD *)(a1 + 72) = 0;
  }
  else
  {
    result = 2147549183LL;
  }
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_DWORD *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 96) = 0;
  return result;
}

```

## disassembly

```asm
0x180028dc4  push    rbx
0x180028dc6  sub     rsp, 20h
0x180028dca  cmp     qword ptr [rcx+58h], 0
0x180028dcf  mov     rbx, rcx
0x180028dd2  jz      short loc_180028DE6
0x180028dd4  call    ?CompleteCopyBuffer_@CBufferSourceManager@@AEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::CompleteCopyBuffer_(CTStickyVal<int> *)
0x180028dd9  test    eax, eax
0x180028ddb  js      short loc_180028DEB
0x180028ddd  mov     dword ptr [rbx+48h], 0
0x180028de4  jmp     short loc_180028DEB
0x180028de6  mov     eax, 8000FFFFh
0x180028deb  mov     qword ptr [rbx+68h], 0
0x180028df3  mov     qword ptr [rbx+58h], 0
0x180028dfb  mov     dword ptr [rbx+1Ch], 0
0x180028e02  mov     dword ptr [rbx+60h], 0
0x180028e09  add     rsp, 20h
0x180028e0d  pop     rbx
0x180028e0e  retn
```
