# StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)

- ea: `0x40ba88`
- end: `0x40bad2`
- name: `?StrIsEqualCaseInsensitive@@YG_NPBG0H@Z`
- size: `74`
- prototype: `bool __userpurge@<al>(unsigned __int16 *@<edx>, unsigned __int16 *@<ecx>, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x40b65c`
- `0x40b6d3`
- `0x40bb42`

## callees

- `0x40ba88`

## pseudocode

```c
bool __userpurge StrIsEqualCaseInsensitive@<al>(
        unsigned __int16 *a1@<edx>,
        unsigned __int16 *a2@<ecx>,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  int v7; // esi
  int v8; // ecx
  int v9; // edx
  int v10; // esi

  do
  {
    v7 = *a2++;
    v8 = *a1++;
    v9 = v7 + 32;
    if ( (unsigned int)(v7 - 65) > 0x19 )
      v9 = v7;
    v10 = v8 + 32;
    if ( (unsigned int)(v8 - 65) > 0x19 )
      v10 = v8;
    a3 = (const unsigned __int16 *)((char *)a3 - 1);
  }
  while ( a3 && v9 && v9 == v10 );
  return v9 == v10;
}

```

## disassembly

```asm
0x40ba88  mov     edi, edi
0x40ba8a  push    ebp
0x40ba8b  mov     ebp, esp
0x40ba8d  push    ebx
0x40ba8e  push    esi
0x40ba8f  push    edi
0x40ba90  mov     edi, edx
0x40ba92  mov     ebx, ecx
0x40ba94  movzx   esi, word ptr [ebx]
0x40ba97  lea     ebx, [ebx+2]
0x40ba9a  movzx   ecx, word ptr [edi]
0x40ba9d  lea     edi, [edi+2]
0x40baa0  lea     eax, [esi-41h]
0x40baa3  cmp     eax, 19h
0x40baa6  lea     edx, [esi+20h]
0x40baa9  lea     eax, [ecx-41h]
0x40baac  cmova   edx, esi
0x40baaf  cmp     eax, 19h
0x40bab2  lea     esi, [ecx+20h]
0x40bab5  cmova   esi, ecx
0x40bab8  sub     [ebp+arg_0], 1
0x40babc  jz      short loc_40BAC6
0x40babe  test    edx, edx
0x40bac0  jz      short loc_40BAC6
0x40bac2  cmp     edx, esi
0x40bac4  jz      short loc_40BA94
0x40bac6  pop     edi
0x40bac7  cmp     edx, esi
0x40bac9  pop     esi
0x40baca  setz    al
0x40bacd  pop     ebx
0x40bace  pop     ebp
0x40bacf  retn    4
```
