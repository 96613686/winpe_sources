# GetMsCryptKemKeyLength

- ea: `0x180064284`
- end: `0x1800642cd`
- name: `GetMsCryptKemKeyLength`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180063b00`
- `0x180065430`

## callees

- `0x18000ecb0`
- `0x180064284`

## string_xrefs

- `0x18006429f`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall GetMsCryptKemKeyLength(int a1, _DWORD *a2)
{
  unsigned int v2; // ebx

  v2 = 0;
  if ( (unsigned int)(a1 - 458753) < 2 )
  {
    *a2 = 40;
  }
  else
  {
    v2 = -1073741637;
    DebugTraceError(3221225659LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", 281);
  }
  return v2;
}

```

## disassembly

```asm
0x180064284  push    rbx
0x180064286  sub     rsp, 20h
0x18006428a  xor     ebx, ebx
0x18006428c  sub     ecx, 70001h
0x180064292  jz      short loc_1800642BE
0x180064294  cmp     ecx, 1
0x180064297  jz      short loc_1800642BE
0x180064299  mov     r9d, 119h
0x18006429f  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800642a6  lea     rdx, aStatus; "Status"
0x1800642ad  mov     ecx, 0C00000BBh
0x1800642b2  mov     ebx, 0C00000BBh
0x1800642b7  call    DebugTraceError
0x1800642bc  jmp     short loc_1800642C4
0x1800642be  mov     dword ptr [rdx], 28h ; '('
0x1800642c4  mov     eax, ebx
0x1800642c6  add     rsp, 20h
0x1800642ca  pop     rbx
0x1800642cb  retn
```
