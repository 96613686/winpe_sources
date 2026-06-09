# CompressData

- ea: `0x180027edc`
- end: `0x180027f72`
- name: `CompressData`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012fa0`
- `0x180020e28`

## callees

- `0x180004a40`
- `0x180027edc`

## pseudocode

```c
__int64 __fastcall CompressData(int a1, int a2, unsigned int *a3, __int64 a4)
{
  __int16 v4; // si
  unsigned int v5; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ecx
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF

  v4 = a1;
  v5 = 0;
  v8 = (int)(float)((float)a1 * 1.001) + 17;
  v11 = v8;
  if ( a4 )
  {
    if ( *a3 >= v8 )
    {
      if ( (unsigned int)a1 > 0xFFFF || (unsigned int)compress2((int)a4 + 4, (unsigned int)&v11, a2, a1, 9) )
      {
        return 1359;
      }
      else
      {
        v9 = v11 + 4;
        *(_BYTE *)a4 = 1;
        *(_WORD *)(a4 + 2) = v4;
        *a3 = v9;
      }
    }
    else
    {
      *a3 = v8;
      return 234;
    }
  }
  else
  {
    *a3 = v8;
  }
  return v5;
}

```

## disassembly

```asm
0x180027edc  push    rbx
0x180027ede  push    rsi
0x180027edf  push    rdi
0x180027ee0  push    r14
0x180027ee2  sub     rsp, 38h
0x180027ee6  xorps   xmm0, xmm0
0x180027ee9  mov     esi, ecx
0x180027eeb  xor     ebx, ebx
0x180027eed  mov     r14, r9
0x180027ef0  mov     rdi, r8
0x180027ef3  cvtsi2ss xmm0, rsi
0x180027ef8  mulss   xmm0, cs:__real@3f8020c5
0x180027f00  cvttss2si rax, xmm0
0x180027f05  add     eax, 11h
0x180027f08  mov     [rsp+58h+arg_0], eax
0x180027f0c  test    r9, r9
0x180027f0f  jnz     short loc_180027F16
0x180027f11  mov     [r8], eax
0x180027f14  jmp     short loc_180027F66
0x180027f16  cmp     [r8], eax
0x180027f19  jnb     short loc_180027F25
0x180027f1b  mov     [r8], eax
0x180027f1e  mov     ebx, 0EAh
0x180027f23  jmp     short loc_180027F66
0x180027f25  cmp     esi, 0FFFFh
0x180027f2b  jbe     short loc_180027F34
0x180027f2d  mov     ebx, 54Fh
0x180027f32  jmp     short loc_180027F66
0x180027f34  lea     rcx, [r9+4]
0x180027f38  mov     [rsp+58h+var_38], 9
0x180027f40  mov     r8, rdx
0x180027f43  mov     r9d, esi
0x180027f46  lea     rdx, [rsp+58h+arg_0]
0x180027f4b  call    compress2
0x180027f50  test    eax, eax
0x180027f52  jnz     short loc_180027F2D
0x180027f54  mov     ecx, [rsp+58h+arg_0]
0x180027f58  add     ecx, 4
0x180027f5b  mov     byte ptr [r14], 1
0x180027f5f  mov     [r14+2], si
0x180027f64  mov     [rdi], ecx
0x180027f66  mov     eax, ebx
0x180027f68  add     rsp, 38h
0x180027f6c  pop     r14
0x180027f6e  pop     rdi
0x180027f6f  pop     rsi
0x180027f70  pop     rbx
0x180027f71  retn
```
