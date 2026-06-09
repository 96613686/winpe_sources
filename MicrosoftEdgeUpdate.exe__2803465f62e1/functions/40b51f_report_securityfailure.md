# ___report_securityfailure

- ea: `0x40b51f`
- end: `0x40b5ee`
- name: `___report_securityfailure`
- size: `207`
- prototype: `void __usercall __noreturn(int@<ebx>, int@<edi>, int@<esi>, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40b513`

## callees

- `0x40b3f1`
- `0x40b51f`

## import_xrefs

- `KERNEL32!IsProcessorFeaturePresent` at `0x40b52a`
- `KERNEL32!IsProcessorFeaturePresent` at `0x40b52a`

## pseudocode

```c
void __usercall __noreturn __report_securityfailure(int a1@<ebx>, int a2@<edi>, int a3@<esi>, unsigned int a4)
{
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // kr00_4
  int vars0; // [esp+31Ch] [ebp+0h]
  int retaddr; // [esp+320h] [ebp+4h]

  if ( IsProcessorFeaturePresent(0x17u) )
    __fastfail(a4);
  dword_417AB0 = 0;
  dword_417AAC = v5;
  dword_417AA8 = v4;
  dword_417AA4 = a1;
  dword_417AA0 = a3;
  dword_417A9C = a2;
  word_417AC8 = __SS__;
  word_417ABC = __CS__;
  word_417A98 = __DS__;
  word_417A94 = __ES__;
  word_417A90 = __FS__;
  word_417A8C = __GS__;
  v6 = __readeflags();
  dword_417AC0 = v6;
  dword_417AB4 = vars0;
  dword_417AB8 = retaddr;
  dword_417AC4 = (int)&a4;
  dword_4179BC = retaddr;
  dword_4179B0 = -1073740791;
  dword_4179B4 = 1;
  dword_4179C0 = 1;
  dword_4179C4 = a4;
  __raise_securityfailure((struct _EXCEPTION_POINTERS *)&ExceptionInfo);
}

```

## disassembly

```asm
0x40b51f  push    ebp
0x40b520  mov     ebp, esp
0x40b522  sub     esp, 31Ch
0x40b528  push    17h; ProcessorFeature
0x40b52a  call    ds:IsProcessorFeaturePresent
0x40b530  test    eax, eax
0x40b532  jz      short loc_40B539
0x40b534  mov     ecx, [ebp+arg_0]
0x40b537  int     29h; Win8: RtlFailFast(ecx)
0x40b539  mov     dword_417AB0, eax
0x40b53e  mov     dword_417AAC, ecx
0x40b544  mov     dword_417AA8, edx
0x40b54a  mov     dword_417AA4, ebx
0x40b550  mov     dword_417AA0, esi
0x40b556  mov     dword_417A9C, edi
0x40b55c  mov     word_417AC8, ss
0x40b563  mov     word_417ABC, cs
0x40b56a  mov     word_417A98, ds
0x40b571  mov     word_417A94, es
0x40b578  mov     word_417A90, fs
0x40b57f  mov     word_417A8C, gs
0x40b586  pushf
0x40b587  pop     dword_417AC0
0x40b58d  mov     eax, [ebp+var_s0]
0x40b590  mov     dword_417AB4, eax
0x40b595  mov     eax, [ebp+4]
0x40b598  mov     dword_417AB8, eax
0x40b59d  lea     eax, [ebp+arg_0]
0x40b5a0  mov     dword_417AC4, eax
0x40b5a5  mov     eax, [ebp+var_31C]
0x40b5ab  mov     eax, dword_417AB8
0x40b5b0  mov     dword_4179BC, eax
0x40b5b5  mov     dword_4179B0, 0C0000409h
0x40b5bf  mov     dword_4179B4, 1
0x40b5c9  mov     dword_4179C0, 1
0x40b5d3  push    4
0x40b5d5  pop     eax
0x40b5d6  imul    eax, 0
0x40b5d9  mov     ecx, [ebp+arg_0]
0x40b5dc  mov     dword_4179C4[eax], ecx
0x40b5e2  push    offset ExceptionInfo; ExceptionInfo
0x40b5e7  call    ___raise_securityfailure
0x40b5ec  leave
0x40b5ed  retn
```
