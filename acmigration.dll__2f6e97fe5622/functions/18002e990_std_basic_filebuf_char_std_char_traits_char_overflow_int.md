# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x18002e990`
- end: `0x18002eb1e`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `398`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001cf0`
- `0x18002e990`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18002ea55`
- `api-ms-win-crt-private-l1-1-0!_o_fputc` at `0x18002ea55`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18002eade`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18002eade`

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
  char v19; // [rsp+50h] [rbp+7h] BYREF
  _BYTE v20[7]; // [rsp+51h] [rbp+8h] BYREF
  _BYTE *v21; // [rsp+58h] [rbp+Fh] BYREF
  char *v22; // [rsp+60h] [rbp+17h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp+1Fh] BYREF
  __int64 v24; // [rsp+88h] [rbp+3Fh] BYREF

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
    v16 = (*(__int64 (__fastcall **)(__int64, __int64, char *, _BYTE *, char **, _BYTE *, __int64 *, _BYTE **))(*(_QWORD *)v13 + 56LL))(
            v13,
            a1 + 116,
            &v19,
            v20,
            &v22,
            v23,
            &v24,
            &v21);
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
0x18002e990  mov     [rsp-8+arg_10], rbx
0x18002e995  mov     [rsp-8+arg_18], rsi
0x18002e99a  push    rbp
0x18002e99b  push    rdi
0x18002e99c  push    r14
0x18002e99e  lea     rbp, [rsp-47h]
0x18002e9a3  sub     rsp, 90h
0x18002e9aa  mov     rax, cs:__security_cookie
0x18002e9b1  xor     rax, rsp
0x18002e9b4  mov     [rbp+57h+var_18], rax
0x18002e9b8  or      edi, 0FFFFFFFFh
0x18002e9bb  mov     esi, edx
0x18002e9bd  mov     rbx, rcx
0x18002e9c0  cmp     edx, edi
0x18002e9c2  jnz     short loc_18002E9CB
0x18002e9c4  xor     eax, eax
0x18002e9c6  jmp     loc_18002EAFA
0x18002e9cb  mov     rax, [rcx+40h]
0x18002e9cf  xor     r14d, r14d
0x18002e9d2  cmp     [rax], r14
0x18002e9d5  jz      short loc_18002EA07
0x18002e9d7  mov     rdx, [rcx+58h]
0x18002e9db  movsxd  r8, dword ptr [rdx]
0x18002e9de  mov     rcx, r8
0x18002e9e1  add     rcx, [rax]
0x18002e9e4  cmp     [rax], rcx
0x18002e9e7  jnb     short loc_18002EA07
0x18002e9e9  lea     ecx, [r8-1]
0x18002e9ed  mov     eax, esi
0x18002e9ef  mov     [rdx], ecx
0x18002e9f1  mov     rdx, [rbx+40h]
0x18002e9f5  mov     r8, [rdx]
0x18002e9f8  lea     rcx, [r8+1]
0x18002e9fc  mov     [rdx], rcx
0x18002e9ff  mov     [r8], sil
0x18002ea02  jmp     loc_18002EAFA
0x18002ea07  cmp     [rbx+80h], r14
0x18002ea0e  jz      loc_18002EAF8
0x18002ea14  mov     r8, [rbx+18h]
0x18002ea18  lea     rax, [rbx+70h]
0x18002ea1c  cmp     [r8], rax
0x18002ea1f  jnz     short loc_18002EA41
0x18002ea21  mov     rcx, [rbx+88h]
0x18002ea28  mov     rdx, [rbx+90h]
0x18002ea2f  mov     [r8], rcx
0x18002ea32  sub     edx, ecx
0x18002ea34  mov     rax, [rbx+38h]
0x18002ea38  mov     [rax], rcx
0x18002ea3b  mov     rax, [rbx+50h]
0x18002ea3f  mov     [rax], edx
0x18002ea41  mov     rcx, [rbx+68h]
0x18002ea45  test    rcx, rcx
0x18002ea48  jnz     short loc_18002EA62
0x18002ea4a  movsx   ecx, sil
0x18002ea4e  mov     rdx, [rbx+80h]
0x18002ea55  call    cs:__imp__o_fputc
0x18002ea5b  cmp     eax, edi
0x18002ea5d  jmp     loc_18002EAF5
0x18002ea62  lea     r8, [rbp+57h+var_48]
0x18002ea66  mov     [rbp+57h+var_50], sil
0x18002ea6a  mov     [rsp+0A0h+var_68], r8
0x18002ea6f  lea     rdx, [rbx+74h]
0x18002ea73  lea     r8, [rbp+57h+var_18]
0x18002ea77  mov     [rbp+57h+var_40], r14
0x18002ea7b  mov     [rsp+0A0h+var_70], r8
0x18002ea80  lea     r9, [rbp+57h+var_4F]
0x18002ea84  lea     r8, [rbp+57h+var_38]
0x18002ea88  mov     [rbp+57h+var_48], r14
0x18002ea8c  mov     rax, [rcx]
0x18002ea8f  mov     [rsp+0A0h+var_78], r8
0x18002ea94  lea     r8, [rbp+57h+var_40]
0x18002ea98  mov     [rsp+0A0h+var_80], r8
0x18002ea9d  lea     r8, [rbp+57h+var_50]
0x18002eaa1  mov     rax, [rax+38h]
0x18002eaa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaaa  test    eax, eax
0x18002eaac  jz      short loc_18002EABE
0x18002eaae  sub     eax, 1
0x18002eab1  jz      short loc_18002EABE
0x18002eab3  cmp     eax, 2
0x18002eab6  jnz     short loc_18002EAF8
0x18002eab8  movsx   ecx, [rbp+57h+var_50]
0x18002eabc  jmp     short loc_18002EA4E
0x18002eabe  mov     r14, [rbp+57h+var_48]
0x18002eac2  lea     rax, [rbp+57h+var_38]
0x18002eac6  sub     r14, rax
0x18002eac9  jz      short loc_18002EAE9
0x18002eacb  mov     r9, [rbx+80h]
0x18002ead2  lea     rcx, [rbp+57h+var_38]
0x18002ead6  mov     r8, r14
0x18002ead9  mov     edx, 1
0x18002eade  call    cs:__imp__o_fwrite
0x18002eae4  cmp     r14, rax
0x18002eae7  jnz     short loc_18002EAF8
0x18002eae9  lea     rax, [rbp+57h+var_50]
0x18002eaed  mov     byte ptr [rbx+71h], 1
0x18002eaf1  cmp     [rbp+57h+var_40], rax
0x18002eaf5  cmovnz  edi, esi
0x18002eaf8  mov     eax, edi
0x18002eafa  mov     rcx, [rbp+57h+var_18]
0x18002eafe  xor     rcx, rsp; StackCookie
0x18002eb01  call    __security_check_cookie
0x18002eb06  lea     r11, [rsp+0A0h+var_10]
0x18002eb0e  mov     rbx, [r11+30h]
0x18002eb12  mov     rsi, [r11+38h]
0x18002eb16  mov     rsp, r11
0x18002eb19  pop     r14
0x18002eb1b  pop     rdi
0x18002eb1c  pop     rbp
0x18002eb1d  retn
```
