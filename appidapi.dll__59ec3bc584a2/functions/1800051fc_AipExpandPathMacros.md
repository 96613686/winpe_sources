# AipExpandPathMacros

- ea: `0x1800051fc`
- end: `0x180005333`
- name: `AipExpandPathMacros`
- size: `311`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800028d0`
- `0x180004ca0`

## callees

- `0x180003fd4`
- `0x1800051fc`
- `0x180005594`
- `0x180009562`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800052e0`
- `ntdll!RtlFreeHeap` at `0x1800052e0`

## pseudocode

```c
__int64 AipExpandPathMacros()
{
  PVOID *v0; // rbx
  unsigned int v1; // esi
  PVOID *v2; // rdi
  int v3; // r14d
  _WORD *v4; // r15
  _WORD *v5; // rbp
  char *v6; // rax
  char *v7; // r14
  __int128 v9; // [rsp+20h] [rbp-48h]

  v0 = (PVOID *)P;
  v1 = 0;
  while ( v0 != &P )
  {
    v1 = 0;
    DWORD1(v9) = 0;
    if ( ((_BYTE)v0[2] & 4) == 0 )
    {
      while ( 2 )
      {
        v2 = (PVOID *)P;
        v3 = 0;
        if ( P != &P )
        {
          do
          {
            if ( v2 != v0 )
            {
              v4 = v2 + 3;
              v5 = v0 + 5;
              if ( (unsigned int)AipIsPathMacroPrefix((PCUNICODE_STRING)(v0 + 5), (PCUNICODE_STRING)(v2 + 3)) )
              {
                LOWORD(v9) = *v5 + *((_WORD *)v2 + 20) - *v4;
                WORD1(v9) = v9;
                v6 = (char *)AiAlloc((unsigned __int16)v9);
                *((_QWORD *)&v9 + 1) = v6;
                v7 = v6;
                if ( !v6 )
                  return (unsigned int)-1073741801;
                memcpy_0(v6, v2[6], *((unsigned __int16 *)v2 + 20));
                memcpy_0(
                  &v7[*((unsigned __int16 *)v2 + 20)],
                  (char *)v0[6] + (unsigned __int16)*v4,
                  (unsigned __int16)*v5 - (unsigned __int64)(unsigned __int16)*v4);
                if ( ((_BYTE)v0[2] & 2) != 0 )
                  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v0[6]);
                *((_DWORD *)v0 + 4) |= 2u;
                v3 = 1;
                *(_OWORD *)v5 = v9;
              }
            }
            v2 = (PVOID *)*v2;
          }
          while ( v2 != &P );
          if ( v3 )
            continue;
        }
        break;
      }
    }
    v0 = (PVOID *)*v0;
  }
  return v1;
}

```

## disassembly

```asm
0x1800051fc  push    rbx
0x1800051fe  push    rbp
0x1800051ff  push    rsi
0x180005200  push    rdi
0x180005201  push    r12
0x180005203  push    r14
0x180005205  push    r15
0x180005207  sub     rsp, 30h
0x18000520b  mov     rbx, cs:P
0x180005212  lea     r12, P
0x180005219  xor     esi, esi
0x18000521b  jmp     loc_180005312
0x180005220  xor     esi, esi
0x180005222  xorps   xmm0, xmm0
0x180005225  test    byte ptr [rbx+10h], 4
0x180005229  movups  [rsp+68h+var_48], xmm0
0x18000522e  jnz     loc_18000530F
0x180005234  mov     rdi, cs:P
0x18000523b  xor     r14d, r14d
0x18000523e  cmp     rdi, r12
0x180005241  jz      loc_18000530F
0x180005247  cmp     rdi, rbx
0x18000524a  jz      loc_1800052FA
0x180005250  lea     r15, [rdi+18h]
0x180005254  lea     rbp, [rbx+28h]
0x180005258  mov     rdx, r15; String1
0x18000525b  mov     rcx, rbp; String2
0x18000525e  call    AipIsPathMacroPrefix
0x180005263  test    eax, eax
0x180005265  jz      loc_1800052FA
0x18000526b  movzx   eax, word ptr [rdi+28h]
0x18000526f  sub     ax, [r15]
0x180005273  add     ax, [rbp+0]
0x180005277  movzx   ecx, ax
0x18000527a  mov     word ptr [rsp+68h+var_48], cx
0x18000527f  mov     word ptr [rsp+68h+var_48+2], cx
0x180005284  call    AiAlloc
0x180005289  mov     qword ptr [rsp+68h+var_48+8], rax
0x18000528e  mov     r14, rax
0x180005291  test    rax, rax
0x180005294  jz      loc_18000531D
0x18000529a  movzx   r8d, word ptr [rdi+28h]; Size
0x18000529f  mov     rcx, rax; void *
0x1800052a2  mov     rdx, [rdi+30h]; Src
0x1800052a6  call    memcpy_0
0x1800052ab  movzx   edx, word ptr [r15]
0x1800052af  movzx   r8d, word ptr [rbp+0]
0x1800052b4  movzx   ecx, word ptr [rdi+28h]
0x1800052b8  sub     r8, rdx; Size
0x1800052bb  add     rdx, [rbx+30h]; Src
0x1800052bf  add     rcx, r14; void *
0x1800052c2  call    memcpy_0
0x1800052c7  test    byte ptr [rbx+10h], 2
0x1800052cb  jz      short loc_1800052E6
0x1800052cd  mov     rcx, gs:60h
0x1800052d6  xor     edx, edx; Flags
0x1800052d8  mov     r8, [rbx+30h]; P
0x1800052dc  mov     rcx, [rcx+30h]; HeapHandle
0x1800052e0  call    cs:__imp_RtlFreeHeap
0x1800052e6  movups  xmm0, [rsp+68h+var_48]
0x1800052eb  or      dword ptr [rbx+10h], 2
0x1800052ef  mov     r14d, 1
0x1800052f5  movdqu  xmmword ptr [rbp+0], xmm0
0x1800052fa  mov     rdi, [rdi]
0x1800052fd  cmp     rdi, r12
0x180005300  jnz     loc_180005247
0x180005306  test    r14d, r14d
0x180005309  jnz     loc_180005234
0x18000530f  mov     rbx, [rbx]
0x180005312  cmp     rbx, r12
0x180005315  jnz     loc_180005220
0x18000531b  jmp     short loc_180005322
0x18000531d  mov     esi, 0C0000017h
0x180005322  mov     eax, esi
0x180005324  add     rsp, 30h
0x180005328  pop     r15
0x18000532a  pop     r14
0x18000532c  pop     r12
0x18000532e  pop     rdi
0x18000532f  pop     rsi
0x180005330  pop     rbp
0x180005331  pop     rbx
0x180005332  retn
```
