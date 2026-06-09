# extElementConfig

- ea: `0x18007a198`
- end: `0x18007a2f9`
- name: `extElementConfig`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180079960`

## callees

- `0x18000e9b0`
- `0x180012264`
- `0x180013550`
- `0x18007a128`
- `0x18007a198`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall extElementConfig(
        __int64 a1,
        int *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  unsigned int v12; // eax
  int v13; // esi
  unsigned int v14; // r12d
  __int16 v15; // ax
  int v16; // r15d
  __int64 result; // rax
  unsigned int v18; // ebx
  __int64 (__fastcall *v19)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int); // rax
  __int64 v20; // rdx

  v12 = escapedValue_0(a2, 4, 8, 16);
  v13 = v12;
  if ( a9 == 42 && v12 > 2 && v12 - 3 >= 2 )
    v13 = 255;
  v14 = escapedValue_0(a2, 4, 8, 16);
  if ( (unsigned int)CDKreadBit((__int64)a2) )
    v15 = escapedValue_0(a2, 8, 16, 0) + 1;
  else
    v15 = 0;
  *(_WORD *)(a1 + 4) = v15;
  *(_BYTE *)(a1 + 6) = CDKreadBit((__int64)a2);
  CDKsyncCache_0(a2);
  v16 = a2[2];
  if ( v16 < (int)(8 * v14) )
    return 257;
  v18 = 0;
  if ( v13 )
  {
    if ( v13 == 3 )
    {
      *(_BYTE *)(a1 + 7) = 1;
    }
    else if ( v13 == 4 )
    {
      v19 = *(__int64 (__fastcall **)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int))(a3 + 112);
      if ( v19 )
      {
        result = v19(*(_QWORD *)(a3 + 120), a2, v14, 0, 0, 0, a9);
        v18 = result;
        if ( (_DWORD)result )
          return result;
      }
    }
    else if ( v13 != 255 )
    {
      v13 = 255;
    }
  }
  *(_DWORD *)a1 = v13;
  CDKsyncCache_0(a2);
  v20 = 8 * v14 + a2[2] - v16;
  if ( (int)v20 < 0 )
    return 1025;
  else
    CDKpushFor(a2, v20);
  return v18;
}

```

## disassembly

```asm
0x18007a198  push    rbx
0x18007a19a  push    rbp
0x18007a19b  push    rsi
0x18007a19c  push    rdi
0x18007a19d  push    r12
0x18007a19f  push    r13
0x18007a1a1  push    r14
0x18007a1a3  push    r15
0x18007a1a5  sub     rsp, 48h
0x18007a1a9  mov     ebx, 10h
0x18007a1ae  mov     rdi, rdx
0x18007a1b1  mov     r13, r8
0x18007a1b4  mov     r14, rcx
0x18007a1b7  mov     r9d, ebx
0x18007a1ba  mov     rcx, rdi
0x18007a1bd  lea     ebp, [rbx-8]
0x18007a1c0  lea     r15d, [rbx-0Ch]
0x18007a1c4  mov     r8d, ebp
0x18007a1c7  mov     edx, r15d
0x18007a1ca  call    escapedValue_0
0x18007a1cf  cmp     [rsp+88h+arg_40], 2Ah ; '*'
0x18007a1d7  mov     esi, eax
0x18007a1d9  jnz     short loc_18007A1FA
0x18007a1db  mov     ecx, eax
0x18007a1dd  test    eax, eax
0x18007a1df  jz      short loc_18007A1FA
0x18007a1e1  sub     ecx, 1
0x18007a1e4  jz      short loc_18007A1FA
0x18007a1e6  sub     ecx, 1
0x18007a1e9  jz      short loc_18007A1FA
0x18007a1eb  sub     ecx, 1
0x18007a1ee  jz      short loc_18007A1FA
0x18007a1f0  cmp     ecx, 1
0x18007a1f3  jz      short loc_18007A1FA
0x18007a1f5  mov     esi, 0FFh
0x18007a1fa  mov     r9d, ebx
0x18007a1fd  mov     r8d, ebp
0x18007a200  mov     edx, r15d
0x18007a203  mov     rcx, rdi
0x18007a206  call    escapedValue_0
0x18007a20b  mov     rcx, rdi
0x18007a20e  mov     r12d, eax
0x18007a211  call    CDKreadBit
0x18007a216  test    eax, eax
0x18007a218  jz      short loc_18007A22F
0x18007a21a  xor     r9d, r9d
0x18007a21d  mov     r8d, ebx
0x18007a220  mov     edx, ebp
0x18007a222  mov     rcx, rdi
0x18007a225  call    escapedValue_0
0x18007a22a  inc     ax
0x18007a22d  jmp     short loc_18007A231
0x18007a22f  xor     eax, eax
0x18007a231  mov     rcx, rdi
0x18007a234  mov     [r14+4], ax
0x18007a239  call    CDKreadBit
0x18007a23e  mov     rcx, rdi
0x18007a241  mov     [r14+6], al
0x18007a245  call    CDKsyncCache_0
0x18007a24a  mov     r15d, [rdi+8]
0x18007a24e  lea     ebp, ds:0[r12*8]
0x18007a256  cmp     r15d, ebp
0x18007a259  jge     short loc_18007A265
0x18007a25b  mov     eax, 101h
0x18007a260  jmp     loc_18007A2E7
0x18007a265  xor     ebx, ebx
0x18007a267  mov     eax, esi
0x18007a269  test    esi, esi
0x18007a26b  jz      short loc_18007A2C1
0x18007a26d  sub     eax, 3
0x18007a270  jz      short loc_18007A2BC
0x18007a272  sub     eax, 1
0x18007a275  jz      short loc_18007A285
0x18007a277  cmp     eax, 0FBh
0x18007a27c  jz      short loc_18007A2C1
0x18007a27e  mov     esi, 0FFh
0x18007a283  jmp     short loc_18007A2C1
0x18007a285  mov     rax, [r13+70h]
0x18007a289  test    rax, rax
0x18007a28c  jz      short loc_18007A2C1
0x18007a28e  mov     ecx, [rsp+88h+arg_40]
0x18007a295  xor     r9d, r9d
0x18007a298  mov     [rsp+88h+var_58], ecx
0x18007a29c  mov     r8d, r12d
0x18007a29f  mov     rcx, [r13+78h]
0x18007a2a3  mov     rdx, rdi
0x18007a2a6  mov     [rsp+88h+var_60], ebx
0x18007a2aa  mov     [rsp+88h+var_68], ebx
0x18007a2ae  call    cs:__guard_dispatch_icall_fptr
0x18007a2b4  mov     ebx, eax
0x18007a2b6  test    eax, eax
0x18007a2b8  jz      short loc_18007A2C1
0x18007a2ba  jmp     short loc_18007A2E7
0x18007a2bc  mov     byte ptr [r14+7], 1
0x18007a2c1  mov     rcx, rdi
0x18007a2c4  mov     [r14], esi
0x18007a2c7  call    CDKsyncCache_0
0x18007a2cc  mov     edx, [rdi+8]
0x18007a2cf  sub     edx, r15d
0x18007a2d2  add     edx, ebp
0x18007a2d4  js      short loc_18007A2E0
0x18007a2d6  mov     rcx, rdi
0x18007a2d9  call    CDKpushFor
0x18007a2de  jmp     short loc_18007A2E5
0x18007a2e0  mov     ebx, 401h
0x18007a2e5  mov     eax, ebx
0x18007a2e7  add     rsp, 48h
0x18007a2eb  pop     r15
0x18007a2ed  pop     r14
0x18007a2ef  pop     r13
0x18007a2f1  pop     r12
0x18007a2f3  pop     rdi
0x18007a2f4  pop     rsi
0x18007a2f5  pop     rbp
0x18007a2f6  pop     rbx
0x18007a2f7  retn
```
