# wil::details::lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___::_lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___

- ea: `0x18000629c`
- end: `0x180006303`
- name: `wil::details::lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___::_lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___`
- size: `103`
- prototype: `_UNKNOWN **__fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180006c94`
- `0x1800080db`

## callees

- `0x180001930`
- `0x180006140`
- `0x18000629c`

## pseudocode

```c
_UNKNOWN **__fastcall wil::details::lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___::_lambda_call__lambda_7ef35568b0ec6ddb9fde9c0b9bdcc052___(
        __int64 a1)
{
  void *v2; // rcx
  _UNKNOWN **result; // rax

  if ( *(_BYTE *)(a1 + 8) )
  {
    *(_BYTE *)(a1 + 8) = 0;
    v2 = **(void ***)a1;
    if ( v2 )
    {
      operator delete(v2);
      **(_QWORD **)a1 = 0;
    }
    result = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      return (_UNKNOWN **)WPP_SF_(
                            *((_QWORD *)WPP_GLOBAL_Control + 2),
                            22,
                            &WPP_90890ce224d03ac7b34da71504f71581_Traceguids);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000629c  push    rbx
0x18000629e  sub     rsp, 20h
0x1800062a2  cmp     byte ptr [rcx+8], 0
0x1800062a6  mov     rbx, rcx
0x1800062a9  jz      short loc_1800062FD
0x1800062ab  mov     byte ptr [rcx+8], 0
0x1800062af  mov     rax, [rcx]
0x1800062b2  mov     rcx, [rax]; Block
0x1800062b5  test    rcx, rcx
0x1800062b8  jz      short loc_1800062C9
0x1800062ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800062bf  mov     rax, [rbx]
0x1800062c2  mov     qword ptr [rax], 0
0x1800062c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062d0  lea     rax, WPP_GLOBAL_Control
0x1800062d7  cmp     rcx, rax
0x1800062da  jz      short loc_1800062FD
0x1800062dc  test    byte ptr [rcx+1Ch], 1
0x1800062e0  jz      short loc_1800062FD
0x1800062e2  cmp     byte ptr [rcx+19h], 5
0x1800062e6  jb      short loc_1800062FD
0x1800062e8  mov     rcx, [rcx+10h]
0x1800062ec  lea     r8, WPP_90890ce224d03ac7b34da71504f71581_Traceguids
0x1800062f3  mov     edx, 16h
0x1800062f8  call    WPP_SF_
0x1800062fd  add     rsp, 20h
0x180006301  pop     rbx
0x180006302  retn
```
