# MSCryptCreateSecret

- ea: `0x180020408`
- end: `0x18002049a`
- name: `MSCryptCreateSecret`
- size: `146`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, size_t Size@<rdx>, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001fad0`
- `0x180058400`
- `0x18006bd38`

## callees

- `0x18000ecb0`
- `0x1800102a0`
- `0x180020408`
- `0x180063170`

## string_xrefs

- `0x180020437`: `onecore\ds\security\cryptoapi\ncrypt\msprim\common\secret.c`

## pseudocode

```c
__int64 __fastcall MSCryptCreateSecret(void *Src, size_t Size, _QWORD *a3, __int64 a4, int a5)
{
  size_t v5; // rsi
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  unsigned int v10; // edi

  v5 = (unsigned int)Size;
  v8 = (_DWORD *)SafeAllocaAllocateFromHeap((unsigned int)Size + 640LL);
  v9 = v8;
  if ( v8 )
  {
    v10 = 0;
    v8[2] = a5;
    *v8 = 640;
    v8[1] = 1297302851;
    v8[3] = v5;
    v8[4] = v5;
    memcpy_0(v8 + 156, Src, v5);
    *a3 = v9;
  }
  else
  {
    v10 = -1073741801;
    DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\common\\secret.c", 162);
  }
  return v10;
}

```

## disassembly

```asm
0x180020408  push    rbx
0x18002040a  push    rbp
0x18002040b  push    rsi
0x18002040c  push    rdi
0x18002040d  push    r14
0x18002040f  push    r15
0x180020411  sub     rsp, 28h
0x180020415  mov     esi, edx
0x180020417  mov     r15, rcx
0x18002041a  mov     r14, r8
0x18002041d  lea     rcx, [rsi+280h]
0x180020424  call    SafeAllocaAllocateFromHeap
0x180020429  mov     rbx, rax
0x18002042c  test    rax, rax
0x18002042f  jnz     short loc_180020456
0x180020431  mov     r9d, 0A2h
0x180020437  lea     r8, aOnecoreDsSecur_10; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002043e  lea     rdx, aStatus; "Status"
0x180020445  mov     ecx, 0C0000017h
0x18002044a  mov     edi, 0C0000017h
0x18002044f  call    DebugTraceError
0x180020454  jmp     short loc_18002048A
0x180020456  mov     ecx, [rsp+58h+arg_20]
0x18002045d  xor     edi, edi
0x18002045f  mov     [rax+8], ecx
0x180020462  mov     r8, rsi; Size
0x180020465  lea     rcx, [rax+270h]; void *
0x18002046c  mov     dword ptr [rax], 280h
0x180020472  mov     rdx, r15; Src
0x180020475  mov     dword ptr [rax+4], 4D534543h
0x18002047c  mov     [rax+0Ch], esi
0x18002047f  mov     [rax+10h], esi
0x180020482  call    memcpy_0
0x180020487  mov     [r14], rbx
0x18002048a  mov     eax, edi
0x18002048c  add     rsp, 28h
0x180020490  pop     r15
0x180020492  pop     r14
0x180020494  pop     rdi
0x180020495  pop     rsi
0x180020496  pop     rbp
0x180020497  pop     rbx
0x180020498  retn
```
