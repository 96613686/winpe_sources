# parse_command_line<wchar_t>(wchar_t *,wchar_t * *,wchar_t *,uint *,uint *)

- ea: `0x40e5d6`
- end: `0x40e76a`
- name: `??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z`
- size: `404`
- prototype: `_DWORD *__cdecl(__int16 *, __int16 **, __int16 *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x40e4a7`

## callees

- `0x40e5d6`

## pseudocode

```c
_DWORD *__cdecl parse_command_line<wchar_t>(__int16 *a1, __int16 **a2, __int16 *a3, _DWORD *a4, _DWORD *a5)
{
  __int16 *v6; // edx
  __int16 **v7; // esi
  bool v8; // bl
  __int16 v9; // ax
  bool v10; // zf
  __int16 v11; // ax
  __int16 v12; // di
  unsigned int v13; // ebx
  __int16 v14; // di
  bool v15; // al
  __int16 v16; // ax
  _DWORD *result; // eax
  int v18; // [esp+8h] [ebp-10h]
  bool v19; // [esp+17h] [ebp-1h]

  v6 = a3;
  v7 = a2;
  *a5 = 0;
  *a4 = 1;
  if ( a2 )
  {
    *a2 = a3;
    v7 = ++a2;
  }
  v8 = 0;
LABEL_4:
  v9 = 34;
  do
  {
    if ( *a1 == 34 )
    {
      v8 = !v8;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( v6 )
        *v6++ = *a1;
      v9 = *a1++;
      if ( !v9 )
      {
        --a1;
        goto LABEL_16;
      }
    }
    if ( v8 )
      goto LABEL_4;
    if ( v9 == 32 )
      break;
    v10 = v9 == 9;
    v9 = 34;
  }
  while ( !v10 );
  if ( v6 )
    *(v6 - 1) = 0;
LABEL_16:
  v19 = 0;
LABEL_17:
  v11 = *a1;
  v12 = *a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      if ( v11 != 32 )
      {
        v12 = v11;
        if ( v11 != 9 )
          break;
      }
      v11 = *++a1;
    }
  }
  if ( v12 )
  {
    if ( v7 )
    {
      *v7 = v6;
      a2 = v7 + 1;
    }
    ++*a4;
    while ( 1 )
    {
      v13 = 0;
      v18 = 1;
      v14 = *a1;
      if ( *a1 == 92 )
      {
        do
        {
          ++a1;
          ++v13;
        }
        while ( *a1 == 92 );
        v14 = *a1;
      }
      if ( v14 == 34 )
        break;
LABEL_36:
      while ( v13 )
      {
        --v13;
        if ( v6 )
          *v6++ = 92;
        ++*a5;
      }
      v16 = *a1;
      if ( !*a1 || !v19 && (v16 == 32 || v16 == 9) )
      {
        v7 = a2;
        if ( v6 )
          *v6++ = 0;
        ++*a5;
        goto LABEL_17;
      }
      if ( v18 )
      {
        if ( v6 )
          *v6++ = v16;
        ++*a5;
      }
      ++a1;
    }
    if ( (v13 & 1) == 0 )
    {
      v15 = v19;
      if ( v19 )
      {
        if ( a1[1] == 34 )
        {
          ++a1;
          goto LABEL_35;
        }
        v15 = v19;
      }
      v18 = 0;
      v19 = !v15;
    }
LABEL_35:
    v13 >>= 1;
    goto LABEL_36;
  }
  if ( v7 )
    *v7 = 0;
  result = a4;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x40e5d6  mov     edi, edi
0x40e5d8  push    ebp
0x40e5d9  mov     ebp, esp
0x40e5db  mov     eax, [ebp+arg_C]
0x40e5de  sub     esp, 10h
0x40e5e1  mov     ecx, [ebp+arg_0]
0x40e5e4  mov     edx, [ebp+arg_8]
0x40e5e7  push    esi
0x40e5e8  mov     esi, [ebp+arg_4]
0x40e5eb  push    edi
0x40e5ec  mov     edi, [ebp+arg_10]
0x40e5ef  and     dword ptr [edi], 0
0x40e5f2  mov     dword ptr [eax], 1
0x40e5f8  test    esi, esi
0x40e5fa  jz      short loc_40E604
0x40e5fc  mov     [esi], edx
0x40e5fe  add     esi, 4
0x40e601  mov     [ebp+arg_4], esi
0x40e604  push    ebx
0x40e605  xor     bl, bl
0x40e607  mov     [ebp+var_8], 20h ; ' '
0x40e60e  mov     [ebp+var_C], 9
0x40e615  push    22h ; '"'
0x40e617  pop     eax
0x40e618  cmp     [ecx], ax
0x40e61b  jnz     short loc_40E627
0x40e61d  test    bl, bl
0x40e61f  setz    bl
0x40e622  add     ecx, 2
0x40e625  jmp     short loc_40E641
0x40e627  inc     dword ptr [edi]
0x40e629  test    edx, edx
0x40e62b  jz      short loc_40E636
0x40e62d  mov     ax, [ecx]
0x40e630  mov     [edx], ax
0x40e633  add     edx, 2
0x40e636  movzx   eax, word ptr [ecx]
0x40e639  add     ecx, 2
0x40e63c  test    ax, ax
0x40e63f  jz      short loc_40E660
0x40e641  test    bl, bl
0x40e643  jnz     short loc_40E615
0x40e645  cmp     ax, word ptr [ebp+var_8]
0x40e649  jz      short loc_40E654
0x40e64b  cmp     ax, word ptr [ebp+var_C]
0x40e64f  push    22h ; '"'
0x40e651  pop     eax
0x40e652  jnz     short loc_40E618
0x40e654  test    edx, edx
0x40e656  jz      short loc_40E663
0x40e658  xor     eax, eax
0x40e65a  mov     [edx-2], ax
0x40e65e  jmp     short loc_40E663
0x40e660  sub     ecx, 2
0x40e663  mov     [ebp+var_1], 0
0x40e667  movzx   eax, word ptr [ecx]
0x40e66a  mov     edi, eax
0x40e66c  test    ax, ax
0x40e66f  jz      short loc_40E68A
0x40e671  mov     ebx, [ebp+var_8]
0x40e674  cmp     ax, bx
0x40e677  jz      short loc_40E682
0x40e679  movzx   edi, ax
0x40e67c  cmp     ax, word ptr [ebp+var_C]
0x40e680  jnz     short loc_40E68A
0x40e682  add     ecx, 2
0x40e685  movzx   eax, word ptr [ecx]
0x40e688  jmp     short loc_40E674
0x40e68a  test    di, di
0x40e68d  jz      loc_40E759
0x40e693  test    esi, esi
0x40e695  jz      short loc_40E69F
0x40e697  mov     [esi], edx
0x40e699  add     esi, 4
0x40e69c  mov     [ebp+arg_4], esi
0x40e69f  mov     eax, [ebp+arg_C]
0x40e6a2  push    5Ch ; '\'
0x40e6a4  pop     esi
0x40e6a5  inc     dword ptr [eax]
0x40e6a7  movzx   eax, word ptr [ecx]
0x40e6aa  xor     ebx, ebx
0x40e6ac  mov     [ebp+var_10], 1
0x40e6b3  mov     edi, eax
0x40e6b5  cmp     ax, si
0x40e6b8  jnz     short loc_40E6C8
0x40e6ba  add     ecx, 2
0x40e6bd  inc     ebx
0x40e6be  movzx   eax, word ptr [ecx]
0x40e6c1  cmp     ax, si
0x40e6c4  jz      short loc_40E6BA
0x40e6c6  mov     edi, eax
0x40e6c8  push    22h ; '"'
0x40e6ca  pop     eax
0x40e6cb  cmp     di, ax
0x40e6ce  jnz     short loc_40E6F9
0x40e6d0  test    bl, 1
0x40e6d3  jnz     short loc_40E6F7
0x40e6d5  mov     al, [ebp+var_1]
0x40e6d8  test    al, al
0x40e6da  jz      short loc_40E6ED
0x40e6dc  push    22h ; '"'
0x40e6de  pop     edi
0x40e6df  cmp     [ecx+2], di
0x40e6e3  jnz     short loc_40E6EA
0x40e6e5  add     ecx, 2
0x40e6e8  jmp     short loc_40E6F7
0x40e6ea  mov     al, [ebp+var_1]
0x40e6ed  and     [ebp+var_10], 0
0x40e6f1  test    al, al
0x40e6f3  setz    [ebp+var_1]
0x40e6f7  shr     ebx, 1
0x40e6f9  mov     edi, [ebp+arg_10]
0x40e6fc  test    ebx, ebx
0x40e6fe  jz      short loc_40E70F
0x40e700  dec     ebx
0x40e701  test    edx, edx
0x40e703  jz      short loc_40E70B
0x40e705  mov     [edx], si
0x40e708  add     edx, 2
0x40e70b  inc     dword ptr [edi]
0x40e70d  jmp     short loc_40E6FC
0x40e70f  movzx   eax, word ptr [ecx]
0x40e712  test    ax, ax
0x40e715  jz      short loc_40E743
0x40e717  cmp     [ebp+var_1], 0
0x40e71b  jnz     short loc_40E729
0x40e71d  cmp     ax, word ptr [ebp+var_8]
0x40e721  jz      short loc_40E743
0x40e723  cmp     ax, word ptr [ebp+var_C]
0x40e727  jz      short loc_40E743
0x40e729  cmp     [ebp+var_10], 0
0x40e72d  jz      short loc_40E73B
0x40e72f  test    edx, edx
0x40e731  jz      short loc_40E739
0x40e733  mov     [edx], ax
0x40e736  add     edx, 2
0x40e739  inc     dword ptr [edi]
0x40e73b  add     ecx, 2
0x40e73e  jmp     loc_40E6A7
0x40e743  mov     esi, [ebp+arg_4]
0x40e746  test    edx, edx
0x40e748  jz      short loc_40E752
0x40e74a  xor     eax, eax
0x40e74c  mov     [edx], ax
0x40e74f  add     edx, 2
0x40e752  inc     dword ptr [edi]
0x40e754  jmp     loc_40E667
0x40e759  pop     ebx
0x40e75a  test    esi, esi
0x40e75c  jz      short loc_40E761
0x40e75e  and     dword ptr [esi], 0
0x40e761  mov     eax, [ebp+arg_C]
0x40e764  pop     edi
0x40e765  pop     esi
0x40e766  inc     dword ptr [eax]
0x40e768  leave
0x40e769  retn
```
