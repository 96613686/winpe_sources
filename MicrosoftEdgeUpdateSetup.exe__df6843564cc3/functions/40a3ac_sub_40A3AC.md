# sub_40A3AC

- ea: `0x40a3ac`
- end: `0x40a452`
- name: `sub_40A3AC`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x40a3ac`

## pseudocode

```c

```

## disassembly

```asm
0x40a3ac  mov     edi, edi
0x40a3ae  push    ebp
0x40a3af  mov     ebp, esp
0x40a3b1  mov     eax, [ebp+arg_0]
0x40a3b4  mov     eax, [eax]
0x40a3b6  cmp     eax, dword_426E54
0x40a3bc  jz      short loc_40A3C5
0x40a3be  push    eax
0x40a3bf  call    near ptr 0CD04011Dh
0x40a3c5  int     3; Trap to Debugger
0x40a3c6  int     3; Trap to Debugger
0x40a3c7  int     3; Trap to Debugger
0x40a3c8  mov     edi, edi
0x40a3ca  push    ebp
0x40a3cb  mov     ebp, esp
0x40a3cd  mov     eax, [ebp+arg_0]
0x40a3d0  mov     eax, [eax]
0x40a3d2  cmp     eax, dword_426E50
0x40a3d8  jz      short loc_40A3E1
0x40a3da  push    eax
0x40a3db  call    near ptr 69040139h
0x40a3e0  pusha
0x40a3e1  mov     bh, 40h ; '@'
0x40a3e3  add     byte_426E48[ecx], bh
0x40a3e9  call    near ptr 40F82456h
0x40a3ee  add     byte_426E4C[ecx], bh
0x40a3f4  call    near ptr 6E94D9F8h
0x40a3f9  inc     edx
0x40a3fa  add     al, ch
0x40a3fc  push    dword_426E50
0x40a402  call    near ptr 0EA03FD60h
0x40a407  mov     edi, edi
0x40a409  push    ebx
0x40a40a  push    esi
0x40a40b  call    near ptr 6EF4D99Bh
0x40a410  inc     edx
0x40a411  add     [ebp+var_41FA8A0A], al
0x40a417  pop     eax
0x40a418  outsb
0x40a419  inc     edx
0x40a41a  add     [edx], dh
0x40a41c  fisttp  dword ptr [edx+77203C06h]
0x40a422  or      [eax+eax*8-247BD58Ch], al
0x40a429  jz      short loc_40A446
0x40a42b  cmp     al, 22h ; '"'
0x40a42d  jnz     short loc_40A434
0x40a42f  test    bl, bl
0x40a431  setz    bl
0x40a434  movzx   eax, al
0x40a437  push    eax
0x40a438  call    near ptr 75012996h
0x40a43d  add     [esi+46h], eax
0x40a440  jmp     short loc_40A419
0x40a442  cmp     al, 20h ; ' '
0x40a444  ja      short loc_40A44D
0x40a446  inc     esi
0x40a447  mov     al, [esi]
0x40a449  test    al, al
0x40a44b  jnz     short loc_40A442
0x40a44d  mov     eax, esi
0x40a44f  pop     esi
0x40a450  pop     ebx
0x40a451  retn
```
