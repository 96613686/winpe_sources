# std::basic_filebuf<ushort,std::char_traits<ushort>>::_Endwrite(void)

- ea: `0x14000f854`
- end: `0x14000f938`
- name: `?_Endwrite@?$basic_filebuf@GU?$char_traits@G@std@@@std@@IEAA_NXZ`
- size: `228`
- prototype: `bool __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140009edc`
- `0x1400103f0`
- `0x140010660`

## callees

- `0x140002210`
- `0x14000793c`
- `0x14000f854`
- `0x140012010`

## import_xrefs

- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14000f8c7`
- `msvcp_win!?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z` at `0x14000f8c7`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14000f920`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x14000f920`

## pseudocode

```c
bool __fastcall std::basic_filebuf<unsigned short>::_Endwrite(__int64 a1)
{
  unsigned __int16 v2; // ax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  __int64 v7; // rdi
  _BYTE *v8; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v10; // [rsp+58h] [rbp-10h] BYREF

  if ( !*(_QWORD *)(a1 + 104) || !*(_BYTE *)(a1 + 114) )
    return 1;
  v2 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 24LL))(a1, 0xFFFF);
  if ( (unsigned __int8)std::_WChar_traits<unsigned short>::eq_int_type(0xFFFF, v2) )
    return 0;
  v3 = *(_QWORD *)(a1 + 104);
  v8 = 0;
  v4 = std::codecvt<unsigned short,char,_Mbstatet>::unshift(v3, a1 + 116, v9, &v10, &v8);
  if ( v4 )
  {
    v5 = v4 - 1;
    if ( v5 )
    {
      if ( v5 == 2 )
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
  if ( v8 == v9 )
    return *(_BYTE *)(a1 + 114) == 0;
  v7 = v8 - v9;
  if ( v7 == _o_fwrite(v9, 1, v8 - v9, *(_QWORD *)(a1 + 128)) )
    return *(_BYTE *)(a1 + 114) == 0;
  return 0;
}

```

## disassembly

```asm
0x14000f854  mov     [rsp+arg_8], rbx
0x14000f859  push    rdi
0x14000f85a  sub     rsp, 60h
0x14000f85e  mov     rax, cs:__security_cookie
0x14000f865  xor     rax, rsp
0x14000f868  mov     [rsp+68h+var_10], rax
0x14000f86d  cmp     qword ptr [rcx+68h], 0
0x14000f872  mov     rbx, rcx
0x14000f875  jz      short loc_14000F8DF
0x14000f877  cmp     byte ptr [rcx+72h], 0
0x14000f87b  jz      short loc_14000F8DF
0x14000f87d  mov     rax, [rcx]
0x14000f880  mov     edi, 0FFFFh
0x14000f885  mov     edx, edi
0x14000f887  mov     rax, [rax+18h]
0x14000f88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f890  movzx   edx, ax
0x14000f893  mov     ecx, edi
0x14000f895  call    ?eq_int_type@?$_WChar_traits@G@std@@SA_NGG@Z; std::_WChar_traits<ushort>::eq_int_type(ushort,ushort)
0x14000f89a  test    al, al
0x14000f89c  jnz     loc_14000F934
0x14000f8a2  mov     rcx, [rbx+68h]
0x14000f8a6  lea     rax, [rsp+68h+var_38]
0x14000f8ab  lea     rdx, [rbx+74h]
0x14000f8af  mov     [rsp+68h+var_48], rax
0x14000f8b4  lea     r9, [rsp+68h+var_10]
0x14000f8b9  mov     [rsp+68h+var_38], 0
0x14000f8c2  lea     r8, [rsp+68h+var_30]
0x14000f8c7  call    cs:__imp_?unshift@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEAD1AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::unshift(_Mbstatet &,char *,char *,char * &)
0x14000f8cd  test    eax, eax
0x14000f8cf  jz      short loc_14000F8F9
0x14000f8d1  sub     eax, 1
0x14000f8d4  jz      short loc_14000F8FD
0x14000f8d6  cmp     eax, 2
0x14000f8d9  jnz     short loc_14000F934
0x14000f8db  mov     byte ptr [rbx+72h], 0
0x14000f8df  mov     al, 1
0x14000f8e1  mov     rcx, [rsp+68h+var_10]
0x14000f8e6  xor     rcx, rsp; StackCookie
0x14000f8e9  call    __security_check_cookie
0x14000f8ee  mov     rbx, [rsp+68h+arg_8]
0x14000f8f3  add     rsp, 60h
0x14000f8f7  pop     rdi
0x14000f8f8  retn
0x14000f8f9  mov     byte ptr [rbx+72h], 0
0x14000f8fd  mov     rdi, [rsp+68h+var_38]
0x14000f902  lea     rax, [rsp+68h+var_30]
0x14000f907  sub     rdi, rax
0x14000f90a  jz      short loc_14000F92B
0x14000f90c  mov     r9, [rbx+80h]
0x14000f913  lea     rcx, [rsp+68h+var_30]
0x14000f918  mov     r8, rdi
0x14000f91b  mov     edx, 1
0x14000f920  call    cs:__imp__o_fwrite
0x14000f926  cmp     rdi, rax
0x14000f929  jnz     short loc_14000F934
0x14000f92b  cmp     byte ptr [rbx+72h], 0
0x14000f92f  setz    al
0x14000f932  jmp     short loc_14000F8E1
0x14000f934  xor     al, al
0x14000f936  jmp     short loc_14000F8E1
```
