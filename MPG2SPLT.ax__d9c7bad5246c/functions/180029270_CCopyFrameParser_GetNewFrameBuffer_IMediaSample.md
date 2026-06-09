# CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)

- ea: `0x180029270`
- end: `0x1800292bf`
- name: `?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z`
- size: `79`
- prototype: `__int64 __fastcall(CCopyFrameParser *__hidden this, struct IMediaSample *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x180029b4c`
- `0x18002a2f0`
- `0x18002a480`
- `0x18002a9a0`

## callees

- `0x180029208`
- `0x180029270`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall CCopyFrameParser::GetNewFrameBuffer(CCopyFrameParser *this, struct IMediaSample *a2)
{
  __int64 result; // rax
  struct IMediaSample *v4; // [rsp+38h] [rbp+10h] BYREF

  v4 = a2;
  LODWORD(v4) = *((_DWORD *)this + 94);
  result = CBufferSourceManager::GetNewCopyBuffer((CCopyFrameParser *)((char *)this + 48), (int *)&v4);
  if ( (int)result >= 0 && (int)v4 < *((_DWORD *)this + 94) )
  {
    (*(void (__fastcall **)(CCopyFrameParser *))(*(_QWORD *)this + 24LL))(this);
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180029270  mov     [rsp+arg_8], rdx
0x180029275  push    rbx
0x180029276  sub     rsp, 20h
0x18002927a  mov     eax, [rcx+178h]
0x180029280  lea     rdx, [rsp+28h+arg_8]; int *
0x180029285  mov     rbx, rcx
0x180029288  mov     dword ptr [rsp+28h+arg_8], eax
0x18002928c  add     rcx, 30h ; '0'; this
0x180029290  call    ?GetNewCopyBuffer@CBufferSourceManager@@IEAAJPEAH@Z; CBufferSourceManager::GetNewCopyBuffer(int *)
0x180029295  test    eax, eax
0x180029297  js      short loc_1800292B9
0x180029299  mov     edx, [rbx+178h]
0x18002929f  cmp     dword ptr [rsp+28h+arg_8], edx
0x1800292a3  jge     short loc_1800292B9
0x1800292a5  mov     rax, [rbx]
0x1800292a8  mov     rcx, rbx
0x1800292ab  mov     rax, [rax+18h]
0x1800292af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292b4  mov     eax, 80004005h
0x1800292b9  add     rsp, 20h
0x1800292bd  pop     rbx
0x1800292be  retn
```
