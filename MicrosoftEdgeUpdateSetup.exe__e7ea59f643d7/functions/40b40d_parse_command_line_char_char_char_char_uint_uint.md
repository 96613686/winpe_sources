# parse_command_line<char>(char *,char * *,char *,uint *,uint *)

- ea: `0x40b40d`
- end: `0x40b581`
- name: `??$parse_command_line@D@@YAXPADPAPAD0PAI2@Z`
- size: `372`
- prototype: `_DWORD *__cdecl(char *, char **, char *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40b2d7`

## callees

- `0x40b40d`
- `0x40ffa6`

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
0x40b40d  mov     edi, edi
0x40b40f  push    ebp
0x40b410  mov     ebp, esp
0x40b412  push    ecx
0x40b413  mov     eax, [ebp+arg_C]
0x40b416  push    ebx
0x40b417  mov     ebx, [ebp+arg_10]
0x40b41a  push    esi
0x40b41b  mov     esi, [ebp+arg_8]
0x40b41e  push    edi
0x40b41f  and     dword ptr [ebx], 0
0x40b422  mov     edi, [ebp+arg_0]
0x40b425  mov     dword ptr [eax], 1
0x40b42b  mov     eax, [ebp+arg_4]
0x40b42e  test    eax, eax
0x40b430  jz      short loc_40B43A
0x40b432  mov     [eax], esi
0x40b434  add     eax, 4
0x40b437  mov     [ebp+arg_4], eax
0x40b43a  xor     cl, cl
0x40b43c  mov     [ebp+var_1], cl
0x40b43f  cmp     byte ptr [edi], 22h ; '"'
0x40b442  jnz     short loc_40B451
0x40b444  test    cl, cl
0x40b446  mov     al, 22h ; '"'
0x40b448  setz    cl
0x40b44b  inc     edi
0x40b44c  mov     [ebp+var_1], cl
0x40b44f  jmp     short loc_40B486
0x40b451  inc     dword ptr [ebx]
0x40b453  test    esi, esi
0x40b455  jz      short loc_40B45C
0x40b457  mov     al, [edi]
0x40b459  mov     [esi], al
0x40b45b  inc     esi
0x40b45c  mov     al, [edi]
0x40b45e  inc     edi
0x40b45f  mov     [ebp+var_2], al
0x40b462  movsx   eax, al
0x40b465  push    eax; Ch
0x40b466  call    __ismbblead
0x40b46b  pop     ecx
0x40b46c  test    eax, eax
0x40b46e  jz      short loc_40B47C
0x40b470  inc     dword ptr [ebx]
0x40b472  test    esi, esi
0x40b474  jz      short loc_40B47B
0x40b476  mov     al, [edi]
0x40b478  mov     [esi], al
0x40b47a  inc     esi
0x40b47b  inc     edi
0x40b47c  mov     al, [ebp+var_2]
0x40b47f  test    al, al
0x40b481  jz      short loc_40B49C
0x40b483  mov     cl, [ebp+var_1]
0x40b486  test    cl, cl
0x40b488  jnz     short loc_40B43F
0x40b48a  cmp     al, 20h ; ' '
0x40b48c  jz      short loc_40B492
0x40b48e  cmp     al, 9
0x40b490  jnz     short loc_40B43F
0x40b492  test    esi, esi
0x40b494  jz      short loc_40B49D
0x40b496  mov     byte ptr [esi-1], 0
0x40b49a  jmp     short loc_40B49D
0x40b49c  dec     edi
0x40b49d  mov     [ebp+var_1], 0
0x40b4a1  mov     al, [edi]
0x40b4a3  test    al, al
0x40b4a5  jz      loc_40B56D
0x40b4ab  cmp     al, 20h ; ' '
0x40b4ad  jz      short loc_40B4B3
0x40b4af  cmp     al, 9
0x40b4b1  jnz     short loc_40B4B8
0x40b4b3  inc     edi
0x40b4b4  mov     al, [edi]
0x40b4b6  jmp     short loc_40B4AB
0x40b4b8  test    al, al
0x40b4ba  jz      loc_40B56D
0x40b4c0  mov     ecx, [ebp+arg_4]
0x40b4c3  test    ecx, ecx
0x40b4c5  jz      short loc_40B4CF
0x40b4c7  mov     [ecx], esi
0x40b4c9  add     ecx, 4
0x40b4cc  mov     [ebp+arg_4], ecx
0x40b4cf  mov     eax, [ebp+arg_C]
0x40b4d2  inc     dword ptr [eax]
0x40b4d4  xor     edx, edx
0x40b4d6  inc     edx
0x40b4d7  xor     eax, eax
0x40b4d9  jmp     short loc_40B4DD
0x40b4db  inc     edi
0x40b4dc  inc     eax
0x40b4dd  mov     cl, [edi]
0x40b4df  cmp     cl, 5Ch ; '\'
0x40b4e2  jz      short loc_40B4DB
0x40b4e4  cmp     cl, 22h ; '"'
0x40b4e7  jnz     short loc_40B517
0x40b4e9  test    al, 1
0x40b4eb  jnz     short loc_40B508
0x40b4ed  mov     cl, [ebp+var_1]
0x40b4f0  test    cl, cl
0x40b4f2  jz      short loc_40B500
0x40b4f4  cmp     byte ptr [edi+1], 22h ; '"'
0x40b4f8  jnz     short loc_40B4FD
0x40b4fa  inc     edi
0x40b4fb  jmp     short loc_40B508
0x40b4fd  mov     cl, [ebp+var_1]
0x40b500  xor     edx, edx
0x40b502  test    cl, cl
0x40b504  setz    [ebp+var_1]
0x40b508  shr     eax, 1
0x40b50a  jmp     short loc_40B517
0x40b50c  dec     eax
0x40b50d  test    esi, esi
0x40b50f  jz      short loc_40B515
0x40b511  mov     byte ptr [esi], 5Ch ; '\'
0x40b514  inc     esi
0x40b515  inc     dword ptr [ebx]
0x40b517  test    eax, eax
0x40b519  jnz     short loc_40B50C
0x40b51b  mov     al, [edi]
0x40b51d  test    al, al
0x40b51f  jz      short loc_40B55E
0x40b521  cmp     [ebp+var_1], 0
0x40b525  jnz     short loc_40B52F
0x40b527  cmp     al, 20h ; ' '
0x40b529  jz      short loc_40B55E
0x40b52b  cmp     al, 9
0x40b52d  jz      short loc_40B55E
0x40b52f  test    edx, edx
0x40b531  jz      short loc_40B558
0x40b533  test    esi, esi
0x40b535  jz      short loc_40B53C
0x40b537  mov     [esi], al
0x40b539  inc     esi
0x40b53a  mov     al, [edi]
0x40b53c  movsx   eax, al
0x40b53f  push    eax; Ch
0x40b540  call    __ismbblead
0x40b545  pop     ecx
0x40b546  test    eax, eax
0x40b548  jz      short loc_40B556
0x40b54a  inc     edi
0x40b54b  inc     dword ptr [ebx]
0x40b54d  test    esi, esi
0x40b54f  jz      short loc_40B556
0x40b551  mov     al, [edi]
0x40b553  mov     [esi], al
0x40b555  inc     esi
0x40b556  inc     dword ptr [ebx]
0x40b558  inc     edi
0x40b559  jmp     loc_40B4D4
0x40b55e  test    esi, esi
0x40b560  jz      short loc_40B566
0x40b562  mov     byte ptr [esi], 0
0x40b565  inc     esi
0x40b566  inc     dword ptr [ebx]
0x40b568  jmp     loc_40B4A1
0x40b56d  mov     ecx, [ebp+arg_4]
0x40b570  pop     edi
0x40b571  pop     esi
0x40b572  pop     ebx
0x40b573  test    ecx, ecx
0x40b575  jz      short loc_40B57A
0x40b577  and     dword ptr [ecx], 0
0x40b57a  mov     eax, [ebp+arg_C]
0x40b57d  inc     dword ptr [eax]
0x40b57f  leave
0x40b580  retn
```
