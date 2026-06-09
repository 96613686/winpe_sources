# PrjfGetUnionContextByVirtualizationInstanceInfo

- ea: `0x140021f8c`
- end: `0x140022084`
- name: `PrjfGetUnionContextByVirtualizationInstanceInfo`
- size: `248`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x14000420c`
- `0x14002f134`
- `0x14002f204`
- `0x14002f5f0`
- `0x1400306f8`
- `0x1400333c4`
- `0x140035238`
- `0x140035f3c`
- `0x1400368c4`

## callees

- `0x140003480`
- `0x14000d008`
- `0x140021f8c`

## pseudocode

```c
_QWORD *__fastcall PrjfGetUnionContextByVirtualizationInstanceInfo(__int128 *a1, struct _FLT_INSTANCE *a2)
{
  __int64 v2; // rbx
  __int128 v4; // [rsp+50h] [rbp-18h] BYREF

  v2 = 0;
  if ( a1 )
  {
    if ( *((_DWORD *)a1 + 4) == -1879048164 )
    {
      v4 = *a1;
      return PrjfGetUnionContext(a2, &v4);
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 2;
      WPP_RECORDER_AND_TRACE_SF_sD(
        521,
        (_DWORD)a2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        9,
        41,
        (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
        195);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 2) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(a2) = BYTE1(xmmword_14001A3D0) & 2;
    WPP_RECORDER_AND_TRACE_SF_sD(
      521,
      (_DWORD)a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      9,
      40,
      (__int64)WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\context.c",
      189);
  }
  return (_QWORD *)v2;
}

```

## disassembly

```asm
0x140021f8c  push    rbx
0x140021f8e  sub     rsp, 60h
0x140021f92  xor     ebx, ebx
0x140021f94  mov     rax, rdx
0x140021f97  test    rcx, rcx
0x140021f9a  jnz     short loc_14002200D
0x140021f9c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140021fa2  lea     rax, WPP_RECORDER_INITIALIZED
0x140021fa9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021fb0  setnz   r8b
0x140021fb4  and     dl, 2
0x140021fb7  jnz     short loc_140021FC2
0x140021fb9  test    r8b, r8b
0x140021fbc  jz      loc_14002207A
0x140021fc2  mov     [rsp+68h+var_20], 8BDh
0x140021fca  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140021fd1  mov     [rsp+68h+var_28], rax
0x140021fd6  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140021fdd  mov     [rsp+68h+var_30], rax
0x140021fe2  mov     [rsp+68h+var_38], 28h ; '('
0x140021fe9  mov     r9, cs:WPP_GLOBAL_Control
0x140021ff0  mov     ecx, 209h
0x140021ff5  mov     [rsp+68h+var_40], 9
0x140021ffd  mov     [rsp+68h+var_48], 2
0x140022002  mov     r9, [r9+40h]
0x140022006  call    WPP_RECORDER_AND_TRACE_SF_sD
0x14002200b  jmp     short loc_14002207A
0x14002200d  cmp     dword ptr [rcx+10h], 9000001Ch
0x140022014  jz      short loc_140022061
0x140022016  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002201c  lea     rax, WPP_RECORDER_INITIALIZED
0x140022023  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002202a  setnz   r8b
0x14002202e  and     dl, 2
0x140022031  jnz     short loc_140022038
0x140022033  test    r8b, r8b
0x140022036  jz      short loc_14002207A
0x140022038  mov     [rsp+68h+var_20], 8C3h
0x140022040  lea     rax, aOnecoreBaseFsG_7; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140022047  mov     [rsp+68h+var_28], rax
0x14002204c  lea     rax, WPP_428015d65e5a38c78b9ccff1fa78a732_Traceguids
0x140022053  mov     [rsp+68h+var_30], rax
0x140022058  mov     [rsp+68h+var_38], 29h ; ')'
0x14002205f  jmp     short loc_140021FE9
0x140022061  movups  xmm0, xmmword ptr [rcx]
0x140022064  lea     rdx, [rsp+68h+var_18]
0x140022069  mov     rcx, rax
0x14002206c  movdqu  [rsp+68h+var_18], xmm0
0x140022072  call    PrjfGetUnionContext
0x140022077  mov     rbx, rax
0x14002207a  mov     rax, rbx
0x14002207d  add     rsp, 60h
0x140022081  pop     rbx
0x140022082  retn
```
