# TieringJetSession::~TieringJetSession(void)

- ea: `0x1400188b8`
- end: `0x1400188e1`
- name: `??1TieringJetSession@@QEAA@XZ`
- size: `41`
- prototype: `void __fastcall(TieringJetSession *__hidden this)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c444`
- `0x14000c648`
- `0x14000d5f0`
- `0x14000ef74`
- `0x14000f108`
- `0x1400108e0`
- `0x140010d1c`
- `0x1400122fc`
- `0x140017120`
- `0x14001e2d4`
- `0x1400211a4`
- `0x14002eef0`
- `0x14003cfb4`
- `0x14003d800`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003eba8`
- `0x14003f4d8`

## callees

- `0x1400188b8`
- `0x1400197b0`
- `0x140019a50`

## pseudocode

```c
void __fastcall TieringJetSession::~TieringJetSession(TieringJetSession *this)
{
  if ( *(_BYTE *)this )
  {
    TieringJetSession::CloseJetTable(this, *(_BYTE *)(*((_QWORD *)this + 5) + 76LL));
  }
  else if ( *((_BYTE *)this + 34) )
  {
    TieringJetSession::DecrementSessionCount(this);
  }
}

```

## disassembly

```asm
0x1400188b8  sub     rsp, 28h
0x1400188bc  cmp     byte ptr [rcx], 0
0x1400188bf  jz      short loc_1400188D1
0x1400188c1  mov     rdx, [rcx+28h]
0x1400188c5  mov     dl, [rdx+4Ch]; bool
0x1400188c8  add     rsp, 28h
0x1400188cc  jmp     ?CloseJetTable@TieringJetSession@@QEAAJ_N@Z; TieringJetSession::CloseJetTable(bool)
0x1400188d1  cmp     byte ptr [rcx+22h], 0
0x1400188d5  jz      short loc_1400188DC
0x1400188d7  call    ?DecrementSessionCount@TieringJetSession@@AEAAXXZ; TieringJetSession::DecrementSessionCount(void)
0x1400188dc  add     rsp, 28h
0x1400188e0  retn
```
