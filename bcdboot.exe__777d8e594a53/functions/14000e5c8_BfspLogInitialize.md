# BfspLogInitialize

- ea: `0x14000e5c8`
- end: `0x14000e622`
- name: `BfspLogInitialize`
- size: `90`
- prototype: `__int64 __fastcall(int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140003d30`
- `0x140004080`
- `0x140009658`
- `0x140009fd4`
- `0x140010728`

## callees

- `0x14000e5c8`
- `0x140013334`

## pseudocode

```c
__int64 __fastcall BfspLogInitialize(int a1)
{
  if ( !LogEnabled && a1 < 5 )
  {
    if ( !BcdLogInitialized )
      BcdLogInitialized = (int)BcdSetLogging(3, BcdLogCallback) >= 0;
    FilterLevel = a1;
    LogInitialized = 1;
    LogEnabled = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14000e5c8  push    rbx
0x14000e5ca  sub     rsp, 20h
0x14000e5ce  cmp     cs:LogEnabled, 0
0x14000e5d5  mov     ebx, ecx
0x14000e5d7  jnz     short loc_14000E61A
0x14000e5d9  cmp     ecx, 5
0x14000e5dc  jge     short loc_14000E61A
0x14000e5de  cmp     cs:BcdLogInitialized, 0
0x14000e5e5  jnz     short loc_14000E603
0x14000e5e7  lea     rdx, BcdLogCallback
0x14000e5ee  mov     ecx, 3
0x14000e5f3  call    BcdSetLogging
0x14000e5f8  not     eax
0x14000e5fa  shr     eax, 1Fh
0x14000e5fd  mov     cs:BcdLogInitialized, eax
0x14000e603  mov     eax, 1
0x14000e608  mov     cs:FilterLevel, ebx
0x14000e60e  mov     cs:LogInitialized, eax
0x14000e614  mov     cs:LogEnabled, eax
0x14000e61a  xor     eax, eax
0x14000e61c  add     rsp, 20h
0x14000e620  pop     rbx
0x14000e621  retn
```
