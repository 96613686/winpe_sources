# pre_c_init

- ea: `0x140002d40`
- end: `0x140002e17`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002d40`
- `0x140003124`
- `0x14001d910`

## import_xrefs

- `msvcrt!__setusermatherr` at `0x140002e0a`
- `msvcrt!__setusermatherr` at `0x140002e0a`
- `msvcrt!__set_app_type` at `0x140002dbf`
- `msvcrt!__set_app_type` at `0x140002dbf`
- `msvcrt!_commode` at `0x140002de6`
- `msvcrt!_fmode` at `0x140002ddd`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( MEMORY[0x140000000] != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
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
  dword_1400525C0 = v0;
  image_app_type = (unsigned int)get_image_app_type(1);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  KerbIumDHKeyAgreement::GetAlgorithmId(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(KerbIumDHKeyAgreement::GetAlgorithmId);
  return 0;
}

```

## disassembly

```asm
0x140002d40  sub     rsp, 28h
0x140002d44  mov     eax, 5A4Dh
0x140002d49  cmp     cs:140000000h, ax
0x140002d50  jz      short loc_140002D56
0x140002d52  xor     eax, eax
0x140002d54  jmp     short loc_140002DAD
0x140002d56  movsxd  rcx, dword ptr cs:14000003Ch
0x140002d5d  lea     rdx, cs:140000000h
0x140002d64  cmp     dword ptr [rcx+rdx], 4550h
0x140002d6b  jnz     short loc_140002D52
0x140002d6d  mov     eax, 10Bh
0x140002d72  cmp     [rcx+rdx+18h], ax
0x140002d77  jz      short loc_140002D9A
0x140002d79  mov     eax, 20Bh
0x140002d7e  cmp     [rcx+rdx+18h], ax
0x140002d83  jnz     short loc_140002D52
0x140002d85  xor     eax, eax
0x140002d87  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140002d8f  jbe     short loc_140002DAD
0x140002d91  cmp     [rcx+rdx+0F8h], eax
0x140002d98  jmp     short loc_140002DAA
0x140002d9a  xor     eax, eax
0x140002d9c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140002da1  jbe     short loc_140002DAD
0x140002da3  cmp     [rcx+rdx+0E8h], eax
0x140002daa  setnz   al
0x140002dad  mov     ecx, 1
0x140002db2  mov     cs:dword_1400525C0, eax
0x140002db8  call    _get_image_app_type
0x140002dbd  mov     ecx, eax; Type
0x140002dbf  call    cs:__imp___set_app_type
0x140002dc5  mov     ecx, cs:_fmode
0x140002dcb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140002dcf  mov     cs:__onexitend, rax
0x140002dd6  mov     cs:__onexitbegin, rax
0x140002ddd  mov     rax, cs:__imp__fmode
0x140002de4  mov     [rax], ecx
0x140002de6  mov     rcx, cs:__imp__commode; struct _exception *
0x140002ded  mov     eax, cs:_commode
0x140002df3  mov     [rcx], eax
0x140002df5  call    ?GetAlgorithmId@KerbIumDHKeyAgreement@@UEAAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; KerbIumDHKeyAgreement::GetAlgorithmId(void)
0x140002dfa  cmp     cs:__defaultmatherr, 0
0x140002e01  jnz     short loc_140002E10
0x140002e03  lea     rcx, ?GetAlgorithmId@KerbIumDHKeyAgreement@@UEAAPEAUKERB_ALGORITHM_IDENTIFIER@@XZ; UserMathErrorFunction
0x140002e0a  call    cs:__imp___setusermatherr
0x140002e10  xor     eax, eax
0x140002e12  add     rsp, 28h
0x140002e16  retn
```
