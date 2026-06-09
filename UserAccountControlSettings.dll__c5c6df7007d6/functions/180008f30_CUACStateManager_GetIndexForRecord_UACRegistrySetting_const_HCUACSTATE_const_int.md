# CUACStateManager::_GetIndexForRecord(_UACRegistrySetting const *,HCUACSTATE const *,int)

- ea: `0x180008f30`
- end: `0x180008fe4`
- name: `?_GetIndexForRecord@CUACStateManager@@AEBAHPEBU_UACRegistrySetting@@PEBW4HCUACSTATE@@H@Z`
- size: `180`
- prototype: `__int64 __fastcall(CUACStateManager *__hidden this, const struct _UACRegistrySetting *, const enum HCUACSTATE *, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180008ab0`
- `0x180008b20`
- `0x180008c10`
- `0x180008e50`

## callees

- `0x180008f30`

## pseudocode

```c
__int64 __fastcall CUACStateManager::_GetIndexForRecord(
        CUACStateManager *this,
        const struct _UACRegistrySetting *a2,
        const enum HCUACSTATE *a3,
        int a4)
{
  unsigned int v4; // r11d
  int v7; // ecx
  int v8; // ebx
  int v9; // r9d
  unsigned int v10; // r8d
  bool v11; // al

  v4 = -1;
  if ( !a2 )
  {
    v7 = 0;
    v8 = 0;
    v9 = 0;
    goto LABEL_8;
  }
  v7 = *(_DWORD *)a2;
  v8 = *((_DWORD *)a2 + 2);
  if ( *(_DWORD *)a2 == 2 )
  {
    v7 = 4;
  }
  else
  {
    v9 = *((_DWORD *)a2 + 1);
    if ( v7 != 1 )
      goto LABEL_8;
    v7 = 3;
  }
  v9 = 1;
LABEL_8:
  v10 = 0;
  while ( v4 == -1 )
  {
    v11 = *((_DWORD *)&qword_18000F170 + 5 * (int)v10 + 1) == a4;
    if ( a2 && *((_DWORD *)&qword_18000F170 + 5 * (int)v10 + 1) == a4 )
      v11 = *((_DWORD *)&qword_18000F170 + 5 * (int)v10 + 2) == v7
         && *((_DWORD *)&qword_18000F170 + 5 * (int)v10 + 4) == v8
         && *((_DWORD *)&qword_18000F170 + 5 * (int)v10 + 3) == v9;
    if ( a3 )
    {
      if ( !v11 || *((_DWORD *)&qword_18000F170 + 5 * (int)v10) != *(_DWORD *)a3 )
        goto LABEL_23;
LABEL_22:
      v4 = v10;
      goto LABEL_23;
    }
    if ( v11 )
      goto LABEL_22;
LABEL_23:
    if ( ++v10 >= 0x21 )
      return v4;
  }
  return v4;
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  push    rsi
0x180008f33  push    rdi
0x180008f34  push    r14
0x180008f36  or      r11d, 0FFFFFFFFh
0x180008f3a  mov     esi, r9d
0x180008f3d  mov     rdi, r8
0x180008f40  test    rdx, rdx
0x180008f43  jz      short loc_180008F6B
0x180008f45  mov     ecx, [rdx]
0x180008f47  mov     ebx, [rdx+8]
0x180008f4a  cmp     ecx, 2
0x180008f4d  jnz     short loc_180008F5B
0x180008f4f  lea     ecx, [r11+5]
0x180008f53  mov     r9d, 1
0x180008f59  jmp     short loc_180008F72
0x180008f5b  mov     r9d, [rdx+4]
0x180008f5f  cmp     ecx, 1
0x180008f62  jnz     short loc_180008F72
0x180008f64  mov     ecx, 3
0x180008f69  jmp     short loc_180008F53
0x180008f6b  xor     ecx, ecx
0x180008f6d  xor     ebx, ebx
0x180008f6f  xor     r9d, r9d
0x180008f72  xor     r8d, r8d
0x180008f75  lea     r14, qword_18000F170
0x180008f7c  cmp     r11d, 0FFFFFFFFh
0x180008f80  jnz     short loc_180008FDB
0x180008f82  movsxd  rax, r8d
0x180008f85  lea     r10, [rax+rax*4]
0x180008f89  cmp     [r14+r10*4+4], esi
0x180008f8e  setz    al
0x180008f91  test    rdx, rdx
0x180008f94  jz      short loc_180008FB8
0x180008f96  cmp     [r14+r10*4+4], esi
0x180008f9b  jnz     short loc_180008FB8
0x180008f9d  cmp     [r14+r10*4+8], ecx
0x180008fa2  jnz     short loc_180008FB6
0x180008fa4  cmp     [r14+r10*4+10h], ebx
0x180008fa9  jnz     short loc_180008FB6
0x180008fab  cmp     [r14+r10*4+0Ch], r9d
0x180008fb0  jnz     short loc_180008FB6
0x180008fb2  mov     al, 1
0x180008fb4  jmp     short loc_180008FB8
0x180008fb6  xor     al, al
0x180008fb8  test    rdi, rdi
0x180008fbb  jz      short loc_180008FCB
0x180008fbd  test    al, al
0x180008fbf  jz      short loc_180008FD2
0x180008fc1  mov     eax, [rdi]
0x180008fc3  cmp     [r14+r10*4], eax
0x180008fc7  jnz     short loc_180008FD2
0x180008fc9  jmp     short loc_180008FCF
0x180008fcb  test    al, al
0x180008fcd  jz      short loc_180008FD2
0x180008fcf  mov     r11d, r8d
0x180008fd2  inc     r8d
0x180008fd5  cmp     r8d, 21h ; '!'
0x180008fd9  jb      short loc_180008F7C
0x180008fdb  mov     eax, r11d
0x180008fde  pop     r14
0x180008fe0  pop     rdi
0x180008fe1  pop     rsi
0x180008fe2  pop     rbx
0x180008fe3  retn
```
