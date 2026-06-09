# BcdQueryObject

- ea: `0x1400140c4`
- end: `0x14001412a`
- name: `BcdQueryObject`
- size: `102`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x140003d30`
- `0x140004e98`
- `0x140005b98`
- `0x140005fc4`
- `0x140025368`

## callees

- `0x1400133e4`
- `0x1400140c4`
- `0x140014650`
- `0x14001ae94`
- `0x14001c014`

## pseudocode

```c
__int64 __fastcall BcdQueryObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // rbp
  int v7; // eax
  unsigned int ObjectIdentifier; // ebx
  __int64 v9; // rcx

  v5 = a1;
  if ( !a4 )
    return 3221225485LL;
  LOBYTE(a1) = a1 & 1;
  v7 = BiAcquireBcdSyncMutant(a1);
  ObjectIdentifier = v7;
  if ( v7 >= 0 )
  {
    ObjectIdentifier = BiGetObjectIdentifier(v5, a4);
    LOBYTE(v9) = v5 & 1;
    BiReleaseBcdSyncMutant(v9);
  }
  else
  {
    BiLogMessage(4, L"BcdQueryObject: Failed to acquire BCD sync mutant. Status: %x", (unsigned int)v7);
  }
  return ObjectIdentifier;
}

```

## disassembly

```asm
0x1400140c4  push    rbx
0x1400140c6  push    rbp
0x1400140c7  push    rsi
0x1400140c8  push    rdi
0x1400140c9  sub     rsp, 28h
0x1400140cd  mov     rsi, r9
0x1400140d0  mov     rbp, rcx
0x1400140d3  test    r9, r9
0x1400140d6  jnz     short loc_1400140DF
0x1400140d8  mov     eax, 0C000000Dh
0x1400140dd  jmp     short loc_140014121
0x1400140df  mov     dil, bpl
0x1400140e2  and     dil, 1
0x1400140e6  mov     cl, dil
0x1400140e9  call    BiAcquireBcdSyncMutant
0x1400140ee  mov     ebx, eax
0x1400140f0  test    eax, eax
0x1400140f2  jns     short loc_14001410A
0x1400140f4  mov     r8d, eax
0x1400140f7  lea     rdx, aBcdqueryobject; "BcdQueryObject: Failed to acquire BCD s"...
0x1400140fe  mov     ecx, 4
0x140014103  call    BiLogMessage
0x140014108  jmp     short loc_14001411F
0x14001410a  mov     rdx, rsi
0x14001410d  mov     rcx, rbp
0x140014110  call    BiGetObjectIdentifier
0x140014115  mov     ebx, eax
0x140014117  mov     cl, dil
0x14001411a  call    BiReleaseBcdSyncMutant
0x14001411f  mov     eax, ebx
0x140014121  add     rsp, 28h
0x140014125  pop     rdi
0x140014126  pop     rsi
0x140014127  pop     rbp
0x140014128  pop     rbx
0x140014129  retn
```
