# RMoveTo

- ea: `0x18004fa84`
- end: `0x18004fbbc`
- name: `RMoveTo`
- size: `312`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004ff08`
- `0x18005017c`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18004f41c`
- `0x18004f538`
- `0x18004fa84`
- `0x180052ed8`
- `0x180052f30`

## pseudocode

```c
__int64 __fastcall RMoveTo(__int64 a1, _DWORD *a2, _DWORD *a3, unsigned int a4)
{
  __int16 v8; // bp
  _DWORD *v9; // rdx
  _DWORD *v10; // r11
  __int64 result; // rax
  _DWORD *v12; // r11
  unsigned int v13; // [rsp+20h] [rbp-88h] BYREF
  int v14; // [rsp+24h] [rbp-84h]

  memset_0(&v13, 0, 0x44u);
  if ( *a2 || a2[1] )
  {
    if ( !*a3 && !a3[1] )
    {
      v8 = 22;
      v9 = a2;
      goto LABEL_9;
    }
    XC_WriteT1PStackValue(a1, a2, a4);
    v8 = 21;
  }
  else
  {
    v8 = 4;
  }
  v9 = a3;
LABEL_9:
  XC_WriteT1PStackValue(a1, v9, a4);
  XC_WriteT1OpCode(a1, v8, a4);
  PSVCopy(a1, &v13, *(unsigned int **)(a1 + 21952));
  if ( *(_DWORD *)(a1 + 488) )
  {
    PStackValueAdd(a1, v10, &v13, a2);
  }
  else
  {
    v10[1] = v14 + a2[1];
    *v10 = 0;
  }
  result = PSVCopy(a1, &v13, *(unsigned int **)(a1 + 21960));
  if ( *(_DWORD *)(a1 + 488) )
    return PStackValueAdd(a1, v12, &v13, a3);
  v12[1] = v14 + a3[1];
  *v12 = 0;
  return result;
}

```

## disassembly

```asm
0x18004fa84  push    rbx
0x18004fa86  push    rbp
0x18004fa87  push    rsi
0x18004fa88  push    rdi
0x18004fa89  push    r14
0x18004fa8b  sub     rsp, 80h
0x18004fa92  mov     rax, cs:__security_cookie
0x18004fa99  xor     rax, rsp
0x18004fa9c  mov     [rsp+0A8h+var_38], rax
0x18004faa1  mov     rsi, rdx
0x18004faa4  mov     rdi, r8
0x18004faa7  xor     edx, edx; Val
0x18004faa9  mov     rbx, rcx
0x18004faac  lea     rcx, [rsp+0A8h+var_88]; void *
0x18004fab1  mov     r14d, r9d
0x18004fab4  lea     r8d, [rdx+44h]; Size
0x18004fab8  call    memset_0
0x18004fabd  cmp     dword ptr [rsi], 0
0x18004fac0  jnz     short loc_18004FACF
0x18004fac2  cmp     dword ptr [rsi+4], 0
0x18004fac6  jnz     short loc_18004FACF
0x18004fac8  mov     ebp, 4
0x18004facd  jmp     short loc_18004FAF7
0x18004facf  cmp     dword ptr [rdi], 0
0x18004fad2  jnz     short loc_18004FAE4
0x18004fad4  cmp     dword ptr [rdi+4], 0
0x18004fad8  jnz     short loc_18004FAE4
0x18004fada  mov     ebp, 16h
0x18004fadf  mov     rdx, rsi
0x18004fae2  jmp     short loc_18004FAFA
0x18004fae4  mov     r8d, r14d
0x18004fae7  mov     rdx, rsi
0x18004faea  mov     rcx, rbx
0x18004faed  call    XC_WriteT1PStackValue
0x18004faf2  mov     ebp, 15h
0x18004faf7  mov     rdx, rdi
0x18004fafa  mov     r8d, r14d
0x18004fafd  mov     rcx, rbx
0x18004fb00  call    XC_WriteT1PStackValue
0x18004fb05  mov     r8d, r14d
0x18004fb08  movzx   edx, bp
0x18004fb0b  mov     rcx, rbx
0x18004fb0e  call    XC_WriteT1OpCode
0x18004fb13  mov     r11, [rbx+55C0h]
0x18004fb1a  lea     rdx, [rsp+0A8h+var_88]
0x18004fb1f  mov     r8, r11
0x18004fb22  mov     rcx, rbx
0x18004fb25  call    PSVCopy
0x18004fb2a  cmp     dword ptr [rbx+1E8h], 0
0x18004fb31  jnz     short loc_18004FB47
0x18004fb33  mov     edx, [rsi+4]
0x18004fb36  add     edx, [rsp+0A8h+var_84]
0x18004fb3a  mov     [r11+4], edx
0x18004fb3e  mov     dword ptr [r11], 0
0x18004fb45  jmp     short loc_18004FB5A
0x18004fb47  mov     r9, rsi
0x18004fb4a  lea     r8, [rsp+0A8h+var_88]
0x18004fb4f  mov     rdx, r11
0x18004fb52  mov     rcx, rbx
0x18004fb55  call    PStackValueAdd
0x18004fb5a  mov     r11, [rbx+55C8h]
0x18004fb61  lea     rdx, [rsp+0A8h+var_88]
0x18004fb66  mov     r8, r11
0x18004fb69  mov     rcx, rbx
0x18004fb6c  call    PSVCopy
0x18004fb71  cmp     dword ptr [rbx+1E8h], 0
0x18004fb78  jnz     short loc_18004FB8E
0x18004fb7a  mov     edx, [rdi+4]
0x18004fb7d  add     edx, [rsp+0A8h+var_84]
0x18004fb81  mov     [r11+4], edx
0x18004fb85  mov     dword ptr [r11], 0
0x18004fb8c  jmp     short loc_18004FBA1
0x18004fb8e  mov     r9, rdi
0x18004fb91  lea     r8, [rsp+0A8h+var_88]
0x18004fb96  mov     rdx, r11
0x18004fb99  mov     rcx, rbx
0x18004fb9c  call    PStackValueAdd
0x18004fba1  mov     rcx, [rsp+0A8h+var_38]
0x18004fba6  xor     rcx, rsp; StackCookie
0x18004fba9  call    __security_check_cookie
0x18004fbae  add     rsp, 80h
0x18004fbb5  pop     r14
0x18004fbb7  pop     rdi
0x18004fbb8  pop     rsi
0x18004fbb9  pop     rbp
0x18004fbba  pop     rbx
0x18004fbbb  retn
```
