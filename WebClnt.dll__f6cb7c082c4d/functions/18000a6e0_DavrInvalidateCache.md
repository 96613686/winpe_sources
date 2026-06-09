# DavrInvalidateCache

- ea: `0x18000a6e0`
- end: `0x18000a769`
- name: `DavrInvalidateCache`
- size: `137`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000a6e0`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18002bb70`

## pseudocode

```c
__int64 __fastcall DavrInvalidateCache(__int64 a1, __int64 a2)
{
  void *v3; // rcx
  unsigned int v5; // eax
  unsigned int v6; // ebx

  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a2);
  if ( !a2 )
    return 87;
  v5 = TfsInvalidateEntry(v3, a2);
  v6 = v5;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 187, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v5);
  return v6;
}

```

## disassembly

```asm
0x18000a6e0  mov     [rsp+arg_0], rbx
0x18000a6e5  push    rdi
0x18000a6e6  sub     rsp, 20h
0x18000a6ea  mov     rbx, rdx
0x18000a6ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a6f4  lea     rdi, WPP_GLOBAL_Control
0x18000a6fb  cmp     rcx, rdi
0x18000a6fe  jz      short loc_18000A71E
0x18000a700  test    byte ptr [rcx+1Ch], 2
0x18000a704  jz      short loc_18000A71E
0x18000a706  mov     rcx, [rcx+10h]
0x18000a70a  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a711  mov     edx, 0BAh
0x18000a716  mov     r9, rbx
0x18000a719  call    WPP_SF_S
0x18000a71e  test    rbx, rbx
0x18000a721  jnz     short loc_18000A728
0x18000a723  lea     eax, [rbx+57h]
0x18000a726  jmp     short loc_18000A75E
0x18000a728  mov     rdx, rbx
0x18000a72b  call    TfsInvalidateEntry
0x18000a730  mov     ebx, eax
0x18000a732  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a739  cmp     rcx, rdi
0x18000a73c  jz      short loc_18000A75C
0x18000a73e  test    byte ptr [rcx+1Ch], 2
0x18000a742  jz      short loc_18000A75C
0x18000a744  mov     rcx, [rcx+10h]
0x18000a748  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a74f  mov     edx, 0BBh
0x18000a754  mov     r9d, eax
0x18000a757  call    WPP_SF_d
0x18000a75c  mov     eax, ebx
0x18000a75e  mov     rbx, [rsp+28h+arg_0]
0x18000a763  add     rsp, 20h
0x18000a767  pop     rdi
0x18000a768  retn
```
