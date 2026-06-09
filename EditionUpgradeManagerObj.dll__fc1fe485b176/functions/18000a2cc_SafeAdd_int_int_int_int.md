# SafeAdd<int>(int,int,int *)

- ea: `0x18000a2cc`
- end: `0x18000a33a`
- name: `??$SafeAdd@H@@YAJHHPEAH@Z`
- size: `110`
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
- `0x18000a2cc`

## pseudocode

```c
__int64 __fastcall SafeAdd<int>(int a1, __int64 a2, int *a3)
{
  int v4; // edi
  unsigned int v5; // ebx

  if ( a1 < 0 )
  {
    v5 = -2147024809;
    goto LABEL_10;
  }
  v4 = a1 + 1;
  if ( a1 + 1 < (unsigned int)a1 )
  {
    v5 = -2147024362;
    v4 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942934LL);
  }
  else
  {
    v5 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( (v5 & 0x80000000) != 0 )
    goto LABEL_10;
  if ( v4 < 0 )
  {
    v5 = -2147024362;
LABEL_10:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
    goto LABEL_11;
  }
  *a3 = v4;
LABEL_11:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000a2cc  mov     [rsp+arg_0], rbx
0x18000a2d1  mov     [rsp+arg_8], rsi
0x18000a2d6  push    rdi
0x18000a2d7  sub     rsp, 20h
0x18000a2db  mov     rsi, r8
0x18000a2de  test    ecx, ecx
0x18000a2e0  js      short loc_18000A315
0x18000a2e2  lea     edi, [rcx+1]
0x18000a2e5  cmp     edi, ecx
0x18000a2e7  jb      short loc_18000A2ED
0x18000a2e9  xor     ebx, ebx
0x18000a2eb  jmp     short loc_18000A2FB
0x18000a2ed  mov     ebx, 80070216h
0x18000a2f2  xor     edi, edi
0x18000a2f4  mov     ecx, ebx
0x18000a2f6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a2fb  mov     ecx, ebx
0x18000a2fd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a302  test    ebx, ebx
0x18000a304  js      short loc_18000A31A
0x18000a306  test    edi, edi
0x18000a308  jns     short loc_18000A311
0x18000a30a  mov     ebx, 80070216h
0x18000a30f  jmp     short loc_18000A31A
0x18000a311  mov     [rsi], edi
0x18000a313  jmp     short loc_18000A321
0x18000a315  mov     ebx, 80070057h
0x18000a31a  mov     ecx, ebx
0x18000a31c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000a321  mov     ecx, ebx
0x18000a323  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000a328  mov     rsi, [rsp+28h+arg_8]
0x18000a32d  mov     eax, ebx
0x18000a32f  mov     rbx, [rsp+28h+arg_0]
0x18000a334  add     rsp, 20h
0x18000a338  pop     rdi
0x18000a339  retn
```
