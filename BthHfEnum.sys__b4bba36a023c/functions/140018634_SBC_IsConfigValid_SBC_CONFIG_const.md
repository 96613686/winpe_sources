# SBC::IsConfigValid(SBC_CONFIG const &)

- ea: `0x140018634`
- end: `0x1400186a9`
- name: `?IsConfigValid@SBC@@SA_NAEBUSBC_CONFIG@@@Z`
- size: `117`
- prototype: `bool __fastcall(const struct SBC_CONFIG *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140017fe8`
- `0x140018094`

## callees

- `0x140018634`

## pseudocode

```c
char __fastcall SBC::IsConfigValid(const struct SBC_CONFIG *a1)
{
  int v2; // r9d
  char v3; // cl
  int v4; // eax
  int v5; // r8d
  int v6; // r10d

  if ( *(_DWORD *)a1 == 4 )
    return 0;
  if ( *((_DWORD *)a1 + 5) == 2 )
    return 0;
  v2 = *((_DWORD *)a1 + 3);
  if ( v2 == 4 )
    return 0;
  v3 = 1;
  if ( v2 < 2 && *((_DWORD *)a1 + 4) != 1 )
    return 0;
  v4 = *((_DWORD *)a1 + 1);
  if ( v4 > 16 || !*((_BYTE *)a1 + 28) && (v4 & 3) != 0 )
    return 0;
  v5 = *((_DWORD *)a1 + 2);
  if ( ((v5 - 4) & 0xFFFFFFFB) != 0 )
    return 0;
  v6 = *((_DWORD *)a1 + 6);
  if ( (unsigned int)(v6 - 2) > 0x33 || v2 < 2 && v6 > 16 * v5 )
    return 0;
  if ( v6 > 32 * v5 )
    return 0;
  return v3;
}

```

## disassembly

```asm
0x140018634  cmp     dword ptr [rcx], 4
0x140018637  mov     rdx, rcx
0x14001863a  jz      short loc_1400186A4
0x14001863c  cmp     dword ptr [rcx+14h], 2
0x140018640  jz      short loc_1400186A4
0x140018642  mov     r9d, [rcx+0Ch]
0x140018646  cmp     r9d, 4
0x14001864a  jz      short loc_1400186A4
0x14001864c  mov     ecx, 1
0x140018651  cmp     r9d, 2
0x140018655  jge     short loc_14001865C
0x140018657  cmp     [rdx+10h], ecx
0x14001865a  jnz     short loc_1400186A4
0x14001865c  mov     eax, [rdx+4]
0x14001865f  cmp     eax, 10h
0x140018662  jg      short loc_1400186A4
0x140018664  cmp     byte ptr [rdx+1Ch], 0
0x140018668  jnz     short loc_14001866E
0x14001866a  test    al, 3
0x14001866c  jnz     short loc_1400186A4
0x14001866e  mov     r8d, [rdx+8]
0x140018672  lea     eax, [r8-4]
0x140018676  test    eax, 0FFFFFFFBh
0x14001867b  jnz     short loc_1400186A4
0x14001867d  mov     r10d, [rdx+18h]
0x140018681  lea     eax, [r10-2]
0x140018685  cmp     eax, 33h ; '3'
0x140018688  ja      short loc_1400186A4
0x14001868a  cmp     r9d, 2
0x14001868e  jge     short loc_14001869B
0x140018690  mov     eax, r8d
0x140018693  shl     eax, 4
0x140018696  cmp     r10d, eax
0x140018699  jg      short loc_1400186A4
0x14001869b  shl     r8d, 5
0x14001869f  cmp     r10d, r8d
0x1400186a2  jle     short loc_1400186A6
0x1400186a4  xor     cl, cl
0x1400186a6  mov     al, cl
0x1400186a8  retn
```
