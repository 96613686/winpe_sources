# opus_select_arch

- ea: `0x180009360`
- end: `0x1800093fa`
- name: `opus_select_arch`
- size: `154`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003620`
- `0x180007330`
- `0x1800139b0`

## callees

- `0x180009360`

## pseudocode

```c
__int64 opus_select_arch()
{
  unsigned int v5; // r8d
  unsigned int v11; // r9d
  unsigned int v12; // r10d
  unsigned int v13; // r11d
  unsigned int v19; // ebx

  _RAX = 0;
  __asm { cpuid }
  v5 = _RAX;
  if ( !(_DWORD)_RAX )
    return 0;
  _RAX = 1;
  __asm { cpuid }
  v11 = ((unsigned int)_RDX >> 25) & 1;
  v12 = (unsigned int)_RDX >> 26;
  v13 = (unsigned int)_RCX >> 19;
  if ( (_RCX & 0x10000000) == 0 )
    goto LABEL_6;
  if ( (_RCX & 0x1000) != 0 && v5 >= 7 )
  {
    _RAX = 7;
    __asm { cpuid }
    v19 = ((unsigned int)_RBX >> 5) & 1;
  }
  else
  {
LABEL_6:
    v19 = 0;
  }
  if ( !v11 )
    return 0;
  if ( (v12 & 1) == 0 )
    return 1;
  if ( (v13 & 1) != 0 )
    return (unsigned int)(v19 != 0) + 3;
  return 2;
}

```

## disassembly

```asm
0x180009360  push    rbx
0x180009362  sub     rsp, 10h
0x180009366  xor     eax, eax
0x180009368  xor     ecx, ecx
0x18000936a  cpuid
0x18000936c  mov     r8d, eax
0x18000936f  cmp     eax, 1
0x180009372  jb      short loc_1800093F2
0x180009374  xor     ecx, ecx
0x180009376  mov     eax, 1
0x18000937b  cpuid
0x18000937d  mov     r9d, edx
0x180009380  mov     r10d, edx
0x180009383  shr     r9d, 19h
0x180009387  mov     r11d, ecx
0x18000938a  and     r9d, 1
0x18000938e  shr     r10d, 1Ah
0x180009392  shr     r11d, 13h
0x180009396  bt      ecx, 1Ch
0x18000939a  jnb     short loc_1800093B9
0x18000939c  bt      ecx, 0Ch
0x1800093a0  jnb     short loc_1800093B9
0x1800093a2  cmp     r8d, 7
0x1800093a6  jb      short loc_1800093B9
0x1800093a8  xor     ecx, ecx
0x1800093aa  mov     eax, 7
0x1800093af  cpuid
0x1800093b1  shr     ebx, 5
0x1800093b4  and     ebx, 1
0x1800093b7  jmp     short loc_1800093BB
0x1800093b9  xor     ebx, ebx
0x1800093bb  test    r9d, r9d
0x1800093be  jz      short loc_1800093F2
0x1800093c0  test    r10b, 1
0x1800093c4  jnz     short loc_1800093D1
0x1800093c6  mov     eax, 1
0x1800093cb  add     rsp, 10h
0x1800093cf  pop     rbx
0x1800093d0  retn
0x1800093d1  test    r11b, 1
0x1800093d5  jnz     short loc_1800093E2
0x1800093d7  mov     eax, 2
0x1800093dc  add     rsp, 10h
0x1800093e0  pop     rbx
0x1800093e1  retn
0x1800093e2  xor     eax, eax
0x1800093e4  test    ebx, ebx
0x1800093e6  setnz   al
0x1800093e9  add     eax, 3
0x1800093ec  add     rsp, 10h
0x1800093f0  pop     rbx
0x1800093f1  retn
0x1800093f2  xor     eax, eax
0x1800093f4  add     rsp, 10h
0x1800093f8  pop     rbx
0x1800093f9  retn
```
