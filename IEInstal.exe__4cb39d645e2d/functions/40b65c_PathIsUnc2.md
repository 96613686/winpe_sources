# PathIsUnc2

- ea: `0x40b65c`
- end: `0x40b6cd`
- name: `PathIsUnc2`
- size: `113`
- prototype: `BOOL __fastcall(_WORD *, _DWORD *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x40b6d3`
- `0x40b825`

## callees

- `0x40b645`
- `0x40b65c`
- `0x40ba88`
- `0x40bb42`

## pseudocode

```c
BOOL __fastcall PathIsUnc2(_WORD *a1, _DWORD *a2, int a3)
{
  BOOL v4; // ebx
  int v6; // eax
  const unsigned __int16 *v8; // [esp+0h] [ebp-Ch]
  int v9; // [esp+4h] [ebp-8h]

  v4 = 0;
  if ( a2 )
    *a2 = 0;
  if ( (unsigned __int8)IsBackslash(*a1) && (unsigned __int8)IsBackslash(a1[1]) )
  {
    if ( a1[2] == 63 )
    {
      if ( !StrIsEqualCaseInsensitive(L"\\UNC\\", a1 + 3, (const unsigned __int16 *)5, v8, v9) )
        return v4;
      v6 = 8;
      v4 = 1;
    }
    else
    {
      v4 = !PathIsVolumeGUIDWorker(v8);
      v6 = 2 * v4;
      if ( !v4 )
        return v4;
    }
    if ( a2 )
      *a2 = &a1[v6];
  }
  return v4;
}

```

## disassembly

```asm
0x40b65c  mov     edi, edi
0x40b65e  push    ebx
0x40b65f  push    esi; int
0x40b660  push    edi; unsigned __int16 *
0x40b661  mov     edi, edx
0x40b663  xor     ebx, ebx
0x40b665  mov     esi, ecx
0x40b667  test    edi, edi
0x40b669  jz      short loc_40B66D
0x40b66b  mov     [edi], ebx
0x40b66d  movzx   eax, word ptr [esi]
0x40b670  push    eax
0x40b671  call    IsBackslash
0x40b676  test    al, al
0x40b678  jz      short loc_40B6C5
0x40b67a  movzx   eax, word ptr [esi+2]
0x40b67e  push    eax
0x40b67f  call    IsBackslash
0x40b684  test    al, al
0x40b686  jz      short loc_40B6C5
0x40b688  cmp     word ptr [esi+4], 3Fh ; '?'
0x40b68d  jz      short loc_40B6A3
0x40b68f  mov     ecx, esi
0x40b691  call    ?PathIsVolumeGUIDWorker@@YG_NPBG@Z; PathIsVolumeGUIDWorker(ushort const *)
0x40b696  movzx   ebx, al
0x40b699  xor     ebx, 1
0x40b69c  lea     eax, [ebx+ebx]
0x40b69f  jz      short loc_40B6C5
0x40b6a1  jmp     short loc_40B6BC
0x40b6a3  push    5; unsigned __int16 *
0x40b6a5  lea     ecx, [esi+6]
0x40b6a8  mov     edx, offset aUnc; "\\UNC\\"
0x40b6ad  call    ?StrIsEqualCaseInsensitive@@YG_NPBG0H@Z; StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)
0x40b6b2  test    al, al
0x40b6b4  jz      short loc_40B6C5
0x40b6b6  push    8
0x40b6b8  xor     ebx, ebx
0x40b6ba  pop     eax
0x40b6bb  inc     ebx
0x40b6bc  test    edi, edi
0x40b6be  jz      short loc_40B6C5
0x40b6c0  lea     ecx, [esi+eax*2]
0x40b6c3  mov     [edi], ecx
0x40b6c5  pop     edi
0x40b6c6  pop     esi
0x40b6c7  mov     eax, ebx
0x40b6c9  pop     ebx
0x40b6ca  retn    4
```
