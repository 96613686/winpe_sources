# common_expand_argv_wildcards<char>(char * * const,char * * * const)

- ea: `0x10018eb1`
- end: `0x100190a1`
- name: `??$common_expand_argv_wildcards@D@@YAHQAPADQAPAPAD@Z`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1001952a`

## callees

- `0x10015cbc`
- `0x10015ccc`
- `0x10015d79`
- `0x10016681`
- `0x1001770e`
- `0x10018b4d`
- `0x10018eb1`
- `0x100190a2`
- `0x10019155`
- `0x1001d990`

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
          v2 = sub_100190A2((char *)v9, 0, 0, (int)&Block);
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
0x10018eb1  mov     edi, edi
0x10018eb3  push    ebp
0x10018eb4  mov     ebp, esp
0x10018eb6  mov     eax, [ebp+arg_4]
0x10018eb9  sub     esp, 28h
0x10018ebc  push    esi
0x10018ebd  test    eax, eax
0x10018ebf  jnz     short loc_10018ED5
0x10018ec1  call    __errno
0x10018ec6  push    16h
0x10018ec8  pop     esi
0x10018ec9  mov     [eax], esi
0x10018ecb  call    __invalid_parameter_noinfo
0x10018ed0  jmp     loc_10019090
0x10018ed5  mov     esi, [ebp+arg_0]
0x10018ed8  push    ebx
0x10018ed9  xor     ebx, ebx
0x10018edb  push    edi
0x10018edc  mov     [eax], ebx
0x10018ede  mov     edi, ebx
0x10018ee0  mov     eax, [esi]
0x10018ee2  mov     ecx, ebx
0x10018ee4  mov     [ebp+Block], edi
0x10018ee7  mov     [ebp+var_24], ecx
0x10018eea  mov     [ebp+var_20], ebx
0x10018eed  test    eax, eax
0x10018eef  jz      short loc_10018F52
0x10018ef1  lea     ecx, [ebp+Control]
0x10018ef4  mov     word ptr [ebp+Control], 3F2Ah
0x10018efa  push    ecx; Control
0x10018efb  push    eax; Str
0x10018efc  mov     [ebp+Control+2], bl
0x10018eff  call    _strpbrk
0x10018f04  pop     ecx
0x10018f05  pop     ecx
0x10018f06  mov     ecx, [esi]
0x10018f08  test    eax, eax
0x10018f0a  jnz     short loc_10018F22
0x10018f0c  lea     eax, [ebp+Block]
0x10018f0f  push    eax; int
0x10018f10  push    ebx; MaxCount
0x10018f11  push    ebx; Source
0x10018f12  push    ecx; char *
0x10018f13  call    sub_100190A2
0x10018f18  mov     esi, eax
0x10018f1a  add     esp, 10h
0x10018f1d  mov     [ebp+var_8], esi
0x10018f20  jmp     short loc_10018F35
0x10018f22  lea     edx, [ebp+Block]
0x10018f25  push    edx; int
0x10018f26  push    eax; Pos
0x10018f27  push    ecx; Start
0x10018f28  call    ??$expand_argument_wildcards@D@@YAHQAD0AAV?$argument_list@D@?A0x5f5c8891@@@Z
0x10018f2d  add     esp, 0Ch
0x10018f30  mov     [ebp+var_8], eax
0x10018f33  mov     esi, eax
0x10018f35  test    esi, esi
0x10018f37  jnz     loc_10018FC5
0x10018f3d  mov     esi, [ebp+arg_0]
0x10018f40  add     esi, 4
0x10018f43  mov     [ebp+arg_0], esi
0x10018f46  mov     eax, [esi]
0x10018f48  test    eax, eax
0x10018f4a  jnz     short loc_10018EF1
0x10018f4c  mov     edi, [ebp+Block]
0x10018f4f  mov     ecx, [ebp+var_24]
0x10018f52  mov     eax, ecx
0x10018f54  mov     dword ptr [ebp+Control], ebx
0x10018f57  sub     eax, edi
0x10018f59  mov     esi, edi
0x10018f5b  mov     edx, eax
0x10018f5d  mov     [ebp+var_8], esi
0x10018f60  sar     edx, 2
0x10018f63  add     eax, 3
0x10018f66  inc     edx
0x10018f67  shr     eax, 2
0x10018f6a  cmp     ecx, esi
0x10018f6c  mov     [ebp+var_C], edx
0x10018f6f  sbb     esi, esi
0x10018f71  not     esi
0x10018f73  and     esi, eax
0x10018f75  jz      short loc_10018FA6
0x10018f77  mov     eax, edi
0x10018f79  mov     edx, ebx
0x10018f7b  mov     ecx, [eax]
0x10018f7d  lea     eax, [ecx+1]
0x10018f80  mov     [ebp+var_10], eax
0x10018f83  mov     al, [ecx]
0x10018f85  inc     ecx
0x10018f86  test    al, al
0x10018f88  jnz     short loc_10018F83
0x10018f8a  sub     ecx, [ebp+var_10]
0x10018f8d  inc     ebx
0x10018f8e  mov     eax, [ebp+var_8]
0x10018f91  add     ebx, ecx
0x10018f93  add     eax, 4
0x10018f96  inc     edx
0x10018f97  mov     [ebp+var_8], eax
0x10018f9a  cmp     edx, esi
0x10018f9c  jnz     short loc_10018F7B
0x10018f9e  mov     edx, [ebp+var_C]
0x10018fa1  mov     dword ptr [ebp+Control], ebx
0x10018fa4  xor     ebx, ebx
0x10018fa6  push    1
0x10018fa8  push    dword ptr [ebp+Control]
0x10018fab  push    edx
0x10018fac  call    ___acrt_allocate_buffer_for_argv
0x10018fb1  mov     esi, eax
0x10018fb3  add     esp, 0Ch
0x10018fb6  test    esi, esi
0x10018fb8  jnz     short loc_10018FCD
0x10018fba  or      esi, 0FFFFFFFFh
0x10018fbd  mov     [ebp+var_8], esi
0x10018fc0  jmp     loc_1001904A
0x10018fc5  mov     edi, [ebp+Block]
0x10018fc8  jmp     loc_10019051
0x10018fcd  mov     eax, [ebp+var_C]
0x10018fd0  mov     [ebp+var_8], edi
0x10018fd3  lea     eax, [esi+eax*4]
0x10018fd6  mov     ecx, eax
0x10018fd8  mov     [ebp+var_18], eax
0x10018fdb  mov     eax, edi
0x10018fdd  mov     [ebp+var_C], ecx
0x10018fe0  cmp     eax, [ebp+var_24]
0x10018fe3  jz      short loc_10019040
0x10018fe5  mov     edx, esi
0x10018fe7  sub     edx, edi
0x10018fe9  mov     [ebp+var_1C], edx
0x10018fec  mov     eax, [eax]
0x10018fee  mov     edx, eax
0x10018ff0  mov     [ebp+Source], eax
0x10018ff3  lea     eax, [edx+1]
0x10018ff6  mov     [ebp+var_10], eax
0x10018ff9  mov     al, [edx]
0x10018ffb  inc     edx
0x10018ffc  test    al, al
0x10018ffe  jnz     short loc_10018FF9
0x10019000  sub     edx, [ebp+var_10]
0x10019003  lea     eax, [edx+1]
0x10019006  push    eax; MaxCount
0x10019007  push    [ebp+Source]; Source
0x1001900a  mov     [ebp+var_10], eax
0x1001900d  mov     eax, [ebp+var_18]
0x10019010  sub     eax, ecx
0x10019012  add     eax, dword ptr [ebp+Control]
0x10019015  push    eax; SizeInBytes
0x10019016  push    ecx; Destination
0x10019017  call    _strncpy_s
0x1001901c  add     esp, 10h
0x1001901f  test    eax, eax
0x10019021  jnz     short loc_10019097
0x10019023  mov     eax, [ebp+var_8]
0x10019026  mov     edx, [ebp+var_1C]
0x10019029  mov     ecx, [ebp+var_C]
0x1001902c  mov     [edx+eax], ecx
0x1001902f  add     eax, 4
0x10019032  add     ecx, [ebp+var_10]
0x10019035  mov     [ebp+var_C], ecx
0x10019038  mov     [ebp+var_8], eax
0x1001903b  cmp     eax, [ebp+var_24]
0x1001903e  jnz     short loc_10018FEC
0x10019040  mov     eax, [ebp+arg_4]
0x10019043  mov     [ebp+var_8], ebx
0x10019046  mov     [eax], esi
0x10019048  mov     esi, ebx
0x1001904a  push    ebx; Block
0x1001904b  call    __free_base
0x10019050  pop     ecx
0x10019051  mov     eax, [ebp+var_24]
0x10019054  mov     edx, edi
0x10019056  sub     eax, edx
0x10019058  mov     [ebp+var_1C], edx
0x1001905b  add     eax, 3
0x1001905e  shr     eax, 2
0x10019061  cmp     [ebp+var_24], edx
0x10019064  sbb     ecx, ecx
0x10019066  not     ecx
0x10019068  and     ecx, eax
0x1001906a  mov     [ebp+var_18], ecx
0x1001906d  jz      short loc_10019087
0x1001906f  mov     esi, ecx
0x10019071  push    dword ptr [edi]; Block
0x10019073  call    __free_base
0x10019078  inc     ebx
0x10019079  lea     edi, [edi+4]
0x1001907c  pop     ecx
0x1001907d  cmp     ebx, esi
0x1001907f  jnz     short loc_10019071
0x10019081  mov     edi, [ebp+Block]
0x10019084  mov     esi, [ebp+var_8]
0x10019087  push    edi; Block
0x10019088  call    __free_base
0x1001908d  pop     ecx
0x1001908e  pop     edi
0x1001908f  pop     ebx
0x10019090  mov     eax, esi
0x10019092  pop     esi
0x10019093  mov     esp, ebp
0x10019095  pop     ebp
0x10019096  retn
0x10019097  push    ebx; Reserved
0x10019098  push    ebx; LineNo
0x10019099  push    ebx; FileName
0x1001909a  push    ebx; FunctionName
0x1001909b  push    ebx; Expression
0x1001909c  call    __invoke_watson
```
