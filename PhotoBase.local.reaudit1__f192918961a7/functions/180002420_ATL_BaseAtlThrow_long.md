# ATL::BaseAtlThrow(long)

- ea: `0x180002420`
- end: `0x18000242a`
- name: `?BaseAtlThrow@ATL@@YAXJ@Z`
- size: `10`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `31`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025e8`
- `0x180002650`
- `0x180002a24`
- `0x180002e70`
- `0x180004000`
- `0x18000408c`
- `0x180004128`
- `0x1800041b4`
- `0x1800043dc`
- `0x1800045f4`
- `0x1800049c0`
- `0x1800049f0`
- `0x180004b14`
- `0x180004c6c`
- `0x180004dd8`
- `0x180005208`
- `0x180005388`
- `0x18000558c`
- `0x180005744`
- `0x180005874`
- `0x1800059a4`
- `0x180005ad4`
- `0x180005fbc`
- `0x1800060d0`
- `0x18000613c`
- `0x1800062bc`
- `0x180006388`
- `0x1800066dc`
- `0x180006880`
- `0x1800069e4`
- `0x180006cd0`

## callees

- `0x18000247c`

## pseudocode

```c
void __fastcall __noreturn ATL::BaseAtlThrow(BasePrivate *a1, int a2)
{
  BasePrivate::ThrowImpl(a1, a2);
}

```

## disassembly

```asm
0x180002420  sub     rsp, 28h; void ATL::BaseAtlThrow(long)
0x180002424  call    ?ThrowImpl@BasePrivate@@YAXJ@Z; BasePrivate::ThrowImpl(long)
```
