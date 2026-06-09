# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x413e98`
- end: `0x4140bf`
- name: `??$common_expand_argv_wildcards@_W@@YAHQAPA_WQAPAPA_W@Z`
- size: `551`
- prototype: `int __cdecl(const wchar_t **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x414391`

## callees

- `0x40d08d`
- `0x410369`
- `0x410396`
- `0x410443`
- `0x410bf2`
- `0x4136b2`
- `0x413e98`
- `0x4140c0`
- `0x414174`
- `0x415d1f`
- `0x4166c7`

## pseudocode

```c
int __cdecl common_expand_argv_wildcards<wchar_t>(const wchar_t **a1, void **a2)
{
  WCHAR **v2; // esi
  int v3; // esi
  int v4; // edi
  void **v5; // ebx
  const wchar_t *v6; // eax
  unsigned int v7; // ecx
  wchar_t *v8; // eax
  WCHAR *v9; // ecx
  int v10; // edx
  unsigned int v11; // esi
  void **v12; // eax
  int i; // edx
  _WORD *v14; // ecx
  _BYTE *buffer_for_argv; // eax
  _BYTE *v17; // esi
  wchar_t *v18; // edx
  wchar_t **v19; // eax
  wchar_t *v20; // ecx
  wchar_t **v22; // eax
  wchar_t *v23; // edx
  unsigned int v24; // eax
  unsigned int v25; // esi
  wchar_t *v27; // [esp+4h] [ebp-34h]
  wchar_t *Source; // [esp+8h] [ebp-30h]
  void *Block; // [esp+Ch] [ebp-2Ch] BYREF
  char *v30; // [esp+10h] [ebp-28h]
  int v31; // [esp+14h] [ebp-24h]
  void **v32; // [esp+18h] [ebp-20h]
  wchar_t *v33; // [esp+1Ch] [ebp-1Ch]
  rsize_t v34; // [esp+20h] [ebp-18h]
  wchar_t **v35; // [esp+24h] [ebp-14h]
  int v36; // [esp+28h] [ebp-10h]
  wchar_t Control[4]; // [esp+2Ch] [ebp-Ch] BYREF

  v32 = a2;
  v2 = (WCHAR **)a1;
  v35 = (wchar_t **)a1;
  if ( a2 )
  {
    v4 = 0;
    *a2 = 0;
    v5 = 0;
    v6 = *a1;
    v7 = 0;
    Block = 0;
    v30 = 0;
    v31 = 0;
    if ( v6 )
    {
      while ( 1 )
      {
        wcscpy(Control, L"*?");
        v8 = wcspbrk(v6, Control);
        v9 = *v2;
        if ( v8 )
        {
          v36 = expand_argument_wildcards<wchar_t>(v9, (int)v8, (int)&Block);
          v3 = v36;
        }
        else
        {
          v3 = copy_and_add_argument_to_buffer<wchar_t>(v9, 0, 0, (int)&Block);
          v36 = v3;
        }
        if ( v3 )
          break;
        v2 = v35 + 1;
        v35 = v2;
        v6 = *v2;
        if ( !*v2 )
        {
          v5 = (void **)Block;
          v7 = (unsigned int)v30;
          goto LABEL_10;
        }
      }
      v5 = (void **)Block;
    }
    else
    {
LABEL_10:
      v36 = 0;
      v35 = (wchar_t **)v5;
      v10 = ((int)(v7 - (_DWORD)v5) >> 2) + 1;
      v33 = (wchar_t *)v10;
      v11 = v7 >= (unsigned int)v5 ? (v7 - (unsigned int)v5 + 3) >> 2 : 0;
      if ( v11 )
      {
        v12 = v5;
        for ( i = 0; i != v11; ++i )
        {
          v14 = *v12;
          v34 = (rsize_t)*v12 + 2;
          while ( *v14++ )
            ;
          v36 += ((int)((int)v14 - v34) >> 1) + 1;
          v12 = (void **)++v35;
        }
        v10 = (int)v33;
      }
      buffer_for_argv = (_BYTE *)__acrt_allocate_buffer_for_argv(v10, v36, 2);
      v17 = buffer_for_argv;
      if ( buffer_for_argv )
      {
        v35 = (wchar_t **)v5;
        v18 = (wchar_t *)&buffer_for_argv[4 * (_DWORD)v33];
        v27 = v18;
        v19 = (wchar_t **)v5;
        v33 = (wchar_t *)&v17[4 * (_DWORD)v33];
        if ( v5 != (void **)v30 )
        {
          *(_DWORD *)Control = v17 - (_BYTE *)v5;
          do
          {
            v20 = *v19;
            Source = *v19;
            v34 = (rsize_t)(*v19 + 1);
            while ( *v20++ )
              ;
            v34 = ((int)((int)v20 - v34) >> 1) + 1;
            if ( wcsncpy_s(v18, v36 - (v18 - v27), Source, v34) )
              _invoke_watson(0, 0, 0, 0, 0);
            v22 = v35;
            v23 = v33;
            *(wchar_t **)((char *)v35 + *(_DWORD *)Control) = v33;
            v19 = v22 + 1;
            v35 = v19;
            v18 = &v23[v34];
            v33 = v18;
          }
          while ( v19 != (wchar_t **)v30 );
        }
        v36 = 0;
        *v32 = v17;
        v3 = 0;
      }
      else
      {
        v3 = -1;
        v36 = -1;
      }
      _free_base(0);
    }
    v32 = v5;
    v24 = (unsigned int)(v30 - (char *)v5 + 3) >> 2;
    *(_DWORD *)Control = v30 >= (char *)v5 ? v24 : 0;
    if ( *(_DWORD *)Control )
    {
      v25 = v30 >= (char *)v5 ? v24 : 0;
      do
      {
        _free_base(*v5);
        ++v4;
        ++v5;
      }
      while ( v4 != v25 );
      v5 = (void **)Block;
      v3 = v36;
    }
    _free_base(v5);
  }
  else
  {
    v3 = 22;
    *_errno() = 22;
    _invalid_parameter_noinfo();
  }
  return v3;
}

```

## disassembly

```asm
0x413e98  mov     edi, edi
0x413e9a  push    ebp
0x413e9b  mov     ebp, esp
0x413e9d  sub     esp, 34h
0x413ea0  mov     eax, ___security_cookie
0x413ea5  xor     eax, ebp
0x413ea7  mov     [ebp+var_4], eax
0x413eaa  mov     eax, [ebp+arg_4]
0x413ead  mov     [ebp+var_20], eax
0x413eb0  push    esi
0x413eb1  mov     esi, [ebp+arg_0]
0x413eb4  mov     [ebp+var_14], esi
0x413eb7  test    eax, eax
0x413eb9  jnz     short loc_413ECF
0x413ebb  call    __errno
0x413ec0  push    16h
0x413ec2  pop     esi
0x413ec3  mov     [eax], esi
0x413ec5  call    __invalid_parameter_noinfo
0x413eca  jmp     loc_4140A6
0x413ecf  push    ebx
0x413ed0  push    edi
0x413ed1  xor     edi, edi
0x413ed3  mov     [eax], edi
0x413ed5  mov     ebx, edi
0x413ed7  mov     eax, [esi]
0x413ed9  mov     ecx, edi
0x413edb  mov     [ebp+Block], ebx
0x413ede  mov     [ebp+var_28], ecx
0x413ee1  mov     [ebp+var_24], edi
0x413ee4  test    eax, eax
0x413ee6  jz      short loc_413F54
0x413ee8  push    2Ah ; '*'
0x413eea  pop     ecx
0x413eeb  mov     [ebp+Control], cx
0x413eef  push    3Fh ; '?'
0x413ef1  pop     ecx
0x413ef2  mov     [ebp+Control+2], cx
0x413ef6  xor     ecx, ecx
0x413ef8  mov     [ebp+var_8], cx
0x413efc  lea     ecx, [ebp+Control]
0x413eff  push    ecx; Control
0x413f00  push    eax; String
0x413f01  call    _wcspbrk
0x413f06  pop     ecx
0x413f07  pop     ecx
0x413f08  mov     ecx, [esi]
0x413f0a  test    eax, eax
0x413f0c  jnz     short loc_413F24
0x413f0e  lea     eax, [ebp+Block]
0x413f11  push    eax; int
0x413f12  push    edi; MaxCount
0x413f13  push    edi; Source
0x413f14  push    ecx; wchar_t *
0x413f15  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQB_W0IAAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x413f1a  mov     esi, eax
0x413f1c  add     esp, 10h
0x413f1f  mov     [ebp+var_10], esi
0x413f22  jmp     short loc_413F37
0x413f24  lea     edx, [ebp+Block]
0x413f27  push    edx; int
0x413f28  push    eax; int
0x413f29  push    ecx; lpFileName
0x413f2a  call    ??$expand_argument_wildcards@_W@@YAHQA_W0AAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x413f2f  add     esp, 0Ch
0x413f32  mov     [ebp+var_10], eax
0x413f35  mov     esi, eax
0x413f37  test    esi, esi
0x413f39  jnz     loc_413FCE
0x413f3f  mov     esi, [ebp+var_14]
0x413f42  add     esi, 4
0x413f45  mov     [ebp+var_14], esi
0x413f48  mov     eax, [esi]
0x413f4a  test    eax, eax
0x413f4c  jnz     short loc_413EE8
0x413f4e  mov     ebx, [ebp+Block]
0x413f51  mov     ecx, [ebp+var_28]
0x413f54  mov     eax, ecx
0x413f56  mov     [ebp+var_10], edi
0x413f59  sub     eax, ebx
0x413f5b  mov     esi, ebx
0x413f5d  mov     edx, eax
0x413f5f  mov     [ebp+var_14], esi
0x413f62  sar     edx, 2
0x413f65  add     eax, 3
0x413f68  inc     edx
0x413f69  shr     eax, 2
0x413f6c  cmp     ecx, esi
0x413f6e  mov     [ebp+var_1C], edx
0x413f71  sbb     esi, esi
0x413f73  not     esi
0x413f75  and     esi, eax
0x413f77  jz      short loc_413FAF
0x413f79  mov     eax, ebx
0x413f7b  mov     edx, edi
0x413f7d  mov     ecx, [eax]
0x413f7f  lea     eax, [ecx+2]
0x413f82  mov     [ebp+var_18], eax
0x413f85  mov     ax, [ecx]
0x413f88  add     ecx, 2
0x413f8b  cmp     ax, di
0x413f8e  jnz     short loc_413F85
0x413f90  sub     ecx, [ebp+var_18]
0x413f93  mov     eax, [ebp+var_10]
0x413f96  inc     eax
0x413f97  sar     ecx, 1
0x413f99  add     eax, ecx
0x413f9b  mov     [ebp+var_10], eax
0x413f9e  mov     eax, [ebp+var_14]
0x413fa1  add     eax, 4
0x413fa4  inc     edx
0x413fa5  mov     [ebp+var_14], eax
0x413fa8  cmp     edx, esi
0x413faa  jnz     short loc_413F7D
0x413fac  mov     edx, [ebp+var_1C]
0x413faf  push    2
0x413fb1  push    [ebp+var_10]
0x413fb4  push    edx
0x413fb5  call    ___acrt_allocate_buffer_for_argv
0x413fba  mov     esi, eax
0x413fbc  add     esp, 0Ch
0x413fbf  test    esi, esi
0x413fc1  jnz     short loc_413FD6
0x413fc3  or      esi, 0FFFFFFFFh
0x413fc6  mov     [ebp+var_10], esi
0x413fc9  jmp     loc_414060
0x413fce  mov     ebx, [ebp+Block]
0x413fd1  jmp     loc_414067
0x413fd6  mov     eax, [ebp+var_1C]
0x413fd9  mov     [ebp+var_14], ebx
0x413fdc  lea     eax, [esi+eax*4]
0x413fdf  mov     edx, eax
0x413fe1  mov     [ebp+var_34], eax
0x413fe4  mov     eax, ebx
0x413fe6  mov     [ebp+var_1C], edx
0x413fe9  cmp     eax, [ebp+var_28]
0x413fec  jz      short loc_414056
0x413fee  mov     ecx, esi
0x413ff0  sub     ecx, ebx
0x413ff2  mov     dword ptr [ebp+Control], ecx
0x413ff5  mov     eax, [eax]
0x413ff7  mov     ecx, eax
0x413ff9  mov     [ebp+Source], eax
0x413ffc  lea     eax, [ecx+2]
0x413fff  mov     [ebp+var_18], eax
0x414002  mov     ax, [ecx]
0x414005  add     ecx, 2
0x414008  cmp     ax, di
0x41400b  jnz     short loc_414002
0x41400d  sub     ecx, [ebp+var_18]
0x414010  sar     ecx, 1
0x414012  lea     eax, [ecx+1]
0x414015  mov     ecx, edx
0x414017  sub     ecx, [ebp+var_34]
0x41401a  push    eax; MaxCount
0x41401b  push    [ebp+Source]; Source
0x41401e  mov     [ebp+var_18], eax
0x414021  mov     eax, [ebp+var_10]
0x414024  sar     ecx, 1
0x414026  sub     eax, ecx
0x414028  push    eax; SizeInWords
0x414029  push    edx; Destination
0x41402a  call    _wcsncpy_s
0x41402f  add     esp, 10h
0x414032  test    eax, eax
0x414034  jnz     short loc_4140B5
0x414036  mov     eax, [ebp+var_14]
0x414039  mov     ecx, dword ptr [ebp+Control]
0x41403c  mov     edx, [ebp+var_1C]
0x41403f  mov     [ecx+eax], edx
0x414042  add     eax, 4
0x414045  mov     ecx, [ebp+var_18]
0x414048  mov     [ebp+var_14], eax
0x41404b  lea     edx, [edx+ecx*2]
0x41404e  mov     [ebp+var_1C], edx
0x414051  cmp     eax, [ebp+var_28]
0x414054  jnz     short loc_413FF5
0x414056  mov     eax, [ebp+var_20]
0x414059  mov     [ebp+var_10], edi
0x41405c  mov     [eax], esi
0x41405e  mov     esi, edi
0x414060  push    edi; Block
0x414061  call    __free_base
0x414066  pop     ecx
0x414067  mov     eax, [ebp+var_28]
0x41406a  mov     edx, ebx
0x41406c  sub     eax, edx
0x41406e  mov     [ebp+var_20], edx
0x414071  add     eax, 3
0x414074  shr     eax, 2
0x414077  cmp     [ebp+var_28], edx
0x41407a  sbb     ecx, ecx
0x41407c  not     ecx
0x41407e  and     ecx, eax
0x414080  mov     dword ptr [ebp+Control], ecx
0x414083  jz      short loc_41409D
0x414085  mov     esi, ecx
0x414087  push    dword ptr [ebx]; Block
0x414089  call    __free_base
0x41408e  inc     edi
0x41408f  lea     ebx, [ebx+4]
0x414092  pop     ecx
0x414093  cmp     edi, esi
0x414095  jnz     short loc_414087
0x414097  mov     ebx, [ebp+Block]
0x41409a  mov     esi, [ebp+var_10]
0x41409d  push    ebx; Block
0x41409e  call    __free_base
0x4140a3  pop     ecx
0x4140a4  pop     edi
0x4140a5  pop     ebx
0x4140a6  mov     ecx, [ebp+var_4]
0x4140a9  mov     eax, esi
0x4140ab  xor     ecx, ebp; StackCookie
0x4140ad  pop     esi
0x4140ae  call    @__security_check_cookie@4
0x4140b3  leave
0x4140b4  retn
0x4140b5  push    edi; Reserved
0x4140b6  push    edi; LineNo
0x4140b7  push    edi; FileName
0x4140b8  push    edi; FunctionName
0x4140b9  push    edi; Expression
0x4140ba  call    __invoke_watson
```
