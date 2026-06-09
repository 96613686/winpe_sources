# AiAddUninstallStringToUninstallStringEaData

- ea: `0x14002061c`
- end: `0x1400206f5`
- name: `AiAddUninstallStringToUninstallStringEaData`
- size: `217`
- prototype: `__int64 __fastcall(const void **, _WORD *, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140020db4`

## callees

- `0x140006c40`
- `0x14002061c`
- `0x140020c28`
- `0x140032a50`

## pseudocode

```c
__int64 __fastcall AiAddUninstallStringToUninstallStringEaData(
        const void **a1,
        _WORD *a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int *a5)
{
  size_t v5; // r14
  __int64 result; // rax
  unsigned int v10; // ebp
  char *v11; // rax
  char *v12; // rdi
  unsigned int *v13; // rax
  _QWORD v14[7]; // [rsp+20h] [rbp-38h] BYREF
  char v15; // [rsp+68h] [rbp+10h] BYREF

  v5 = a3;
  v15 = 0;
  v14[0] = 0;
  v14[1] = a2 + 20;
  WORD1(v14[0]) = a2[18];
  LOWORD(v14[0]) = WORD1(v14[0]);
  result = AiIsStringNoQuotePrefixedByDelimitedUninstallString(a1, v14, &v15);
  if ( (int)result >= 0 )
  {
    if ( v15 )
    {
      return 3221227288LL;
    }
    else
    {
      v10 = v5 + *(unsigned __int16 *)a1 + 2;
      v11 = (char *)AiAlloc(v10);
      v12 = v11;
      if ( v11 )
      {
        memmove(v11, a2, v5);
        *(_WORD *)&v12[v5] = 0;
        memmove(&v12[(unsigned int)(v5 + 2)], a1[1], *(unsigned __int16 *)a1);
        v13 = a5;
        *a4 = v12;
        *v13 = v10;
        return 0;
      }
      else
      {
        return 3221225495LL;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002061c  mov     r11, rsp
0x14002061f  mov     [r11+8], rbx
0x140020623  mov     [r11+18h], rbp
0x140020627  push    rsi
0x140020628  push    rdi
0x140020629  push    r12
0x14002062b  push    r14
0x14002062d  push    r15
0x14002062f  sub     rsp, 30h
0x140020633  lea     rax, [rdx+28h]
0x140020637  mov     r14d, r8d
0x14002063a  xorps   xmm0, xmm0
0x14002063d  mov     [rsp+58h+arg_8], 0
0x140020642  movups  [rsp+58h+var_38], xmm0
0x140020647  mov     [r11-30h], rax
0x14002064b  lea     r8, [r11+10h]
0x14002064f  movzx   eax, word ptr [rdx+24h]
0x140020653  mov     r15, rdx
0x140020656  lea     rdx, [r11-38h]
0x14002065a  mov     word ptr [rsp+58h+var_38+2], ax
0x14002065f  mov     word ptr [rsp+58h+var_38], ax
0x140020664  mov     r12, r9
0x140020667  mov     rsi, rcx
0x14002066a  call    AiIsStringNoQuotePrefixedByDelimitedUninstallString
0x14002066f  test    eax, eax
0x140020671  js      short loc_1400206DD
0x140020673  cmp     [rsp+58h+arg_8], 0
0x140020678  jz      short loc_140020681
0x14002067a  mov     eax, 0C0000718h
0x14002067f  jmp     short loc_1400206DD
0x140020681  movzx   ebp, word ptr [rsi]
0x140020684  add     ebp, 2
0x140020687  add     ebp, r14d
0x14002068a  mov     ecx, ebp
0x14002068c  call    AiAlloc
0x140020691  mov     rdi, rax
0x140020694  test    rax, rax
0x140020697  jnz     short loc_1400206A0
0x140020699  mov     eax, 0C0000017h
0x14002069e  jmp     short loc_1400206DD
0x1400206a0  mov     r8, r14; Size
0x1400206a3  mov     rdx, r15; Src
0x1400206a6  mov     rcx, rdi; void *
0x1400206a9  call    memmove
0x1400206ae  mov     eax, cs:dword_14000AB70
0x1400206b4  lea     ecx, [r14+2]
0x1400206b8  mov     [r14+rdi], ax
0x1400206bd  add     rcx, rdi; void *
0x1400206c0  movzx   r8d, word ptr [rsi]; Size
0x1400206c4  mov     rdx, [rsi+8]; Src
0x1400206c8  call    memmove
0x1400206cd  mov     rax, [rsp+58h+arg_20]
0x1400206d5  mov     [r12], rdi
0x1400206d9  mov     [rax], ebp
0x1400206db  xor     eax, eax
0x1400206dd  mov     rbx, [rsp+58h+arg_0]
0x1400206e2  mov     rbp, [rsp+58h+arg_10]
0x1400206e7  add     rsp, 30h
0x1400206eb  pop     r15
0x1400206ed  pop     r14
0x1400206ef  pop     r12
0x1400206f1  pop     rdi
0x1400206f2  pop     rsi
0x1400206f3  retn
```
