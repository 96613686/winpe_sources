# _CWriteMap::CopyRecord_::_1_::catch$1

- ea: `0x1800142b8`
- end: `0x180014316`
- name: `_CWriteMap::CopyRecord_::_1_::catch$1`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000a990`
- `0x18001266c`
- `0x1800142b8`

## pseudocode

```c
void __fastcall __noreturn CWriteMap::CopyRecord_::_1_::catch_1(__int64 a1, __int64 a2)
{
  int v3; // ebx
  __int64 v4; // rdi

  v3 = *(_DWORD *)(a2 + 136) - 1;
  if ( v3 >= 0 )
  {
    v4 = *(_QWORD *)(a2 + 112);
    do
    {
      if ( *(_QWORD *)(32LL * v3 + v4 + 104) )
        CLogStorage::PutWriteBuffer(*(CLogStorage **)(v4 + 32), *(struct CBuffer **)(32LL * v3 + v4 + 104));
      --v3;
    }
    while ( v3 >= 0 );
  }
  *(_DWORD *)(a2 + 68) = *(_DWORD *)(a2 + 76);
  throw (long *)(a2 + 68);
}

```

## disassembly

```asm
0x1800142b8  mov     [rsp+arg_8], rdx
0x1800142bd  push    rbx
0x1800142be  push    rbp
0x1800142bf  push    rdi
0x1800142c0  sub     rsp, 30h
0x1800142c4  mov     rbp, rdx
0x1800142c7  mov     ebx, [rbp+88h]
0x1800142cd  sub     ebx, 1
0x1800142d0  js      short loc_1800142FF
0x1800142d2  mov     rdi, [rbp+70h]
0x1800142d6  movsxd  rax, ebx
0x1800142d9  shl     rax, 5
0x1800142dd  cmp     qword ptr [rax+rdi+68h], 0
0x1800142e3  jz      short loc_1800142FA
0x1800142e5  movsxd  rdx, ebx
0x1800142e8  shl     rdx, 5
0x1800142ec  mov     rdx, [rdx+rdi+68h]; struct CBuffer *
0x1800142f1  mov     rcx, [rdi+20h]; this
0x1800142f5  call    ?PutWriteBuffer@CLogStorage@@QEAAXPEAVCBuffer@@@Z; CLogStorage::PutWriteBuffer(CBuffer *)
0x1800142fa  sub     ebx, 1
0x1800142fd  jns     short loc_1800142D6
0x1800142ff  mov     eax, [rbp+4Ch]
0x180014302  mov     [rbp+44h], eax
0x180014305  lea     rdx, _TI1J; pThrowInfo
0x18001430c  lea     rcx, [rbp+44h]; pExceptionObject
0x180014310  call    _CxxThrowException_0
```
