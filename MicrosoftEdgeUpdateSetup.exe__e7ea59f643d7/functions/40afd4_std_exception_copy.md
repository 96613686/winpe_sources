# ___std_exception_copy

- ea: `0x40afd4`
- end: `0x40b037`
- name: `___std_exception_copy`
- size: `99`
- prototype: `void __cdecl(int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x40aa80`

## callees

- `0x40afd4`
- `0x40c28b`
- `0x40c2a6`
- `0x40c2b1`

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
0x40afd4  push    ebp
0x40afd5  mov     ebp, esp
0x40afd7  push    edi
0x40afd8  mov     edi, [ebp+arg_0]
0x40afdb  cmp     byte ptr [edi+4], 0
0x40afdf  jz      short loc_40B029
0x40afe1  mov     ecx, [edi]
0x40afe3  test    ecx, ecx
0x40afe5  jz      short loc_40B029
0x40afe7  lea     edx, [ecx+1]
0x40afea  mov     al, [ecx]
0x40afec  inc     ecx
0x40afed  test    al, al
0x40afef  jnz     short loc_40AFEA
0x40aff1  sub     ecx, edx
0x40aff3  push    ebx
0x40aff4  push    esi
0x40aff5  lea     ebx, [ecx+1]
0x40aff8  push    ebx; Size
0x40aff9  call    _malloc
0x40affe  mov     esi, eax
0x40b000  pop     ecx
0x40b001  test    esi, esi
0x40b003  jz      short loc_40B01E
0x40b005  push    dword ptr [edi]; Source
0x40b007  push    ebx; SizeInBytes
0x40b008  push    esi; Destination
0x40b009  call    _strcpy_s
0x40b00e  mov     eax, [ebp+arg_4]
0x40b011  mov     ecx, esi
0x40b013  add     esp, 0Ch
0x40b016  xor     esi, esi
0x40b018  mov     [eax], ecx
0x40b01a  mov     byte ptr [eax+4], 1
0x40b01e  push    esi; Block
0x40b01f  call    _free
0x40b024  pop     ecx
0x40b025  pop     esi
0x40b026  pop     ebx
0x40b027  jmp     short loc_40B034
0x40b029  mov     ecx, [ebp+arg_4]
0x40b02c  mov     eax, [edi]
0x40b02e  mov     [ecx], eax
0x40b030  mov     byte ptr [ecx+4], 0
0x40b034  pop     edi
0x40b035  pop     ebp
0x40b036  retn
```
