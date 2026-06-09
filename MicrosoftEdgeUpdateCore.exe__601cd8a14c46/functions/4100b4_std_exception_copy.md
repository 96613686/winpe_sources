# ___std_exception_copy

- ea: `0x4100b4`
- end: `0x410117`
- name: `___std_exception_copy`
- size: `99`
- prototype: `void __cdecl(int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x40fb60`
- `0x41de9d`

## callees

- `0x4100b4`
- `0x4101a2`
- `0x4116f4`
- `0x4116ff`

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
0x4100b4  push    ebp
0x4100b5  mov     ebp, esp
0x4100b7  push    edi
0x4100b8  mov     edi, [ebp+arg_0]
0x4100bb  cmp     byte ptr [edi+4], 0
0x4100bf  jz      short loc_410109
0x4100c1  mov     ecx, [edi]
0x4100c3  test    ecx, ecx
0x4100c5  jz      short loc_410109
0x4100c7  lea     edx, [ecx+1]
0x4100ca  mov     al, [ecx]
0x4100cc  inc     ecx
0x4100cd  test    al, al
0x4100cf  jnz     short loc_4100CA
0x4100d1  sub     ecx, edx
0x4100d3  push    ebx
0x4100d4  push    esi
0x4100d5  lea     ebx, [ecx+1]
0x4100d8  push    ebx; Size
0x4100d9  call    _malloc
0x4100de  mov     esi, eax
0x4100e0  pop     ecx
0x4100e1  test    esi, esi
0x4100e3  jz      short loc_4100FE
0x4100e5  push    dword ptr [edi]; Source
0x4100e7  push    ebx; SizeInBytes
0x4100e8  push    esi; Destination
0x4100e9  call    _strcpy_s
0x4100ee  mov     eax, [ebp+arg_4]
0x4100f1  mov     ecx, esi
0x4100f3  add     esp, 0Ch
0x4100f6  xor     esi, esi
0x4100f8  mov     [eax], ecx
0x4100fa  mov     byte ptr [eax+4], 1
0x4100fe  push    esi; Block
0x4100ff  call    _free
0x410104  pop     ecx
0x410105  pop     esi
0x410106  pop     ebx
0x410107  jmp     short loc_410114
0x410109  mov     ecx, [ebp+arg_4]
0x41010c  mov     eax, [edi]
0x41010e  mov     [ecx], eax
0x410110  mov     byte ptr [ecx+4], 0
0x410114  pop     edi
0x410115  pop     ebp
0x410116  retn
```
