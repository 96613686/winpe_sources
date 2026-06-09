# pre_c_init

- ea: `0x40c810`
- end: `0x40c87c`
- name: `pre_c_init`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x40c810`
- `0x40cadb`
- `0x40ceb4`
- `0x40cf10`
- `0x40d117`

## import_xrefs

- `msvcrt!__setusermatherr` at `0x40c86d`
- `msvcrt!__setusermatherr` at `0x40c86d`
- `msvcrt!__p__fmode` at `0x40c83e`
- `msvcrt!__p__fmode` at `0x40c83e`
- `msvcrt!__set_app_type` at `0x40c822`
- `msvcrt!__set_app_type` at `0x40c822`
- `msvcrt!__p__commode` at `0x40c84c`
- `msvcrt!__p__commode` at `0x40c84c`

## pseudocode

```c

```

## disassembly

```asm
0x40c810  call    check_managed_app
0x40c815  push    2
0x40c817  mov     dword_40F138, eax
0x40c81c  call    __get_image_app_type
0x40c821  push    eax; Type
0x40c822  call    ds:__imp____set_app_type
0x40c828  pop     ecx
0x40c829  pop     ecx
0x40c82a  mov     ___onexitend, 0FFFFFFFFh
0x40c834  mov     ___onexitbegin, 0FFFFFFFFh
0x40c83e  call    ds:__imp____p__fmode
0x40c844  mov     ecx, __fmode
0x40c84a  mov     [eax], ecx
0x40c84c  call    ds:__imp____p__commode
0x40c852  mov     ecx, __commode
0x40c858  mov     [eax], ecx
0x40c85a  call    __wsetargv
0x40c85f  cmp     ___defaultmatherr, 0
0x40c866  jnz     short loc_40C874
0x40c868  push    offset __wsetargv; UserMathErrorFunction
0x40c86d  call    ds:__imp____setusermatherr
0x40c873  pop     ecx
0x40c874  call    __setdefaultprecision
0x40c879  xor     eax, eax
0x40c87b  retn
```
