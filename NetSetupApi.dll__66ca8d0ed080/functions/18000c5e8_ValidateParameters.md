# ValidateParameters

- ea: `0x18000c5e8`
- end: `0x18000c652`
- name: `ValidateParameters`
- size: `106`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c660`
- `0x18000c760`
- `0x18000c960`
- `0x18000ca10`

## callees

- `0x18000c5e8`
- `0x18000cab4`

## pseudocode

```c
__int64 __fastcall ValidateParameters(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rcx
  __int64 v3; // rdx

  if ( !a1 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 2147942487LL;
    v3 = 10;
LABEL_9:
    WPP_SF_(v2[2], v3, WPP_8228437e81df3f2b17e42002fd9073a5_Traceguids);
    return 2147942487LL;
  }
  if ( !a2 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      return 2147942487LL;
    v3 = 11;
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c5e8  sub     rsp, 28h
0x18000c5ec  test    rcx, rcx
0x18000c5ef  jnz     short loc_18000C611
0x18000c5f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c5f8  lea     rax, WPP_GLOBAL_Control
0x18000c5ff  cmp     rcx, rax
0x18000c602  jz      short loc_18000C644
0x18000c604  cmp     byte ptr [rcx+19h], 2
0x18000c608  jb      short loc_18000C644
0x18000c60a  mov     edx, 0Ah
0x18000c60f  jmp     short loc_18000C634
0x18000c611  test    rdx, rdx
0x18000c614  jnz     short loc_18000C64B
0x18000c616  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c61d  lea     rax, WPP_GLOBAL_Control
0x18000c624  cmp     rcx, rax
0x18000c627  jz      short loc_18000C644
0x18000c629  cmp     byte ptr [rcx+19h], 2
0x18000c62d  jb      short loc_18000C644
0x18000c62f  mov     edx, 0Bh
0x18000c634  mov     rcx, [rcx+10h]
0x18000c638  lea     r8, WPP_8228437e81df3f2b17e42002fd9073a5_Traceguids
0x18000c63f  call    WPP_SF_
0x18000c644  mov     eax, 80070057h
0x18000c649  jmp     short loc_18000C64D
0x18000c64b  xor     eax, eax
0x18000c64d  add     rsp, 28h
0x18000c651  retn
```
