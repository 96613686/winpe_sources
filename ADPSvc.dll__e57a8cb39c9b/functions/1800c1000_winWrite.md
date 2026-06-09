# winWrite

- ea: `0x1800c1000`
- end: `0x1800c1131`
- name: `winWrite`
- size: `305`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800bf47c`
- `0x1800bf558`
- `0x1800c01b8`
- `0x1800c1000`
- `0x1800ca010`

## string_xrefs

- `0x1800c1118`: `winWrite1`
- `0x1800c1102`: `winWrite2`

## pseudocode

```c
__int64 __fastcall winWrite(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rdi
  int v5; // ebx
  DWORD v8; // eax
  _QWORD v10[2]; // [rsp+30h] [rbp-20h] BYREF
  __int64 v11; // [rsp+40h] [rbp-10h]
  __int64 v12; // [rsp+48h] [rbp-8h]
  DWORD v13; // [rsp+80h] [rbp+30h] BYREF
  unsigned int v14; // [rsp+88h] [rbp+38h] BYREF
  unsigned int v15; // [rsp+90h] [rbp+40h] BYREF

  v14 = 0;
  v4 = a4;
  v15 = 0;
  v13 = 0;
  v5 = a3;
  v10[0] = 0;
  v10[1] = 0;
  v12 = 0;
  v11 = a4 & 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 <= 0 )
    goto LABEL_9;
  while ( !(unsigned int)((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, unsigned int *, _QWORD *))off_18010C3C0)(
                           *(_QWORD *)(a1 + 16),
                           a2,
                           (unsigned int)v5,
                           &v15,
                           v10) )
  {
    if ( !(unsigned int)winRetryIoerr(&v14, &v13) )
    {
      v8 = v13;
      goto LABEL_11;
    }
LABEL_8:
    if ( v5 <= 0 )
      goto LABEL_9;
  }
  if ( v15 && v15 <= v5 )
  {
    v4 += v15;
    a2 += v15;
    v11 = v4 & 0x7FFFFFFFFFFFFFFFLL;
    v5 -= v15;
    goto LABEL_8;
  }
  v8 = off_18010C078();
LABEL_11:
  if ( !v5 )
  {
LABEL_9:
    winLogIoerr(v14, 49646);
    return 0;
  }
  *(_DWORD *)(a1 + 32) = v8;
  if ( v8 == 39 || v8 == 112 )
    return winLogErrorAtLine(13, v8, (unsigned int)"winWrite1", *(_QWORD *)(a1 + 48), 49639);
  else
    return winLogErrorAtLine(778, v8, (unsigned int)"winWrite2", *(_QWORD *)(a1 + 48), 49644);
}

```

## disassembly

```asm
0x1800c1000  push    rbp
0x1800c1002  push    rbx
0x1800c1003  push    rsi
0x1800c1004  push    rdi
0x1800c1005  push    r14
0x1800c1007  mov     rbp, rsp
0x1800c100a  sub     rsp, 50h
0x1800c100e  mov     rax, r9
0x1800c1011  mov     [rbp+arg_8], 0
0x1800c1018  sar     rax, 20h
0x1800c101c  mov     rdi, r9
0x1800c101f  btr     eax, 1Fh
0x1800c1023  mov     [rbp+arg_10], 0
0x1800c102a  mov     [rbp+arg_0], 0
0x1800c1031  mov     ebx, r8d
0x1800c1034  mov     [rbp+var_20], 0
0x1800c103c  mov     r14, rdx
0x1800c103f  mov     [rbp+var_18], 0
0x1800c1047  mov     rsi, rcx
0x1800c104a  mov     [rbp+var_8], 0
0x1800c1052  mov     dword ptr [rbp+var_10], r9d
0x1800c1056  mov     dword ptr [rbp+var_10+4], eax
0x1800c1059  test    r8d, r8d
0x1800c105c  jle     short loc_1800C10C3
0x1800c105e  mov     rcx, [rsi+10h]
0x1800c1062  lea     rax, [rbp+var_20]
0x1800c1066  mov     [rsp+50h+var_30], rax
0x1800c106b  lea     r9, [rbp+arg_10]
0x1800c106f  mov     rax, cs:off_18010C3C0
0x1800c1076  mov     r8d, ebx
0x1800c1079  mov     rdx, r14
0x1800c107c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1081  test    eax, eax
0x1800c1083  jnz     short loc_1800C109B
0x1800c1085  lea     rdx, [rbp+arg_0]
0x1800c1089  lea     rcx, [rbp+arg_8]
0x1800c108d  call    winRetryIoerr
0x1800c1092  test    eax, eax
0x1800c1094  jnz     short loc_1800C10BF
0x1800c1096  mov     eax, [rbp+arg_0]
0x1800c1099  jmp     short loc_1800C10E9
0x1800c109b  mov     edx, [rbp+arg_10]
0x1800c109e  test    edx, edx
0x1800c10a0  jz      short loc_1800C10DD
0x1800c10a2  cmp     edx, ebx
0x1800c10a4  ja      short loc_1800C10DD
0x1800c10a6  add     rdi, rdx
0x1800c10a9  add     r14, rdx
0x1800c10ac  mov     rax, rdi
0x1800c10af  mov     dword ptr [rbp+var_10], edi
0x1800c10b2  sar     rax, 20h
0x1800c10b6  btr     eax, 1Fh
0x1800c10ba  mov     dword ptr [rbp+var_10+4], eax
0x1800c10bd  sub     ebx, edx
0x1800c10bf  test    ebx, ebx
0x1800c10c1  jg      short loc_1800C105E
0x1800c10c3  mov     ecx, [rbp+arg_8]
0x1800c10c6  mov     edx, 0C1EEh
0x1800c10cb  call    winLogIoerr
0x1800c10d0  xor     eax, eax
0x1800c10d2  add     rsp, 50h
0x1800c10d6  pop     r14
0x1800c10d8  pop     rdi
0x1800c10d9  pop     rsi
0x1800c10da  pop     rbx
0x1800c10db  pop     rbp
0x1800c10dc  retn
0x1800c10dd  mov     rax, cs:off_18010C078
0x1800c10e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c10e9  test    ebx, ebx
0x1800c10eb  jz      short loc_1800C10C3
0x1800c10ed  mov     [rsi+20h], eax
0x1800c10f0  cmp     eax, 27h ; '''
0x1800c10f3  jz      short loc_1800C1110
0x1800c10f5  cmp     eax, 70h ; 'p'
0x1800c10f8  jz      short loc_1800C1110
0x1800c10fa  mov     dword ptr [rsp+50h+var_30], 0C1ECh
0x1800c1102  lea     r8, aWinwrite2; "winWrite2"
0x1800c1109  mov     ecx, 30Ah
0x1800c110e  jmp     short loc_1800C1124
0x1800c1110  mov     dword ptr [rsp+50h+var_30], 0C1E7h
0x1800c1118  lea     r8, aWinwrite1; "winWrite1"
0x1800c111f  mov     ecx, 0Dh
0x1800c1124  mov     r9, [rsi+30h]
0x1800c1128  mov     edx, eax
0x1800c112a  call    winLogErrorAtLine
0x1800c112f  jmp     short loc_1800C10D2
```
