# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x1800dfd40`
- end: `0x1800dfe1b`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `219`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800d95a0`
- `0x1800e0370`
- `0x1800e0450`

## callees

- `0x180005890`
- `0x1800dfd40`
- `0x1800eb010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800dfdaa`
- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x1800dfdaa`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800dfe03`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1800dfe03`

## pseudocode

```c
bool __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  __int64 v2; // rcx
  int v3; // eax
  int v4; // eax
  __int64 v6; // rdi
  _BYTE *v7; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v8[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v9; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  if ( (*(unsigned __int16 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF) == 0xFFFF )
    return 0;
  v2 = *(_QWORD *)(a1 + 104);
  v7 = 0;
  v3 = std::codecvt<unsigned short,char,_Mbstatet>::unshift(v2, a1 + 116, v8, &v9, &v7);
  if ( v3 )
  {
    v4 = v3 - 1;
    if ( v4 )
    {
      if ( v4 == 2 )
      {
        *(_BYTE *)(a1 + 114) = 0;
        return 1;
      }
      return 0;
    }
  }
  else
  {
    *(_BYTE *)(a1 + 114) = 0;
  }
  if ( v7 == v8 )
    return *(_BYTE *)(a1 + 114) == 0;
  v6 = v7 - v8;
  if ( v6 == _o_fwrite(v8, 1, v7 - v8, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x1800dfd40  mov     [rsp+arg_8], rbx
0x1800dfd45  push    rdi
0x1800dfd46  sub     rsp, 60h
0x1800dfd4a  mov     rax, cs:__security_cookie
0x1800dfd51  xor     rax, rsp
0x1800dfd54  mov     [rsp+68h+var_10], rax
0x1800dfd59  cmp     qword ptr [rcx+68h], 0
0x1800dfd5e  mov     rbx, rcx
0x1800dfd61  jz      short loc_1800DFDC2
0x1800dfd63  cmp     byte ptr [rcx+72h], 0
0x1800dfd67  jz      short loc_1800DFDC2
0x1800dfd69  mov     rax, [rcx]
0x1800dfd6c  mov     edi, 0FFFFh
0x1800dfd71  mov     edx, edi
0x1800dfd73  mov     rax, [rax+18h]
0x1800dfd77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dfd7c  cmp     di, ax
0x1800dfd7f  jz      loc_1800DFE17
0x1800dfd85  mov     rcx, [rbx+68h]
0x1800dfd89  lea     rax, [rsp+68h+var_38]
0x1800dfd8e  lea     rdx, [rbx+74h]
0x1800dfd92  mov     [rsp+68h+var_48], rax
0x1800dfd97  lea     r9, [rsp+68h+var_10]
0x1800dfd9c  mov     [rsp+68h+var_38], 0
0x1800dfda5  lea     r8, [rsp+68h+var_30]
0x1800dfdaa  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x1800dfdb0  test    eax, eax
0x1800dfdb2  jz      short loc_1800DFDDC
0x1800dfdb4  sub     eax, 1
0x1800dfdb7  jz      short loc_1800DFDE0
0x1800dfdb9  cmp     eax, 2
0x1800dfdbc  jnz     short loc_1800DFE17
0x1800dfdbe  mov     byte ptr [rbx+72h], 0
0x1800dfdc2  mov     al, 1
0x1800dfdc4  mov     rcx, [rsp+68h+var_10]
0x1800dfdc9  xor     rcx, rsp; StackCookie
0x1800dfdcc  call    __security_check_cookie
0x1800dfdd1  mov     rbx, [rsp+68h+arg_8]
0x1800dfdd6  add     rsp, 60h
0x1800dfdda  pop     rdi
0x1800dfddb  retn
0x1800dfddc  mov     byte ptr [rbx+72h], 0
0x1800dfde0  mov     rdi, [rsp+68h+var_38]
0x1800dfde5  lea     rax, [rsp+68h+var_30]
0x1800dfdea  sub     rdi, rax
0x1800dfded  jz      short loc_1800DFE0E
0x1800dfdef  mov     r9, [rbx+80h]
0x1800dfdf6  lea     rcx, [rsp+68h+var_30]
0x1800dfdfb  mov     r8, rdi
0x1800dfdfe  mov     edx, 1
0x1800dfe03  call    cs:__imp__o_fwrite
0x1800dfe09  cmp     rdi, rax
0x1800dfe0c  jnz     short loc_1800DFE17
0x1800dfe0e  cmp     byte ptr [rbx+72h], 0
0x1800dfe12  setz    al
0x1800dfe15  jmp     short loc_1800DFDC4
0x1800dfe17  xor     al, al
0x1800dfe19  jmp     short loc_1800DFDC4
```
