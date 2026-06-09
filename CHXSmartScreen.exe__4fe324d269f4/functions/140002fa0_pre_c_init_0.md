# pre_c_init_0

- ea: `0x140002fa0`
- end: `0x140003077`
- name: `pre_c_init_0`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002fa0`
- `0x140003908`
- `0x14000acf0`

## import_xrefs

- `msvcrt!_commode` at `0x140003046`
- `msvcrt!_fmode` at `0x14000303d`
- `msvcrt!__setusermatherr` at `0x14000306a`
- `msvcrt!__setusermatherr` at `0x14000306a`
- `msvcrt!__set_app_type` at `0x14000301f`
- `msvcrt!__set_app_type` at `0x14000301f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init_0()
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
  dword_14004CAD0 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = (void *)-1LL;
  _fmode = fmode;
  _commode = commode;
  std::wstreambuf::showmanyc(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(std::wstreambuf::showmanyc);
  return 0;
}

```

## disassembly

```asm
0x140002fa0  sub     rsp, 28h
0x140002fa4  mov     eax, 5A4Dh
0x140002fa9  cmp     cs:140000000h, ax
0x140002fb0  jz      short loc_140002FB6
0x140002fb2  xor     eax, eax
0x140002fb4  jmp     short loc_14000300D
0x140002fb6  movsxd  rcx, dword ptr cs:14000003Ch
0x140002fbd  lea     rdx, cs:140000000h
0x140002fc4  cmp     dword ptr [rcx+rdx], 4550h
0x140002fcb  jnz     short loc_140002FB2
0x140002fcd  mov     eax, 10Bh
0x140002fd2  cmp     [rcx+rdx+18h], ax
0x140002fd7  jz      short loc_140002FFA
0x140002fd9  mov     eax, 20Bh
0x140002fde  cmp     [rcx+rdx+18h], ax
0x140002fe3  jnz     short loc_140002FB2
0x140002fe5  xor     eax, eax
0x140002fe7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140002fef  jbe     short loc_14000300D
0x140002ff1  cmp     [rcx+rdx+0F8h], eax
0x140002ff8  jmp     short loc_14000300A
0x140002ffa  xor     eax, eax
0x140002ffc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140003001  jbe     short loc_14000300D
0x140003003  cmp     [rcx+rdx+0E8h], eax
0x14000300a  setnz   al
0x14000300d  mov     ecx, 2
0x140003012  mov     cs:dword_14004CAD0, eax
0x140003018  call    _get_image_app_type
0x14000301d  mov     ecx, eax; Type
0x14000301f  call    cs:__imp___set_app_type
0x140003025  mov     ecx, cs:_fmode
0x14000302b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000302f  mov     cs:__onexitend, rax
0x140003036  mov     cs:__onexitbegin, rax
0x14000303d  mov     rax, cs:__imp__fmode
0x140003044  mov     [rax], ecx
0x140003046  mov     rcx, cs:__imp__commode; struct _exception *
0x14000304d  mov     eax, cs:_commode
0x140003053  mov     [rcx], eax
0x140003055  call    ?showmanyc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAA_JXZ; std::wstreambuf::showmanyc(void)
0x14000305a  cmp     cs:__defaultmatherr, 0
0x140003061  jnz     short loc_140003070
0x140003063  lea     rcx, ?showmanyc@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@MEAA_JXZ; UserMathErrorFunction
0x14000306a  call    cs:__imp___setusermatherr
0x140003070  xor     eax, eax
0x140003072  add     rsp, 28h
0x140003076  retn
```
