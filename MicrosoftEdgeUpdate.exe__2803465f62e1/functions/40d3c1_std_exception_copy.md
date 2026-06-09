# ___std_exception_copy

- ea: `0x40d3c1`
- end: `0x40d424`
- name: `___std_exception_copy`
- size: `99`
- prototype: `void __cdecl(int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x40b910`
- `0x40c266`

## callees

- `0x40d3c1`
- `0x40e294`
- `0x40ef25`
- `0x40f4c0`

## pseudocode

```c
void __cdecl __std_exception_copy(int a1, int a2)
{
  unsigned int v2; // kr00_4
  char *v3; // eax
  char *v4; // esi
  char *v5; // ecx

  if ( *(_BYTE *)(a1 + 4) && *(_DWORD *)a1 )
  {
    v2 = strlen(*(const char **)a1);
    v3 = (char *)malloc(v2 + 1);
    v4 = v3;
    if ( v3 )
    {
      strcpy_s(v3, v2 + 1, *(const char **)a1);
      v5 = v4;
      v4 = 0;
      *(_DWORD *)a2 = v5;
      *(_BYTE *)(a2 + 4) = 1;
    }
    free(v4);
  }
  else
  {
    *(_DWORD *)a2 = *(_DWORD *)a1;
    *(_BYTE *)(a2 + 4) = 0;
  }
}

```

## disassembly

```asm
0x40d3c1  push    ebp
0x40d3c2  mov     ebp, esp
0x40d3c4  push    edi
0x40d3c5  mov     edi, [ebp+arg_0]
0x40d3c8  cmp     byte ptr [edi+4], 0
0x40d3cc  jz      short loc_40D416
0x40d3ce  mov     ecx, [edi]
0x40d3d0  test    ecx, ecx
0x40d3d2  jz      short loc_40D416
0x40d3d4  lea     edx, [ecx+1]
0x40d3d7  mov     al, [ecx]
0x40d3d9  inc     ecx
0x40d3da  test    al, al
0x40d3dc  jnz     short loc_40D3D7
0x40d3de  sub     ecx, edx
0x40d3e0  push    ebx
0x40d3e1  push    esi
0x40d3e2  lea     ebx, [ecx+1]
0x40d3e5  push    ebx; Size
0x40d3e6  call    _malloc
0x40d3eb  mov     esi, eax
0x40d3ed  pop     ecx
0x40d3ee  test    esi, esi
0x40d3f0  jz      short loc_40D40B
0x40d3f2  push    dword ptr [edi]; Source
0x40d3f4  push    ebx; SizeInBytes
0x40d3f5  push    esi; Destination
0x40d3f6  call    _strcpy_s
0x40d3fb  mov     eax, [ebp+arg_4]
0x40d3fe  mov     ecx, esi
0x40d400  add     esp, 0Ch
0x40d403  xor     esi, esi
0x40d405  mov     [eax], ecx
0x40d407  mov     byte ptr [eax+4], 1
0x40d40b  push    esi; Block
0x40d40c  call    _free
0x40d411  pop     ecx
0x40d412  pop     esi
0x40d413  pop     ebx
0x40d414  jmp     short loc_40D421
0x40d416  mov     ecx, [ebp+arg_4]
0x40d419  mov     eax, [edi]
0x40d41b  mov     [ecx], eax
0x40d41d  mov     byte ptr [ecx+4], 0
0x40d421  pop     edi
0x40d422  pop     ebp
0x40d423  retn
```
