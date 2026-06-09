# sub_409FAA

- ea: `0x409faa`
- end: `0x40a02a`
- name: `sub_409FAA`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x409faa`

## pseudocode

```c
void __usercall __noreturn sub_409FAA(int a1@<ebx>, _BYTE *a2@<esi>, int a3)
{
  int v3; // eax
  int v5; // ecx
  bool v6; // zf
  int v7; // [esp+2Eh] [ebp-10h]
  int v8; // [esp+32h] [ebp-Ch] BYREF
  int v9; // [esp+36h] [ebp-8h]
  int *v10; // [esp+3Ah] [ebp-4h] BYREF
  int savedregs; // [esp+3Eh] [ebp+0h] BYREF

  MEMORY[0x6D794310](a3, savedregs);
  savedregs = (int)&savedregs;
  if ( a3 )
  {
    if ( a3 != 1 )
    {
      MEMORY[0x899EB648](a1, v7, v8, v9, v10, savedregs);
      JUMPOUT(0x4A9883E);
    }
    v3 = MEMORY[0x42AF5499](0, a2, a1, v7, v8, v9, v10);
    MEMORY[0x35890CC5] += v3;
    MEMORY[0] = *a2;
    _ESI = a2 + 1;
    __asm { outsb }
    v6 = (_BYTE)v5 + *(_BYTE *)(v5 - 1064964027) == 0;
    *(_BYTE *)(v5 - 1064964027) += v5;
    if ( v6 || !*(_BYTE *)v3 )
      v3 = (int)_ESI;
    v10 = &v8;
    MEMORY[0x763FA193](v3, 1, 1, &v10);
    __halt();
  }
  JUMPOUT(0x33C2328);
}

```

## disassembly

```asm
0x409faa  mov     edi, edi
0x409fac  push    ebp
0x409fad  mov     ebp, esp
0x409faf  push    [ebp+arg_0]
0x409fb2  call    near ptr 6D794310h
0x409fb7  inc     edx
0x409fb8  add     [ebp+var_3D], bl
0x409fbb  mov     edi, edi
0x409fbd  push    ebp
0x409fbe  mov     ebp, esp
0x409fc0  sub     esp, 10h
0x409fc3  push    ebx
0x409fc4  mov     ebx, [ebp+arg_0]
0x409fc7  test    ebx, ebx
0x409fc9  jnz     short loc_409FD2
0x409fcb  xor     eax, eax
0x409fcd  jmp     near ptr 33C2328h
0x409fd2  jz      short loc_409FEF
0x409fd4  cmp     ebx, 1
0x409fd7  jz      short loc_409FEF
0x409fd9  call    near ptr 899EB648h
0x409fde  xor     al, ch
0x409fe0  mov     eax, esi
0x409fe2  jmp     near ptr 4A9883Eh
0x409fef  xor     edi, edi
0x409ff1  push    esi
0x409ff2  push    edi
0x409ff3  call    near ptr 42AF5499h
0x409ff8  add     [ebx+35890CC4h], al
0x409ffe  movsb
0x409fff  outsb
0x40a000  inc     edx
0x40a001  add     [ecx-3F7A0FBBh], cl
0x40a007  jz      short loc_40A00E
0x40a009  cmp     byte ptr [eax], 0
0x40a00c  jnz     short loc_40A013
0x40a00e  mov     eax, esi
0x40a010  mov     [ebp+var_10], esi
0x40a013  lea     ecx, [ebp+var_C]
0x40a016  mov     [ebp+var_4], edi
0x40a019  push    ecx
0x40a01a  lea     ecx, [ebp+var_4]
0x40a01d  mov     [ebp+var_C], edi
0x40a020  push    ecx
0x40a021  push    edi
0x40a022  push    edi
0x40a023  push    eax
0x40a024  call    near ptr 763FA193h
0x40a029  hlt
```
