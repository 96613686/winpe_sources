# CRegType<ushort *>::GetPointerDataSize(ushort const *,ulong *)

- ea: `0x18000c0cc`
- end: `0x18000c1ba`
- name: `?GetPointerDataSize@?$CRegType@PEAG@@SAJPEBGPEAK@Z`
- size: `238`
- prototype: `__int64 __fastcall(_WORD *, _DWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800156d0`
- `0x180015864`
- `0x1800161b0`
- `0x180016320`

## callees

- `0x1800090dc`
- `0x180009480`
- `0x18000c0cc`

## pseudocode

```c
__int64 __fastcall CRegType<unsigned short *>::GetPointerDataSize(_WORD *a1, _DWORD *a2)
{
  int v3; // ebp
  __int64 v4; // r8
  int v5; // ebx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rsi
  unsigned __int64 v8; // rdx
  int v9; // edi

  v3 = 0;
  if ( a1 )
  {
    v4 = 0x3FFFFFFF;
    do
    {
      if ( !*a1 )
        break;
      ++a1;
      --v4;
    }
    while ( v4 );
    v5 = v4 == 0 ? 0x80070057 : 0;
    if ( v4 )
    {
      v6 = (2 * (0x3FFFFFFF - v4)) & -(__int64)(v4 != 0);
      v7 = v6 + 2;
      if ( v6 + 2 < v6 )
      {
        v5 = -2147024362;
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        v7 = v8;
      }
      else
      {
        v5 = 0;
      }
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
      if ( v5 >= 0 )
      {
        v9 = v7;
        if ( v7 == (unsigned int)v7 )
        {
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
          v5 = 0;
        }
        else
        {
          v5 = -2147024362;
          v9 = 0;
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024362);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
        if ( v5 >= 0 )
        {
          v3 = v9;
          goto LABEL_17;
        }
      }
    }
  }
  else
  {
    v5 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
LABEL_17:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  if ( v5 >= 0 )
    *a2 = v3;
  else
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v5);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c0cc  push    rbx
0x18000c0ce  push    rbp
0x18000c0cf  push    rsi
0x18000c0d0  push    rdi
0x18000c0d1  push    r14
0x18000c0d3  push    r15
0x18000c0d5  sub     rsp, 28h
0x18000c0d9  xor     r15d, r15d
0x18000c0dc  mov     r14, rdx
0x18000c0df  mov     ebp, r15d
0x18000c0e2  test    rcx, rcx
0x18000c0e5  jz      loc_18000C181
0x18000c0eb  mov     r9d, 3FFFFFFFh
0x18000c0f1  mov     r8d, r9d
0x18000c0f4  cmp     [rcx], r15w
0x18000c0f8  jz      short loc_18000C104
0x18000c0fa  add     rcx, 2
0x18000c0fe  sub     r8, 1
0x18000c102  jnz     short loc_18000C0F4
0x18000c104  mov     rax, r8
0x18000c107  neg     rax
0x18000c10a  sbb     ebx, ebx
0x18000c10c  not     ebx
0x18000c10e  and     ebx, 80070057h
0x18000c114  test    r8, r8
0x18000c117  jz      short loc_18000C186
0x18000c119  sub     r9, r8
0x18000c11c  add     r9, r9
0x18000c11f  neg     r8
0x18000c122  sbb     rdx, rdx
0x18000c125  and     rdx, r9
0x18000c128  lea     rsi, [rdx+2]
0x18000c12c  cmp     rsi, rdx
0x18000c12f  jb      short loc_18000C136
0x18000c131  mov     ebx, r15d
0x18000c134  jmp     short loc_18000C145
0x18000c136  mov     ebx, 80070216h
0x18000c13b  mov     ecx, ebx
0x18000c13d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c142  mov     rsi, rdx
0x18000c145  mov     ecx, ebx
0x18000c147  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c14c  test    ebx, ebx
0x18000c14e  js      short loc_18000C186
0x18000c150  mov     edi, esi
0x18000c152  cmp     rsi, rdi
0x18000c155  jz      short loc_18000C168
0x18000c157  mov     ebx, 80070216h
0x18000c15c  mov     edi, r15d
0x18000c15f  mov     ecx, ebx
0x18000c161  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c166  jmp     short loc_18000C172
0x18000c168  xor     ecx, ecx
0x18000c16a  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c16f  mov     ebx, r15d
0x18000c172  mov     ecx, ebx
0x18000c174  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c179  test    ebx, ebx
0x18000c17b  js      short loc_18000C186
0x18000c17d  mov     ebp, edi
0x18000c17f  jmp     short loc_18000C18D
0x18000c181  mov     ebx, 80070057h
0x18000c186  mov     ecx, ebx
0x18000c188  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c18d  mov     ecx, ebx
0x18000c18f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c194  test    ebx, ebx
0x18000c196  jns     short loc_18000C1A1
0x18000c198  mov     ecx, ebx
0x18000c19a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000c19f  jmp     short loc_18000C1A4
0x18000c1a1  mov     [r14], ebp
0x18000c1a4  mov     ecx, ebx
0x18000c1a6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000c1ab  mov     eax, ebx
0x18000c1ad  add     rsp, 28h
0x18000c1b1  pop     r15
0x18000c1b3  pop     r14
0x18000c1b5  pop     rdi
0x18000c1b6  pop     rsi
0x18000c1b7  pop     rbp
0x18000c1b8  pop     rbx
0x18000c1b9  retn
```
