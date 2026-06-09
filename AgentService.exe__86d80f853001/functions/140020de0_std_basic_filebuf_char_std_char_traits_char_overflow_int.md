# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x140020de0`
- end: `0x140020f66`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `390`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003e50`
- `0x140020de0`

## import_xrefs

- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x140020eec`
- `msvcp_win!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x140020eec`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x140020ea3`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x140020ea3`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140020f26`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x140020f26`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned int v2; // edi
  __int64 result; // rax
  _QWORD *v6; // rax
  int *v7; // rdx
  _QWORD *v8; // rdx
  _BYTE *v9; // r8
  _QWORD *v10; // r8
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  bool v15; // zf
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  char v19; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[7]; // [rsp+41h] [rbp-3Fh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  char *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  if ( a2 == -1 )
    return 0;
  v6 = *(_QWORD **)(a1 + 64);
  if ( *v6 )
  {
    v7 = *(int **)(a1 + 88);
    if ( *v6 < (unsigned __int64)(*v6 + *v7) )
    {
      result = a2;
      --*v7;
      v8 = *(_QWORD **)(a1 + 64);
      v9 = (_BYTE *)(*v8)++;
      *v9 = a2;
      return result;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v10 = *(_QWORD **)(a1 + 24);
    if ( *v10 == a1 + 112 )
    {
      v11 = *(_QWORD *)(a1 + 136);
      v12 = *(_QWORD *)(a1 + 144);
      *v10 = v11;
      **(_QWORD **)(a1 + 56) = v11;
      **(_DWORD **)(a1 + 80) = v12 - v11;
    }
    v13 = *(_QWORD *)(a1 + 104);
    if ( !v13 )
    {
      v14 = (unsigned int)(char)a2;
LABEL_11:
      v15 = (unsigned int)_o_fputc(v14, *(_QWORD *)(a1 + 128)) == -1;
LABEL_19:
      if ( !v15 )
        return a2;
      return v2;
    }
    v19 = a2;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<char,char,_Mbstatet>::out(v13, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      if ( v21 != v23 )
      {
        v18 = v21 - v23;
        if ( v18 != _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128)) )
          return v2;
      }
      *(_BYTE *)(a1 + 113) = 1;
      v15 = v22 == &v19;
      goto LABEL_19;
    }
    if ( v17 == 2 )
    {
      v14 = (unsigned int)v19;
      goto LABEL_11;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140020de0  mov     [rsp-18h+arg_10], rbx
0x140020de5  mov     [rsp-18h+arg_18], rsi
0x140020dea  push    rbp
0x140020deb  push    rdi
0x140020dec  push    r14
0x140020dee  mov     rbp, rsp
0x140020df1  sub     rsp, 80h
0x140020df8  mov     rax, cs:__security_cookie
0x140020dff  xor     rax, rsp
0x140020e02  mov     [rbp+var_8], rax
0x140020e06  or      edi, 0FFFFFFFFh
0x140020e09  mov     esi, edx
0x140020e0b  mov     rbx, rcx
0x140020e0e  cmp     edx, edi
0x140020e10  jnz     short loc_140020E19
0x140020e12  xor     eax, eax
0x140020e14  jmp     loc_140020F42
0x140020e19  mov     rax, [rcx+40h]
0x140020e1d  xor     r14d, r14d
0x140020e20  cmp     [rax], r14
0x140020e23  jz      short loc_140020E55
0x140020e25  mov     rdx, [rcx+58h]
0x140020e29  movsxd  r8, dword ptr [rdx]
0x140020e2c  mov     rcx, r8
0x140020e2f  add     rcx, [rax]
0x140020e32  cmp     [rax], rcx
0x140020e35  jnb     short loc_140020E55
0x140020e37  lea     ecx, [r8-1]
0x140020e3b  mov     eax, esi
0x140020e3d  mov     [rdx], ecx
0x140020e3f  mov     rdx, [rbx+40h]
0x140020e43  mov     r8, [rdx]
0x140020e46  lea     rcx, [r8+1]
0x140020e4a  mov     [rdx], rcx
0x140020e4d  mov     [r8], sil
0x140020e50  jmp     loc_140020F42
0x140020e55  cmp     [rbx+80h], r14
0x140020e5c  jz      loc_140020F40
0x140020e62  mov     r8, [rbx+18h]
0x140020e66  lea     rax, [rbx+70h]
0x140020e6a  cmp     [r8], rax
0x140020e6d  jnz     short loc_140020E8F
0x140020e6f  mov     rcx, [rbx+88h]
0x140020e76  mov     rdx, [rbx+90h]
0x140020e7d  mov     [r8], rcx
0x140020e80  sub     edx, ecx
0x140020e82  mov     rax, [rbx+38h]
0x140020e86  mov     [rax], rcx
0x140020e89  mov     rax, [rbx+50h]
0x140020e8d  mov     [rax], edx
0x140020e8f  mov     rcx, [rbx+68h]
0x140020e93  test    rcx, rcx
0x140020e96  jnz     short loc_140020EB0
0x140020e98  movsx   ecx, sil
0x140020e9c  mov     rdx, [rbx+80h]
0x140020ea3  call    cs:__imp__o_fputc
0x140020ea9  cmp     eax, edi
0x140020eab  jmp     loc_140020F3D
0x140020eb0  lea     rax, [rbp+var_38]
0x140020eb4  mov     [rbp+var_40], sil
0x140020eb8  mov     [rsp+80h+var_48], rax
0x140020ebd  lea     rdx, [rbx+74h]
0x140020ec1  lea     rax, [rbp+var_8]
0x140020ec5  mov     [rbp+var_30], r14
0x140020ec9  mov     [rsp+80h+var_50], rax
0x140020ece  lea     r9, [rbp+var_3F]
0x140020ed2  lea     rax, [rbp+var_28]
0x140020ed6  mov     [rbp+var_38], r14
0x140020eda  mov     [rsp+80h+var_58], rax
0x140020edf  lea     r8, [rbp+var_40]
0x140020ee3  lea     rax, [rbp+var_30]
0x140020ee7  mov     [rsp+80h+var_60], rax
0x140020eec  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x140020ef2  test    eax, eax
0x140020ef4  jz      short loc_140020F06
0x140020ef6  sub     eax, 1
0x140020ef9  jz      short loc_140020F06
0x140020efb  cmp     eax, 2
0x140020efe  jnz     short loc_140020F40
0x140020f00  movsx   ecx, [rbp+var_40]
0x140020f04  jmp     short loc_140020E9C
0x140020f06  mov     r14, [rbp+var_38]
0x140020f0a  lea     rax, [rbp+var_28]
0x140020f0e  sub     r14, rax
0x140020f11  jz      short loc_140020F31
0x140020f13  mov     r9, [rbx+80h]
0x140020f1a  lea     rcx, [rbp+var_28]
0x140020f1e  mov     r8, r14
0x140020f21  mov     edx, 1
0x140020f26  call    cs:__imp__o_fwrite
0x140020f2c  cmp     r14, rax
0x140020f2f  jnz     short loc_140020F40
0x140020f31  lea     rax, [rbp+var_40]
0x140020f35  mov     byte ptr [rbx+71h], 1
0x140020f39  cmp     [rbp+var_30], rax
0x140020f3d  cmovnz  edi, esi
0x140020f40  mov     eax, edi
0x140020f42  mov     rcx, [rbp+var_8]
0x140020f46  xor     rcx, rsp; StackCookie
0x140020f49  call    __security_check_cookie
0x140020f4e  lea     r11, [rsp+80h+var_s0]
0x140020f56  mov     rbx, [r11+30h]
0x140020f5a  mov     rsi, [r11+38h]
0x140020f5e  mov     rsp, r11
0x140020f61  pop     r14
0x140020f63  pop     rdi
0x140020f64  pop     rbp
0x140020f65  retn
```
