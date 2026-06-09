# _NewLoadedProviderHandle

- ea: `0x18000dac4`
- end: `0x18000dc20`
- name: `_NewLoadedProviderHandle`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180007d60`

## callees

- `0x180004200`
- `0x180005060`
- `0x180007a7c`
- `0x18000dac4`
- `0x18001b79d`

## string_xrefs

- `0x18000db59`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`
- `0x18000dbf3`: `onecore\ds\security\cryptoapi\ncrypt\loader\loader.c`

## pseudocode

```c
__int64 __fastcall NewLoadedProviderHandle(__int64 a1, __int64 a2, _QWORD *a3)
{
  _WORD **v3; // rax
  _WORD *v7; // r11
  __int64 v8; // r9
  unsigned int v9; // ecx
  unsigned __int64 v10; // rax
  size_t v11; // rsi
  unsigned int v12; // edi
  __int64 v13; // rcx
  _QWORD *v14; // rbx
  _QWORD *v16; // rax

  v3 = *(_WORD ***)(a1 + 40);
  *a3 = 0;
  v7 = *v3;
  if ( !*v3 )
  {
    LOBYTE(v9) = 87;
    goto LABEL_10;
  }
  v8 = 2048;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v9 = v8 == 0 ? 0x80070057 : 0;
  if ( !v8 )
  {
LABEL_10:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)WPP_GLOBAL_Control,
        (_DWORD)a3,
        (unsigned int)"hResult",
        v9,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c",
        82);
    v12 = -1073741811;
    goto LABEL_14;
  }
  v10 = (2 * (2048 - v8)) & -(__int64)(v8 != 0);
  v11 = v10 + 2;
  if ( v10 + 2 >= v10 && v11 < 0xFFFFFFFFFFFFFFE0uLL )
  {
    v16 = (_QWORD *)SafeAllocaAllocateFromHeap(v10 + 34);
    v14 = v16;
    if ( v16 )
    {
      *v16 = v16 + 4;
      v12 = 0;
      memcpy_0(v16 + 4, **(const void ***)(a1 + 40), v11);
      v14[1] = a2;
      *((_DWORD *)v14 + 4) = 2;
      v14[3] = 0;
      goto LABEL_15;
    }
    v12 = -1073741801;
    v13 = 3221225495LL;
  }
  else
  {
    v12 = -1073741675;
    v13 = 3221225621LL;
  }
  DebugTraceError(v13, "sResult", "onecore\\ds\\security\\cryptoapi\\ncrypt\\loader\\loader.c");
LABEL_14:
  v14 = 0;
LABEL_15:
  *a3 = v14;
  return v12;
}

```

## disassembly

```asm
0x18000dac4  push    rbx
0x18000dac6  push    rbp
0x18000dac7  push    rsi
0x18000dac8  push    rdi
0x18000dac9  push    r12
0x18000dacb  push    r14
0x18000dacd  push    r15
0x18000dacf  sub     rsp, 40h
0x18000dad3  mov     rax, [rcx+28h]
0x18000dad7  xor     r12d, r12d
0x18000dada  mov     r14, r8
0x18000dadd  mov     [r8], r12
0x18000dae0  mov     r15, rdx
0x18000dae3  mov     rbp, rcx
0x18000dae6  mov     r11, [rax]
0x18000dae9  test    r11, r11
0x18000daec  jz      loc_18000DBE9
0x18000daf2  mov     r10d, 800h
0x18000daf8  mov     r9d, r10d
0x18000dafb  cmp     [r11], r12w
0x18000daff  jz      short loc_18000DB0B
0x18000db01  add     r11, 2
0x18000db05  sub     r9, 1
0x18000db09  jnz     short loc_18000DAFB
0x18000db0b  mov     rax, r9
0x18000db0e  neg     rax
0x18000db11  sbb     ecx, ecx
0x18000db13  not     ecx
0x18000db15  and     ecx, 80070057h
0x18000db1b  test    r9, r9
0x18000db1e  jz      short loc_18000DB67
0x18000db20  sub     r10, r9
0x18000db23  add     r10, r10
0x18000db26  neg     r9
0x18000db29  sbb     rax, rax
0x18000db2c  and     rax, r10
0x18000db2f  lea     rsi, [rax+2]
0x18000db33  cmp     rsi, rax
0x18000db36  jb      short loc_18000DB42
0x18000db38  lea     rcx, [rsi+20h]
0x18000db3c  cmp     rcx, 20h ; ' '
0x18000db40  jnb     short loc_18000DB9D
0x18000db42  mov     edi, 0C0000095h
0x18000db47  mov     r9d, 15Ch
0x18000db4d  mov     ecx, 0C0000095h
0x18000db52  lea     rdx, aSresult; "sResult"
0x18000db59  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000db60  call    DebugTraceError
0x18000db65  jmp     short loc_18000DB85
0x18000db67  mov     rdx, cs:WPP_GLOBAL_Control
0x18000db6e  lea     rax, WPP_GLOBAL_Control
0x18000db75  cmp     rdx, rax
0x18000db78  jz      short loc_18000DB80
0x18000db7a  test    byte ptr [rdx+1Ch], 1
0x18000db7e  jnz     short loc_18000DBF3
0x18000db80  mov     edi, 0C000000Dh
0x18000db85  mov     rbx, r12
0x18000db88  mov     [r14], rbx
0x18000db8b  mov     eax, edi
0x18000db8d  add     rsp, 40h
0x18000db91  pop     r15
0x18000db93  pop     r14
0x18000db95  pop     r12
0x18000db97  pop     rdi
0x18000db98  pop     rsi
0x18000db99  pop     rbp
0x18000db9a  pop     rbx
0x18000db9b  retn
0x18000db9d  call    SafeAllocaAllocateFromHeap
0x18000dba2  mov     rbx, rax
0x18000dba5  test    rax, rax
0x18000dba8  jz      short loc_18000DBD4
0x18000dbaa  lea     rcx, [rax+20h]; void *
0x18000dbae  mov     r8, rsi; Size
0x18000dbb1  mov     [rax], rcx
0x18000dbb4  mov     edi, r12d
0x18000dbb7  mov     rdx, [rbp+28h]
0x18000dbbb  mov     rdx, [rdx]; Src
0x18000dbbe  call    memcpy_0
0x18000dbc3  mov     [rbx+8], r15
0x18000dbc7  mov     dword ptr [rbx+10h], 2
0x18000dbce  mov     [rbx+18h], r12
0x18000dbd2  jmp     short loc_18000DB88
0x18000dbd4  mov     edi, 0C0000017h
0x18000dbd9  mov     r9d, 16Fh
0x18000dbdf  mov     ecx, 0C0000017h
0x18000dbe4  jmp     loc_18000DB52
0x18000dbe9  mov     ecx, 80070057h
0x18000dbee  jmp     loc_18000DB67
0x18000dbf3  lea     rax, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000dbfa  mov     [rsp+78h+var_48], 152h
0x18000dc02  mov     [rsp+78h+var_50], rax
0x18000dc07  lea     r9, aHresult; "hResult"
0x18000dc0e  mov     [rsp+78h+var_58], ecx
0x18000dc12  mov     rcx, [rdx+10h]
0x18000dc16  call    WPP_SF_sDsd
0x18000dc1b  jmp     loc_18000DB80
```
