# SpatialDecParseExtensionConfig

- ea: `0x18007cb98`
- end: `0x18007cc8f`
- name: `SpatialDecParseExtensionConfig`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18007d4f4`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012264`
- `0x18007cb98`

## pseudocode

```c
__int64 __fastcall SpatialDecParseExtensionConfig(int *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  unsigned int v6; // edi
  __int64 v9; // r8
  int v10; // ebx
  __int64 v11; // r8
  int v12; // ebx
  int v13; // ebp
  __int64 v14; // r8
  int v15; // eax
  __int64 v16; // r8
  int v17; // r15d
  int v18; // ebp
  __int64 v19; // rdx

  v6 = 0;
  *(_DWORD *)(a2 + 120) = 0;
  *(_DWORD *)(a2 + 28) = 0;
  CDKsyncCache_0(a1);
  v10 = a6;
  if ( a1[2] < a6 )
    v10 = a1[2];
  while ( v10 >= 8 && *(int *)(a2 + 120) < 8 )
  {
    *(_DWORD *)(a2 + 4LL * *(int *)(a2 + 120) + 124) = CDKreadBits(a1, 4, v9);
    v12 = v10 - 8;
    v13 = CDKreadBits(a1, 4, v11);
    if ( v13 == 15 )
    {
      v15 = CDKreadBits(a1, 8, v14);
      v12 -= 8;
      v13 = v15 + 15;
      if ( v15 == 255 )
      {
        v12 -= 16;
        v13 = CDKreadBits(a1, 16, v16) + 270;
      }
    }
    CDKsyncCache_0(a1);
    v17 = a1[2];
    if ( v17 <= 0 )
      return (unsigned int)-982;
    v18 = 8 * v13;
    if ( v17 < v18 )
      return (unsigned int)-982;
    if ( v12 < v18 )
      return (unsigned int)-982;
    CDKsyncCache_0(a1);
    v19 = (unsigned int)(v18 + a1[2] - v17);
    if ( (int)v19 < 0 )
      return (unsigned int)-982;
    CDKpushFor(a1, v19);
    v10 = v12 - v18;
    ++*(_DWORD *)(a2 + 120);
  }
  return v6;
}

```

## disassembly

```asm
0x18007cb98  push    rbx
0x18007cb9a  push    rbp
0x18007cb9b  push    rsi
0x18007cb9c  push    rdi
0x18007cb9d  push    r14
0x18007cb9f  push    r15
0x18007cba1  sub     rsp, 28h
0x18007cba5  xor     edi, edi
0x18007cba7  mov     r14, rdx
0x18007cbaa  mov     [rdx+78h], edi
0x18007cbad  mov     rsi, rcx
0x18007cbb0  mov     [rdx+1Ch], edi
0x18007cbb3  call    CDKsyncCache_0
0x18007cbb8  mov     ebx, [rsp+58h+arg_28]
0x18007cbbf  cmp     [rsi+8], ebx
0x18007cbc2  cmovl   ebx, [rsi+8]
0x18007cbc6  cmp     ebx, 8
0x18007cbc9  jl      loc_18007CC7F
0x18007cbcf  cmp     dword ptr [r14+78h], 8
0x18007cbd4  jge     loc_18007CC7F
0x18007cbda  mov     edx, 4
0x18007cbdf  mov     rcx, rsi
0x18007cbe2  call    CDKreadBits
0x18007cbe7  mov     ecx, eax
0x18007cbe9  mov     edx, 4
0x18007cbee  movsxd  rax, dword ptr [r14+78h]
0x18007cbf2  mov     [r14+rax*4+7Ch], ecx
0x18007cbf7  mov     rcx, rsi
0x18007cbfa  call    CDKreadBits
0x18007cbff  sub     ebx, 8
0x18007cc02  mov     ebp, eax
0x18007cc04  cmp     eax, 0Fh
0x18007cc07  jnz     short loc_18007CC38
0x18007cc09  lea     edx, [rax-7]
0x18007cc0c  mov     rcx, rsi
0x18007cc0f  call    CDKreadBits
0x18007cc14  add     ebx, 0FFFFFFF8h
0x18007cc17  lea     ebp, [rax+0Fh]
0x18007cc1a  cmp     ebp, 10Eh
0x18007cc20  jnz     short loc_18007CC38
0x18007cc22  mov     edx, 10h
0x18007cc27  mov     rcx, rsi
0x18007cc2a  call    CDKreadBits
0x18007cc2f  add     ebx, 0FFFFFFF0h
0x18007cc32  lea     ebp, [rax+10Eh]
0x18007cc38  mov     rcx, rsi
0x18007cc3b  call    CDKsyncCache_0
0x18007cc40  mov     r15d, [rsi+8]
0x18007cc44  test    r15d, r15d
0x18007cc47  jle     short loc_18007CC7A
0x18007cc49  shl     ebp, 3
0x18007cc4c  cmp     r15d, ebp
0x18007cc4f  jl      short loc_18007CC7A
0x18007cc51  cmp     ebx, ebp
0x18007cc53  jl      short loc_18007CC7A
0x18007cc55  mov     rcx, rsi
0x18007cc58  call    CDKsyncCache_0
0x18007cc5d  mov     edx, [rsi+8]
0x18007cc60  sub     edx, r15d
0x18007cc63  add     edx, ebp
0x18007cc65  js      short loc_18007CC7A
0x18007cc67  mov     rcx, rsi
0x18007cc6a  call    CDKpushFor
0x18007cc6f  sub     ebx, ebp
0x18007cc71  inc     dword ptr [r14+78h]
0x18007cc75  jmp     loc_18007CBC6
0x18007cc7a  mov     edi, 0FFFFFC2Ah
0x18007cc7f  mov     eax, edi
0x18007cc81  add     rsp, 28h
0x18007cc85  pop     r15
0x18007cc87  pop     r14
0x18007cc89  pop     rdi
0x18007cc8a  pop     rsi
0x18007cc8b  pop     rbp
0x18007cc8c  pop     rbx
0x18007cc8d  retn
```
