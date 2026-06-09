# ownGetCacheSize

- ea: `0x180010f63`
- end: `0x180011010`
- name: `ownGetCacheSize`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010f63`

## pseudocode

```c
__int64 __fastcall ownGetCacheSize(int *a1)
{
  int *v2; // rbp
  unsigned int v3; // esi
  __int64 result; // rax
  int v10; // edx
  __int64 v11; // rcx
  int v12; // [rsp+0h] [rbp-38h] BYREF
  int v13; // [rsp+4h] [rbp-34h] BYREF

  v2 = &v12;
  v3 = 0;
  _RAX = 2;
  __asm { cpuid }
  if ( (_BYTE)_RAX != 1 )
    return 0xFFFFFFFFLL;
  if ( (int)_RAX < 0 )
    LODWORD(_RAX) = 0;
  if ( (int)_RBX < 0 )
    LODWORD(_RBX) = 0;
  if ( (int)_RCX < 0 )
    LODWORD(_RCX) = 0;
  if ( (int)_RDX < 0 )
    LODWORD(_RDX) = 0;
  if ( (_DWORD)_RAX )
  {
    v12 = _RAX;
    v2 = &v13;
    v3 = 3;
  }
  if ( (_DWORD)_RBX )
  {
    *v2++ = _RBX;
    v3 += 4;
  }
  if ( (_DWORD)_RCX )
  {
    *v2++ = _RCX;
    v3 += 4;
  }
  if ( (_DWORD)_RDX )
  {
    *v2 = _RDX;
    v3 += 4;
  }
  if ( !v3 )
    return 0xFFFFFFFFLL;
  result = 0xFFFFFFFFLL;
LABEL_20:
  v10 = *a1;
  if ( *a1 )
  {
    a1 += 2;
    v11 = v3;
    while ( (_BYTE)v10 != *((_BYTE *)&v12 + v11) )
    {
      v11 = (unsigned int)(v11 - 1);
      if ( !(_DWORD)v11 )
        goto LABEL_20;
    }
    return (unsigned int)*(a1 - 1);
  }
  return result;
}

```

## disassembly

```asm
0x180010f63  push    rsi
0x180010f64  push    rdi
0x180010f65  push    rbx
0x180010f66  push    rbp
0x180010f67  sub     rsp, 18h
0x180010f6b  mov     rdi, rcx
0x180010f6e  mov     rbp, rsp
0x180010f71  xor     esi, esi
0x180010f73  mov     eax, 2
0x180010f78  cpuid
0x180010f7a  cmp     al, 1
0x180010f7c  jnz     loc_180011009
0x180010f82  test    eax, 80000000h
0x180010f87  jz      short loc_180010F8B
0x180010f89  xor     eax, eax
0x180010f8b  test    ebx, 80000000h
0x180010f91  jz      short loc_180010F95
0x180010f93  xor     ebx, ebx
0x180010f95  test    ecx, 80000000h
0x180010f9b  jz      short loc_180010F9F
0x180010f9d  xor     ecx, ecx
0x180010f9f  test    edx, 80000000h
0x180010fa5  jz      short loc_180010FA9
0x180010fa7  xor     edx, edx
0x180010fa9  test    eax, eax
0x180010fab  jz      short loc_180010FB7
0x180010fad  mov     [rbp+0], eax
0x180010fb0  add     rbp, 4
0x180010fb4  add     esi, 3
0x180010fb7  test    ebx, ebx
0x180010fb9  jz      short loc_180010FC5
0x180010fbb  mov     [rbp+0], ebx
0x180010fbe  add     rbp, 4
0x180010fc2  add     esi, 4
0x180010fc5  test    ecx, ecx
0x180010fc7  jz      short loc_180010FD3
0x180010fc9  mov     [rbp+0], ecx
0x180010fcc  add     rbp, 4
0x180010fd0  add     esi, 4
0x180010fd3  test    edx, edx
0x180010fd5  jz      short loc_180010FDD
0x180010fd7  mov     [rbp+0], edx
0x180010fda  add     esi, 4
0x180010fdd  test    esi, esi
0x180010fdf  jz      short loc_180011009
0x180010fe1  mov     eax, 0FFFFFFFFh
0x180010fe6  xor     edx, edx
0x180010fe8  add     edx, [rdi]
0x180010fea  jz      short loc_180011000
0x180010fec  add     rdi, 8
0x180010ff0  mov     ecx, esi
0x180010ff2  cmp     dl, [rsp+rcx+38h+var_38]
0x180010ff5  jz      short loc_180010FFD
0x180010ff7  dec     ecx
0x180010ff9  jnz     short loc_180010FF2
0x180010ffb  jmp     short loc_180010FE6
0x180010ffd  mov     eax, [rdi-4]
0x180011000  add     rsp, 18h
0x180011004  pop     rbp
0x180011005  pop     rbx
0x180011006  pop     rdi
0x180011007  pop     rsi
0x180011008  retn
0x180011009  mov     eax, 0FFFFFFFFh
0x18001100e  jmp     short loc_180011000
```
