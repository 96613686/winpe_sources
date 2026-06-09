# pre_c_init

- ea: `0x1400012c0`
- end: `0x140001397`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400012c0`
- `0x140001694`
- `0x140003350`

## import_xrefs

- `msvcrt!_commode` at `0x140001366`
- `msvcrt!_fmode` at `0x14000135d`
- `msvcrt!__setusermatherr` at `0x14000138a`
- `msvcrt!__setusermatherr` at `0x14000138a`
- `msvcrt!__set_app_type` at `0x14000133f`
- `msvcrt!__set_app_type` at `0x14000133f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( _ImageBase != 23117 || *(_DWORD *)((char *)&_ImageBase + (int)off_14000003C) != 17744 )
    goto LABEL_2;
  if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 267 )
  {
    if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xEu )
        goto LABEL_11;
      v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 184] == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 52] <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 168] == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_14001D2A0 = v0;
  image_app_type = (unsigned int)get_image_app_type(1);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  AuthHostWebInstance::ContextSensitiveHelp(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(AuthHostWebInstance::ContextSensitiveHelp);
  return 0;
}

```

## disassembly

```asm
0x1400012c0  sub     rsp, 28h
0x1400012c4  mov     eax, 5A4Dh
0x1400012c9  cmp     cs:__ImageBase, ax
0x1400012d0  jz      short loc_1400012D6
0x1400012d2  xor     eax, eax
0x1400012d4  jmp     short loc_14000132D
0x1400012d6  movsxd  rcx, cs:off_14000003C
0x1400012dd  lea     rdx, __ImageBase
0x1400012e4  cmp     dword ptr [rcx+rdx], 4550h
0x1400012eb  jnz     short loc_1400012D2
0x1400012ed  mov     eax, 10Bh
0x1400012f2  cmp     [rcx+rdx+18h], ax
0x1400012f7  jz      short loc_14000131A
0x1400012f9  mov     eax, 20Bh
0x1400012fe  cmp     [rcx+rdx+18h], ax
0x140001303  jnz     short loc_1400012D2
0x140001305  xor     eax, eax
0x140001307  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000130f  jbe     short loc_14000132D
0x140001311  cmp     [rcx+rdx+0F8h], eax
0x140001318  jmp     short loc_14000132A
0x14000131a  xor     eax, eax
0x14000131c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001321  jbe     short loc_14000132D
0x140001323  cmp     [rcx+rdx+0E8h], eax
0x14000132a  setnz   al
0x14000132d  mov     ecx, 1
0x140001332  mov     cs:dword_14001D2A0, eax
0x140001338  call    _get_image_app_type
0x14000133d  mov     ecx, eax; Type
0x14000133f  call    cs:__imp___set_app_type
0x140001345  mov     ecx, cs:_fmode
0x14000134b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000134f  mov     cs:__onexitend, rax
0x140001356  mov     cs:__onexitbegin, rax
0x14000135d  mov     rax, cs:__imp__fmode
0x140001364  mov     [rax], ecx
0x140001366  mov     rcx, cs:__imp__commode; struct _exception *
0x14000136d  mov     eax, cs:_commode
0x140001373  mov     [rcx], eax
0x140001375  call    ?ContextSensitiveHelp@AuthHostWebInstance@@UEAAJH@Z; AuthHostWebInstance::ContextSensitiveHelp(int)
0x14000137a  cmp     cs:__defaultmatherr, 0
0x140001381  jnz     short loc_140001390
0x140001383  lea     rcx, ?ContextSensitiveHelp@AuthHostWebInstance@@UEAAJH@Z; UserMathErrorFunction
0x14000138a  call    cs:__imp___setusermatherr
0x140001390  xor     eax, eax
0x140001392  add     rsp, 28h
0x140001396  retn
```
