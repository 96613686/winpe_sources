# patternCompare

- ea: `0x18005b544`
- end: `0x18005b909`
- name: `patternCompare`
- size: `965`
- prototype: `__int64 __fastcall(_BYTE *, char *, unsigned __int8 *, unsigned int)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800158e8`
- `0x18005b544`
- `0x180068280`
- `0x1800794b0`
- `0x1800900c0`

## callees

- `0x18005b544`
- `0x18005b910`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x18005b87b`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x18005b87b`

## pseudocode

```c
__int64 __fastcall patternCompare(_BYTE *a1, char *a2, unsigned __int8 *a3, unsigned int a4)
{
  int v4; // r12d
  unsigned int v5; // r14d
  int v6; // eax
  char *v8; // rsi
  _BYTE *v9; // rdi
  _BYTE *v10; // r13
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // esi
  int v16; // ebx
  int v17; // r14d
  unsigned int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 result; // rax
  unsigned int v22; // ebx
  unsigned int v23; // eax
  char *v24; // rbx
  unsigned __int8 v25; // al
  char *v26; // rcx
  char *v27; // rbx
  char *v28; // rbx
  char *v29; // rsi
  int v30; // eax
  _BYTE *Control; // [rsp+60h] [rbp+40h] BYREF
  char *Str; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v33; // [rsp+78h] [rbp+58h]

  v33 = a4;
  Str = a2;
  Control = a1;
  v4 = a3[1];
  v5 = a4;
  v6 = *a3;
  v8 = a2;
  v9 = a1;
  v10 = 0;
  while ( 1 )
  {
    if ( *v9 >= 0x80u )
    {
      v12 = sqlite3Utf8Read(&Control);
      v9 = Control;
      v11 = v12;
      v6 = *a3;
    }
    else
    {
      v11 = (unsigned __int8)*v9++;
      Control = v9;
    }
    if ( !v11 )
      return *v8 != 0;
    if ( v11 == v6 )
    {
      while ( 1 )
      {
        if ( *v9 >= 0x80u )
        {
          v23 = sqlite3Utf8Read(&Control);
          v9 = Control;
          v22 = v23;
          v6 = *a3;
        }
        else
        {
          v22 = (unsigned __int8)*v9++;
          Control = v9;
        }
        if ( v22 != v6 && (v22 != v4 || !v4) )
          break;
        if ( v22 == v4 )
        {
          if ( !(unsigned int)sqlite3Utf8Read(&Str) )
            return 2;
          v6 = *a3;
        }
      }
      if ( !v22 )
        return 0;
      if ( v22 == v5 )
      {
        if ( a3[2] )
        {
          v24 = Str;
          while ( *v24 )
          {
            result = patternCompare(v9 - 1, v24, a3, v5);
            if ( (_DWORD)result != 1 )
              return result;
            v25 = *v24++;
            if ( v25 >= 0xC0u && (*v24 & 0xC0) == 0x80 )
            {
              v26 = v24 + 1;
              do
                v24 = v26++;
              while ( (*v24 & 0xC0) == 0x80 );
            }
          }
        }
        else
        {
          v22 = sqlite3Utf8Read(&Control);
          if ( v22 )
          {
            v9 = Control;
            goto LABEL_59;
          }
        }
      }
      else
      {
LABEL_59:
        if ( v22 >= 0x80 )
        {
          v29 = Str;
          while ( 1 )
          {
            if ( (unsigned __int8)*v29 >= 0x80u )
            {
              v30 = sqlite3Utf8Read(&Str);
              v29 = Str;
            }
            else
            {
              v30 = (unsigned __int8)*v29++;
              Str = v29;
            }
            if ( !v30 )
              break;
            if ( v30 == v22 )
            {
              result = patternCompare(v9, v29, a3, v5);
              if ( (_DWORD)result != 1 )
                return result;
            }
          }
        }
        else
        {
          if ( a3[3] )
          {
            BYTE2(Control) = 0;
            LOBYTE(Control) = v22 & ~(*((_BYTE *)&qword_18009E630 + (unsigned __int8)v22) & 0x20);
            BYTE1(Control) = *((_BYTE *)qword_18009E760 + (unsigned __int8)v22);
          }
          else
          {
            LOWORD(Control) = (unsigned __int8)v22;
          }
          v27 = Str;
          while ( 1 )
          {
            v28 = &v27[strcspn(v27, (const char *)&Control)];
            if ( !*v28 )
              break;
            v27 = v28 + 1;
            result = patternCompare(v9, v27, a3, v5);
            if ( (_DWORD)result != 1 )
              return result;
          }
        }
      }
      return 2;
    }
    if ( v11 == v5 )
    {
      if ( !a3[2] )
      {
        v11 = sqlite3Utf8Read(&Control);
        if ( !v11 )
          return 1;
        v9 = Control;
        v10 = Control;
        goto LABEL_11;
      }
      v14 = sqlite3Utf8Read(&Str);
      if ( !v14 )
        return 1;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = sqlite3Utf8Read(&Control);
      if ( v18 == 94 )
      {
        v17 = 1;
        v18 = sqlite3Utf8Read(&Control);
      }
      if ( v18 == 93 )
      {
        v18 = sqlite3Utf8Read(&Control);
        LOBYTE(v16) = v14 == 93;
      }
      if ( !v18 )
        return 1;
      while ( v18 != 93 )
      {
        if ( v18 == 45 && *Control != 93 && *Control && v15 )
        {
          v19 = sqlite3Utf8Read(&Control);
          if ( v14 >= v15 && v14 <= v19 )
            v16 = 1;
          v15 = 0;
        }
        else
        {
          v15 = v18;
          if ( v14 == v18 )
            v16 = 1;
        }
        v18 = sqlite3Utf8Read(&Control);
        if ( !v18 )
          return 1;
      }
      if ( v17 == v16 )
        return 1;
      v8 = Str;
      v9 = Control;
      v5 = v33;
      v6 = *a3;
    }
    else
    {
LABEL_11:
      if ( (unsigned __int8)*v8 >= 0x80u )
      {
        v20 = sqlite3Utf8Read(&Str);
        v8 = Str;
        v13 = v20;
      }
      else
      {
        v13 = (unsigned __int8)*v8++;
        Str = v8;
      }
      v6 = *a3;
      if ( v11 != v13 )
      {
        if ( !a3[3]
          || *((_BYTE *)qword_18009E760 + (unsigned __int8)v11) != *((_BYTE *)qword_18009E760 + (unsigned __int8)v13)
          || v11 >= 0x80
          || (v6 = *a3, v13 >= 0x80) )
        {
          if ( v11 != v4 )
            return 1;
          if ( v9 == v10 )
            return 1;
          v6 = *a3;
          if ( !v13 )
            return 1;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18005b544  mov     rax, rsp
0x18005b547  mov     [rax+18h], rbx
0x18005b54b  mov     [rax+20h], r9d
0x18005b54f  mov     [rax+10h], rdx
0x18005b553  mov     [rax+8], rcx
0x18005b557  push    rbp
0x18005b558  push    rsi
0x18005b559  push    rdi
0x18005b55a  push    r12
0x18005b55c  push    r13
0x18005b55e  push    r14
0x18005b560  push    r15
0x18005b562  mov     rbp, rsp
0x18005b565  sub     rsp, 20h
0x18005b569  movzx   r12d, byte ptr [r8+1]
0x18005b56e  mov     r14d, r9d
0x18005b571  movzx   eax, byte ptr [r8]
0x18005b575  mov     r15, r8
0x18005b578  mov     rsi, rdx
0x18005b57b  mov     rdi, rcx
0x18005b57e  xor     r13d, r13d
0x18005b581  mov     ecx, 1
0x18005b586  cmp     byte ptr [rdi], 80h
0x18005b589  jnb     short loc_18005B597
0x18005b58b  movzx   ebx, byte ptr [rdi]
0x18005b58e  add     rdi, rcx
0x18005b591  mov     [rbp+Control], rdi
0x18005b595  jmp     short loc_18005B5AA
0x18005b597  lea     rcx, [rbp+Control]
0x18005b59b  call    sqlite3Utf8Read
0x18005b5a0  mov     rdi, [rbp+Control]
0x18005b5a4  mov     ebx, eax
0x18005b5a6  movzx   eax, byte ptr [r15]
0x18005b5aa  test    ebx, ebx
0x18005b5ac  jz      loc_18005B8ED
0x18005b5b2  cmp     ebx, eax
0x18005b5b4  jz      loc_18005B751
0x18005b5ba  cmp     ebx, r14d
0x18005b5bd  jnz     short loc_18005B5E0
0x18005b5bf  cmp     byte ptr [r15+2], 0
0x18005b5c4  jnz     short loc_18005B5FD
0x18005b5c6  lea     rcx, [rbp+Control]
0x18005b5ca  call    sqlite3Utf8Read
0x18005b5cf  mov     ebx, eax
0x18005b5d1  test    eax, eax
0x18005b5d3  jz      loc_18005B747
0x18005b5d9  mov     rdi, [rbp+Control]
0x18005b5dd  mov     r13, rdi
0x18005b5e0  cmp     byte ptr [rsi], 80h
0x18005b5e3  jnb     loc_18005B6C9
0x18005b5e9  movzx   edx, byte ptr [rsi]
0x18005b5ec  mov     ecx, 1
0x18005b5f1  add     rsi, rcx
0x18005b5f4  mov     [rbp+Str], rsi
0x18005b5f8  jmp     loc_18005B6DD
0x18005b5fd  lea     rcx, [rbp+Str]
0x18005b601  call    sqlite3Utf8Read
0x18005b606  mov     edi, eax
0x18005b608  test    eax, eax
0x18005b60a  jz      loc_18005B747
0x18005b610  lea     rcx, [rbp+Control]
0x18005b614  xor     esi, esi
0x18005b616  xor     ebx, ebx
0x18005b618  xor     r14d, r14d
0x18005b61b  call    sqlite3Utf8Read
0x18005b620  mov     ecx, eax
0x18005b622  cmp     eax, 5Eh ; '^'
0x18005b625  jnz     short loc_18005B636
0x18005b627  lea     rcx, [rbp+Control]
0x18005b62b  lea     r14d, [rsi+1]
0x18005b62f  call    sqlite3Utf8Read
0x18005b634  mov     ecx, eax
0x18005b636  cmp     ecx, 5Dh ; ']'
0x18005b639  jnz     short loc_18005B64C
0x18005b63b  lea     rcx, [rbp+Control]
0x18005b63f  call    sqlite3Utf8Read
0x18005b644  cmp     edi, 5Dh ; ']'
0x18005b647  mov     ecx, eax
0x18005b649  setz    bl
0x18005b64c  test    ecx, ecx
0x18005b64e  jz      loc_18005B747
0x18005b654  cmp     ecx, 5Dh ; ']'
0x18005b657  jz      short loc_18005B6AB
0x18005b659  cmp     ecx, 2Dh ; '-'
0x18005b65c  jnz     short loc_18005B68B
0x18005b65e  mov     rax, [rbp+Control]
0x18005b662  cmp     byte ptr [rax], 5Dh ; ']'
0x18005b665  jz      short loc_18005B68B
0x18005b667  cmp     byte ptr [rax], 0
0x18005b66a  jz      short loc_18005B68B
0x18005b66c  test    esi, esi
0x18005b66e  jz      short loc_18005B68B
0x18005b670  lea     rcx, [rbp+Control]
0x18005b674  call    sqlite3Utf8Read
0x18005b679  cmp     edi, esi
0x18005b67b  jb      short loc_18005B687
0x18005b67d  cmp     edi, eax
0x18005b67f  mov     eax, 1
0x18005b684  cmovbe  ebx, eax
0x18005b687  xor     esi, esi
0x18005b689  jmp     short loc_18005B697
0x18005b68b  cmp     edi, ecx
0x18005b68d  mov     eax, 1
0x18005b692  mov     esi, ecx
0x18005b694  cmovz   ebx, eax
0x18005b697  lea     rcx, [rbp+Control]
0x18005b69b  call    sqlite3Utf8Read
0x18005b6a0  mov     ecx, eax
0x18005b6a2  test    eax, eax
0x18005b6a4  jnz     short loc_18005B654
0x18005b6a6  jmp     loc_18005B747
0x18005b6ab  cmp     r14d, ebx
0x18005b6ae  jz      loc_18005B747
0x18005b6b4  mov     rsi, [rbp+Str]
0x18005b6b8  mov     rdi, [rbp+Control]
0x18005b6bc  mov     r14d, [rbp+arg_18]
0x18005b6c0  movzx   eax, byte ptr [r15]
0x18005b6c4  jmp     loc_18005B581
0x18005b6c9  lea     rcx, [rbp+Str]
0x18005b6cd  call    sqlite3Utf8Read
0x18005b6d2  mov     rsi, [rbp+Str]
0x18005b6d6  mov     edx, eax
0x18005b6d8  mov     ecx, 1
0x18005b6dd  movzx   eax, byte ptr [r15]
0x18005b6e1  cmp     ebx, edx
0x18005b6e3  jz      loc_18005B586
0x18005b6e9  cmp     byte ptr [r15+3], 0
0x18005b6ee  jz      short loc_18005B72C
0x18005b6f0  lea     r8, cs:180000000h
0x18005b6f7  movzx   eax, dl
0x18005b6fa  movzx   ecx, bl
0x18005b6fd  mov     al, [rax+r8+9E760h]
0x18005b705  cmp     [rcx+r8+9E760h], al
0x18005b70d  jnz     short loc_18005B72C
0x18005b70f  cmp     ebx, 80h
0x18005b715  jnb     short loc_18005B72C
0x18005b717  movzx   eax, byte ptr [r15]
0x18005b71b  mov     ecx, 1
0x18005b720  cmp     edx, 80h
0x18005b726  jb      loc_18005B586
0x18005b72c  cmp     ebx, r12d
0x18005b72f  jnz     short loc_18005B747
0x18005b731  cmp     rdi, r13
0x18005b734  jz      short loc_18005B747
0x18005b736  movzx   eax, byte ptr [r15]
0x18005b73a  mov     ecx, 1
0x18005b73f  test    edx, edx
0x18005b741  jnz     loc_18005B586
0x18005b747  mov     eax, 1
0x18005b74c  jmp     loc_18005B8F4
0x18005b751  cmp     byte ptr [rdi], 80h
0x18005b754  jnb     short loc_18005B768
0x18005b756  movzx   ebx, byte ptr [rdi]
0x18005b759  mov     r13d, 1
0x18005b75f  add     rdi, r13
0x18005b762  mov     [rbp+Control], rdi
0x18005b766  jmp     short loc_18005B781
0x18005b768  lea     rcx, [rbp+Control]
0x18005b76c  call    sqlite3Utf8Read
0x18005b771  mov     rdi, [rbp+Control]
0x18005b775  mov     ebx, eax
0x18005b777  movzx   eax, byte ptr [r15]
0x18005b77b  mov     r13d, 1
0x18005b781  cmp     ebx, eax
0x18005b783  jz      short loc_18005B78F
0x18005b785  cmp     ebx, r12d
0x18005b788  jnz     short loc_18005B7AB
0x18005b78a  test    r12d, r12d
0x18005b78d  jz      short loc_18005B7AB
0x18005b78f  cmp     ebx, r12d
0x18005b792  jnz     short loc_18005B751
0x18005b794  lea     rcx, [rbp+Str]
0x18005b798  call    sqlite3Utf8Read
0x18005b79d  test    eax, eax
0x18005b79f  jz      loc_18005B8E6
0x18005b7a5  movzx   eax, byte ptr [r15]
0x18005b7a9  jmp     short loc_18005B751
0x18005b7ab  test    ebx, ebx
0x18005b7ad  jnz     short loc_18005B7B6
0x18005b7af  xor     eax, eax
0x18005b7b1  jmp     loc_18005B8F4
0x18005b7b6  cmp     ebx, r14d
0x18005b7b9  jnz     short loc_18005B7D9
0x18005b7bb  cmp     byte ptr [r15+2], 0
0x18005b7c0  jnz     short loc_18005B816
0x18005b7c2  lea     rcx, [rbp+Control]
0x18005b7c6  call    sqlite3Utf8Read
0x18005b7cb  mov     ebx, eax
0x18005b7cd  test    eax, eax
0x18005b7cf  jz      loc_18005B8E6
0x18005b7d5  mov     rdi, [rbp+Control]
0x18005b7d9  cmp     ebx, 80h
0x18005b7df  jnb     loc_18005B8A4
0x18005b7e5  cmp     byte ptr [r15+3], 0
0x18005b7ea  jz      short loc_18005B869
0x18005b7ec  movzx   ecx, bl
0x18005b7ef  lea     rdx, cs:180000000h
0x18005b7f6  mov     byte ptr [rbp+Control+2], 0
0x18005b7fa  mov     al, [rcx+rdx+9E630h]
0x18005b801  and     al, 20h
0x18005b803  not     al
0x18005b805  and     al, bl
0x18005b807  mov     byte ptr [rbp+Control], al
0x18005b80a  mov     al, [rcx+rdx+9E760h]
0x18005b811  mov     byte ptr [rbp+Control+1], al
0x18005b814  jmp     short loc_18005B870
0x18005b816  mov     rbx, [rbp+Str]
0x18005b81a  mov     sil, 0C0h
0x18005b81d  cmp     byte ptr [rbx], 0
0x18005b820  jz      loc_18005B8E6
0x18005b826  lea     rcx, [rdi-1]
0x18005b82a  mov     r9d, r14d
0x18005b82d  mov     r8, r15
0x18005b830  mov     rdx, rbx
0x18005b833  call    patternCompare
0x18005b838  cmp     eax, r13d
0x18005b83b  jnz     loc_18005B8F4
0x18005b841  mov     al, [rbx]
0x18005b843  add     rbx, r13
0x18005b846  cmp     al, sil
0x18005b849  jb      short loc_18005B81D
0x18005b84b  mov     al, [rbx]
0x18005b84d  and     al, sil
0x18005b850  cmp     al, 80h
0x18005b852  jnz     short loc_18005B81D
0x18005b854  lea     rcx, [rbx+1]
0x18005b858  mov     rbx, rcx
0x18005b85b  add     rcx, r13
0x18005b85e  mov     al, [rbx]
0x18005b860  and     al, sil
0x18005b863  cmp     al, 80h
0x18005b865  jz      short loc_18005B858
0x18005b867  jmp     short loc_18005B81D
0x18005b869  mov     byte ptr [rbp+Control], bl
0x18005b86c  mov     byte ptr [rbp+Control+1], 0
0x18005b870  mov     rbx, [rbp+Str]
0x18005b874  lea     rdx, [rbp+Control]; Control
0x18005b878  mov     rcx, rbx; Str
0x18005b87b  call    cs:__imp_strcspn
0x18005b881  add     rbx, rax
0x18005b884  cmp     byte ptr [rbx], 0
0x18005b887  jz      short loc_18005B8E6
0x18005b889  inc     rbx
0x18005b88c  mov     r9d, r14d
0x18005b88f  mov     rdx, rbx
0x18005b892  mov     r8, r15
0x18005b895  mov     rcx, rdi
0x18005b898  call    patternCompare
0x18005b89d  cmp     eax, r13d
0x18005b8a0  jz      short loc_18005B874
0x18005b8a2  jmp     short loc_18005B8F4
0x18005b8a4  mov     rsi, [rbp+Str]
0x18005b8a8  cmp     byte ptr [rsi], 80h
0x18005b8ab  jnb     short loc_18005B8B9
0x18005b8ad  movzx   eax, byte ptr [rsi]
0x18005b8b0  add     rsi, r13
0x18005b8b3  mov     [rbp+Str], rsi
0x18005b8b7  jmp     short loc_18005B8C6
0x18005b8b9  lea     rcx, [rbp+Str]
0x18005b8bd  call    sqlite3Utf8Read
0x18005b8c2  mov     rsi, [rbp+Str]
0x18005b8c6  test    eax, eax
0x18005b8c8  jz      short loc_18005B8E6
0x18005b8ca  cmp     eax, ebx
0x18005b8cc  jnz     short loc_18005B8A8
0x18005b8ce  mov     r9d, r14d
0x18005b8d1  mov     r8, r15
0x18005b8d4  mov     rdx, rsi
0x18005b8d7  mov     rcx, rdi
0x18005b8da  call    patternCompare
0x18005b8df  cmp     eax, r13d
0x18005b8e2  jz      short loc_18005B8A8
0x18005b8e4  jmp     short loc_18005B8F4
0x18005b8e6  mov     eax, 2
0x18005b8eb  jmp     short loc_18005B8F4
0x18005b8ed  xor     eax, eax
0x18005b8ef  cmp     [rsi], al
0x18005b8f1  setnz   al
0x18005b8f4  mov     rbx, [rsp+20h+arg_10]
0x18005b8f9  add     rsp, 20h
0x18005b8fd  pop     r15
0x18005b8ff  pop     r14
0x18005b901  pop     r13
0x18005b903  pop     r12
0x18005b905  pop     rdi
0x18005b906  pop     rsi
0x18005b907  pop     rbp
0x18005b908  retn
```
