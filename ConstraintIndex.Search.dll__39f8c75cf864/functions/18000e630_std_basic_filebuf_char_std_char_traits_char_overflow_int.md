# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18000e630`
- end: `0x18000e7b4`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `388`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800049e0`
- `0x18000c938`
- `0x18000e200`
- `0x18000e5a0`
- `0x18000e630`
- `0x18000f2a8`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18000e6e9`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18000e6e9`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000e774`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18000e774`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, __int64 a2)
{
  unsigned int v2; // esi
  unsigned int v4; // ebx
  unsigned int v5; // edx
  unsigned __int64 v7; // rcx
  int *v8; // rdx
  __int64 v9; // r8
  char v10; // al
  _BYTE *v11; // rdx
  char v12; // al
  __int64 v13; // r10
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  __int64 v17; // r14
  _BYTE *v18; // [rsp+50h] [rbp+7h] BYREF
  char *v19; // [rsp+58h] [rbp+Fh] BYREF
  char v20; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v21[7]; // [rsp+61h] [rbp+18h] BYREF
  _BYTE v22[32]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v23; // [rsp+88h] [rbp+3Fh] BYREF

  v2 = -1;
  v4 = a2;
  if ( (unsigned __int8)std::_Narrow_char_traits<char,int>::eq_int_type(0xFFFFFFFFLL, a2) )
    return std::_Narrow_char_traits<char,int>::not_eof(v5);
  v7 = **(_QWORD **)(a1 + 64);
  if ( v7 )
  {
    v8 = *(int **)(a1 + 88);
    v9 = *v8;
    if ( v7 < v7 + v9 )
    {
      *v8 = v9 - 1;
      ++**(_QWORD **)(a1 + 64);
      v10 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
      *v11 = v10;
      return v4;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    v12 = std::_Narrow_char_traits<char,int>::to_char_type(v4);
    if ( !v13 )
    {
      v14 = (unsigned int)v12;
      goto LABEL_10;
    }
    v20 = v12;
    v19 = 0;
    v18 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, char *, _BYTE *, char **, _BYTE *, __int64 *, _BYTE **))(*(_QWORD *)v13 + 56LL))(
            v13,
            a1 + 116,
            &v20,
            v21,
            &v19,
            v22,
            &v23,
            &v18);
    if ( v15 && (v16 = v15 - 1) != 0 )
    {
      if ( v16 == 2 )
      {
        v14 = (unsigned int)v20;
LABEL_10:
        if ( (unsigned int)_o_fputc(v14, *(_QWORD *)(a1 + 128)) == -1 )
          return (unsigned int)-1;
        return v4;
      }
    }
    else if ( v18 == v22 || (v17 = v18 - v22, v17 == _o_fwrite(v22, 1, v18 - v22, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 113) = 1;
      if ( v19 != &v20 )
        return v4;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000e630  mov     [rsp-8+arg_10], rbx
0x18000e635  mov     [rsp-8+arg_18], rsi
0x18000e63a  push    rbp
0x18000e63b  push    rdi
0x18000e63c  push    r14
0x18000e63e  lea     rbp, [rsp-47h]
0x18000e643  sub     rsp, 90h
0x18000e64a  mov     rax, cs:__security_cookie
0x18000e651  xor     rax, rsp
0x18000e654  mov     [rbp+57h+var_18], rax
0x18000e658  or      esi, 0FFFFFFFFh
0x18000e65b  mov     rdi, rcx
0x18000e65e  mov     ecx, esi
0x18000e660  mov     ebx, edx
0x18000e662  call    ?eq_int_type@?$_Narrow_char_traits@DH@std@@SA_NHH@Z; std::_Narrow_char_traits<char,int>::eq_int_type(int,int)
0x18000e667  xor     r14d, r14d
0x18000e66a  test    al, al
0x18000e66c  jz      short loc_18000E67A
0x18000e66e  mov     ecx, edx
0x18000e670  call    ?not_eof@?$_Narrow_char_traits@DH@std@@SAHH@Z; std::_Narrow_char_traits<char,int>::not_eof(int)
0x18000e675  jmp     loc_18000E790
0x18000e67a  mov     rax, [rdi+40h]
0x18000e67e  mov     rcx, [rax]
0x18000e681  test    rcx, rcx
0x18000e684  jz      short loc_18000E6BA
0x18000e686  mov     rdx, [rdi+58h]
0x18000e68a  movsxd  r8, dword ptr [rdx]
0x18000e68d  lea     rax, [rcx+r8]
0x18000e691  cmp     rcx, rax
0x18000e694  jnb     short loc_18000E6BA
0x18000e696  lea     eax, [r8-1]
0x18000e69a  mov     [rdx], eax
0x18000e69c  mov     rcx, [rdi+40h]
0x18000e6a0  mov     rdx, [rcx]
0x18000e6a3  lea     rax, [rdx+1]
0x18000e6a7  mov     [rcx], rax
0x18000e6aa  mov     ecx, ebx
0x18000e6ac  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x18000e6b1  mov     [rdx], al
0x18000e6b3  mov     eax, ebx
0x18000e6b5  jmp     loc_18000E790
0x18000e6ba  cmp     [rdi+80h], r14
0x18000e6c1  jz      loc_18000E78E
0x18000e6c7  mov     rcx, rdi
0x18000e6ca  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18000e6cf  mov     r10, [rdi+68h]
0x18000e6d3  mov     ecx, ebx
0x18000e6d5  call    ?to_char_type@?$_Narrow_char_traits@DH@std@@SADH@Z; std::_Narrow_char_traits<char,int>::to_char_type(int)
0x18000e6da  test    r10, r10
0x18000e6dd  jnz     short loc_18000E6F6
0x18000e6df  movsx   ecx, al
0x18000e6e2  mov     rdx, [rdi+80h]
0x18000e6e9  call    cs:__imp__o_fputc
0x18000e6ef  cmp     eax, esi
0x18000e6f1  cmovz   ebx, esi
0x18000e6f4  jmp     short loc_18000E6B3
0x18000e6f6  mov     [rbp+57h+var_40], al
0x18000e6f9  lea     rcx, [rbp+57h+var_50]
0x18000e6fd  mov     [rsp+0A0h+var_68], rcx
0x18000e702  lea     rdx, [rdi+74h]
0x18000e706  lea     rcx, [rbp+57h+var_18]
0x18000e70a  mov     [rbp+57h+var_48], r14
0x18000e70e  mov     [rsp+0A0h+var_70], rcx
0x18000e713  lea     r9, [rbp+57h+var_3F]
0x18000e717  lea     rcx, [rbp+57h+var_38]
0x18000e71b  mov     [rbp+57h+var_50], r14
0x18000e71f  mov     rax, [r10]
0x18000e722  lea     r8, [rbp+57h+var_40]
0x18000e726  mov     [rsp+0A0h+var_78], rcx
0x18000e72b  lea     rcx, [rbp+57h+var_48]
0x18000e72f  mov     [rsp+0A0h+var_80], rcx
0x18000e734  mov     rcx, r10
0x18000e737  mov     rax, [rax+38h]
0x18000e73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e740  test    eax, eax
0x18000e742  jz      short loc_18000E754
0x18000e744  sub     eax, 1
0x18000e747  jz      short loc_18000E754
0x18000e749  cmp     eax, 2
0x18000e74c  jnz     short loc_18000E78E
0x18000e74e  movsx   ecx, [rbp+57h+var_40]
0x18000e752  jmp     short loc_18000E6E2
0x18000e754  mov     r14, [rbp+57h+var_50]
0x18000e758  lea     rax, [rbp+57h+var_38]
0x18000e75c  sub     r14, rax
0x18000e75f  jz      short loc_18000E77F
0x18000e761  mov     r9, [rdi+80h]
0x18000e768  lea     rcx, [rbp+57h+var_38]
0x18000e76c  mov     r8, r14
0x18000e76f  mov     edx, 1
0x18000e774  call    cs:__imp__o_fwrite
0x18000e77a  cmp     r14, rax
0x18000e77d  jnz     short loc_18000E78E
0x18000e77f  lea     rax, [rbp+57h+var_40]
0x18000e783  mov     byte ptr [rdi+71h], 1
0x18000e787  cmp     [rbp+57h+var_48], rax
0x18000e78b  cmovnz  esi, ebx
0x18000e78e  mov     eax, esi
0x18000e790  mov     rcx, [rbp+57h+var_18]
0x18000e794  xor     rcx, rsp; StackCookie
0x18000e797  call    __security_check_cookie
0x18000e79c  lea     r11, [rsp+0A0h+var_10]
0x18000e7a4  mov     rbx, [r11+30h]
0x18000e7a8  mov     rsi, [r11+38h]
0x18000e7ac  mov     rsp, r11
0x18000e7af  pop     r14
0x18000e7b1  pop     rdi
0x18000e7b2  pop     rbp
0x18000e7b3  retn
```
