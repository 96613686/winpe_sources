# CFileBuffer::QueryPosition(ulong,ulong)

- ea: `0x18001692c`
- end: `0x180016989`
- name: `?QueryPosition@CFileBuffer@@QEAAHKK@Z`
- size: `93`
- prototype: `__int64 __fastcall(CFileBuffer *__hidden this, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180016a94`
- `0x180016d20`
- `0x180017170`

## callees

- `0x18001692c`

## pseudocode

```c
_BOOL8 __fastcall CFileBuffer::QueryPosition(CFileBuffer *this, unsigned int a2, unsigned int a3)
{
  unsigned int v4; // r8d
  unsigned int v5; // edx
  unsigned int v7; // ecx

  if ( *(_DWORD *)this != 2 )
  {
    v4 = *((_DWORD *)this + 9)
       + a3
       - 1
       - (*((unsigned int *)this + 9) + (unsigned __int64)a3 - 1) % *((unsigned int *)this + 9);
    if ( a2 < v4 )
    {
      v7 = *((_DWORD *)this + 8);
      if ( a2 >= v7 )
        return a2 < *((_DWORD *)this + 7) + v7;
    }
    else
    {
      v5 = *((_DWORD *)this + 7);
      if ( !v5 || v5 + *((_DWORD *)this + 8) == v4 && v5 < *((_DWORD *)this + 6) )
        return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001692c  cmp     dword ptr [rcx], 2
0x18001692f  mov     r11d, edx
0x180016932  mov     r10, rcx
0x180016935  jz      short loc_180016986
0x180016937  mov     r9d, [rcx+24h]
0x18001693b  xor     edx, edx
0x18001693d  mov     r8d, r8d
0x180016940  dec     r8
0x180016943  add     r8, r9
0x180016946  mov     rax, r8
0x180016949  div     r9
0x18001694c  sub     r8d, edx
0x18001694f  cmp     r11d, r8d
0x180016952  jb      short loc_180016971
0x180016954  mov     edx, [rcx+1Ch]
0x180016957  test    edx, edx
0x180016959  jz      short loc_18001696B
0x18001695b  mov     ecx, [rcx+20h]
0x18001695e  add     ecx, edx
0x180016960  cmp     ecx, r8d
0x180016963  jnz     short loc_180016986
0x180016965  cmp     edx, [r10+18h]
0x180016969  jnb     short loc_180016986
0x18001696b  mov     eax, 1
0x180016970  retn
0x180016971  mov     ecx, [rcx+20h]
0x180016974  cmp     r11d, ecx
0x180016977  jb      short loc_180016986
0x180016979  add     ecx, [r10+1Ch]
0x18001697d  xor     eax, eax
0x18001697f  cmp     r11d, ecx
0x180016982  setb    al
0x180016985  retn
0x180016986  xor     eax, eax
0x180016988  retn
```
