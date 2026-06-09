# ValidateUncompressedFormat

- ea: `0x18000a6b8`
- end: `0x18000a78c`
- name: `ValidateUncompressedFormat`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180080df0`

## callees

- `0x18000a6b8`
- `0x18008312c`

## pseudocode

```c
__int64 __fastcall ValidateUncompressedFormat(__int64 a1, _WORD *a2)
{
  __int64 v2; // rdx
  unsigned int v3; // r11d
  unsigned int v4; // ecx
  unsigned int v5; // r9d
  int v6; // r10d
  bool v7; // zf

  if ( *a2 == 1 || *a2 == 3 || *a2 == 0xFFFE )
  {
    if ( (unsigned int)ValidateWaveFormat() )
    {
      v4 = *(unsigned __int16 *)(v2 + 14);
      if ( (_WORD)v4 )
      {
        if ( (v4 & 7) == 0 )
        {
          v5 = *(unsigned __int16 *)(v2 + 2);
          v6 = *(unsigned __int16 *)(v2 + 12);
          if ( v5 * (v4 >> 3) == v6 && *(_DWORD *)(v2 + 4) * v6 == *(_DWORD *)(v2 + 8) )
          {
            if ( *(_WORD *)v2 == 0xFFFE )
            {
              if ( *(_WORD *)(v2 + 16) >= 0x16u && *(_WORD *)(v2 + 18) <= (unsigned __int16)v4 )
              {
                v7 = ((*(_DWORD *)(v2 + 24) - v3) & 0xFFFFFFFD) == 0;
                goto LABEL_17;
              }
            }
            else if ( *(_WORD *)v2 == (_WORD)v3 )
            {
              if ( v5 <= 2 && v4 <= 0x10 )
              {
                v7 = (v4 & 7) == 0;
LABEL_17:
                if ( v7 )
                  return v3;
              }
            }
            else
            {
              if ( *(_WORD *)v2 != 3 )
                return v3;
              if ( (unsigned __int16)v5 <= 2u )
                return v4 == 32;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000a6b8  mov     [rsp+arg_0], rbx
0x18000a6bd  push    rdi
0x18000a6be  sub     rsp, 20h
0x18000a6c2  mov     r11d, 1
0x18000a6c8  mov     edi, 0FFFEh
0x18000a6cd  cmp     [rdx], r11w
0x18000a6d1  jz      short loc_18000A6E2
0x18000a6d3  cmp     word ptr [rdx], 3
0x18000a6d7  jz      short loc_18000A6E2
0x18000a6d9  cmp     [rdx], di
0x18000a6dc  jnz     loc_18000A77F
0x18000a6e2  call    ValidateWaveFormat
0x18000a6e7  xor     ebx, ebx
0x18000a6e9  test    eax, eax
0x18000a6eb  jz      loc_18000A77F
0x18000a6f1  movzx   ecx, word ptr [rdx+0Eh]
0x18000a6f5  test    cx, cx
0x18000a6f8  jz      loc_18000A77F
0x18000a6fe  test    cl, 7
0x18000a701  jnz     short loc_18000A77F
0x18000a703  movzx   r9d, word ptr [rdx+2]
0x18000a708  mov     eax, ecx
0x18000a70a  movzx   r10d, word ptr [rdx+0Ch]
0x18000a70f  shr     eax, 3
0x18000a712  imul    eax, r9d
0x18000a716  cmp     eax, r10d
0x18000a719  jnz     short loc_18000A77F
0x18000a71b  imul    r10d, [rdx+4]
0x18000a720  cmp     r10d, [rdx+8]
0x18000a724  jnz     short loc_18000A77F
0x18000a726  cmp     [rdx], di
0x18000a729  jnz     short loc_18000A745
0x18000a72b  cmp     word ptr [rdx+10h], 16h
0x18000a730  jb      short loc_18000A77F
0x18000a732  cmp     [rdx+12h], cx
0x18000a736  ja      short loc_18000A77F
0x18000a738  mov     eax, [rdx+18h]
0x18000a73b  sub     eax, r11d
0x18000a73e  test    eax, 0FFFFFFFDh
0x18000a743  jmp     short loc_18000A75D
0x18000a745  cmp     [rdx], r11w
0x18000a749  jnz     short loc_18000A764
0x18000a74b  mov     eax, 2
0x18000a750  cmp     r9d, eax
0x18000a753  ja      short loc_18000A77F
0x18000a755  cmp     ecx, 10h
0x18000a758  ja      short loc_18000A77F
0x18000a75a  test    cl, 7
0x18000a75d  jnz     short loc_18000A77F
0x18000a75f  mov     eax, r11d
0x18000a762  jmp     short loc_18000A781
0x18000a764  cmp     word ptr [rdx], 3
0x18000a768  jnz     short loc_18000A75F
0x18000a76a  mov     eax, 2
0x18000a76f  cmp     r9w, ax
0x18000a773  ja      short loc_18000A77F
0x18000a775  cmp     ecx, 20h ; ' '
0x18000a778  mov     eax, ebx
0x18000a77a  setz    al
0x18000a77d  jmp     short loc_18000A781
0x18000a77f  xor     eax, eax
0x18000a781  mov     rbx, [rsp+28h+arg_0]
0x18000a786  add     rsp, 20h
0x18000a78a  pop     rdi
0x18000a78b  retn
```
