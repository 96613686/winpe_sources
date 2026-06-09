# SafeMul<int>(int,int,int *)

- ea: `0x18000a340`
- end: `0x18000a3b6`
- name: `??$SafeMul@H@@YAJHHPEAH@Z`
- size: `118`
- prototype: `__int64 __fastcall(int, __int64, int *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a4c0`
- `0x180014800`
- `0x180014ba0`
- `0x180018044`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000a340`

## pseudocode

```c
__int64 __fastcall SafeMul<int>(int a1, __int64 a2, int *a3)
{
  int v4; // edi
  unsigned int v5; // ebx

  if ( a1 < 0 )
  {
    v5 = -2147024809;
    goto LABEL_12;
  }
  if ( a1 )
  {
    v4 = 2 * a1;
    if ( (unsigned int)(2 * a1) >> 1 != a1 )
    {
      v5 = -2147024362;
      v4 = 0;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
      goto LABEL_7;
    }
  }
  else
  {
    v4 = 0;
  }
  v5 = 0;
LABEL_7:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
  {
LABEL_12:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_13;
  }
  if ( v4 < 0 )
  {
    v5 = -2147024362;
    goto LABEL_12;
  }
  *a3 = v4;
LABEL_13:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000a340  mov     [rsp+arg_0], rbx
0x18000a345  mov     [rsp+arg_8], rsi
0x18000a34a  push    rdi
0x18000a34b  sub     rsp, 20h
0x18000a34f  mov     rsi, r8
0x18000a352  test    ecx, ecx
0x18000a354  js      short loc_18000A391
0x18000a356  jz      short loc_18000A373
0x18000a358  lea     edi, [rcx+rcx]
0x18000a35b  mov     eax, edi
0x18000a35d  shr     eax, 1
0x18000a35f  cmp     eax, ecx
0x18000a361  jz      short loc_18000A375
0x18000a363  mov     ebx, 80070216h
0x18000a368  xor     edi, edi
0x18000a36a  mov     ecx, ebx
0x18000a36c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a371  jmp     short loc_18000A377
0x18000a373  xor     edi, edi
0x18000a375  xor     ebx, ebx
0x18000a377  mov     ecx, ebx
0x18000a379  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a37e  test    ebx, ebx
0x18000a380  js      short loc_18000A396
0x18000a382  test    edi, edi
0x18000a384  jns     short loc_18000A38D
0x18000a386  mov     ebx, 80070216h
0x18000a38b  jmp     short loc_18000A396
0x18000a38d  mov     [rsi], edi
0x18000a38f  jmp     short loc_18000A39D
0x18000a391  mov     ebx, 80070057h
0x18000a396  mov     ecx, ebx
0x18000a398  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a39d  mov     ecx, ebx
0x18000a39f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a3a4  mov     rsi, [rsp+28h+arg_8]
0x18000a3a9  mov     eax, ebx
0x18000a3ab  mov     rbx, [rsp+28h+arg_0]
0x18000a3b0  add     rsp, 20h
0x18000a3b4  pop     rdi
0x18000a3b5  retn
```
