# pre_c_init

- ea: `0x1400020d0`
- end: `0x1400021a7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400020d0`
- `0x140002734`
- `0x14000a400`

## import_xrefs

- `msvcrt!__setusermatherr` at `0x14000219a`
- `msvcrt!__setusermatherr` at `0x14000219a`
- `msvcrt!__set_app_type` at `0x14000214f`
- `msvcrt!__set_app_type` at `0x14000214f`
- `msvcrt!_fmode` at `0x14000216d`
- `msvcrt!_commode` at `0x140002176`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(MEMORY[0x140000000].unused) != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
    goto LABEL_2;
  if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) != 267 )
  {
    if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000084LL) <= 0xEu )
        goto LABEL_11;
      v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000F8LL) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000074LL) <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000E8LL) == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_140017480 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  CloudExperienceHostWAMExecuteCommand::SetKeyState(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(CloudExperienceHostWAMExecuteCommand::SetKeyState);
  return 0;
}

```

## disassembly

```asm
0x1400020d0  sub     rsp, 28h
0x1400020d4  mov     eax, 5A4Dh
0x1400020d9  cmp     cs:140000000h, ax
0x1400020e0  jz      short loc_1400020E6
0x1400020e2  xor     eax, eax
0x1400020e4  jmp     short loc_14000213D
0x1400020e6  movsxd  rcx, dword ptr cs:14000003Ch
0x1400020ed  lea     rdx, cs:140000000h
0x1400020f4  cmp     dword ptr [rcx+rdx], 4550h
0x1400020fb  jnz     short loc_1400020E2
0x1400020fd  mov     eax, 10Bh
0x140002102  cmp     [rcx+rdx+18h], ax
0x140002107  jz      short loc_14000212A
0x140002109  mov     eax, 20Bh
0x14000210e  cmp     [rcx+rdx+18h], ax
0x140002113  jnz     short loc_1400020E2
0x140002115  xor     eax, eax
0x140002117  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000211f  jbe     short loc_14000213D
0x140002121  cmp     [rcx+rdx+0F8h], eax
0x140002128  jmp     short loc_14000213A
0x14000212a  xor     eax, eax
0x14000212c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140002131  jbe     short loc_14000213D
0x140002133  cmp     [rcx+rdx+0E8h], eax
0x14000213a  setnz   al
0x14000213d  mov     ecx, 2
0x140002142  mov     cs:dword_140017480, eax
0x140002148  call    _get_image_app_type
0x14000214d  mov     ecx, eax; Type
0x14000214f  call    cs:__imp___set_app_type
0x140002155  mov     ecx, cs:_fmode
0x14000215b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000215f  mov     cs:__onexitend, rax
0x140002166  mov     cs:__onexitbegin, rax
0x14000216d  mov     rax, cs:__imp__fmode
0x140002174  mov     [rax], ecx
0x140002176  mov     rcx, cs:__imp__commode; struct _exception *
0x14000217d  mov     eax, cs:_commode
0x140002183  mov     [rcx], eax
0x140002185  call    ?SetKeyState@CloudExperienceHostWAMExecuteCommand@@UEAAJK@Z; CloudExperienceHostWAMExecuteCommand::SetKeyState(ulong)
0x14000218a  cmp     cs:__defaultmatherr, 0
0x140002191  jnz     short loc_1400021A0
0x140002193  lea     rcx, ?SetKeyState@CloudExperienceHostWAMExecuteCommand@@UEAAJK@Z; UserMathErrorFunction
0x14000219a  call    cs:__imp___setusermatherr
0x1400021a0  xor     eax, eax
0x1400021a2  add     rsp, 28h
0x1400021a6  retn
```
