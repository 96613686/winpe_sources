# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>(void)

- ea: `0x18000d420`
- end: `0x18000d48a`
- name: `??1?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027f0b`
- `0x180028082`

## callees

- `0x180009660`
- `0x18000d420`
- `0x1800268f4`

## pseudocode

```c
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::~list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>(
        __int64 a1)
{
  _QWORD **v1; // rax
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx

  v1 = *(_QWORD ***)(a1 + 8);
  v3 = *v1;
  *v1 = v1;
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 16) = 0;
  if ( v3 != *(_QWORD **)(a1 + 8) )
  {
    do
    {
      v4 = (_QWORD *)*v3;
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD((Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v3 + 2));
      operator delete(v3);
      v3 = v4;
    }
    while ( v4 != *(_QWORD **)(a1 + 8) );
  }
  operator delete(*(void **)(a1 + 8));
  *(_QWORD *)(a1 + 8) = 0;
}

```

## disassembly

```asm
0x18000d420  mov     [rsp+arg_0], rbx
0x18000d425  mov     [rsp+arg_8], rsi
0x18000d42a  push    rdi
0x18000d42b  sub     rsp, 20h
0x18000d42f  mov     rax, [rcx+8]
0x18000d433  mov     rdi, rcx
0x18000d436  mov     rsi, [rax]
0x18000d439  mov     [rax], rax
0x18000d43c  mov     rax, [rcx+8]
0x18000d440  mov     [rax+8], rax
0x18000d444  and     qword ptr [rcx+10h], 0
0x18000d449  cmp     rsi, [rcx+8]
0x18000d44d  jz      short loc_18000D46C
0x18000d44f  mov     rbx, [rsi]
0x18000d452  lea     rcx, [rsi+10h]; this
0x18000d456  call    ??1CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Performance::CCvDDCache::CCvDD::~CCvDD(void)
0x18000d45b  mov     rcx, rsi; Block
0x18000d45e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d463  mov     rsi, rbx
0x18000d466  cmp     rbx, [rdi+8]
0x18000d46a  jnz     short loc_18000D44F
0x18000d46c  mov     rcx, [rdi+8]; Block
0x18000d470  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d475  and     qword ptr [rdi+8], 0
0x18000d47a  mov     rbx, [rsp+28h+arg_0]
0x18000d47f  mov     rsi, [rsp+28h+arg_8]
0x18000d484  add     rsp, 20h
0x18000d488  pop     rdi
0x18000d489  retn
```
