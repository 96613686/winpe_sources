# WriteOptionAttribute

- ea: `0x18000ffe8`
- end: `0x180010106`
- name: `WriteOptionAttribute`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char, char, __int64, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007918`

## callees

- `0x180005db4`
- `0x18000ffe8`
- `0x180015010`

## string_xrefs

- `0x180010053`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x1800100e1`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall WriteOptionAttribute(__int64 a1, __int64 a2, __int64 a3, char a4, char a5, __int64 a6, char a7)
{
  const char *v10; // rdx
  int v11; // edi
  __int64 v12; // rdx
  const char *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (a4 & 2) != 0 || (a4 & 4) != 0 )
  {
    v10 = L"true";
    if ( (a4 & 2) == 0 )
      v10 = L"false";
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, const char *))(*(_QWORD *)a1 + 56LL))(
            a1,
            0,
            a2,
            0,
            v10);
    if ( v11 < 0 )
    {
      v12 = 265;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
        (const char *)(unsigned int)v11);
      return (unsigned int)v11;
    }
    if ( a3 )
    {
      v14 = L"true";
      if ( !a5 )
        v14 = L"false";
      v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, const char *))(*(_QWORD *)a1 + 56LL))(
              a1,
              0,
              a3,
              0,
              v14);
      if ( v11 < 0 )
      {
        v12 = 268;
        goto LABEL_7;
      }
    }
  }
  if ( !a6 )
    return 0;
  if ( !a7 )
    return 0;
  v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, const char *))(*(_QWORD *)a1 + 56LL))(
          a1,
          0,
          a6,
          0,
          L"true");
  v16 = v15;
  if ( v15 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x111,
    (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
    (const char *)(unsigned int)v15);
  return v16;
}

```

## disassembly

```asm
0x18000ffe8  push    rbx
0x18000ffea  push    rbp
0x18000ffeb  push    rsi
0x18000ffec  push    rdi
0x18000ffed  push    r14
0x18000ffef  sub     rsp, 30h
0x18000fff3  mov     rbx, rcx
0x18000fff6  lea     rbp, aTrue; "true"
0x18000fffd  mov     cl, r9b
0x180010000  mov     rsi, r8
0x180010003  mov     r8, rdx
0x180010006  and     cl, 2
0x180010009  jnz     short loc_180010015
0x18001000b  test    r9b, 4
0x18001000f  jz      loc_1800100A6
0x180010015  mov     rax, [rbx]
0x180010018  lea     r14, aFalse; "false"
0x18001001f  test    cl, cl
0x180010021  mov     rdx, rbp
0x180010024  setnz   cl
0x180010027  mov     rax, [rax+38h]
0x18001002b  test    cl, cl
0x18001002d  mov     rcx, rbx
0x180010030  cmovz   rdx, r14
0x180010034  xor     r9d, r9d
0x180010037  mov     qword ptr [rsp+58h+var_38], rdx; int
0x18001003c  xor     edx, edx
0x18001003e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010043  mov     edi, eax
0x180010045  test    eax, eax
0x180010047  jns     short loc_180010069
0x180010049  mov     edx, 109h; void *
0x18001004e  mov     rcx, [rsp+58h]; this
0x180010053  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18001005a  mov     r9d, edi; char *
0x18001005d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010062  mov     eax, edi
0x180010064  jmp     loc_1800100FB
0x180010069  test    rsi, rsi
0x18001006c  jz      short loc_1800100A6
0x18001006e  mov     rax, [rbx]
0x180010071  mov     rcx, rbp
0x180010074  cmp     [rsp+58h+arg_20], 0
0x18001007c  mov     r8, rsi
0x18001007f  cmovz   rcx, r14
0x180010083  xor     r9d, r9d
0x180010086  mov     rax, [rax+38h]
0x18001008a  xor     edx, edx
0x18001008c  mov     qword ptr [rsp+58h+var_38], rcx
0x180010091  mov     rcx, rbx
0x180010094  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010099  mov     edi, eax
0x18001009b  test    eax, eax
0x18001009d  jns     short loc_1800100A6
0x18001009f  mov     edx, 10Ch
0x1800100a4  jmp     short loc_18001004E
0x1800100a6  mov     r8, [rsp+58h+arg_28]
0x1800100ae  test    r8, r8
0x1800100b1  jz      short loc_1800100F9
0x1800100b3  cmp     [rsp+58h+arg_30], 0
0x1800100bb  jz      short loc_1800100F9
0x1800100bd  mov     rax, [rbx]
0x1800100c0  xor     r9d, r9d
0x1800100c3  xor     edx, edx
0x1800100c5  mov     qword ptr [rsp+58h+var_38], rbp; int
0x1800100ca  mov     rcx, rbx
0x1800100cd  mov     rax, [rax+38h]
0x1800100d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100d6  mov     ebx, eax
0x1800100d8  test    eax, eax
0x1800100da  jns     short loc_1800100F9
0x1800100dc  mov     rcx, [rsp+58h]; this
0x1800100e1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x1800100e8  mov     r9d, eax; char *
0x1800100eb  mov     edx, 111h; void *
0x1800100f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100f5  mov     eax, ebx
0x1800100f7  jmp     short loc_1800100FB
0x1800100f9  xor     eax, eax
0x1800100fb  add     rsp, 30h
0x1800100ff  pop     r14
0x180010101  pop     rdi
0x180010102  pop     rsi
0x180010103  pop     rbp
0x180010104  pop     rbx
0x180010105  retn
```
