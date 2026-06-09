# parse_command_line<char>(char *,char * *,char *,uint *,uint *)

- ea: `0x10016508`
- end: `0x10016681`
- name: `??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100163d0`

## callees

- `0x10016508`
- `0x10018bb1`

## pseudocode

```c
_DWORD *__cdecl parse_command_line<char>(char *a1, char **a2, char *a3, _DWORD *a4, _DWORD *a5)
{
  char *v5; // esi
  bool v7; // cl
  char v8; // al
  char v9; // al
  char v10; // al
  int v11; // edx
  unsigned int v12; // eax
  bool v13; // cl
  char v14; // al
  _DWORD *result; // eax
  char v16; // [esp+Eh] [ebp-2h]
  bool v17; // [esp+Fh] [ebp-1h]
  bool v18; // [esp+Fh] [ebp-1h]

  v5 = a3;
  *a5 = 0;
  *a4 = 1;
  if ( a2 )
    *a2++ = a3;
  v7 = 0;
  v17 = 0;
  do
  {
    if ( *a1 == 34 )
    {
      v8 = 34;
      v7 = !v7;
      ++a1;
      v17 = v7;
    }
    else
    {
      ++*a5;
      if ( v5 )
        *v5++ = *a1;
      v9 = *a1++;
      v16 = v9;
      if ( _ismbblead(v9) )
      {
        ++*a5;
        if ( v5 )
          *v5++ = *a1;
        ++a1;
      }
      v8 = v16;
      if ( !v16 )
      {
        --a1;
        goto LABEL_20;
      }
      v7 = v17;
    }
  }
  while ( v7 || v8 != 32 && v8 != 9 );
  if ( v5 )
    *(v5 - 1) = 0;
LABEL_20:
  v18 = 0;
LABEL_21:
  v10 = *a1;
  if ( *a1 )
  {
    while ( v10 == 32 || v10 == 9 )
      v10 = *++a1;
    if ( v10 )
    {
      if ( a2 )
        *a2++ = v5;
      ++*a4;
      while ( 1 )
      {
        v11 = 1;
        v12 = 0;
        while ( *a1 == 92 )
        {
          ++a1;
          ++v12;
        }
        if ( *a1 == 34 )
          break;
LABEL_43:
        while ( v12 )
        {
          --v12;
          if ( v5 )
            *v5++ = 92;
          ++*a5;
        }
        v14 = *a1;
        if ( !*a1 || !v18 && (v14 == 32 || v14 == 9) )
        {
          if ( v5 )
            *v5++ = 0;
          ++*a5;
          goto LABEL_21;
        }
        if ( v11 )
        {
          if ( v5 )
          {
            *v5++ = v14;
            v14 = *a1;
          }
          if ( _ismbblead(v14) )
          {
            ++a1;
            ++*a5;
            if ( v5 )
              *v5++ = *a1;
          }
          ++*a5;
        }
        ++a1;
      }
      if ( (v12 & 1) == 0 )
      {
        v13 = v18;
        if ( v18 )
        {
          if ( a1[1] == 34 )
          {
            ++a1;
            goto LABEL_39;
          }
          v13 = v18;
        }
        v11 = 0;
        v18 = !v13;
      }
LABEL_39:
      v12 >>= 1;
      goto LABEL_43;
    }
  }
  if ( a2 )
    *a2 = 0;
  result = a4;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x10016508  mov     edi, edi
0x1001650a  push    ebp
0x1001650b  mov     ebp, esp
0x1001650d  push    ecx
0x1001650e  mov     eax, [ebp+arg_C]
0x10016511  push    ebx
0x10016512  mov     ebx, [ebp+arg_10]
0x10016515  push    esi
0x10016516  mov     esi, [ebp+arg_8]
0x10016519  push    edi
0x1001651a  and     dword ptr [ebx], 0
0x1001651d  mov     edi, [ebp+arg_0]
0x10016520  mov     dword ptr [eax], 1
0x10016526  mov     eax, [ebp+arg_4]
0x10016529  test    eax, eax
0x1001652b  jz      short loc_10016535
0x1001652d  mov     [eax], esi
0x1001652f  add     eax, 4
0x10016532  mov     [ebp+arg_4], eax
0x10016535  xor     cl, cl
0x10016537  mov     [ebp+var_1], cl
0x1001653a  cmp     byte ptr [edi], 22h ; '"'
0x1001653d  jnz     short loc_1001654C
0x1001653f  test    cl, cl
0x10016541  mov     al, 22h ; '"'
0x10016543  setz    cl
0x10016546  inc     edi
0x10016547  mov     [ebp+var_1], cl
0x1001654a  jmp     short loc_10016581
0x1001654c  inc     dword ptr [ebx]
0x1001654e  test    esi, esi
0x10016550  jz      short loc_10016557
0x10016552  mov     al, [edi]
0x10016554  mov     [esi], al
0x10016556  inc     esi
0x10016557  mov     al, [edi]
0x10016559  inc     edi
0x1001655a  mov     [ebp+var_2], al
0x1001655d  movsx   eax, al
0x10016560  push    eax; Ch
0x10016561  call    __ismbblead
0x10016566  pop     ecx
0x10016567  test    eax, eax
0x10016569  jz      short loc_10016577
0x1001656b  inc     dword ptr [ebx]
0x1001656d  test    esi, esi
0x1001656f  jz      short loc_10016576
0x10016571  mov     al, [edi]
0x10016573  mov     [esi], al
0x10016575  inc     esi
0x10016576  inc     edi
0x10016577  mov     al, [ebp+var_2]
0x1001657a  test    al, al
0x1001657c  jz      short loc_10016597
0x1001657e  mov     cl, [ebp+var_1]
0x10016581  test    cl, cl
0x10016583  jnz     short loc_1001653A
0x10016585  cmp     al, 20h ; ' '
0x10016587  jz      short loc_1001658D
0x10016589  cmp     al, 9
0x1001658b  jnz     short loc_1001653A
0x1001658d  test    esi, esi
0x1001658f  jz      short loc_10016598
0x10016591  mov     byte ptr [esi-1], 0
0x10016595  jmp     short loc_10016598
0x10016597  dec     edi
0x10016598  mov     [ebp+var_1], 0
0x1001659c  mov     al, [edi]
0x1001659e  test    al, al
0x100165a0  jz      loc_1001666B
0x100165a6  cmp     al, 20h ; ' '
0x100165a8  jz      short loc_100165AE
0x100165aa  cmp     al, 9
0x100165ac  jnz     short loc_100165B3
0x100165ae  inc     edi
0x100165af  mov     al, [edi]
0x100165b1  jmp     short loc_100165A6
0x100165b3  test    al, al
0x100165b5  jz      loc_1001666B
0x100165bb  mov     ecx, [ebp+arg_4]
0x100165be  test    ecx, ecx
0x100165c0  jz      short loc_100165CA
0x100165c2  mov     [ecx], esi
0x100165c4  add     ecx, 4
0x100165c7  mov     [ebp+arg_4], ecx
0x100165ca  mov     eax, [ebp+arg_C]
0x100165cd  inc     dword ptr [eax]
0x100165cf  xor     edx, edx
0x100165d1  inc     edx
0x100165d2  xor     eax, eax
0x100165d4  jmp     short loc_100165D8
0x100165d6  inc     edi
0x100165d7  inc     eax
0x100165d8  mov     cl, [edi]
0x100165da  cmp     cl, 5Ch ; '\'
0x100165dd  jz      short loc_100165D6
0x100165df  cmp     cl, 22h ; '"'
0x100165e2  jnz     short loc_10016615
0x100165e4  test    al, 1
0x100165e6  jnz     short loc_10016606
0x100165e8  mov     cl, [ebp+var_1]
0x100165eb  test    cl, cl
0x100165ed  jz      short loc_100165FE
0x100165ef  lea     ecx, [edi+1]
0x100165f2  cmp     byte ptr [ecx], 22h ; '"'
0x100165f5  jnz     short loc_100165FB
0x100165f7  mov     edi, ecx
0x100165f9  jmp     short loc_10016606
0x100165fb  mov     cl, [ebp+var_1]
0x100165fe  xor     edx, edx
0x10016600  test    cl, cl
0x10016602  setz    [ebp+var_1]
0x10016606  shr     eax, 1
0x10016608  jmp     short loc_10016615
0x1001660a  dec     eax
0x1001660b  test    esi, esi
0x1001660d  jz      short loc_10016613
0x1001660f  mov     byte ptr [esi], 5Ch ; '\'
0x10016612  inc     esi
0x10016613  inc     dword ptr [ebx]
0x10016615  test    eax, eax
0x10016617  jnz     short loc_1001660A
0x10016619  mov     al, [edi]
0x1001661b  test    al, al
0x1001661d  jz      short loc_1001665C
0x1001661f  cmp     [ebp+var_1], 0
0x10016623  jnz     short loc_1001662D
0x10016625  cmp     al, 20h ; ' '
0x10016627  jz      short loc_1001665C
0x10016629  cmp     al, 9
0x1001662b  jz      short loc_1001665C
0x1001662d  test    edx, edx
0x1001662f  jz      short loc_10016656
0x10016631  test    esi, esi
0x10016633  jz      short loc_1001663A
0x10016635  mov     [esi], al
0x10016637  inc     esi
0x10016638  mov     al, [edi]
0x1001663a  movsx   eax, al
0x1001663d  push    eax; Ch
0x1001663e  call    __ismbblead
0x10016643  pop     ecx
0x10016644  test    eax, eax
0x10016646  jz      short loc_10016654
0x10016648  inc     edi
0x10016649  inc     dword ptr [ebx]
0x1001664b  test    esi, esi
0x1001664d  jz      short loc_10016654
0x1001664f  mov     al, [edi]
0x10016651  mov     [esi], al
0x10016653  inc     esi
0x10016654  inc     dword ptr [ebx]
0x10016656  inc     edi
0x10016657  jmp     loc_100165CF
0x1001665c  test    esi, esi
0x1001665e  jz      short loc_10016664
0x10016660  mov     byte ptr [esi], 0
0x10016663  inc     esi
0x10016664  inc     dword ptr [ebx]
0x10016666  jmp     loc_1001659C
0x1001666b  mov     ecx, [ebp+arg_4]
0x1001666e  pop     edi
0x1001666f  pop     esi
0x10016670  pop     ebx
0x10016671  test    ecx, ecx
0x10016673  jz      short loc_10016678
0x10016675  and     dword ptr [ecx], 0
0x10016678  mov     eax, [ebp+arg_C]
0x1001667b  inc     dword ptr [eax]
0x1001667d  mov     esp, ebp
0x1001667f  pop     ebp
0x10016680  retn
```
