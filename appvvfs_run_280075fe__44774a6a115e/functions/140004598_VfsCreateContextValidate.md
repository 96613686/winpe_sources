# VfsCreateContextValidate

- ea: `0x140004598`
- end: `0x1400046b4`
- name: `VfsCreateContextValidate`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003c00`

## callees

- `0x140004598`

## pseudocode

```c
__int64 __fastcall VfsCreateContextValidate(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 result; // rax
  int v5; // ecx
  unsigned int v6; // edx
  int v7; // eax
  int v8; // ecx

  if ( !*(_QWORD *)(a2 + 16) )
  {
    *a3 = 1;
    return 0;
  }
  v5 = *(_DWORD *)(a2 + 76);
  if ( (v5 & 0x6000) == 0x6000 )
    return 3221225485LL;
  v6 = *(unsigned __int8 *)(*(_QWORD *)(a1 + 16) + 35LL);
  if ( (v6 & 0xFFFFFFFA) == 0 && v6 != 1 && (v5 & 0x2000) != 0 )
    return 3221225485LL;
  if ( (v5 & 0x20) != 0 || (v5 & 0x18) == 0 )
    return 3221225530LL;
  if ( (v6 & 0xFFFFFFFA) != 0 || v6 == 1 || (v5 & 0xC0) == 0 || (v5 & 0x300) != 0x100 )
  {
    if ( ((v6 - 1) & 0xFFFFFFFD) != 0 || (v5 & 0xC0) == 0 || (v5 & 0x200) != 0 )
    {
      if ( (v5 & 0x200) == 0 )
        return 0;
      if ( v6 > 5 )
        return 0;
      v7 = 45;
      if ( !_bittest(&v7, v6) )
        return 0;
      v8 = v5 & 0x2100;
      if ( v8 == 256 )
      {
        return 3221225506LL;
      }
      else
      {
        result = 0;
        if ( v8 == 0x2000 )
          return 3221225506LL;
      }
    }
    else if ( (v5 & 0x100) != 0 )
    {
      return (v5 & 0x4000) != 0 ? 0xC00000BA : 0;
    }
    else
    {
      return (v5 & 0x2000) != 0 ? 0xC0000103 : 0;
    }
  }
  else if ( (v5 & 0x4000) != 0 )
  {
    return 3221225658LL;
  }
  else
  {
    return 3221225525LL;
  }
  return result;
}

```

## disassembly

```asm
0x140004598  cmp     qword ptr [rdx+10h], 0
0x14000459d  mov     r9, rcx
0x1400045a0  jnz     short loc_1400045AD
0x1400045a2  mov     dword ptr [r8], 1
0x1400045a9  xor     eax, eax
0x1400045ab  retn
0x1400045ad  mov     ecx, [rdx+4Ch]
0x1400045b0  mov     edx, 6000h
0x1400045b5  mov     eax, ecx
0x1400045b7  and     eax, edx
0x1400045b9  cmp     eax, edx
0x1400045bb  jz      loc_1400046AE
0x1400045c1  mov     rax, [r9+10h]
0x1400045c5  mov     r10d, 2000h
0x1400045cb  movzx   edx, byte ptr [rax+23h]
0x1400045cf  mov     eax, 0FFFFFFFAh
0x1400045d4  test    eax, edx
0x1400045d6  jnz     short loc_1400045E6
0x1400045d8  cmp     edx, 1
0x1400045db  jz      short loc_1400045E6
0x1400045dd  test    r10d, ecx
0x1400045e0  jnz     loc_1400046AE
0x1400045e6  test    cl, 20h
0x1400045e9  jnz     loc_1400046A7
0x1400045ef  test    cl, 18h
0x1400045f2  jz      loc_1400046A7
0x1400045f8  mov     r8d, 100h
0x1400045fe  test    eax, edx
0x140004600  jnz     short loc_14000462C
0x140004602  cmp     edx, 1
0x140004605  jz      short loc_14000462C
0x140004607  test    cl, 0C0h
0x14000460a  jz      short loc_14000462C
0x14000460c  mov     eax, ecx
0x14000460e  and     eax, 300h
0x140004613  cmp     eax, r8d
0x140004616  jnz     short loc_14000462C
0x140004618  bt      ecx, 0Eh
0x14000461c  jb      short loc_140004625
0x14000461e  mov     eax, 0C0000035h
0x140004623  retn
0x140004625  mov     eax, 0C00000BAh
0x14000462a  retn
0x14000462c  lea     eax, [rdx-1]
0x14000462f  test    eax, 0FFFFFFFDh
0x140004634  jnz     short loc_140004665
0x140004636  test    cl, 0C0h
0x140004639  jz      short loc_140004665
0x14000463b  bt      ecx, 9
0x14000463f  jb      short loc_140004665
0x140004641  test    r8d, ecx
0x140004644  jz      short loc_140004657
0x140004646  and     ecx, 4000h
0x14000464c  neg     ecx
0x14000464e  sbb     eax, eax
0x140004650  and     eax, 0C00000BAh
0x140004655  retn
0x140004657  and     ecx, r10d
0x14000465a  neg     ecx
0x14000465c  sbb     eax, eax
0x14000465e  and     eax, 0C0000103h
0x140004663  retn
0x140004665  bt      ecx, 9
0x140004669  jnb     loc_1400045A9
0x14000466f  cmp     edx, 5
0x140004672  ja      loc_1400045A9
0x140004678  mov     eax, 2Dh ; '-'
0x14000467d  bt      eax, edx
0x140004680  jnb     loc_1400045A9
0x140004686  and     ecx, 2100h
0x14000468c  cmp     ecx, r8d
0x14000468f  jz      short loc_1400046A0
0x140004691  xor     eax, eax
0x140004693  mov     edx, 0C0000022h
0x140004698  cmp     ecx, r10d
0x14000469b  cmovz   eax, edx
0x14000469e  retn
0x1400046a0  mov     eax, 0C0000022h
0x1400046a5  retn
0x1400046a7  mov     eax, 0C000003Ah
0x1400046ac  retn
0x1400046ae  mov     eax, 0C000000Dh
0x1400046b3  retn
```
