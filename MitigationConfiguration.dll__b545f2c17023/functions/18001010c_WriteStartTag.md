# WriteStartTag

- ea: `0x18001010c`
- end: `0x1800101a5`
- name: `WriteStartTag`
- size: `153`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _BYTE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180007918`

## callees

- `0x180005db4`
- `0x18001010c`
- `0x180015010`

## string_xrefs

- `0x180010154`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`

## pseudocode

```c
__int64 __fastcall WriteStartTag(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _BYTE *a5)
{
  int v8; // ebx
  __int64 v9; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !*a5 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)a1 + 216LL))(a1, 0, a2, 0);
    if ( v8 < 0 )
    {
      v9 = 1052;
LABEL_4:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
        (const char *)(unsigned int)v8);
      return (unsigned int)v8;
    }
    if ( a3 )
    {
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD, __int64))(*(_QWORD *)a1 + 56LL))(
             a1,
             0,
             a3,
             0,
             a4);
      if ( v8 < 0 )
      {
        v9 = 1055;
        goto LABEL_4;
      }
    }
  }
  *a5 = 1;
  return 0;
}

```

## disassembly

```asm
0x18001010c  push    rbx
0x18001010e  push    rbp
0x18001010f  push    rsi
0x180010110  push    rdi
0x180010111  push    r14
0x180010113  sub     rsp, 30h
0x180010117  mov     rdi, [rsp+58h+arg_20]
0x18001011f  mov     rbp, r9
0x180010122  mov     rsi, r8
0x180010125  mov     r14, rcx
0x180010128  cmp     byte ptr [rdi], 0
0x18001012b  jnz     short loc_180010195
0x18001012d  mov     rax, [rcx]
0x180010130  mov     r8, rdx
0x180010133  xor     r9d, r9d
0x180010136  xor     edx, edx
0x180010138  mov     rax, [rax+0D8h]
0x18001013f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010144  mov     ebx, eax
0x180010146  test    eax, eax
0x180010148  jns     short loc_180010167
0x18001014a  mov     edx, 41Ch; void *
0x18001014f  mov     rcx, [rsp+58h]; this
0x180010154  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18001015b  mov     r9d, ebx; char *
0x18001015e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010163  mov     eax, ebx
0x180010165  jmp     short loc_18001019A
0x180010167  test    rsi, rsi
0x18001016a  jz      short loc_180010195
0x18001016c  mov     rax, [r14]
0x18001016f  xor     r9d, r9d
0x180010172  mov     r8, rsi
0x180010175  mov     [rsp+58h+var_38], rbp
0x18001017a  xor     edx, edx
0x18001017c  mov     rcx, r14
0x18001017f  mov     rax, [rax+38h]
0x180010183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010188  mov     ebx, eax
0x18001018a  test    eax, eax
0x18001018c  jns     short loc_180010195
0x18001018e  mov     edx, 41Fh
0x180010193  jmp     short loc_18001014F
0x180010195  mov     byte ptr [rdi], 1
0x180010198  xor     eax, eax
0x18001019a  add     rsp, 30h
0x18001019e  pop     r14
0x1800101a0  pop     rdi
0x1800101a1  pop     rsi
0x1800101a2  pop     rbp
0x1800101a3  pop     rbx
0x1800101a4  retn
```
