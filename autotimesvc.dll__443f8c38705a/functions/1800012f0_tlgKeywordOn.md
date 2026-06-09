# _tlgKeywordOn

- ea: `0x1800012f0`
- end: `0x180001316`
- name: `_tlgKeywordOn`
- size: `38`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `57`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c64`
- `0x180005f40`
- `0x1800061ac`
- `0x180006350`
- `0x180006598`
- `0x180007220`
- `0x18000743c`
- `0x180007534`
- `0x180007a5c`
- `0x180008100`
- `0x1800084c4`
- `0x180008798`
- `0x18000891c`
- `0x1800096b0`
- `0x1800098d4`
- `0x180009934`
- `0x180009bb8`
- `0x180009d88`
- `0x18000ad28`
- `0x18000af0c`
- `0x18000b118`
- `0x18000b264`
- `0x18000b3b8`
- `0x18000b668`
- `0x18000b86c`
- `0x18000bd34`
- `0x18000bea8`
- `0x18000bf30`
- `0x18000c300`
- `0x18000c450`
- `0x18000c6a8`
- `0x18000c720`
- `0x18000c7ac`
- `0x18000c900`
- `0x18000caf0`
- `0x18000cc10`
- `0x18000cf10`
- `0x18000d0ec`
- `0x18000d178`
- `0x18000d330`
- `0x18000d720`
- `0x18000e048`
- `0x18000e440`
- `0x18000e550`
- `0x18000e6f8`
- `0x18000edd8`
- `0x18000ee3c`
- `0x18000eef0`
- `0x18000efb8`
- `0x18000f6e0`

## callees

- `0x1800012f0`

## pseudocode

```c
bool __fastcall tlgKeywordOn(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  bool result; // al

  result = 1;
  if ( a2 )
  {
    v3 = *(_QWORD *)(a1 + 24);
    if ( (*(_QWORD *)(a1 + 16) & a2) == 0 || (a2 & v3) != v3 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800012f0  mov     rax, rcx
0x1800012f3  test    rdx, rdx
0x1800012f6  jz      short loc_180001310
0x1800012f8  mov     rcx, [rcx+18h]
0x1800012fc  mov     rax, [rax+10h]
0x180001300  test    rdx, rax
0x180001303  jz      short loc_180001313
0x180001305  mov     rax, rcx
0x180001308  and     rax, rdx
0x18000130b  cmp     rax, rcx
0x18000130e  jnz     short loc_180001313
0x180001310  mov     al, 1
0x180001312  retn
0x180001313  xor     al, al
0x180001315  retn
```
