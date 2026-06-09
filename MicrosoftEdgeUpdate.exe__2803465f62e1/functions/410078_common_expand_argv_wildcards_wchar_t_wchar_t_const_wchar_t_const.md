# common_expand_argv_wildcards<wchar_t>(wchar_t * * const,wchar_t * * * const)

- ea: `0x410078`
- end: `0x41029f`
- name: `??$common_expand_argv_wildcards@_W@@YAHQAPA_WQAPAPA_W@Z`
- size: `551`
- prototype: `int __cdecl(const wchar_t **, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x410571`

## callees

- `0x40b3e3`
- `0x40de54`
- `0x40de81`
- `0x40e76a`
- `0x40ff25`
- `0x40ffa9`
- `0x41001a`
- `0x410078`
- `0x4102a0`
- `0x410354`
- `0x41169f`

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
0x410078  mov     edi, edi
0x41007a  push    ebp
0x41007b  mov     ebp, esp
0x41007d  sub     esp, 34h
0x410080  mov     eax, ___security_cookie
0x410085  xor     eax, ebp
0x410087  mov     [ebp+var_4], eax
0x41008a  mov     eax, [ebp+arg_4]
0x41008d  mov     [ebp+var_20], eax
0x410090  push    esi
0x410091  mov     esi, [ebp+arg_0]
0x410094  mov     [ebp+var_14], esi
0x410097  test    eax, eax
0x410099  jnz     short loc_4100AF
0x41009b  call    __errno
0x4100a0  push    16h
0x4100a2  pop     esi
0x4100a3  mov     [eax], esi
0x4100a5  call    __invalid_parameter_noinfo
0x4100aa  jmp     loc_410286
0x4100af  push    ebx
0x4100b0  push    edi
0x4100b1  xor     edi, edi
0x4100b3  mov     [eax], edi
0x4100b5  mov     ebx, edi
0x4100b7  mov     eax, [esi]
0x4100b9  mov     ecx, edi
0x4100bb  mov     [ebp+Block], ebx
0x4100be  mov     [ebp+var_28], ecx
0x4100c1  mov     [ebp+var_24], edi
0x4100c4  test    eax, eax
0x4100c6  jz      short loc_410134
0x4100c8  push    2Ah ; '*'
0x4100ca  pop     ecx
0x4100cb  mov     [ebp+Control], cx
0x4100cf  push    3Fh ; '?'
0x4100d1  pop     ecx
0x4100d2  mov     [ebp+Control+2], cx
0x4100d6  xor     ecx, ecx
0x4100d8  mov     [ebp+var_8], cx
0x4100dc  lea     ecx, [ebp+Control]
0x4100df  push    ecx; Control
0x4100e0  push    eax; String
0x4100e1  call    _wcspbrk
0x4100e6  pop     ecx
0x4100e7  pop     ecx
0x4100e8  mov     ecx, [esi]
0x4100ea  test    eax, eax
0x4100ec  jnz     short loc_410104
0x4100ee  lea     eax, [ebp+Block]
0x4100f1  push    eax; int
0x4100f2  push    edi; MaxCount
0x4100f3  push    edi; Source
0x4100f4  push    ecx; wchar_t *
0x4100f5  call    ??$copy_and_add_argument_to_buffer@_W@@YAHQB_W0IAAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x4100fa  mov     esi, eax
0x4100fc  add     esp, 10h
0x4100ff  mov     [ebp+var_10], esi
0x410102  jmp     short loc_410117
0x410104  lea     edx, [ebp+Block]
0x410107  push    edx; int
0x410108  push    eax; int
0x410109  push    ecx; lpFileName
0x41010a  call    ??$expand_argument_wildcards@_W@@YAHQA_W0AAV?$argument_list@_W@?A0x5f5c8891@@@Z
0x41010f  add     esp, 0Ch
0x410112  mov     [ebp+var_10], eax
0x410115  mov     esi, eax
0x410117  test    esi, esi
0x410119  jnz     loc_4101AE
0x41011f  mov     esi, [ebp+var_14]
0x410122  add     esi, 4
0x410125  mov     [ebp+var_14], esi
0x410128  mov     eax, [esi]
0x41012a  test    eax, eax
0x41012c  jnz     short loc_4100C8
0x41012e  mov     ebx, [ebp+Block]
0x410131  mov     ecx, [ebp+var_28]
0x410134  mov     eax, ecx
0x410136  mov     [ebp+var_10], edi
0x410139  sub     eax, ebx
0x41013b  mov     esi, ebx
0x41013d  mov     edx, eax
0x41013f  mov     [ebp+var_14], esi
0x410142  sar     edx, 2
0x410145  add     eax, 3
0x410148  inc     edx
0x410149  shr     eax, 2
0x41014c  cmp     ecx, esi
0x41014e  mov     [ebp+var_1C], edx
0x410151  sbb     esi, esi
0x410153  not     esi
0x410155  and     esi, eax
0x410157  jz      short loc_41018F
0x410159  mov     eax, ebx
0x41015b  mov     edx, edi
0x41015d  mov     ecx, [eax]
0x41015f  lea     eax, [ecx+2]
0x410162  mov     [ebp+var_18], eax
0x410165  mov     ax, [ecx]
0x410168  add     ecx, 2
0x41016b  cmp     ax, di
0x41016e  jnz     short loc_410165
0x410170  sub     ecx, [ebp+var_18]
0x410173  mov     eax, [ebp+var_10]
0x410176  inc     eax
0x410177  sar     ecx, 1
0x410179  add     eax, ecx
0x41017b  mov     [ebp+var_10], eax
0x41017e  mov     eax, [ebp+var_14]
0x410181  add     eax, 4
0x410184  inc     edx
0x410185  mov     [ebp+var_14], eax
0x410188  cmp     edx, esi
0x41018a  jnz     short loc_41015D
0x41018c  mov     edx, [ebp+var_1C]
0x41018f  push    2
0x410191  push    [ebp+var_10]
0x410194  push    edx
0x410195  call    ___acrt_allocate_buffer_for_argv
0x41019a  mov     esi, eax
0x41019c  add     esp, 0Ch
0x41019f  test    esi, esi
0x4101a1  jnz     short loc_4101B6
0x4101a3  or      esi, 0FFFFFFFFh
0x4101a6  mov     [ebp+var_10], esi
0x4101a9  jmp     loc_410240
0x4101ae  mov     ebx, [ebp+Block]
0x4101b1  jmp     loc_410247
0x4101b6  mov     eax, [ebp+var_1C]
0x4101b9  mov     [ebp+var_14], ebx
0x4101bc  lea     eax, [esi+eax*4]
0x4101bf  mov     edx, eax
0x4101c1  mov     [ebp+var_34], eax
0x4101c4  mov     eax, ebx
0x4101c6  mov     [ebp+var_1C], edx
0x4101c9  cmp     eax, [ebp+var_28]
0x4101cc  jz      short loc_410236
0x4101ce  mov     ecx, esi
0x4101d0  sub     ecx, ebx
0x4101d2  mov     dword ptr [ebp+Control], ecx
0x4101d5  mov     eax, [eax]
0x4101d7  mov     ecx, eax
0x4101d9  mov     [ebp+Source], eax
0x4101dc  lea     eax, [ecx+2]
0x4101df  mov     [ebp+var_18], eax
0x4101e2  mov     ax, [ecx]
0x4101e5  add     ecx, 2
0x4101e8  cmp     ax, di
0x4101eb  jnz     short loc_4101E2
0x4101ed  sub     ecx, [ebp+var_18]
0x4101f0  sar     ecx, 1
0x4101f2  lea     eax, [ecx+1]
0x4101f5  mov     ecx, edx
0x4101f7  sub     ecx, [ebp+var_34]
0x4101fa  push    eax; MaxCount
0x4101fb  push    [ebp+Source]; Source
0x4101fe  mov     [ebp+var_18], eax
0x410201  mov     eax, [ebp+var_10]
0x410204  sar     ecx, 1
0x410206  sub     eax, ecx
0x410208  push    eax; SizeInWords
0x410209  push    edx; Destination
0x41020a  call    _wcsncpy_s
0x41020f  add     esp, 10h
0x410212  test    eax, eax
0x410214  jnz     short loc_410295
0x410216  mov     eax, [ebp+var_14]
0x410219  mov     ecx, dword ptr [ebp+Control]
0x41021c  mov     edx, [ebp+var_1C]
0x41021f  mov     [ecx+eax], edx
0x410222  add     eax, 4
0x410225  mov     ecx, [ebp+var_18]
0x410228  mov     [ebp+var_14], eax
0x41022b  lea     edx, [edx+ecx*2]
0x41022e  mov     [ebp+var_1C], edx
0x410231  cmp     eax, [ebp+var_28]
0x410234  jnz     short loc_4101D5
0x410236  mov     eax, [ebp+var_20]
0x410239  mov     [ebp+var_10], edi
0x41023c  mov     [eax], esi
0x41023e  mov     esi, edi
0x410240  push    edi; Block
0x410241  call    __free_base
0x410246  pop     ecx
0x410247  mov     eax, [ebp+var_28]
0x41024a  mov     edx, ebx
0x41024c  sub     eax, edx
0x41024e  mov     [ebp+var_20], edx
0x410251  add     eax, 3
0x410254  shr     eax, 2
0x410257  cmp     [ebp+var_28], edx
0x41025a  sbb     ecx, ecx
0x41025c  not     ecx
0x41025e  and     ecx, eax
0x410260  mov     dword ptr [ebp+Control], ecx
0x410263  jz      short loc_41027D
0x410265  mov     esi, ecx
0x410267  push    dword ptr [ebx]; Block
0x410269  call    __free_base
0x41026e  inc     edi
0x41026f  lea     ebx, [ebx+4]
0x410272  pop     ecx
0x410273  cmp     edi, esi
0x410275  jnz     short loc_410267
0x410277  mov     ebx, [ebp+Block]
0x41027a  mov     esi, [ebp+var_10]
0x41027d  push    ebx; Block
0x41027e  call    __free_base
0x410283  pop     ecx
0x410284  pop     edi
0x410285  pop     ebx
0x410286  mov     ecx, [ebp+var_4]
0x410289  mov     eax, esi
0x41028b  xor     ecx, ebp; StackCookie
0x41028d  pop     esi
0x41028e  call    @__security_check_cookie@4
0x410293  leave
0x410294  retn
0x410295  push    edi; Reserved
0x410296  push    edi; LineNo
0x410297  push    edi; FileName
0x410298  push    edi; FunctionName
0x410299  push    edi; Expression
0x41029a  call    __invoke_watson
```
