# parse_command_line<wchar_t>(wchar_t *,wchar_t * *,wchar_t *,uint *,uint *)

- ea: `0x410a5e`
- end: `0x410bf2`
- name: `??$parse_command_line@_W@@YAXPA_WPAPA_W0PAI2@Z`
- size: `404`
- prototype: `_DWORD *__cdecl(__int16 *, __int16 **, __int16 *, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x41092f`

## callees

- `0x410a5e`

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
0x410a5e  mov     edi, edi
0x410a60  push    ebp
0x410a61  mov     ebp, esp
0x410a63  mov     eax, [ebp+arg_C]
0x410a66  sub     esp, 10h
0x410a69  mov     ecx, [ebp+arg_0]
0x410a6c  mov     edx, [ebp+arg_8]
0x410a6f  push    esi
0x410a70  mov     esi, [ebp+arg_4]
0x410a73  push    edi
0x410a74  mov     edi, [ebp+arg_10]
0x410a77  and     dword ptr [edi], 0
0x410a7a  mov     dword ptr [eax], 1
0x410a80  test    esi, esi
0x410a82  jz      short loc_410A8C
0x410a84  mov     [esi], edx
0x410a86  add     esi, 4
0x410a89  mov     [ebp+arg_4], esi
0x410a8c  push    ebx
0x410a8d  xor     bl, bl
0x410a8f  mov     [ebp+var_8], 20h ; ' '
0x410a96  mov     [ebp+var_C], 9
0x410a9d  push    22h ; '"'
0x410a9f  pop     eax
0x410aa0  cmp     [ecx], ax
0x410aa3  jnz     short loc_410AAF
0x410aa5  test    bl, bl
0x410aa7  setz    bl
0x410aaa  add     ecx, 2
0x410aad  jmp     short loc_410AC9
0x410aaf  inc     dword ptr [edi]
0x410ab1  test    edx, edx
0x410ab3  jz      short loc_410ABE
0x410ab5  mov     ax, [ecx]
0x410ab8  mov     [edx], ax
0x410abb  add     edx, 2
0x410abe  movzx   eax, word ptr [ecx]
0x410ac1  add     ecx, 2
0x410ac4  test    ax, ax
0x410ac7  jz      short loc_410AE8
0x410ac9  test    bl, bl
0x410acb  jnz     short loc_410A9D
0x410acd  cmp     ax, word ptr [ebp+var_8]
0x410ad1  jz      short loc_410ADC
0x410ad3  cmp     ax, word ptr [ebp+var_C]
0x410ad7  push    22h ; '"'
0x410ad9  pop     eax
0x410ada  jnz     short loc_410AA0
0x410adc  test    edx, edx
0x410ade  jz      short loc_410AEB
0x410ae0  xor     eax, eax
0x410ae2  mov     [edx-2], ax
0x410ae6  jmp     short loc_410AEB
0x410ae8  sub     ecx, 2
0x410aeb  mov     [ebp+var_1], 0
0x410aef  movzx   eax, word ptr [ecx]
0x410af2  mov     edi, eax
0x410af4  test    ax, ax
0x410af7  jz      short loc_410B12
0x410af9  mov     ebx, [ebp+var_8]
0x410afc  cmp     ax, bx
0x410aff  jz      short loc_410B0A
0x410b01  movzx   edi, ax
0x410b04  cmp     ax, word ptr [ebp+var_C]
0x410b08  jnz     short loc_410B12
0x410b0a  add     ecx, 2
0x410b0d  movzx   eax, word ptr [ecx]
0x410b10  jmp     short loc_410AFC
0x410b12  test    di, di
0x410b15  jz      loc_410BE1
0x410b1b  test    esi, esi
0x410b1d  jz      short loc_410B27
0x410b1f  mov     [esi], edx
0x410b21  add     esi, 4
0x410b24  mov     [ebp+arg_4], esi
0x410b27  mov     eax, [ebp+arg_C]
0x410b2a  push    5Ch ; '\'
0x410b2c  pop     esi
0x410b2d  inc     dword ptr [eax]
0x410b2f  movzx   eax, word ptr [ecx]
0x410b32  xor     ebx, ebx
0x410b34  mov     [ebp+var_10], 1
0x410b3b  mov     edi, eax
0x410b3d  cmp     ax, si
0x410b40  jnz     short loc_410B50
0x410b42  add     ecx, 2
0x410b45  inc     ebx
0x410b46  movzx   eax, word ptr [ecx]
0x410b49  cmp     ax, si
0x410b4c  jz      short loc_410B42
0x410b4e  mov     edi, eax
0x410b50  push    22h ; '"'
0x410b52  pop     eax
0x410b53  cmp     di, ax
0x410b56  jnz     short loc_410B81
0x410b58  test    bl, 1
0x410b5b  jnz     short loc_410B7F
0x410b5d  mov     al, [ebp+var_1]
0x410b60  test    al, al
0x410b62  jz      short loc_410B75
0x410b64  push    22h ; '"'
0x410b66  pop     edi
0x410b67  cmp     [ecx+2], di
0x410b6b  jnz     short loc_410B72
0x410b6d  add     ecx, 2
0x410b70  jmp     short loc_410B7F
0x410b72  mov     al, [ebp+var_1]
0x410b75  and     [ebp+var_10], 0
0x410b79  test    al, al
0x410b7b  setz    [ebp+var_1]
0x410b7f  shr     ebx, 1
0x410b81  mov     edi, [ebp+arg_10]
0x410b84  test    ebx, ebx
0x410b86  jz      short loc_410B97
0x410b88  dec     ebx
0x410b89  test    edx, edx
0x410b8b  jz      short loc_410B93
0x410b8d  mov     [edx], si
0x410b90  add     edx, 2
0x410b93  inc     dword ptr [edi]
0x410b95  jmp     short loc_410B84
0x410b97  movzx   eax, word ptr [ecx]
0x410b9a  test    ax, ax
0x410b9d  jz      short loc_410BCB
0x410b9f  cmp     [ebp+var_1], 0
0x410ba3  jnz     short loc_410BB1
0x410ba5  cmp     ax, word ptr [ebp+var_8]
0x410ba9  jz      short loc_410BCB
0x410bab  cmp     ax, word ptr [ebp+var_C]
0x410baf  jz      short loc_410BCB
0x410bb1  cmp     [ebp+var_10], 0
0x410bb5  jz      short loc_410BC3
0x410bb7  test    edx, edx
0x410bb9  jz      short loc_410BC1
0x410bbb  mov     [edx], ax
0x410bbe  add     edx, 2
0x410bc1  inc     dword ptr [edi]
0x410bc3  add     ecx, 2
0x410bc6  jmp     loc_410B2F
0x410bcb  mov     esi, [ebp+arg_4]
0x410bce  test    edx, edx
0x410bd0  jz      short loc_410BDA
0x410bd2  xor     eax, eax
0x410bd4  mov     [edx], ax
0x410bd7  add     edx, 2
0x410bda  inc     dword ptr [edi]
0x410bdc  jmp     loc_410AEF
0x410be1  pop     ebx
0x410be2  test    esi, esi
0x410be4  jz      short loc_410BE9
0x410be6  and     dword ptr [esi], 0
0x410be9  mov     eax, [ebp+arg_C]
0x410bec  pop     edi
0x410bed  pop     esi
0x410bee  inc     dword ptr [eax]
0x410bf0  leave
0x410bf1  retn
```
