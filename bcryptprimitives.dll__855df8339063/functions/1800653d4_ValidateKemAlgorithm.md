# ValidateKemAlgorithm

- ea: `0x1800653d4`
- end: `0x180065428`
- name: `ValidateKemAlgorithm`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800645f0`
- `0x180064ef0`
- `0x180064ff0`

## callees

- `0x18000ecb0`
- `0x1800653d4`

## string_xrefs

- `0x180065402`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall ValidateKemAlgorithm(_DWORD *a1, _QWORD *a2)
{
  __int64 v2; // r9
  unsigned int v3; // ebx

  if ( !a1 )
  {
    v2 = 235;
LABEL_7:
    v3 = -1073741811;
    DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v2);
    return v3;
  }
  if ( a1[1] != 1297302849 || *a1 != 12 )
  {
    v2 = 245;
    goto LABEL_7;
  }
  v3 = 0;
  *a2 = a1;
  return v3;
}

```

## disassembly

```asm
0x1800653d4  push    rbx
0x1800653d6  sub     rsp, 20h
0x1800653da  test    rcx, rcx
0x1800653dd  jnz     short loc_1800653E7
0x1800653df  mov     r9d, 0EBh
0x1800653e5  jmp     short loc_180065402
0x1800653e7  cmp     dword ptr [rcx+4], 4D534541h
0x1800653ee  jnz     short loc_1800653FC
0x1800653f0  cmp     dword ptr [rcx], 0Ch
0x1800653f3  jnz     short loc_1800653FC
0x1800653f5  xor     ebx, ebx
0x1800653f7  mov     [rdx], rcx
0x1800653fa  jmp     short loc_18006541F
0x1800653fc  mov     r9d, 0F5h
0x180065402  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180065409  mov     ecx, 0C000000Dh
0x18006540e  lea     rdx, aStatus; "Status"
0x180065415  mov     ebx, 0C000000Dh
0x18006541a  call    DebugTraceError
0x18006541f  mov     eax, ebx
0x180065421  add     rsp, 20h
0x180065425  pop     rbx
0x180065426  retn
```
