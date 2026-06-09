# common_expand_argv_wildcards<char>(char * * const,char * * * const)

- ea: `0x40ef46`
- end: `0x40f134`
- name: `??$common_expand_argv_wildcards@D@@YAHQAPADQAPAPAD@Z`
- size: `494`
- prototype: `int __cdecl(const char **, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x40f5b7`

## callees

- `0x40b581`
- `0x40ec26`
- `0x40ec36`
- `0x40ece3`
- `0x40ed53`
- `0x40ef46`
- `0x40f135`
- `0x40f1e6`
- `0x413841`
- `0x413850`

## pseudocode

```c
int __cdecl common_expand_argv_wildcards<char>(const char **a1, _DWORD *a2)
{
  int v2; // esi
  unsigned __int8 **v3; // esi
  int v4; // ebx
  void **v5; // edi
  const char *v6; // eax
  unsigned int v7; // ecx
  unsigned __int8 *v8; // eax
  unsigned __int8 *v9; // ecx
  int v10; // edx
  unsigned int v11; // esi
  const char **v12; // eax
  int i; // edx
  const char *v14; // ecx
  int buffer_for_argv; // eax
  int v16; // esi
  char *v17; // ecx
  char **v18; // eax
  int v19; // eax
  char *v20; // ecx
  unsigned int v21; // eax
  unsigned int v22; // esi
  void *Block; // [esp+4h] [ebp-28h] BYREF
  char **v25; // [esp+8h] [ebp-24h]
  int v26; // [esp+Ch] [ebp-20h]
  void **v27; // [esp+10h] [ebp-1Ch]
  char *v28; // [esp+14h] [ebp-18h]
  char *Source; // [esp+18h] [ebp-14h]
  const char *v30; // [esp+1Ch] [ebp-10h]
  char *v31; // [esp+20h] [ebp-Ch]
  int v32; // [esp+24h] [ebp-8h]
  char Control[4]; // [esp+28h] [ebp-4h] BYREF

  if ( a2 )
  {
    v3 = (unsigned __int8 **)a1;
    v4 = 0;
    *a2 = 0;
    v5 = 0;
    v6 = *a1;
    v7 = 0;
    Block = 0;
    v25 = 0;
    v26 = 0;
    if ( v6 )
    {
      while ( 1 )
      {
        strcpy(Control, "*?");
        v8 = (unsigned __int8 *)strpbrk(v6, Control);
        v9 = *v3;
        if ( v8 )
        {
          v32 = expand_argument_wildcards<char>(v9, v8, (int)&Block);
          v2 = v32;
        }
        else
        {
          v2 = copy_and_add_argument_to_buffer<char>((char *)v9, 0, 0, (int)&Block);
          v32 = v2;
        }
        if ( v2 )
          break;
        v3 = (unsigned __int8 **)(a1 + 1);
        a1 = (const char **)v3;
        v6 = (const char *)*v3;
        if ( !*v3 )
        {
          v5 = (void **)Block;
          v7 = (unsigned int)v25;
          goto LABEL_10;
        }
      }
      v5 = (void **)Block;
    }
    else
    {
LABEL_10:
      *(_DWORD *)Control = 0;
      v32 = (int)v5;
      v10 = ((int)(v7 - (_DWORD)v5) >> 2) + 1;
      v31 = (char *)v10;
      v11 = v7 >= (unsigned int)v5 ? (v7 - (unsigned int)v5 + 3) >> 2 : 0;
      if ( v11 )
      {
        v12 = (const char **)v5;
        for ( i = 0; i != v11; ++i )
        {
          v14 = *v12;
          v30 = *v12 + 1;
          v4 += &v14[strlen(v14) + 1] - v30 + 1;
          v12 = (const char **)(v32 + 4);
          v32 += 4;
        }
        v10 = (int)v31;
        *(_DWORD *)Control = v4;
        v4 = 0;
      }
      buffer_for_argv = __acrt_allocate_buffer_for_argv(v10, *(_DWORD *)Control, 1);
      v16 = buffer_for_argv;
      if ( buffer_for_argv )
      {
        v32 = (int)v5;
        v17 = (char *)(buffer_for_argv + 4 * (_DWORD)v31);
        v28 = v17;
        v18 = (char **)v5;
        v31 = (char *)(v16 + 4 * (_DWORD)v31);
        if ( v5 != (void **)v25 )
        {
          v27 = (void **)(v16 - (_DWORD)v5);
          do
          {
            Source = *v18;
            v30 = (const char *)(strlen(Source) + 1);
            if ( strncpy_s(v17, *(_DWORD *)Control + v28 - v17, Source, (rsize_t)v30) )
              _invoke_watson(0, 0, 0, 0, 0);
            v19 = v32;
            v20 = v31;
            *(void **)((char *)v27 + v32) = v31;
            v18 = (char **)(v19 + 4);
            v17 = &v20[(_DWORD)v30];
            v31 = v17;
            v32 = (int)v18;
          }
          while ( v18 != v25 );
        }
        v32 = 0;
        *a2 = v16;
        v2 = 0;
      }
      else
      {
        v2 = -1;
        v32 = -1;
      }
      _free_base(0);
    }
    v27 = v5;
    v21 = (unsigned int)((char *)v25 - (char *)v5 + 3) >> 2;
    v28 = v25 >= (char **)v5 ? (char *)v21 : 0;
    if ( v28 )
    {
      v22 = v25 >= (char **)v5 ? v21 : 0;
      do
      {
        _free_base(*v5);
        ++v4;
        ++v5;
      }
      while ( v4 != v22 );
      v5 = (void **)Block;
      v2 = v32;
    }
    _free_base(v5);
  }
  else
  {
    v2 = 22;
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  return v2;
}

```

## disassembly

```asm
0x40ef46  mov     edi, edi
0x40ef48  push    ebp
0x40ef49  mov     ebp, esp
0x40ef4b  mov     eax, [ebp+arg_4]
0x40ef4e  sub     esp, 28h
0x40ef51  push    esi
0x40ef52  test    eax, eax
0x40ef54  jnz     short loc_40EF6A
0x40ef56  call    __errno
0x40ef5b  push    16h
0x40ef5d  pop     esi
0x40ef5e  mov     [eax], esi
0x40ef60  call    __invalid_parameter_noinfo
0x40ef65  jmp     loc_40F125
0x40ef6a  mov     esi, [ebp+arg_0]
0x40ef6d  push    ebx
0x40ef6e  xor     ebx, ebx
0x40ef70  push    edi
0x40ef71  mov     [eax], ebx
0x40ef73  mov     edi, ebx
0x40ef75  mov     eax, [esi]
0x40ef77  mov     ecx, ebx
0x40ef79  mov     [ebp+Block], edi
0x40ef7c  mov     [ebp+var_24], ecx
0x40ef7f  mov     [ebp+var_20], ebx
0x40ef82  test    eax, eax
0x40ef84  jz      short loc_40EFE7
0x40ef86  lea     ecx, [ebp+Control]
0x40ef89  mov     word ptr [ebp+Control], 3F2Ah
0x40ef8f  push    ecx; Control
0x40ef90  push    eax; Str
0x40ef91  mov     [ebp+Control+2], bl
0x40ef94  call    _strpbrk
0x40ef99  pop     ecx
0x40ef9a  pop     ecx
0x40ef9b  mov     ecx, [esi]
0x40ef9d  test    eax, eax
0x40ef9f  jnz     short loc_40EFB7
0x40efa1  lea     eax, [ebp+Block]
0x40efa4  push    eax; int
0x40efa5  push    ebx; MaxCount
0x40efa6  push    ebx; Source
0x40efa7  push    ecx; char *
0x40efa8  call    ??$copy_and_add_argument_to_buffer@D@@YAHQBD0IAAV?$argument_list@D@?A0x5f5c8891@@@Z
0x40efad  mov     esi, eax
0x40efaf  add     esp, 10h
0x40efb2  mov     [ebp+var_8], esi
0x40efb5  jmp     short loc_40EFCA
0x40efb7  lea     edx, [ebp+Block]
0x40efba  push    edx; int
0x40efbb  push    eax; Pos
0x40efbc  push    ecx; Start
0x40efbd  call    ??$expand_argument_wildcards@D@@YAHQAD0AAV?$argument_list@D@?A0x5f5c8891@@@Z
0x40efc2  add     esp, 0Ch
0x40efc5  mov     [ebp+var_8], eax
0x40efc8  mov     esi, eax
0x40efca  test    esi, esi
0x40efcc  jnz     loc_40F05A
0x40efd2  mov     esi, [ebp+arg_0]
0x40efd5  add     esi, 4
0x40efd8  mov     [ebp+arg_0], esi
0x40efdb  mov     eax, [esi]
0x40efdd  test    eax, eax
0x40efdf  jnz     short loc_40EF86
0x40efe1  mov     edi, [ebp+Block]
0x40efe4  mov     ecx, [ebp+var_24]
0x40efe7  mov     eax, ecx
0x40efe9  mov     dword ptr [ebp+Control], ebx
0x40efec  sub     eax, edi
0x40efee  mov     esi, edi
0x40eff0  mov     edx, eax
0x40eff2  mov     [ebp+var_8], esi
0x40eff5  sar     edx, 2
0x40eff8  add     eax, 3
0x40effb  inc     edx
0x40effc  shr     eax, 2
0x40efff  cmp     ecx, esi
0x40f001  mov     [ebp+var_C], edx
0x40f004  sbb     esi, esi
0x40f006  not     esi
0x40f008  and     esi, eax
0x40f00a  jz      short loc_40F03B
0x40f00c  mov     eax, edi
0x40f00e  mov     edx, ebx
0x40f010  mov     ecx, [eax]
0x40f012  lea     eax, [ecx+1]
0x40f015  mov     [ebp+var_10], eax
0x40f018  mov     al, [ecx]
0x40f01a  inc     ecx
0x40f01b  test    al, al
0x40f01d  jnz     short loc_40F018
0x40f01f  sub     ecx, [ebp+var_10]
0x40f022  inc     ebx
0x40f023  mov     eax, [ebp+var_8]
0x40f026  add     ebx, ecx
0x40f028  add     eax, 4
0x40f02b  inc     edx
0x40f02c  mov     [ebp+var_8], eax
0x40f02f  cmp     edx, esi
0x40f031  jnz     short loc_40F010
0x40f033  mov     edx, [ebp+var_C]
0x40f036  mov     dword ptr [ebp+Control], ebx
0x40f039  xor     ebx, ebx
0x40f03b  push    1
0x40f03d  push    dword ptr [ebp+Control]
0x40f040  push    edx
0x40f041  call    ___acrt_allocate_buffer_for_argv
0x40f046  mov     esi, eax
0x40f048  add     esp, 0Ch
0x40f04b  test    esi, esi
0x40f04d  jnz     short loc_40F062
0x40f04f  or      esi, 0FFFFFFFFh
0x40f052  mov     [ebp+var_8], esi
0x40f055  jmp     loc_40F0DF
0x40f05a  mov     edi, [ebp+Block]
0x40f05d  jmp     loc_40F0E6
0x40f062  mov     eax, [ebp+var_C]
0x40f065  mov     [ebp+var_8], edi
0x40f068  lea     eax, [esi+eax*4]
0x40f06b  mov     ecx, eax
0x40f06d  mov     [ebp+var_18], eax
0x40f070  mov     eax, edi
0x40f072  mov     [ebp+var_C], ecx
0x40f075  cmp     eax, [ebp+var_24]
0x40f078  jz      short loc_40F0D5
0x40f07a  mov     edx, esi
0x40f07c  sub     edx, edi
0x40f07e  mov     [ebp+var_1C], edx
0x40f081  mov     eax, [eax]
0x40f083  mov     edx, eax
0x40f085  mov     [ebp+Source], eax
0x40f088  lea     eax, [edx+1]
0x40f08b  mov     [ebp+var_10], eax
0x40f08e  mov     al, [edx]
0x40f090  inc     edx
0x40f091  test    al, al
0x40f093  jnz     short loc_40F08E
0x40f095  sub     edx, [ebp+var_10]
0x40f098  lea     eax, [edx+1]
0x40f09b  push    eax; MaxCount
0x40f09c  push    [ebp+Source]; Source
0x40f09f  mov     [ebp+var_10], eax
0x40f0a2  mov     eax, [ebp+var_18]
0x40f0a5  sub     eax, ecx
0x40f0a7  add     eax, dword ptr [ebp+Control]
0x40f0aa  push    eax; SizeInBytes
0x40f0ab  push    ecx; Destination
0x40f0ac  call    _strncpy_s
0x40f0b1  add     esp, 10h
0x40f0b4  test    eax, eax
0x40f0b6  jnz     short loc_40F12A
0x40f0b8  mov     eax, [ebp+var_8]
0x40f0bb  mov     edx, [ebp+var_1C]
0x40f0be  mov     ecx, [ebp+var_C]
0x40f0c1  mov     [edx+eax], ecx
0x40f0c4  add     eax, 4
0x40f0c7  add     ecx, [ebp+var_10]
0x40f0ca  mov     [ebp+var_C], ecx
0x40f0cd  mov     [ebp+var_8], eax
0x40f0d0  cmp     eax, [ebp+var_24]
0x40f0d3  jnz     short loc_40F081
0x40f0d5  mov     eax, [ebp+arg_4]
0x40f0d8  mov     [ebp+var_8], ebx
0x40f0db  mov     [eax], esi
0x40f0dd  mov     esi, ebx
0x40f0df  push    ebx; Block
0x40f0e0  call    __free_base
0x40f0e5  pop     ecx
0x40f0e6  mov     eax, [ebp+var_24]
0x40f0e9  mov     edx, edi
0x40f0eb  sub     eax, edx
0x40f0ed  mov     [ebp+var_1C], edx
0x40f0f0  add     eax, 3
0x40f0f3  shr     eax, 2
0x40f0f6  cmp     [ebp+var_24], edx
0x40f0f9  sbb     ecx, ecx
0x40f0fb  not     ecx
0x40f0fd  and     ecx, eax
0x40f0ff  mov     [ebp+var_18], ecx
0x40f102  jz      short loc_40F11C
0x40f104  mov     esi, ecx
0x40f106  push    dword ptr [edi]; Block
0x40f108  call    __free_base
0x40f10d  inc     ebx
0x40f10e  lea     edi, [edi+4]
0x40f111  pop     ecx
0x40f112  cmp     ebx, esi
0x40f114  jnz     short loc_40F106
0x40f116  mov     edi, [ebp+Block]
0x40f119  mov     esi, [ebp+var_8]
0x40f11c  push    edi; Block
0x40f11d  call    __free_base
0x40f122  pop     ecx
0x40f123  pop     edi
0x40f124  pop     ebx
0x40f125  mov     eax, esi
0x40f127  pop     esi
0x40f128  leave
0x40f129  retn
0x40f12a  push    ebx; Reserved
0x40f12b  push    ebx; LineNo
0x40f12c  push    ebx; FileName
0x40f12d  push    ebx; FunctionName
0x40f12e  push    ebx; Expression
0x40f12f  call    __invoke_watson
```
